# BaseSrvCreatePairWaitHandles

- ea: `0x180009698`
- end: `0x180009728`
- name: `BaseSrvCreatePairWaitHandles`
- size: `144`
- prototype: `NTSTATUS __fastcall(void **, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008644`
- `0x180008d80`
- `0x18000a960`
- `0x18000c088`
- `0x18000c454`

## callees

- `0x180009698`

## import_xrefs

- `ntdll!NtClose` at `0x18000970e`
- `ntdll!NtClose` at `0x18000970e`
- `ntdll!NtDuplicateObject` at `0x1800096f5`
- `ntdll!NtDuplicateObject` at `0x1800096f5`
- `ntdll!NtCreateEvent` at `0x1800096b8`
- `ntdll!NtCreateEvent` at `0x1800096b8`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvCreatePairWaitHandles(void **a1, void **a2)
{
  NTSTATUS result; // eax
  NTSTATUS v5; // edi

  result = NtCreateEvent(a1, 0x1F0003u, 0, NotificationEvent, 0);
  if ( result >= 0 )
  {
    v5 = NtDuplicateObject(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           *a1,
           *(HANDLE *)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL),
           a2,
           0,
           0,
           2u);
    if ( v5 < 0 )
    {
      NtClose(*a1);
      return v5;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009698  mov     [rsp+arg_0], rbx
0x18000969d  push    rdi
0x18000969e  sub     rsp, 40h
0x1800096a2  mov     rdi, rdx
0x1800096a5  mov     [rsp+48h+InitialState], 0; DesiredAccess
0x1800096aa  mov     edx, 1F0003h; DesiredAccess
0x1800096af  xor     r9d, r9d; EventType
0x1800096b2  xor     r8d, r8d; ObjectAttributes
0x1800096b5  mov     rbx, rcx
0x1800096b8  call    cs:__imp_NtCreateEvent
0x1800096bf  nop     dword ptr [rax+rax+00h]
0x1800096c4  test    eax, eax
0x1800096c6  js      short loc_18000971C
0x1800096c8  mov     rax, gs:70h
0x1800096d1  mov     r9, rdi; TargetHandle
0x1800096d4  mov     rdx, [rbx]; SourceHandle
0x1800096d7  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800096db  mov     [rsp+48h+Options], 2; Options
0x1800096e3  and     [rsp+48h+var_20], 0
0x1800096e8  mov     r8, [rax+38h]
0x1800096ec  and     dword ptr [rsp+48h+InitialState], 0
0x1800096f1  mov     r8, [r8+50h]; TargetProcessHandle
0x1800096f5  call    cs:__imp_NtDuplicateObject
0x1800096fc  nop     dword ptr [rax+rax+00h]
0x180009701  mov     edi, eax
0x180009703  test    eax, eax
0x180009705  js      short loc_18000970B
0x180009707  xor     eax, eax
0x180009709  jmp     short loc_18000971C
0x18000970b  mov     rcx, [rbx]; Handle
0x18000970e  call    cs:__imp_NtClose
0x180009715  nop     dword ptr [rax+rax+00h]
0x18000971a  mov     eax, edi
0x18000971c  mov     rbx, [rsp+48h+arg_0]
0x180009721  add     rsp, 40h
0x180009725  pop     rdi
0x180009726  retn
```

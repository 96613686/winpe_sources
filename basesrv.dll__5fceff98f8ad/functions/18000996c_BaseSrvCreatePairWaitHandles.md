# BaseSrvCreatePairWaitHandles

- ea: `0x18000996c`
- end: `0x180009a02`
- name: `BaseSrvCreatePairWaitHandles`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008938`
- `0x18000905c`
- `0x18000abe0`
- `0x18000c434`
- `0x18000c820`

## callees

- `0x18000996c`

## import_xrefs

- `ntdll!NtClose` at `0x1800099e8`
- `ntdll!NtClose` at `0x1800099e8`
- `ntdll!NtDuplicateObject` at `0x1800099cf`
- `ntdll!NtDuplicateObject` at `0x1800099cf`
- `ntdll!NtCreateEvent` at `0x18000998c`
- `ntdll!NtCreateEvent` at `0x18000998c`

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
0x18000996c  mov     [rsp+arg_0], rbx
0x180009971  push    rdi
0x180009972  sub     rsp, 40h
0x180009976  mov     rdi, rdx
0x180009979  mov     [rsp+48h+InitialState], 0; InitialState
0x18000997e  mov     edx, 1F0003h; DesiredAccess
0x180009983  xor     r9d, r9d; EventType
0x180009986  xor     r8d, r8d; ObjectAttributes
0x180009989  mov     rbx, rcx
0x18000998c  call    cs:__imp_NtCreateEvent
0x180009993  nop     dword ptr [rax+rax+00h]
0x180009998  test    eax, eax
0x18000999a  js      short loc_1800099F6
0x18000999c  mov     rax, gs:70h
0x1800099a5  mov     r9, rdi; TargetHandle
0x1800099a8  mov     rdx, [rbx]; SourceHandle
0x1800099ab  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x1800099af  mov     [rsp+48h+Options], 2; Options
0x1800099b7  mov     [rsp+48h+HandleAttributes], 0; HandleAttributes
0x1800099bf  mov     r8, [rax+38h]
0x1800099c3  mov     dword ptr [rsp+48h+InitialState], 0; DesiredAccess
0x1800099cb  mov     r8, [r8+50h]; TargetProcessHandle
0x1800099cf  call    cs:__imp_NtDuplicateObject
0x1800099d6  nop     dword ptr [rax+rax+00h]
0x1800099db  mov     edi, eax
0x1800099dd  test    eax, eax
0x1800099df  js      short loc_1800099E5
0x1800099e1  xor     eax, eax
0x1800099e3  jmp     short loc_1800099F6
0x1800099e5  mov     rcx, [rbx]; Handle
0x1800099e8  call    cs:__imp_NtClose
0x1800099ef  nop     dword ptr [rax+rax+00h]
0x1800099f4  mov     eax, edi
0x1800099f6  mov     rbx, [rsp+48h+arg_0]
0x1800099fb  add     rsp, 40h
0x1800099ff  pop     rdi
0x180009a00  retn
```

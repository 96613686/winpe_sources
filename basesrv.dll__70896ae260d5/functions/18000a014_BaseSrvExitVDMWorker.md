# BaseSrvExitVDMWorker

- ea: `0x18000a014`
- end: `0x18000a097`
- name: `BaseSrvExitVDMWorker`
- size: `131`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005c70`
- `0x180006ee0`

## callees

- `0x18000a014`
- `0x18000a54c`

## import_xrefs

- `ntdll!NtClose` at `0x18000a02a`
- `ntdll!NtClose` at `0x18000a05c`
- `ntdll!NtClose` at `0x18000a079`
- `ntdll!NtClose` at `0x18000a02a`
- `ntdll!NtClose` at `0x18000a05c`
- `ntdll!NtClose` at `0x18000a079`
- `ntdll!NtSetEvent` at `0x18000a04c`
- `ntdll!NtSetEvent` at `0x18000a04c`

## pseudocode

```c
__int64 __fastcall BaseSrvExitVDMWorker(PVOID P)
{
  void *v2; // rcx
  __int64 **i; // rbx
  __int64 *v4; // rcx

  v2 = (void *)*((_QWORD *)P + 4);
  if ( v2 )
  {
    NtClose(v2);
    *((_QWORD *)P + 4) = 0;
  }
  for ( i = (__int64 **)*((_QWORD *)P + 9); i; i = (__int64 **)*i )
  {
    v4 = i[3];
    if ( v4 )
    {
      NtSetEvent(v4, 0);
      NtClose(i[3]);
      i[3] = 0;
    }
  }
  NtClose(*((HANDLE *)P + 2));
  return BaseSrvFreeConsoleRecord(P);
}

```

## disassembly

```asm
0x18000a014  mov     [rsp+arg_0], rbx
0x18000a019  push    rdi
0x18000a01a  sub     rsp, 20h
0x18000a01e  mov     rdi, rcx
0x18000a021  mov     rcx, [rcx+20h]; Handle
0x18000a025  test    rcx, rcx
0x18000a028  jz      short loc_18000A03B
0x18000a02a  call    cs:__imp_NtClose
0x18000a031  nop     dword ptr [rax+rax+00h]
0x18000a036  and     qword ptr [rdi+20h], 0
0x18000a03b  mov     rbx, [rdi+48h]
0x18000a03f  jmp     short loc_18000A070
0x18000a041  mov     rcx, [rbx+18h]; EventHandle
0x18000a045  test    rcx, rcx
0x18000a048  jz      short loc_18000A06D
0x18000a04a  xor     edx, edx; PreviousState
0x18000a04c  call    cs:__imp_NtSetEvent
0x18000a053  nop     dword ptr [rax+rax+00h]
0x18000a058  mov     rcx, [rbx+18h]; Handle
0x18000a05c  call    cs:__imp_NtClose
0x18000a063  nop     dword ptr [rax+rax+00h]
0x18000a068  and     qword ptr [rbx+18h], 0
0x18000a06d  mov     rbx, [rbx]
0x18000a070  test    rbx, rbx
0x18000a073  jnz     short loc_18000A041
0x18000a075  mov     rcx, [rdi+10h]; Handle
0x18000a079  call    cs:__imp_NtClose
0x18000a080  nop     dword ptr [rax+rax+00h]
0x18000a085  mov     rcx, rdi; P
0x18000a088  mov     rbx, [rsp+28h+arg_0]
0x18000a08d  add     rsp, 20h
0x18000a091  pop     rdi
0x18000a092  jmp     BaseSrvFreeConsoleRecord
```

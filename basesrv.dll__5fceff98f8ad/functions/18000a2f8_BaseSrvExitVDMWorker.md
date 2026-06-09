# BaseSrvExitVDMWorker

- ea: `0x18000a2f8`
- end: `0x18000a381`
- name: `BaseSrvExitVDMWorker`
- size: `137`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005ed0`
- `0x180007170`

## callees

- `0x18000a2f8`
- `0x18000a7d0`

## import_xrefs

- `ntdll!NtClose` at `0x18000a30e`
- `ntdll!NtClose` at `0x18000a343`
- `ntdll!NtClose` at `0x18000a363`
- `ntdll!NtClose` at `0x18000a30e`
- `ntdll!NtClose` at `0x18000a343`
- `ntdll!NtClose` at `0x18000a363`
- `ntdll!NtSetEvent` at `0x18000a333`
- `ntdll!NtSetEvent` at `0x18000a333`

## pseudocode

```c
void __fastcall BaseSrvExitVDMWorker(PVOID P)
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
  BaseSrvFreeConsoleRecord((PVOID *)P);
}

```

## disassembly

```asm
0x18000a2f8  mov     [rsp+arg_0], rbx
0x18000a2fd  push    rdi
0x18000a2fe  sub     rsp, 20h
0x18000a302  mov     rdi, rcx
0x18000a305  mov     rcx, [rcx+20h]; Handle
0x18000a309  test    rcx, rcx
0x18000a30c  jz      short loc_18000A322
0x18000a30e  call    cs:__imp_NtClose
0x18000a315  nop     dword ptr [rax+rax+00h]
0x18000a31a  mov     qword ptr [rdi+20h], 0
0x18000a322  mov     rbx, [rdi+48h]
0x18000a326  jmp     short loc_18000A35A
0x18000a328  mov     rcx, [rbx+18h]; EventHandle
0x18000a32c  test    rcx, rcx
0x18000a32f  jz      short loc_18000A357
0x18000a331  xor     edx, edx; PreviousState
0x18000a333  call    cs:__imp_NtSetEvent
0x18000a33a  nop     dword ptr [rax+rax+00h]
0x18000a33f  mov     rcx, [rbx+18h]; Handle
0x18000a343  call    cs:__imp_NtClose
0x18000a34a  nop     dword ptr [rax+rax+00h]
0x18000a34f  mov     qword ptr [rbx+18h], 0
0x18000a357  mov     rbx, [rbx]
0x18000a35a  test    rbx, rbx
0x18000a35d  jnz     short loc_18000A328
0x18000a35f  mov     rcx, [rdi+10h]; Handle
0x18000a363  call    cs:__imp_NtClose
0x18000a36a  nop     dword ptr [rax+rax+00h]
0x18000a36f  mov     rcx, rdi; P
0x18000a372  mov     rbx, [rsp+28h+arg_0]
0x18000a377  add     rsp, 20h
0x18000a37b  pop     rdi
0x18000a37c  jmp     BaseSrvFreeConsoleRecord
```

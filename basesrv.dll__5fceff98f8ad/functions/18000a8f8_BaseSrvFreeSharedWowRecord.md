# BaseSrvFreeSharedWowRecord

- ea: `0x18000a8f8`
- end: `0x18000a9ad`
- name: `BaseSrvFreeSharedWowRecord`
- size: `181`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000905c`
- `0x180009a08`

## callees

- `0x18000a8f8`
- `0x18000ab1c`

## import_xrefs

- `ntdll!NtClose` at `0x18000a913`
- `ntdll!NtClose` at `0x18000a947`
- `ntdll!NtClose` at `0x18000a974`
- `ntdll!NtClose` at `0x18000a913`
- `ntdll!NtClose` at `0x18000a947`
- `ntdll!NtClose` at `0x18000a974`
- `ntdll!RtlFreeHeap` at `0x18000a9a1`
- `ntdll!NtSetEvent` at `0x18000a937`
- `ntdll!NtSetEvent` at `0x18000a937`

## pseudocode

```c
BOOLEAN __fastcall BaseSrvFreeSharedWowRecord(_QWORD *a1)
{
  void *v2; // rcx
  __int64 v3; // rbx
  void *v4; // rcx
  __int64 v5; // rsi
  void *v6; // rcx

  v2 = (void *)a1[9];
  if ( v2 )
    NtClose(v2);
  v3 = a1[7];
  if ( v3 )
  {
    do
    {
      v4 = *(void **)(v3 + 8);
      v5 = *(_QWORD *)(v3 + 32);
      if ( v4 )
      {
        NtSetEvent(v4, 0);
        NtClose(*(HANDLE *)(v3 + 8));
        *(_QWORD *)(v3 + 8) = 0;
      }
      BaseSrvFreeWOWRecord((_QWORD *)v3);
      v3 = v5;
    }
    while ( v5 );
  }
  v6 = (void *)a1[2];
  if ( v6 )
    NtClose(v6);
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000a8f8  mov     [rsp+arg_0], rbx
0x18000a8fd  mov     [rsp+arg_8], rsi
0x18000a902  push    rdi
0x18000a903  sub     rsp, 20h
0x18000a907  mov     rdi, rcx
0x18000a90a  mov     rcx, [rcx+48h]; Handle
0x18000a90e  test    rcx, rcx
0x18000a911  jz      short loc_18000A91F
0x18000a913  call    cs:__imp_NtClose
0x18000a91a  nop     dword ptr [rax+rax+00h]
0x18000a91f  mov     rbx, [rdi+38h]
0x18000a923  test    rbx, rbx
0x18000a926  jz      short loc_18000A96B
0x18000a928  mov     rcx, [rbx+8]; EventHandle
0x18000a92c  mov     rsi, [rbx+20h]
0x18000a930  test    rcx, rcx
0x18000a933  jz      short loc_18000A95B
0x18000a935  xor     edx, edx; PreviousState
0x18000a937  call    cs:__imp_NtSetEvent
0x18000a93e  nop     dword ptr [rax+rax+00h]
0x18000a943  mov     rcx, [rbx+8]; Handle
0x18000a947  call    cs:__imp_NtClose
0x18000a94e  nop     dword ptr [rax+rax+00h]
0x18000a953  mov     qword ptr [rbx+8], 0
0x18000a95b  mov     rcx, rbx; P
0x18000a95e  call    BaseSrvFreeWOWRecord
0x18000a963  mov     rbx, rsi
0x18000a966  test    rsi, rsi
0x18000a969  jnz     short loc_18000A928
0x18000a96b  mov     rcx, [rdi+10h]; Handle
0x18000a96f  test    rcx, rcx
0x18000a972  jz      short loc_18000A980
0x18000a974  call    cs:__imp_NtClose
0x18000a97b  nop     dword ptr [rax+rax+00h]
0x18000a980  mov     rcx, gs:60h
0x18000a989  mov     r8, rdi
0x18000a98c  xor     edx, edx
0x18000a98e  mov     rcx, [rcx+30h]
0x18000a992  mov     rbx, [rsp+28h+arg_0]
0x18000a997  mov     rsi, [rsp+28h+arg_8]
0x18000a99c  add     rsp, 20h
0x18000a9a0  pop     rdi
0x18000a9a1  jmp     cs:__imp_RtlFreeHeap
```

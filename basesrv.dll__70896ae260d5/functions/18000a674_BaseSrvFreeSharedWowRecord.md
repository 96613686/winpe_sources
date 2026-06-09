# BaseSrvFreeSharedWowRecord

- ea: `0x18000a674`
- end: `0x18000a726`
- name: `BaseSrvFreeSharedWowRecord`
- size: `178`
- prototype: `BOOLEAN __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008d80`
- `0x180009730`

## callees

- `0x18000a674`
- `0x18000a894`

## import_xrefs

- `ntdll!NtClose` at `0x18000a68f`
- `ntdll!NtClose` at `0x18000a6c3`
- `ntdll!NtClose` at `0x18000a6ed`
- `ntdll!NtClose` at `0x18000a68f`
- `ntdll!NtClose` at `0x18000a6c3`
- `ntdll!NtClose` at `0x18000a6ed`
- `ntdll!RtlFreeHeap` at `0x18000a71a`
- `ntdll!NtSetEvent` at `0x18000a6b3`
- `ntdll!NtSetEvent` at `0x18000a6b3`

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
0x18000a674  mov     [rsp+arg_0], rbx
0x18000a679  mov     [rsp+arg_8], rsi
0x18000a67e  push    rdi
0x18000a67f  sub     rsp, 20h
0x18000a683  mov     rdi, rcx
0x18000a686  mov     rcx, [rcx+48h]; Handle
0x18000a68a  test    rcx, rcx
0x18000a68d  jz      short loc_18000A69B
0x18000a68f  call    cs:__imp_NtClose
0x18000a696  nop     dword ptr [rax+rax+00h]
0x18000a69b  mov     rbx, [rdi+38h]
0x18000a69f  test    rbx, rbx
0x18000a6a2  jz      short loc_18000A6E4
0x18000a6a4  mov     rcx, [rbx+8]; EventHandle
0x18000a6a8  mov     rsi, [rbx+20h]
0x18000a6ac  test    rcx, rcx
0x18000a6af  jz      short loc_18000A6D4
0x18000a6b1  xor     edx, edx; PreviousState
0x18000a6b3  call    cs:__imp_NtSetEvent
0x18000a6ba  nop     dword ptr [rax+rax+00h]
0x18000a6bf  mov     rcx, [rbx+8]; Handle
0x18000a6c3  call    cs:__imp_NtClose
0x18000a6ca  nop     dword ptr [rax+rax+00h]
0x18000a6cf  and     qword ptr [rbx+8], 0
0x18000a6d4  mov     rcx, rbx; P
0x18000a6d7  call    BaseSrvFreeWOWRecord
0x18000a6dc  mov     rbx, rsi
0x18000a6df  test    rsi, rsi
0x18000a6e2  jnz     short loc_18000A6A4
0x18000a6e4  mov     rcx, [rdi+10h]; Handle
0x18000a6e8  test    rcx, rcx
0x18000a6eb  jz      short loc_18000A6F9
0x18000a6ed  call    cs:__imp_NtClose
0x18000a6f4  nop     dword ptr [rax+rax+00h]
0x18000a6f9  mov     rcx, gs:60h
0x18000a702  mov     r8, rdi
0x18000a705  xor     edx, edx
0x18000a707  mov     rcx, [rcx+30h]
0x18000a70b  mov     rbx, [rsp+28h+arg_0]
0x18000a710  mov     rsi, [rsp+28h+arg_8]
0x18000a715  add     rsp, 20h
0x18000a719  pop     rdi
0x18000a71a  jmp     cs:__imp_RtlFreeHeap
```

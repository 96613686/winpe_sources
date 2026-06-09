# SrvWriteConsole

- ea: `0x1400204b0`
- end: `0x140020546`
- name: `SrvWriteConsole`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14001f0e0`

## callees

- `0x1400204b0`
- `0x1400213bc`
- `0x140021484`
- `0x140021e10`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020531`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140020531`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400204de`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400204de`

## pseudocode

```c
__int64 __fastcall SrvWriteConsole(__int64 a1)
{
  __int64 v1; // rdi
  int *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // ebp

  v1 = *(_QWORD *)(a1 + 328);
  if ( !v1 )
    return 3221225480LL;
  v4 = (int *)(a1 + 360);
  RtlAcquireSRWLockExclusive(a1 + 48);
  v5 = a1 + 216;
  v6 = v1 + 24;
  if ( *((_BYTE *)v4 + 4) )
    v7 = CspWriteConsole((void **)a1, v5, v6, v4);
  else
    v7 = CspWriteConsoleA((void **)a1, v5, v6, v4);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *(_QWORD *)(a1 + 232) = (unsigned int)*v4;
    if ( v1 == *(_QWORD *)(a1 + 96) )
      CspTriggerScreenRedraw(a1, a1 + 216, 0);
  }
  RtlReleaseSRWLockExclusive(a1 + 48);
  return v8;
}

```

## disassembly

```asm
0x1400204b0  push    rbx
0x1400204b2  push    rbp
0x1400204b3  push    rsi
0x1400204b4  push    rdi
0x1400204b5  push    r14
0x1400204b7  push    r15
0x1400204b9  sub     rsp, 28h
0x1400204bd  mov     rdi, [rcx+148h]
0x1400204c4  mov     rbx, rcx
0x1400204c7  test    rdi, rdi
0x1400204ca  jnz     short loc_1400204D3
0x1400204cc  mov     eax, 0C0000008h
0x1400204d1  jmp     short loc_140020539
0x1400204d3  lea     rsi, [rcx+168h]
0x1400204da  add     rcx, 30h ; '0'
0x1400204de  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400204e4  cmp     byte ptr [rsi+4], 0
0x1400204e8  lea     r15, [rbx+0D8h]
0x1400204ef  mov     rdx, r15
0x1400204f2  lea     r8, [rdi+18h]
0x1400204f6  mov     r9, rsi
0x1400204f9  mov     rcx, rbx
0x1400204fc  jz      short loc_140020505
0x1400204fe  call    CspWriteConsole
0x140020503  jmp     short loc_14002050A
0x140020505  call    CspWriteConsoleA
0x14002050a  mov     ebp, eax
0x14002050c  test    eax, eax
0x14002050e  js      short loc_14002052D
0x140020510  mov     eax, [rsi]
0x140020512  mov     [rbx+0E8h], rax
0x140020519  cmp     rdi, [rbx+60h]
0x14002051d  jnz     short loc_14002052D
0x14002051f  xor     r8d, r8d
0x140020522  mov     rdx, r15
0x140020525  mov     rcx, rbx
0x140020528  call    CspTriggerScreenRedraw
0x14002052d  lea     rcx, [rbx+30h]
0x140020531  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140020537  mov     eax, ebp
0x140020539  add     rsp, 28h
0x14002053d  pop     r15
0x14002053f  pop     r14
0x140020541  pop     rdi
0x140020542  pop     rsi
0x140020543  pop     rbp
0x140020544  pop     rbx
0x140020545  retn
```

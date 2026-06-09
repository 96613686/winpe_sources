# HampConnectionCreate

- ea: `0x180003270`
- end: `0x18000341e`
- name: `HampConnectionCreate`
- size: `430`
- prototype: `__int64 __fastcall(_OWORD *, __int64 *, unsigned int, __int64, __int64 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004990`
- `0x180004aa0`
- `0x180010650`
- `0x180019810`

## callees

- `0x180003270`
- `0x180003430`
- `0x180003978`
- `0x180003a08`
- `0x180003af0`
- `0x18001ae8e`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x1800032cf`
- `ntdll!RtlInitializeSRWLock` at `0x1800032cf`
- `ntdll!RtlAllocateHeap` at `0x1800032a4`
- `ntdll!RtlAllocateHeap` at `0x1800032a4`

## pseudocode

```c
__int64 __fastcall HampConnectionCreate(_OWORD *a1, __int64 *a2, unsigned int a3, __int64 a4, __int64 *a5)
{
  PVOID Heap; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  int State; // edi
  char v16; // al

  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0xA0u);
  v10 = (__int64)Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, 0xA0u);
  RtlInitializeSRWLock(v10 + 120);
  *(_DWORD *)(v10 + 128) = 0;
  if ( a1 )
    *(_OWORD *)(v10 + 104) = *a1;
  if ( a2 == qword_18001DC80 )
  {
    *(_BYTE *)(v10 + 156) = 0;
    HamIpcChannelInitialize(v12, v11, v13, v10 + 24);
  }
  else if ( a2 == qword_18001D1F0 )
  {
    *(_BYTE *)(v10 + 156) = 2;
    HamIpcChannelInitialize(v12, v11, v13, v10 + 24);
  }
  else if ( a2 == qword_18001D2B0 )
  {
    *(_BYTE *)(v10 + 156) = 6;
  }
  else if ( a2 == qword_18001D310 )
  {
    *(_BYTE *)(v10 + 156) = 1;
    HamIpcChannelInitialize(v12, v11, v13, v10 + 24);
  }
  else if ( a2 == qword_18001D370 )
  {
    *(_BYTE *)(v10 + 156) = 3;
    HamIpcChannelInitialize(v12, v11, v13, v10 + 24);
  }
  else if ( a2 == qword_18001D250 )
  {
    *(_BYTE *)(v10 + 156) = 4;
  }
  else
  {
    v16 = 7;
    if ( a2 == qword_18001D4F0 )
      v16 = 5;
    *(_BYTE *)(v10 + 156) = v16;
  }
  State = HampConnectionAllocateState(v10, a2, a3, a4);
  if ( State < 0 || (State = HampConnectionStart(v10), State < 0) )
  {
    HampConnectionDestroy(v10);
    return (unsigned int)State;
  }
  else
  {
    *a5 = v10;
    return 0;
  }
}

```

## disassembly

```asm
0x180003270  mov     [rsp+arg_8], rbx
0x180003275  mov     [rsp+arg_10], rbp
0x18000327a  push    rsi
0x18000327b  push    r14
0x18000327d  push    r15
0x18000327f  sub     rsp, 20h
0x180003283  mov     rbp, rcx
0x180003286  mov     r15d, r8d
0x180003289  mov     rcx, gs:60h
0x180003292  mov     rsi, rdx
0x180003295  xor     edx, edx; Flags
0x180003297  mov     r8d, 0A0h; Size
0x18000329d  mov     r14, r9
0x1800032a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800032a4  call    cs:__imp_RtlAllocateHeap
0x1800032aa  mov     rbx, rax
0x1800032ad  test    rax, rax
0x1800032b0  jz      loc_1800033AA
0x1800032b6  xor     edx, edx; Val
0x1800032b8  mov     [rsp+38h+arg_0], rdi
0x1800032bd  mov     r8d, 0A0h; Size
0x1800032c3  mov     rcx, rax; void *
0x1800032c6  call    memset_0
0x1800032cb  lea     rcx, [rbx+78h]
0x1800032cf  call    cs:__imp_RtlInitializeSRWLock
0x1800032d5  mov     dword ptr [rbx+80h], 0
0x1800032df  test    rbp, rbp
0x1800032e2  jnz     short loc_18000334C
0x1800032e4  lea     rax, qword_18001DC80
0x1800032eb  cmp     rsi, rax
0x1800032ee  jnz     short loc_180003356
0x1800032f0  lea     r9, [rbx+18h]
0x1800032f4  mov     byte ptr [rbx+9Ch], 0
0x1800032fb  call    HamIpcChannelInitialize
0x180003300  mov     r9, r14
0x180003303  mov     r8d, r15d
0x180003306  mov     rdx, rsi
0x180003309  mov     rcx, rbx
0x18000330c  call    HampConnectionAllocateState
0x180003311  mov     edi, eax
0x180003313  test    eax, eax
0x180003315  js      loc_18000339E
0x18000331b  mov     rcx, rbx
0x18000331e  call    HampConnectionStart
0x180003323  mov     edi, eax
0x180003325  test    eax, eax
0x180003327  js      short loc_18000339E
0x180003329  mov     rax, [rsp+38h+arg_20]
0x18000332e  mov     [rax], rbx
0x180003331  xor     eax, eax
0x180003333  mov     rdi, [rsp+38h+arg_0]
0x180003338  mov     rbx, [rsp+38h+arg_8]
0x18000333d  mov     rbp, [rsp+38h+arg_10]
0x180003342  add     rsp, 20h
0x180003346  pop     r15
0x180003348  pop     r14
0x18000334a  pop     rsi
0x18000334b  retn
0x18000334c  movups  xmm0, xmmword ptr [rbp+0]
0x180003350  movups  xmmword ptr [rbx+68h], xmm0
0x180003354  jmp     short loc_1800032E4
0x180003356  lea     rax, qword_18001D1F0
0x18000335d  cmp     rsi, rax
0x180003360  jz      short loc_1800033B1
0x180003362  lea     rax, qword_18001D2B0
0x180003369  cmp     rsi, rax
0x18000336c  jz      short loc_1800033C6
0x18000336e  lea     rax, qword_18001D310
0x180003375  cmp     rsi, rax
0x180003378  jz      short loc_1800033D2
0x18000337a  lea     rax, qword_18001D370
0x180003381  cmp     rsi, rax
0x180003384  jz      short loc_1800033E7
0x180003386  lea     rax, qword_18001D250
0x18000338d  cmp     rsi, rax
0x180003390  jnz     short loc_1800033FC
0x180003392  mov     byte ptr [rbx+9Ch], 4
0x180003399  jmp     loc_180003300
0x18000339e  mov     rcx, rbx
0x1800033a1  call    HampConnectionDestroy
0x1800033a6  mov     eax, edi
0x1800033a8  jmp     short loc_180003333
0x1800033aa  mov     eax, 0C0000017h
0x1800033af  jmp     short loc_180003338
0x1800033b1  lea     r9, [rbx+18h]
0x1800033b5  mov     byte ptr [rbx+9Ch], 2
0x1800033bc  call    HamIpcChannelInitialize
0x1800033c1  jmp     loc_180003300
0x1800033c6  mov     byte ptr [rbx+9Ch], 6
0x1800033cd  jmp     loc_180003300
0x1800033d2  lea     r9, [rbx+18h]
0x1800033d6  mov     byte ptr [rbx+9Ch], 1
0x1800033dd  call    HamIpcChannelInitialize
0x1800033e2  jmp     loc_180003300
0x1800033e7  lea     r9, [rbx+18h]
0x1800033eb  mov     byte ptr [rbx+9Ch], 3
0x1800033f2  call    HamIpcChannelInitialize
0x1800033f7  jmp     loc_180003300
0x1800033fc  lea     rcx, qword_18001D4F0
0x180003403  mov     eax, 7
0x180003408  cmp     rsi, rcx
0x18000340b  mov     edx, 5
0x180003410  cmovz   eax, edx
0x180003413  mov     [rbx+9Ch], al
0x180003419  jmp     loc_180003300
```

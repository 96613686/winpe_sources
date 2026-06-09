# BaseSrvAddSharedWowTask

- ea: `0x180008528`
- end: `0x18000869e`
- name: `BaseSrvAddSharedWowTask`
- size: `374`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800086cc`

## callees

- `0x180008528`
- `0x1800086a4`
- `0x1800088b0`
- `0x18000ab1c`
- `0x18000db05`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800085f6`
- `ntdll!RtlAllocateHeap` at `0x1800085f6`
- `ntdll!RtlFreeHeap` at `0x1800085cb`
- `ntdll!RtlFreeHeap` at `0x1800085cb`

## pseudocode

```c
__int64 __fastcall BaseSrvAddSharedWowTask(__int64 a1, __int64 a2)
{
  __int64 WOWRecord; // rax
  __int64 v5; // rbx
  int v6; // ebp
  __int64 v7; // rdi
  _BYTE *i; // rax
  void *v9; // r8
  unsigned int v10; // r15d
  PVOID Heap; // rax

  if ( *(_DWORD *)(a1 + 104) != 148 )
    return 3221225485LL;
  if ( !*(_QWORD *)(a2 + 88) )
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 152);
  if ( *(_DWORD *)a1 != -1 )
  {
    v5 = *(_QWORD *)(a2 + 56);
    v6 = 0;
    while ( v5 )
    {
      if ( *(_DWORD *)v5 == *(_DWORD *)a1 )
        goto LABEL_7;
      v5 = *(_QWORD *)(v5 + 32);
    }
    return 3221225485LL;
  }
  WOWRecord = BaseSrvAllocateWOWRecord();
  v5 = WOWRecord;
  if ( !WOWRecord )
    return 3221225632LL;
  *(_DWORD *)(WOWRecord + 4) = 1;
  v6 = 1;
LABEL_7:
  *(_DWORD *)a1 = *(_DWORD *)v5;
  v7 = *(_QWORD *)(a1 + 96);
  for ( i = (_BYTE *)(v7 + 17); *i; ++i )
  {
    if ( (unsigned __int64)i >= v7 + 144 )
      break;
  }
  v9 = *(void **)(v5 + 48);
  v10 = (_DWORD)i - v7 - 16;
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v10);
  *(_QWORD *)(v5 + 48) = Heap;
  if ( !Heap )
  {
    if ( v6 )
      BaseSrvFreeWOWRecord((PVOID)v5);
    return 3221225632LL;
  }
  *(_DWORD *)(v5 + 40) = *(_DWORD *)v7;
  *(_WORD *)(v5 + 44) = *(_WORD *)(v7 + 4);
  *(_WORD *)(v5 + 46) = *(_WORD *)(v7 + 6);
  *(_QWORD *)(v5 + 56) = *(_QWORD *)(v7 + 8);
  *(_BYTE *)(v5 + 64) = *(_BYTE *)(v7 + 16);
  memcpy_0(Heap, (const void *)(v7 + 17), v10);
  *(_BYTE *)(v10 - 1 + *(_QWORD *)(v5 + 48)) = 0;
  if ( v6 )
    BaseSrvAddWOWRecord(a2, v5);
  return 0;
}

```

## disassembly

```asm
0x180008528  push    rbx
0x18000852a  push    rbp
0x18000852b  push    rsi
0x18000852c  push    rdi
0x18000852d  push    r12
0x18000852f  push    r14
0x180008531  push    r15
0x180008533  sub     rsp, 20h
0x180008537  cmp     dword ptr [rcx+68h], 94h
0x18000853e  mov     rsi, rdx
0x180008541  mov     rdi, rcx
0x180008544  jnz     loc_18000863A
0x18000854a  cmp     qword ptr [rdx+58h], 0
0x18000854f  jnz     short loc_18000855C
0x180008551  mov     rax, [rcx+98h]
0x180008558  mov     [rdx+58h], rax
0x18000855c  mov     eax, [rcx]
0x18000855e  cmp     eax, 0FFFFFFFFh
0x180008561  jnz     loc_180008621
0x180008567  call    BaseSrvAllocateWOWRecord
0x18000856c  mov     rbx, rax
0x18000856f  test    rax, rax
0x180008572  jz      loc_18000861A
0x180008578  mov     dword ptr [rax+4], 1
0x18000857f  mov     ebp, 1
0x180008584  mov     eax, [rbx]
0x180008586  mov     [rdi], eax
0x180008588  mov     rdi, [rdi+60h]
0x18000858c  lea     r14, [rdi+11h]
0x180008590  cmp     byte ptr [r14], 0
0x180008594  mov     rax, r14
0x180008597  jz      short loc_1800085AD
0x180008599  lea     rcx, [rdi+90h]
0x1800085a0  cmp     rax, rcx
0x1800085a3  jnb     short loc_1800085AD
0x1800085a5  inc     rax
0x1800085a8  cmp     byte ptr [rax], 0
0x1800085ab  jnz     short loc_1800085A0
0x1800085ad  mov     r8, [rbx+30h]; P
0x1800085b1  sub     eax, edi
0x1800085b3  lea     r15d, [rax-10h]
0x1800085b7  test    r8, r8
0x1800085ba  jz      short loc_1800085D7
0x1800085bc  mov     rcx, gs:60h
0x1800085c5  xor     edx, edx; Flags
0x1800085c7  mov     rcx, [rcx+30h]; HeapHandle
0x1800085cb  call    cs:__imp_RtlFreeHeap
0x1800085d2  nop     dword ptr [rax+rax+00h]
0x1800085d7  mov     rcx, gs:60h
0x1800085e0  mov     edx, cs:BaseSrvTag
0x1800085e6  add     edx, 40000h; Flags
0x1800085ec  mov     r8d, r15d; Size
0x1800085ef  mov     r12d, r15d
0x1800085f2  mov     rcx, [rcx+30h]; HeapHandle
0x1800085f6  call    cs:__imp_RtlAllocateHeap
0x1800085fd  nop     dword ptr [rax+rax+00h]
0x180008602  mov     [rbx+30h], rax
0x180008606  mov     rcx, rax; void *
0x180008609  test    rax, rax
0x18000860c  jnz     short loc_18000864F
0x18000860e  test    ebp, ebp
0x180008610  jz      short loc_18000861A
0x180008612  mov     rcx, rbx; P
0x180008615  call    BaseSrvFreeWOWRecord
0x18000861a  mov     eax, 0C00000A0h
0x18000861f  jmp     short loc_18000863F
0x180008621  mov     rbx, [rdx+38h]
0x180008625  xor     ebp, ebp
0x180008627  jmp     short loc_180008635
0x180008629  cmp     [rbx], eax
0x18000862b  jz      loc_180008584
0x180008631  mov     rbx, [rbx+20h]
0x180008635  test    rbx, rbx
0x180008638  jnz     short loc_180008629
0x18000863a  mov     eax, 0C000000Dh
0x18000863f  add     rsp, 20h
0x180008643  pop     r15
0x180008645  pop     r14
0x180008647  pop     r12
0x180008649  pop     rdi
0x18000864a  pop     rsi
0x18000864b  pop     rbp
0x18000864c  pop     rbx
0x18000864d  retn
0x18000864f  mov     eax, [rdi]
0x180008651  mov     r8, r12; Size
0x180008654  mov     [rbx+28h], eax
0x180008657  mov     rdx, r14; Src
0x18000865a  movzx   eax, word ptr [rdi+4]
0x18000865e  mov     [rbx+2Ch], ax
0x180008662  movzx   eax, word ptr [rdi+6]
0x180008666  mov     [rbx+2Eh], ax
0x18000866a  movsd   xmm0, qword ptr [rdi+8]
0x18000866f  movsd   qword ptr [rbx+38h], xmm0
0x180008674  mov     al, [rdi+10h]
0x180008677  mov     [rbx+40h], al
0x18000867a  call    memcpy_0
0x18000867f  mov     rax, [rbx+30h]
0x180008683  lea     ecx, [r15-1]
0x180008687  mov     byte ptr [rcx+rax], 0
0x18000868b  test    ebp, ebp
0x18000868d  jz      short loc_18000869A
0x18000868f  mov     rdx, rbx
0x180008692  mov     rcx, rsi
0x180008695  call    BaseSrvAddWOWRecord
0x18000869a  xor     eax, eax
0x18000869c  jmp     short loc_18000863F
```

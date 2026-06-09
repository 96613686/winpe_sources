# BaseSrvAddSepWowTask

- ea: `0x18000806c`
- end: `0x180008213`
- name: `BaseSrvAddSepWowTask`
- size: `423`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x1800083dc`

## callees

- `0x180008038`
- `0x18000806c`
- `0x1800084bc`
- `0x18000a614`
- `0x18000b4a4`
- `0x18000d6fb`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008179`
- `ntdll!RtlAllocateHeap` at `0x180008179`
- `ntdll!RtlFreeHeap` at `0x1800080ff`
- `ntdll!RtlFreeHeap` at `0x18000814e`
- `ntdll!RtlFreeHeap` at `0x1800080ff`
- `ntdll!RtlFreeHeap` at `0x18000814e`

## pseudocode

```c
__int64 __fastcall BaseSrvAddSepWowTask(__int64 a1, __int64 a2)
{
  int v2; // r14d
  __int64 DOSRecord; // rbx
  void *v7; // r8
  __int64 v8; // rsi
  _BYTE *i; // rdi
  void *v10; // r8
  unsigned int v11; // edi
  PVOID Heap; // rax

  v2 = 0;
  if ( *(_DWORD *)(a1 + 104) != 148 )
    return 3221225485LL;
  if ( !*(_QWORD *)(a2 + 88) )
    *(_QWORD *)(a2 + 88) = *(_QWORD *)(a1 + 152);
  if ( *(_DWORD *)a1 == -1 )
  {
    DOSRecord = BaseSrvAllocateDOSRecord();
    if ( !DOSRecord )
      return 3221225632LL;
    *(_DWORD *)(DOSRecord + 40) = BaseSrvGetWOWTaskId();
    v2 = 1;
    *(_DWORD *)(DOSRecord + 8) = 2;
  }
  else
  {
    DOSRecord = *(_QWORD *)(a2 + 72);
  }
  v7 = *(void **)(DOSRecord + 56);
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *(_QWORD *)(DOSRecord + 56) = 0;
  }
  v8 = *(_QWORD *)(a1 + 96);
  for ( i = (_BYTE *)(v8 + 17); *i; ++i )
  {
    if ( (unsigned __int64)i >= v8 + 144 )
      break;
  }
  v10 = *(void **)(DOSRecord + 56);
  v11 = (_DWORD)i - v8 - 16;
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, BaseSrvTag + 0x40000, v11);
  *(_QWORD *)(DOSRecord + 56) = Heap;
  if ( !Heap )
  {
    if ( v2 )
      BaseSrvFreeDOSRecord(DOSRecord);
    return 3221225632LL;
  }
  *(_DWORD *)(DOSRecord + 44) = *(_DWORD *)v8;
  *(_WORD *)(DOSRecord + 48) = *(_WORD *)(v8 + 4);
  *(_WORD *)(DOSRecord + 50) = *(_WORD *)(v8 + 6);
  *(_QWORD *)(DOSRecord + 64) = *(_QWORD *)(v8 + 8);
  *(_BYTE *)(DOSRecord + 72) = *(_BYTE *)(v8 + 16);
  memcpy_0(Heap, (const void *)(v8 + 17), v11);
  *(_BYTE *)(v11 - 1 + *(_QWORD *)(DOSRecord + 56)) = 0;
  if ( v2 )
    BaseSrvAddDOSRecord(a2, DOSRecord);
  return 0;
}

```

## disassembly

```asm
0x18000806c  mov     rax, rsp
0x18000806f  mov     [rax+8], rbx
0x180008073  mov     [rax+10h], rbp
0x180008077  mov     [rax+18h], rsi
0x18000807b  mov     [rax+20h], rdi
0x18000807f  push    r12
0x180008081  push    r14
0x180008083  push    r15
0x180008085  sub     rsp, 20h
0x180008089  xor     r14d, r14d
0x18000808c  mov     rbp, rdx
0x18000808f  cmp     dword ptr [rcx+68h], 94h
0x180008096  mov     rdi, rcx
0x180008099  jz      short loc_1800080A5
0x18000809b  mov     eax, 0C000000Dh
0x1800080a0  jmp     loc_1800081F3
0x1800080a5  cmp     [rdx+58h], r14
0x1800080a9  jnz     short loc_1800080B6
0x1800080ab  mov     rax, [rcx+98h]
0x1800080b2  mov     [rdx+58h], rax
0x1800080b6  cmp     dword ptr [rcx], 0FFFFFFFFh
0x1800080b9  jnz     short loc_1800080E3
0x1800080bb  call    BaseSrvAllocateDOSRecord
0x1800080c0  mov     rbx, rax
0x1800080c3  test    rax, rax
0x1800080c6  jz      loc_18000819E
0x1800080cc  call    BaseSrvGetWOWTaskId
0x1800080d1  mov     [rbx+28h], eax
0x1800080d4  mov     r14d, 1
0x1800080da  mov     dword ptr [rbx+8], 2
0x1800080e1  jmp     short loc_1800080E7
0x1800080e3  mov     rbx, [rdx+48h]
0x1800080e7  mov     r8, [rbx+38h]; P
0x1800080eb  test    r8, r8
0x1800080ee  jz      short loc_180008110
0x1800080f0  mov     rcx, gs:60h
0x1800080f9  xor     edx, edx; Flags
0x1800080fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800080ff  call    cs:__imp_RtlFreeHeap
0x180008106  nop     dword ptr [rax+rax+00h]
0x18000810b  and     qword ptr [rbx+38h], 0
0x180008110  mov     rsi, [rdi+60h]
0x180008114  lea     rdi, [rsi+11h]
0x180008118  cmp     byte ptr [rdi], 0
0x18000811b  jz      short loc_180008131
0x18000811d  lea     rax, [rsi+90h]
0x180008124  cmp     rdi, rax
0x180008127  jnb     short loc_180008131
0x180008129  inc     rdi
0x18000812c  cmp     byte ptr [rdi], 0
0x18000812f  jnz     short loc_180008124
0x180008131  mov     r8, [rbx+38h]; P
0x180008135  sub     edi, esi
0x180008137  sub     edi, 10h
0x18000813a  test    r8, r8
0x18000813d  jz      short loc_18000815A
0x18000813f  mov     rcx, gs:60h
0x180008148  xor     edx, edx; Flags
0x18000814a  mov     rcx, [rcx+30h]; HeapHandle
0x18000814e  call    cs:__imp_RtlFreeHeap
0x180008155  nop     dword ptr [rax+rax+00h]
0x18000815a  mov     rcx, gs:60h
0x180008163  mov     edx, cs:BaseSrvTag
0x180008169  add     edx, 40000h; Flags
0x18000816f  mov     r8d, edi; Size
0x180008172  mov     r15d, edi
0x180008175  mov     rcx, [rcx+30h]; HeapHandle
0x180008179  call    cs:__imp_RtlAllocateHeap
0x180008180  nop     dword ptr [rax+rax+00h]
0x180008185  mov     [rbx+38h], rax
0x180008189  mov     rcx, rax; void *
0x18000818c  test    rax, rax
0x18000818f  jnz     short loc_1800081A5
0x180008191  test    r14d, r14d
0x180008194  jz      short loc_18000819E
0x180008196  mov     rcx, rbx
0x180008199  call    BaseSrvFreeDOSRecord
0x18000819e  mov     eax, 0C00000A0h
0x1800081a3  jmp     short loc_1800081F3
0x1800081a5  mov     eax, [rsi]
0x1800081a7  lea     rdx, [rsi+11h]; Src
0x1800081ab  mov     [rbx+2Ch], eax
0x1800081ae  mov     r8, r15; Size
0x1800081b1  movzx   eax, word ptr [rsi+4]
0x1800081b5  mov     [rbx+30h], ax
0x1800081b9  movzx   eax, word ptr [rsi+6]
0x1800081bd  mov     [rbx+32h], ax
0x1800081c1  movsd   xmm0, qword ptr [rsi+8]
0x1800081c6  movsd   qword ptr [rbx+40h], xmm0
0x1800081cb  mov     al, [rsi+10h]
0x1800081ce  mov     [rbx+48h], al
0x1800081d1  call    memcpy_0
0x1800081d6  mov     rax, [rbx+38h]
0x1800081da  lea     ecx, [rdi-1]
0x1800081dd  mov     byte ptr [rcx+rax], 0
0x1800081e1  test    r14d, r14d
0x1800081e4  jz      short loc_1800081F1
0x1800081e6  mov     rdx, rbx
0x1800081e9  mov     rcx, rbp
0x1800081ec  call    BaseSrvAddDOSRecord
0x1800081f1  xor     eax, eax
0x1800081f3  mov     rbx, [rsp+38h+arg_0]
0x1800081f8  mov     rbp, [rsp+38h+arg_8]
0x1800081fd  mov     rsi, [rsp+38h+arg_10]
0x180008202  mov     rdi, [rsp+38h+arg_18]
0x180008207  add     rsp, 20h
0x18000820b  pop     r15
0x18000820d  pop     r14
0x18000820f  pop     r12
0x180008211  retn
```

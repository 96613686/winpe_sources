# SdbpCreateSearchDBContext

- ea: `0x1800334ac`
- end: `0x18003382a`
- name: `SdbpCreateSearchDBContext`
- size: `894`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180017b80`
- `0x18004cb90`

## callees

- `0x180004cd8`
- `0x1800055e0`
- `0x180005660`
- `0x18000f114`
- `0x180018f20`
- `0x1800334ac`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180033552`
- `ntdll!RtlAllocateHeap` at `0x1800335eb`
- `ntdll!RtlAllocateHeap` at `0x180033689`
- `ntdll!RtlAllocateHeap` at `0x1800336ca`
- `ntdll!RtlAllocateHeap` at `0x1800336e8`
- `ntdll!RtlAllocateHeap` at `0x180033706`
- `ntdll!RtlAllocateHeap` at `0x180033552`
- `ntdll!RtlAllocateHeap` at `0x1800335eb`
- `ntdll!RtlAllocateHeap` at `0x180033689`
- `ntdll!RtlAllocateHeap` at `0x1800336ca`
- `ntdll!RtlAllocateHeap` at `0x1800336e8`
- `ntdll!RtlAllocateHeap` at `0x180033706`

## string_xrefs

- `0x180033560`: `Unable to allocate memory for directory path`
- `0x1800335af`: `Unable to parse executable path for "%ws"`
- `0x18003356d`: `SdbpCreateSearchDBContext`
- `0x1800335bc`: `SdbpCreateSearchDBContext`
- `0x180033606`: `SdbpCreateSearchDBContext`
- `0x18003379c`: `SdbpCreateSearchDBContext`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, const wchar_t **a2, __int64 a3, __int64 a4)
{
  const wchar_t **v5; // r15
  __int64 v7; // r14
  void *v8; // rbp
  const wchar_t *v9; // r15
  __int64 v10; // rax
  unsigned int v11; // edi
  _WORD *Heap; // rsi
  __int64 result; // rax
  _WORD *v14; // rdi
  _WORD *v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // r14
  PVOID v18; // rax
  PVOID v19; // rax
  __int16 v20; // r10
  _WORD *v21; // r11
  int v22; // [rsp+20h] [rbp-4A8h]
  _WORD v25[264]; // [rsp+60h] [rbp-468h] BYREF
  _WORD v26[264]; // [rsp+270h] [rbp-258h] BYREF

  v5 = a2;
  memset_0(v26, 0, 0x208u);
  memset_0(v25, 0, 0x208u);
  v7 = -1;
  v8 = 0;
  if ( v5 )
  {
    v9 = *v5;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    v11 = v10 + 1;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v10 + 1));
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 437, "Unable to allocate memory for directory path");
      return 0;
    }
    if ( (int)AslPathSplit(v9, Heap, v11, v25, v22, v26) < 0 )
    {
      v14 = 0;
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 448, "Unable to parse executable path for \"%ws\"", v9);
LABEL_25:
      AslFree(NtCurrentPeb()->ProcessHeap, Heap);
      goto LABEL_26;
    }
    v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    v14 = v15;
    if ( !v15 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 454, "Unable to allocate memory for full name");
      goto LABEL_25;
    }
    if ( (int)RtlStringCchCopyW(v15, 260, v25) < 0 || (int)RtlStringCchCatW(v14, v16, v26) < 0 )
      goto LABEL_25;
    v5 = a2;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4u);
    v14 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v19 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    if ( !Heap || !v14 || !v19 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 469, "Unable to allocate memory");
      goto LABEL_24;
    }
    RtlStringCchCopyW(Heap, 2, L".");
    *v14 = v20;
    *v21 = 0;
    a1[3] = v21;
  }
  if ( !a3 )
    goto LABEL_22;
  do
    ++v7;
  while ( *(_WORD *)(a3 + 2 * v7) );
  v17 = (int)v7 + 1;
  v18 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v17);
  v8 = v18;
  if ( !v18 )
  {
    AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 483, "Unable to allocate memory for szModule");
    goto LABEL_24;
  }
  if ( (int)RtlStringCchCopyW(v18, v17, a3) >= 0 )
  {
LABEL_22:
    a1[7] = a4;
    result = 1;
    a1[1] = v5;
    a1[4] = Heap;
    a1[5] = v14;
    a1[6] = v8;
    a1[9] = 0;
    a1[8] = 0;
    a1[11] = 0;
    a1[12] = 0;
    return result;
  }
LABEL_24:
  if ( Heap )
    goto LABEL_25;
LABEL_26:
  if ( v14 )
    AslFree(NtCurrentPeb()->ProcessHeap, v14);
  if ( v8 )
    AslFree(NtCurrentPeb()->ProcessHeap, v8);
  return 0;
}

```

## disassembly

```asm
0x1800334ac  mov     [rsp+arg_18], rbx
0x1800334b1  push    rbp
0x1800334b2  push    rsi
0x1800334b3  push    rdi
0x1800334b4  push    r12
0x1800334b6  push    r13
0x1800334b8  push    r14
0x1800334ba  push    r15
0x1800334bc  sub     rsp, 490h
0x1800334c3  mov     rax, cs:__security_cookie
0x1800334ca  xor     rax, rsp
0x1800334cd  mov     [rsp+4C8h+var_48], rax
0x1800334d5  mov     r13, r8
0x1800334d8  mov     [rsp+4C8h+var_480], rdx
0x1800334dd  mov     r15, rdx
0x1800334e0  mov     [rsp+4C8h+var_478], r9
0x1800334e5  mov     rbx, rcx
0x1800334e8  mov     esi, 208h
0x1800334ed  xor     edi, edi
0x1800334ef  lea     rcx, [rsp+4C8h+var_258]; void *
0x1800334f7  mov     r8d, esi; Size
0x1800334fa  mov     [rsp+4C8h+var_488], edi
0x1800334fe  xor     edx, edx; Val
0x180033500  call    memset_0
0x180033505  mov     r8d, esi; Size
0x180033508  lea     rcx, [rsp+4C8h+var_468]; void *
0x18003350d  xor     edx, edx; Val
0x18003350f  call    memset_0
0x180033514  or      r14, 0FFFFFFFFFFFFFFFFh
0x180033518  mov     ebp, edi
0x18003351a  test    r15, r15
0x18003351d  jz      loc_1800336B0
0x180033523  mov     r15, [r15]
0x180033526  mov     rax, r14
0x180033529  inc     rax
0x18003352c  cmp     [r15+rax*2], di
0x180033531  jnz     short loc_180033529
0x180033533  mov     rcx, gs:60h
0x18003353c  lea     edi, [rax+1]
0x18003353f  mov     r8d, edi
0x180033542  mov     r12d, 8
0x180033548  add     r8, r8; Size
0x18003354b  mov     edx, r12d; Flags
0x18003354e  mov     rcx, [rcx+30h]; HeapHandle
0x180033552  call    cs:__imp_RtlAllocateHeap
0x180033558  mov     rsi, rax
0x18003355b  test    rax, rax
0x18003355e  jnz     short loc_180033583
0x180033560  lea     r9, aUnableToAlloca_5; "Unable to allocate memory for directory"...
0x180033567  mov     r8d, 1B5h
0x18003356d  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x180033574  lea     ecx, [rax+1]
0x180033577  call    AslLogCallPrintf
0x18003357c  mov     eax, ebp
0x18003357e  jmp     loc_1800337FF
0x180033583  lea     rax, [rsp+4C8h+var_258]
0x18003358b  mov     r8d, edi
0x18003358e  lea     r9, [rsp+4C8h+var_468]
0x180033593  mov     [rsp+4C8h+var_4A0], rax
0x180033598  mov     rdx, rsi
0x18003359b  mov     rcx, r15
0x18003359e  call    AslPathSplit
0x1800335a3  test    eax, eax
0x1800335a5  jns     short loc_1800335D5
0x1800335a7  xor     r12d, r12d
0x1800335aa  mov     [rsp+4C8h+var_4A8], r15
0x1800335af  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x1800335b6  mov     r8d, 1C0h
0x1800335bc  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x1800335c3  mov     edi, r12d
0x1800335c6  lea     ecx, [r12+1]
0x1800335cb  call    AslLogCallPrintf
0x1800335d0  jmp     loc_1800337B2
0x1800335d5  mov     rcx, gs:60h
0x1800335de  mov     r8d, 208h; Size
0x1800335e4  mov     edx, r12d; Flags
0x1800335e7  mov     rcx, [rcx+30h]; HeapHandle
0x1800335eb  call    cs:__imp_RtlAllocateHeap
0x1800335f1  mov     rdi, rax
0x1800335f4  test    rax, rax
0x1800335f7  jnz     short loc_18003361A
0x1800335f9  lea     r9, aUnableToAlloca_3; "Unable to allocate memory for full name"
0x180033600  mov     r8d, 1C6h
0x180033606  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x18003360d  lea     ecx, [rax+1]
0x180033610  call    AslLogCallPrintf
0x180033615  jmp     loc_1800337B2
0x18003361a  mov     r10d, 104h
0x180033620  lea     r8, [rsp+4C8h+var_468]
0x180033625  mov     edx, r10d
0x180033628  mov     rcx, rdi
0x18003362b  call    RtlStringCchCopyW
0x180033630  test    eax, eax
0x180033632  js      loc_1800337B2
0x180033638  lea     r8, [rsp+4C8h+var_258]
0x180033640  mov     edx, r10d
0x180033643  mov     rcx, rdi
0x180033646  call    RtlStringCchCatW
0x18003364b  test    eax, eax
0x18003364d  js      loc_1800337B2
0x180033653  mov     r15, [rsp+4C8h+var_480]
0x180033658  xor     eax, eax
0x18003365a  test    r13, r13
0x18003365d  jz      loc_18003375C
0x180033663  inc     r14
0x180033666  cmp     [r13+r14*2+0], ax
0x18003366c  jnz     short loc_180033663
0x18003366e  mov     rcx, gs:60h
0x180033677  lea     eax, [r14+1]
0x18003367b  movsxd  r14, eax
0x18003367e  mov     edx, r12d; Flags
0x180033681  mov     rcx, [rcx+30h]; HeapHandle
0x180033685  lea     r8, [r14+r14]; Size
0x180033689  call    cs:__imp_RtlAllocateHeap
0x18003368f  xor     r12d, r12d
0x180033692  mov     rbp, rax
0x180033695  test    rax, rax
0x180033698  jnz     loc_180033748
0x18003369e  lea     r9, aUnableToAlloca_4; "Unable to allocate memory for szModule"
0x1800336a5  mov     r8d, 1E3h
0x1800336ab  jmp     loc_18003379C
0x1800336b0  mov     rcx, gs:60h
0x1800336b9  mov     r8d, 4; Size
0x1800336bf  mov     rcx, [rcx+30h]; HeapHandle
0x1800336c3  lea     r12d, [r8+4]
0x1800336c7  mov     edx, r12d; Flags
0x1800336ca  call    cs:__imp_RtlAllocateHeap
0x1800336d0  mov     rcx, gs:60h
0x1800336d9  lea     r8d, [r12-6]; Size
0x1800336de  mov     edx, r12d; Flags
0x1800336e1  mov     rsi, rax
0x1800336e4  mov     rcx, [rcx+30h]; HeapHandle
0x1800336e8  call    cs:__imp_RtlAllocateHeap
0x1800336ee  mov     rcx, gs:60h
0x1800336f7  lea     r8d, [r12-6]; Size
0x1800336fc  mov     edx, r12d; Flags
0x1800336ff  mov     rdi, rax
0x180033702  mov     rcx, [rcx+30h]; HeapHandle
0x180033706  call    cs:__imp_RtlAllocateHeap
0x18003370c  xor     r10d, r10d
0x18003370f  mov     r11, rax
0x180033712  test    rsi, rsi
0x180033715  jz      short loc_18003378F
0x180033717  test    rdi, rdi
0x18003371a  jz      short loc_18003378F
0x18003371c  test    rax, rax
0x18003371f  jz      short loc_18003378F
0x180033721  lea     r8, asc_180060EDC; "."
0x180033728  mov     rcx, rsi
0x18003372b  lea     edx, [r12-6]
0x180033730  call    RtlStringCchCopyW
0x180033735  mov     [rdi], r10w
0x180033739  xor     eax, eax
0x18003373b  mov     [r11], ax
0x18003373f  mov     [rbx+18h], r11
0x180033743  jmp     loc_180033658
0x180033748  mov     r8, r13
0x18003374b  mov     rdx, r14
0x18003374e  mov     rcx, rax
0x180033751  call    RtlStringCchCopyW
0x180033756  test    eax, eax
0x180033758  jns     short loc_18003375F
0x18003375a  jmp     short loc_1800337AD
0x18003375c  xor     r12d, r12d
0x18003375f  mov     rax, [rsp+4C8h+var_478]
0x180033764  mov     [rbx+38h], rax
0x180033768  mov     eax, 1
0x18003376d  mov     [rbx+8], r15
0x180033771  mov     [rbx+20h], rsi
0x180033775  mov     [rbx+28h], rdi
0x180033779  mov     [rbx+30h], rbp
0x18003377d  mov     [rbx+48h], r12
0x180033781  mov     [rbx+40h], r12
0x180033785  mov     [rbx+58h], r12
0x180033789  mov     [rbx+60h], r12
0x18003378d  jmp     short loc_1800337FF
0x18003378f  lea     r9, aUnableToAlloca_2; "Unable to allocate memory"
0x180033796  mov     r8d, 1D5h
0x18003379c  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x1800337a3  mov     ecx, 1
0x1800337a8  call    AslLogCallPrintf
0x1800337ad  test    rsi, rsi
0x1800337b0  jz      short loc_1800337C7
0x1800337b2  mov     rcx, gs:60h
0x1800337bb  mov     rdx, rsi
0x1800337be  mov     rcx, [rcx+30h]
0x1800337c2  call    AslFree
0x1800337c7  test    rdi, rdi
0x1800337ca  jz      short loc_1800337E1
0x1800337cc  mov     rcx, gs:60h
0x1800337d5  mov     rdx, rdi
0x1800337d8  mov     rcx, [rcx+30h]
0x1800337dc  call    AslFree
0x1800337e1  test    rbp, rbp
0x1800337e4  jz      short loc_1800337FB
0x1800337e6  mov     rcx, gs:60h
0x1800337ef  mov     rdx, rbp
0x1800337f2  mov     rcx, [rcx+30h]
0x1800337f6  call    AslFree
0x1800337fb  mov     eax, [rsp+4C8h+var_488]
0x1800337ff  mov     rcx, [rsp+4C8h+var_48]
0x180033807  xor     rcx, rsp; StackCookie
0x18003380a  call    __security_check_cookie
0x18003380f  mov     rbx, [rsp+4C8h+arg_18]
0x180033817  add     rsp, 490h
0x18003381e  pop     r15
0x180033820  pop     r14
0x180033822  pop     r13
0x180033824  pop     r12
0x180033826  pop     rdi
0x180033827  pop     rsi
0x180033828  pop     rbp
0x180033829  retn
```

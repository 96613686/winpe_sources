# PinCacheAdd

- ea: `0x18002a368`
- end: `0x18002a790`
- name: `PinCacheAdd`
- size: `1064`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800102a8`
- `0x18002b1a4`

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000de80`
- `0x180029fcc`
- `0x18002a020`
- `0x18002a20c`
- `0x18002a310`
- `0x18002a368`
- `0x18002cf46`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a64f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002a64f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a5df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a674`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002a6d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a683`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a6b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a6e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a5b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a683`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a6b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002a6e6`

## pseudocode

```c
__int64 __fastcall PinCacheAdd(
        _QWORD *a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(__int64, __int64),
        __int64 a6)
{
  unsigned int v6; // r15d
  void *v7; // rbp
  unsigned int v9; // r9d
  unsigned int Luid; // ebx
  _OWORD *v11; // r14
  void **v12; // rdi
  unsigned int v13; // eax
  int v14; // r13d
  unsigned int v15; // eax
  void *v16; // r12
  int v17; // ecx
  unsigned __int8 v18; // cf
  int v19; // ecx
  int v20; // eax
  BOOL v21; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rax
  int v24; // r14d
  unsigned __int64 v25; // rax
  unsigned int v26; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v28; // r8
  void *v29; // rax
  void *v30; // r12
  void *v31; // rbx
  HANDLE v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  _OWORD *v37; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  _QWORD *v40; // rax
  _BYTE *v41; // rax
  __int64 v42; // rcx
  int v44; // [rsp+30h] [rbp-68h]
  BOOL v45; // [rsp+34h] [rbp-64h]
  unsigned int v46; // [rsp+38h] [rbp-60h]
  void *Buf1; // [rsp+40h] [rbp-58h] BYREF
  int v50; // [rsp+B0h] [rbp+18h]
  size_t Size; // [rsp+B8h] [rbp+20h] BYREF

  v50 = a3;
  v6 = 0;
  v7 = 0;
  LODWORD(Size) = 0;
  v9 = *(_DWORD *)a4;
  Buf1 = 0;
  if ( v9 - 1 > 7 )
  {
    Luid = 160;
    goto LABEL_56;
  }
  if ( a3 && (unsigned int)(*(_DWORD *)(a3 + 24) - 2) <= 1 )
  {
    Luid = a5(a4, a6);
    goto LABEL_56;
  }
  v11 = (_OWORD *)*a1;
  v46 = v9 - 1;
  v44 = *(_DWORD *)(a4 + 4);
  if ( *a1 )
  {
    v12 = (void **)*((_QWORD *)v11 + v9 - 1);
    v13 = I_PinCacheLookup(v12);
    Luid = v13;
    if ( v13 && v13 != 4306 )
      goto LABEL_56;
  }
  else
  {
    v12 = 0;
    Luid = 4306;
  }
  v14 = 0;
  v45 = Luid == 0;
  if ( v12 )
  {
    v15 = I_PinCacheDecryptPin(v12, &Buf1, &Size);
    v7 = Buf1;
    Luid = v15;
    if ( v15 )
    {
      v6 = Size;
      goto LABEL_41;
    }
    v6 = Size;
    if ( *((_DWORD *)v12 + 8)
      || *(_DWORD *)(a4 + 12) != (_DWORD)Size
      || memcmp_0(Buf1, *(const void **)(a4 + 16), (unsigned int)Size) )
    {
      v14 = 1;
    }
  }
  else
  {
    Luid = 0;
  }
  v16 = *(void **)(a4 + 32);
  Buf1 = v16;
  if ( v16 )
  {
    v14 = 1;
    LODWORD(Size) = *(_DWORD *)(a4 + 24);
  }
  else
  {
    v17 = a2;
    v18 = _bittest(&v17, *(_DWORD *)a4);
    v16 = *(void **)(a4 + 16);
    v19 = *(_DWORD *)(a4 + 4);
    if ( !v18 )
      v14 = 1;
    v20 = *(_DWORD *)(a4 + 12);
    LODWORD(Size) = v20;
    Buf1 = v16;
    v44 = v19;
    if ( !v14 && v12 )
      goto LABEL_28;
  }
  Luid = a5(a4, a6);
  if ( Luid )
    goto LABEL_41;
  if ( *(_QWORD *)(a4 + 48) )
  {
    v16 = *(void **)(a4 + 48);
    v20 = *(_DWORD *)(a4 + 40);
    Buf1 = v16;
    LODWORD(Size) = v20;
    v44 = 1;
  }
  else
  {
    v20 = Size;
  }
  if ( v12 )
  {
LABEL_28:
    if ( v20 == v6 && !memcmp_0(v16, v7, v6) )
    {
      v21 = v45;
    }
    else
    {
      memset_0(*v12, 0, 8LL * *((unsigned int *)v12 + 3));
      v21 = 0;
      *((_DWORD *)v12 + 2) = 0;
    }
    if ( !v21 )
    {
      v22 = *((unsigned int *)v12 + 3);
      if ( (unsigned int)v22 <= *((_DWORD *)v12 + 2) )
      {
        v23 = 2 * v22;
        if ( v23 > 0xFFFFFFFF || (v24 = v23, v25 = 8LL * (unsigned int)v23, v25 > 0xFFFFFFFF) )
        {
          Luid = 534;
          goto LABEL_41;
        }
        v26 = v25;
        ProcessHeap = GetProcessHeap();
        v28 = v26;
        Luid = 8;
        v29 = HeapAlloc(ProcessHeap, 8u, v28);
        v30 = v29;
        if ( !v29 )
          goto LABEL_41;
        memcpy_0(v29, *v12, 8LL * *((unsigned int *)v12 + 3));
        v31 = *v12;
        *((_DWORD *)v12 + 3) = v24;
        v32 = GetProcessHeap();
        HeapFree(v32, 0, v31);
        *v12 = v30;
      }
      Luid = I_PinCacheGetLuid((_QWORD *)*v12 + *((unsigned int *)v12 + 2));
      if ( Luid )
        goto LABEL_41;
      ++*((_DWORD *)v12 + 2);
    }
    if ( v14 )
      goto LABEL_54;
    goto LABEL_41;
  }
  Luid = 8;
  if ( !v11 )
  {
    v36 = GetProcessHeap();
    v37 = HeapAlloc(v36, 8u, 0x40u);
    v11 = v37;
    if ( !v37 )
      goto LABEL_41;
    *v37 = 0;
    v37[1] = 0;
    v37[2] = 0;
    v37[3] = 0;
  }
  v38 = GetProcessHeap();
  v12 = (void **)HeapAlloc(v38, 8u, 0x38u);
  if ( v12 )
  {
    *((_QWORD *)v11 + v46) = v12;
    *((_DWORD *)v12 + 3) = 10;
    v39 = GetProcessHeap();
    v40 = HeapAlloc(v39, 8u, 0x50u);
    *v12 = v40;
    if ( v40 )
    {
      Luid = I_PinCacheGetLuid(v40);
      if ( !Luid )
      {
        ++*((_DWORD *)v12 + 2);
        *a1 = v11;
LABEL_54:
        Luid = I_CommitPinToCache((_DWORD)v12, (_DWORD)Buf1, Size, v50, v44);
      }
    }
  }
LABEL_41:
  if ( v7 )
  {
    v33 = v6;
    v34 = v7;
    if ( v6 )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v7);
  }
LABEL_56:
  v41 = *(_BYTE **)(a4 + 48);
  if ( v41 )
  {
    v42 = *(unsigned int *)(a4 + 40);
    if ( *(_DWORD *)(a4 + 40) )
    {
      do
      {
        *v41++ = 0;
        --v42;
      }
      while ( v42 );
    }
    CspFreeH(*(_QWORD *)(a4 + 48));
    *(_QWORD *)(a4 + 48) = 0;
  }
  return Luid;
}

```

## disassembly

```asm
0x18002a368  mov     rax, rsp
0x18002a36b  mov     [rax+18h], r8
0x18002a36f  mov     [rax+10h], edx
0x18002a372  mov     [rax+8], rcx
0x18002a376  push    rbx
0x18002a377  push    rbp
0x18002a378  push    rsi
0x18002a379  push    rdi
0x18002a37a  push    r12
0x18002a37c  push    r13
0x18002a37e  push    r14
0x18002a380  push    r15
0x18002a382  sub     rsp, 58h
0x18002a386  xor     r15d, r15d
0x18002a389  xor     ebp, ebp
0x18002a38b  mov     rsi, r9
0x18002a38e  mov     [rax+20h], r15d
0x18002a392  mov     r9d, [r9]
0x18002a395  mov     [rax-58h], rbp
0x18002a399  lea     r12d, [r15+1]
0x18002a39d  lea     eax, [r9-1]
0x18002a3a1  cmp     eax, 7
0x18002a3a4  ja      loc_18002A74B
0x18002a3aa  test    r8, r8
0x18002a3ad  jz      short loc_18002A3DA
0x18002a3af  mov     eax, [r8+18h]
0x18002a3b3  sub     eax, 2
0x18002a3b6  cmp     eax, r12d
0x18002a3b9  ja      short loc_18002A3DA
0x18002a3bb  mov     rdx, [rsp+98h+arg_28]
0x18002a3c3  mov     rcx, rsi
0x18002a3c6  mov     rax, [rsp+98h+arg_20]
0x18002a3ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3d3  mov     ebx, eax
0x18002a3d5  jmp     loc_18002A750
0x18002a3da  mov     r14, [rcx]
0x18002a3dd  lea     eax, [r9-1]
0x18002a3e1  mov     ecx, [rsi+4]
0x18002a3e4  mov     [rsp+98h+var_60], eax
0x18002a3e8  mov     [rsp+98h+var_68], ecx
0x18002a3ec  test    r14, r14
0x18002a3ef  jnz     short loc_18002A3FA
0x18002a3f1  xor     edi, edi
0x18002a3f3  mov     ebx, 10D2h
0x18002a3f8  jmp     short loc_18002A417
0x18002a3fa  mov     rdi, [r14+rax*8]
0x18002a3fe  mov     rcx, rdi
0x18002a401  call    I_PinCacheLookup
0x18002a406  mov     ebx, eax
0x18002a408  test    eax, eax
0x18002a40a  jz      short loc_18002A417
0x18002a40c  cmp     eax, 10D2h
0x18002a411  jnz     loc_18002A750
0x18002a417  xor     eax, eax
0x18002a419  xor     r13d, r13d
0x18002a41c  test    ebx, ebx
0x18002a41e  setz    al
0x18002a421  mov     [rsp+98h+var_64], eax
0x18002a425  test    rdi, rdi
0x18002a428  jz      short loc_18002A483
0x18002a42a  lea     r8, [rsp+98h+Size]
0x18002a432  mov     rcx, rdi
0x18002a435  lea     rdx, [rsp+98h+Buf1]
0x18002a43a  call    I_PinCacheDecryptPin
0x18002a43f  mov     rbp, [rsp+98h+Buf1]
0x18002a444  mov     ebx, eax
0x18002a446  test    eax, eax
0x18002a448  jnz     short loc_18002A476
0x18002a44a  mov     r15d, dword ptr [rsp+98h+Size]
0x18002a452  cmp     [rdi+20h], r13d
0x18002a456  jnz     short loc_18002A471
0x18002a458  cmp     [rsi+0Ch], r15d
0x18002a45c  jnz     short loc_18002A471
0x18002a45e  mov     rdx, [rsi+10h]; Buf2
0x18002a462  mov     r8d, r15d; Size
0x18002a465  mov     rcx, rbp; Buf1
0x18002a468  call    memcmp_0
0x18002a46d  test    eax, eax
0x18002a46f  jz      short loc_18002A485
0x18002a471  mov     r13d, r12d
0x18002a474  jmp     short loc_18002A485
0x18002a476  mov     r15d, dword ptr [rsp+98h+Size]
0x18002a47e  jmp     loc_18002A622
0x18002a483  xor     ebx, ebx
0x18002a485  mov     r12, [rsi+20h]
0x18002a489  mov     [rsp+98h+Buf1], r12
0x18002a48e  test    r12, r12
0x18002a491  jz      short loc_18002A4A7
0x18002a493  mov     r8d, [rsi+18h]
0x18002a497  mov     r13d, 1
0x18002a49d  mov     dword ptr [rsp+98h+Size], r8d
0x18002a4a5  jmp     short loc_18002A4E0
0x18002a4a7  mov     eax, [rsi]
0x18002a4a9  mov     ecx, [rsp+98h+arg_8]
0x18002a4b0  bt      ecx, eax
0x18002a4b3  mov     r12, [rsi+10h]
0x18002a4b7  mov     eax, 1
0x18002a4bc  mov     ecx, [rsi+4]
0x18002a4bf  cmovnb  r13d, eax
0x18002a4c3  mov     eax, [rsi+0Ch]
0x18002a4c6  mov     dword ptr [rsp+98h+Size], eax
0x18002a4cd  mov     [rsp+98h+Buf1], r12
0x18002a4d2  mov     [rsp+98h+var_68], ecx
0x18002a4d6  test    r13d, r13d
0x18002a4d9  jnz     short loc_18002A4E0
0x18002a4db  test    rdi, rdi
0x18002a4de  jnz     short loc_18002A536
0x18002a4e0  mov     rdx, [rsp+98h+arg_28]
0x18002a4e8  mov     rcx, rsi
0x18002a4eb  mov     rax, [rsp+98h+arg_20]
0x18002a4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4f8  mov     ebx, eax
0x18002a4fa  test    eax, eax
0x18002a4fc  jnz     loc_18002A61C
0x18002a502  cmp     qword ptr [rsi+30h], 0
0x18002a507  jz      short loc_18002A526
0x18002a509  mov     r12, [rsi+30h]
0x18002a50d  mov     eax, [rsi+28h]
0x18002a510  mov     [rsp+98h+Buf1], r12
0x18002a515  mov     dword ptr [rsp+98h+Size], eax
0x18002a51c  mov     [rsp+98h+var_68], 1
0x18002a524  jmp     short loc_18002A52D
0x18002a526  mov     eax, dword ptr [rsp+98h+Size]
0x18002a52d  test    rdi, rdi
0x18002a530  jz      loc_18002A66A
0x18002a536  cmp     eax, r15d
0x18002a539  jnz     short loc_18002A553
0x18002a53b  mov     r8d, r15d; Size
0x18002a53e  mov     rdx, rbp; Buf2
0x18002a541  mov     rcx, r12; Buf1
0x18002a544  call    memcmp_0
0x18002a549  test    eax, eax
0x18002a54b  jnz     short loc_18002A553
0x18002a54d  mov     eax, [rsp+98h+var_64]
0x18002a551  jmp     short loc_18002A56A
0x18002a553  mov     r8d, [rdi+0Ch]
0x18002a557  xor     edx, edx; Val
0x18002a559  mov     rcx, [rdi]; void *
0x18002a55c  shl     r8, 3; Size
0x18002a560  call    memset_0
0x18002a565  xor     eax, eax
0x18002a567  mov     [rdi+8], eax
0x18002a56a  test    rdi, rdi
0x18002a56d  jz      loc_18002A66A
0x18002a573  test    eax, eax
0x18002a575  jnz     loc_18002A65A
0x18002a57b  mov     eax, [rdi+0Ch]
0x18002a57e  cmp     eax, [rdi+8]
0x18002a581  ja      short loc_18002A5F6
0x18002a583  add     rax, rax
0x18002a586  mov     ecx, 0FFFFFFFFh
0x18002a58b  cmp     rax, rcx
0x18002a58e  ja      loc_18002A617
0x18002a594  mov     r14d, eax
0x18002a597  mov     eax, eax
0x18002a599  shl     rax, 3
0x18002a59d  cmp     rax, rcx
0x18002a5a0  ja      short loc_18002A617
0x18002a5a2  mov     ebx, eax
0x18002a5a4  call    cs:__imp_GetProcessHeap
0x18002a5aa  mov     r8d, ebx; dwBytes
0x18002a5ad  mov     ebx, 8
0x18002a5b2  mov     edx, ebx; dwFlags
0x18002a5b4  mov     rcx, rax; hHeap
0x18002a5b7  call    cs:__imp_HeapAlloc
0x18002a5bd  mov     r12, rax
0x18002a5c0  test    rax, rax
0x18002a5c3  jz      short loc_18002A61C
0x18002a5c5  mov     r8d, [rdi+0Ch]
0x18002a5c9  mov     rcx, rax; void *
0x18002a5cc  mov     rdx, [rdi]; Src
0x18002a5cf  shl     r8, 3; Size
0x18002a5d3  call    memcpy_0
0x18002a5d8  mov     rbx, [rdi]
0x18002a5db  mov     [rdi+0Ch], r14d
0x18002a5df  call    cs:__imp_GetProcessHeap
0x18002a5e5  mov     r8, rbx; lpMem
0x18002a5e8  xor     edx, edx; dwFlags
0x18002a5ea  mov     rcx, rax; hHeap
0x18002a5ed  call    cs:__imp_HeapFree
0x18002a5f3  mov     [rdi], r12
0x18002a5f6  mov     ecx, [rdi+8]
0x18002a5f9  mov     rax, [rdi]
0x18002a5fc  lea     rcx, [rax+rcx*8]
0x18002a600  call    I_PinCacheGetLuid
0x18002a605  mov     ebx, eax
0x18002a607  mov     r12d, 1
0x18002a60d  test    eax, eax
0x18002a60f  jnz     short loc_18002A622
0x18002a611  add     [rdi+8], r12d
0x18002a615  jmp     short loc_18002A660
0x18002a617  mov     ebx, 216h
0x18002a61c  mov     r12d, 1
0x18002a622  test    rbp, rbp
0x18002a625  jz      loc_18002A750
0x18002a62b  mov     ecx, r15d
0x18002a62e  mov     rax, rbp
0x18002a631  test    r15d, r15d
0x18002a634  jz      short loc_18002A641
0x18002a636  mov     byte ptr [rax], 0
0x18002a639  add     rax, r12
0x18002a63c  sub     rcx, r12
0x18002a63f  jnz     short loc_18002A636
0x18002a641  call    cs:__imp_GetProcessHeap
0x18002a647  mov     r8, rbp; lpMem
0x18002a64a  xor     edx, edx; dwFlags
0x18002a64c  mov     rcx, rax; hHeap
0x18002a64f  call    cs:__imp_HeapFree
0x18002a655  jmp     loc_18002A750
0x18002a65a  mov     r12d, 1
0x18002a660  test    r13d, r13d
0x18002a663  jz      short loc_18002A622
0x18002a665  jmp     loc_18002A71F
0x18002a66a  mov     ebx, 8
0x18002a66f  test    r14, r14
0x18002a672  jnz     short loc_18002A6A3
0x18002a674  call    cs:__imp_GetProcessHeap
0x18002a67a  lea     r8d, [rbx+38h]; dwBytes
0x18002a67e  mov     edx, ebx; dwFlags
0x18002a680  mov     rcx, rax; hHeap
0x18002a683  call    cs:__imp_HeapAlloc
0x18002a689  mov     r14, rax
0x18002a68c  test    rax, rax
0x18002a68f  jz      short loc_18002A61C
0x18002a691  xorps   xmm0, xmm0
0x18002a694  movups  xmmword ptr [rax], xmm0
0x18002a697  movups  xmmword ptr [rax+10h], xmm0
0x18002a69b  movups  xmmword ptr [rax+20h], xmm0
0x18002a69f  movups  xmmword ptr [rax+30h], xmm0
0x18002a6a3  call    cs:__imp_GetProcessHeap
0x18002a6a9  mov     r8d, 38h ; '8'; dwBytes
0x18002a6af  mov     edx, ebx; dwFlags
0x18002a6b1  mov     rcx, rax; hHeap
0x18002a6b4  call    cs:__imp_HeapAlloc
0x18002a6ba  mov     rdi, rax
0x18002a6bd  test    rax, rax
0x18002a6c0  jz      loc_18002A61C
0x18002a6c6  mov     eax, [rsp+98h+var_60]
0x18002a6ca  mov     [r14+rax*8], rdi
0x18002a6ce  mov     dword ptr [rdi+0Ch], 0Ah
0x18002a6d5  call    cs:__imp_GetProcessHeap
0x18002a6db  mov     r8d, 50h ; 'P'; dwBytes
0x18002a6e1  mov     edx, ebx; dwFlags
0x18002a6e3  mov     rcx, rax; hHeap
0x18002a6e6  call    cs:__imp_HeapAlloc
0x18002a6ec  mov     [rdi], rax
0x18002a6ef  test    rax, rax
0x18002a6f2  jz      loc_18002A61C
0x18002a6f8  mov     rcx, rax
0x18002a6fb  call    I_PinCacheGetLuid
0x18002a700  mov     ebx, eax
0x18002a702  mov     r12d, 1
0x18002a708  test    eax, eax
0x18002a70a  jnz     loc_18002A622
0x18002a710  mov     rax, [rsp+98h+arg_0]
0x18002a718  add     [rdi+8], r12d
0x18002a71c  mov     [rax], r14
0x18002a71f  mov     eax, [rsp+98h+var_68]
0x18002a723  mov     rcx, rdi
0x18002a726  mov     r9, [rsp+98h+arg_10]
0x18002a72e  mov     r8d, dword ptr [rsp+98h+Size]
0x18002a736  mov     rdx, [rsp+98h+Buf1]
0x18002a73b  mov     [rsp+98h+var_78], eax
0x18002a73f  call    I_CommitPinToCache
0x18002a744  mov     ebx, eax
0x18002a746  jmp     loc_18002A622
0x18002a74b  mov     ebx, 0A0h
0x18002a750  mov     rax, [rsi+30h]
0x18002a754  test    rax, rax
0x18002a757  jz      short loc_18002A77D
0x18002a759  mov     ecx, [rsi+28h]
0x18002a75c  test    rcx, rcx
0x18002a75f  jz      short loc_18002A76C
0x18002a761  mov     byte ptr [rax], 0
0x18002a764  add     rax, r12
0x18002a767  sub     rcx, r12
0x18002a76a  jnz     short loc_18002A761
0x18002a76c  mov     rcx, [rsi+30h]
0x18002a770  call    CspFreeH
0x18002a775  mov     qword ptr [rsi+30h], 0
0x18002a77d  mov     eax, ebx
0x18002a77f  add     rsp, 58h
0x18002a783  pop     r15
0x18002a785  pop     r14
0x18002a787  pop     r13
0x18002a789  pop     r12
0x18002a78b  pop     rdi
0x18002a78c  pop     rsi
0x18002a78d  pop     rbp
0x18002a78e  pop     rbx
0x18002a78f  retn
```

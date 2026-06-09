# CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Initialize(void)

- ea: `0x1400878f4`
- end: `0x140087c04`
- name: `?Initialize@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAAJXZ`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1401670a8`

## callees

- `0x140049050`
- `0x1400878f4`
- `0x140088930`
- `0x1400b4c5c`
- `0x1400ceda0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008794f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087a75`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008794f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140087a75`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140087911`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140087a3d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140087911`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140087a3d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14008795d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140087a83`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14008795d`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140087a83`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087998`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087abe`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087998`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140087abe`

## string_xrefs

- `0x140087bf7`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Initialize(
        unsigned __int16 *a1)
{
  unsigned __int64 v2; // rbp
  const struct std::nothrow_t *v3; // rdx
  unsigned int *v4; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  int v8; // ecx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rax
  int v11; // eax
  unsigned int v12; // edx
  int v13; // r8d
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  const struct std::nothrow_t *v16; // rdx
  unsigned int *v17; // rdi
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  int v21; // ecx
  unsigned __int64 v22; // rcx
  _QWORD *v23; // rax
  int v24; // eax
  unsigned int v25; // edx
  int v26; // r8d
  __int64 v27; // rax
  unsigned __int16 v28; // r8
  unsigned __int16 i; // ax
  __int64 v30; // rdx
  unsigned __int128 v31; // rax
  unsigned __int64 v32; // kr00_8
  void *v33; // rax
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx

  v2 = 8LL * *a1 + 48;
  v3 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v4 = (unsigned int *)(qword_140269490 + 192LL * (_QWORD)v3);
  if ( v2 > *v4 )
  {
    v4 = 0;
    goto LABEL_16;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v5 = (struct _NPAGED_LOOKASIDE_LIST *)(v4 + 16);
    if ( *((_BYTE *)v4 + 9) )
      v6 = ExAllocateFromNPagedLookasideList(v5);
    else
      v6 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v5);
    goto LABEL_6;
  }
  if ( (int)*((_QWORD *)v4 + 11) <= (int)HIDWORD(*((_QWORD *)v4 + 11)) )
    goto LABEL_13;
  v8 = _InterlockedDecrement((volatile signed __int32 *)v4 + 22);
  if ( v8 >= (int)v4[23] && v8 >= 0 )
  {
    v6 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v4 + 4);
LABEL_6:
    v7 = v6;
    goto LABEL_12;
  }
  v7 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v4 + 22);
LABEL_12:
  if ( v7 )
  {
LABEL_19:
    *v7 = v4;
    v7 += 2;
    goto LABEL_20;
  }
LABEL_13:
  if ( v4 )
  {
    v9 = v4[1];
    goto LABEL_17;
  }
LABEL_16:
  v9 = v2 + 16;
LABEL_17:
  v10 = operator new(v9, v3);
  v7 = v10;
  if ( ((unsigned __int8)v10 & 0xF) != 0 )
    goto LABEL_64;
  if ( v10 )
    goto LABEL_19;
LABEL_20:
  if ( v7 )
  {
    v11 = *a1;
    v12 = 0;
    *v7 = 0;
    v13 = v11;
    v7[1] = 0;
    v7[2] = 0;
    *((_WORD *)v7 + 12) = 0;
    v7[4] = 0;
    v7[5] = 0;
    if ( v11 )
    {
      do
      {
        v14 = v12++;
        v7[v14 + 6] = 0;
      }
      while ( (int)v12 < v13 );
    }
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)a1 + 2) = v7;
  if ( !v7 )
    goto LABEL_57;
  v15 = 8LL * *a1 + 48;
  v16 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v17 = (unsigned int *)(qword_140269490 + 192LL * (_QWORD)v16);
  if ( v15 > *v17 )
  {
    v17 = 0;
    goto LABEL_41;
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v17 + 16);
    if ( *((_BYTE *)v17 + 9) )
      v19 = ExAllocateFromNPagedLookasideList(v18);
    else
      v19 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18);
    goto LABEL_31;
  }
  if ( (int)*((_QWORD *)v17 + 11) <= (int)HIDWORD(*((_QWORD *)v17 + 11)) )
    goto LABEL_38;
  v21 = _InterlockedDecrement((volatile signed __int32 *)v17 + 22);
  if ( v21 >= (int)v17[23] && v21 >= 0 )
  {
    v19 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17 + 4);
LABEL_31:
    v20 = v19;
    goto LABEL_37;
  }
  v20 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v17 + 22);
LABEL_37:
  if ( !v20 )
  {
LABEL_38:
    if ( v17 )
    {
      v22 = v17[1];
      goto LABEL_42;
    }
LABEL_41:
    v22 = v15 + 16;
LABEL_42:
    v23 = operator new(v22, v16);
    v20 = v23;
    if ( ((unsigned __int8)v23 & 0xF) == 0 )
    {
      if ( !v23 )
        goto LABEL_45;
      goto LABEL_44;
    }
LABEL_64:
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  }
LABEL_44:
  *v20 = v17;
  v20 += 2;
LABEL_45:
  if ( v20 )
  {
    v24 = *a1;
    v25 = 0;
    *v20 = 0;
    v26 = v24;
    v20[1] = 0;
    v20[2] = 0;
    *((_WORD *)v20 + 12) = 0;
    v20[4] = 0;
    v20[5] = 0;
    if ( v24 )
    {
      do
      {
        v27 = v25++;
        v20[v27 + 6] = 0;
      }
      while ( (int)v25 < v26 );
    }
  }
  else
  {
    v20 = 0;
  }
  *((_QWORD *)a1 + 3) = v20;
  if ( v20 )
  {
    v28 = 0;
    *(_QWORD *)(*((_QWORD *)a1 + 2) + 32LL) = v20;
    *(_QWORD *)(*((_QWORD *)a1 + 3) + 40LL) = *((_QWORD *)a1 + 2);
    for ( i = *a1; v28 < *a1; i = *a1 )
    {
      v30 = v28++;
      *(_QWORD *)(*((_QWORD *)a1 + 2) + 8 * v30 + 48) = *((_QWORD *)a1 + 3);
    }
    v32 = i;
    v31 = i * (unsigned __int128)8uLL;
    if ( !is_mul_ok(v32, 8u) )
      *(_QWORD *)&v31 = -1;
    v33 = operator new(v31, *((const struct std::nothrow_t **)&v31 + 1));
    *((_QWORD *)a1 + 13) = v33;
    if ( v33 )
      return 0;
  }
LABEL_57:
  v35 = (void *)*((_QWORD *)a1 + 2);
  if ( v35 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v35);
    *((_QWORD *)a1 + 2) = 0;
  }
  v36 = (void *)*((_QWORD *)a1 + 3);
  if ( v36 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v36);
    *((_QWORD *)a1 + 3) = 0;
  }
  v37 = (void *)*((_QWORD *)a1 + 13);
  if ( v37 )
  {
    operator delete(v37);
    *((_QWORD *)a1 + 13) = 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400878f4  push    rbx
0x1400878f6  push    rbp
0x1400878f7  push    rsi
0x1400878f8  push    rdi
0x1400878f9  push    r14
0x1400878fb  push    r15
0x1400878fd  sub     rsp, 28h
0x140087901  movzx   eax, word ptr [rcx]
0x140087904  mov     rsi, rcx
0x140087907  xor     ecx, ecx; ProcNumber
0x140087909  lea     rbp, ds:30h[rax*8]
0x140087911  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140087918  nop     dword ptr [rax+rax+00h]
0x14008791d  xor     edx, edx; struct std::nothrow_t *
0x14008791f  or      r15, 0FFFFFFFFFFFFFFFFh
0x140087923  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140087929  xor     ebx, ebx
0x14008792b  lea     rdi, [rdx+rdx*2]
0x14008792f  shl     rdi, 6
0x140087933  add     rdi, cs:qword_140269490
0x14008793a  mov     eax, [rdi]
0x14008793c  cmp     rbp, rax
0x14008793f  ja      short loc_1400879BE
0x140087941  cmp     [rdi+8], bl
0x140087944  jz      short loc_14008796E
0x140087946  lea     rcx, [rdi+40h]; Lookaside
0x14008794a  cmp     [rdi+9], bl
0x14008794d  jz      short loc_14008795D
0x14008794f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140087956  nop     dword ptr [rax+rax+00h]
0x14008795b  jmp     short loc_140087969
0x14008795d  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140087964  nop     dword ptr [rax+rax+00h]
0x140087969  mov     rcx, rax
0x14008796c  jmp     short loc_1400879AF
0x14008796e  mov     rcx, [rdi+58h]
0x140087972  mov     rax, rcx
0x140087975  sar     rax, 20h
0x140087979  cmp     ecx, eax
0x14008797b  jle     short loc_1400879B4
0x14008797d  nop
0x14008797e  mov     ecx, r15d
0x140087981  lock xadd [rdi+58h], ecx
0x140087986  nop
0x140087987  dec     ecx
0x140087989  mov     eax, [rdi+5Ch]
0x14008798c  cmp     ecx, eax
0x14008798e  jl      short loc_1400879A6
0x140087990  test    ecx, ecx
0x140087992  js      short loc_1400879A6
0x140087994  lea     rcx, [rdi+40h]; ListHead
0x140087998  call    cs:__imp_ExpInterlockedPopEntrySList
0x14008799f  nop     dword ptr [rax+rax+00h]
0x1400879a4  jmp     short loc_140087969
0x1400879a6  mov     rcx, rbx
0x1400879a9  nop
0x1400879aa  lock inc dword ptr [rdi+58h]
0x1400879ae  nop
0x1400879af  test    rcx, rcx
0x1400879b2  jnz     short loc_1400879DA
0x1400879b4  test    rdi, rdi
0x1400879b7  jz      short loc_1400879C1
0x1400879b9  mov     ecx, [rdi+4]
0x1400879bc  jmp     short loc_1400879C5
0x1400879be  mov     rdi, rbx
0x1400879c1  lea     rcx, [rbp+10h]; unsigned __int64
0x1400879c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400879ca  mov     rcx, rax
0x1400879cd  test    al, 0Fh
0x1400879cf  jnz     loc_140087BF7
0x1400879d5  test    rax, rax
0x1400879d8  jz      short loc_1400879E1
0x1400879da  mov     [rcx], rdi
0x1400879dd  add     rcx, 10h
0x1400879e1  mov     r14d, 1
0x1400879e7  test    rcx, rcx
0x1400879ea  jz      short loc_140087A20
0x1400879ec  movzx   eax, word ptr [rsi]
0x1400879ef  mov     edx, ebx
0x1400879f1  mov     [rcx], rbx
0x1400879f4  mov     r8d, eax
0x1400879f7  mov     [rcx+8], rbx
0x1400879fb  mov     [rcx+10h], rbx
0x1400879ff  mov     [rcx+18h], bx
0x140087a03  mov     [rcx+20h], rbx
0x140087a07  mov     [rcx+28h], rbx
0x140087a0b  test    eax, eax
0x140087a0d  jz      short loc_140087A23
0x140087a0f  mov     eax, edx
0x140087a11  add     edx, r14d
0x140087a14  mov     [rcx+rax*8+30h], rbx
0x140087a19  cmp     edx, r8d
0x140087a1c  jl      short loc_140087A0F
0x140087a1e  jmp     short loc_140087A23
0x140087a20  mov     rcx, rbx
0x140087a23  mov     [rsi+10h], rcx
0x140087a27  test    rcx, rcx
0x140087a2a  jz      loc_140087BBA
0x140087a30  movzx   eax, word ptr [rsi]
0x140087a33  xor     ecx, ecx; ProcNumber
0x140087a35  lea     rbp, ds:30h[rax*8]
0x140087a3d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140087a44  nop     dword ptr [rax+rax+00h]
0x140087a49  xor     edx, edx; struct std::nothrow_t *
0x140087a4b  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140087a51  lea     rdi, [rdx+rdx*2]
0x140087a55  shl     rdi, 6
0x140087a59  add     rdi, cs:qword_140269490
0x140087a60  mov     eax, [rdi]
0x140087a62  cmp     rbp, rax
0x140087a65  ja      short loc_140087AE4
0x140087a67  cmp     [rdi+8], bl
0x140087a6a  jz      short loc_140087A94
0x140087a6c  lea     rcx, [rdi+40h]; Lookaside
0x140087a70  cmp     [rdi+9], bl
0x140087a73  jz      short loc_140087A83
0x140087a75  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140087a7c  nop     dword ptr [rax+rax+00h]
0x140087a81  jmp     short loc_140087A8F
0x140087a83  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140087a8a  nop     dword ptr [rax+rax+00h]
0x140087a8f  mov     rcx, rax
0x140087a92  jmp     short loc_140087AD5
0x140087a94  mov     rcx, [rdi+58h]
0x140087a98  mov     rax, rcx
0x140087a9b  sar     rax, 20h
0x140087a9f  cmp     ecx, eax
0x140087aa1  jle     short loc_140087ADA
0x140087aa3  nop
0x140087aa4  mov     ecx, r15d
0x140087aa7  lock xadd [rdi+58h], ecx
0x140087aac  nop
0x140087aad  dec     ecx
0x140087aaf  mov     eax, [rdi+5Ch]
0x140087ab2  cmp     ecx, eax
0x140087ab4  jl      short loc_140087ACC
0x140087ab6  test    ecx, ecx
0x140087ab8  js      short loc_140087ACC
0x140087aba  lea     rcx, [rdi+40h]; ListHead
0x140087abe  call    cs:__imp_ExpInterlockedPopEntrySList
0x140087ac5  nop     dword ptr [rax+rax+00h]
0x140087aca  jmp     short loc_140087A8F
0x140087acc  mov     rcx, rbx
0x140087acf  nop
0x140087ad0  lock inc dword ptr [rdi+58h]
0x140087ad4  nop
0x140087ad5  test    rcx, rcx
0x140087ad8  jnz     short loc_140087B00
0x140087ada  test    rdi, rdi
0x140087add  jz      short loc_140087AE7
0x140087adf  mov     ecx, [rdi+4]
0x140087ae2  jmp     short loc_140087AEB
0x140087ae4  mov     rdi, rbx
0x140087ae7  lea     rcx, [rbp+10h]; unsigned __int64
0x140087aeb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140087af0  mov     rcx, rax
0x140087af3  test    al, 0Fh
0x140087af5  jnz     loc_140087BF7
0x140087afb  test    rax, rax
0x140087afe  jz      short loc_140087B07
0x140087b00  mov     [rcx], rdi
0x140087b03  add     rcx, 10h
0x140087b07  test    rcx, rcx
0x140087b0a  jz      short loc_140087B40
0x140087b0c  movzx   eax, word ptr [rsi]
0x140087b0f  mov     edx, ebx
0x140087b11  mov     [rcx], rbx
0x140087b14  mov     r8d, eax
0x140087b17  mov     [rcx+8], rbx
0x140087b1b  mov     [rcx+10h], rbx
0x140087b1f  mov     [rcx+18h], bx
0x140087b23  mov     [rcx+20h], rbx
0x140087b27  mov     [rcx+28h], rbx
0x140087b2b  test    eax, eax
0x140087b2d  jz      short loc_140087B43
0x140087b2f  mov     eax, edx
0x140087b31  add     edx, r14d
0x140087b34  mov     [rcx+rax*8+30h], rbx
0x140087b39  cmp     edx, r8d
0x140087b3c  jl      short loc_140087B2F
0x140087b3e  jmp     short loc_140087B43
0x140087b40  mov     rcx, rbx
0x140087b43  mov     [rsi+18h], rcx
0x140087b47  test    rcx, rcx
0x140087b4a  jz      short loc_140087BBA
0x140087b4c  mov     rax, [rsi+10h]
0x140087b50  movzx   r8d, bx
0x140087b54  mov     [rax+20h], rcx
0x140087b58  mov     rax, [rsi+10h]
0x140087b5c  mov     rcx, [rsi+18h]
0x140087b60  mov     [rcx+28h], rax
0x140087b64  movzx   eax, word ptr [rsi]
0x140087b67  cmp     bx, ax
0x140087b6a  jnb     short loc_140087B8A
0x140087b6c  mov     rax, [rsi+18h]
0x140087b70  mov     rcx, [rsi+10h]
0x140087b74  movzx   edx, r8w; struct std::nothrow_t *
0x140087b78  add     r8w, r14w
0x140087b7c  mov     [rcx+rdx*8+30h], rax
0x140087b81  movzx   eax, word ptr [rsi]
0x140087b84  cmp     r8w, ax
0x140087b88  jb      short loc_140087B6C
0x140087b8a  movzx   ecx, ax
0x140087b8d  mov     eax, 8
0x140087b92  mul     rcx
0x140087b95  cmovb   rax, r15
0x140087b99  mov     rcx, rax; unsigned __int64
0x140087b9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140087ba1  mov     [rsi+68h], rax
0x140087ba5  test    rax, rax
0x140087ba8  jz      short loc_140087BBA
0x140087baa  xor     eax, eax
0x140087bac  add     rsp, 28h
0x140087bb0  pop     r15
0x140087bb2  pop     r14
0x140087bb4  pop     rdi
0x140087bb5  pop     rsi
0x140087bb6  pop     rbp
0x140087bb7  pop     rbx
0x140087bb8  retn
0x140087bba  mov     rcx, [rsi+10h]; void *
0x140087bbe  test    rcx, rcx
0x140087bc1  jz      short loc_140087BCC
0x140087bc3  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x140087bc8  mov     [rsi+10h], rbx
0x140087bcc  mov     rcx, [rsi+18h]; void *
0x140087bd0  test    rcx, rcx
0x140087bd3  jz      short loc_140087BDE
0x140087bd5  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x140087bda  mov     [rsi+18h], rbx
0x140087bde  mov     rcx, [rsi+68h]; void *
0x140087be2  test    rcx, rcx
0x140087be5  jz      short loc_140087BF0
0x140087be7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140087bec  mov     [rsi+68h], rbx
0x140087bf0  mov     eax, 0C000009Ah
0x140087bf5  jmp     short loc_140087BAC
0x140087bf7  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140087bfe  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
```

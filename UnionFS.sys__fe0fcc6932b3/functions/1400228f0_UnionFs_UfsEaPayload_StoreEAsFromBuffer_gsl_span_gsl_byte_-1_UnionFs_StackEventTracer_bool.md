# UnionFs::UfsEaPayload::StoreEAsFromBuffer(gsl::span<gsl::byte,-1> &,UnionFs::StackEventTracer &,bool)

- ea: `0x1400228f0`
- end: `0x140022e1a`
- name: `?StoreEAsFromBuffer@UfsEaPayload@UnionFs@@AEAAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAVStackEventTracer@2@_N@Z`
- size: `1322`
- prototype: `__int64 __fastcall(__int64, __int64, int, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140021878`
- `0x140021cb4`

## callees

- `0x14000f81c`
- `0x14000fc90`
- `0x1400214ac`
- `0x140022334`
- `0x1400228f0`
- `0x140022e80`
- `0x140056c44`
- `0x140056c7c`
- `0x140079c90`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!RtlCompareString` at `0x140022a5c`
- `ntoskrnl!RtlCompareString` at `0x140022a97`
- `ntoskrnl!RtlCompareString` at `0x140022a5c`
- `ntoskrnl!RtlCompareString` at `0x140022a97`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022b59`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022ad9`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022b59`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022deb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400229b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022deb`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsEaPayload::StoreEAsFromBuffer(__int64 a1, __int64 a2, int a3, char a4)
{
  __int64 v4; // rsi
  char v5; // r14
  const struct std::nothrow_t *v7; // rdx
  unsigned __int64 v8; // rcx
  int EAsFromFullEaInfoBuffer; // edi
  PVOID v10; // rbx
  _BYTE *v12; // r15
  char *v13; // rdi
  char *v14; // rbx
  unsigned __int64 v15; // r14
  __int64 v16; // rsi
  _QWORD *v17; // r13
  __int64 v18; // rax
  volatile signed __int32 *v19; // rsi
  _OWORD *v20; // r14
  __int128 *v21; // rax
  __int128 v22; // xmm6
  char *v23; // rax
  const struct std::nothrow_t *v24; // rdx
  char *v25; // r12
  __int128 *v26; // rax
  __int128 v27; // xmm6
  char *v28; // rax
  __int128 v29; // xmm0
  __int64 v30; // rax
  char *v31; // rax
  __int64 v32; // rcx
  unsigned __int64 i; // rax
  int v34; // edx
  __int64 *v35; // rdx
  __int64 v36; // r8
  unsigned __int64 v37; // rax
  const char *v38; // [rsp+28h] [rbp-58h]
  __int64 v39; // [rsp+30h] [rbp-50h] BYREF
  _BYTE *v40; // [rsp+38h] [rbp-48h]
  __int128 v41; // [rsp+40h] [rbp-40h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v43; // [rsp+60h] [rbp-20h]

  v4 = a1;
  v5 = a4;
  v43 = -1;
  *(__m128i *)P = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  EAsFromFullEaInfoBuffer = UnionFs::GetEAsFromFullEaInfoBuffer(a2, P);
  if ( EAsFromFullEaInfoBuffer < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)EAsFromFullEaInfoBuffer,
      a3,
      (struct UnionFs::StackEventTracer *)0x55000070098LL,
      (unsigned __int64)"UnionFs::UfsEaPayload::StoreEAsFromBuffer",
      "PUSH: Getting EAs from buffer",
      v38);
    v10 = P[0];
    if ( P[0] != (PVOID)-1LL )
    {
      utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(
        (char *)P[1] - (char *)P[0],
        P[0],
        ((char *)P[1] - (char *)P[0]) / 40);
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
    }
    return (unsigned int)EAsFromFullEaInfoBuffer;
  }
  v12 = P[0];
  v13 = (char *)P[1];
  DWORD1(v41) = 0;
  v14 = (char *)P[0];
  v40 = P[0];
  while ( v14 != v13 )
  {
    if ( v5 )
    {
      v7 = 0;
      do
      {
        if ( *(_BYTE *)((unsigned __int16)v7 + *((_QWORD *)v14 + 1)) != aKernel[(unsigned __int16)v7] )
          break;
        v8 = 7;
        if ( (unsigned __int16)v7 == 7 )
          goto LABEL_49;
        LOWORD(v7) = (_WORD)v7 + 1;
      }
      while ( (unsigned __int16)v7 < 8u );
    }
    v15 = v4 + 32;
    if ( *(_QWORD *)(v4 + 48) != v4 + 32 )
    {
      v16 = *(_QWORD *)v15;
      v17 = (_QWORD *)v15;
      do
      {
        if ( RtlCompareString((const STRING *)(v16 + 24), (const STRING *)v14, 1u) < 0 )
        {
          v18 = 16;
        }
        else
        {
          v17 = (_QWORD *)v16;
          v18 = 8;
        }
        v16 = *(_QWORD *)(v18 + v16);
      }
      while ( (void **)v16 != &utl::_TreeSentinel );
      v12 = v40;
      if ( v17 != (_QWORD *)v15 && RtlCompareString((const STRING *)v14, (const STRING *)(v17 + 3), 1u) >= 0 )
      {
        v19 = (volatile signed __int32 *)v17[6];
        v8 = v17[5];
        if ( v19 )
          _InterlockedIncrement(v19 + 2);
        v20 = (_OWORD *)(v8 + 8);
        *(_BYTE *)v8 = v14[16];
        v21 = (__int128 *)(v14 + 24);
        if ( (char *)(v8 + 8) != v14 + 24 )
        {
          v22 = *v21;
          *v21 = 0;
          ((void (__fastcall *)(unsigned __int64))RtlFreeAnsiString)(v8 + 8);
          *v20 = v22;
        }
        if ( !v19 )
          goto LABEL_48;
LABEL_47:
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v19);
        goto LABEL_48;
      }
    }
    v23 = (char *)operator new(0x28u, v7);
    v19 = (volatile signed __int32 *)v23;
    if ( v23 )
    {
      *((_DWORD *)v23 + 2) = 1;
      *((_DWORD *)v23 + 3) = 1;
      *(_QWORD *)v23 = &utl::_RefCountVtable<utl::_RefCountStored<UnionFs::_UFS_EA_DATA,utl::allocator<int>,0>,0>::`vftable';
      v25 = v23 + 16;
      *((_QWORD *)v23 + 2) = 0;
      *(_OWORD *)(v23 + 24) = 0;
    }
    else
    {
      v19 = 0;
      v25 = 0;
    }
    *v25 = v14[16];
    v26 = (__int128 *)(v14 + 24);
    if ( v25 + 8 != v14 + 24 )
    {
      v27 = *v26;
      *v26 = 0;
      RtlFreeAnsiString((PANSI_STRING)(v25 + 8));
      *(_OWORD *)(v25 + 8) = v27;
    }
    if ( *(_QWORD *)(v15 + 16) == v15 )
    {
      v28 = (char *)operator new(0x38u, v24);
      v8 = (unsigned __int64)v28;
      if ( !v28 )
        goto LABEL_50;
      *(_OWORD *)(v28 + 24) = *(_OWORD *)v14;
      *(_OWORD *)v14 = 0;
      *((_QWORD *)v28 + 5) = v25;
      *((_QWORD *)v28 + 6) = v19;
      if ( v19 )
        _InterlockedIncrement(v19 + 2);
      *(_QWORD *)v28 = v15 | 1;
      *((_QWORD *)v28 + 1) = &utl::_TreeSentinel;
      *((_QWORD *)v28 + 2) = &utl::_TreeSentinel;
      *(_QWORD *)v15 = v28;
      *(_QWORD *)(v15 + 8) = v28;
      *(_QWORD *)(v15 + 16) = v28;
      ++*(_QWORD *)(v15 + 24);
    }
    else
    {
      v39 = 0;
      v29 = *(_OWORD *)utl::_Tree<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::pair<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>,UnionFs::Utils::AnsiStringComparator,utl::allocator<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>>,0>::_FindInsertionPointUniqueUpper(
                         v15,
                         P,
                         &v39,
                         v14);
      v30 = v39;
      v41 = v29;
      if ( v39 )
      {
        if ( v19 )
          _InterlockedIncrement(v19 + 2);
        v8 = *(_QWORD *)(v30 + 48);
        *(_QWORD *)(v30 + 40) = v25;
        *(_QWORD *)(v30 + 48) = v19;
        if ( v8 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v8);
      }
      else
      {
        v31 = (char *)operator new(0x38u, v7);
        if ( !v31 )
        {
LABEL_50:
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            a3,
            (struct UnionFs::StackEventTracer *)0x54F000700C2LL,
            (unsigned __int64)"UnionFs::UfsEaPayload::StoreEAsFromBuffer",
            "ORIGIN: Adding to m_EaInfoMap",
            v38);
          if ( v19 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v19);
          if ( v12 != (_BYTE *)-1LL )
          {
            utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(v32, v12, (v13 - v12) / 40);
            if ( v12 )
              ExFreePoolWithTag(v12, 0);
          }
          return 3221225626LL;
        }
        *(_OWORD *)(v31 + 24) = *(_OWORD *)v14;
        *(_OWORD *)v14 = 0;
        *((_QWORD *)v31 + 5) = v25;
        *((_QWORD *)v31 + 6) = v19;
        if ( v19 )
          _InterlockedIncrement(v19 + 2);
        utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::_InsertAt(
          v15,
          &v41,
          v31);
      }
    }
    if ( v19 )
      goto LABEL_47;
LABEL_48:
    v5 = a4;
    v4 = a1;
LABEL_49:
    v14 += 40;
  }
  *(_DWORD *)(v4 + 64) = 0;
  for ( i = *(_QWORD *)(v4 + 48); i != v4 + 32; i = v8 )
  {
    v34 = *(unsigned __int16 *)(*(_QWORD *)(i + 40) + 8LL);
    if ( (_WORD)v34 )
      *(_DWORD *)(v4 + 64) += (v34 + *(unsigned __int16 *)(i + 24) + 12) & 0xFFFFFFFC;
    v8 = *(_QWORD *)(i + 16);
    if ( (void **)v8 == &utl::_TreeSentinel )
    {
      v35 = (__int64 *)(*(_QWORD *)i & 0xFFFFFFFFFFFFFFFEuLL);
      v8 = (unsigned __int64)v35;
      if ( v35[2] == i )
      {
        v36 = *v35;
        if ( *v35 != i )
        {
          v8 = v36 & 0xFFFFFFFFFFFFFFFEuLL;
          if ( *(__int64 **)((v36 & 0xFFFFFFFFFFFFFFFEuLL) + 16) == v35 && *(__int64 **)v8 != v35 )
          {
            do
            {
              v37 = v8;
              v8 = *(_QWORD *)v8 & 0xFFFFFFFFFFFFFFFEuLL;
            }
            while ( *(_QWORD *)(v8 + 16) == v37 );
          }
        }
      }
    }
    else
    {
      if ( i == v8 )
        __int2c();
      while ( *(void ***)(v8 + 8) != &utl::_TreeSentinel )
        v8 = *(_QWORD *)(v8 + 8);
    }
  }
  if ( v12 != (_BYTE *)-1LL )
  {
    utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(v8, v12, (v13 - v12) / 40);
    if ( v12 )
      ExFreePoolWithTag(v12, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1400228f0  mov     rax, rsp
0x1400228f3  mov     [rax+10h], rbx
0x1400228f7  mov     [rax+20h], r9b
0x1400228fb  mov     [rax+18h], r8
0x1400228ff  mov     [rax+8], rcx
0x140022903  push    rbp
0x140022904  push    rsi
0x140022905  push    rdi
0x140022906  push    r12
0x140022908  push    r13
0x14002290a  push    r14
0x14002290c  push    r15
0x14002290e  mov     rbp, rsp
0x140022911  sub     rsp, 80h
0x140022918  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140022920  mov     rsi, rcx
0x140022923  movaps  xmmword ptr [rax-48h], xmm6
0x140022927  mov     r14b, r9b
0x14002292a  mov     rax, rdx
0x14002292d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x140022935  mov     rcx, rax
0x140022938  lea     rdx, [rbp+P]
0x14002293c  mov     rbx, r8
0x14002293f  movdqu  xmmword ptr [rbp+P], xmm0
0x140022944  call    ?GetEAsFromFullEaInfoBuffer@UnionFs@@YAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$vector@U_UFS_EA@UnionFs@@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@1@@Z; UnionFs::GetEAsFromFullEaInfoBuffer(gsl::span<gsl::byte,-1> &,utl::vector<UnionFs::_UFS_EA,utl::allocator<UnionFs::_UFS_EA>> &,UnionFs::StackEventTracer &)
0x140022949  xor     r13d, r13d
0x14002294c  mov     edi, eax
0x14002294e  test    eax, eax
0x140022950  jns     short loc_1400229CA
0x140022952  lea     rax, aPushGettingEas; "PUSH: Getting EAs from buffer"
0x140022959  mov     r8, 55000070098h; struct UnionFs::StackEventTracer *
0x140022963  lea     r9, aUnionfsUfseapa; "UnionFs::UfsEaPayload::StoreEAsFromBuff"...
0x14002296a  mov     [rsp+80h+var_60], rax; char *
0x14002296f  mov     rdx, rbx; int
0x140022972  mov     ecx, edi; this
0x140022974  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140022979  mov     rbx, [rbp+P]
0x14002297d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140022981  jz      short loc_1400229C3
0x140022983  mov     rcx, [rbp+P+8]
0x140022987  mov     rax, 6666666666666667h
0x140022991  sub     rcx, rbx
0x140022994  imul    rcx
0x140022997  sar     rdx, 4
0x14002299b  mov     r8, rdx
0x14002299e  shr     r8, 3Fh
0x1400229a2  add     r8, rdx
0x1400229a5  mov     rdx, rbx
0x1400229a8  call    ??$_RangeDestroyApc@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@YAXAEAV?$allocator@U_UFS_EA@UnionFs@@@0@PEAU_UFS_EA@UnionFs@@_K@Z; utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(utl::allocator<UnionFs::_UFS_EA> &,UnionFs::_UFS_EA *,unsigned __int64)
0x1400229ad  test    rbx, rbx
0x1400229b0  jz      short loc_1400229C3
0x1400229b2  xor     edx, edx; Tag
0x1400229b4  mov     rcx, rbx; P
0x1400229b7  call    cs:__imp_ExFreePoolWithTag
0x1400229be  nop     dword ptr [rax+rax+00h]
0x1400229c3  mov     eax, edi
0x1400229c5  jmp     loc_140022DF9
0x1400229ca  mov     r15, [rbp+P]
0x1400229ce  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1400229d5  mov     rdi, [rbp+P+8]
0x1400229d9  xor     eax, eax
0x1400229db  mov     [rbp+var_3C], eax
0x1400229de  mov     rbx, r15
0x1400229e1  mov     [rbp+var_48], r15
0x1400229e5  lea     r9d, [rax+8]
0x1400229e9  lea     r12d, [rax+1]
0x1400229ed  cmp     rbx, rdi
0x1400229f0  jz      loc_140022D1F
0x1400229f6  test    r14b, r14b
0x1400229f9  jz      short loc_140022A37
0x1400229fb  cmp     r13w, r9w
0x1400229ff  jnb     short loc_140022A37
0x140022a01  mov     r8, [rbx+8]
0x140022a05  mov     edx, r13d
0x140022a08  movzx   ecx, dx
0x140022a0b  lea     rax, aKernel; "$KERNEL."
0x140022a12  mov     al, [rcx+rax]
0x140022a15  cmp     [rcx+r8], al
0x140022a19  jnz     short loc_140022A37
0x140022a1b  movzx   ecx, r9w
0x140022a1f  sub     ecx, r12d
0x140022a22  movzx   eax, dx
0x140022a25  cmp     eax, ecx
0x140022a27  jz      loc_140022C93
0x140022a2d  add     dx, r12w
0x140022a31  cmp     dx, r9w
0x140022a35  jb      short loc_140022A08
0x140022a37  lea     r14, [rsi+20h]
0x140022a3b  cmp     [r14+10h], r14
0x140022a3f  jz      loc_140022AFB
0x140022a45  mov     rsi, [r14]
0x140022a48  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022a4f  mov     r13, r14
0x140022a52  lea     rcx, [rsi+18h]; String1
0x140022a56  mov     r8b, r12b; CaseInSensitive
0x140022a59  mov     rdx, rbx; String2
0x140022a5c  call    cs:__imp_RtlCompareString
0x140022a63  nop     dword ptr [rax+rax+00h]
0x140022a68  test    eax, eax
0x140022a6a  js      short loc_140022A76
0x140022a6c  mov     r13, rsi
0x140022a6f  mov     eax, 8
0x140022a74  jmp     short loc_140022A7B
0x140022a76  mov     eax, 10h
0x140022a7b  mov     rsi, [rax+rsi]
0x140022a7f  cmp     rsi, r15
0x140022a82  jnz     short loc_140022A52
0x140022a84  mov     r15, [rbp+var_48]
0x140022a88  cmp     r13, r14
0x140022a8b  jz      short loc_140022AF8
0x140022a8d  lea     rdx, [r13+18h]; String2
0x140022a91  mov     r8b, r12b; CaseInSensitive
0x140022a94  mov     rcx, rbx; String1
0x140022a97  call    cs:__imp_RtlCompareString
0x140022a9e  nop     dword ptr [rax+rax+00h]
0x140022aa3  test    eax, eax
0x140022aa5  js      short loc_140022AF8
0x140022aa7  mov     rsi, [r13+30h]
0x140022aab  mov     rcx, [r13+28h]
0x140022aaf  xor     r13d, r13d
0x140022ab2  test    rsi, rsi
0x140022ab5  jz      short loc_140022ABB
0x140022ab7  lock inc dword ptr [rsi+8]
0x140022abb  mov     al, [rbx+10h]
0x140022abe  lea     r14, [rcx+8]
0x140022ac2  mov     [rcx], al
0x140022ac4  lea     rax, [rbx+18h]
0x140022ac8  cmp     r14, rax
0x140022acb  jz      short loc_140022AEA
0x140022acd  movups  xmm6, xmmword ptr [rax]
0x140022ad0  mov     rcx, r14
0x140022ad3  xorps   xmm0, xmm0
0x140022ad6  movups  xmmword ptr [rax], xmm0
0x140022ad9  mov     rax, cs:__imp_RtlFreeAnsiString
0x140022ae0  call    _guard_dispatch_icall
0x140022ae5  movdqu  xmmword ptr [r14], xmm6
0x140022aea  test    rsi, rsi
0x140022aed  jz      loc_140022C7E
0x140022af3  jmp     loc_140022C76
0x140022af8  xor     r13d, r13d
0x140022afb  mov     ecx, 28h ; '('; unsigned __int64
0x140022b00  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022b05  mov     rsi, rax
0x140022b08  test    rax, rax
0x140022b0b  jz      short loc_140022B32
0x140022b0d  mov     [rax+8], r12d
0x140022b11  xorps   xmm0, xmm0
0x140022b14  mov     [rax+0Ch], r12d
0x140022b18  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@U_UFS_EA_DATA@UnionFs@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<UnionFs::_UFS_EA_DATA,utl::allocator<int>,0>,0>::`vftable'
0x140022b1f  mov     [rsi], rax
0x140022b22  lea     r12, [rsi+10h]
0x140022b26  mov     [rsi+10h], r13
0x140022b2a  movups  xmmword ptr [r12+8], xmm0
0x140022b30  jmp     short loc_140022B38
0x140022b32  mov     rsi, r13
0x140022b35  mov     r12, r13
0x140022b38  mov     al, [rbx+10h]
0x140022b3b  lea     r13, [r12+8]
0x140022b40  mov     [r12], al
0x140022b44  lea     rax, [rbx+18h]
0x140022b48  cmp     r13, rax
0x140022b4b  jz      short loc_140022B6B
0x140022b4d  movups  xmm6, xmmword ptr [rax]
0x140022b50  mov     rcx, r13; AnsiString
0x140022b53  xorps   xmm0, xmm0
0x140022b56  movups  xmmword ptr [rax], xmm0
0x140022b59  call    cs:__imp_RtlFreeAnsiString
0x140022b60  nop     dword ptr [rax+rax+00h]
0x140022b65  movdqu  xmmword ptr [r13+0], xmm6
0x140022b6b  cmp     [r14+10h], r14
0x140022b6f  jnz     short loc_140022BDB
0x140022b71  mov     ecx, 38h ; '8'; unsigned __int64
0x140022b76  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022b7b  xor     r13d, r13d
0x140022b7e  mov     rcx, rax
0x140022b81  test    rax, rax
0x140022b84  jz      loc_140022C9C
0x140022b8a  xorps   xmm1, xmm1
0x140022b8d  movups  xmm0, xmmword ptr [rbx]
0x140022b90  movdqu  xmmword ptr [rax+18h], xmm0
0x140022b95  movups  xmmword ptr [rbx], xmm1
0x140022b98  mov     [rax+28h], r12
0x140022b9c  mov     [rax+30h], rsi
0x140022ba0  test    rsi, rsi
0x140022ba3  jz      short loc_140022BA9
0x140022ba5  lock inc dword ptr [rsi+8]
0x140022ba9  mov     r12d, 1
0x140022baf  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022bb6  mov     rax, r14
0x140022bb9  or      rax, r12
0x140022bbc  mov     [rcx], rax
0x140022bbf  mov     [rcx+8], r10
0x140022bc3  mov     [rcx+10h], r10
0x140022bc7  mov     [r14], rcx
0x140022bca  mov     [r14+8], rcx
0x140022bce  mov     [r14+10h], rcx
0x140022bd2  add     [r14+18h], r12
0x140022bd6  jmp     loc_140022C71
0x140022bdb  xor     r13d, r13d
0x140022bde  lea     r8, [rbp+var_50]
0x140022be2  mov     r9, rbx
0x140022be5  mov     [rbp+var_50], r13
0x140022be9  lea     rdx, [rbp+P]
0x140022bed  mov     rcx, r14
0x140022bf0  call    ?_FindInsertionPointUniqueUpper@?$_Tree@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@UAnsiStringComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@4@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@2@AEBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@Z; utl::_Tree<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>,UnionFs::Utils::AnsiStringComparator,utl::allocator<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>> * &,wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const &)
0x140022bf5  movups  xmm0, xmmword ptr [rax]
0x140022bf8  mov     rax, [rbp+var_50]
0x140022bfc  movdqu  xmmword ptr [rbp-40h], xmm0
0x140022c01  test    rax, rax
0x140022c04  jz      short loc_140022C27
0x140022c06  test    rsi, rsi
0x140022c09  jz      short loc_140022C0F
0x140022c0b  lock inc dword ptr [rsi+8]
0x140022c0f  mov     rcx, [rax+30h]; this
0x140022c13  mov     [rax+28h], r12
0x140022c17  mov     [rax+30h], rsi
0x140022c1b  test    rcx, rcx
0x140022c1e  jz      short loc_140022C64
0x140022c20  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022c25  jmp     short loc_140022C64
0x140022c27  mov     ecx, 38h ; '8'; unsigned __int64
0x140022c2c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022c31  test    rax, rax
0x140022c34  jz      short loc_140022C9C
0x140022c36  xorps   xmm1, xmm1
0x140022c39  movups  xmm0, xmmword ptr [rbx]
0x140022c3c  movdqu  xmmword ptr [rax+18h], xmm0
0x140022c41  movups  xmmword ptr [rbx], xmm1
0x140022c44  mov     [rax+28h], r12
0x140022c48  mov     [rax+30h], rsi
0x140022c4c  test    rsi, rsi
0x140022c4f  jz      short loc_140022C55
0x140022c51  lock inc dword ptr [rsi+8]
0x140022c55  mov     r8, rax
0x140022c58  lea     rdx, [rbp+var_40]
0x140022c5c  mov     rcx, r14
0x140022c5f  call    ?_InsertAt@?$_Tree@VUfsFileID@UnionFs@@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@U?$less@VUfsFileID@UnionFs@@@4@V?$allocator@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@4@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@2@@Z; utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>> *,bool> const &,utl::_TreeNode<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>> *)
0x140022c64  mov     r12d, 1
0x140022c6a  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022c71  test    rsi, rsi
0x140022c74  jz      short loc_140022C85
0x140022c76  mov     rcx, rsi; this
0x140022c79  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022c7e  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022c85  mov     r14b, [rbp+arg_18]
0x140022c89  mov     r9d, 8
0x140022c8f  mov     rsi, [rbp+arg_0]
0x140022c93  add     rbx, 28h ; '('
0x140022c97  jmp     loc_1400229ED
0x140022c9c  mov     rdx, qword ptr [rbp+arg_10]; int
0x140022ca0  lea     rax, aOriginAddingTo_3; "ORIGIN: Adding to m_EaInfoMap"
0x140022ca7  mov     ebx, 0C000009Ah
0x140022cac  mov     [rsp+80h+var_60], rax; char *
0x140022cb1  mov     ecx, ebx; this
0x140022cb3  lea     r9, aUnionfsUfseapa; "UnionFs::UfsEaPayload::StoreEAsFromBuff"...
0x140022cba  mov     r8, 54F000700C2h; struct UnionFs::StackEventTracer *
0x140022cc4  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140022cc9  test    rsi, rsi
0x140022ccc  jz      short loc_140022CD6
0x140022cce  mov     rcx, rsi; this
0x140022cd1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022cd6  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140022cda  jz      short loc_140022D18
0x140022cdc  sub     rdi, r15
0x140022cdf  mov     rax, 6666666666666667h
0x140022ce9  imul    rdi
0x140022cec  sar     rdx, 4
0x140022cf0  mov     r8, rdx
0x140022cf3  shr     r8, 3Fh
0x140022cf7  add     r8, rdx
0x140022cfa  mov     rdx, r15
0x140022cfd  call    ??$_RangeDestroyApc@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@YAXAEAV?$allocator@U_UFS_EA@UnionFs@@@0@PEAU_UFS_EA@UnionFs@@_K@Z; utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(utl::allocator<UnionFs::_UFS_EA> &,UnionFs::_UFS_EA *,unsigned __int64)
0x140022d02  test    r15, r15
0x140022d05  jz      short loc_140022D18
0x140022d07  xor     edx, edx; Tag
0x140022d09  mov     rcx, r15; P
0x140022d0c  call    cs:__imp_ExFreePoolWithTag
0x140022d13  nop     dword ptr [rax+rax+00h]
0x140022d18  mov     eax, ebx
0x140022d1a  jmp     loc_140022DF9
0x140022d1f  lea     r9, [rsi+20h]
0x140022d23  mov     [rsi+40h], r13d
0x140022d27  mov     rax, [r9+10h]
0x140022d2b  cmp     rax, r9
0x140022d2e  jz      loc_140022DB5
0x140022d34  mov     rcx, [rax+28h]
0x140022d38  movzx   edx, word ptr [rcx+8]
0x140022d3c  test    dx, dx
0x140022d3f  jz      short loc_140022D55
0x140022d41  movzx   r8d, word ptr [rax+18h]
0x140022d46  add     r8d, 0Ch
0x140022d4a  add     r8d, edx
0x140022d4d  and     r8d, 0FFFFFFFCh
0x140022d51  add     [rsi+40h], r8d
0x140022d55  mov     rcx, [rax+10h]
0x140022d59  cmp     rcx, r10
0x140022d5c  jz      short loc_140022D73
0x140022d5e  cmp     rax, rcx
0x140022d61  jnz     short loc_140022D6B
0x140022d63  int     2Ch; Windows NT - assertion failure
  ... truncated ...
```

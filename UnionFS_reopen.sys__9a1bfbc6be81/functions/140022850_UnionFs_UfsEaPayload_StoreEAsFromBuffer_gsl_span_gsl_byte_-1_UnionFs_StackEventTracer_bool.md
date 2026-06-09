# UnionFs::UfsEaPayload::StoreEAsFromBuffer(gsl::span<gsl::byte,-1> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140022850`
- end: `0x140022d7a`
- name: `?StoreEAsFromBuffer@UfsEaPayload@UnionFs@@AEAAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAVStackEventTracer@2@_N@Z`
- size: `1322`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400217d8`
- `0x140021c14`

## callees

- `0x14000f7fc`
- `0x14000fc70`
- `0x14002140c`
- `0x140022294`
- `0x140022850`
- `0x140022de0`
- `0x140056ac4`
- `0x140056afc`
- `0x140079970`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!RtlCompareString` at `0x1400229bc`
- `ntoskrnl!RtlCompareString` at `0x1400229f7`
- `ntoskrnl!RtlCompareString` at `0x1400229bc`
- `ntoskrnl!RtlCompareString` at `0x1400229f7`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022ab9`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022a39`
- `ntoskrnl!RtlFreeAnsiString` at `0x140022ab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022917`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022917`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022d4b`

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
  __int64 *v15; // r14
  __int64 v16; // rsi
  __int64 *v17; // r13
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
    v15 = (__int64 *)(v4 + 32);
    if ( *(_QWORD *)(v4 + 48) != v4 + 32 )
    {
      v16 = *v15;
      v17 = v15;
      do
      {
        if ( RtlCompareString((const STRING *)(v16 + 24), (const STRING *)v14, 1u) < 0 )
        {
          v18 = 16;
        }
        else
        {
          v17 = (__int64 *)v16;
          v18 = 8;
        }
        v16 = *(_QWORD *)(v18 + v16);
      }
      while ( (void **)v16 != &utl::_TreeSentinel );
      v12 = v40;
      if ( v17 != v15 && RtlCompareString((const STRING *)v14, (const STRING *)(v17 + 3), 1u) >= 0 )
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
    if ( (__int64 *)v15[2] == v15 )
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
      *(_QWORD *)v28 = (unsigned __int64)v15 | 1;
      *((_QWORD *)v28 + 1) = &utl::_TreeSentinel;
      *((_QWORD *)v28 + 2) = &utl::_TreeSentinel;
      *v15 = (__int64)v28;
      v15[1] = (__int64)v28;
      v15[2] = (__int64)v28;
      ++v15[3];
    }
    else
    {
      v39 = 0;
      v29 = *(_OWORD *)utl::_Tree<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::pair<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>,UnionFs::Utils::AnsiStringComparator,utl::allocator<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>>,0>::_FindInsertionPointUniqueUpper(
                         v15,
                         (__int64)P,
                         (__int64)&v39,
                         (const STRING *)v14);
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
0x140022850  mov     rax, rsp
0x140022853  mov     [rax+10h], rbx
0x140022857  mov     [rax+20h], r9b
0x14002285b  mov     [rax+18h], r8
0x14002285f  mov     [rax+8], rcx
0x140022863  push    rbp
0x140022864  push    rsi
0x140022865  push    rdi
0x140022866  push    r12
0x140022868  push    r13
0x14002286a  push    r14
0x14002286c  push    r15
0x14002286e  mov     rbp, rsp
0x140022871  sub     rsp, 80h
0x140022878  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140022880  mov     rsi, rcx
0x140022883  movaps  xmmword ptr [rax-48h], xmm6
0x140022887  mov     r14b, r9b
0x14002288a  mov     rax, rdx
0x14002288d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x140022895  mov     rcx, rax
0x140022898  lea     rdx, [rbp+P]
0x14002289c  mov     rbx, r8
0x14002289f  movdqu  xmmword ptr [rbp+P], xmm0
0x1400228a4  call    ?GetEAsFromFullEaInfoBuffer@UnionFs@@YAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$vector@U_UFS_EA@UnionFs@@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@1@@Z; UnionFs::GetEAsFromFullEaInfoBuffer(gsl::span<gsl::byte,-1> &,utl::vector<UnionFs::_UFS_EA,utl::allocator<UnionFs::_UFS_EA>> &,UnionFs::StackEventTracer &)
0x1400228a9  xor     r13d, r13d
0x1400228ac  mov     edi, eax
0x1400228ae  test    eax, eax
0x1400228b0  jns     short loc_14002292A
0x1400228b2  lea     rax, aPushGettingEas; "PUSH: Getting EAs from buffer"
0x1400228b9  mov     r8, 55000070098h; struct UnionFs::StackEventTracer *
0x1400228c3  lea     r9, aUnionfsUfseapa; "UnionFs::UfsEaPayload::StoreEAsFromBuff"...
0x1400228ca  mov     [rsp+80h+var_60], rax; char *
0x1400228cf  mov     rdx, rbx; int
0x1400228d2  mov     ecx, edi; this
0x1400228d4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400228d9  mov     rbx, [rbp+P]
0x1400228dd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400228e1  jz      short loc_140022923
0x1400228e3  mov     rcx, [rbp+P+8]
0x1400228e7  mov     rax, 6666666666666667h
0x1400228f1  sub     rcx, rbx
0x1400228f4  imul    rcx
0x1400228f7  sar     rdx, 4
0x1400228fb  mov     r8, rdx
0x1400228fe  shr     r8, 3Fh
0x140022902  add     r8, rdx
0x140022905  mov     rdx, rbx
0x140022908  call    ??$_RangeDestroyApc@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@YAXAEAV?$allocator@U_UFS_EA@UnionFs@@@0@PEAU_UFS_EA@UnionFs@@_K@Z; utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(utl::allocator<UnionFs::_UFS_EA> &,UnionFs::_UFS_EA *,unsigned __int64)
0x14002290d  test    rbx, rbx
0x140022910  jz      short loc_140022923
0x140022912  xor     edx, edx; Tag
0x140022914  mov     rcx, rbx; P
0x140022917  call    cs:__imp_ExFreePoolWithTag
0x14002291e  nop     dword ptr [rax+rax+00h]
0x140022923  mov     eax, edi
0x140022925  jmp     loc_140022D59
0x14002292a  mov     r15, [rbp+P]
0x14002292e  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022935  mov     rdi, [rbp+P+8]
0x140022939  xor     eax, eax
0x14002293b  mov     [rbp+var_3C], eax
0x14002293e  mov     rbx, r15
0x140022941  mov     [rbp+var_48], r15
0x140022945  lea     r9d, [rax+8]
0x140022949  lea     r12d, [rax+1]
0x14002294d  cmp     rbx, rdi
0x140022950  jz      loc_140022C7F
0x140022956  test    r14b, r14b
0x140022959  jz      short loc_140022997
0x14002295b  cmp     r13w, r9w
0x14002295f  jnb     short loc_140022997
0x140022961  mov     r8, [rbx+8]
0x140022965  mov     edx, r13d
0x140022968  movzx   ecx, dx
0x14002296b  lea     rax, aKernel; "$KERNEL."
0x140022972  mov     al, [rcx+rax]
0x140022975  cmp     [rcx+r8], al
0x140022979  jnz     short loc_140022997
0x14002297b  movzx   ecx, r9w
0x14002297f  sub     ecx, r12d
0x140022982  movzx   eax, dx
0x140022985  cmp     eax, ecx
0x140022987  jz      loc_140022BF3
0x14002298d  add     dx, r12w
0x140022991  cmp     dx, r9w
0x140022995  jb      short loc_140022968
0x140022997  lea     r14, [rsi+20h]
0x14002299b  cmp     [r14+10h], r14
0x14002299f  jz      loc_140022A5B
0x1400229a5  mov     rsi, [r14]
0x1400229a8  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1400229af  mov     r13, r14
0x1400229b2  lea     rcx, [rsi+18h]; String1
0x1400229b6  mov     r8b, r12b; CaseInSensitive
0x1400229b9  mov     rdx, rbx; String2
0x1400229bc  call    cs:__imp_RtlCompareString
0x1400229c3  nop     dword ptr [rax+rax+00h]
0x1400229c8  test    eax, eax
0x1400229ca  js      short loc_1400229D6
0x1400229cc  mov     r13, rsi
0x1400229cf  mov     eax, 8
0x1400229d4  jmp     short loc_1400229DB
0x1400229d6  mov     eax, 10h
0x1400229db  mov     rsi, [rax+rsi]
0x1400229df  cmp     rsi, r15
0x1400229e2  jnz     short loc_1400229B2
0x1400229e4  mov     r15, [rbp+var_48]
0x1400229e8  cmp     r13, r14
0x1400229eb  jz      short loc_140022A58
0x1400229ed  lea     rdx, [r13+18h]; String2
0x1400229f1  mov     r8b, r12b; CaseInSensitive
0x1400229f4  mov     rcx, rbx; String1
0x1400229f7  call    cs:__imp_RtlCompareString
0x1400229fe  nop     dword ptr [rax+rax+00h]
0x140022a03  test    eax, eax
0x140022a05  js      short loc_140022A58
0x140022a07  mov     rsi, [r13+30h]
0x140022a0b  mov     rcx, [r13+28h]
0x140022a0f  xor     r13d, r13d
0x140022a12  test    rsi, rsi
0x140022a15  jz      short loc_140022A1B
0x140022a17  lock inc dword ptr [rsi+8]
0x140022a1b  mov     al, [rbx+10h]
0x140022a1e  lea     r14, [rcx+8]
0x140022a22  mov     [rcx], al
0x140022a24  lea     rax, [rbx+18h]
0x140022a28  cmp     r14, rax
0x140022a2b  jz      short loc_140022A4A
0x140022a2d  movups  xmm6, xmmword ptr [rax]
0x140022a30  mov     rcx, r14
0x140022a33  xorps   xmm0, xmm0
0x140022a36  movups  xmmword ptr [rax], xmm0
0x140022a39  mov     rax, cs:__imp_RtlFreeAnsiString
0x140022a40  call    _guard_dispatch_icall
0x140022a45  movdqu  xmmword ptr [r14], xmm6
0x140022a4a  test    rsi, rsi
0x140022a4d  jz      loc_140022BDE
0x140022a53  jmp     loc_140022BD6
0x140022a58  xor     r13d, r13d
0x140022a5b  mov     ecx, 28h ; '('; unsigned __int64
0x140022a60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022a65  mov     rsi, rax
0x140022a68  test    rax, rax
0x140022a6b  jz      short loc_140022A92
0x140022a6d  mov     [rax+8], r12d
0x140022a71  xorps   xmm0, xmm0
0x140022a74  mov     [rax+0Ch], r12d
0x140022a78  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@U_UFS_EA_DATA@UnionFs@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<UnionFs::_UFS_EA_DATA,utl::allocator<int>,0>,0>::`vftable'
0x140022a7f  mov     [rsi], rax
0x140022a82  lea     r12, [rsi+10h]
0x140022a86  mov     [rsi+10h], r13
0x140022a8a  movups  xmmword ptr [r12+8], xmm0
0x140022a90  jmp     short loc_140022A98
0x140022a92  mov     rsi, r13
0x140022a95  mov     r12, r13
0x140022a98  mov     al, [rbx+10h]
0x140022a9b  lea     r13, [r12+8]
0x140022aa0  mov     [r12], al
0x140022aa4  lea     rax, [rbx+18h]
0x140022aa8  cmp     r13, rax
0x140022aab  jz      short loc_140022ACB
0x140022aad  movups  xmm6, xmmword ptr [rax]
0x140022ab0  mov     rcx, r13; AnsiString
0x140022ab3  xorps   xmm0, xmm0
0x140022ab6  movups  xmmword ptr [rax], xmm0
0x140022ab9  call    cs:__imp_RtlFreeAnsiString
0x140022ac0  nop     dword ptr [rax+rax+00h]
0x140022ac5  movdqu  xmmword ptr [r13+0], xmm6
0x140022acb  cmp     [r14+10h], r14
0x140022acf  jnz     short loc_140022B3B
0x140022ad1  mov     ecx, 38h ; '8'; unsigned __int64
0x140022ad6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022adb  xor     r13d, r13d
0x140022ade  mov     rcx, rax
0x140022ae1  test    rax, rax
0x140022ae4  jz      loc_140022BFC
0x140022aea  xorps   xmm1, xmm1
0x140022aed  movups  xmm0, xmmword ptr [rbx]
0x140022af0  movdqu  xmmword ptr [rax+18h], xmm0
0x140022af5  movups  xmmword ptr [rbx], xmm1
0x140022af8  mov     [rax+28h], r12
0x140022afc  mov     [rax+30h], rsi
0x140022b00  test    rsi, rsi
0x140022b03  jz      short loc_140022B09
0x140022b05  lock inc dword ptr [rsi+8]
0x140022b09  mov     r12d, 1
0x140022b0f  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022b16  mov     rax, r14
0x140022b19  or      rax, r12
0x140022b1c  mov     [rcx], rax
0x140022b1f  mov     [rcx+8], r10
0x140022b23  mov     [rcx+10h], r10
0x140022b27  mov     [r14], rcx
0x140022b2a  mov     [r14+8], rcx
0x140022b2e  mov     [r14+10h], rcx
0x140022b32  add     [r14+18h], r12
0x140022b36  jmp     loc_140022BD1
0x140022b3b  xor     r13d, r13d
0x140022b3e  lea     r8, [rbp+var_50]
0x140022b42  mov     r9, rbx
0x140022b45  mov     [rbp+var_50], r13
0x140022b49  lea     rdx, [rbp+P]
0x140022b4d  mov     rcx, r14
0x140022b50  call    ?_FindInsertionPointUniqueUpper@?$_Tree@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@UAnsiStringComparator@Utils@UnionFs@@V?$allocator@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@4@$0A@@utl@@AEAA?AU?$pair@PEAU?$_TreeNode@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@utl@@_N@2@AEAPEAU?$_TreeNode@U?$pair@$$CBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$shared_ptr@U_UFS_EA_DATA@UnionFs@@@utl@@@utl@@@2@AEBV?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@Z; utl::_Tree<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>,UnionFs::Utils::AnsiStringComparator,utl::allocator<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>>,0>::_FindInsertionPointUniqueUpper(utl::_TreeNode<utl::pair<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const,utl::shared_ptr<UnionFs::_UFS_EA_DATA>>> * &,wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0> const &)
0x140022b55  movups  xmm0, xmmword ptr [rax]
0x140022b58  mov     rax, [rbp+var_50]
0x140022b5c  movdqu  xmmword ptr [rbp-40h], xmm0
0x140022b61  test    rax, rax
0x140022b64  jz      short loc_140022B87
0x140022b66  test    rsi, rsi
0x140022b69  jz      short loc_140022B6F
0x140022b6b  lock inc dword ptr [rsi+8]
0x140022b6f  mov     rcx, [rax+30h]; this
0x140022b73  mov     [rax+28h], r12
0x140022b77  mov     [rax+30h], rsi
0x140022b7b  test    rcx, rcx
0x140022b7e  jz      short loc_140022BC4
0x140022b80  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022b85  jmp     short loc_140022BC4
0x140022b87  mov     ecx, 38h ; '8'; unsigned __int64
0x140022b8c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022b91  test    rax, rax
0x140022b94  jz      short loc_140022BFC
0x140022b96  xorps   xmm1, xmm1
0x140022b99  movups  xmm0, xmmword ptr [rbx]
0x140022b9c  movdqu  xmmword ptr [rax+18h], xmm0
0x140022ba1  movups  xmmword ptr [rbx], xmm1
0x140022ba4  mov     [rax+28h], r12
0x140022ba8  mov     [rax+30h], rsi
0x140022bac  test    rsi, rsi
0x140022baf  jz      short loc_140022BB5
0x140022bb1  lock inc dword ptr [rsi+8]
0x140022bb5  mov     r8, rax
0x140022bb8  lea     rdx, [rbp+var_40]
0x140022bbc  mov     rcx, r14
0x140022bbf  call    ?_InsertAt@?$_Tree@VUfsFileID@UnionFs@@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@U?$less@VUfsFileID@UnionFs@@@4@V?$allocator@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@4@$0A@@utl@@AEAAXAEBU?$pair@PEAU?$_TreeNode@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@_N@2@PEAU?$_TreeNode@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@2@@Z; utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::_InsertAt(utl::pair<utl::_TreeNode<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>> *,bool> const &,utl::_TreeNode<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>> *)
0x140022bc4  mov     r12d, 1
0x140022bca  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022bd1  test    rsi, rsi
0x140022bd4  jz      short loc_140022BE5
0x140022bd6  mov     rcx, rsi; this
0x140022bd9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022bde  lea     r10, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140022be5  mov     r14b, [rbp+arg_18]
0x140022be9  mov     r9d, 8
0x140022bef  mov     rsi, [rbp+arg_0]
0x140022bf3  add     rbx, 28h ; '('
0x140022bf7  jmp     loc_14002294D
0x140022bfc  mov     rdx, qword ptr [rbp+arg_10]; int
0x140022c00  lea     rax, aOriginAddingTo_3; "ORIGIN: Adding to m_EaInfoMap"
0x140022c07  mov     ebx, 0C000009Ah
0x140022c0c  mov     [rsp+80h+var_60], rax; char *
0x140022c11  mov     ecx, ebx; this
0x140022c13  lea     r9, aUnionfsUfseapa; "UnionFs::UfsEaPayload::StoreEAsFromBuff"...
0x140022c1a  mov     r8, 54F000700C2h; struct UnionFs::StackEventTracer *
0x140022c24  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140022c29  test    rsi, rsi
0x140022c2c  jz      short loc_140022C36
0x140022c2e  mov     rcx, rsi; this
0x140022c31  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140022c36  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140022c3a  jz      short loc_140022C78
0x140022c3c  sub     rdi, r15
0x140022c3f  mov     rax, 6666666666666667h
0x140022c49  imul    rdi
0x140022c4c  sar     rdx, 4
0x140022c50  mov     r8, rdx
0x140022c53  shr     r8, 3Fh
0x140022c57  add     r8, rdx
0x140022c5a  mov     rdx, r15
0x140022c5d  call    ??$_RangeDestroyApc@V?$allocator@U_UFS_EA@UnionFs@@@utl@@@utl@@YAXAEAV?$allocator@U_UFS_EA@UnionFs@@@0@PEAU_UFS_EA@UnionFs@@_K@Z; utl::_RangeDestroyApc<utl::allocator<UnionFs::_UFS_EA>>(utl::allocator<UnionFs::_UFS_EA> &,UnionFs::_UFS_EA *,unsigned __int64)
0x140022c62  test    r15, r15
0x140022c65  jz      short loc_140022C78
0x140022c67  xor     edx, edx; Tag
0x140022c69  mov     rcx, r15; P
0x140022c6c  call    cs:__imp_ExFreePoolWithTag
0x140022c73  nop     dword ptr [rax+rax+00h]
0x140022c78  mov     eax, ebx
0x140022c7a  jmp     loc_140022D59
0x140022c7f  lea     r9, [rsi+20h]
0x140022c83  mov     [rsi+40h], r13d
0x140022c87  mov     rax, [r9+10h]
0x140022c8b  cmp     rax, r9
0x140022c8e  jz      loc_140022D15
0x140022c94  mov     rcx, [rax+28h]
0x140022c98  movzx   edx, word ptr [rcx+8]
0x140022c9c  test    dx, dx
0x140022c9f  jz      short loc_140022CB5
0x140022ca1  movzx   r8d, word ptr [rax+18h]
0x140022ca6  add     r8d, 0Ch
0x140022caa  add     r8d, edx
0x140022cad  and     r8d, 0FFFFFFFCh
0x140022cb1  add     [rsi+40h], r8d
0x140022cb5  mov     rcx, [rax+10h]
0x140022cb9  cmp     rcx, r10
0x140022cbc  jz      short loc_140022CD3
0x140022cbe  cmp     rax, rcx
0x140022cc1  jnz     short loc_140022CCB
0x140022cc3  int     2Ch; Windows NT - assertion failure
  ... truncated ...
```

# GetLogonCredsFromAuthData(ICloudAPContext *,_DECRYPTED_AUTH_DATA *,LOGON_CREDS * *)

- ea: `0x18000ed44`
- end: `0x18000f3bc`
- name: `?GetLogonCredsFromAuthData@@YAJPEAVICloudAPContext@@PEAU_DECRYPTED_AUTH_DATA@@PEAPEAULOGON_CREDS@@@Z`
- size: `1656`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **, struct LOGON_CREDS **)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting`

## callers

- `0x1800141a0`
- `0x1800144b4`

## callees

- `0x180007eb8`
- `0x180008440`
- `0x18000baac`
- `0x18000d824`
- `0x18000d91c`
- `0x18000d968`
- `0x18000da60`
- `0x18000deac`
- `0x18000df44`
- `0x18000e678`
- `0x18000ec04`
- `0x18000ed44`
- `0x18000fcf4`
- `0x180010064`
- `0x180010830`
- `0x180023d38`
- `0x1800267c0`
- `0x180027310`
- `0x180027d2c`
- `0x18002fdd0`
- `0x180032010`

## import_xrefs

- `cryptngc!NgcUnpackCredData` at `0x18000f1ff`
- `cryptngc!NgcUnpackCredData` at `0x18000f1ff`

## string_xrefs

- `0x18000edf8`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000ee8b`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000ef7a`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLogonCredsFromAuthData(
        struct ICloudAPContext *a1,
        struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **a2,
        struct LOGON_CREDS **a3)
{
  char *v5; // rsi
  rsize_t v6; // rbx
  _WORD *v7; // rdi
  __int64 v8; // r13
  unsigned int v9; // eax
  __int64 v10; // rcx
  rsize_t v11; // r8
  int v12; // eax
  bool v13; // dl
  int v14; // eax
  int v15; // r8d
  unsigned int v16; // ebx
  int DATokenParamsFromCredBag; // eax
  __int64 v19; // rax
  __int64 v20; // rbx
  void *v21; // r15
  errno_t v22; // eax
  unsigned __int64 v23; // r15
  void *v24; // r12
  errno_t v25; // eax
  ATL::CStringData *v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  int v29; // r15d
  int *v30; // rbx
  ATL::CStringData *v31; // r14
  void *v32; // r12
  errno_t v33; // eax
  unsigned __int64 v34; // rdi
  void *v35; // r15
  errno_t v36; // eax
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **v37; // r14
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *v38; // rax
  void *v39; // rbx
  errno_t v40; // eax
  unsigned __int16 **v41; // [rsp+20h] [rbp-E0h]
  unsigned __int16 **v42; // [rsp+20h] [rbp-E0h]
  void *v43; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  void **v48; // [rsp+78h] [rbp-88h] BYREF
  char *v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h]
  __int64 v51; // [rsp+90h] [rbp-70h]
  void *v52[3]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-50h] BYREF
  void *Source[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v55[3]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v56[13]; // [rsp+E8h] [rbp-18h] BYREF
  int AuthDataFromPackedCredentials; // [rsp+160h] [rbp+60h] BYREF
  struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS **v58; // [rsp+168h] [rbp+68h]
  struct LOGON_CREDS **v59; // [rsp+170h] [rbp+70h]
  rsize_t SourceSize; // [rsp+178h] [rbp+78h] BYREF

  v59 = a3;
  v58 = a2;
  AuthDataFromPackedCredentials = 0;
  v49 = 0;
  v51 = 0;
  v50 = 0;
  memset(v52, 0, sizeof(v52));
  memset(v55, 0, sizeof(v55));
  memset(Source, 0, sizeof(Source));
  LODWORD(SourceSize) = 0;
  v48 = &LiveMemoryManager::`vftable';
  Buf1 = 0;
  v45 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v44 = 0;
  v56[0] = "GetLogonCredsFromAuthData";
  v56[1] = &AuthDataFromPackedCredentials;
  v56[2] = 0;
  v56[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "GetLogonCredsFromAuthData",
    (const char *)0x32E,
    0,
    (const unsigned __int16 *)v41);
  if ( !a2 || !a3 )
    goto LABEL_20;
  *a3 = 0;
  AuthDataFromPackedCredentials = GetAuthDataFromPackedCredentials(
                                    a2[2],
                                    (unsigned __int8 **)Source,
                                    (unsigned int *)&SourceSize,
                                    &Buf1);
  if ( AuthDataFromPackedCredentials < 0 )
    goto LABEL_21;
  v5 = (char *)LiveAllocate(0xD8u);
  Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::Clear(&v49);
  v49 = v5;
  if ( !v5 )
    goto LABEL_59;
  v6 = (unsigned int)SourceSize;
  v7 = Source[0];
  if ( !Source[0] || !(_DWORD)SourceSize )
  {
    AuthDataFromPackedCredentials = -1073741718;
    LODWORD(v42) = -1073741718;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
      0x34Au,
      L"spAuthData == nullptr, Status=0x%x.",
      v42);
    if ( AuthDataFromPackedCredentials < 0 )
      goto LABEL_21;
  }
  v8 = -1;
  if ( memcmp_0(&Buf1, qword_18003AB38, 0x10u) )
  {
    if ( !memcmp_0(&Buf1, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD, 0x10u) )
    {
      if ( (v6 & 1) != 0 )
        goto LABEL_20;
      v23 = (unsigned int)(v6 + 2);
      v24 = LiveAllocate(v23);
      Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v5 + 32);
      *((_QWORD *)v5 + 4) = v24;
      if ( !v24 )
        goto LABEL_59;
      v25 = memcpy_s_0(v24, (unsigned int)v23, v7, v6);
      AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v25 != 0 ? 0x8000FFFF : 0);
      if ( AuthDataFromPackedCredentials < 0 )
        goto LABEL_21;
      *((_QWORD *)v5 + 5) = v23;
      *((_DWORD *)v5 + 6) = 1;
LABEL_52:
      v37 = v58;
      v38 = v58[1];
      if ( !v38 )
        goto LABEL_56;
      do
        ++v8;
      while ( *((_WORD *)v38 + v8) );
      v39 = LiveAllocate((unsigned int)(2 * v8) + 2LL);
      Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v5);
      *(_QWORD *)v5 = v39;
      if ( v39 )
      {
        v40 = memcpy_s_0(v39, (unsigned int)(2 * v8), v37[1], (unsigned int)(2 * v8));
        AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v40 != 0 ? 0x8000FFFF : 0);
        if ( AuthDataFromPackedCredentials < 0 )
          goto LABEL_21;
LABEL_56:
        v49 = 0;
        v50 = 0;
        *v59 = (struct LOGON_CREDS *)v5;
        goto LABEL_21;
      }
LABEL_59:
      AuthDataFromPackedCredentials = -1073741670;
      goto LABEL_21;
    }
    if ( memcmp_0(&Buf1, SEC_WINNT_AUTH_DATA_TYPE_NGC, 0x10u) )
      goto LABEL_20;
    v47 = 0;
    v53 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
    if ( (v6 & 1) != 0 )
    {
      AuthDataFromPackedCredentials = -1073741811;
LABEL_40:
      v26 = (ATL::CStringData *)((char *)v43 - 24);
LABEL_41:
      ATL::CStringData::Release(v26);
      goto LABEL_21;
    }
    v27 = NgcUnpackCredData(v7, (unsigned int)v6, v52, &v47, v55, &v53);
    AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v27);
    if ( AuthDataFromPackedCredentials < 0 )
      goto LABEL_40;
    if ( !v52[0] )
    {
      AuthDataFromPackedCredentials = -1073741670;
      goto LABEL_40;
    }
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v52[0] + v28) );
    v29 = 2 * v28;
    LODWORD(SourceSize) = 2 * v28;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v43,
      L"%I64x",
      v47);
    v30 = (int *)v43;
    v31 = (ATL::CStringData *)((char *)v43 - 24);
    *(_QWORD *)&Buf1.Data1 = (unsigned int)(2 * *((_DWORD *)v43 - 4) + 2);
    v32 = LiveAllocate(Buf1.Data1);
    Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v5 + 152);
    *((_QWORD *)v5 + 19) = v32;
    if ( v32 )
    {
      v33 = memcpy_s_0(v32, *(const rsize_t *)&Buf1.Data1, v30, 2LL * *(v30 - 4));
      AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v33 != 0 ? 0x8000FFFF : 0);
      if ( AuthDataFromPackedCredentials < 0 )
      {
LABEL_58:
        v26 = v31;
        goto LABEL_41;
      }
      v34 = (unsigned int)(v29 + 2);
      v35 = LiveAllocate(v34);
      Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v5 + 32);
      *((_QWORD *)v5 + 4) = v35;
      if ( v35 )
      {
        v36 = memcpy_s_0(v35, (unsigned int)v34, v52[0], (unsigned int)SourceSize);
        AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v36 != 0 ? 0x8000FFFF : 0);
        if ( AuthDataFromPackedCredentials >= 0 )
        {
          *((_QWORD *)v5 + 5) = v34;
          *((_DWORD *)v5 + 6) = 2;
          ATL::CStringData::Release(v31);
          goto LABEL_52;
        }
        goto LABEL_58;
      }
    }
    AuthDataFromPackedCredentials = -1073741670;
    goto LABEL_58;
  }
  if ( (unsigned int)v6 < 0x10 )
    goto LABEL_20;
  v9 = (unsigned __int16)v7[1];
  if ( v9 > (unsigned int)v6 )
    goto LABEL_20;
  if ( *v7 > (unsigned __int16)v9 )
    goto LABEL_20;
  v10 = *((unsigned int *)v7 + 1);
  v11 = (unsigned __int16)v7[4];
  if ( (int)v11 + (int)v10 < (unsigned int)v10 || (int)v11 + (int)v10 > v9 || (v11 & 1) != 0 )
    goto LABEL_20;
  v12 = CredSerializationHelper::DeSerializeCredentials(
          (struct WLIDCredentialBagSerializer *)&v45,
          (unsigned __int8 *)v7 + v10,
          v11,
          (struct _WLIDCredentialBag *)&v44);
  AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v12);
  if ( AuthDataFromPackedCredentials >= 0 )
  {
    v14 = CWLIDCCHelper::ValidateCredUICredBag((const struct _WLIDCredentialBag *)&v44, v13);
    AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v14);
    if ( AuthDataFromPackedCredentials >= 0 )
    {
      v15 = v44;
      if ( (_DWORD)v44 != 1 )
      {
        if ( (unsigned int)(v44 - 3) >= 2 )
        {
          LODWORD(v42) = v44;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
            0x397u,
            L"Unexpected credBag type. credType=%d.",
            v42);
LABEL_20:
          AuthDataFromPackedCredentials = -1073741811;
          goto LABEL_21;
        }
        DATokenParamsFromCredBag = CWLIDCCHelper::GetDATokenParamsFromCredBag(
                                     (struct IMemoryManager *)&v48,
                                     (const struct _WLIDCredentialBag *)&v44,
                                     (unsigned __int16 **)v5 + 7,
                                     (unsigned __int16 **)v5 + 13,
                                     (unsigned __int16 **)v5 + 10,
                                     (unsigned __int8 **)v5 + 16,
                                     (unsigned int *)v5 + 44,
                                     (unsigned __int16 **)v5 + 23);
        AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(DATokenParamsFromCredBag);
        if ( AuthDataFromPackedCredentials < 0 )
          goto LABEL_21;
        *((_QWORD *)v5 + 17) = *((unsigned int *)v5 + 44);
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(*((_QWORD *)v5 + 7) + 2 * v19) );
        *((_QWORD *)v5 + 8) = 2 * v19;
        v15 = v44;
        if ( (_DWORD)v44 == 4 )
        {
          *((_DWORD *)v5 + 6) = 3;
          v15 = v44;
        }
      }
      if ( ((v15 - 1) & 0xFFFFFFFD) == 0 )
      {
        v20 = (unsigned int)(2 * *(_DWORD *)(*((_QWORD *)&v44 + 1) + 8LL));
        v21 = LiveAllocate(v20 + 2);
        Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(v5 + 32);
        *((_QWORD *)v5 + 4) = v21;
        if ( !v21 )
          goto LABEL_59;
        v22 = memcpy_s_0(
                v21,
                (unsigned int)v20,
                *(const void *const *)(*((_QWORD *)&v44 + 1) + 16LL),
                (unsigned int)v20);
        AuthDataFromPackedCredentials = LiveMapHResultToNtStatus(v22 != 0 ? 0x8000FFFF : 0);
        if ( AuthDataFromPackedCredentials < 0 )
          goto LABEL_21;
        *((_QWORD *)v5 + 5) = v20;
        *((_DWORD *)v5 + 6) = 1;
      }
      *((_DWORD *)v5 + 52) = *((_DWORD *)v7 + 3);
      goto LABEL_52;
    }
  }
LABEL_21:
  v16 = AuthDataFromPackedCredentials;
  CTraceFuncW<long>::~CTraceFuncW<long>(v56);
  AutoWLIDCredentialBag::~AutoWLIDCredentialBag((AutoWLIDCredentialBag *)&v44);
  v48 = &IMemoryFunctions::`vftable';
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(Source);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v55);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v52);
  Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(&v49);
  return v16;
}

```

## disassembly

```asm
0x18000ed44  mov     [rsp-8+arg_10], r8
0x18000ed49  mov     [rsp-8+arg_8], rdx
0x18000ed4e  push    rbp
0x18000ed4f  push    rbx
0x18000ed50  push    rsi
0x18000ed51  push    rdi
0x18000ed52  push    r12
0x18000ed54  push    r13
0x18000ed56  push    r14
0x18000ed58  push    r15
0x18000ed5a  lea     rbp, [rsp-18h]
0x18000ed5f  sub     rsp, 118h
0x18000ed66  mov     rbx, r8
0x18000ed69  mov     rdi, rdx
0x18000ed6c  xor     r15d, r15d
0x18000ed6f  mov     [rbp+50h+arg_0], r15d
0x18000ed73  mov     [rbp+50h+var_D0], r15
0x18000ed77  mov     [rbp+50h+var_C0], r15
0x18000ed7b  mov     [rbp+50h+var_C8], r15
0x18000ed7f  mov     [rbp+50h+var_B8], r15
0x18000ed83  mov     [rbp+50h+var_A8], r15
0x18000ed87  mov     [rbp+50h+var_B0], r15
0x18000ed8b  mov     [rbp+50h+var_80], r15
0x18000ed8f  mov     [rbp+50h+var_70], r15
0x18000ed93  mov     [rbp+50h+var_78], r15
0x18000ed97  mov     [rbp+50h+Source], r15
0x18000ed9b  mov     [rbp+50h+var_88], r15
0x18000ed9f  mov     [rbp+50h+var_90], r15
0x18000eda3  mov     dword ptr [rbp+50h+SourceSize], r15d
0x18000eda7  lea     rax, ??_7LiveMemoryManager@@6B@; const LiveMemoryManager::`vftable'
0x18000edae  mov     [rsp+150h+var_D8], rax
0x18000edb3  xorps   xmm0, xmm0
0x18000edb6  movups  [rsp+150h+Buf1], xmm0
0x18000edbb  mov     rax, [rcx]
0x18000edbe  mov     rax, [rax+8]
0x18000edc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edc7  mov     [rsp+150h+var_F8], rax
0x18000edcc  xorps   xmm0, xmm0
0x18000edcf  movups  [rsp+150h+var_108], xmm0
0x18000edd4  lea     rdx, aGetlogoncredsf; "GetLogonCredsFromAuthData"
0x18000eddb  mov     [rbp+50h+var_68], rdx
0x18000eddf  lea     rax, [rbp+50h+arg_0]
0x18000ede3  mov     [rbp+50h+var_60], rax
0x18000ede7  mov     [rbp+50h+var_58], r15
0x18000edeb  mov     [rbp+50h+var_50], r15
0x18000edef  xor     r9d, r9d; unsigned int
0x18000edf2  mov     r8d, 32Eh; char *
0x18000edf8  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000edff  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000ee04  nop
0x18000ee05  test    rdi, rdi
0x18000ee08  jz      loc_18000EF89
0x18000ee0e  test    rbx, rbx
0x18000ee11  jz      loc_18000EF89
0x18000ee17  mov     [rbx], r15
0x18000ee1a  lea     r9, [rsp+150h+Buf1]; struct _GUID *
0x18000ee1f  lea     r8, [rbp+50h+SourceSize]; unsigned int *
0x18000ee23  lea     rdx, [rbp+50h+Source]; unsigned __int8 **
0x18000ee27  mov     rcx, [rdi+10h]; struct _SEC_WINNT_AUTH_PACKED_CREDENTIALS *
0x18000ee2b  call    ?GetAuthDataFromPackedCredentials@@YAJPEAU_SEC_WINNT_AUTH_PACKED_CREDENTIALS@@PEAPEAEPEAKPEAU_GUID@@@Z; GetAuthDataFromPackedCredentials(_SEC_WINNT_AUTH_PACKED_CREDENTIALS *,uchar * *,ulong *,_GUID *)
0x18000ee30  mov     [rbp+50h+arg_0], eax
0x18000ee33  test    eax, eax
0x18000ee35  js      loc_18000EF90
0x18000ee3b  mov     ecx, 0D8h; unsigned __int64
0x18000ee40  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000ee45  mov     rsi, rax
0x18000ee48  lea     rcx, [rbp+50h+var_D0]
0x18000ee4c  call    ?Clear@?$Auto@PEAULOGON_CREDS@@VLogonCredsFunctor@@VDummyContext@@@@QEAAXXZ; Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::Clear(void)
0x18000ee51  mov     [rbp+50h+var_D0], rsi
0x18000ee55  test    rsi, rsi
0x18000ee58  jz      loc_18000F3AF
0x18000ee5e  lea     r12d, [r15+2]
0x18000ee62  mov     ebx, dword ptr [rbp+50h+SourceSize]
0x18000ee65  mov     rdi, [rbp+50h+Source]
0x18000ee69  test    rdi, rdi
0x18000ee6c  jz      short loc_18000EE72
0x18000ee6e  test    ebx, ebx
0x18000ee70  jnz     short loc_18000EEA4
0x18000ee72  mov     eax, 0C000006Ah
0x18000ee77  mov     [rbp+50h+arg_0], eax
0x18000ee7a  mov     dword ptr [rsp+150h+var_130], eax
0x18000ee7e  lea     r9, aSpauthdataNull; "spAuthData == nullptr, Status=0x%x."
0x18000ee85  mov     r8d, 34Ah; unsigned int
0x18000ee8b  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000ee92  mov     ecx, r12d; unsigned __int8
0x18000ee95  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ee9a  cmp     [rbp+50h+arg_0], r15d
0x18000ee9e  jl      loc_18000EF90
0x18000eea4  mov     r14d, 10h
0x18000eeaa  mov     r8d, r14d; Size
0x18000eead  lea     rdx, qword_18003AB38; Buf2
0x18000eeb4  lea     rcx, [rsp+150h+Buf1]; Buf1
0x18000eeb9  call    memcmp_0
0x18000eebe  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000eec2  test    eax, eax
0x18000eec4  jnz     loc_18000F108
0x18000eeca  cmp     ebx, r14d
0x18000eecd  jb      loc_18000EF89
0x18000eed3  movzx   eax, word ptr [rdi+2]
0x18000eed7  cmp     eax, ebx
0x18000eed9  ja      loc_18000EF89
0x18000eedf  cmp     [rdi], ax
0x18000eee2  ja      loc_18000EF89
0x18000eee8  mov     ecx, [rdi+4]
0x18000eeeb  movzx   r8d, word ptr [rdi+8]; DestinationSize
0x18000eef0  lea     edx, [r8+rcx]
0x18000eef4  cmp     edx, ecx
0x18000eef6  jb      loc_18000EF89
0x18000eefc  cmp     edx, eax
0x18000eefe  ja      loc_18000EF89
0x18000ef04  test    r8b, 1
0x18000ef08  jnz     short loc_18000EF89
0x18000ef0a  lea     rdx, [rdi+rcx]; Source
0x18000ef0e  lea     r9, [rsp+150h+var_108]; pObject
0x18000ef13  lea     rcx, [rsp+150h+var_F8]; this
0x18000ef18  call    ?DeSerializeCredentials@CredSerializationHelper@@SAJAEAVWLIDCredentialBagSerializer@@PEAEKPEAU_WLIDCredentialBag@@@Z; CredSerializationHelper::DeSerializeCredentials(WLIDCredentialBagSerializer &,uchar *,ulong,_WLIDCredentialBag *)
0x18000ef1d  mov     ecx, eax; int
0x18000ef1f  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000ef24  mov     [rbp+50h+arg_0], eax
0x18000ef27  test    eax, eax
0x18000ef29  js      short loc_18000EF90
0x18000ef2b  lea     rcx, [rsp+150h+var_108]; struct _WLIDCredentialBag *
0x18000ef30  call    ?ValidateCredUICredBag@CWLIDCCHelper@@SAJPEBU_WLIDCredentialBag@@_N@Z; CWLIDCCHelper::ValidateCredUICredBag(_WLIDCredentialBag const *,bool)
0x18000ef35  mov     ecx, eax; int
0x18000ef37  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000ef3c  mov     [rbp+50h+arg_0], eax
0x18000ef3f  test    eax, eax
0x18000ef41  js      short loc_18000EF90
0x18000ef43  mov     r8d, dword ptr [rsp+150h+var_108]
0x18000ef48  mov     r9d, r8d
0x18000ef4b  sub     r9d, 1
0x18000ef4f  jz      loc_18000F080
0x18000ef55  sub     r9d, r12d
0x18000ef58  jz      loc_18000EFF1
0x18000ef5e  cmp     r9d, 1
0x18000ef62  jz      loc_18000EFF1
0x18000ef68  mov     dword ptr [rsp+150h+var_130], r8d
0x18000ef6d  lea     r9, aUnexpectedCred; "Unexpected credBag type. credType=%d."
0x18000ef74  mov     r8d, 397h; unsigned int
0x18000ef7a  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000ef81  mov     ecx, r12d; unsigned __int8
0x18000ef84  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000ef89  mov     [rbp+50h+arg_0], 0C000000Dh
0x18000ef90  mov     ebx, [rbp+50h+arg_0]
0x18000ef93  lea     rcx, [rbp+50h+var_68]
0x18000ef97  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000ef9c  nop
0x18000ef9d  lea     rcx, [rsp+150h+var_108]; this
0x18000efa2  call    ??1AutoWLIDCredentialBag@@QEAA@XZ; AutoWLIDCredentialBag::~AutoWLIDCredentialBag(void)
0x18000efa7  nop
0x18000efa8  lea     rax, ??_7IMemoryFunctions@@6B@; const IMemoryFunctions::`vftable'
0x18000efaf  mov     [rsp+150h+var_D8], rax
0x18000efb4  lea     rcx, [rbp+50h+Source]
0x18000efb8  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x18000efbd  nop
0x18000efbe  lea     rcx, [rbp+50h+var_80]
0x18000efc2  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x18000efc7  nop
0x18000efc8  lea     rcx, [rbp+50h+var_B8]
0x18000efcc  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x18000efd1  nop
0x18000efd2  lea     rcx, [rbp+50h+var_D0]
0x18000efd6  call    ??1?$Auto@PEAULOGON_CREDS@@VLogonCredsFunctor@@VDummyContext@@@@QEAA@XZ; Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>::~Auto<LOGON_CREDS *,LogonCredsFunctor,DummyContext>(void)
0x18000efdb  mov     eax, ebx
0x18000efdd  add     rsp, 118h
0x18000efe4  pop     r15
0x18000efe6  pop     r14
0x18000efe8  pop     r13
0x18000efea  pop     r12
0x18000efec  pop     rdi
0x18000efed  pop     rsi
0x18000efee  pop     rbx
0x18000efef  pop     rbp
0x18000eff0  retn
0x18000eff1  lea     r14, [rsi+0B0h]
0x18000eff8  lea     r15, [rsi+80h]
0x18000efff  lea     rax, [rsi+0B8h]
0x18000f006  lea     rcx, [rsi+50h]
0x18000f00a  lea     r9, [rsi+68h]; unsigned __int16 **
0x18000f00e  mov     [rsp+150h+var_118], rax; unsigned __int16 **
0x18000f013  mov     [rsp+150h+var_120], r14; unsigned int *
0x18000f018  mov     [rsp+150h+var_128], r15; unsigned __int8 **
0x18000f01d  mov     [rsp+150h+var_130], rcx; unsigned __int16 **
0x18000f022  lea     r8, [rsi+38h]; unsigned __int16 **
0x18000f026  lea     rdx, [rsp+150h+var_108]; struct _WLIDCredentialBag *
0x18000f02b  lea     rcx, [rsp+150h+var_D8]; struct IMemoryManager *
0x18000f030  call    ?GetDATokenParamsFromCredBag@CWLIDCCHelper@@SAJPEAVIMemoryManager@@PEBU_WLIDCredentialBag@@PEAPEAG22PEAPEAEPEAK2@Z; CWLIDCCHelper::GetDATokenParamsFromCredBag(IMemoryManager *,_WLIDCredentialBag const *,ushort * *,ushort * *,ushort * *,uchar * *,ulong *,ushort * *)
0x18000f035  mov     ecx, eax; int
0x18000f037  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000f03c  mov     [rbp+50h+arg_0], eax
0x18000f03f  test    eax, eax
0x18000f041  js      loc_18000EF90
0x18000f047  mov     eax, [r14]
0x18000f04a  mov     [r15+8], rax
0x18000f04e  mov     rcx, [rsi+38h]
0x18000f052  mov     rax, r13
0x18000f055  xor     r15d, r15d
0x18000f058  inc     rax
0x18000f05b  cmp     [rcx+rax*2], r15w
0x18000f060  jnz     short loc_18000F058
0x18000f062  add     rax, rax
0x18000f065  mov     [rsi+40h], rax
0x18000f069  mov     r8d, dword ptr [rsp+150h+var_108]
0x18000f06e  cmp     r8d, 4
0x18000f072  jnz     short loc_18000F080
0x18000f074  mov     dword ptr [rsi+18h], 3
0x18000f07b  mov     r8d, dword ptr [rsp+150h+var_108]
0x18000f080  lea     eax, [r8-1]
0x18000f084  mov     r12d, 8000FFFFh
0x18000f08a  test    eax, 0FFFFFFFDh
0x18000f08f  jnz     short loc_18000F0FA
0x18000f091  mov     rax, qword ptr [rsp+150h+var_108+8]
0x18000f096  mov     ecx, [rax+8]
0x18000f099  add     ecx, ecx
0x18000f09b  mov     ebx, ecx
0x18000f09d  add     rcx, 2; unsigned __int64
0x18000f0a1  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000f0a6  mov     r15, rax
0x18000f0a9  lea     rcx, [rsi+20h]
0x18000f0ad  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000f0b2  mov     [rsi+20h], r15
0x18000f0b6  test    r15, r15
0x18000f0b9  jz      loc_18000F3AF
0x18000f0bf  mov     r9d, ebx; SourceSize
0x18000f0c2  mov     r8, qword ptr [rsp+150h+var_108+8]
0x18000f0c7  mov     r8, [r8+10h]; Source
0x18000f0cb  mov     edx, ebx; DestinationSize
0x18000f0cd  mov     rcx, r15; Destination
0x18000f0d0  call    memcpy_s_0
0x18000f0d5  neg     eax
0x18000f0d7  sbb     ecx, ecx
0x18000f0d9  and     ecx, r12d; int
0x18000f0dc  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000f0e1  mov     [rbp+50h+arg_0], eax
0x18000f0e4  xor     r15d, r15d
0x18000f0e7  test    eax, eax
0x18000f0e9  js      loc_18000EF90
0x18000f0ef  mov     [rsi+28h], rbx
0x18000f0f3  mov     dword ptr [rsi+18h], 1
0x18000f0fa  mov     eax, [rdi+0Ch]
0x18000f0fd  mov     [rsi+0D0h], eax
0x18000f103  jmp     loc_18000F327
0x18000f108  mov     r8, r14; Size
0x18000f10b  lea     rdx, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD; Buf2
0x18000f112  lea     rcx, [rsp+150h+Buf1]; Buf1
0x18000f117  call    memcmp_0
0x18000f11c  test    eax, eax
0x18000f11e  jnz     short loc_18000F190
0x18000f120  test    bl, 1
0x18000f123  jnz     loc_18000EF89
0x18000f129  lea     eax, [rbx+2]
0x18000f12c  mov     r15d, eax
0x18000f12f  mov     ecx, eax; unsigned __int64
0x18000f131  call    ?LiveAllocate@@YAPEAX_K@Z; LiveAllocate(unsigned __int64)
0x18000f136  mov     r12, rax
0x18000f139  lea     rcx, [rsi+20h]
0x18000f13d  call    ?Clear@?$Auto@PEAU_UnsignedProofOfPossessionTokenParameter@@V?$LiveMemoryFunctor@PEAU_UnsignedProofOfPossessionTokenParameter@@@@VDummyContext@@@@QEAAXXZ; Auto<_UnsignedProofOfPossessionTokenParameter *,LiveMemoryFunctor<_UnsignedProofOfPossessionTokenParameter *>,DummyContext>::Clear(void)
0x18000f142  mov     [rsi+20h], r12
0x18000f146  test    r12, r12
0x18000f149  jz      loc_18000F3AF
0x18000f14f  mov     r9, rbx; SourceSize
0x18000f152  mov     r8, rdi; Source
0x18000f155  mov     edx, r15d; DestinationSize
0x18000f158  mov     rcx, r12; Destination
0x18000f15b  call    memcpy_s_0
0x18000f160  neg     eax
0x18000f162  sbb     ecx, ecx
0x18000f164  mov     r12d, 8000FFFFh
0x18000f16a  and     ecx, r12d; int
0x18000f16d  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18000f172  mov     [rbp+50h+arg_0], eax
0x18000f175  test    eax, eax
0x18000f177  js      loc_18000EF90
0x18000f17d  mov     [rsi+28h], r15
0x18000f181  mov     dword ptr [rsi+18h], 1
0x18000f188  xor     r15d, r15d
0x18000f18b  jmp     loc_18000F327
0x18000f190  mov     r8, r14; Size
0x18000f193  lea     rdx, SEC_WINNT_AUTH_DATA_TYPE_NGC; Buf2
0x18000f19a  lea     rcx, [rsp+150h+Buf1]; Buf1
0x18000f19f  call    memcmp_0
0x18000f1a4  test    eax, eax
0x18000f1a6  jnz     loc_18000EF89
0x18000f1ac  mov     [rsp+150h+var_E0], r15
0x18000f1b1  mov     [rbp+50h+var_A0], r15
0x18000f1b5  lea     rcx, [rsp+150h+var_110]
0x18000f1ba  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000f1bf  nop
0x18000f1c0  test    bl, 1
0x18000f1c3  jz      short loc_18000F1DF
0x18000f1c5  mov     [rbp+50h+arg_0], 0C000000Dh
0x18000f1cc  mov     rcx, [rsp+150h+var_110]
0x18000f1d1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f1d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f1da  jmp     loc_18000EF90
0x18000f1df  lea     rax, [rbp+50h+var_A0]
0x18000f1e3  mov     [rsp+150h+var_128], rax
0x18000f1e8  lea     rax, [rbp+50h+var_80]
0x18000f1ec  mov     [rsp+150h+var_130], rax
0x18000f1f1  lea     r9, [rsp+150h+var_E0]
  ... truncated ...
```

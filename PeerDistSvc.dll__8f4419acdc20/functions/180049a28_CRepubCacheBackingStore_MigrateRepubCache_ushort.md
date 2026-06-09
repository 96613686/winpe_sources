# CRepubCacheBackingStore::MigrateRepubCache(ushort *)

- ea: `0x180049a28`
- end: `0x180049fea`
- name: `?MigrateRepubCache@CRepubCacheBackingStore@@QEAAKPEAG@Z`
- size: `1474`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x18004a510`

## callees

- `0x180004b18`
- `0x18000573c`
- `0x180008290`
- `0x1800094d4`
- `0x180009ec4`
- `0x18000ceac`
- `0x18000cf48`
- `0x18000e58c`
- `0x180018340`
- `0x18002a878`
- `0x180049a28`
- `0x180052460`
- `0x180114ae0`
- `0x180114fd4`
- `0x18012e628`
- `0x180130318`
- `0x1801303ac`
- `0x1801448c0`
- `0x180159010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049df8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180049dec`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180049dec`

## string_xrefs

- `0x180049c05`: `PeerDistRepubCacheImportJetInstance`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRepubCacheBackingStore::MigrateRepubCache(CRepubCacheBackingStore *this, unsigned __int16 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64); // rbx
  unsigned int appended; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // edi
  CHostedCacheMsgEncoding *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int i; // r13d
  const unsigned __int16 *v19; // r8
  int v20; // eax
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v22; // rcx
  int v23; // edx
  const size_t *v25; // rax
  struct IPreLoadingEngine *v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, __int64); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, __int64); // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, __int64); // [rsp+58h] [rbp-A8h] BYREF
  CRepubCacheBackingStore *v32; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  v33 = a2;
  v32 = this;
  v27 = 0;
  v3 = 0;
  v29 = 0;
  v31 = 0;
  v28 = 0;
  v30 = *((_QWORD *)this + 6);
  SmartPointer<CHostedCacheListManager>::AddRef(&v30);
  FileName[0] = 0;
  if ( a2 && *a2 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 529, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, a2);
    }
    v26 = 0;
    appended = IPreLoadingEngine::Create(&v26);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 530;
      goto LABEL_42;
    }
    std::auto_ptr<TnoHashKey>::reset(&v27, v26, v5, v6);
    v26 = 0;
    appended = IPreLoadDatasetSecondaryStoreEnabledInfo::Create(&v26, 1);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 531;
      goto LABEL_42;
    }
    std::auto_ptr<TnoHashKey>::reset(&v31, v26, v10, v11);
    v26 = 0;
    appended = IPreLoadDataset::Create(&v26);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 532;
      goto LABEL_42;
    }
    std::auto_ptr<TnoHashKey>::reset(&v29, v26, v12, v13);
    v3 = v29;
    appended = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), unsigned __int16 *, const wchar_t *, __int64 (__fastcall ***)(_QWORD, __int64), _QWORD))(*v29)[1])(
                 v29,
                 a2,
                 L"PeerDistRepubCacheImportJetInstance",
                 v31,
                 *((_QWORD *)v32 + 7));
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 533;
      goto LABEL_42;
    }
    appended = (*v3)[3](v3, (__int64)&v28);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 534;
      goto LABEL_42;
    }
    appended = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), _QWORD, _QWORD, __int64 *))(*v27)[1])(
                 v27,
                 0,
                 0,
                 &v30);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_43;
      }
      v9 = 535;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v8 + 12), v9, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, appended);
      goto LABEL_43;
    }
    appended = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 96LL))(v28, v27);
    v7 = appended;
    if ( appended )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v9 = 536;
        goto LABEL_42;
      }
    }
LABEL_43:
    SmartPointer<CHostedCacheListManager>::Release(&v28);
    v28 = 0;
    if ( v3 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v3)[2])(v3);
      std::auto_ptr<TnoHashKey>::reset(&v29, 0, v14, v15);
      v3 = v29;
    }
    if ( v27 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v27)[2])(v27);
      std::auto_ptr<TnoHashKey>::reset(&v27, 0, v16, v17);
    }
    if ( v7 )
    {
LABEL_75:
      SmartPointer<CHostedCacheListManager>::Release(&v30);
      SmartPointer<CHostedCacheListManager>::Release(&v28);
      std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v31);
      std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v29);
      std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v27);
      return v7;
    }
    for ( i = 1; ; ++i )
    {
      if ( i >= 5 )
      {
        v7 = DestroyCacheStore(v33, 1, 0, 0, 0);
        goto LABEL_75;
      }
      v19 = (const unsigned __int16 *)((char *)v32 + 768 * i + 4052);
      if ( *v19 )
      {
        v20 = StringCchCopyW(FileName, 0x104u, v19);
        if ( v20 < 0 )
        {
          v7 = TnoWin32ErrFromHR(v20);
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 537, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
          }
          goto LABEL_43;
        }
        appended = AppendFilePath(FileName, L"PeerDistRepubBlockStorage.pds");
        v7 = appended;
        if ( appended )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v9 = 538;
            goto LABEL_42;
          }
          goto LABEL_43;
        }
        if ( !DeleteFileW(FileName) )
        {
          LastError = GetLastError();
          if ( LastError - 2 <= 1 )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
            {
              v23 = 539;
              goto LABEL_64;
            }
          }
          else if ( LastError )
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              v23 = 540;
LABEL_64:
              WPP_SF_Sd(
                *((_QWORD *)v22 + 12),
                v23,
                (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
                (unsigned int)FileName,
                LastError);
              continue;
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v25 = (const size_t *)a2;
    if ( !a2 )
      v25 = &dword_1801747C4;
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      528,
      (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      (_DWORD)a2,
      (__int64)v25);
  }
  SmartPointer<CHostedCacheListManager>::Release(&v30);
  SmartPointer<CHostedCacheListManager>::Release(&v28);
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v31);
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v29);
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(&v27);
  return 87;
}

```

## disassembly

```asm
0x180049a28  mov     [rsp-8+arg_10], rbx
0x180049a2d  mov     [rsp-8+arg_18], rdi
0x180049a32  push    rbp
0x180049a33  push    r12
0x180049a35  push    r13
0x180049a37  push    r14
0x180049a39  push    r15
0x180049a3b  lea     rbp, [rsp-190h]
0x180049a43  sub     rsp, 290h
0x180049a4a  mov     rax, cs:__security_cookie
0x180049a51  xor     rax, rsp
0x180049a54  mov     [rbp+1B0h+var_30], rax
0x180049a5b  mov     r13, rdx
0x180049a5e  mov     [rsp+2B0h+var_248], rdx
0x180049a63  mov     [rsp+2B0h+var_250], rcx
0x180049a68  xor     edi, edi
0x180049a6a  mov     [rsp+2B0h+var_278], rdi
0x180049a6f  mov     ebx, edi
0x180049a71  mov     [rsp+2B0h+var_268], rbx
0x180049a76  mov     [rsp+2B0h+var_258], rdi
0x180049a7b  mov     [rsp+2B0h+var_270], rdi
0x180049a80  mov     rax, [rcx+30h]
0x180049a84  mov     [rsp+2B0h+var_260], rax
0x180049a89  lea     rcx, [rsp+2B0h+var_260]
0x180049a8e  call    ?AddRef@?$SmartPointer@VCHostedCacheListManager@@@@IEAAXXZ; SmartPointer<CHostedCacheListManager>::AddRef(void)
0x180049a93  nop
0x180049a94  mov     [rsp+2B0h+FileName], di
0x180049a99  test    r13, r13
0x180049a9c  jz      loc_180049F32
0x180049aa2  cmp     [r13+0], di
0x180049aa7  jz      loc_180049F32
0x180049aad  lea     r15, WPP_GLOBAL_Control
0x180049ab4  lea     r12, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180049abb  mov     r14b, 4
0x180049abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ac5  cmp     rcx, r15
0x180049ac8  jz      short loc_180049AEA
0x180049aca  test    [rcx+6Ch], r14b
0x180049ace  jz      short loc_180049AEA
0x180049ad0  cmp     [rcx+69h], r14b
0x180049ad4  jb      short loc_180049AEA
0x180049ad6  mov     edx, 211h
0x180049adb  mov     r9, r13
0x180049ade  mov     r8, r12
0x180049ae1  mov     rcx, [rcx+60h]
0x180049ae5  call    WPP_SF_S
0x180049aea  mov     [rsp+2B0h+var_280], rdi
0x180049aef  lea     rcx, [rsp+2B0h+var_280]; struct IPreLoadingEngine **
0x180049af4  call    ?Create@IPreLoadingEngine@@SAKPEAPEAV1@@Z; IPreLoadingEngine::Create(IPreLoadingEngine * *)
0x180049af9  mov     edi, eax
0x180049afb  test    eax, eax
0x180049afd  jz      short loc_180049B2D
0x180049aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b06  cmp     rcx, r15
0x180049b09  jz      loc_180049D1C
0x180049b0f  test    [rcx+6Ch], r14b
0x180049b13  jz      loc_180049D1C
0x180049b19  cmp     byte ptr [rcx+69h], 1
0x180049b1d  jb      loc_180049D1C
0x180049b23  mov     edx, 212h
0x180049b28  jmp     loc_180049D0D
0x180049b2d  mov     rdx, [rsp+2B0h+var_280]
0x180049b32  lea     rcx, [rsp+2B0h+var_278]
0x180049b37  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180049b3c  mov     [rsp+2B0h+var_280], 0
0x180049b45  mov     dl, 1; bool
0x180049b47  lea     rcx, [rsp+2B0h+var_280]; struct IPreLoadDatasetSecondaryStoreEnabledInfo **
0x180049b4c  call    ?Create@IPreLoadDatasetSecondaryStoreEnabledInfo@@SAKPEAPEAV1@_N@Z; IPreLoadDatasetSecondaryStoreEnabledInfo::Create(IPreLoadDatasetSecondaryStoreEnabledInfo * *,bool)
0x180049b51  mov     edi, eax
0x180049b53  test    eax, eax
0x180049b55  jz      short loc_180049B85
0x180049b57  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b5e  cmp     rcx, r15
0x180049b61  jz      loc_180049D1C
0x180049b67  test    [rcx+6Ch], r14b
0x180049b6b  jz      loc_180049D1C
0x180049b71  cmp     byte ptr [rcx+69h], 1
0x180049b75  jb      loc_180049D1C
0x180049b7b  mov     edx, 213h
0x180049b80  jmp     loc_180049D0D
0x180049b85  mov     rdx, [rsp+2B0h+var_280]
0x180049b8a  lea     rcx, [rsp+2B0h+var_258]
0x180049b8f  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180049b94  mov     [rsp+2B0h+var_280], 0
0x180049b9d  lea     rcx, [rsp+2B0h+var_280]; struct IPreLoadDataset **
0x180049ba2  call    ?Create@IPreLoadDataset@@SAKPEAPEAV1@@Z; IPreLoadDataset::Create(IPreLoadDataset * *)
0x180049ba7  mov     edi, eax
0x180049ba9  test    eax, eax
0x180049bab  jz      short loc_180049BDB
0x180049bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bb4  cmp     rcx, r15
0x180049bb7  jz      loc_180049D1C
0x180049bbd  test    [rcx+6Ch], r14b
0x180049bc1  jz      loc_180049D1C
0x180049bc7  cmp     byte ptr [rcx+69h], 1
0x180049bcb  jb      loc_180049D1C
0x180049bd1  mov     edx, 214h
0x180049bd6  jmp     loc_180049D0D
0x180049bdb  mov     rdx, [rsp+2B0h+var_280]
0x180049be0  lea     rcx, [rsp+2B0h+var_268]
0x180049be5  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180049bea  mov     rbx, [rsp+2B0h+var_268]
0x180049bef  mov     rax, [rbx]
0x180049bf2  mov     rcx, [rsp+2B0h+var_250]
0x180049bf7  mov     rcx, [rcx+38h]
0x180049bfb  mov     qword ptr [rsp+2B0h+var_290], rcx
0x180049c00  mov     r9, [rsp+2B0h+var_258]
0x180049c05  lea     r8, aPeerdistrepubc_0; "PeerDistRepubCacheImportJetInstance"
0x180049c0c  mov     rdx, r13
0x180049c0f  mov     rcx, rbx
0x180049c12  mov     rax, [rax+8]
0x180049c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c1b  mov     edi, eax
0x180049c1d  test    eax, eax
0x180049c1f  jz      short loc_180049C4F
0x180049c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c28  cmp     rcx, r15
0x180049c2b  jz      loc_180049D1C
0x180049c31  test    [rcx+6Ch], r14b
0x180049c35  jz      loc_180049D1C
0x180049c3b  cmp     byte ptr [rcx+69h], 1
0x180049c3f  jb      loc_180049D1C
0x180049c45  mov     edx, 215h
0x180049c4a  jmp     loc_180049D0D
0x180049c4f  mov     rax, [rbx]
0x180049c52  lea     rdx, [rsp+2B0h+var_270]
0x180049c57  mov     rcx, rbx
0x180049c5a  mov     rax, [rax+18h]
0x180049c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c63  mov     edi, eax
0x180049c65  test    eax, eax
0x180049c67  jz      short loc_180049C94
0x180049c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c70  cmp     rcx, r15
0x180049c73  jz      loc_180049D1C
0x180049c79  test    [rcx+6Ch], r14b
0x180049c7d  jz      loc_180049D1C
0x180049c83  cmp     byte ptr [rcx+69h], 1
0x180049c87  jb      loc_180049D1C
0x180049c8d  mov     edx, 216h
0x180049c92  jmp     short loc_180049D0D
0x180049c94  mov     rcx, [rsp+2B0h+var_278]
0x180049c99  mov     rax, [rcx]
0x180049c9c  lea     r9, [rsp+2B0h+var_260]
0x180049ca1  xor     r8d, r8d
0x180049ca4  xor     edx, edx
0x180049ca6  mov     rax, [rax+8]
0x180049caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049caf  mov     edi, eax
0x180049cb1  test    eax, eax
0x180049cb3  jz      short loc_180049CD4
0x180049cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cbc  cmp     rcx, r15
0x180049cbf  jz      short loc_180049D1C
0x180049cc1  test    [rcx+6Ch], r14b
0x180049cc5  jz      short loc_180049D1C
0x180049cc7  cmp     byte ptr [rcx+69h], 1
0x180049ccb  jb      short loc_180049D1C
0x180049ccd  mov     edx, 217h
0x180049cd2  jmp     short loc_180049D0D
0x180049cd4  mov     rcx, [rsp+2B0h+var_270]
0x180049cd9  mov     rax, [rcx]
0x180049cdc  mov     rdx, [rsp+2B0h+var_278]
0x180049ce1  mov     rax, [rax+60h]
0x180049ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cea  mov     edi, eax
0x180049cec  test    eax, eax
0x180049cee  jz      short loc_180049D1C
0x180049cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cf7  cmp     rcx, r15
0x180049cfa  jz      short loc_180049D1C
0x180049cfc  test    [rcx+6Ch], r14b
0x180049d00  jz      short loc_180049D1C
0x180049d02  cmp     byte ptr [rcx+69h], 1
0x180049d06  jb      short loc_180049D1C
0x180049d08  mov     edx, 218h
0x180049d0d  mov     r9d, eax
0x180049d10  mov     r8, r12
0x180049d13  mov     rcx, [rcx+60h]
0x180049d17  call    WPP_SF_d
0x180049d1c  lea     rcx, [rsp+2B0h+var_270]
0x180049d21  call    ?Release@?$SmartPointer@VCHostedCacheListManager@@@@IEAAXXZ; SmartPointer<CHostedCacheListManager>::Release(void)
0x180049d26  xor     edx, edx
0x180049d28  mov     [rsp+2B0h+var_270], rdx
0x180049d2d  test    rbx, rbx
0x180049d30  jz      short loc_180049D54
0x180049d32  mov     rax, [rbx]
0x180049d35  mov     rcx, rbx
0x180049d38  mov     rax, [rax+10h]
0x180049d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d41  xor     edx, edx
0x180049d43  lea     rcx, [rsp+2B0h+var_268]
0x180049d48  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180049d4d  mov     rbx, [rsp+2B0h+var_268]
0x180049d52  xor     edx, edx
0x180049d54  mov     rcx, [rsp+2B0h+var_278]
0x180049d59  test    rcx, rcx
0x180049d5c  jz      short loc_180049D78
0x180049d5e  mov     rax, [rcx]
0x180049d61  mov     rax, [rax+10h]
0x180049d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d6a  xor     edx, edx
0x180049d6c  lea     rcx, [rsp+2B0h+var_278]
0x180049d71  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180049d76  xor     edx, edx
0x180049d78  test    edi, edi
0x180049d7a  jnz     loc_180049EF5
0x180049d80  lea     r13d, [rdi+1]
0x180049d84  cmp     r13d, 5
0x180049d88  jnb     loc_180049EDD
0x180049d8e  mov     eax, r13d
0x180049d91  lea     rcx, [rax+rax*2]
0x180049d95  shl     rcx, 8
0x180049d99  mov     r8, [rsp+2B0h+var_250]
0x180049d9e  add     r8, 0FD4h
0x180049da5  add     r8, rcx; unsigned __int16 *
0x180049da8  cmp     [r8], dx
0x180049dac  jz      loc_180049E5F
0x180049db2  mov     edx, 104h; unsigned __int64
0x180049db7  lea     rcx, [rsp+2B0h+FileName]; unsigned __int16 *
0x180049dbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180049dc1  mov     r9d, eax
0x180049dc4  test    eax, eax
0x180049dc6  js      loc_180049E95
0x180049dcc  lea     rdx, ?c_wszRepubBlockFileName@@3QBGB; "PeerDistRepubBlockStorage.pds"
0x180049dd3  lea     rcx, [rsp+2B0h+FileName]; unsigned __int16 *
0x180049dd8  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180049ddd  mov     edi, eax
0x180049ddf  test    eax, eax
0x180049de1  jnz     loc_180049E67
0x180049de7  lea     rcx, [rsp+2B0h+FileName]; lpFileName
0x180049dec  call    cs:__imp_DeleteFileW
0x180049df2  xor     edx, edx
0x180049df4  test    eax, eax
0x180049df6  jnz     short loc_180049E5F
0x180049df8  call    cs:__imp_GetLastError
0x180049dfe  lea     ecx, [rax-2]
0x180049e01  cmp     ecx, 1
0x180049e04  jbe     short loc_180049E2B
0x180049e06  xor     edx, edx
0x180049e08  test    eax, eax
0x180049e0a  jz      short loc_180049E5F
0x180049e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e13  cmp     rcx, r15
0x180049e16  jz      short loc_180049E5F
0x180049e18  test    [rcx+6Ch], r14b
0x180049e1c  jz      short loc_180049E5F
0x180049e1e  cmp     byte ptr [rcx+69h], 1
0x180049e22  jb      short loc_180049E5F
0x180049e24  mov     edx, 21Ch
0x180049e29  jmp     short loc_180049E48
0x180049e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e32  cmp     rcx, r15
0x180049e35  jz      short loc_180049E5D
0x180049e37  test    [rcx+6Ch], r14b
0x180049e3b  jz      short loc_180049E5D
0x180049e3d  cmp     [rcx+69h], r14b
0x180049e41  jb      short loc_180049E5D
0x180049e43  mov     edx, 21Bh
0x180049e48  mov     [rsp+2B0h+var_290], eax
0x180049e4c  lea     r9, [rsp+2B0h+FileName]
0x180049e51  mov     r8, r12
0x180049e54  mov     rcx, [rcx+60h]
0x180049e58  call    WPP_SF_Sd
0x180049e5d  xor     edx, edx
0x180049e5f  inc     r13d
0x180049e62  jmp     loc_180049D84
0x180049e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e6e  cmp     rcx, r15
0x180049e71  jz      loc_180049D1C
0x180049e77  test    [rcx+6Ch], r14b
0x180049e7b  jz      loc_180049D1C
0x180049e81  cmp     byte ptr [rcx+69h], 1
0x180049e85  jb      loc_180049D1C
0x180049e8b  mov     edx, 21Ah
0x180049e90  jmp     loc_180049D0D
0x180049e95  mov     ecx, r9d; int
0x180049e98  call    ?TnoWin32ErrFromHR@@YAKJ@Z; TnoWin32ErrFromHR(long)
0x180049e9d  mov     edi, eax
0x180049e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ea6  cmp     rcx, r15
0x180049ea9  jz      loc_180049D1C
0x180049eaf  test    [rcx+6Ch], r14b
0x180049eb3  jz      loc_180049D1C
0x180049eb9  cmp     byte ptr [rcx+69h], 1
0x180049ebd  jb      loc_180049D1C
0x180049ec3  mov     edx, 219h
0x180049ec8  mov     [rsp+2B0h+var_290], eax
0x180049ecc  mov     r8, r12
0x180049ecf  mov     rcx, [rcx+60h]
0x180049ed3  call    WPP_SF_Dd
0x180049ed8  jmp     loc_180049D1C
0x180049edd  mov     [rsp+2B0h+var_290], edx; unsigned int
0x180049ee1  xor     r9d, r9d; bool
0x180049ee4  xor     r8d, r8d; void *
0x180049ee7  mov     dl, 1; bool
0x180049ee9  mov     rcx, [rsp+2B0h+var_248]; unsigned __int16 *
0x180049eee  call    ?DestroyCacheStore@@YAKPEBG_NPEAX1K@Z; DestroyCacheStore(ushort const *,bool,void *,bool,ulong)
0x180049ef3  mov     edi, eax
0x180049ef5  lea     rcx, [rsp+2B0h+var_260]
  ... truncated ...
```

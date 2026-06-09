# CWatcherFactory::RegisterLocalChangeWatcher(ushort const *,_GUID const &,ushort const *,ushort const *,std::shared_ptr<void> const &,ulong const &,bool &)

- ea: `0x18002f440`
- end: `0x18002fbf4`
- name: `?RegisterLocalChangeWatcher@CWatcherFactory@@UEAAXPEBGAEBU_GUID@@00AEBV?$shared_ptr@X@std@@AEBKAEA_N@Z`
- size: `1972`
- prototype: `__int64 __usercall@<rax>(CWatcherFactory *this@<rcx>, __int64, __int64, __int64, bool *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180009158`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x18002f1e0`
- `0x18002f440`
- `0x18002fe24`
- `0x1800644c4`
- `0x18013e010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x18002f5c8`
- `ADVAPI32!GetTokenInformation` at `0x18002f5c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f639`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f67c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f81b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f639`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f67c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f81b`

## string_xrefs

- `0x18002f6d6`: `@%systemroot%\system32\WorkfoldersControl.dll,-1`
- `0x18002f708`: `%systemroot%\system32\WorkfoldersControl.dll,-1`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
void __fastcall CWatcherFactory::RegisterLocalChangeWatcher(
        CWatcherFactory *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        HANDLE *a6,
        _DWORD *a7,
        bool *a8)
{
  _BYTE *v11; // rax
  char v12; // al
  HANDLE *v13; // r14
  unsigned int v14; // r15d
  HRESULT v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  HRESULT v22; // eax
  int v23; // [rsp+30h] [rbp-158h] BYREF
  int v24; // [rsp+34h] [rbp-154h]
  char v25; // [rsp+38h] [rbp-150h]
  const char *v26; // [rsp+40h] [rbp-148h]
  __int64 v27; // [rsp+48h] [rbp-140h]
  LPVOID v28; // [rsp+50h] [rbp-138h] BYREF
  unsigned int TokenInformation; // [rsp+58h] [rbp-130h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-128h] BYREF
  LPVOID v31; // [rsp+68h] [rbp-120h] BYREF
  int pExceptionObject; // [rsp+70h] [rbp-118h] BYREF
  int v33; // [rsp+74h] [rbp-114h] BYREF
  int v34; // [rsp+78h] [rbp-110h] BYREF
  int v35; // [rsp+7Ch] [rbp-10Ch] BYREF
  int v36; // [rsp+80h] [rbp-108h]
  DWORD ReturnLength; // [rsp+84h] [rbp-104h] BYREF
  int LastFailureAsHRESULT; // [rsp+88h] [rbp-100h] BYREF
  HRESULT v39; // [rsp+8Ch] [rbp-FCh] BYREF
  HRESULT v40; // [rsp+90h] [rbp-F8h] BYREF
  int v41; // [rsp+94h] [rbp-F4h] BYREF
  int v42; // [rsp+98h] [rbp-F0h] BYREF
  int v43; // [rsp+9Ch] [rbp-ECh] BYREF
  int v44; // [rsp+A0h] [rbp-E8h] BYREF
  int v45; // [rsp+A4h] [rbp-E4h] BYREF
  HRESULT v46; // [rsp+A8h] [rbp-E0h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-D0h]
  __int64 *v48; // [rsp+C8h] [rbp-C0h]
  __int128 v49; // [rsp+D0h] [rbp-B8h]
  void **v50; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v51; // [rsp+F8h] [rbp-90h]
  __int64 *v52; // [rsp+108h] [rbp-80h]
  void ***v53; // [rsp+128h] [rbp-60h]
  void **v54; // [rsp+130h] [rbp-58h] BYREF
  __int128 v55; // [rsp+138h] [rbp-50h]
  void ***v56; // [rsp+168h] [rbp-20h]
  unsigned __int16 *v57; // [rsp+1A8h] [rbp+20h] BYREF

  v57 = a4;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( (v11[68] & 8) != 0 && v11[65] >= 6u )
  {
    v12 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v12 = 0;
LABEL_9:
  v23 = 0;
  v24 = 51;
  v25 = v12;
  v26 = "CWatcherFactory::RegisterLocalChangeWatcher";
  v27 = 0;
  if ( !a2 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 53;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v24) = 53;
  v23 = 0;
  if ( !v57 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 54;
    v33 = -2147024809;
    throw (long *)&v33;
  }
  LOWORD(v24) = 54;
  v23 = 0;
  if ( !a5 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 55;
    v34 = -2147024809;
    throw (long *)&v34;
  }
  LOWORD(v24) = 55;
  v23 = 0;
  v13 = a6;
  if ( !*a6 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 56;
    v35 = -2147024809;
    throw (long *)&v35;
  }
  v23 = 0;
  LOWORD(v24) = 56;
  CWatcherFactory::EnsureSearchIndexOnExpandedLocalPath(this, v57, a8);
  TokenInformation = 1;
  ReturnLength = 0;
  v14 = 34;
  v36 = 34;
  if ( !*a7 )
    v14 = 98;
  v36 = v14;
  if ( !GetTokenInformation(*v13, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    HIWORD(v24) = 83;
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    throw (long *)&LastFailureAsHRESULT;
  }
  v23 = 0;
  LOWORD(v24) = 83;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids, TokenInformation);
  }
  ppv = 0;
  v15 = CoCreateInstance(&CLSID_SyncRootManager, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &ppv);
  v23 = v15;
  if ( v15 < 0 )
  {
    HIWORD(v24) = 90;
    v39 = v15;
    throw (long *)&v39;
  }
  LOWORD(v24) = 90;
  v28 = 0;
  v16 = CoCreateInstance(&CLSID_StorageProviderInfo, 0, 1u, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v28);
  v23 = v16;
  if ( v16 < 0 )
  {
    HIWORD(v24) = 94;
    v40 = v16;
    throw (long *)&v40;
  }
  LOWORD(v24) = 94;
  v17 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v28 + 32LL))(v28, L"WorkFolders");
  v23 = v17;
  if ( v17 < 0 )
  {
    HIWORD(v24) = 96;
    v41 = v17;
    throw (long *)&v41;
  }
  LOWORD(v24) = 96;
  v18 = (*(__int64 (**)(LPVOID, const wchar_t *, ...))(*(_QWORD *)v28 + 72LL))(
          v28,
          L"@%systemroot%\\system32\\WorkfoldersControl.dll,-1");
  v23 = v18;
  if ( v18 < 0 )
  {
    HIWORD(v24) = 103;
    v42 = v18;
    throw (long *)&v42;
  }
  LOWORD(v24) = 103;
  v19 = (*(__int64 (**)(LPVOID, const wchar_t *, ...))(*(_QWORD *)v28 + 96LL))(
          v28,
          L"%systemroot%\\system32\\WorkfoldersControl.dll,-1");
  v23 = v19;
  if ( v19 < 0 )
  {
    HIWORD(v24) = 105;
    v43 = v19;
    throw (long *)&v43;
  }
  LOWORD(v24) = 105;
  v20 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)v28 + 176LL))(v28, 4095, v14);
  v23 = v20;
  if ( v20 < 0 )
  {
    HIWORD(v24) = 108;
    v44 = v20;
    throw (long *)&v44;
  }
  LOWORD(v24) = 108;
  v21 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 120LL))(ppv, v28);
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        14,
        WPP_0c56b6059df7331eccde46e15be22fba_Traceguids,
        (unsigned int)v21);
    }
  }
  else if ( (*(unsigned int (__fastcall **)(LPVOID, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)ppv + 144LL))(
              ppv,
              L"WorkFolders",
              v57) == -2147024891 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids, v57);
    }
    v23 = -2134375643;
    HIWORD(v24) = 125;
    v45 = -2134375643;
    throw (long *)&v45;
  }
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v28);
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppv);
  v31 = 0;
  v22 = CoCreateInstance(
          &GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9,
          0,
          1u,
          &GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d,
          &v31);
  v23 = v22;
  if ( v22 < 0 )
  {
    HIWORD(v24) = 147;
    v46 = v22;
    throw (long *)&v46;
  }
  LOWORD(v24) = 147;
  *(_QWORD *)&v49 = &v31;
  *((_QWORD *)&v49 + 1) = a3;
  v54 = &std::_Func_impl_no_alloc<_lambda_284c59efe11c027c3f6d01d0513a86ba_,long,>::`vftable';
  v55 = v49;
  v56 = &v54;
  CChangeTrackerHelper::CallChangeTrackerWithRetry(&v54);
  *(_QWORD *)&v47 = &v31;
  *((_QWORD *)&v47 + 1) = &v57;
  v48 = &a5;
  v50 = &std::_Func_impl_no_alloc<_lambda_67b4112495765de174c68ba358699944_,long,>::`vftable';
  v51 = v47;
  v52 = &a5;
  v53 = &v50;
  CChangeTrackerHelper::CallChangeTrackerWithRetry(&v50);
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v31);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v23);
}

```

## disassembly

```asm
0x18002f440  mov     [rsp+arg_0], rbx
0x18002f445  mov     [rsp+arg_10], r12
0x18002f44a  mov     [rsp+arg_18], r9
0x18002f44f  push    r13
0x18002f451  push    r14
0x18002f453  push    r15
0x18002f455  sub     rsp, 170h
0x18002f45c  mov     r12, r8
0x18002f45f  mov     r14, rdx
0x18002f462  mov     r15, rcx
0x18002f465  lea     r13, WPP_GLOBAL_Control
0x18002f46c  mov     rax, cs:WPP_GLOBAL_Control
0x18002f473  cmp     rax, r13
0x18002f476  jz      short loc_18002F4A0
0x18002f478  test    byte ptr [rax+44h], 8
0x18002f47c  jz      short loc_18002F4B2
0x18002f47e  cmp     byte ptr [rax+41h], 6
0x18002f482  jb      short loc_18002F4A0
0x18002f484  mov     edx, 0Bh
0x18002f489  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x18002f490  mov     rcx, [rax+38h]
0x18002f494  call    WPP_SF_
0x18002f499  mov     rax, cs:WPP_GLOBAL_Control
0x18002f4a0  test    byte ptr [rax+44h], 8
0x18002f4a4  jz      short loc_18002F4B2
0x18002f4a6  cmp     byte ptr [rax+41h], 6
0x18002f4aa  jb      short loc_18002F4B2
0x18002f4ac  mov     al, 1
0x18002f4ae  xor     ebx, ebx
0x18002f4b0  jmp     short loc_18002F4B6
0x18002f4b2  xor     ebx, ebx
0x18002f4b4  mov     al, bl
0x18002f4b6  mov     [rsp+188h+var_158], ebx
0x18002f4ba  mov     [rsp+188h+var_154], 33h ; '3'
0x18002f4c2  mov     [rsp+188h+var_150], al
0x18002f4c6  lea     rax, aCwatcherfactor_8; "CWatcherFactory::RegisterLocalChangeWat"...
0x18002f4cd  mov     [rsp+188h+var_148], rax
0x18002f4d2  mov     [rsp+188h+var_140], rbx
0x18002f4d7  mov     eax, [rsp+188h+var_158]
0x18002f4db  mov     [rsp+188h+var_158], eax
0x18002f4df  mov     ecx, 35h ; '5'
0x18002f4e4  test    r14, r14
0x18002f4e7  jz      loc_18002F98D
0x18002f4ed  mov     [rsp+188h+var_158], ebx
0x18002f4f1  mov     word ptr [rsp+188h+var_154], cx
0x18002f4f6  mov     [rsp+188h+var_158], ebx
0x18002f4fa  mov     rdx, [rsp+188h+arg_18]; unsigned __int16 *
0x18002f502  mov     ecx, 36h ; '6'
0x18002f507  test    rdx, rdx
0x18002f50a  jz      loc_18002F9B1
0x18002f510  mov     [rsp+188h+var_158], ebx
0x18002f514  mov     word ptr [rsp+188h+var_154], cx
0x18002f519  mov     [rsp+188h+var_158], ebx
0x18002f51d  mov     ecx, 37h ; '7'
0x18002f522  cmp     [rsp+188h+arg_20], rbx
0x18002f52a  jz      loc_18002F9D5
0x18002f530  mov     [rsp+188h+var_158], ebx
0x18002f534  mov     word ptr [rsp+188h+var_154], cx
0x18002f539  mov     [rsp+188h+var_158], ebx
0x18002f53d  mov     r14, [rsp+188h+arg_28]
0x18002f545  mov     ecx, 38h ; '8'
0x18002f54a  cmp     [r14], rbx
0x18002f54d  jz      loc_18002F9F9
0x18002f553  mov     [rsp+188h+var_158], ebx
0x18002f557  mov     word ptr [rsp+188h+var_154], cx
0x18002f55c  mov     r8, [rsp+188h+arg_38]; bool *
0x18002f564  mov     rcx, r15; this
0x18002f567  call    ?EnsureSearchIndexOnExpandedLocalPath@CWatcherFactory@@AEAAXPEBGAEA_N@Z; CWatcherFactory::EnsureSearchIndexOnExpandedLocalPath(ushort const *,bool &)
0x18002f56c  nop
0x18002f56d  mov     [rsp+188h+TokenInformation], 1
0x18002f575  mov     [rsp+188h+var_104], ebx
0x18002f57c  mov     r15d, 22h ; '"'
0x18002f582  mov     [rsp+188h+var_108], r15d
0x18002f58a  lea     ecx, [r15+40h]
0x18002f58e  mov     rax, [rsp+188h+arg_30]
0x18002f596  cmp     [rax], ebx
0x18002f598  cmovz   r15d, ecx
0x18002f59c  mov     [rsp+188h+var_108], r15d
0x18002f5a4  mov     eax, [rsp+188h+var_158]
0x18002f5a8  mov     [rsp+188h+var_158], eax
0x18002f5ac  lea     rax, [rsp+188h+var_104]
0x18002f5b4  mov     [rsp+188h+ReturnLength], rax; ReturnLength
0x18002f5b9  lea     r9d, [rcx-5Eh]; TokenInformationLength
0x18002f5bd  lea     r8, [rsp+188h+TokenInformation]; TokenInformation
0x18002f5c2  lea     edx, [rcx-50h]; TokenInformationClass
0x18002f5c5  mov     rcx, [r14]; TokenHandle
0x18002f5c8  call    cs:__imp_GetTokenInformation
0x18002f5ce  test    eax, eax
0x18002f5d0  jz      loc_18002FA1D
0x18002f5d6  mov     [rsp+188h+var_158], ebx
0x18002f5da  mov     ecx, 53h ; 'S'
0x18002f5df  mov     word ptr [rsp+188h+var_154], cx
0x18002f5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5eb  cmp     rcx, r13
0x18002f5ee  jz      short loc_18002F616
0x18002f5f0  test    byte ptr [rcx+44h], 8
0x18002f5f4  jz      short loc_18002F616
0x18002f5f6  cmp     byte ptr [rcx+41h], 4
0x18002f5fa  jb      short loc_18002F616
0x18002f5fc  mov     edx, 0Ch
0x18002f601  mov     r9d, [rsp+188h+TokenInformation]
0x18002f606  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x18002f60d  mov     rcx, [rcx+38h]
0x18002f611  call    WPP_SF_d
0x18002f616  mov     [rsp+188h+ppv], rbx
0x18002f61b  lea     rax, [rsp+188h+ppv]
0x18002f620  mov     [rsp+188h+ReturnLength], rax; ppv
0x18002f625  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18002f62c  xor     edx, edx; pUnkOuter
0x18002f62e  lea     r8d, [rdx+1]; dwClsContext
0x18002f632  lea     rcx, CLSID_SyncRootManager; rclsid
0x18002f639  call    cs:__imp_CoCreateInstance
0x18002f63f  mov     [rsp+188h+var_158], eax
0x18002f643  mov     [rsp+188h+var_158], eax
0x18002f647  mov     ecx, 5Ah ; 'Z'
0x18002f64c  test    eax, eax
0x18002f64e  js      loc_18002FA4C
0x18002f654  mov     word ptr [rsp+188h+var_154], cx
0x18002f659  mov     [rsp+188h+var_138], rbx
0x18002f65e  lea     rax, [rsp+188h+var_138]
0x18002f663  mov     [rsp+188h+ReturnLength], rax; ppv
0x18002f668  lea     r9, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86; riid
0x18002f66f  xor     edx, edx; pUnkOuter
0x18002f671  lea     r8d, [rdx+1]; dwClsContext
0x18002f675  lea     rcx, CLSID_StorageProviderInfo; rclsid
0x18002f67c  call    cs:__imp_CoCreateInstance
0x18002f682  mov     [rsp+188h+var_158], eax
0x18002f686  mov     [rsp+188h+var_158], eax
0x18002f68a  mov     ecx, 5Eh ; '^'
0x18002f68f  test    eax, eax
0x18002f691  js      loc_18002FA6D
0x18002f697  mov     word ptr [rsp+188h+var_154], cx
0x18002f69c  mov     rcx, [rsp+188h+var_138]
0x18002f6a1  mov     rax, [rcx]
0x18002f6a4  lea     rdx, aWorkfolders; "WorkFolders"
0x18002f6ab  mov     rax, [rax+20h]
0x18002f6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6b4  mov     [rsp+188h+var_158], eax
0x18002f6b8  mov     [rsp+188h+var_158], eax
0x18002f6bc  mov     ecx, 60h ; '`'
0x18002f6c1  test    eax, eax
0x18002f6c3  js      loc_18002FA8D
0x18002f6c9  mov     word ptr [rsp+188h+var_154], cx
0x18002f6ce  mov     rcx, [rsp+188h+var_138]
0x18002f6d3  mov     rax, [rcx]
0x18002f6d6  lea     rdx, aSystemrootSyst_0; "@%systemroot%\\system32\\WorkfoldersCon"...
0x18002f6dd  mov     rax, [rax+48h]
0x18002f6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6e6  mov     [rsp+188h+var_158], eax
0x18002f6ea  mov     [rsp+188h+var_158], eax
0x18002f6ee  mov     ecx, 67h ; 'g'
0x18002f6f3  test    eax, eax
0x18002f6f5  js      loc_18002FAAD
0x18002f6fb  mov     word ptr [rsp+188h+var_154], cx
0x18002f700  mov     rcx, [rsp+188h+var_138]
0x18002f705  mov     rax, [rcx]
0x18002f708  lea     rdx, aSystemrootSyst; "%systemroot%\\system32\\WorkfoldersCont"...
0x18002f70f  mov     rax, [rax+60h]
0x18002f713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f718  mov     [rsp+188h+var_158], eax
0x18002f71c  mov     [rsp+188h+var_158], eax
0x18002f720  mov     ecx, 69h ; 'i'
0x18002f725  test    eax, eax
0x18002f727  js      loc_18002FACD
0x18002f72d  mov     word ptr [rsp+188h+var_154], cx
0x18002f732  mov     rcx, [rsp+188h+var_138]
0x18002f737  mov     rax, [rcx]
0x18002f73a  mov     r8d, r15d
0x18002f73d  mov     edx, 0FFFh
0x18002f742  mov     rax, [rax+0B0h]
0x18002f749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f74e  mov     [rsp+188h+var_158], eax
0x18002f752  mov     [rsp+188h+var_158], eax
0x18002f756  mov     ecx, 6Ch ; 'l'
0x18002f75b  test    eax, eax
0x18002f75d  js      loc_18002FAED
0x18002f763  mov     word ptr [rsp+188h+var_154], cx
0x18002f768  mov     rcx, [rsp+188h+ppv]
0x18002f76d  mov     rax, [rcx]
0x18002f770  mov     rdx, [rsp+188h+var_138]
0x18002f775  mov     rax, [rax+78h]
0x18002f779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f77e  test    eax, eax
0x18002f780  js      short loc_18002F7B2
0x18002f782  mov     rcx, [rsp+188h+ppv]
0x18002f787  mov     rax, [rcx]
0x18002f78a  mov     r8, [rsp+188h+arg_18]
0x18002f792  lea     rdx, aWorkfolders; "WorkFolders"
0x18002f799  mov     rax, [rax+90h]
0x18002f7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a5  cmp     eax, 80070005h
0x18002f7aa  jz      loc_18002FB0D
0x18002f7b0  jmp     short loc_18002F7E3
0x18002f7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7b9  cmp     rcx, r13
0x18002f7bc  jz      short loc_18002F7E3
0x18002f7be  test    byte ptr [rcx+44h], 8
0x18002f7c2  jz      short loc_18002F7E3
0x18002f7c4  cmp     byte ptr [rcx+41h], 3
0x18002f7c8  jb      short loc_18002F7E3
0x18002f7ca  mov     edx, 0Eh
0x18002f7cf  mov     r9d, eax
0x18002f7d2  lea     r8, WPP_0c56b6059df7331eccde46e15be22fba_Traceguids
0x18002f7d9  mov     rcx, [rcx+38h]
0x18002f7dd  call    WPP_SF_d
0x18002f7e2  nop
0x18002f7e3  lea     rcx, [rsp+188h+var_138]
0x18002f7e8  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18002f7ed  nop
0x18002f7ee  lea     rcx, [rsp+188h+ppv]
0x18002f7f3  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18002f7f8  mov     [rsp+188h+var_120], rbx
0x18002f7fd  lea     rax, [rsp+188h+var_120]
0x18002f802  mov     [rsp+188h+ReturnLength], rax; ppv
0x18002f807  lea     r9, _GUID_5c4c1c61_6779_4c4b_9c8a_da2653ce628d; riid
0x18002f80e  xor     edx, edx; pUnkOuter
0x18002f810  lea     r8d, [rdx+1]; dwClsContext
0x18002f814  lea     rcx, _GUID_69f31c37_09e1_433b_aecb_ebc83e4065d9; rclsid
0x18002f81b  call    cs:__imp_CoCreateInstance
0x18002f821  mov     [rsp+188h+var_158], eax
0x18002f825  mov     [rsp+188h+var_158], eax
0x18002f829  mov     ecx, 93h
0x18002f82e  test    eax, eax
0x18002f830  js      loc_18002FB79
0x18002f836  mov     word ptr [rsp+188h+var_154], cx
0x18002f83b  lea     rax, [rsp+188h+var_58]
0x18002f843  mov     [rsp+188h+arg_8], rax
0x18002f84b  lea     rax, [rsp+188h+var_120]
0x18002f850  mov     qword ptr [rsp+188h+var_B8], rax
0x18002f858  mov     qword ptr [rsp+188h+var_B8+8], r12
0x18002f860  mov     [rsp+188h+var_20], rbx
0x18002f868  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_284c59efe11c027c3f6d01d0513a86ba_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_284c59efe11c027c3f6d01d0513a86ba_,long,>::`vftable'
0x18002f86f  mov     [rsp+188h+var_58], rax
0x18002f877  movups  xmm0, [rsp+188h+var_B8]
0x18002f87f  movdqu  [rsp+188h+var_50], xmm0
0x18002f888  lea     rax, [rsp+188h+var_58]
0x18002f890  mov     [rsp+188h+var_20], rax
0x18002f898  lea     rcx, [rsp+188h+var_58]
0x18002f8a0  call    ?CallChangeTrackerWithRetry@CChangeTrackerHelper@@SAXV?$function@$$A6AJXZ@std@@@Z; CChangeTrackerHelper::CallChangeTrackerWithRetry(std::function<long (void)>)
0x18002f8a5  lea     rax, [rsp+188h+var_98]
0x18002f8ad  mov     [rsp+188h+arg_8], rax
0x18002f8b5  lea     rax, [rsp+188h+var_120]
0x18002f8ba  mov     qword ptr [rsp+188h+var_D0], rax
0x18002f8c2  lea     rax, [rsp+188h+arg_18]
0x18002f8ca  mov     qword ptr [rsp+188h+var_D0+8], rax
0x18002f8d2  lea     rax, [rsp+188h+arg_20]
0x18002f8da  mov     [rsp+188h+var_C0], rax
0x18002f8e2  mov     [rsp+188h+var_60], rbx
0x18002f8ea  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_67b4112495765de174c68ba358699944_@@J$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_67b4112495765de174c68ba358699944_,long,>::`vftable'
0x18002f8f1  mov     [rsp+188h+var_98], rax
0x18002f8f9  movups  xmm0, [rsp+188h+var_D0]
0x18002f901  movups  [rsp+188h+var_90], xmm0
0x18002f909  movsd   xmm1, [rsp+188h+var_C0]
0x18002f912  movsd   [rsp+188h+var_80], xmm1
0x18002f91b  lea     rax, [rsp+188h+var_98]
0x18002f923  mov     [rsp+188h+var_60], rax
0x18002f92b  lea     rcx, [rsp+188h+var_98]
0x18002f933  call    ?CallChangeTrackerWithRetry@CChangeTrackerHelper@@SAXV?$function@$$A6AJXZ@std@@@Z; CChangeTrackerHelper::CallChangeTrackerWithRetry(std::function<long (void)>)
0x18002f938  nop
0x18002f939  lea     rcx, [rsp+188h+var_120]
0x18002f93e  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x18002f943  nop
0x18002f944  jmp     short loc_18002F948
0x18002f946  xor     ebx, ebx
0x18002f948  mov     eax, [rsp+188h+var_158]
0x18002f94c  test    eax, eax
0x18002f94e  js      loc_18002FB9A
0x18002f954  jmp     short loc_18002F969
0x18002f956  jmp     short loc_18002F946
0x18002f958  jmp     short loc_18002F946
0x18002f95a  jmp     loc_18002FBBB
0x18002f95f  jmp     loc_18002FBBB
0x18002f964  jmp     loc_18002FBBB
0x18002f969  lea     rcx, [rsp+188h+var_158]; this
0x18002f96e  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18002f973  lea     r11, [rsp+188h+var_18]
0x18002f97b  mov     rbx, [r11+20h]
0x18002f97f  mov     r12, [r11+30h]
0x18002f983  mov     rsp, r11
0x18002f986  pop     r15
0x18002f988  pop     r14
0x18002f98a  pop     r13
0x18002f98c  retn
0x18002f98d  mov     eax, 80070057h
0x18002f992  mov     [rsp+188h+var_158], eax
0x18002f996  mov     word ptr [rsp+188h+var_154+2], cx
0x18002f99b  mov     [rsp+188h+pExceptionObject], eax
0x18002f99f  lea     rdx, _TI1J; pThrowInfo
0x18002f9a6  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18002f9ab  call    _CxxThrowException_0
0x18002f9b1  mov     eax, 80070057h
0x18002f9b6  mov     [rsp+188h+var_158], eax
0x18002f9ba  mov     word ptr [rsp+188h+var_154+2], cx
0x18002f9bf  mov     [rsp+188h+var_114], eax
0x18002f9c3  lea     rdx, _TI1J; pThrowInfo
0x18002f9ca  lea     rcx, [rsp+188h+var_114]; pExceptionObject
0x18002f9cf  call    _CxxThrowException_0
0x18002f9d5  mov     eax, 80070057h
0x18002f9da  mov     [rsp+188h+var_158], eax
0x18002f9de  mov     word ptr [rsp+188h+var_154+2], cx
  ... truncated ...
```

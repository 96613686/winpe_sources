# OpenSessionKey(IAudioSessionInfo *,HKEY__ *,HKEY__ * *)

- ea: `0x180012fb0`
- end: `0x1800136ba`
- name: `?OpenSessionKey@@YAJPEAUIAudioSessionInfo@@PEAUHKEY__@@PEAPEAU2@@Z`
- size: `1802`
- prototype: `__int64 __fastcall(struct IAudioSessionInfo *, HKEY, HKEY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180012aa0`

## callees

- `0x18000a384`
- `0x1800101ac`
- `0x180011f18`
- `0x180012844`
- `0x1800128d4`
- `0x180012fb0`
- `0x180014290`
- `0x1800146b0`
- `0x180015394`
- `0x1800232a0`
- `0x18002c73c`
- `0x180031e00`
- `0x180031eb0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013591`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001319a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001319a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800133dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013690`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001349f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013530`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001349f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013530`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013390`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013390`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001334e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800133c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001344b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800135c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001360d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013206`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001334e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800133c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001344b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800135c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001360d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013674`
- `RPCRT4!RpcRevertToSelf` at `0x180013040`
- `RPCRT4!RpcRevertToSelf` at `0x1800130a7`
- `RPCRT4!RpcRevertToSelf` at `0x1800133e9`
- `RPCRT4!RpcRevertToSelf` at `0x1800135ee`
- `RPCRT4!RpcRevertToSelf` at `0x18001369c`
- `RPCRT4!RpcRevertToSelf` at `0x180013040`
- `RPCRT4!RpcRevertToSelf` at `0x1800130a7`
- `RPCRT4!RpcRevertToSelf` at `0x1800133e9`
- `RPCRT4!RpcRevertToSelf` at `0x1800135ee`
- `RPCRT4!RpcRevertToSelf` at `0x18001369c`
- `RPCRT4!RpcImpersonateClient` at `0x180012fda`
- `RPCRT4!RpcImpersonateClient` at `0x180012fda`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall OpenSessionKey(struct IAudioSessionInfo *a1, HKEY a2, HKEY *a3)
{
  HKEY v3; // r13
  RPC_STATUS v5; // eax
  RPC_STATUS *v6; // rdi
  unsigned int v7; // ebx
  int v9; // eax
  void *v10; // rcx
  bool v11; // zf
  unsigned int v12; // r14d
  __int64 v13; // r12
  __int64 v14; // rax
  LPCWSTR v15; // rbx
  unsigned int v16; // eax
  DWORD i; // esi
  const unsigned __int16 *v18; // rbx
  int v19; // eax
  HKEY v20; // rbx
  LSTATUS v21; // eax
  unsigned int v22; // esi
  void *v23; // rcx
  HKEY v24; // rcx
  unsigned int ValueW; // eax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  char *v28; // rsi
  unsigned int v29; // eax
  HKEY v30; // rcx
  ATL::CAtlException *v31; // rbx
  ATL::CAtlException *v32; // rbx
  ATL::CAtlException *v33; // rbx
  int phkResult; // [rsp+20h] [rbp-B8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-B8h]
  int phkResultb; // [rsp+20h] [rbp-B8h]
  unsigned int phkResultc; // [rsp+20h] [rbp-B8h]
  unsigned int phkResultd; // [rsp+20h] [rbp-B8h]
  HKEY hKey; // [rsp+40h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-90h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-88h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-80h] BYREF
  int v43; // [rsp+5Ch] [rbp-7Ch]
  unsigned int v44; // [rsp+60h] [rbp-78h]
  char *v45; // [rsp+68h] [rbp-70h] BYREF
  RPC_STATUS *v46; // [rsp+70h] [rbp-68h]
  char v47; // [rsp+78h] [rbp-60h]
  ATL::CAtlException *v48; // [rsp+80h] [rbp-58h] BYREF
  ATL::CAtlException *v49; // [rsp+88h] [rbp-50h] BYREF
  ATL::CAtlException *v50; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  RPC_STATUS v54; // [rsp+F8h] [rbp+20h] BYREF

  v3 = a2;
  *a3 = 0;
  v5 = RpcImpersonateClient(0);
  v54 = v5;
  v6 = &v54;
  v46 = &v54;
  v47 = 1;
  if ( v5 && v5 != 1725 )
  {
    if ( v5 > 0 )
      v7 = (unsigned __int16)v5 | 0x80070000;
    else
      v7 = v5;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)v7,
      phkResult);
    if ( !v54 )
      RpcRevertToSelf();
    return v7;
  }
  pv = 0;
  v9 = (*(__int64 (__fastcall **)(struct IAudioSessionInfo *, LPVOID *))(*(_QWORD *)a1 + 144LL))(a1, &pv);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v9,
      phkResult);
    v10 = pv;
    if ( !pv )
    {
LABEL_12:
      v11 = v54 == 0;
      goto LABEL_13;
    }
LABEL_11:
    CoTaskMemFree(v10);
    goto LABEL_12;
  }
  try
  {
    v44 = 0;
    v44 = ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Hash(pv);
  }
  catch ( ATL::CAtlException *v48 )
  {
    v31 = v48;
    if ( *(_DWORD *)v48 == -1073741571 )
      _o__resetstkoflw();
    v43 = *(_DWORD *)v31;
    v7 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v43,
        phkResult);
      v10 = pv;
      if ( !pv )
        goto LABEL_12;
      goto LABEL_11;
    }
    v3 = a2;
    v6 = v46;
  }
  v12 = 0;
  v43 = 0;
  v13 = -1;
  while ( 1 )
  {
    v14 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
    try
    {
      lpSubKey = (LPCWSTR)(v14 + 24);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &lpSubKey,
        L"%x_%d",
        v44,
        v12);
    }
    catch ( ATL::CAtlException *v49 )
    {
      v32 = v49;
      if ( *(_DWORD *)v49 == -1073741571 )
        _o__resetstkoflw();
      LODWORD(v45) = *(_DWORD *)v32;
      v7 = (unsigned int)v45;
      if ( (int)v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v45,
          phkResult);
        ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
LABEL_23:
        if ( pv )
          CoTaskMemFree(pv);
        v11 = *v46 == 0;
LABEL_13:
        if ( v11 )
        {
          RpcRevertToSelf();
          return v7;
        }
        return v7;
      }
      v13 = -1;
      v3 = a2;
      v6 = v46;
      v12 = v43;
    }
    hKey = 0;
    v15 = lpSubKey;
    v16 = RegOpenKeyExW(v3, lpSubKey, 0, 0x2001Fu, &hKey);
    if ( v16 == 2 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
      for ( i = 0; ; ++i )
      {
        pcbData = i;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
        try
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            &lpSubKey,
            L"%x_%d",
            v44,
            i);
        }
        catch ( ATL::CAtlException *v50 )
        {
          v33 = v50;
          if ( *(_DWORD *)v50 == -1073741571 )
            _o__resetstkoflw();
          LODWORD(v45) = *(_DWORD *)v33;
          v7 = (unsigned int)v45;
          if ( (int)v45 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x13E,
              (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
              (const char *)(unsigned int)v45,
              phkResulta);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
            goto LABEL_23;
          }
          v13 = -1;
          v3 = a2;
          v6 = v46;
          i = pcbData;
        }
        hKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v18 = lpSubKey;
        if ( RegOpenKeyExW(v3, lpSubKey, 0, 0x20019u, &hKey) )
          break;
        if ( hKey )
          RegCloseKey(hKey);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
      }
      if ( hKey )
        RegCloseKey(hKey);
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v19 = CreateLowRightsRegistryKey(v3, v18, 0x2001F, &hKey);
      v7 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14B,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v19,
          phkResulta);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_58;
      }
      do
        ++v13;
      while ( *((_WORD *)pv + v13) );
      v20 = hKey;
      v21 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)pv, 2 * v13 + 2);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14F,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)(unsigned int)v21,
          phkResultb);
        if ( v20 )
          RegCloseKey(v20);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
        if ( pv )
          CoTaskMemFree(pv);
        if ( !*v6 )
          RpcRevertToSelf();
        return v22;
      }
      *a3 = v20;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
      v23 = pv;
      if ( !pv )
      {
LABEL_75:
        if ( !*v6 )
          RpcRevertToSelf();
        return 0;
      }
LABEL_74:
      CoTaskMemFree(v23);
      goto LABEL_75;
    }
    if ( v16 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x125,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
             (const char *)v16,
             phkResulta);
      v24 = hKey;
      if ( !hKey )
      {
LABEL_58:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
        if ( pv )
          CoTaskMemFree(pv);
        v11 = *v6 == 0;
        goto LABEL_13;
      }
LABEL_57:
      RegCloseKey(v24);
      goto LABEL_58;
    }
    pcbData = 0;
    ValueW = RegGetValueW(hKey, 0, 0, 2u, 0, 0, &pcbData);
    if ( ValueW )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x128,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
             (const char *)ValueW,
             phkResultc);
      v24 = hKey;
      if ( !hKey )
        goto LABEL_58;
      goto LABEL_57;
    }
    v26 = ((unsigned __int64)pcbData >> 1) + 1;
    v27 = 2 * v26;
    if ( !is_mul_ok(v26, 2u) )
      v27 = -1;
    v28 = (char *)operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
    v45 = v28;
    if ( !v28 )
      break;
    v29 = RegGetValueW(hKey, 0, 0, 2u, 0, v28, &pcbData);
    if ( v29 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x12D,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
             (const char *)v29,
             phkResultd);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v45);
      v24 = hKey;
      if ( !hKey )
        goto LABEL_58;
      goto LABEL_57;
    }
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)pv, -1, (PCNZWCH)v28, -1) == 2 )
    {
      v30 = hKey;
      hKey = 0;
      *a3 = v30;
      operator delete(v28, (const struct std::nothrow_t *)2);
      if ( hKey )
        RegCloseKey(hKey);
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
      v23 = pv;
      if ( !pv )
        goto LABEL_75;
      goto LABEL_74;
    }
    operator delete(v28, (const struct std::nothrow_t *)2);
    if ( hKey )
      RegCloseKey(hKey);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
    v43 = ++v12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12B,
    (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
    (const char *)0x8007000ELL,
    phkResultc);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v45);
  if ( hKey )
    RegCloseKey(hKey);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
  if ( pv )
    CoTaskMemFree(pv);
  if ( !*v6 )
    RpcRevertToSelf();
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012fb0  mov     [rsp+arg_10], r8
0x180012fb5  mov     [rsp+arg_8], rdx
0x180012fba  push    rbx
0x180012fbb  push    rsi
0x180012fbc  push    rdi
0x180012fbd  push    r12
0x180012fbf  push    r13
0x180012fc1  push    r14
0x180012fc3  push    r15
0x180012fc5  sub     rsp, 0A0h
0x180012fcc  mov     r13, rdx
0x180012fcf  mov     rbx, rcx
0x180012fd2  xor     r15d, r15d
0x180012fd5  mov     [r8], r15
0x180012fd8  xor     ecx, ecx; BindingHandle
0x180012fda  call    cs:__imp_RpcImpersonateClient
0x180012fe0  mov     [rsp+0D8h+arg_18], eax
0x180012fe7  lea     rdi, [rsp+0D8h+arg_18]
0x180012fef  mov     [rsp+0D8h+var_68], rdi
0x180012ff4  mov     [rsp+0D8h+var_60], 1
0x180012ff9  test    eax, eax
0x180012ffb  jz      short loc_18001304D
0x180012ffd  cmp     eax, 6BDh
0x180013002  jz      short loc_18001304D
0x180013004  test    eax, eax
0x180013006  jg      short loc_18001300C
0x180013008  mov     ebx, eax
0x18001300a  jmp     short loc_180013015
0x18001300c  movzx   ebx, ax
0x18001300f  or      ebx, 80070000h
0x180013015  test    ebx, ebx
0x180013017  jns     short loc_18001303C
0x180013019  mov     rcx, [rsp+0D8h]; this
0x180013021  mov     r9d, ebx; char *
0x180013024  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18001302b  mov     edx, 10Bh; void *
0x180013030  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013035  mov     eax, [rsp+0D8h+arg_18]
0x18001303c  test    eax, eax
0x18001303e  jnz     short loc_180013046
0x180013040  call    cs:__imp_RpcRevertToSelf
0x180013046  mov     eax, ebx
0x180013048  jmp     loc_1800136A7
0x18001304d  mov     [rsp+0D8h+pv], r15
0x180013052  mov     rax, [rbx]
0x180013055  lea     rdx, [rsp+0D8h+pv]
0x18001305a  mov     rcx, rbx
0x18001305d  mov     rax, [rax+90h]
0x180013064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013069  mov     ebx, eax
0x18001306b  test    eax, eax
0x18001306d  jns     short loc_1800130B4
0x18001306f  mov     rcx, [rsp+0D8h]; this
0x180013077  mov     r9d, eax; char *
0x18001307a  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180013081  mov     edx, 10Eh; void *
0x180013086  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001308b  nop
0x18001308c  mov     rcx, [rsp+0D8h+pv]; pv
0x180013091  test    rcx, rcx
0x180013094  jz      short loc_18001309D
0x180013096  call    cs:__imp_CoTaskMemFree
0x18001309c  nop
0x18001309d  cmp     [rsp+0D8h+arg_18], 0
0x1800130a5  jnz     short loc_180013046
0x1800130a7  call    cs:__imp_RpcRevertToSelf
0x1800130ad  mov     eax, ebx
0x1800130af  jmp     loc_1800136A7
0x1800130b4  mov     dword ptr [rsp+0D8h+var_7C+4], r15d
0x1800130b9  mov     rcx, [rsp+0D8h+pv]
0x1800130be  call    ?Hash@?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@SAKPEBG@Z; ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Hash(ushort const *)
0x1800130c3  mov     dword ptr [rsp+0D8h+var_7C+4], eax
0x1800130c7  jmp     short loc_18001310A
0x1800130c9  mov     ebx, dword ptr [rsp+0D8h+var_7C]
0x1800130cd  test    ebx, ebx
0x1800130cf  jns     short loc_1800130FA
0x1800130d1  mov     rcx, [rsp+0D8h]; this
0x1800130d9  mov     r9d, ebx; char *
0x1800130dc  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800130e3  mov     edx, 116h; void *
0x1800130e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130ed  nop
0x1800130ee  mov     rcx, [rsp+0D8h+pv]
0x1800130f3  test    rcx, rcx
0x1800130f6  jz      short loc_18001309D
0x1800130f8  jmp     short loc_180013096
0x1800130fa  xor     r15d, r15d
0x1800130fd  mov     r13, [rsp+0D8h+arg_8]
0x180013105  mov     rdi, [rsp+0D8h+var_68]
0x18001310a  mov     r14d, r15d
0x18001310d  mov     dword ptr [rsp+0D8h+var_7C], r15d
0x180013112  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180013119  nop     dword ptr [rax+00000000h]
0x180013120  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013127  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001312e  mov     rax, [rax+18h]
0x180013132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013137  add     rax, 18h
0x18001313b  mov     [rsp+0D8h+lpSubKey], rax
0x180013140  mov     r9d, r14d
0x180013143  mov     r8d, dword ptr [rsp+0D8h+var_7C+4]
0x180013148  lea     rdx, aXD; "%x_%d"
0x18001314f  lea     rcx, [rsp+0D8h+lpSubKey]
0x180013154  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013159  nop
0x18001315a  jmp     short loc_1800131CA
0x18001315c  mov     ebx, dword ptr [rsp+0D8h+var_70]
0x180013160  test    ebx, ebx
0x180013162  jns     short loc_1800131AE
0x180013164  mov     rcx, [rsp+0D8h]; this
0x18001316c  mov     r9d, ebx; char *
0x18001316f  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180013176  mov     edx, 11Fh; void *
0x18001317b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013180  nop
0x180013181  mov     rcx, [rsp+0D8h+lpSubKey]
0x180013186  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001318a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001318f  nop
0x180013190  mov     rcx, [rsp+0D8h+pv]; pv
0x180013195  test    rcx, rcx
0x180013198  jz      short loc_1800131A1
0x18001319a  call    cs:__imp_CoTaskMemFree
0x1800131a0  nop
0x1800131a1  mov     rcx, [rsp+0D8h+var_68]
0x1800131a6  cmp     dword ptr [rcx], 0
0x1800131a9  jmp     loc_1800130A5
0x1800131ae  xor     r15d, r15d
0x1800131b1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800131b8  mov     r13, [rsp+0D8h+arg_8]
0x1800131c0  mov     rdi, [rsp+0D8h+var_68]
0x1800131c5  mov     r14d, dword ptr [rsp+0D8h+var_7C]
0x1800131ca  mov     [rsp+0D8h+hKey], r15
0x1800131cf  lea     rax, [rsp+0D8h+hKey]
0x1800131d4  mov     [rsp+0D8h+phkResult], rax; unsigned int
0x1800131d9  mov     r9d, 2001Fh; samDesired
0x1800131df  xor     r8d, r8d; ulOptions
0x1800131e2  mov     rbx, [rsp+0D8h+lpSubKey]
0x1800131e7  mov     rdx, rbx; lpSubKey
0x1800131ea  mov     rcx, r13; hKey
0x1800131ed  call    cs:__imp_RegOpenKeyExW
0x1800131f3  cmp     eax, 2
0x1800131f6  jnz     loc_18001341F
0x1800131fc  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180013201  test    rcx, rcx
0x180013204  jz      short loc_18001320D
0x180013206  call    cs:__imp_RegCloseKey
0x18001320c  nop
0x18001320d  lea     rcx, [rsp+0D8h+lpSubKey]
0x180013212  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013217  mov     esi, r15d
0x18001321a  mov     [rsp+0D8h+var_80], esi
0x18001321e  lea     rcx, [rsp+0D8h+lpSubKey]
0x180013223  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013228  nop
0x180013229  mov     r9d, esi
0x18001322c  mov     r8d, dword ptr [rsp+0D8h+var_7C+4]
0x180013231  lea     rdx, aXD; "%x_%d"
0x180013238  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001323d  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180013242  nop
0x180013243  jmp     short loc_180013294
0x180013245  mov     ebx, dword ptr [rsp+0D8h+var_70]
0x180013249  test    ebx, ebx
0x18001324b  jns     short loc_180013279
0x18001324d  mov     rcx, [rsp+0D8h]; this
0x180013255  mov     r9d, ebx; char *
0x180013258  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x18001325f  mov     edx, 13Eh; void *
0x180013264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013269  nop
0x18001326a  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001326f  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180013274  jmp     loc_180013190
0x180013279  xor     r15d, r15d
0x18001327c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180013283  mov     r13, [rsp+0D8h+arg_8]
0x18001328b  mov     rdi, [rsp+0D8h+var_68]
0x180013290  mov     esi, [rsp+0D8h+var_80]
0x180013294  mov     [rsp+0D8h+hKey], r15
0x180013299  xor     edx, edx
0x18001329b  lea     rcx, [rsp+0D8h+hKey]
0x1800132a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800132a5  lea     rax, [rsp+0D8h+hKey]
0x1800132aa  mov     [rsp+0D8h+phkResult], rax; int
0x1800132af  mov     r9d, 20019h; samDesired
0x1800132b5  xor     r8d, r8d; ulOptions
0x1800132b8  mov     rbx, [rsp+0D8h+lpSubKey]
0x1800132bd  mov     rdx, rbx; lpSubKey
0x1800132c0  mov     rcx, r13; hKey
0x1800132c3  call    cs:__imp_RegOpenKeyExW
0x1800132c9  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800132ce  test    eax, eax
0x1800132d0  jnz     short loc_1800132EF
0x1800132d2  test    rcx, rcx
0x1800132d5  jz      short loc_1800132DE
0x1800132d7  call    cs:__imp_RegCloseKey
0x1800132dd  nop
0x1800132de  lea     rcx, [rsp+0D8h+lpSubKey]
0x1800132e3  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800132e8  inc     esi
0x1800132ea  jmp     loc_18001321A
0x1800132ef  test    rcx, rcx
0x1800132f2  jz      short loc_1800132FA
0x1800132f4  call    cs:__imp_RegCloseKey
0x1800132fa  mov     [rsp+0D8h+hKey], r15
0x1800132ff  xor     edx, edx
0x180013301  lea     rcx, [rsp+0D8h+hKey]
0x180013306  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001330b  lea     r9, [rsp+0D8h+hKey]; HKEY *
0x180013310  mov     r8d, 2001Fh; unsigned int
0x180013316  mov     rdx, rbx; unsigned __int16 *
0x180013319  mov     rcx, r13; HKEY
0x18001331c  call    ?CreateLowRightsRegistryKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateLowRightsRegistryKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180013321  mov     ebx, eax
0x180013323  test    eax, eax
0x180013325  jns     short loc_18001335A
0x180013327  mov     rcx, [rsp+0D8h]; this
0x18001332f  mov     r9d, eax; char *
0x180013332  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180013339  mov     edx, 14Bh; void *
0x18001333e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013343  nop
0x180013344  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180013349  test    rcx, rcx
0x18001334c  jz      short loc_180013355
0x18001334e  call    cs:__imp_RegCloseKey
0x180013354  nop
0x180013355  jmp     loc_180013452
0x18001335a  mov     rax, [rsp+0D8h+pv]
0x18001335f  lea     r12, [r12+1]
0x180013364  cmp     word ptr [rax+r12*2], 0
0x18001336a  jnz     short loc_18001335F
0x18001336c  lea     ecx, ds:2[r12*2]
0x180013374  mov     [rsp+0D8h+cbData], ecx; cbData
0x180013378  mov     [rsp+0D8h+phkResult], rax; int
0x18001337d  mov     r9d, 1; dwType
0x180013383  xor     r8d, r8d; Reserved
0x180013386  xor     edx, edx; lpValueName
0x180013388  mov     rbx, [rsp+0D8h+hKey]
0x18001338d  mov     rcx, rbx; hKey
0x180013390  call    cs:__imp_RegSetValueExW
0x180013396  mov     esi, eax
0x180013398  test    eax, eax
0x18001339a  jns     short loc_1800133F6
0x18001339c  mov     rcx, [rsp+0D8h]; this
0x1800133a4  mov     r9d, eax; char *
0x1800133a7  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x1800133ae  mov     edx, 14Fh; void *
0x1800133b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800133b8  nop
0x1800133b9  test    rbx, rbx
0x1800133bc  jz      short loc_1800133C8
0x1800133be  mov     rcx, rbx; hKey
0x1800133c1  call    cs:__imp_RegCloseKey
0x1800133c7  nop
0x1800133c8  lea     rcx, [rsp+0D8h+lpSubKey]
0x1800133cd  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800133d2  nop
0x1800133d3  mov     rcx, [rsp+0D8h+pv]; pv
0x1800133d8  test    rcx, rcx
0x1800133db  jz      short loc_1800133E4
0x1800133dd  call    cs:__imp_CoTaskMemFree
0x1800133e3  nop
0x1800133e4  cmp     dword ptr [rdi], 0
0x1800133e7  jnz     short loc_1800133EF
0x1800133e9  call    cs:__imp_RpcRevertToSelf
0x1800133ef  mov     eax, esi
0x1800133f1  jmp     loc_1800136A7
0x1800133f6  mov     rax, [rsp+0D8h+arg_10]
0x1800133fe  mov     [rax], rbx
0x180013401  lea     rcx, [rsp+0D8h+lpSubKey]
0x180013406  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001340b  nop
0x18001340c  mov     rcx, [rsp+0D8h+pv]
0x180013411  test    rcx, rcx
0x180013414  jnz     loc_1800135E2
0x18001341a  jmp     loc_1800135E9
0x18001341f  test    eax, eax
0x180013421  jz      short loc_180013476
0x180013423  mov     rcx, [rsp+0D8h]; this
0x18001342b  mov     r9d, eax; char *
0x18001342e  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180013435  mov     edx, 125h; void *
0x18001343a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001343f  mov     ebx, eax
0x180013441  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180013446  test    rcx, rcx
0x180013449  jz      short loc_180013452
0x18001344b  call    cs:__imp_RegCloseKey
0x180013451  nop
0x180013452  lea     rcx, [rsp+0D8h+lpSubKey]
0x180013457  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001345c  nop
0x18001345d  mov     rcx, [rsp+0D8h+pv]; pv
0x180013462  test    rcx, rcx
0x180013465  jz      short loc_18001346E
0x180013467  call    cs:__imp_CoTaskMemFree
0x18001346d  nop
0x18001346e  cmp     dword ptr [rdi], 0
  ... truncated ...
```

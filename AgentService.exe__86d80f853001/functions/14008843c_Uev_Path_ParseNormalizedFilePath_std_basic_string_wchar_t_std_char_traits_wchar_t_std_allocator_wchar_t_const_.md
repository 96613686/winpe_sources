# Uev::Path::ParseNormalizedFilePath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x14008843c`
- end: `0x140088d89`
- name: `?ParseNormalizedFilePath@Path@Uev@@IEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `2381`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14005db10`

## callees

- `0x1400039e0`
- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004a6c`
- `0x140004ab4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000c1cc`
- `0x14000c2b8`
- `0x14000c3a4`
- `0x14000c4c8`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d2d8`
- `0x14000d448`
- `0x14000d7b4`
- `0x14001a2a4`
- `0x14001b8b0`
- `0x14001b8c8`
- `0x140021a80`
- `0x140026898`
- `0x14005e444`
- `0x140087c2c`
- `0x140087d10`
- `0x140087e38`
- `0x140087f98`
- `0x14008843c`
- `0x140088d90`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140088731`
- `ADVAPI32!RegGetValueW` at `0x1400887a0`
- `ADVAPI32!RegGetValueW` at `0x140088731`
- `ADVAPI32!RegGetValueW` at `0x1400887a0`
- `ole32!CLSIDFromString` at `0x140088564`
- `ole32!CLSIDFromString` at `0x140088564`
- `SHELL32!SHGetKnownFolderPath` at `0x140088585`
- `SHELL32!SHGetKnownFolderPath` at `0x140088585`

## string_xrefs

- `0x140088c27`: `Attempting to use an invalid handle.`
- `0x140088bf6`: `Unable to get known folder path for GUID: `
- `0x140088b8c`: `Invalid normalized file path format (no closing } character found).`
- `0x140088d3b`: `Invalid normalized file path format (no closing % character found).`
- `0x140088b5b`: `Invalid normalized file path format (no root delimiter found).`
- `0x140088ca9`: `Unable to get registry value from `
- `0x140088cff`: `Unable to get registry value from `
- `0x140088c58`: `Invalid normalized file path format (no closing ] character found).`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Uev::Path::ParseNormalizedFilePath(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  __int64 v3; // r13
  unsigned __int64 v4; // rax
  unsigned __int16 *v5; // rcx
  int v6; // ecx
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  __int64 v9; // r15
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r14
  unsigned __int64 v13; // r8
  const OLECHAR *v14; // rcx
  __int64 v15; // r8
  unsigned __int64 v16; // rdx
  void **v17; // rdi
  __int64 v18; // rbx
  void *v19; // rcx
  __int64 v20; // rcx
  _QWORD *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  const WCHAR *v26; // r8
  const WCHAR *v27; // rdx
  unsigned int ValueW; // ebx
  __int64 v29; // r8
  void *pvData; // r12
  const WCHAR *v31; // r8
  const WCHAR *v32; // rdx
  unsigned int v33; // ebx
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  void **v36; // rdi
  __int64 v37; // rbx
  unsigned __int64 v38; // rdx
  void **v39; // rdi
  __int64 v40; // rbx
  unsigned __int64 v41; // rcx
  _QWORD *v42; // rdi
  __int64 v43; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v45; // r8
  __int64 fixed; // rbx
  unsigned __int64 v47; // r14
  void **v48; // rax
  __int64 v49; // rdx
  void **v50; // rcx
  _QWORD *v51; // rax
  _QWORD *v52; // rbx
  unsigned __int64 v53; // rax
  __int64 v54; // rax
  _QWORD *v55; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  PWSTR ppszPath; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v61; // [rsp+50h] [rbp-B0h]
  void *v62[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v63; // [rsp+68h] [rbp-98h]
  WCHAR v64[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  LPCOLESTR lpsz[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v69; // [rsp+B0h] [rbp-50h]
  LPCWSTR lpValue[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v71; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v72; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v74; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v75; // [rsp+F0h] [rbp-10h]
  __int128 v76; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+110h] [rbp+10h]
  CLSID pclsid; // [rsp+118h] [rbp+18h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR v81[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]
  _WORD Src[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v2 = a2;
  v3 = a1;
  v61 = a1;
  *(_OWORD *)v62 = 0;
  *(_QWORD *)&v63 = 0;
  *((_QWORD *)&v63 + 1) = 7;
  LOWORD(v62[0]) = 0;
  v4 = a2[3];
  if ( v4 <= 7 )
    v5 = (unsigned __int16 *)a2;
  else
    v5 = (unsigned __int16 *)*a2;
  v6 = *v5;
  if ( v6 == 37 )
  {
    v41 = a2[2];
    if ( v4 <= 7 )
      v42 = a2;
    else
      v42 = (_QWORD *)*a2;
    v9 = -1;
    if ( v41 <= 1
      || (v43 = (__int64)v42 + 2 * v41, trivial_2 = _std_find_trivial_2((char *)v42 + 2, v43, 37), trivial_2 == v43) )
    {
      v12 = -1;
    }
    else
    {
      v12 = (trivial_2 - (__int64)v42) >> 1;
    }
    if ( v12 == -1 )
    {
      std::wstring::wstring(lpsz, L"Invalid normalized file path format (no closing % character found).");
      Uev::ParseException::ParseException(pExceptionObject, lpsz);
      throw (Uev::ParseException *)pExceptionObject;
    }
    *(_OWORD *)v64 = 0;
    v65 = 0;
    v66 = 0;
    v45 = v2[2];
    if ( v45 >= v12 + 1 )
      v45 = v12 + 1;
    if ( v2[3] <= 7u )
      std::wstring::_Construct<1,wchar_t *>(v64, v2, v45);
    else
      std::wstring::_Construct<1,wchar_t *>(v64, *v2, v45);
    Uev::Common::ExpandWString(v64);
    v19 = v64;
    goto LABEL_88;
  }
  if ( v6 != 91 )
  {
    if ( v6 != 123 )
    {
      std::wstring::wstring(v64, L"Invalid normalized file path format (no root delimiter found).");
      Uev::ParseException::ParseException(pExceptionObject, v64);
      throw (Uev::ParseException *)pExceptionObject;
    }
    v7 = a2[2];
    if ( v4 <= 7 )
      v8 = a2;
    else
      v8 = (_QWORD *)*a2;
    v9 = -1;
    if ( !v7 || (v10 = (__int64)v8 + 2 * v7, v11 = _std_find_trivial_2(v8, v10, 125), v11 == v10) )
      v12 = -1;
    else
      v12 = (v11 - (__int64)v8) >> 1;
    if ( v12 == -1 )
    {
      std::wstring::wstring(v64, L"Invalid normalized file path format (no closing } character found).");
      Uev::ParseException::ParseException(pExceptionObject, v64);
      throw (Uev::ParseException *)pExceptionObject;
    }
    *(_OWORD *)lpsz = 0;
    v68 = 0;
    v69 = 0;
    v13 = v2[2];
    if ( v13 >= v12 + 1 )
      v13 = v12 + 1;
    if ( v2[3] <= 7u )
      std::wstring::_Construct<1,wchar_t *>(lpsz, v2, v13);
    else
      std::wstring::_Construct<1,wchar_t *>(lpsz, *v2, v13);
    pclsid = 0;
    v14 = (const OLECHAR *)lpsz;
    if ( v69 > 7 )
      v14 = lpsz[0];
    if ( CLSIDFromString(v14, &pclsid) < 0 )
    {
      std::operator+<wchar_t>(v64, L"Invalid known folder GUID: ", lpsz);
      Uev::UevException::UevException(pExceptionObject, v64);
      throw (Uev::UevException *)pExceptionObject;
    }
    ppszPath = 0;
    if ( SHGetKnownFolderPath(&pclsid, 0, 0, &ppszPath) < 0 )
    {
      std::operator+<wchar_t>(v64, L"Unable to get known folder path for GUID: ", lpsz);
      Uev::UevException::UevException(pExceptionObject, v64);
      throw (Uev::UevException *)pExceptionObject;
    }
    if ( !ppszPath )
    {
      std::wstring::wstring(v64, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v64);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    v16 = -1;
    do
      ++v16;
    while ( ppszPath[v16] );
    if ( v16 > *((_QWORD *)&v63 + 1) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v62, v16, v15, ppszPath);
    }
    else
    {
      v17 = v62;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v17 = (void **)v62[0];
      *(_QWORD *)&v63 = v16;
      v18 = 2 * v16;
      memmove_0(v17, ppszPath, 2 * v16);
      *(_WORD *)((char *)v17 + v18) = 0;
    }
    Uev::SmartHandle<wchar_t *,&private: static void Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>::~SmartHandle<wchar_t *,&private: static void Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>(&ppszPath);
    v19 = lpsz;
LABEL_88:
    std::wstring::_Tidy_deallocate(v19);
    goto LABEL_89;
  }
  v20 = a2[2];
  if ( v4 <= 7 )
    v21 = a2;
  else
    v21 = (_QWORD *)*a2;
  v9 = -1;
  if ( !v20 || (v22 = (__int64)v21 + 2 * v20, v23 = _std_find_trivial_2(v21, v22, 93), v23 == v22) )
    v12 = -1;
  else
    v12 = (v23 - (__int64)v21) >> 1;
  if ( v12 == -1 )
  {
    std::wstring::wstring(v64, L"Invalid normalized file path format (no closing ] character found).");
    Uev::ParseException::ParseException(pExceptionObject, v64);
    throw (Uev::ParseException *)pExceptionObject;
  }
  *(_OWORD *)lpSubKey = 0;
  v74 = 0;
  v75 = 7;
  LOWORD(lpSubKey[0]) = 0;
  *(_OWORD *)lpValue = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(lpValue[0]) = 0;
  *(_OWORD *)v64 = 0;
  v65 = 0;
  v66 = 0;
  v24 = v2[2];
  if ( !v24 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  if ( v24 - 1 >= (unsigned __int64)(v12 - 1) )
    v24 = v12;
  v25 = v24 - 1;
  if ( v2[3] <= 7u )
    std::wstring::_Construct<1,wchar_t *>(v64, (char *)v2 + 2, v25);
  else
    std::wstring::_Construct<1,wchar_t *>(v64, *v2 + 2LL, v25);
  Uev::Path::ParsePathAndName(v64, lpSubKey, lpValue);
  std::wstring::_Tidy_deallocate(v64);
  pcbData = 520;
  v26 = (const WCHAR *)lpValue;
  if ( v72 > 7 )
    v26 = lpValue[0];
  v27 = (const WCHAR *)lpSubKey;
  if ( v75 > 7 )
    v27 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_CURRENT_USER, v27, v26, 2u, 0, Src, &pcbData);
  if ( ValueW == 234 )
  {
    pvData = operator new[](saturated_mul((unsigned __int64)pcbData >> 1, 2u));
    *(_QWORD *)&pclsid.Data1 = pvData;
    v31 = (const WCHAR *)lpValue;
    if ( v72 > 7 )
      v31 = lpValue[0];
    v32 = (const WCHAR *)lpSubKey;
    if ( v75 > 7 )
      v32 = lpSubKey[0];
    v33 = RegGetValueW(HKEY_CURRENT_USER, v32, v31, 2u, 0, pvData, &pcbData);
    LODWORD(ppszPath) = v33;
    v35 = -1;
    do
      ++v35;
    while ( *((_WORD *)pvData + v35) );
    if ( v35 > *((_QWORD *)&v63 + 1) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v62, v35, v34, pvData);
    }
    else
    {
      v36 = v62;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v36 = (void **)v62[0];
      *(_QWORD *)&v63 = v35;
      v37 = 2 * v35;
      memmove_0(v36, pvData, 2 * v35);
      *(_WORD *)((char *)v36 + v37) = 0;
      v33 = (unsigned int)ppszPath;
    }
    if ( v33 )
    {
      v57 = std::wstring::substr(v2, v64, 1, v12 - 1);
      std::operator+<wchar_t>(lpsz, L"Unable to get registry value from ", v57);
      boost::filesystem::path::~path((boost::filesystem::path *)v64);
      Uev::SystemException::SystemException(pExceptionObject, lpsz, v33);
      throw (Uev::SystemException *)pExceptionObject;
    }
    operator delete(pvData);
  }
  else
  {
    if ( ValueW )
    {
      v58 = std::wstring::substr(v2, v64, 1, v12 - 1);
      std::operator+<wchar_t>(lpsz, L"Unable to get registry value from ", v58);
      boost::filesystem::path::~path((boost::filesystem::path *)v64);
      Uev::SystemException::SystemException(pExceptionObject, lpsz, ValueW);
      throw (Uev::SystemException *)pExceptionObject;
    }
    v38 = -1;
    do
      ++v38;
    while ( Src[v38] );
    if ( v38 > *((_QWORD *)&v63 + 1) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v62, v38, v29, Src);
    }
    else
    {
      v39 = v62;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v39 = (void **)v62[0];
      *(_QWORD *)&v63 = v38;
      v40 = 2 * v38;
      memmove_0(v39, Src, 2 * v38);
      *(_WORD *)((char *)v39 + v40) = 0;
    }
  }
  std::wstring::_Tidy_deallocate(lpValue);
  std::wstring::_Tidy_deallocate(lpSubKey);
  v3 = v61;
LABEL_89:
  fixed = Uev::Path::FixSlashes(pExceptionObject);
  if ( v62 != (void **)fixed )
  {
    std::wstring::_Tidy_deallocate(v62);
    *(_OWORD *)v62 = *(_OWORD *)fixed;
    v63 = *(_OWORD *)(fixed + 16);
    *(_QWORD *)(fixed + 16) = 0;
    *(_QWORD *)(fixed + 24) = 7;
    *(_WORD *)fixed = 0;
  }
  std::wstring::_Tidy_deallocate(pExceptionObject);
  v47 = v12 + 1;
  v48 = v62;
  if ( *((_QWORD *)&v63 + 1) > 7u )
    v48 = (void **)v62[0];
  v49 = v63;
  if ( *((_WORD *)v48 + v63 - 1) != 92 )
  {
    v50 = v62;
    if ( (unsigned __int64)v63 >= *((_QWORD *)&v63 + 1) )
    {
      std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(v62);
    }
    else
    {
      *(_QWORD *)&v63 = v63 + 1;
      if ( *((_QWORD *)&v63 + 1) > 7u )
        v50 = (void **)v62[0];
      *(_DWORD *)((char *)v50 + 2 * v49) = 92;
    }
  }
  if ( v2[3] <= 7u )
    v51 = v2;
  else
    v51 = (_QWORD *)*v2;
  if ( *((_WORD *)v51 + v47) == 92 )
    ++v47;
  *(_OWORD *)v81 = 0;
  v82 = 0;
  v83 = 0;
  v52 = v2 + 2;
  v53 = v2[2];
  if ( v53 < v47 )
    std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
  v54 = v53 - v47;
  if ( v54 != -1 )
    v9 = v54;
  if ( v2[3] <= 7u )
    v55 = v2;
  else
    v55 = (_QWORD *)*v2;
  std::wstring::_Construct<1,wchar_t *>(v81, (char *)v55 + 2 * v47, v9);
  v76 = 0;
  v77 = 0;
  v78 = 7;
  LOWORD(v76) = 0;
  Uev::Common::ExpandWString(v81);
  std::wstring::_Append<wchar_t>(v62);
  Uev::Path::ParseFilePath(v3, v62);
  std::wstring::operator=(v3 + 16, v2);
  if ( !*(_QWORD *)(v3 + 128) )
  {
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    if ( *((_WORD *)v2 + *v52 - 1) != 92 )
      std::wstring::_Append<wchar_t>((void *)(v3 + 16));
  }
  std::wstring::_Tidy_deallocate(&v76);
  std::wstring::_Tidy_deallocate(v81);
  return std::wstring::_Tidy_deallocate(v62);
}

```

## disassembly

```asm
0x14008843c  mov     [rsp-8+arg_10], rbx
0x140088441  push    rbp
0x140088442  push    rsi
0x140088443  push    rdi
0x140088444  push    r12
0x140088446  push    r13
0x140088448  push    r14
0x14008844a  push    r15
0x14008844c  lea     rbp, [rsp-2E0h]
0x140088454  sub     rsp, 3E0h
0x14008845b  mov     rax, cs:__security_cookie
0x140088462  xor     rax, rsp
0x140088465  mov     [rbp+310h+var_40], rax
0x14008846c  mov     rsi, rdx
0x14008846f  mov     r13, rcx
0x140088472  mov     [rsp+410h+var_3C0], rcx
0x140088477  xor     r12d, r12d
0x14008847a  xorps   xmm0, xmm0
0x14008847d  movups  xmmword ptr [rsp+410h+var_3B8], xmm0
0x140088482  mov     qword ptr [rsp+410h+var_3A8], r12
0x140088487  mov     qword ptr [rsp+410h+var_3A8+8], 7
0x140088490  mov     word ptr [rsp+410h+var_3B8], r12w
0x140088496  mov     rax, [rdx+18h]
0x14008849a  cmp     rax, 7
0x14008849e  jbe     short loc_1400884A5
0x1400884a0  mov     rcx, [rdx]
0x1400884a3  jmp     short loc_1400884A8
0x1400884a5  mov     rcx, rsi
0x1400884a8  movzx   ecx, word ptr [rcx]
0x1400884ab  mov     edx, 25h ; '%'
0x1400884b0  cmp     ecx, edx
0x1400884b2  jz      loc_14008889B
0x1400884b8  cmp     ecx, 5Bh ; '['
0x1400884bb  jz      loc_140088603
0x1400884c1  cmp     ecx, 7Bh ; '{'
0x1400884c4  jnz     loc_140088B5B
0x1400884ca  mov     rcx, [rsi+10h]
0x1400884ce  cmp     rax, 7
0x1400884d2  jbe     short loc_1400884D9
0x1400884d4  mov     rdi, [rsi]
0x1400884d7  jmp     short loc_1400884DC
0x1400884d9  mov     rdi, rsi
0x1400884dc  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400884e0  test    rcx, rcx
0x1400884e3  jz      short loc_140088508
0x1400884e5  lea     rbx, [rdi+rcx*2]
0x1400884e9  lea     r8d, [r15+7Eh]
0x1400884ed  mov     rdx, rbx
0x1400884f0  mov     rcx, rdi
0x1400884f3  call    __std_find_trivial_2
0x1400884f8  mov     r14, rax
0x1400884fb  cmp     rax, rbx
0x1400884fe  jz      short loc_140088508
0x140088500  sub     r14, rdi
0x140088503  sar     r14, 1
0x140088506  jmp     short loc_14008850B
0x140088508  mov     r14, r15
0x14008850b  cmp     r14, r15
0x14008850e  jz      loc_140088B8C
0x140088514  xorps   xmm0, xmm0
0x140088517  movups  xmmword ptr [rbp+310h+lpsz], xmm0
0x14008851b  mov     [rbp+310h+var_368], r12
0x14008851f  mov     [rbp+310h+var_360], r12
0x140088523  lea     rax, [r14+1]
0x140088527  mov     r8, [rsi+10h]
0x14008852b  cmp     r8, rax
0x14008852e  cmovnb  r8, rax
0x140088532  cmp     qword ptr [rsi+18h], 7
0x140088537  jbe     short loc_14008853E
0x140088539  mov     rdx, [rsi]
0x14008853c  jmp     short loc_140088541
0x14008853e  mov     rdx, rsi
0x140088541  lea     rcx, [rbp+310h+lpsz]
0x140088545  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14008854a  nop
0x14008854b  xorps   xmm0, xmm0
0x14008854e  movups  xmmword ptr [rbp+310h+pclsid.Data1], xmm0
0x140088552  lea     rcx, [rbp+310h+lpsz]
0x140088556  cmp     [rbp+310h+var_360], 7
0x14008855b  cmova   rcx, [rbp+310h+lpsz]; lpsz
0x140088560  lea     rdx, [rbp+310h+pclsid]; pclsid
0x140088564  call    cs:__imp_CLSIDFromString
0x14008856a  test    eax, eax
0x14008856c  js      loc_140088BBD
0x140088572  mov     [rsp+410h+ppszPath], r12
0x140088577  lea     r9, [rsp+410h+ppszPath]; ppszPath
0x14008857c  xor     r8d, r8d; hToken
0x14008857f  xor     edx, edx; dwFlags
0x140088581  lea     rcx, [rbp+310h+pclsid]; rfid
0x140088585  call    cs:__imp_SHGetKnownFolderPath
0x14008858b  test    eax, eax
0x14008858d  js      loc_140088BF2
0x140088593  mov     r9, [rsp+410h+ppszPath]
0x140088598  test    r9, r9
0x14008859b  jz      loc_140088C27
0x1400885a1  mov     rdx, r15
0x1400885a4  inc     rdx
0x1400885a7  cmp     [r9+rdx*2], r12w
0x1400885ac  jnz     short loc_1400885A4
0x1400885ae  cmp     rdx, qword ptr [rsp+410h+var_3A8+8]
0x1400885b3  ja      short loc_1400885E4
0x1400885b5  lea     rdi, [rsp+410h+var_3B8]
0x1400885ba  cmp     qword ptr [rsp+410h+var_3A8+8], 7
0x1400885c0  cmova   rdi, [rsp+410h+var_3B8]
0x1400885c6  mov     qword ptr [rsp+410h+var_3A8], rdx
0x1400885cb  lea     rbx, [rdx+rdx]
0x1400885cf  mov     r8, rbx; Size
0x1400885d2  mov     rdx, r9; Src
0x1400885d5  mov     rcx, rdi; void *
0x1400885d8  call    memmove_0
0x1400885dd  mov     [rbx+rdi], r12w
0x1400885e2  jmp     short loc_1400885EF
0x1400885e4  lea     rcx, [rsp+410h+var_3B8]
0x1400885e9  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400885ee  nop
0x1400885ef  lea     rcx, [rsp+410h+ppszPath]
0x1400885f4  call    ??1?$SmartHandle@PEA_W$1?CoTaskMemFreeWrapper@Path@Uev@@CAXPEA_W@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<wchar_t *,&Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>::~SmartHandle<wchar_t *,&Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>(void)
0x1400885f9  nop
0x1400885fa  lea     rcx, [rbp+310h+lpsz]
0x1400885fe  jmp     loc_140088952
0x140088603  mov     rcx, [rsi+10h]
0x140088607  cmp     rax, 7
0x14008860b  jbe     short loc_140088612
0x14008860d  mov     rdi, [rsi]
0x140088610  jmp     short loc_140088615
0x140088612  mov     rdi, rsi
0x140088615  or      r15, 0FFFFFFFFFFFFFFFFh
0x140088619  test    rcx, rcx
0x14008861c  jz      short loc_140088641
0x14008861e  lea     rbx, [rdi+rcx*2]
0x140088622  lea     r8d, [r15+5Eh]
0x140088626  mov     rdx, rbx
0x140088629  mov     rcx, rdi
0x14008862c  call    __std_find_trivial_2
0x140088631  mov     r14, rax
0x140088634  cmp     rax, rbx
0x140088637  jz      short loc_140088641
0x140088639  sub     r14, rdi
0x14008863c  sar     r14, 1
0x14008863f  jmp     short loc_140088644
0x140088641  mov     r14, r15
0x140088644  cmp     r14, r15
0x140088647  jz      loc_140088C58
0x14008864d  xorps   xmm0, xmm0
0x140088650  movups  xmmword ptr [rbp+310h+lpSubKey], xmm0
0x140088654  mov     [rbp+310h+var_328], r12
0x140088658  mov     [rbp+310h+var_320], 7
0x140088660  mov     word ptr [rbp+310h+lpSubKey], r12w
0x140088665  movups  xmmword ptr [rbp+310h+lpValue], xmm0
0x140088669  mov     [rbp+310h+var_348], r12
0x14008866d  mov     [rbp+310h+var_340], 7
0x140088675  mov     word ptr [rbp+310h+lpValue], r12w
0x14008867a  movups  xmmword ptr [rsp+410h+var_398], xmm0
0x14008867f  mov     [rbp+310h+var_388], r12
0x140088683  mov     [rbp+310h+var_380], r12
0x140088687  mov     rcx, [rsi+10h]
0x14008868b  cmp     rcx, 1
0x14008868f  jb      loc_140088C89
0x140088695  lea     r13, [r14-1]
0x140088699  lea     rax, [rcx-1]
0x14008869d  cmp     rax, r13
0x1400886a0  cmovnb  rcx, r14
0x1400886a4  lea     r8, [rcx-1]
0x1400886a8  cmp     qword ptr [rsi+18h], 7
0x1400886ad  jbe     short loc_1400886B4
0x1400886af  mov     rdx, [rsi]
0x1400886b2  jmp     short loc_1400886B7
0x1400886b4  mov     rdx, rsi
0x1400886b7  add     rdx, 2
0x1400886bb  lea     rcx, [rsp+410h+var_398]
0x1400886c0  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400886c5  nop
0x1400886c6  lea     r8, [rbp+310h+lpValue]
0x1400886ca  lea     rdx, [rbp+310h+lpSubKey]
0x1400886ce  lea     rcx, [rsp+410h+var_398]
0x1400886d3  call    ?ParsePathAndName@Path@Uev@@KAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@1_N@Z; Uev::Path::ParsePathAndName(std::wstring const &,std::wstring &,std::wstring &,bool)
0x1400886d8  nop
0x1400886d9  lea     rcx, [rsp+410h+var_398]
0x1400886de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400886e3  mov     [rsp+410h+var_3D0], 208h
0x1400886eb  lea     r8, [rbp+310h+lpValue]
0x1400886ef  cmp     [rbp+310h+var_340], 7
0x1400886f4  cmova   r8, [rbp+310h+lpValue]; lpValue
0x1400886f9  lea     rdx, [rbp+310h+lpSubKey]
0x1400886fd  cmp     [rbp+310h+var_320], 7
0x140088702  cmova   rdx, [rbp+310h+lpSubKey]; lpSubKey
0x140088707  lea     rax, [rsp+410h+var_3D0]
0x14008870c  mov     [rsp+410h+pcbData], rax; pcbData
0x140088711  lea     rax, [rbp+310h+Src]
0x140088718  mov     [rsp+410h+pvData], rax; pvData
0x14008871d  mov     [rsp+410h+pdwType], r12; pdwType
0x140088722  mov     edi, 2
0x140088727  mov     r9d, edi; dwFlags
0x14008872a  mov     rcx, 0FFFFFFFF80000001h; hkey
0x140088731  call    cs:__imp_RegGetValueW
0x140088737  mov     ebx, eax
0x140088739  cmp     eax, 0EAh
0x14008873e  jnz     loc_140088816
0x140088744  mov     ecx, [rsp+410h+var_3D0]
0x140088748  shr     rcx, 1
0x14008874b  mov     eax, edi
0x14008874d  mul     rcx
0x140088750  cmovb   rax, r15
0x140088754  mov     rcx, rax; unsigned __int64
0x140088757  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14008875c  mov     r12, rax
0x14008875f  mov     qword ptr [rbp+310h+pclsid.Data1], rax
0x140088763  lea     r8, [rbp+310h+lpValue]
0x140088767  cmp     [rbp+310h+var_340], 7
0x14008876c  cmova   r8, [rbp+310h+lpValue]; lpValue
0x140088771  lea     rdx, [rbp+310h+lpSubKey]
0x140088775  cmp     [rbp+310h+var_320], 7
0x14008877a  cmova   rdx, [rbp+310h+lpSubKey]; lpSubKey
0x14008877f  lea     rax, [rsp+410h+var_3D0]
0x140088784  mov     [rsp+410h+pcbData], rax; pcbData
0x140088789  mov     [rsp+410h+pvData], r12; pvData
0x14008878e  xor     edi, edi
0x140088790  mov     [rsp+410h+pdwType], rdi; pdwType
0x140088795  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14008879c  lea     r9d, [rdi+2]; dwFlags
0x1400887a0  call    cs:__imp_RegGetValueW
0x1400887a6  mov     ebx, eax
0x1400887a8  mov     dword ptr [rsp+410h+ppszPath], eax
0x1400887ac  mov     rdx, r15
0x1400887af  inc     rdx
0x1400887b2  cmp     [r12+rdx*2], di
0x1400887b7  jnz     short loc_1400887AF
0x1400887b9  cmp     rdx, qword ptr [rsp+410h+var_3A8+8]
0x1400887be  ja      short loc_1400887F4
0x1400887c0  lea     rdi, [rsp+410h+var_3B8]
0x1400887c5  cmp     qword ptr [rsp+410h+var_3A8+8], 7
0x1400887cb  cmova   rdi, [rsp+410h+var_3B8]
0x1400887d1  mov     qword ptr [rsp+410h+var_3A8], rdx
0x1400887d6  lea     rbx, [rdx+rdx]
0x1400887da  mov     r8, rbx; Size
0x1400887dd  mov     rdx, r12; Src
0x1400887e0  mov     rcx, rdi; void *
0x1400887e3  call    memmove_0
0x1400887e8  xor     eax, eax
0x1400887ea  mov     [rdi+rbx], ax
0x1400887ee  mov     ebx, dword ptr [rsp+410h+ppszPath]
0x1400887f2  jmp     short loc_140088801
0x1400887f4  mov     r9, r12
0x1400887f7  lea     rcx, [rsp+410h+var_3B8]
0x1400887fc  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140088801  test    ebx, ebx
0x140088803  jnz     loc_140088C8F
0x140088809  mov     rcx, r12; Block
0x14008880c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140088811  xor     r12d, r12d
0x140088814  jmp     short loc_14008887E
0x140088816  test    ebx, ebx
0x140088818  jnz     loc_140088CE5
0x14008881e  lea     rax, [rbp+310h+Src]
0x140088825  mov     rdx, r15
0x140088828  inc     rdx
0x14008882b  cmp     [rax+rdx*2], r12w
0x140088830  jnz     short loc_140088828
0x140088832  cmp     rdx, qword ptr [rsp+410h+var_3A8+8]
0x140088837  ja      short loc_14008886C
0x140088839  lea     rdi, [rsp+410h+var_3B8]
0x14008883e  cmp     qword ptr [rsp+410h+var_3A8+8], 7
0x140088844  cmova   rdi, [rsp+410h+var_3B8]
0x14008884a  mov     qword ptr [rsp+410h+var_3A8], rdx
0x14008884f  lea     rbx, [rdx+rdx]
0x140088853  mov     r8, rbx; Size
0x140088856  lea     rdx, [rbp+310h+Src]; Src
0x14008885d  mov     rcx, rdi; void *
0x140088860  call    memmove_0
0x140088865  mov     [rdi+rbx], r12w
0x14008886a  jmp     short loc_14008887E
0x14008886c  lea     r9, [rbp+310h+Src]
0x140088873  lea     rcx, [rsp+410h+var_3B8]
0x140088878  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14008887d  nop
0x14008887e  lea     rcx, [rbp+310h+lpValue]
0x140088882  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140088887  nop
0x140088888  lea     rcx, [rbp+310h+lpSubKey]
0x14008888c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140088891  mov     r13, [rsp+410h+var_3C0]
0x140088896  jmp     loc_140088957
0x14008889b  mov     rcx, [rsi+10h]
0x14008889f  cmp     rax, 7
0x1400888a3  jbe     short loc_1400888AA
0x1400888a5  mov     rdi, [rsi]
0x1400888a8  jmp     short loc_1400888AD
0x1400888aa  mov     rdi, rsi
0x1400888ad  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400888b1  cmp     rcx, 1
0x1400888b5  jbe     short loc_1400888DA
0x1400888b7  lea     rbx, [rdi+rcx*2]
0x1400888bb  mov     r8d, edx
0x1400888be  lea     rcx, [rdi+2]
0x1400888c2  mov     rdx, rbx
0x1400888c5  call    __std_find_trivial_2
0x1400888ca  mov     r14, rax
0x1400888cd  cmp     rax, rbx
0x1400888d0  jz      short loc_1400888DA
0x1400888d2  sub     r14, rdi
  ... truncated ...
```

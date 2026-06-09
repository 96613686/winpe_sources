# _lambda_d14cb1dae6af4e860105638303883acf_::operator()

- ea: `0x18001a3f4`
- end: `0x18001aba2`
- name: `_lambda_d14cb1dae6af4e860105638303883acf_::operator()`
- size: `1966`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a0250`

## callees

- `0x18000e6e0`
- `0x18001a3f4`
- `0x18001aba8`
- `0x180067050`
- `0x18007689c`
- `0x180076900`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a219c`
- `0x1800f0700`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ab8b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a8eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001a8eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aaaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ab96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a8b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a935`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a984`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa32`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a49e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a49e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001a462`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001a462`

## string_xrefs

- `0x18001a877`: `onecore\admin\appmodel\osim\src\deh\geolocation\geolocationextensionhandler.cpp`
- `0x18001a949`: `onecore\admin\appmodel\osim\src\deh\geolocation\geolocationextensionhandler.cpp`
- `0x18001a98f`: `onecore\admin\appmodel\osim\src\deh\geolocation\geolocationextensionhandler.cpp`
- `0x18001a9f3`: `onecore\admin\appmodel\osim\src\deh\geolocation\geolocationextensionhandler.cpp`
- `0x18001aa58`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001aa76`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001aa94`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001aabd`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001aae5`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001ab03`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001ab2b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001ab49`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x18001ab72`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_d14cb1dae6af4e860105638303883acf_::operator()(__int64 **a1)
{
  unsigned int LastError; // ebx
  LPWSTR v3; // rbx
  const char *v4; // r9
  __int64 v5; // rdx
  _WORD *v6; // rax
  __int64 v7; // r8
  signed int appended; // edi
  __int64 v9; // r9
  const WCHAR *v10; // rax
  __int64 v11; // r9
  const unsigned __int16 *v12; // rax
  unsigned int v13; // edi
  __int64 v14; // r9
  const WCHAR *v15; // rax
  __int64 v16; // rdx
  LPWSTR v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  const unsigned __int16 *v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // r9
  __int64 v23; // rdx
  _WORD *v24; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  const WCHAR *v27; // rax
  __int64 v28; // r8
  const unsigned __int16 *v29; // rax
  __int64 v30; // rdx
  unsigned __int64 v31; // rdx
  void *v32; // rcx
  bool v33; // zf
  char *FileW; // rax
  unsigned __int64 v36; // rdx
  void *v37; // rcx
  unsigned __int64 v38; // rdx
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  __int64 v43; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-49h]
  _QWORD v45[3]; // [rsp+40h] [rbp-29h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+58h] [rbp-11h] BYREF
  int v47; // [rsp+68h] [rbp-1h]
  LPVOID *p_pv; // [rsp+70h] [rbp+7h]
  PWSTR ppszPath; // [rsp+78h] [rbp+Fh] BYREF
  char v50; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPVOID pv; // [rsp+D8h] [rbp+6Fh] BYREF
  LPWSTR StringSid; // [rsp+E0h] [rbp+77h] BYREF
  char v54; // [rsp+E8h] [rbp+7Fh] BYREF

  StringSid = 0;
  *(_OWORD *)lpFileName = 0;
  v47 = 0;
  v45[1] = lpFileName;
  v45[0] = &Common::StringBufferBuilder::`vftable';
  v45[2] = lpFileName;
  pv = 0;
  p_pv = &pv;
  ppszPath = 0;
  v50 = 1;
  LastError = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x4000u, 0, &ppszPath);
  if ( v50 )
  {
    v41 = *p_pv;
    *p_pv = ppszPath;
    if ( v41 )
      CoTaskMemFree(v41);
  }
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\geolocation\\geolocationextensionhandler.cpp",
      (const char *)LastError,
      dwCreationDisposition);
    v39 = pv;
    pv = 0;
    if ( v39 )
      CoTaskMemFree(v39);
    if ( lpFileName[1] )
      operator delete((void *)lpFileName[1], v38);
    if ( StringSid )
      LocalFree(StringSid);
    return LastError;
  }
  v3 = StringSid;
  if ( StringSid )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v54);
    LocalFree(v3);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v54);
  }
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)(**a1 + 784), &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x59,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\geolocation\\geolocationextensionhandler.cpp",
                  v4);
    v42 = pv;
    pv = 0;
    if ( v42 )
      CoTaskMemFree(v42);
    goto LABEL_83;
  }
  if ( !pv )
  {
    appended = -2147024809;
LABEL_90:
    LODWORD(v7) = 0;
    goto LABEL_11;
  }
  v5 = 0x3FFFFFFF;
  v6 = pv;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = (0x3FFFFFFF - v5) & -(__int64)(v5 != 0);
  appended = v5 == 0 ? 0x80070057 : 0;
  if ( !v5 )
    goto LABEL_90;
LABEL_11:
  if ( appended < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_92;
  }
  appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v45, (const unsigned __int16 *)pv, v7);
  if ( appended < 0 )
  {
LABEL_92:
    v43 = 91;
LABEL_80:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v43,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\geolocation\\geolocationextensionhandler.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    v40 = pv;
    pv = 0;
    if ( v40 )
      CoTaskMemFree(v40);
    LastError = appended;
LABEL_83:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpFileName);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    return LastError;
  }
  v9 = 0x3FFFFFFF;
  v10 = L"\\";
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  appended = v9 == 0 ? 0x80070057 : 0;
  if ( !v9 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_94;
  }
  appended = Common::StringBuilder::AppendChars(
               (Common::StringBuilder *)v45,
               L"\\",
               v9 != 0 ? (0x3FFFFFFF - v9) & ((unsigned __int128)-(__int128)(unsigned __int64)v9 >> 64) : 0);
  if ( appended < 0 )
  {
LABEL_94:
    v43 = 92;
    goto LABEL_80;
  }
  v11 = 0x3FFFFFFF;
  v12 = L"\\Microsoft\\Windows\\LfSvc\\Geofence";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = v11 == 0 ? 0x80070057 : 0;
  if ( !v11 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v13,
      dwCreationDisposition);
    goto LABEL_96;
  }
  v13 = Common::StringBuilder::AppendChars(
          (Common::StringBuilder *)v45,
          L"\\Microsoft\\Windows\\LfSvc\\Geofence",
          v11 != 0 ? (0x3FFFFFFF - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64) : 0);
  if ( (v13 & 0x80000000) != 0 )
  {
LABEL_96:
    v30 = 93;
    goto LABEL_58;
  }
  v14 = 0x3FFFFFFF;
  v15 = L"\\";
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  appended = v14 == 0 ? 0x80070057 : 0;
  if ( !v14 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_98;
  }
  appended = Common::StringBuilder::AppendChars(
               (Common::StringBuilder *)v45,
               L"\\",
               v14 != 0 ? (0x3FFFFFFF - v14) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64) : 0);
  if ( appended < 0 )
  {
LABEL_98:
    v43 = 94;
    goto LABEL_80;
  }
  if ( !StringSid )
  {
    appended = -2147024809;
LABEL_100:
    LODWORD(v18) = 0;
    goto LABEL_33;
  }
  v16 = 0x3FFFFFFF;
  v17 = StringSid;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = (0x3FFFFFFF - v16) & -(__int64)(v16 != 0);
  appended = v16 == 0 ? 0x80070057 : 0;
  if ( !v16 )
    goto LABEL_100;
LABEL_33:
  if ( appended < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_102;
  }
  appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v45, StringSid, v18);
  if ( appended < 0 )
  {
LABEL_102:
    v43 = 95;
    goto LABEL_80;
  }
  v19 = 0x3FFFFFFF;
  v20 = L"_";
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  appended = v19 == 0 ? 0x80070057 : 0;
  if ( !v19 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_104;
  }
  appended = Common::StringBuilder::AppendChars(
               (Common::StringBuilder *)v45,
               L"_",
               v19 != 0 ? (0x3FFFFFFF - v19) & ((unsigned __int128)-(__int128)(unsigned __int64)v19 >> 64) : 0);
  if ( appended < 0 )
  {
LABEL_104:
    v43 = 96;
    goto LABEL_80;
  }
  v21 = **a1;
  v22 = *(const unsigned __int16 **)(v21 + 712);
  if ( !v22 )
  {
    appended = -2147024809;
LABEL_106:
    LODWORD(v25) = 0;
    goto LABEL_45;
  }
  v23 = 0x3FFFFFFF;
  v24 = *(_WORD **)(v21 + 712);
  do
  {
    if ( !*v24 )
      break;
    ++v24;
    --v23;
  }
  while ( v23 );
  v25 = (0x3FFFFFFF - v23) & -(__int64)(v23 != 0);
  appended = v23 == 0 ? 0x80070057 : 0;
  if ( !v23 )
    goto LABEL_106;
LABEL_45:
  if ( appended < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_108;
  }
  appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)v45, v22, v25);
  if ( appended < 0 )
  {
LABEL_108:
    v43 = 97;
    goto LABEL_80;
  }
  v26 = 0x3FFFFFFF;
  v27 = L"\\";
  do
  {
    if ( !*v27 )
      break;
    ++v27;
    --v26;
  }
  while ( v26 );
  appended = v26 == 0 ? 0x80070057 : 0;
  if ( !v26 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)appended,
      dwCreationDisposition);
    goto LABEL_110;
  }
  appended = Common::StringBuilder::AppendChars(
               (Common::StringBuilder *)v45,
               L"\\",
               v26 != 0 ? (0x3FFFFFFF - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64) : 0);
  if ( appended < 0 )
  {
LABEL_110:
    v43 = 98;
    goto LABEL_80;
  }
  v28 = 0x3FFFFFFF;
  v29 = L"Geofence.dat";
  do
  {
    if ( !*v29 )
      break;
    ++v29;
    --v28;
  }
  while ( v28 );
  v13 = v28 == 0 ? 0x80070057 : 0;
  if ( !v28 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)v13,
      dwCreationDisposition);
    goto LABEL_57;
  }
  v13 = Common::StringBuilder::AppendChars(
          (Common::StringBuilder *)v45,
          L"Geofence.dat",
          v28 != 0 ? 0x3FFFFFFF - v28 : 0);
  if ( (v13 & 0x80000000) != 0 )
  {
LABEL_57:
    v30 = 99;
LABEL_58:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\geolocation\\geolocationextensionhandler.cpp",
      (const char *)v13,
      dwCreationDisposition);
    v32 = pv;
    v33 = pv == 0;
    pv = 0;
    if ( !v33 )
      CoTaskMemFree(v32);
    if ( lpFileName[1] )
      operator delete((void *)lpFileName[1], v31);
    if ( StringSid )
      LocalFree(StringSid);
    return v13;
  }
  FileW = (char *)CreateFileW(lpFileName[1], 0x80u, 0, 0, 3u, 0x80u, 0);
  LOBYTE(v36) = FileW + 1 != 0;
  *(_BYTE *)a1[1] = v36;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  v37 = pv;
  pv = 0;
  if ( v37 )
    CoTaskMemFree(v37);
  if ( lpFileName[1] )
    operator delete((void *)lpFileName[1], v36);
  if ( StringSid )
    LocalFree(StringSid);
  return 0;
}

```

## disassembly

```asm
0x18001a3f4  push    rbp
0x18001a3f6  push    rbx
0x18001a3f7  push    rsi
0x18001a3f8  push    rdi
0x18001a3f9  push    r12
0x18001a3fb  push    r14
0x18001a3fd  push    r15
0x18001a3ff  lea     rbp, [rsp-27h]
0x18001a404  sub     rsp, 90h
0x18001a40b  mov     r14, rcx
0x18001a40e  xor     r15d, r15d
0x18001a411  mov     [rbp+57h+StringSid], r15
0x18001a415  xorps   xmm0, xmm0
0x18001a418  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18001a41c  mov     [rbp+57h+var_58], r15d
0x18001a420  lea     rax, [rbp+57h+lpFileName]
0x18001a424  mov     [rbp+57h+var_78], rax
0x18001a428  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18001a42f  mov     [rbp+57h+var_80], rax
0x18001a433  lea     rax, [rbp+57h+lpFileName]
0x18001a437  mov     [rbp+57h+var_70], rax
0x18001a43b  mov     [rbp+57h+pv], r15
0x18001a43f  lea     rax, [rbp+57h+pv]
0x18001a443  mov     [rbp+57h+var_50], rax
0x18001a447  mov     [rbp+57h+ppszPath], r15
0x18001a44b  mov     [rbp+57h+var_40], 1
0x18001a44f  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x18001a453  xor     r8d, r8d; hToken
0x18001a456  mov     edx, 4000h; dwFlags
0x18001a45b  lea     rcx, FOLDERID_ProgramData; rfid
0x18001a462  call    cs:__imp_SHGetKnownFolderPath
0x18001a468  mov     ebx, eax
0x18001a46a  cmp     [rbp+57h+var_40], r15b
0x18001a46e  jnz     loc_18001A9CD
0x18001a474  test    ebx, ebx
0x18001a476  js      loc_18001A942
0x18001a47c  mov     rbx, [rbp+57h+StringSid]
0x18001a480  test    rbx, rbx
0x18001a483  jnz     loc_18001AA26
0x18001a489  mov     [rbp+57h+StringSid], r15
0x18001a48d  mov     rax, [r14]
0x18001a490  mov     rcx, [rax]
0x18001a493  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001a497  mov     rcx, [rcx+310h]; Sid
0x18001a49e  call    cs:__imp_ConvertSidToStringSidW
0x18001a4a4  test    eax, eax
0x18001a4a6  jz      loc_18001A9EF
0x18001a4ac  mov     r9, [rbp+57h+pv]
0x18001a4b0  mov     ebx, 3FFFFFFFh
0x18001a4b5  test    r9, r9
0x18001a4b8  jz      loc_18001AA46
0x18001a4be  mov     edx, ebx
0x18001a4c0  mov     rax, r9
0x18001a4c3  cmp     [rax], r15w
0x18001a4c7  jz      short loc_18001A4D3
0x18001a4c9  add     rax, 2
0x18001a4cd  sub     rdx, 1
0x18001a4d1  jnz     short loc_18001A4C3
0x18001a4d3  mov     rax, rdx
0x18001a4d6  mov     rcx, rbx
0x18001a4d9  sub     rcx, rdx
0x18001a4dc  neg     rax
0x18001a4df  sbb     r8, r8
0x18001a4e2  and     r8, rcx; unsigned int
0x18001a4e5  mov     rax, rdx
0x18001a4e8  neg     rax
0x18001a4eb  sbb     edi, edi
0x18001a4ed  not     edi
0x18001a4ef  mov     esi, 80070057h
0x18001a4f4  and     edi, esi
0x18001a4f6  test    rdx, rdx
0x18001a4f9  jz      loc_18001AA4D
0x18001a4ff  mov     rcx, [rbp+5Fh]; this
0x18001a503  test    edi, edi
0x18001a505  js      loc_18001AA55
0x18001a50b  mov     rdx, r9; unsigned __int16 *
0x18001a50e  lea     rcx, [rbp+57h+var_80]; this
0x18001a512  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a517  mov     edi, eax
0x18001a519  test    eax, eax
0x18001a51b  js      loc_18001AA69
0x18001a521  mov     r9, rbx
0x18001a524  lea     r12, asc_1802323F0; "\\"
0x18001a52b  mov     rax, r12
0x18001a52e  cmp     [rax], r15w
0x18001a532  jz      short loc_18001A53E
0x18001a534  add     rax, 2
0x18001a538  sub     r9, 1
0x18001a53c  jnz     short loc_18001A52E
0x18001a53e  mov     rax, r9
0x18001a541  neg     rax
0x18001a544  sbb     edi, edi
0x18001a546  not     edi
0x18001a548  and     edi, esi
0x18001a54a  mov     r8, r9
0x18001a54d  mov     rax, r9
0x18001a550  mov     rcx, rbx
0x18001a553  sub     rcx, r9
0x18001a556  neg     rax
0x18001a559  sbb     rdx, rdx
0x18001a55c  and     rdx, rcx
0x18001a55f  neg     r8
0x18001a562  sbb     r8, r8
0x18001a565  and     r8, rdx; unsigned int
0x18001a568  mov     rcx, [rbp+5Fh]; this
0x18001a56c  test    r9, r9
0x18001a56f  jz      loc_18001AA73
0x18001a575  mov     rdx, r12; unsigned __int16 *
0x18001a578  lea     rcx, [rbp+57h+var_80]; this
0x18001a57c  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a581  mov     edi, eax
0x18001a583  test    eax, eax
0x18001a585  js      loc_18001AA87
0x18001a58b  mov     r9, rbx
0x18001a58e  lea     rax, aMicrosoftWindo_0; "\\Microsoft\\Windows\\LfSvc\\Geofence"
0x18001a595  cmp     [rax], r15w
0x18001a599  jz      short loc_18001A5A5
0x18001a59b  add     rax, 2
0x18001a59f  sub     r9, 1
0x18001a5a3  jnz     short loc_18001A595
0x18001a5a5  mov     rax, r9
0x18001a5a8  neg     rax
0x18001a5ab  sbb     edi, edi
0x18001a5ad  not     edi
0x18001a5af  and     edi, esi
0x18001a5b1  mov     r8, r9
0x18001a5b4  mov     rax, r9
0x18001a5b7  mov     rcx, rbx
0x18001a5ba  sub     rcx, r9
0x18001a5bd  neg     rax
0x18001a5c0  sbb     rdx, rdx
0x18001a5c3  and     rdx, rcx
0x18001a5c6  neg     r8
0x18001a5c9  sbb     r8, r8
0x18001a5cc  and     r8, rdx; unsigned int
0x18001a5cf  mov     rcx, [rbp+5Fh]; this
0x18001a5d3  test    r9, r9
0x18001a5d6  jz      loc_18001AA91
0x18001a5dc  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\LfSvc\\Geofence"
0x18001a5e3  lea     rcx, [rbp+57h+var_80]; this
0x18001a5e7  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a5ec  mov     edi, eax
0x18001a5ee  test    eax, eax
0x18001a5f0  js      loc_18001AAA5
0x18001a5f6  mov     r9, rbx
0x18001a5f9  mov     rax, r12
0x18001a5fc  cmp     [rax], r15w
0x18001a600  jz      short loc_18001A60C
0x18001a602  add     rax, 2
0x18001a606  sub     r9, 1
0x18001a60a  jnz     short loc_18001A5FC
0x18001a60c  mov     rax, r9
0x18001a60f  neg     rax
0x18001a612  sbb     edi, edi
0x18001a614  not     edi
0x18001a616  and     edi, esi
0x18001a618  mov     r8, r9
0x18001a61b  mov     rax, r9
0x18001a61e  mov     rcx, rbx
0x18001a621  sub     rcx, r9
0x18001a624  neg     rax
0x18001a627  sbb     rdx, rdx
0x18001a62a  and     rdx, rcx
0x18001a62d  neg     r8
0x18001a630  sbb     r8, r8
0x18001a633  and     r8, rdx; unsigned int
0x18001a636  mov     rcx, [rbp+5Fh]; this
0x18001a63a  test    r9, r9
0x18001a63d  jz      loc_18001AABA
0x18001a643  mov     rdx, r12; unsigned __int16 *
0x18001a646  lea     rcx, [rbp+57h+var_80]; this
0x18001a64a  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a64f  mov     edi, eax
0x18001a651  test    eax, eax
0x18001a653  js      loc_18001AACE
0x18001a659  mov     r9, [rbp+57h+StringSid]
0x18001a65d  test    r9, r9
0x18001a660  jz      loc_18001AAD8
0x18001a666  mov     rdx, rbx
0x18001a669  mov     rax, r9
0x18001a66c  cmp     [rax], r15w
0x18001a670  jz      short loc_18001A67C
0x18001a672  add     rax, 2
0x18001a676  sub     rdx, 1
0x18001a67a  jnz     short loc_18001A66C
0x18001a67c  mov     rax, rdx
0x18001a67f  mov     rcx, rbx
0x18001a682  sub     rcx, rdx
0x18001a685  neg     rax
0x18001a688  sbb     r8, r8
0x18001a68b  and     r8, rcx; unsigned int
0x18001a68e  mov     rax, rdx
0x18001a691  neg     rax
0x18001a694  sbb     edi, edi
0x18001a696  not     edi
0x18001a698  and     edi, esi
0x18001a69a  test    rdx, rdx
0x18001a69d  jz      loc_18001AADA
0x18001a6a3  mov     rcx, [rbp+5Fh]; this
0x18001a6a7  test    edi, edi
0x18001a6a9  js      loc_18001AAE2
0x18001a6af  mov     rdx, r9; unsigned __int16 *
0x18001a6b2  lea     rcx, [rbp+57h+var_80]; this
0x18001a6b6  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a6bb  mov     edi, eax
0x18001a6bd  test    eax, eax
0x18001a6bf  js      loc_18001AAF6
0x18001a6c5  mov     r9, rbx
0x18001a6c8  lea     rax, asc_1802321A4; "_"
0x18001a6cf  cmp     [rax], r15w
0x18001a6d3  jz      short loc_18001A6DF
0x18001a6d5  add     rax, 2
0x18001a6d9  sub     r9, 1
0x18001a6dd  jnz     short loc_18001A6CF
0x18001a6df  mov     rax, r9
0x18001a6e2  neg     rax
0x18001a6e5  sbb     edi, edi
0x18001a6e7  not     edi
0x18001a6e9  and     edi, esi
0x18001a6eb  mov     r8, r9
0x18001a6ee  mov     rax, r9
0x18001a6f1  mov     rcx, rbx
0x18001a6f4  sub     rcx, r9
0x18001a6f7  neg     rax
0x18001a6fa  sbb     rdx, rdx
0x18001a6fd  and     rdx, rcx
0x18001a700  neg     r8
0x18001a703  sbb     r8, r8
0x18001a706  and     r8, rdx; unsigned int
0x18001a709  mov     rcx, [rbp+5Fh]; this
0x18001a70d  test    r9, r9
0x18001a710  jz      loc_18001AB00
0x18001a716  lea     rdx, asc_1802321A4; "_"
0x18001a71d  lea     rcx, [rbp+57h+var_80]; this
0x18001a721  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a726  mov     edi, eax
0x18001a728  test    eax, eax
0x18001a72a  js      loc_18001AB14
0x18001a730  mov     rax, [r14]
0x18001a733  mov     rcx, [rax]
0x18001a736  mov     r9, [rcx+2C8h]
0x18001a73d  test    r9, r9
0x18001a740  jz      loc_18001AB1E
0x18001a746  mov     rdx, rbx
0x18001a749  mov     rax, r9
0x18001a74c  cmp     [rax], r15w
0x18001a750  jz      short loc_18001A75C
0x18001a752  add     rax, 2
0x18001a756  sub     rdx, 1
0x18001a75a  jnz     short loc_18001A74C
0x18001a75c  mov     rax, rdx
0x18001a75f  mov     rcx, rbx
0x18001a762  sub     rcx, rdx
0x18001a765  neg     rax
0x18001a768  sbb     r8, r8
0x18001a76b  and     r8, rcx; unsigned int
0x18001a76e  mov     rax, rdx
0x18001a771  neg     rax
0x18001a774  sbb     edi, edi
0x18001a776  not     edi
0x18001a778  and     edi, esi
0x18001a77a  test    rdx, rdx
0x18001a77d  jz      loc_18001AB20
0x18001a783  mov     rcx, [rbp+5Fh]; this
0x18001a787  test    edi, edi
0x18001a789  js      loc_18001AB28
0x18001a78f  mov     rdx, r9; unsigned __int16 *
0x18001a792  lea     rcx, [rbp+57h+var_80]; this
0x18001a796  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x18001a79b  mov     edi, eax
0x18001a79d  test    eax, eax
0x18001a79f  js      loc_18001AB3C
0x18001a7a5  mov     r9, rbx
0x18001a7a8  mov     rax, r12
0x18001a7ab  cmp     [rax], r15w
0x18001a7af  jz      short loc_18001A7BB
0x18001a7b1  add     rax, 2
0x18001a7b5  sub     r9, 1
0x18001a7b9  jnz     short loc_18001A7AB
0x18001a7bb  mov     rax, r9
0x18001a7be  neg     rax
0x18001a7c1  sbb     edi, edi
0x18001a7c3  not     edi
0x18001a7c5  and     edi, esi
0x18001a7c7  mov     r8, r9
0x18001a7ca  mov     rax, r9
0x18001a7cd  mov     rcx, rbx
0x18001a7d0  sub     rcx, r9
0x18001a7d3  neg     rax
0x18001a7d6  sbb     rdx, rdx
0x18001a7d9  and     rdx, rcx
0x18001a7dc  neg     r8
0x18001a7df  sbb     r8, r8
0x18001a7e2  and     r8, rdx; unsigned int
0x18001a7e5  mov     rcx, [rbp+5Fh]; this
0x18001a7e9  test    r9, r9
0x18001a7ec  jz      loc_18001AB46
0x18001a7f2  mov     rdx, r12; unsigned __int16 *
0x18001a7f5  lea     rcx, [rbp+57h+var_80]; this
0x18001a7f9  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
  ... truncated ...
```

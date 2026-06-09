# Windows::WU::Appraiser::GetTargetVersionInformation(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x140308bcc`
- end: `0x14030953b`
- name: `?GetTargetVersionInformation@Appraiser@WU@Windows@@CA?AV?$optional@UTargetVersionInformation@Appraiser@WU@Windows@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z`
- size: `2415`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1403085c0`

## callees

- `0x14002b6ec`
- `0x1400413a8`
- `0x140043284`
- `0x140043504`
- `0x140045184`
- `0x140045404`
- `0x14012ab5c`
- `0x1401a2aa8`
- `0x140308bcc`
- `0x14030a5d4`
- `0x14036efd0`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403093e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403093f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308de8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140308f78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309022`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309042`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309118`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309138`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403093e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403093f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309414`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140309424`

## string_xrefs

- `0x1403094b7`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\Appraiser.cpp`
- `0x1403094ea`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\Appraiser.cpp`
- `0x1403094ff`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\Appraiser.cpp`
- `0x140309514`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\Appraiser.cpp`
- `0x140309529`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\wuprovider\Appraiser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
_DWORD *__fastcall Windows::WU::Appraiser::GetTargetVersionInformation(_DWORD *a1, __int64 *a2)
{
  void *Src; // rax
  void *v5; // rax
  void *v6; // rax
  void *v7; // rax
  void *v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  void (*v18)(void); // rax
  __int64 v19; // rax
  _QWORD *v20; // rdx
  int v21; // eax
  __int64 v22; // rax
  _QWORD *v23; // rdx
  int v24; // eax
  __int64 v25; // rax
  _QWORD *v26; // rdx
  int v27; // eax
  __int64 v28; // rax
  _QWORD *v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rsi
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // r9
  __int128 *v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  __int128 *v43; // rax
  __int64 v44; // r8
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  int v63; // [rsp+20h] [rbp-E0h]
  __int128 *v64; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v65; // [rsp+48h] [rbp-B8h]
  int v66; // [rsp+50h] [rbp-B0h]
  int v67; // [rsp+54h] [rbp-ACh]
  __int64 v68; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h]
  __int64 v70; // [rsp+68h] [rbp-98h]
  __int64 v71; // [rsp+70h] [rbp-90h] BYREF
  __int64 v72; // [rsp+78h] [rbp-88h]
  __int64 v73; // [rsp+80h] [rbp-80h]
  __int64 v74; // [rsp+88h] [rbp-78h]
  __int64 v75; // [rsp+90h] [rbp-70h]
  __int128 v76; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v77; // [rsp+B0h] [rbp-50h]
  __int128 v78; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v79; // [rsp+D0h] [rbp-30h]
  wchar_t v80[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v81; // [rsp+F0h] [rbp-10h]
  wchar_t v82[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v83; // [rsp+110h] [rbp+10h]
  wchar_t String[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v85; // [rsp+130h] [rbp+30h]
  __int64 *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h] BYREF
  __int64 *v88; // [rsp+150h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+158h] [rbp+58h] BYREF
  LPVOID v90; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v91; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v92[2]; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v93[2]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v94[4]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v95[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v96[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v97[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v98[4]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v93[0] = a1;
  v86 = a2;
  v88 = 0;
  Windows::DockedHelpers::GetDockedSystem(&v88);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 8 )
    std::_Xlen_string();
  Src = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    Src = (void *)*a2;
  std::wstring::wstring(v98, 8, Src, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0xD )
    std::_Xlen_string();
  v5 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v5 = (void *)*a2;
  std::wstring::wstring(v97, 13, v5, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x11 )
    std::_Xlen_string();
  v6 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v6 = (void *)*a2;
  std::wstring::wstring(v96, 17, v6, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x11 )
    std::_Xlen_string();
  v7 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v7 = (void *)*a2;
  std::wstring::wstring(v95, 17, v7, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x15 )
    std::_Xlen_string();
  v8 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v8 = (void *)*a2;
  std::wstring::wstring(v94, 21, v8, a2[2]);
  v87 = 0;
  pv = 0;
  v9 = *v88;
  pv = 0;
  v10 = v98;
  if ( v98[3] > 7u )
    v10 = (_QWORD *)v98[0];
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v9 + 80))(v88, v10, &v87, &pv);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v11,
      v63);
  if ( !v87 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v90 = 0;
  v19 = *v88;
  v90 = 0;
  v20 = v97;
  if ( v97[3] > 7u )
    v20 = (_QWORD *)v97[0];
  v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v19 + 80))(v88, v20, &v87, &v90);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v21,
      v63);
  if ( !v87 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v90 )
      CoTaskMemFree(v90);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v91 = 0;
  v22 = *v88;
  v91 = 0;
  v23 = v95;
  if ( v95[3] > 7u )
    v23 = (_QWORD *)v95[0];
  v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v22 + 80))(v88, v23, &v87, &v91);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v24,
      v63);
  if ( !v87 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v91 )
      CoTaskMemFree(v91);
    if ( v90 )
      CoTaskMemFree(v90);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v92[0] = 0;
  v25 = *v88;
  v92[0] = 0;
  v26 = v94;
  if ( v94[3] > 7u )
    v26 = (_QWORD *)v94[0];
  v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v25 + 80))(v88, v26, &v87, v92);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v27,
      v63);
  if ( !v87 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v92[0] )
      CoTaskMemFree(v92[0]);
    if ( v91 )
      CoTaskMemFree(v91);
    if ( v90 )
      CoTaskMemFree(v90);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_22:
    std::wstring::~wstring(v94, v12);
    std::wstring::~wstring(v95, v13);
    std::wstring::~wstring(v96, v14);
    std::wstring::~wstring(v97, v15);
    std::wstring::~wstring(v98, v16);
    if ( v88 )
    {
      v18 = *(void (**)(void))(*v88 + 16);
LABEL_73:
      v18();
      goto LABEL_101;
    }
    goto LABEL_101;
  }
  v93[0] = 0;
  v28 = *v88;
  v93[0] = 0;
  v29 = v96;
  if ( v96[3] > 7u )
    v29 = (_QWORD *)v96[0];
  v30 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v28 + 80))(v88, v29, &v87, v93);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v30,
      v63);
  if ( v87 )
  {
    *(_OWORD *)String = 0;
    v85 = 0;
    v36 = -1;
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)pv + v37) );
    std::wstring::_Construct<1,wchar_t const *>(String, pv, v37);
    v66 = std::stol(String);
    v67 = 0;
    v78 = 0;
    v79 = 0;
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v90 + v38) );
    std::wstring::_Construct<1,wchar_t const *>(&v78, v90, v38);
    v40 = &v78;
    if ( *((_QWORD *)&v79 + 1) > 7u )
      v40 = (__int128 *)v78;
    v64 = v40;
    v65 = v79;
    LOBYTE(v39) = 1;
    Strings::tokenize(&v68, &v64, 59, v39);
    v76 = 0;
    v77 = 0;
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v93[0] + v41) );
    std::wstring::_Construct<1,wchar_t const *>(&v76, v93[0], v41);
    v43 = &v76;
    if ( *((_QWORD *)&v77 + 1) > 7u )
      v43 = (__int128 *)v76;
    v64 = v43;
    v65 = v77;
    LOBYTE(v42) = 1;
    Strings::tokenize(&v71, &v64, 44, v42);
    *(_OWORD *)v82 = 0;
    v83 = 0;
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v91 + v44) );
    std::wstring::_Construct<1,wchar_t const *>(v82, v91, v44);
    v74 = 10000000 * std::stoll(v82);
    *(_OWORD *)v80 = 0;
    v81 = 0;
    do
      ++v36;
    while ( *((_WORD *)v92[0] + v36) );
    std::wstring::_Construct<1,wchar_t const *>(v80, v92[0], v36);
    v45 = 10000000 * std::stoll(v80);
    v75 = v45;
    *a1 = v66;
    v46 = v70;
    v70 = 0;
    v47 = v69;
    v69 = 0;
    v48 = v68;
    v68 = 0;
    *((_QWORD *)a1 + 1) = v48;
    *((_QWORD *)a1 + 2) = v47;
    *((_QWORD *)a1 + 3) = v46;
    v49 = v73;
    v73 = 0;
    v50 = v72;
    v72 = 0;
    v51 = v71;
    v71 = 0;
    *((_QWORD *)a1 + 4) = v51;
    *((_QWORD *)a1 + 5) = v50;
    *((_QWORD *)a1 + 6) = v49;
    *((_QWORD *)a1 + 7) = v74;
    *((_QWORD *)a1 + 8) = v45;
    *((_BYTE *)a1 + 72) = 1;
    std::vector<std::filesystem::path>::_Tidy(&v71);
    std::vector<std::filesystem::path>::_Tidy(&v68);
    std::wstring::~wstring(v80, v52);
    std::wstring::~wstring(v82, v53);
    std::wstring::~wstring(&v76, v54);
    std::wstring::~wstring(&v78, v55);
    std::wstring::~wstring(String, v56);
    if ( v93[0] )
      CoTaskMemFree(v93[0]);
    if ( v92[0] )
      CoTaskMemFree(v92[0]);
    if ( v91 )
      CoTaskMemFree(v91);
    if ( v90 )
      CoTaskMemFree(v90);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v94, v57);
    std::wstring::~wstring(v95, v58);
    std::wstring::~wstring(v96, v59);
    std::wstring::~wstring(v97, v60);
    std::wstring::~wstring(v98, v61);
    if ( v88 )
      (*(void (__fastcall **)(__int64 *))(*v88 + 16))(v88);
  }
  else
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v93[0] )
      CoTaskMemFree(v93[0]);
    if ( v92[0] )
      CoTaskMemFree(v92[0]);
    if ( v91 )
      CoTaskMemFree(v91);
    if ( v90 )
      CoTaskMemFree(v90);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v94, v31);
    std::wstring::~wstring(v95, v32);
    std::wstring::~wstring(v96, v33);
    std::wstring::~wstring(v97, v34);
    std::wstring::~wstring(v98, v35);
    if ( v88 )
    {
      v18 = *(void (**)(void))(*v88 + 16);
      goto LABEL_73;
    }
  }
LABEL_101:
  std::wstring::~wstring(a2, v17);
  return a1;
}

```

## disassembly

```asm
0x140308bcc  mov     [rsp-8+arg_10], rbx
0x140308bd1  mov     [rsp-8+arg_18], rsi
0x140308bd6  push    rbp
0x140308bd7  push    rdi
0x140308bd8  push    r14
0x140308bda  lea     rbp, [rsp-140h]
0x140308be2  sub     rsp, 240h
0x140308be9  mov     rax, cs:__security_cookie
0x140308bf0  xor     rax, rsp
0x140308bf3  mov     [rbp+150h+var_20], rax
0x140308bfa  mov     rbx, rdx
0x140308bfd  mov     rdi, rcx
0x140308c00  mov     [rbp+150h+var_D0], rcx
0x140308c07  mov     [rbp+150h+var_110], rdx
0x140308c0b  xor     r14d, r14d
0x140308c0e  mov     [rbp+150h+var_100], r14
0x140308c12  lea     rcx, [rbp+150h+var_100]
0x140308c16  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x140308c1b  nop
0x140308c1c  mov     rcx, [rbx+10h]
0x140308c20  mov     rsi, 7FFFFFFFFFFFFFFEh
0x140308c2a  mov     rax, rsi
0x140308c2d  sub     rax, rcx
0x140308c30  cmp     rax, 8
0x140308c34  jb      loc_1403094C9
0x140308c3a  mov     rax, rbx
0x140308c3d  cmp     qword ptr [rbx+18h], 7
0x140308c42  jbe     short loc_140308C47
0x140308c44  mov     rax, [rbx]
0x140308c47  mov     [rsp+250h+var_220], rcx; __int64
0x140308c4c  mov     [rsp+250h+Src], rax; Src
0x140308c51  mov     [rsp+250h+var_230], 8; __int64
0x140308c5a  lea     r9, aGstatus; "GStatus_"
0x140308c61  lea     rcx, [rbp+150h+var_40]; void *
0x140308c68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140308c6d  nop
0x140308c6e  mov     rcx, [rbx+10h]
0x140308c72  mov     rax, rsi
0x140308c75  sub     rax, rcx
0x140308c78  cmp     rax, 0Dh
0x140308c7c  jb      loc_1403094CF
0x140308c82  mov     rax, rbx
0x140308c85  cmp     qword ptr [rbx+18h], 7
0x140308c8a  jbe     short loc_140308C8F
0x140308c8c  mov     rax, [rbx]
0x140308c8f  mov     [rsp+250h+var_220], rcx; __int64
0x140308c94  mov     [rsp+250h+Src], rax; Src
0x140308c99  mov     [rsp+250h+var_230], 0Dh; __int64
0x140308ca2  lea     r9, aGatedblockid; "GatedBlockId_"
0x140308ca9  lea     rcx, [rbp+150h+var_60]; void *
0x140308cb0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140308cb5  nop
0x140308cb6  mov     rcx, [rbx+10h]
0x140308cba  mov     rax, rsi
0x140308cbd  sub     rax, rcx
0x140308cc0  cmp     rax, 11h
0x140308cc4  jb      loc_1403094D5
0x140308cca  mov     rax, rbx
0x140308ccd  cmp     qword ptr [rbx+18h], 7
0x140308cd2  jbe     short loc_140308CD7
0x140308cd4  mov     rax, [rbx]
0x140308cd7  mov     [rsp+250h+var_220], rcx; __int64
0x140308cdc  mov     [rsp+250h+Src], rax; Src
0x140308ce1  mov     [rsp+250h+var_230], 11h; __int64
0x140308cea  lea     r9, aDestbuildnumli; "DestBuildNumList_"
0x140308cf1  lea     rcx, [rbp+150h+var_80]; void *
0x140308cf8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140308cfd  nop
0x140308cfe  mov     rcx, [rbx+10h]
0x140308d02  mov     rax, rsi
0x140308d05  sub     rax, rcx
0x140308d08  cmp     rax, 11h
0x140308d0c  jb      loc_1403094DB
0x140308d12  mov     rax, rbx
0x140308d15  cmp     qword ptr [rbx+18h], 7
0x140308d1a  jbe     short loc_140308D1F
0x140308d1c  mov     rax, [rbx]
0x140308d1f  mov     [rsp+250h+var_220], rcx; __int64
0x140308d24  mov     [rsp+250h+Src], rax; Src
0x140308d29  mov     [rsp+250h+var_230], 11h; __int64
0x140308d32  lea     r9, aDataexpdateepo; "DataExpDateEpoch_"
0x140308d39  lea     rcx, [rbp+150h+var_A0]; void *
0x140308d40  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140308d45  nop
0x140308d46  mov     rcx, [rbx+10h]
0x140308d4a  sub     rsi, rcx
0x140308d4d  cmp     rsi, 15h
0x140308d51  jb      loc_1403094E1
0x140308d57  mov     rax, rbx
0x140308d5a  cmp     qword ptr [rbx+18h], 7
0x140308d5f  jbe     short loc_140308D64
0x140308d61  mov     rax, [rbx]
0x140308d64  mov     [rsp+250h+var_220], rcx; __int64
0x140308d69  mov     [rsp+250h+Src], rax; Src
0x140308d6e  mov     [rsp+250h+var_230], 15h; int
0x140308d77  lea     r9, aTimestampepoch; "TimestampEpochString_"
0x140308d7e  lea     rcx, [rbp+150h+var_C0]; void *
0x140308d85  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140308d8a  nop
0x140308d8b  mov     [rbp+150h+var_108], r14d
0x140308d8f  mov     [rbp+150h+pv], r14
0x140308d93  mov     rcx, [rbp+150h+var_100]
0x140308d97  mov     rax, [rcx]
0x140308d9a  mov     [rbp+150h+pv], r14
0x140308d9e  lea     rdx, [rbp+150h+var_40]
0x140308da5  cmp     [rbp+150h+var_28], 7
0x140308dad  cmova   rdx, [rbp+150h+var_40]
0x140308db5  lea     r9, [rbp+150h+pv]
0x140308db9  lea     r8, [rbp+150h+var_108]
0x140308dbd  mov     rax, [rax+50h]
0x140308dc1  call    _guard_dispatch_icall
0x140308dc6  mov     rcx, [rbp+158h]; this
0x140308dcd  test    eax, eax
0x140308dcf  js      loc_1403094E7
0x140308dd5  cmp     [rbp+150h+var_108], r14d
0x140308dd9  jnz     short loc_140308E49
0x140308ddb  mov     [rdi+48h], r14b
0x140308ddf  mov     rcx, [rbp+150h+pv]; pv
0x140308de3  test    rcx, rcx
0x140308de6  jz      short loc_140308DEF
0x140308de8  call    cs:__imp_CoTaskMemFree
0x140308dee  nop
0x140308def  lea     rcx, [rbp+150h+var_C0]
0x140308df6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308dfb  nop
0x140308dfc  lea     rcx, [rbp+150h+var_A0]
0x140308e03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308e08  nop
0x140308e09  lea     rcx, [rbp+150h+var_80]
0x140308e10  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308e15  nop
0x140308e16  lea     rcx, [rbp+150h+var_60]
0x140308e1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308e22  nop
0x140308e23  lea     rcx, [rbp+150h+var_40]
0x140308e2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308e2f  nop
0x140308e30  mov     rcx, [rbp+150h+var_100]
0x140308e34  test    rcx, rcx
0x140308e37  jz      loc_1403091A6
0x140308e3d  mov     rax, [rcx]
0x140308e40  mov     rax, [rax+10h]
0x140308e44  jmp     loc_1403091A0
0x140308e49  mov     [rbp+150h+var_F0], r14
0x140308e4d  mov     rcx, [rbp+150h+var_100]
0x140308e51  mov     rax, [rcx]
0x140308e54  mov     [rbp+150h+var_F0], r14
0x140308e58  lea     rdx, [rbp+150h+var_60]
0x140308e5f  cmp     [rbp+150h+var_48], 7
0x140308e67  cmova   rdx, [rbp+150h+var_60]
0x140308e6f  lea     r9, [rbp+150h+var_F0]
0x140308e73  lea     r8, [rbp+150h+var_108]
0x140308e77  mov     rax, [rax+50h]
0x140308e7b  call    _guard_dispatch_icall
0x140308e80  mov     rcx, [rbp+158h]; this
0x140308e87  test    eax, eax
0x140308e89  js      loc_1403094FC
0x140308e8f  cmp     [rbp+150h+var_108], r14d
0x140308e93  jnz     short loc_140308EFF
0x140308e95  mov     [rdi+48h], r14b
0x140308e99  mov     rcx, [rbp+150h+var_F0]; pv
0x140308e9d  test    rcx, rcx
0x140308ea0  jz      short loc_140308EA9
0x140308ea2  call    cs:__imp_CoTaskMemFree
0x140308ea8  nop
0x140308ea9  mov     rcx, [rbp+150h+pv]; pv
0x140308ead  test    rcx, rcx
0x140308eb0  jz      short loc_140308EB9
0x140308eb2  call    cs:__imp_CoTaskMemFree
0x140308eb8  nop
0x140308eb9  lea     rcx, [rbp+150h+var_C0]
0x140308ec0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308ec5  nop
0x140308ec6  lea     rcx, [rbp+150h+var_A0]
0x140308ecd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308ed2  nop
0x140308ed3  lea     rcx, [rbp+150h+var_80]
0x140308eda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308edf  nop
0x140308ee0  lea     rcx, [rbp+150h+var_60]
0x140308ee7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308eec  nop
0x140308eed  lea     rcx, [rbp+150h+var_40]
0x140308ef4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308ef9  nop
0x140308efa  jmp     loc_140308E30
0x140308eff  mov     [rbp+150h+var_E8], r14
0x140308f03  mov     rcx, [rbp+150h+var_100]
0x140308f07  mov     rax, [rcx]
0x140308f0a  mov     [rbp+150h+var_E8], r14
0x140308f0e  lea     rdx, [rbp+150h+var_A0]
0x140308f15  cmp     [rbp+150h+var_88], 7
0x140308f1d  cmova   rdx, [rbp+150h+var_A0]
0x140308f25  lea     r9, [rbp+150h+var_E8]
0x140308f29  lea     r8, [rbp+150h+var_108]
0x140308f2d  mov     rax, [rax+50h]
0x140308f31  call    _guard_dispatch_icall
0x140308f36  mov     rcx, [rbp+158h]; this
0x140308f3d  test    eax, eax
0x140308f3f  js      loc_140309511
0x140308f45  cmp     [rbp+150h+var_108], r14d
0x140308f49  jnz     short loc_140308FC5
0x140308f4b  mov     [rdi+48h], r14b
0x140308f4f  mov     rcx, [rbp+150h+var_E8]; pv
0x140308f53  test    rcx, rcx
0x140308f56  jz      short loc_140308F5F
0x140308f58  call    cs:__imp_CoTaskMemFree
0x140308f5e  nop
0x140308f5f  mov     rcx, [rbp+150h+var_F0]; pv
0x140308f63  test    rcx, rcx
0x140308f66  jz      short loc_140308F6F
0x140308f68  call    cs:__imp_CoTaskMemFree
0x140308f6e  nop
0x140308f6f  mov     rcx, [rbp+150h+pv]; pv
0x140308f73  test    rcx, rcx
0x140308f76  jz      short loc_140308F7F
0x140308f78  call    cs:__imp_CoTaskMemFree
0x140308f7e  nop
0x140308f7f  lea     rcx, [rbp+150h+var_C0]
0x140308f86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308f8b  nop
0x140308f8c  lea     rcx, [rbp+150h+var_A0]
0x140308f93  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308f98  nop
0x140308f99  lea     rcx, [rbp+150h+var_80]
0x140308fa0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308fa5  nop
0x140308fa6  lea     rcx, [rbp+150h+var_60]
0x140308fad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308fb2  nop
0x140308fb3  lea     rcx, [rbp+150h+var_40]
0x140308fba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140308fbf  nop
0x140308fc0  jmp     loc_140308E30
0x140308fc5  mov     [rbp+150h+var_E0], r14
0x140308fc9  mov     rcx, [rbp+150h+var_100]
0x140308fcd  mov     rax, [rcx]
0x140308fd0  mov     [rbp+150h+var_E0], r14
0x140308fd4  lea     rdx, [rbp+150h+var_C0]
0x140308fdb  cmp     [rbp+150h+var_A8], 7
0x140308fe3  cmova   rdx, [rbp+150h+var_C0]
0x140308feb  lea     r9, [rbp+150h+var_E0]
0x140308fef  lea     r8, [rbp+150h+var_108]
0x140308ff3  mov     rax, [rax+50h]
0x140308ff7  call    _guard_dispatch_icall
0x140308ffc  mov     rcx, [rbp+158h]; this
0x140309003  test    eax, eax
0x140309005  js      loc_140309526
0x14030900b  cmp     [rbp+150h+var_108], r14d
0x14030900f  jnz     loc_14030909F
0x140309015  mov     [rdi+48h], r14b
0x140309019  mov     rcx, [rbp+150h+var_E0]; pv
0x14030901d  test    rcx, rcx
0x140309020  jz      short loc_140309029
0x140309022  call    cs:__imp_CoTaskMemFree
0x140309028  nop
0x140309029  mov     rcx, [rbp+150h+var_E8]; pv
0x14030902d  test    rcx, rcx
0x140309030  jz      short loc_140309039
0x140309032  call    cs:__imp_CoTaskMemFree
0x140309038  nop
0x140309039  mov     rcx, [rbp+150h+var_F0]; pv
0x14030903d  test    rcx, rcx
0x140309040  jz      short loc_140309049
0x140309042  call    cs:__imp_CoTaskMemFree
0x140309048  nop
0x140309049  mov     rcx, [rbp+150h+pv]; pv
0x14030904d  test    rcx, rcx
0x140309050  jz      short loc_140309059
0x140309052  call    cs:__imp_CoTaskMemFree
0x140309058  nop
0x140309059  lea     rcx, [rbp+150h+var_C0]
0x140309060  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140309065  nop
0x140309066  lea     rcx, [rbp+150h+var_A0]
0x14030906d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140309072  nop
0x140309073  lea     rcx, [rbp+150h+var_80]
0x14030907a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030907f  nop
0x140309080  lea     rcx, [rbp+150h+var_60]
0x140309087  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030908c  nop
0x14030908d  lea     rcx, [rbp+150h+var_40]
0x140309094  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140309099  nop
0x14030909a  jmp     loc_140308E30
0x14030909f  mov     [rbp+150h+var_D0], r14
0x1403090a6  mov     rcx, [rbp+150h+var_100]
0x1403090aa  mov     rax, [rcx]
0x1403090ad  mov     [rbp+150h+var_D0], r14
0x1403090b4  lea     rdx, [rbp+150h+var_80]
0x1403090bb  cmp     [rbp+150h+var_68], 7
0x1403090c3  cmova   rdx, [rbp+150h+var_80]
0x1403090cb  lea     r9, [rbp+150h+var_D0]
0x1403090d2  lea     r8, [rbp+150h+var_108]
0x1403090d6  mov     rax, [rax+50h]
0x1403090da  call    _guard_dispatch_icall
0x1403090df  mov     rcx, [rbp+158h]; this
0x1403090e6  test    eax, eax
  ... truncated ...
```

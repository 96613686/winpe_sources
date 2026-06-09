# Windows::WU::Appraiser::GetTargetVersionInformation(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x140308bcc`
- end: `0x14030953b`
- name: `?GetTargetVersionInformation@Appraiser@WU@Windows@@CA?AV?$optional@UTargetVersionInformation@Appraiser@WU@Windows@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z`
- size: `2415`
- prototype: ``
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
  void (*v12)(void); // rax
  __int64 v13; // rax
  _QWORD *v14; // rdx
  int v15; // eax
  __int64 v16; // rax
  _QWORD *v17; // rdx
  int v18; // eax
  __int64 v19; // rax
  _QWORD *v20; // rdx
  int v21; // eax
  __int64 v22; // rax
  _QWORD *v23; // rdx
  int v24; // eax
  __int64 v25; // rsi
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r9
  __int128 *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  __int128 *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  int v42; // [rsp+20h] [rbp-E0h]
  __int128 *v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h]
  int v45; // [rsp+50h] [rbp-B0h]
  int v46; // [rsp+54h] [rbp-ACh]
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h]
  __int64 v52; // [rsp+80h] [rbp-80h]
  __int64 v53; // [rsp+88h] [rbp-78h]
  __int64 v54; // [rsp+90h] [rbp-70h]
  __int128 v55; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-50h]
  __int128 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v58; // [rsp+D0h] [rbp-30h]
  wchar_t v59[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v60; // [rsp+F0h] [rbp-10h]
  wchar_t v61[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v62; // [rsp+110h] [rbp+10h]
  wchar_t String[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v64; // [rsp+130h] [rbp+30h]
  __int64 *v65; // [rsp+140h] [rbp+40h]
  int v66; // [rsp+148h] [rbp+48h] BYREF
  __int64 *v67; // [rsp+150h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+158h] [rbp+58h] BYREF
  LPVOID v69; // [rsp+160h] [rbp+60h] BYREF
  LPVOID v70; // [rsp+168h] [rbp+68h] BYREF
  LPVOID v71[2]; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v72[2]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v73[4]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD v74[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v75[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v76[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v77[4]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v72[0] = a1;
  v65 = a2;
  v67 = 0;
  Windows::DockedHelpers::GetDockedSystem(&v67);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 8 )
    std::_Xlen_string();
  Src = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    Src = (void *)*a2;
  std::wstring::wstring(v77, 8, Src, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0xD )
    std::_Xlen_string();
  v5 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v5 = (void *)*a2;
  std::wstring::wstring(v76, 13, v5, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x11 )
    std::_Xlen_string();
  v6 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v6 = (void *)*a2;
  std::wstring::wstring(v75, 17, v6, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x11 )
    std::_Xlen_string();
  v7 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v7 = (void *)*a2;
  std::wstring::wstring(v74, 17, v7, a2[2]);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a2[2]) < 0x15 )
    std::_Xlen_string();
  v8 = a2;
  if ( (unsigned __int64)a2[3] > 7 )
    v8 = (void *)*a2;
  std::wstring::wstring(v73, 21, v8, a2[2]);
  v66 = 0;
  pv = 0;
  v9 = *v67;
  pv = 0;
  v10 = v77;
  if ( v77[3] > 7u )
    v10 = (_QWORD *)v77[0];
  v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v9 + 80))(v67, v10, &v66, &pv);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v11,
      v42);
  if ( !v66 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v69 = 0;
  v13 = *v67;
  v69 = 0;
  v14 = v76;
  if ( v76[3] > 7u )
    v14 = (_QWORD *)v76[0];
  v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v13 + 80))(v67, v14, &v66, &v69);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v15,
      v42);
  if ( !v66 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v69 )
      CoTaskMemFree(v69);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v70 = 0;
  v16 = *v67;
  v70 = 0;
  v17 = v74;
  if ( v74[3] > 7u )
    v17 = (_QWORD *)v74[0];
  v18 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v16 + 80))(v67, v17, &v66, &v70);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v18,
      v42);
  if ( !v66 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v70 )
      CoTaskMemFree(v70);
    if ( v69 )
      CoTaskMemFree(v69);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_22;
  }
  v71[0] = 0;
  v19 = *v67;
  v71[0] = 0;
  v20 = v73;
  if ( v73[3] > 7u )
    v20 = (_QWORD *)v73[0];
  v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v19 + 80))(v67, v20, &v66, v71);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v21,
      v42);
  if ( !v66 )
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v71[0] )
      CoTaskMemFree(v71[0]);
    if ( v70 )
      CoTaskMemFree(v70);
    if ( v69 )
      CoTaskMemFree(v69);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_22:
    std::wstring::~wstring(v73);
    std::wstring::~wstring(v74);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(v77);
    if ( v67 )
    {
      v12 = *(void (**)(void))(*v67 + 16);
LABEL_73:
      v12();
      goto LABEL_101;
    }
    goto LABEL_101;
  }
  v72[0] = 0;
  v22 = *v67;
  v72[0] = 0;
  v23 = v75;
  if ( v75[3] > 7u )
    v23 = (_QWORD *)v75[0];
  v24 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *, LPVOID *))(v22 + 80))(v67, v23, &v66, v72);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\wuprovider\\Appraiser.cpp",
      (const char *)(unsigned int)v24,
      v42);
  if ( v66 )
  {
    *(_OWORD *)String = 0;
    v64 = 0;
    v25 = -1;
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)pv + v26) );
    std::wstring::_Construct<1,wchar_t const *>(String, pv);
    v45 = std::stol(String);
    v46 = 0;
    v57 = 0;
    v58 = 0;
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v69 + v27) );
    std::wstring::_Construct<1,wchar_t const *>(&v57, v69);
    v29 = &v57;
    if ( *((_QWORD *)&v58 + 1) > 7u )
      v29 = (__int128 *)v57;
    v43 = v29;
    v44 = v58;
    LOBYTE(v28) = 1;
    Strings::tokenize(&v47, &v43, 59, v28);
    v55 = 0;
    v56 = 0;
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v72[0] + v30) );
    std::wstring::_Construct<1,wchar_t const *>(&v55, v72[0]);
    v32 = &v55;
    if ( *((_QWORD *)&v56 + 1) > 7u )
      v32 = (__int128 *)v55;
    v43 = v32;
    v44 = v56;
    LOBYTE(v31) = 1;
    Strings::tokenize(&v50, &v43, 44, v31);
    *(_OWORD *)v61 = 0;
    v62 = 0;
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v70 + v33) );
    std::wstring::_Construct<1,wchar_t const *>(v61, v70);
    v53 = 10000000 * std::stoll(v61);
    *(_OWORD *)v59 = 0;
    v60 = 0;
    do
      ++v25;
    while ( *((_WORD *)v71[0] + v25) );
    std::wstring::_Construct<1,wchar_t const *>(v59, v71[0]);
    v34 = 10000000 * std::stoll(v59);
    v54 = v34;
    *a1 = v45;
    v35 = v49;
    v49 = 0;
    v36 = v48;
    v48 = 0;
    v37 = v47;
    v47 = 0;
    *((_QWORD *)a1 + 1) = v37;
    *((_QWORD *)a1 + 2) = v36;
    *((_QWORD *)a1 + 3) = v35;
    v38 = v52;
    v52 = 0;
    v39 = v51;
    v51 = 0;
    v40 = v50;
    v50 = 0;
    *((_QWORD *)a1 + 4) = v40;
    *((_QWORD *)a1 + 5) = v39;
    *((_QWORD *)a1 + 6) = v38;
    *((_QWORD *)a1 + 7) = v53;
    *((_QWORD *)a1 + 8) = v34;
    *((_BYTE *)a1 + 72) = 1;
    std::vector<std::filesystem::path>::_Tidy(&v50);
    std::vector<std::filesystem::path>::_Tidy(&v47);
    std::wstring::~wstring(v59);
    std::wstring::~wstring(v61);
    std::wstring::~wstring(&v55);
    std::wstring::~wstring(&v57);
    std::wstring::~wstring(String);
    if ( v72[0] )
      CoTaskMemFree(v72[0]);
    if ( v71[0] )
      CoTaskMemFree(v71[0]);
    if ( v70 )
      CoTaskMemFree(v70);
    if ( v69 )
      CoTaskMemFree(v69);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v73);
    std::wstring::~wstring(v74);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(v77);
    if ( v67 )
      (*(void (__fastcall **)(__int64 *))(*v67 + 16))(v67);
  }
  else
  {
    *((_BYTE *)a1 + 72) = 0;
    if ( v72[0] )
      CoTaskMemFree(v72[0]);
    if ( v71[0] )
      CoTaskMemFree(v71[0]);
    if ( v70 )
      CoTaskMemFree(v70);
    if ( v69 )
      CoTaskMemFree(v69);
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(v73);
    std::wstring::~wstring(v74);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(v77);
    if ( v67 )
    {
      v12 = *(void (**)(void))(*v67 + 16);
      goto LABEL_73;
    }
  }
LABEL_101:
  std::wstring::~wstring(a2);
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

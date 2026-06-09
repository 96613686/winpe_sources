# Windows::UsoProductEnumerator::GetProductInfo(wil::basic_zstring_view<wchar_t>)

- ea: `0x140370068`
- end: `0x140370996`
- name: `?GetProductInfo@UsoProductEnumerator@Windows@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2350`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14023f410`

## callees

- `0x14002ad90`
- `0x14002b6ec`
- `0x14003f4a8`
- `0x1400413a8`
- `0x140043284`
- `0x140044b18`
- `0x140045184`
- `0x140045404`
- `0x1400454a0`
- `0x1400a3d80`
- `0x1400a3eac`
- `0x1401156f8`
- `0x140370068`
- `0x14037099c`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403701a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14037035a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403704bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14037078e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403707a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370887`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403701a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14037035a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403704bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14037078e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403707a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1403701a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1403704c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140370540`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1403701a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1403704c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140370540`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140370196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403704b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14037052d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140370196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1403704b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14037052d`

## string_xrefs

- `0x1403708eb`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370900`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370915`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14037092a`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14037093f`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370954`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x14037096f`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x140370984`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
_QWORD *__fastcall Windows::UsoProductEnumerator::GetProductInfo(_DWORD *a1, _QWORD *a2, __int64 *a3)
{
  _DWORD *v4; // rax
  int v5; // edi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r15
  _QWORD *v14; // rsi
  void *v15; // r14
  DWORD LastError; // ebx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // r8
  int v26; // ebx
  bool v27; // bl
  LPVOID v28; // rbx
  int v29; // edi
  unsigned int v30; // r12d
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  wchar_t *v36; // r15
  wchar_t *v37; // rsi
  void *v38; // r14
  DWORD v39; // ebx
  __int64 v40; // rax
  int v41; // eax
  wchar_t *v42; // r15
  wchar_t *v43; // rsi
  void *v44; // r14
  DWORD v45; // ebx
  __int64 *v46; // rsi
  __int64 v47; // r8
  const wchar_t *v48; // rcx
  char v49; // bl
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  int v56; // [rsp+20h] [rbp-E0h]
  bool v57; // [rsp+40h] [rbp-C0h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-B8h] BYREF
  size_t N[2]; // [rsp+58h] [rbp-A8h]
  int v60; // [rsp+68h] [rbp-98h]
  __int64 *v61; // [rsp+70h] [rbp-90h]
  _DWORD *v62; // [rsp+78h] [rbp-88h]
  _QWORD v63[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  _QWORD *v66; // [rsp+A8h] [rbp-58h]
  _QWORD v67[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v68[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v69[5]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v70[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v71[40]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v72; // [rsp+150h] [rbp+50h] BYREF
  char v73; // [rsp+160h] [rbp+60h]
  unsigned int v74; // [rsp+170h] [rbp+70h] BYREF
  __int64 *v75; // [rsp+178h] [rbp+78h] BYREF
  __int64 *v76; // [rsp+180h] [rbp+80h] BYREF
  LPVOID v77; // [rsp+188h] [rbp+88h] BYREF
  LPVOID v78; // [rsp+190h] [rbp+90h] BYREF
  LPVOID v79; // [rsp+198h] [rbp+98h] BYREF
  LPVOID pv; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v81[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v82; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v61 = a3;
  v4 = a1;
  v62 = a1;
  v69[4] = a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v5 = 1;
  v6 = 0;
  v60 = 0;
  if ( *a1 )
  {
    while ( 1 )
    {
      v75 = 0;
      v7 = (__int64 *)*((_QWORD *)v4 + 3);
      v8 = *v7;
      *(_QWORD *)&v72 = &v75;
      *((_QWORD *)&v72 + 1) = 0;
      v73 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(v8 + 32))(v7, v6, (char *)&v72 + 8);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA3,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v9,
          v56);
      if ( v73 )
      {
        v10 = *(_QWORD *)v72;
        *(_QWORD *)v72 = *((_QWORD *)&v72 + 1);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      pv = 0;
      v11 = *v75;
      *(_QWORD *)&v72 = &pv;
      *((_QWORD *)&v72 + 1) = 0;
      v73 = 1;
      v12 = (*(__int64 (__fastcall **)(__int64 *, char *))(v11 + 24))(v75, (char *)&v72 + 8);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v12,
          v56);
      if ( v73 )
      {
        v13 = *((_QWORD *)&v72 + 1);
        v14 = (_QWORD *)v72;
        v15 = *(void **)v72;
        if ( *(_QWORD *)v72 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v15);
          SetLastError(LastError);
        }
        *v14 = v13;
      }
      v76 = 0;
      v17 = *v75;
      *(_QWORD *)&v72 = &v76;
      *((_QWORD *)&v72 + 1) = 0;
      v73 = 1;
      v18 = (*(__int64 (__fastcall **)(__int64 *, char *))(v17 + 32))(v75, (char *)&v72 + 8);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v18,
          v56);
      if ( v73 )
      {
        v19 = *(_QWORD *)v72;
        *(_QWORD *)v72 = *((_QWORD *)&v72 + 1);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v74 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v76 + 24))(v76, &v74);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAC,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v20,
          v56);
      if ( v74 )
        break;
      if ( v76 )
        (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v75 )
        (*(void (__fastcall **)(__int64 *))(*v75 + 16))(v75);
LABEL_89:
      v6 = (unsigned int)(v60 + 1);
      v60 = v6;
      v4 = v62;
      if ( (unsigned int)v6 >= *v62 )
        return a2;
    }
    v57 = 0;
    *(_QWORD *)&v72 = 0;
    v21 = *v75;
    *(_QWORD *)&v72 = 0;
    if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, __int128 *))(v21 + 40))(v75, L"PrimaryOSProduct", &v72) >= 0 )
    {
      v77 = 0;
      v23 = *(_QWORD *)v72;
      v77 = 0;
      v24 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(v23 + 32))(v72, &v77);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v24,
          v56);
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v25 = -1;
      do
        ++v25;
      while ( *((_WORD *)v77 + v25) );
      std::wstring::_Construct<1,wchar_t const *>(S1, v77);
      v26 = std::stoi((wchar_t *)S1);
      std::wstring::~wstring(S1);
      v27 = v26 == 1;
      v57 = v27;
      if ( v77 )
      {
        CoTaskMemFree(v77);
        v57 = v27;
      }
    }
    if ( (_QWORD)v72 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v72 + 16LL))(v72);
    v28 = pv;
    wil::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(
      v63,
      v22);
    v63[1] = v28;
    v63[0] = 0xB000000000000000uLL;
    *(_QWORD *)&v64 = L"PN={}";
    *((_QWORD *)&v64 + 1) = 5;
    v65 = 1;
    v66 = v63;
    v72 = v64;
    std::vformat<0>(v81);
    v29 = v5 | 0x20;
    v30 = 0;
    if ( !v74 )
    {
LABEL_82:
      if ( v82 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(S1, v82, L";", 1);
      v5 = v29 | 0x10;
      std::wstring::append(a2);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v81);
      if ( v76 )
        (*(void (__fastcall **)(__int64 *))(*v76 + 16))(v76);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v75 )
        (*(void (__fastcall **)(__int64 *))(*v75 + 16))(v75);
      goto LABEL_89;
    }
    while ( 1 )
    {
      *(_QWORD *)&v72 = 0;
      v31 = *v76;
      S1[0] = (wchar_t *)&v72;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v32 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, wchar_t **))(v31 + 32))(v76, v30, &S1[1]);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v32,
          v56);
      if ( LOBYTE(N[0]) )
      {
        v33 = *(_QWORD *)S1[0];
        *(_QWORD *)S1[0] = S1[1];
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v79 = 0;
      v34 = *(_QWORD *)v72;
      S1[0] = (wchar_t *)&v79;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v35 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(v34 + 24))(v72, &S1[1]);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v35,
          v56);
      if ( LOBYTE(N[0]) )
      {
        v36 = S1[1];
        v37 = S1[0];
        v38 = *(void **)S1[0];
        if ( *(_QWORD *)S1[0] )
        {
          v39 = GetLastError();
          CoTaskMemFree(v38);
          SetLastError(v39);
        }
        *(_QWORD *)v37 = v36;
      }
      v78 = 0;
      v40 = *(_QWORD *)v72;
      S1[0] = (wchar_t *)&v78;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v41 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(v40 + 32))(v72, &S1[1]);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v41,
          v56);
      if ( LOBYTE(N[0]) )
      {
        v42 = S1[1];
        v43 = S1[0];
        v44 = *(void **)S1[0];
        if ( *(_QWORD *)S1[0] )
        {
          v45 = GetLastError();
          CoTaskMemFree(v44);
          SetLastError(v45);
        }
        *(_QWORD *)v43 = v42;
      }
      v46 = v61;
      if ( !v61[1] )
        goto LABEL_54;
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v47 = -1;
      do
        ++v47;
      while ( *((_WORD *)v79 + v47) );
      std::wstring::_Construct<1,wchar_t const *>(S1, v79);
      v29 |= 2u;
      v48 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v48 = S1[0];
      if ( N[0] != 7 || (v49 = 1, wmemcmp(v48, L"Version", 7u)) )
LABEL_54:
        v49 = 0;
      if ( (v29 & 2) != 0 )
      {
        v29 &= ~2u;
        std::wstring::~wstring(S1);
      }
      if ( v49 )
      {
        if ( v57 )
        {
          v50 = *v46;
          *(_OWORD *)S1 = 0;
          *(_OWORD *)N = 0;
          v51 = -1;
          do
            ++v51;
          while ( *(_WORD *)(v50 + 2 * v51) );
          std::wstring::_Construct<1,wchar_t const *>(S1, v50);
          v29 |= 4u;
        }
        else
        {
          v52 = -1;
          do
            ++v52;
          while ( *((_WORD *)v78 + v52) );
          v67[0] = v78;
          v67[1] = v52;
          Windows::UsoProductEnumerator::EscapeProductString(v52, v71, v67);
          v29 |= 8u;
        }
        v67[2] = L"&V={}";
        v67[3] = 5;
        std::format<std::wstring const &>(v70);
        std::wstring::append(v81);
        std::wstring::~wstring(v70);
        if ( (v29 & 8) != 0 )
        {
          v29 &= ~8u;
          std::wstring::~wstring(v71);
        }
        if ( (v29 & 4) == 0 )
          goto LABEL_75;
        v29 &= ~4u;
      }
      else
      {
        v53 = -1;
        do
          ++v53;
        while ( *((_WORD *)v78 + v53) );
        v68[0] = v78;
        v68[1] = v53;
        Windows::UsoProductEnumerator::EscapeProductString(v53, S1, v68);
        v54 = -1;
        do
          ++v54;
        while ( *((_WORD *)v79 + v54) );
        v69[0] = v79;
        v69[1] = v54;
        Windows::UsoProductEnumerator::EscapeProductString(v54, v70, v69);
        v69[2] = L"&{}={}";
        v69[3] = 6;
        std::format<std::wstring const &,std::wstring const &>(v71);
        std::wstring::append(v81);
        std::wstring::~wstring(v71);
        std::wstring::~wstring(v70);
      }
      std::wstring::~wstring(S1);
LABEL_75:
      if ( v78 )
        CoTaskMemFree(v78);
      if ( v79 )
        CoTaskMemFree(v79);
      if ( (_QWORD)v72 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v72 + 16LL))(v72);
      if ( ++v30 >= v74 )
        goto LABEL_82;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140370068  mov     [rsp-8+arg_18], rbx
0x14037006d  push    rbp
0x14037006e  push    rsi
0x14037006f  push    rdi
0x140370070  push    r12
0x140370072  push    r13
0x140370074  push    r14
0x140370076  push    r15
0x140370078  lea     rbp, [rsp-0D0h]
0x140370080  sub     rsp, 1D0h
0x140370087  mov     rax, cs:__security_cookie
0x14037008e  xor     rax, rsp
0x140370091  mov     [rbp+100h+var_38], rax
0x140370098  mov     [rsp+200h+var_190], r8
0x14037009d  mov     r13, rdx
0x1403700a0  mov     rax, rcx
0x1403700a3  mov     [rsp+200h+var_188], rcx
0x1403700a8  mov     [rbp+100h+var_100], rdx
0x1403700ac  xor     r14d, r14d
0x1403700af  mov     [rsp+200h+var_1BC], r14d
0x1403700b4  xorps   xmm0, xmm0
0x1403700b7  movups  xmmword ptr [rdx], xmm0
0x1403700ba  mov     [rdx+10h], r14
0x1403700be  mov     qword ptr [rdx+18h], 7
0x1403700c6  mov     [rdx], r14w
0x1403700ca  lea     edi, [r14+1]
0x1403700ce  mov     [rsp+200h+var_1BC], edi
0x1403700d2  mov     edx, r14d
0x1403700d5  mov     [rsp+200h+var_198], edx
0x1403700d9  cmp     [rcx], r14d
0x1403700dc  jbe     loc_1403708BB
0x1403700e2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1403700e6  mov     [rbp+100h+var_88], r14
0x1403700ea  mov     rcx, [rax+18h]
0x1403700ee  mov     rax, [rcx]
0x1403700f1  lea     r8, [rbp+100h+var_88]
0x1403700f5  mov     qword ptr [rbp+100h+var_B0], r8
0x1403700f9  mov     qword ptr [rbp+100h+var_B0+8], r14
0x1403700fd  mov     [rbp+100h+var_A0], 1
0x140370101  lea     r8, [rbp+100h+var_B0+8]
0x140370105  mov     rax, [rax+20h]
0x140370109  call    _guard_dispatch_icall
0x14037010e  mov     rcx, [rbp+108h]; this
0x140370115  test    eax, eax
0x140370117  js      loc_1403708FD
0x14037011d  cmp     [rbp+100h+var_A0], r14b
0x140370121  jz      short loc_140370143
0x140370123  mov     rdx, qword ptr [rbp+100h+var_B0]
0x140370127  mov     rcx, [rdx]
0x14037012a  mov     rax, qword ptr [rbp+100h+var_B0+8]
0x14037012e  mov     [rdx], rax
0x140370131  test    rcx, rcx
0x140370134  jz      short loc_140370143
0x140370136  mov     rax, [rcx]
0x140370139  mov     rax, [rax+10h]
0x14037013d  call    _guard_dispatch_icall
0x140370142  nop
0x140370143  mov     [rbp+100h+pv], r14
0x14037014a  mov     rcx, [rbp+100h+var_88]
0x14037014e  mov     rax, [rcx]
0x140370151  lea     rdx, [rbp+100h+pv]
0x140370158  mov     qword ptr [rbp+100h+var_B0], rdx
0x14037015c  mov     qword ptr [rbp+100h+var_B0+8], r14
0x140370160  mov     [rbp+100h+var_A0], 1
0x140370164  lea     rdx, [rbp+100h+var_B0+8]
0x140370168  mov     rax, [rax+18h]
0x14037016c  call    _guard_dispatch_icall
0x140370171  mov     rcx, [rbp+108h]; this
0x140370178  test    eax, eax
0x14037017a  js      loc_1403708E8
0x140370180  cmp     [rbp+100h+var_A0], r14b
0x140370184  jz      short loc_1403701B9
0x140370186  mov     r15, qword ptr [rbp+100h+var_B0+8]
0x14037018a  mov     rsi, qword ptr [rbp+100h+var_B0]
0x14037018e  mov     r14, [rsi]
0x140370191  test    r14, r14
0x140370194  jz      short loc_1403701AF
0x140370196  call    cs:__imp_GetLastError
0x14037019c  mov     ebx, eax
0x14037019e  mov     rcx, r14; pv
0x1403701a1  call    cs:__imp_CoTaskMemFree
0x1403701a7  mov     ecx, ebx; dwErrCode
0x1403701a9  call    cs:__imp_SetLastError
0x1403701af  mov     [rsi], r15
0x1403701b2  xor     r14d, r14d
0x1403701b5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1403701b9  mov     [rbp+100h+var_80], r14
0x1403701c0  mov     rcx, [rbp+100h+var_88]
0x1403701c4  mov     rax, [rcx]
0x1403701c7  lea     rdx, [rbp+100h+var_80]
0x1403701ce  mov     qword ptr [rbp+100h+var_B0], rdx
0x1403701d2  mov     qword ptr [rbp+100h+var_B0+8], r14
0x1403701d6  mov     [rbp+100h+var_A0], 1
0x1403701da  lea     rdx, [rbp+100h+var_B0+8]
0x1403701de  mov     rax, [rax+20h]
0x1403701e2  call    _guard_dispatch_icall
0x1403701e7  mov     rcx, [rbp+108h]; this
0x1403701ee  test    eax, eax
0x1403701f0  js      loc_140370981
0x1403701f6  cmp     [rbp+100h+var_A0], r14b
0x1403701fa  jz      short loc_14037021C
0x1403701fc  mov     rdx, qword ptr [rbp+100h+var_B0]
0x140370200  mov     rcx, [rdx]
0x140370203  mov     rax, qword ptr [rbp+100h+var_B0+8]
0x140370207  mov     [rdx], rax
0x14037020a  test    rcx, rcx
0x14037020d  jz      short loc_14037021C
0x14037020f  mov     rax, [rcx]
0x140370212  mov     rax, [rax+10h]
0x140370216  call    _guard_dispatch_icall
0x14037021b  nop
0x14037021c  mov     [rbp+100h+var_90], r14d
0x140370220  mov     rcx, [rbp+100h+var_80]
0x140370227  mov     rax, [rcx]
0x14037022a  lea     rdx, [rbp+100h+var_90]
0x14037022e  mov     rax, [rax+18h]
0x140370232  call    _guard_dispatch_icall
0x140370237  mov     rcx, [rbp+108h]; this
0x14037023e  test    eax, eax
0x140370240  js      loc_14037096C
0x140370246  cmp     [rbp+100h+var_90], r14d
0x14037024a  jnz     short loc_140370293
0x14037024c  mov     rcx, [rbp+100h+var_80]
0x140370253  test    rcx, rcx
0x140370256  jz      short loc_140370265
0x140370258  mov     rax, [rcx]
0x14037025b  mov     rax, [rax+10h]
0x14037025f  call    _guard_dispatch_icall
0x140370264  nop
0x140370265  mov     rcx, [rbp+100h+pv]; pv
0x14037026c  test    rcx, rcx
0x14037026f  jz      short loc_140370278
0x140370271  call    cs:__imp_CoTaskMemFree
0x140370277  nop
0x140370278  mov     rcx, [rbp+100h+var_88]
0x14037027c  test    rcx, rcx
0x14037027f  jz      short loc_14037028E
0x140370281  mov     rax, [rcx]
0x140370284  mov     rax, [rax+10h]
0x140370288  call    _guard_dispatch_icall
0x14037028d  nop
0x14037028e  jmp     loc_1403708A4
0x140370293  mov     [rsp+200h+var_1C0], r14b
0x140370298  mov     qword ptr [rbp+100h+var_B0], r14
0x14037029c  mov     rcx, [rbp+100h+var_88]
0x1403702a0  mov     rax, [rcx]
0x1403702a3  mov     qword ptr [rbp+100h+var_B0], r14
0x1403702a7  lea     r8, [rbp+100h+var_B0]
0x1403702ab  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x1403702b2  mov     rax, [rax+28h]
0x1403702b6  call    _guard_dispatch_icall
0x1403702bb  test    eax, eax
0x1403702bd  js      loc_140370364
0x1403702c3  mov     [rbp+100h+var_78], r14
0x1403702ca  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1403702ce  mov     rax, [rcx]
0x1403702d1  mov     [rbp+100h+var_78], r14
0x1403702d8  lea     rdx, [rbp+100h+var_78]
0x1403702df  mov     rax, [rax+20h]
0x1403702e3  call    _guard_dispatch_icall
0x1403702e8  mov     rcx, [rbp+108h]; this
0x1403702ef  test    eax, eax
0x1403702f1  js      loc_140370912
0x1403702f7  xorps   xmm0, xmm0
0x1403702fa  movups  xmmword ptr [rsp+200h+S1], xmm0
0x1403702ff  xorps   xmm1, xmm1
0x140370302  movdqu  xmmword ptr [rsp+200h+N], xmm1
0x140370308  mov     rdx, [rbp+100h+var_78]
0x14037030f  mov     r8, r15
0x140370312  inc     r8
0x140370315  cmp     [rdx+r8*2], r14w
0x14037031a  jnz     short loc_140370312
0x14037031c  lea     rcx, [rsp+200h+S1]
0x140370321  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140370326  nop
0x140370327  mov     r8d, 0Ah
0x14037032d  lea     rcx, [rsp+200h+S1]; String
0x140370332  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x140370337  mov     ebx, eax
0x140370339  lea     rcx, [rsp+200h+S1]
0x14037033e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140370343  nop
0x140370344  cmp     ebx, 1
0x140370347  setz    bl
0x14037034a  mov     [rsp+200h+var_1C0], bl
0x14037034e  mov     rcx, [rbp+100h+var_78]; pv
0x140370355  test    rcx, rcx
0x140370358  jz      short loc_140370364
0x14037035a  call    cs:__imp_CoTaskMemFree
0x140370360  mov     [rsp+200h+var_1C0], bl
0x140370364  mov     rcx, qword ptr [rbp+100h+var_B0]
0x140370368  test    rcx, rcx
0x14037036b  jz      short loc_14037037A
0x14037036d  mov     rax, [rcx]
0x140370370  mov     rax, [rax+10h]
0x140370374  call    _guard_dispatch_icall
0x140370379  nop
0x14037037a  mov     rbx, [rbp+100h+pv]
0x140370381  lea     rcx, [rbp+100h+var_180]
0x140370385  call    ??0?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@ABI@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::com_ptr_t<ABI::Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x14037038a  mov     [rbp+100h+var_178], rbx
0x14037038e  mov     rax, 0B000000000000000h
0x140370398  mov     [rbp+100h+var_180], rax
0x14037039c  lea     rax, aPn_0; "PN={}"
0x1403703a3  mov     qword ptr [rbp+100h+var_170], rax
0x1403703a7  mov     qword ptr [rbp+100h+var_170+8], 5
0x1403703af  mov     [rbp+100h+var_160], 1
0x1403703b7  lea     rax, [rbp+100h+var_180]
0x1403703bb  mov     [rbp+100h+var_158], rax
0x1403703bf  movaps  xmm0, [rbp+100h+var_170]
0x1403703c3  movdqa  [rbp+100h+var_B0], xmm0
0x1403703c8  lea     r8, [rbp+100h+var_160]
0x1403703cc  lea     rdx, [rbp+100h+var_B0]
0x1403703d0  lea     rcx, [rbp+100h+var_58]; Src
0x1403703d7  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x1403703dc  or      edi, 20h
0x1403703df  mov     [rsp+200h+var_1BC], edi
0x1403703e3  mov     r12d, r14d
0x1403703e6  cmp     [rbp+100h+var_90], r14d
0x1403703ea  jbe     loc_1403707CB
0x1403703f0  mov     qword ptr [rbp+100h+var_B0], r14
0x1403703f4  mov     rcx, [rbp+100h+var_80]
0x1403703fb  mov     rax, [rcx]
0x1403703fe  lea     rdx, [rbp+100h+var_B0]
0x140370402  mov     [rsp+200h+S1], rdx
0x140370407  mov     [rsp+200h+S1+8], r14
0x14037040c  mov     byte ptr [rsp+200h+N], 1
0x140370411  lea     r8, [rsp+200h+S1+8]
0x140370416  mov     edx, r12d
0x140370419  mov     rax, [rax+20h]
0x14037041d  call    _guard_dispatch_icall
0x140370422  mov     rcx, [rbp+108h]; this
0x140370429  test    eax, eax
0x14037042b  js      loc_140370951
0x140370431  cmp     byte ptr [rsp+200h+N], r14b
0x140370436  jz      short loc_14037045A
0x140370438  mov     rdx, [rsp+200h+S1]
0x14037043d  mov     rcx, [rdx]
0x140370440  mov     rax, [rsp+200h+S1+8]
0x140370445  mov     [rdx], rax
0x140370448  test    rcx, rcx
0x14037044b  jz      short loc_14037045A
0x14037044d  mov     rax, [rcx]
0x140370450  mov     rax, [rax+10h]
0x140370454  call    _guard_dispatch_icall
0x140370459  nop
0x14037045a  mov     [rbp+100h+var_68], r14
0x140370461  mov     rcx, qword ptr [rbp+100h+var_B0]
0x140370465  mov     rax, [rcx]
0x140370468  lea     rdx, [rbp+100h+var_68]
0x14037046f  mov     [rsp+200h+S1], rdx
0x140370474  mov     [rsp+200h+S1+8], r14
0x140370479  mov     byte ptr [rsp+200h+N], 1
0x14037047e  lea     rdx, [rsp+200h+S1+8]
0x140370483  mov     rax, [rax+18h]
0x140370487  call    _guard_dispatch_icall
0x14037048c  mov     rcx, [rbp+108h]; this
0x140370493  test    eax, eax
0x140370495  js      loc_14037093C
0x14037049b  cmp     byte ptr [rsp+200h+N], r14b
0x1403704a0  jz      short loc_1403704D3
0x1403704a2  mov     r15, [rsp+200h+S1+8]
0x1403704a7  mov     rsi, [rsp+200h+S1]
0x1403704ac  mov     r14, [rsi]
0x1403704af  test    r14, r14
0x1403704b2  jz      short loc_1403704CD
0x1403704b4  call    cs:__imp_GetLastError
0x1403704ba  mov     ebx, eax
0x1403704bc  mov     rcx, r14; pv
0x1403704bf  call    cs:__imp_CoTaskMemFree
0x1403704c5  mov     ecx, ebx; dwErrCode
0x1403704c7  call    cs:__imp_SetLastError
0x1403704cd  mov     [rsi], r15
0x1403704d0  xor     r14d, r14d
0x1403704d3  mov     [rbp+100h+var_70], r14
0x1403704da  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1403704de  mov     rax, [rcx]
0x1403704e1  lea     rdx, [rbp+100h+var_70]
0x1403704e8  mov     [rsp+200h+S1], rdx
0x1403704ed  mov     [rsp+200h+S1+8], r14
0x1403704f2  mov     byte ptr [rsp+200h+N], 1
0x1403704f7  lea     rdx, [rsp+200h+S1+8]
0x1403704fc  mov     rax, [rax+20h]
0x140370500  call    _guard_dispatch_icall
0x140370505  mov     rcx, [rbp+108h]; this
0x14037050c  test    eax, eax
0x14037050e  js      loc_140370927
0x140370514  cmp     byte ptr [rsp+200h+N], r14b
0x140370519  jz      short loc_14037054C
0x14037051b  mov     r15, [rsp+200h+S1+8]
0x140370520  mov     rsi, [rsp+200h+S1]
0x140370525  mov     r14, [rsi]
0x140370528  test    r14, r14
0x14037052b  jz      short loc_140370546
0x14037052d  call    cs:__imp_GetLastError
0x140370533  mov     ebx, eax
0x140370535  mov     rcx, r14; pv
0x140370538  call    cs:__imp_CoTaskMemFree
0x14037053e  mov     ecx, ebx; dwErrCode
0x140370540  call    cs:__imp_SetLastError
  ... truncated ...
```

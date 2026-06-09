# Windows::UsoProductEnumerator::GetPrimaryOsInfo(void)

- ea: `0x14036f70c`
- end: `0x14036fb58`
- name: `?GetPrimaryOsInfo@UsoProductEnumerator@Windows@@QEAA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@XZ`
- size: `1100`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14023e1e0`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x1400433b0`
- `0x140045404`
- `0x1400c695c`
- `0x1401156f8`
- `0x14030535c`
- `0x14036f70c`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f8c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f9a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f9ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fabf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036facf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f8c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f9a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036f9ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fabf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036facf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f930`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f9ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f930`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036f9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036f99b`

## string_xrefs

- `0x14036f76a`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int128 *__fastcall Windows::UsoProductEnumerator::GetPrimaryOsInfo(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rsi
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r8
  int v12; // ebx
  __int64 v13; // rdx
  __int64 *v14; // rbx
  __int64 (__fastcall *v15)(__int64 *, LPVOID *); // r15
  void *v16; // r14
  DWORD LastError; // edi
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, LPVOID *); // r15
  void *v25; // r14
  DWORD v26; // edi
  _WORD *v27; // rbx
  __int64 v28; // r8
  int v30; // [rsp+28h] [rbp-49h]
  _OWORD pExceptionObject[2]; // [rsp+48h] [rbp-29h] BYREF
  __int64 *v32; // [rsp+70h] [rbp-1h] BYREF
  __int64 *v33; // [rsp+78h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+Fh] BYREF
  LPVOID v35; // [rsp+88h] [rbp+17h] BYREF
  LPVOID v36; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v37; // [rsp+98h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v36 = 0;
  v35 = 0;
  v2 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_56;
  v3 = -1;
  while ( 1 )
  {
    v32 = 0;
    v4 = *(__int64 **)(a1 + 24);
    v5 = *v4;
    v32 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v5 + 32))(v4, v2, &v32);
    if ( v6 >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v6,
      v30);
LABEL_22:
    if ( v32 )
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    if ( ++v2 >= *(_DWORD *)a1 )
      goto LABEL_44;
  }
  v33 = 0;
  v7 = *v32;
  v33 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v7 + 40))(v32, L"PrimaryOSProduct", &v33);
  if ( wil::details::in1diag3::Log_IfFailedWithExpected(
         retaddr,
         (void *)0x47,
         (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
         (const char *)v8,
         1,
         0x80070002) < 0 )
  {
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    goto LABEL_22;
  }
  pv = 0;
  v9 = *v33;
  pv = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v9 + 32))(v33, &pv);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v10,
      v30);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    goto LABEL_22;
  }
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  std::wstring::_Construct<1,wchar_t const *>(pExceptionObject, pv, v11);
  v12 = std::stoi((wchar_t *)pExceptionObject);
  std::wstring::~wstring(pExceptionObject, v13);
  if ( v12 != 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    goto LABEL_22;
  }
  v14 = v32;
  v15 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v32 + 24);
  v16 = v36;
  if ( v36 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v16);
    SetLastError(LastError);
  }
  v36 = 0;
  v18 = v15(v14, &v36);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v18,
      v30);
  v37 = 0;
  v19 = *v32;
  v37 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v19 + 40))(v32, L"Version", &v37);
  v21 = retaddr;
  if ( v20 < 0 )
  {
    v22 = 87;
    goto LABEL_35;
  }
  v23 = v37;
  v24 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v37 + 32LL);
  v25 = v35;
  if ( v35 )
  {
    v26 = GetLastError();
    CoTaskMemFree(v25);
    SetLastError(v26);
  }
  v35 = 0;
  v20 = v24(v23, &v35);
  v21 = retaddr;
  if ( v20 < 0 )
  {
    v22 = 89;
LABEL_35:
    wil::details::in1diag3::_Log_Hr(
      v21,
      (void *)v22,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v20,
      v30);
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v33 )
    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  if ( v32 )
    (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
LABEL_44:
  if ( !v36 )
  {
LABEL_56:
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS product present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v27 = v35;
  if ( !v35 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS version present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  xmmword_14054AA70 = 0;
  qword_14054AA80 = 0;
  qword_14054AA88 = 0;
  v28 = -1;
  do
    ++v28;
  while ( *((_WORD *)v36 + v28) );
  std::wstring::_Construct<1,wchar_t const *>(&xmmword_14054AA70, v36, v28);
  xmmword_14054AA90 = 0;
  qword_14054AAA0 = 0;
  qword_14054AAA8 = 0;
  do
    ++v3;
  while ( v27[v3] );
  std::wstring::_Construct<1,wchar_t const *>(&xmmword_14054AA90, v27, v3);
  if ( v35 )
    CoTaskMemFree(v35);
  if ( v36 )
    CoTaskMemFree(v36);
  return &xmmword_14054AA70;
}

```

## disassembly

```asm
0x14036f70c  mov     rax, rsp
0x14036f70f  mov     [rax+10h], rbx
0x14036f713  mov     [rax+18h], rsi
0x14036f717  mov     [rax+20h], rdi
0x14036f71b  push    rbp
0x14036f71c  push    r12
0x14036f71e  push    r13
0x14036f720  push    r14
0x14036f722  push    r15
0x14036f724  lea     rbp, [rax-5Fh]
0x14036f728  sub     rsp, 0A0h
0x14036f72f  mov     rax, cs:__security_cookie
0x14036f736  xor     rax, rsp
0x14036f739  mov     [rbp+57h+var_28], rax
0x14036f73d  mov     r14, rcx
0x14036f740  mov     rax, [rbp+57h+var_90]
0x14036f744  mov     [rbp+57h+var_90], rax
0x14036f748  xor     r12d, r12d
0x14036f74b  lea     r15, xmmword_14054AA70
0x14036f752  mov     [rbp+57h+var_90], r15
0x14036f756  mov     [rbp+57h+var_38], r12
0x14036f75a  mov     [rbp+57h+var_40], r12
0x14036f75e  mov     edi, r12d
0x14036f761  cmp     [rcx], r12d
0x14036f764  jbe     loc_14036FB26
0x14036f76a  lea     r13, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14036f771  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14036f775  mov     [rbp+57h+var_58], r12
0x14036f779  mov     rcx, [r14+18h]
0x14036f77d  mov     rax, [rcx]
0x14036f780  mov     [rbp+57h+var_58], r12
0x14036f784  lea     r8, [rbp+57h+var_58]
0x14036f788  mov     edx, edi
0x14036f78a  mov     rax, [rax+20h]
0x14036f78e  call    _guard_dispatch_icall
0x14036f793  mov     rcx, [rbp+5Fh]; this
0x14036f797  test    eax, eax
0x14036f799  jns     short loc_14036F7B1
0x14036f79b  mov     r9d, eax; char *
0x14036f79e  mov     r8, r13; unsigned int
0x14036f7a1  mov     edx, 40h ; '@'; void *
0x14036f7a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036f7ab  nop
0x14036f7ac  jmp     loc_14036F8E3
0x14036f7b1  mov     [rbp+57h+var_50], r12
0x14036f7b5  mov     rcx, [rbp+57h+var_58]
0x14036f7b9  mov     rax, [rcx]
0x14036f7bc  mov     [rbp+57h+var_50], r12
0x14036f7c0  lea     r8, [rbp+57h+var_50]
0x14036f7c4  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x14036f7cb  mov     rax, [rax+28h]
0x14036f7cf  call    _guard_dispatch_icall
0x14036f7d4  mov     rcx, [rbp+5Fh]; this
0x14036f7d8  mov     [rsp+0C0h+var_98], 80070002h; unsigned int
0x14036f7e0  mov     [rsp+0C0h+var_A0], 1; int
0x14036f7e8  mov     r9d, eax; char *
0x14036f7eb  mov     r8, r13; unsigned int
0x14036f7ee  mov     edx, 47h ; 'G'; void *
0x14036f7f3  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x14036f7f8  test    eax, eax
0x14036f7fa  jns     short loc_14036F817
0x14036f7fc  mov     rcx, [rbp+57h+var_50]
0x14036f800  test    rcx, rcx
0x14036f803  jz      short loc_14036F812
0x14036f805  mov     rax, [rcx]
0x14036f808  mov     rax, [rax+10h]
0x14036f80c  call    _guard_dispatch_icall
0x14036f811  nop
0x14036f812  jmp     loc_14036F8E3
0x14036f817  mov     [rbp+57h+pv], r12
0x14036f81b  mov     rcx, [rbp+57h+var_50]
0x14036f81f  mov     rax, [rcx]
0x14036f822  mov     [rbp+57h+pv], r12
0x14036f826  lea     rdx, [rbp+57h+pv]
0x14036f82a  mov     rax, [rax+20h]
0x14036f82e  call    _guard_dispatch_icall
0x14036f833  mov     rcx, [rbp+5Fh]; this
0x14036f837  test    eax, eax
0x14036f839  jns     short loc_14036F874
0x14036f83b  mov     r9d, eax; char *
0x14036f83e  mov     r8, r13; unsigned int
0x14036f841  mov     edx, 4Dh ; 'M'; void *
0x14036f846  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036f84b  nop
0x14036f84c  mov     rcx, [rbp+57h+pv]; pv
0x14036f850  test    rcx, rcx
0x14036f853  jz      short loc_14036F85C
0x14036f855  call    cs:__imp_CoTaskMemFree
0x14036f85b  nop
0x14036f85c  mov     rcx, [rbp+57h+var_50]
0x14036f860  test    rcx, rcx
0x14036f863  jz      short loc_14036F872
0x14036f865  mov     rax, [rcx]
0x14036f868  mov     rax, [rax+10h]
0x14036f86c  call    _guard_dispatch_icall
0x14036f871  nop
0x14036f872  jmp     short loc_14036F8E3
0x14036f874  xorps   xmm0, xmm0
0x14036f877  movups  [rbp+57h+pExceptionObject], xmm0
0x14036f87b  xorps   xmm1, xmm1
0x14036f87e  movdqu  [rbp+57h+var_70], xmm1
0x14036f883  mov     rdx, [rbp+57h+pv]
0x14036f887  mov     r8, rsi
0x14036f88a  inc     r8
0x14036f88d  cmp     [rdx+r8*2], r12w
0x14036f892  jnz     short loc_14036F88A
0x14036f894  lea     rcx, [rbp+57h+pExceptionObject]
0x14036f898  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036f89d  nop
0x14036f89e  mov     r8d, 0Ah
0x14036f8a4  lea     rcx, [rbp+57h+pExceptionObject]; String
0x14036f8a8  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x14036f8ad  mov     ebx, eax
0x14036f8af  lea     rcx, [rbp+57h+pExceptionObject]
0x14036f8b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14036f8b8  cmp     ebx, 1
0x14036f8bb  jz      short loc_14036F909
0x14036f8bd  mov     rcx, [rbp+57h+pv]; pv
0x14036f8c1  test    rcx, rcx
0x14036f8c4  jz      short loc_14036F8CD
0x14036f8c6  call    cs:__imp_CoTaskMemFree
0x14036f8cc  nop
0x14036f8cd  mov     rcx, [rbp+57h+var_50]
0x14036f8d1  test    rcx, rcx
0x14036f8d4  jz      short loc_14036F8E3
0x14036f8d6  mov     rax, [rcx]
0x14036f8d9  mov     rax, [rax+10h]
0x14036f8dd  call    _guard_dispatch_icall
0x14036f8e2  nop
0x14036f8e3  mov     rcx, [rbp+57h+var_58]
0x14036f8e7  test    rcx, rcx
0x14036f8ea  jz      short loc_14036F8F9
0x14036f8ec  mov     rax, [rcx]
0x14036f8ef  mov     rax, [rax+10h]
0x14036f8f3  call    _guard_dispatch_icall
0x14036f8f8  nop
0x14036f8f9  inc     edi
0x14036f8fb  cmp     edi, [r14]
0x14036f8fe  jb      loc_14036F775
0x14036f904  jmp     loc_14036FA39
0x14036f909  mov     rbx, [rbp+57h+var_58]
0x14036f90d  mov     rax, [rbx]
0x14036f910  mov     r15, [rax+18h]
0x14036f914  mov     r14, [rbp+57h+var_38]
0x14036f918  test    r14, r14
0x14036f91b  jz      short loc_14036F936
0x14036f91d  call    cs:__imp_GetLastError
0x14036f923  mov     edi, eax
0x14036f925  mov     rcx, r14; pv
0x14036f928  call    cs:__imp_CoTaskMemFree
0x14036f92e  mov     ecx, edi; dwErrCode
0x14036f930  call    cs:__imp_SetLastError
0x14036f936  mov     [rbp+57h+var_38], r12
0x14036f93a  lea     rdx, [rbp+57h+var_38]
0x14036f93e  mov     rcx, rbx
0x14036f941  mov     rax, r15
0x14036f944  call    _guard_dispatch_icall
0x14036f949  mov     rcx, [rbp+5Fh]; this
0x14036f94d  test    eax, eax
0x14036f94f  js      loc_14036FB47
0x14036f955  mov     [rbp+57h+var_30], r12
0x14036f959  mov     rcx, [rbp+57h+var_58]
0x14036f95d  mov     rax, [rcx]
0x14036f960  mov     [rbp+57h+var_30], r12
0x14036f964  lea     r8, [rbp+57h+var_30]
0x14036f968  lea     rdx, aVersion_0; "Version"
0x14036f96f  mov     rax, [rax+28h]
0x14036f973  call    _guard_dispatch_icall
0x14036f978  mov     rcx, [rbp+5Fh]
0x14036f97c  test    eax, eax
0x14036f97e  jns     short loc_14036F987
0x14036f980  mov     edx, 57h ; 'W'
0x14036f985  jmp     short loc_14036F9D4
0x14036f987  mov     rbx, [rbp+57h+var_30]
0x14036f98b  mov     rax, [rbx]
0x14036f98e  mov     r15, [rax+20h]
0x14036f992  mov     r14, [rbp+57h+var_40]
0x14036f996  test    r14, r14
0x14036f999  jz      short loc_14036F9B4
0x14036f99b  call    cs:__imp_GetLastError
0x14036f9a1  mov     edi, eax
0x14036f9a3  mov     rcx, r14; pv
0x14036f9a6  call    cs:__imp_CoTaskMemFree
0x14036f9ac  mov     ecx, edi; dwErrCode
0x14036f9ae  call    cs:__imp_SetLastError
0x14036f9b4  mov     [rbp+57h+var_40], r12
0x14036f9b8  lea     rdx, [rbp+57h+var_40]
0x14036f9bc  mov     rcx, rbx
0x14036f9bf  mov     rax, r15
0x14036f9c2  call    _guard_dispatch_icall
0x14036f9c7  mov     rcx, [rbp+5Fh]; this
0x14036f9cb  test    eax, eax
0x14036f9cd  jns     short loc_14036F9E0
0x14036f9cf  mov     edx, 59h ; 'Y'; void *
0x14036f9d4  mov     r9d, eax; char *
0x14036f9d7  mov     r8, r13; unsigned int
0x14036f9da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036f9df  nop
0x14036f9e0  mov     rcx, [rbp+57h+var_30]
0x14036f9e4  test    rcx, rcx
0x14036f9e7  jz      short loc_14036F9F6
0x14036f9e9  mov     rax, [rcx]
0x14036f9ec  mov     rax, [rax+10h]
0x14036f9f0  call    _guard_dispatch_icall
0x14036f9f5  nop
0x14036f9f6  mov     rcx, [rbp+57h+pv]; pv
0x14036f9fa  test    rcx, rcx
0x14036f9fd  jz      short loc_14036FA06
0x14036f9ff  call    cs:__imp_CoTaskMemFree
0x14036fa05  nop
0x14036fa06  mov     rcx, [rbp+57h+var_50]
0x14036fa0a  test    rcx, rcx
0x14036fa0d  jz      short loc_14036FA1C
0x14036fa0f  mov     rax, [rcx]
0x14036fa12  mov     rax, [rax+10h]
0x14036fa16  call    _guard_dispatch_icall
0x14036fa1b  nop
0x14036fa1c  mov     rcx, [rbp+57h+var_58]
0x14036fa20  test    rcx, rcx
0x14036fa23  jz      short loc_14036FA32
0x14036fa25  mov     rax, [rcx]
0x14036fa28  mov     rax, [rax+10h]
0x14036fa2c  call    _guard_dispatch_icall
0x14036fa31  nop
0x14036fa32  lea     r15, xmmword_14054AA70
0x14036fa39  mov     rdx, [rbp+57h+var_38]
0x14036fa3d  test    rdx, rdx
0x14036fa40  jz      loc_14036FB26
0x14036fa46  mov     rbx, [rbp+57h+var_40]
0x14036fa4a  test    rbx, rbx
0x14036fa4d  jz      loc_14036FB05
0x14036fa53  xorps   xmm0, xmm0
0x14036fa56  movups  cs:xmmword_14054AA70, xmm0
0x14036fa5d  mov     cs:qword_14054AA80, r12
0x14036fa64  mov     cs:qword_14054AA88, r12
0x14036fa6b  mov     r8, rsi
0x14036fa6e  inc     r8
0x14036fa71  cmp     [rdx+r8*2], r12w
0x14036fa76  jnz     short loc_14036FA6E
0x14036fa78  mov     rcx, r15
0x14036fa7b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036fa80  nop
0x14036fa81  xorps   xmm0, xmm0
0x14036fa84  movups  cs:xmmword_14054AA90, xmm0
0x14036fa8b  mov     cs:qword_14054AAA0, r12
0x14036fa92  mov     cs:qword_14054AAA8, r12
0x14036fa99  inc     rsi
0x14036fa9c  cmp     [rbx+rsi*2], r12w
0x14036faa1  jnz     short loc_14036FA99
0x14036faa3  mov     r8, rsi
0x14036faa6  mov     rdx, rbx
0x14036faa9  lea     rcx, xmmword_14054AA90
0x14036fab0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036fab5  nop
0x14036fab6  mov     rcx, [rbp+57h+var_40]; pv
0x14036faba  test    rcx, rcx
0x14036fabd  jz      short loc_14036FAC6
0x14036fabf  call    cs:__imp_CoTaskMemFree
0x14036fac5  nop
0x14036fac6  mov     rcx, [rbp+57h+var_38]; pv
0x14036faca  test    rcx, rcx
0x14036facd  jz      short loc_14036FAD5
0x14036facf  call    cs:__imp_CoTaskMemFree
0x14036fad5  mov     rax, r15
0x14036fad8  mov     rcx, [rbp+57h+var_28]
0x14036fadc  xor     rcx, rsp; StackCookie
0x14036fadf  call    __security_check_cookie
0x14036fae4  lea     r11, [rsp+0C0h+var_20]
0x14036faec  mov     rbx, [r11+38h]
0x14036faf0  mov     rsi, [r11+40h]
0x14036faf4  mov     rdi, [r11+48h]
0x14036faf8  mov     rsp, r11
0x14036fafb  pop     r15
0x14036fafd  pop     r14
0x14036faff  pop     r13
0x14036fb01  pop     r12
0x14036fb03  pop     rbp
0x14036fb04  retn
0x14036fb05  lea     rdx, aNoOsVersionPre; "No OS version present."
0x14036fb0c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14036fb10  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14036fb15  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14036fb1c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14036fb20  call    _CxxThrowException
0x14036fb26  lea     rdx, aNoOsProductPre; "No OS product present."
0x14036fb2d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14036fb31  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14036fb36  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14036fb3d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14036fb41  call    _CxxThrowException
0x14036fb47  mov     r9d, eax; char *
0x14036fb4a  mov     r8, r13; unsigned int
0x14036fb4d  mov     edx, 54h ; 'T'; void *
0x14036fb52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

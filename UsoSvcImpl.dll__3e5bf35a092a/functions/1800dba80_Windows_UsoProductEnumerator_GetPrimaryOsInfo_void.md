# Windows::UsoProductEnumerator::GetPrimaryOsInfo(void)

- ea: `0x1800dba80`
- end: `0x1800dbec6`
- name: `?GetPrimaryOsInfo@UsoProductEnumerator@Windows@@QEAA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@XZ`
- size: `1094`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18008da10`

## callees

- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18002dd34`
- `0x18002e064`
- `0x18002e168`
- `0x1800b0948`
- `0x1800dba80`
- `0x1800dd930`
- `0x1800dff58`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbc8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbd09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbc8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbd09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbc9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbd1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbc9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dbd1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbbc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbc34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbd14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbd6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbe2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbe3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbbc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbc34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbc96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbd14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbd6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbe2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbe3d`

## string_xrefs

- `0x1800dbade`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

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
  __int64 *v13; // rbx
  __int64 (__fastcall *v14)(__int64 *, LPVOID *); // r15
  void *v15; // r14
  DWORD LastError; // edi
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, LPVOID *); // r15
  void *v24; // r14
  DWORD v25; // edi
  _WORD *v26; // rbx
  __int64 v27; // r8
  int v29; // [rsp+28h] [rbp-49h]
  _OWORD pExceptionObject[2]; // [rsp+48h] [rbp-29h] BYREF
  __int64 *v31; // [rsp+70h] [rbp-1h] BYREF
  __int64 *v32; // [rsp+78h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+Fh] BYREF
  LPVOID v34; // [rsp+88h] [rbp+17h] BYREF
  LPVOID v35; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v36; // [rsp+98h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v35 = 0;
  v34 = 0;
  v2 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_56;
  v3 = -1;
  while ( 1 )
  {
    v31 = 0;
    v4 = *(__int64 **)(a1 + 24);
    v5 = *v4;
    v31 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v5 + 32))(v4, v2, &v31);
    if ( v6 >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v6,
      v29);
LABEL_22:
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    if ( ++v2 >= *(_DWORD *)a1 )
      goto LABEL_44;
  }
  v32 = 0;
  v7 = *v31;
  v32 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v7 + 40))(v31, L"PrimaryOSProduct", &v32);
  if ( (int)wil::details::in1diag3::Log_IfFailedWithExpected(
              retaddr,
              (void *)0x47,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
              (const char *)v8,
              1,
              2) < 0 )
  {
    if ( v32 )
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    goto LABEL_22;
  }
  pv = 0;
  v9 = *v32;
  pv = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v9 + 32))(v32, &pv);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v10,
      v29);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v32 )
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    goto LABEL_22;
  }
  memset(pExceptionObject, 0, sizeof(pExceptionObject));
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  std::wstring::_Construct<1,wchar_t const *>(pExceptionObject);
  v12 = std::stoi((wchar_t *)pExceptionObject);
  std::wstring::~wstring(pExceptionObject);
  if ( v12 != 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v32 )
      (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
    goto LABEL_22;
  }
  v13 = v31;
  v14 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v31 + 24);
  v15 = v35;
  if ( v35 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v15);
    SetLastError(LastError);
  }
  v35 = 0;
  v17 = v14(v13, &v35);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v17,
      v29);
  v36 = 0;
  v18 = *v31;
  v36 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v18 + 40))(v31, L"Version", &v36);
  v20 = retaddr;
  if ( v19 < 0 )
  {
    v21 = 87;
    goto LABEL_35;
  }
  v22 = v36;
  v23 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v36 + 32LL);
  v24 = v34;
  if ( v34 )
  {
    v25 = GetLastError();
    CoTaskMemFree(v24);
    SetLastError(v25);
  }
  v34 = 0;
  v19 = v23(v22, &v34);
  v20 = retaddr;
  if ( v19 < 0 )
  {
    v21 = 89;
LABEL_35:
    wil::details::in1diag3::_Log_Hr(
      v20,
      (void *)v21,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v19,
      v29);
  }
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v32 )
    (*(void (__fastcall **)(__int64 *))(*v32 + 16))(v32);
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
LABEL_44:
  if ( !v35 )
  {
LABEL_56:
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS product present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v26 = v34;
  if ( !v34 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS version present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  xmmword_180150E20 = 0;
  qword_180150E30 = 0;
  qword_180150E38 = 0;
  v27 = -1;
  do
    ++v27;
  while ( *((_WORD *)v35 + v27) );
  std::wstring::_Construct<1,wchar_t const *>(&xmmword_180150E20);
  xmmword_180150E40 = 0;
  qword_180150E50 = 0;
  qword_180150E58 = 0;
  do
    ++v3;
  while ( v26[v3] );
  std::wstring::_Construct<1,wchar_t const *>(&xmmword_180150E40);
  if ( v34 )
    CoTaskMemFree(v34);
  if ( v35 )
    CoTaskMemFree(v35);
  return &xmmword_180150E20;
}

```

## disassembly

```asm
0x1800dba80  mov     rax, rsp
0x1800dba83  mov     [rax+10h], rbx
0x1800dba87  mov     [rax+18h], rsi
0x1800dba8b  mov     [rax+20h], rdi
0x1800dba8f  push    rbp
0x1800dba90  push    r12
0x1800dba92  push    r13
0x1800dba94  push    r14
0x1800dba96  push    r15
0x1800dba98  lea     rbp, [rax-5Fh]
0x1800dba9c  sub     rsp, 0A0h
0x1800dbaa3  mov     rax, cs:__security_cookie
0x1800dbaaa  xor     rax, rsp
0x1800dbaad  mov     [rbp+57h+var_28], rax
0x1800dbab1  mov     r14, rcx
0x1800dbab4  mov     rax, [rbp+57h+var_90]
0x1800dbab8  mov     [rbp+57h+var_90], rax
0x1800dbabc  xor     r12d, r12d
0x1800dbabf  lea     r15, xmmword_180150E20
0x1800dbac6  mov     [rbp+57h+var_90], r15
0x1800dbaca  mov     [rbp+57h+var_38], r12
0x1800dbace  mov     [rbp+57h+var_40], r12
0x1800dbad2  mov     edi, r12d
0x1800dbad5  cmp     [rcx], r12d
0x1800dbad8  jbe     loc_1800DBE94
0x1800dbade  lea     r13, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dbae5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800dbae9  mov     [rbp+57h+var_58], r12
0x1800dbaed  mov     rcx, [r14+18h]
0x1800dbaf1  mov     rax, [rcx]
0x1800dbaf4  mov     [rbp+57h+var_58], r12
0x1800dbaf8  lea     r8, [rbp+57h+var_58]
0x1800dbafc  mov     edx, edi
0x1800dbafe  mov     rax, [rax+20h]
0x1800dbb02  call    _guard_dispatch_icall
0x1800dbb07  mov     rcx, [rbp+5Fh]; this
0x1800dbb0b  test    eax, eax
0x1800dbb0d  jns     short loc_1800DBB25
0x1800dbb0f  mov     r9d, eax; char *
0x1800dbb12  mov     r8, r13; unsigned int
0x1800dbb15  mov     edx, 40h ; '@'; void *
0x1800dbb1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbb1f  nop
0x1800dbb20  jmp     loc_1800DBC51
0x1800dbb25  mov     [rbp+57h+var_50], r12
0x1800dbb29  mov     rcx, [rbp+57h+var_58]
0x1800dbb2d  mov     rax, [rcx]
0x1800dbb30  mov     [rbp+57h+var_50], r12
0x1800dbb34  lea     r8, [rbp+57h+var_50]
0x1800dbb38  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x1800dbb3f  mov     rax, [rax+28h]
0x1800dbb43  call    _guard_dispatch_icall
0x1800dbb48  mov     rcx, [rbp+5Fh]; this
0x1800dbb4c  mov     dword ptr [rsp+0C0h+var_98], 80070002h; char
0x1800dbb54  mov     [rsp+0C0h+var_A0], 1; int
0x1800dbb5c  mov     r9d, eax; char *
0x1800dbb5f  mov     r8, r13; unsigned int
0x1800dbb62  mov     edx, 47h ; 'G'; void *
0x1800dbb67  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800dbb6c  test    eax, eax
0x1800dbb6e  jns     short loc_1800DBB8B
0x1800dbb70  mov     rcx, [rbp+57h+var_50]
0x1800dbb74  test    rcx, rcx
0x1800dbb77  jz      short loc_1800DBB86
0x1800dbb79  mov     rax, [rcx]
0x1800dbb7c  mov     rax, [rax+10h]
0x1800dbb80  call    _guard_dispatch_icall
0x1800dbb85  nop
0x1800dbb86  jmp     loc_1800DBC51
0x1800dbb8b  mov     [rbp+57h+pv], r12
0x1800dbb8f  mov     rcx, [rbp+57h+var_50]
0x1800dbb93  mov     rax, [rcx]
0x1800dbb96  mov     [rbp+57h+pv], r12
0x1800dbb9a  lea     rdx, [rbp+57h+pv]
0x1800dbb9e  mov     rax, [rax+20h]
0x1800dbba2  call    _guard_dispatch_icall
0x1800dbba7  mov     rcx, [rbp+5Fh]; this
0x1800dbbab  test    eax, eax
0x1800dbbad  jns     short loc_1800DBBE8
0x1800dbbaf  mov     r9d, eax; char *
0x1800dbbb2  mov     r8, r13; unsigned int
0x1800dbbb5  mov     edx, 4Dh ; 'M'; void *
0x1800dbbba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbbbf  nop
0x1800dbbc0  mov     rcx, [rbp+57h+pv]; pv
0x1800dbbc4  test    rcx, rcx
0x1800dbbc7  jz      short loc_1800DBBD0
0x1800dbbc9  call    cs:__imp_CoTaskMemFree
0x1800dbbcf  nop
0x1800dbbd0  mov     rcx, [rbp+57h+var_50]
0x1800dbbd4  test    rcx, rcx
0x1800dbbd7  jz      short loc_1800DBBE6
0x1800dbbd9  mov     rax, [rcx]
0x1800dbbdc  mov     rax, [rax+10h]
0x1800dbbe0  call    _guard_dispatch_icall
0x1800dbbe5  nop
0x1800dbbe6  jmp     short loc_1800DBC51
0x1800dbbe8  xorps   xmm0, xmm0
0x1800dbbeb  movups  [rbp+57h+pExceptionObject], xmm0
0x1800dbbef  xorps   xmm1, xmm1
0x1800dbbf2  movdqu  [rbp+57h+var_70], xmm1
0x1800dbbf7  mov     rdx, [rbp+57h+pv]
0x1800dbbfb  mov     r8, rsi
0x1800dbbfe  inc     r8
0x1800dbc01  cmp     [rdx+r8*2], r12w
0x1800dbc06  jnz     short loc_1800DBBFE
0x1800dbc08  lea     rcx, [rbp+57h+pExceptionObject]
0x1800dbc0c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dbc11  nop
0x1800dbc12  lea     rcx, [rbp+57h+pExceptionObject]; String
0x1800dbc16  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x1800dbc1b  mov     ebx, eax
0x1800dbc1d  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x1800dbc21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dbc26  cmp     ebx, 1
0x1800dbc29  jz      short loc_1800DBC77
0x1800dbc2b  mov     rcx, [rbp+57h+pv]; pv
0x1800dbc2f  test    rcx, rcx
0x1800dbc32  jz      short loc_1800DBC3B
0x1800dbc34  call    cs:__imp_CoTaskMemFree
0x1800dbc3a  nop
0x1800dbc3b  mov     rcx, [rbp+57h+var_50]
0x1800dbc3f  test    rcx, rcx
0x1800dbc42  jz      short loc_1800DBC51
0x1800dbc44  mov     rax, [rcx]
0x1800dbc47  mov     rax, [rax+10h]
0x1800dbc4b  call    _guard_dispatch_icall
0x1800dbc50  nop
0x1800dbc51  mov     rcx, [rbp+57h+var_58]
0x1800dbc55  test    rcx, rcx
0x1800dbc58  jz      short loc_1800DBC67
0x1800dbc5a  mov     rax, [rcx]
0x1800dbc5d  mov     rax, [rax+10h]
0x1800dbc61  call    _guard_dispatch_icall
0x1800dbc66  nop
0x1800dbc67  inc     edi
0x1800dbc69  cmp     edi, [r14]
0x1800dbc6c  jb      loc_1800DBAE9
0x1800dbc72  jmp     loc_1800DBDA7
0x1800dbc77  mov     rbx, [rbp+57h+var_58]
0x1800dbc7b  mov     rax, [rbx]
0x1800dbc7e  mov     r15, [rax+18h]
0x1800dbc82  mov     r14, [rbp+57h+var_38]
0x1800dbc86  test    r14, r14
0x1800dbc89  jz      short loc_1800DBCA4
0x1800dbc8b  call    cs:__imp_GetLastError
0x1800dbc91  mov     edi, eax
0x1800dbc93  mov     rcx, r14; pv
0x1800dbc96  call    cs:__imp_CoTaskMemFree
0x1800dbc9c  mov     ecx, edi; dwErrCode
0x1800dbc9e  call    cs:__imp_SetLastError
0x1800dbca4  mov     [rbp+57h+var_38], r12
0x1800dbca8  lea     rdx, [rbp+57h+var_38]
0x1800dbcac  mov     rcx, rbx
0x1800dbcaf  mov     rax, r15
0x1800dbcb2  call    _guard_dispatch_icall
0x1800dbcb7  mov     rcx, [rbp+5Fh]; this
0x1800dbcbb  test    eax, eax
0x1800dbcbd  js      loc_1800DBEB5
0x1800dbcc3  mov     [rbp+57h+var_30], r12
0x1800dbcc7  mov     rcx, [rbp+57h+var_58]
0x1800dbccb  mov     rax, [rcx]
0x1800dbcce  mov     [rbp+57h+var_30], r12
0x1800dbcd2  lea     r8, [rbp+57h+var_30]
0x1800dbcd6  lea     rdx, aVersion_0; "Version"
0x1800dbcdd  mov     rax, [rax+28h]
0x1800dbce1  call    _guard_dispatch_icall
0x1800dbce6  mov     rcx, [rbp+5Fh]
0x1800dbcea  test    eax, eax
0x1800dbcec  jns     short loc_1800DBCF5
0x1800dbcee  mov     edx, 57h ; 'W'
0x1800dbcf3  jmp     short loc_1800DBD42
0x1800dbcf5  mov     rbx, [rbp+57h+var_30]
0x1800dbcf9  mov     rax, [rbx]
0x1800dbcfc  mov     r15, [rax+20h]
0x1800dbd00  mov     r14, [rbp+57h+var_40]
0x1800dbd04  test    r14, r14
0x1800dbd07  jz      short loc_1800DBD22
0x1800dbd09  call    cs:__imp_GetLastError
0x1800dbd0f  mov     edi, eax
0x1800dbd11  mov     rcx, r14; pv
0x1800dbd14  call    cs:__imp_CoTaskMemFree
0x1800dbd1a  mov     ecx, edi; dwErrCode
0x1800dbd1c  call    cs:__imp_SetLastError
0x1800dbd22  mov     [rbp+57h+var_40], r12
0x1800dbd26  lea     rdx, [rbp+57h+var_40]
0x1800dbd2a  mov     rcx, rbx
0x1800dbd2d  mov     rax, r15
0x1800dbd30  call    _guard_dispatch_icall
0x1800dbd35  mov     rcx, [rbp+5Fh]; this
0x1800dbd39  test    eax, eax
0x1800dbd3b  jns     short loc_1800DBD4E
0x1800dbd3d  mov     edx, 59h ; 'Y'; void *
0x1800dbd42  mov     r9d, eax; char *
0x1800dbd45  mov     r8, r13; unsigned int
0x1800dbd48  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbd4d  nop
0x1800dbd4e  mov     rcx, [rbp+57h+var_30]
0x1800dbd52  test    rcx, rcx
0x1800dbd55  jz      short loc_1800DBD64
0x1800dbd57  mov     rax, [rcx]
0x1800dbd5a  mov     rax, [rax+10h]
0x1800dbd5e  call    _guard_dispatch_icall
0x1800dbd63  nop
0x1800dbd64  mov     rcx, [rbp+57h+pv]; pv
0x1800dbd68  test    rcx, rcx
0x1800dbd6b  jz      short loc_1800DBD74
0x1800dbd6d  call    cs:__imp_CoTaskMemFree
0x1800dbd73  nop
0x1800dbd74  mov     rcx, [rbp+57h+var_50]
0x1800dbd78  test    rcx, rcx
0x1800dbd7b  jz      short loc_1800DBD8A
0x1800dbd7d  mov     rax, [rcx]
0x1800dbd80  mov     rax, [rax+10h]
0x1800dbd84  call    _guard_dispatch_icall
0x1800dbd89  nop
0x1800dbd8a  mov     rcx, [rbp+57h+var_58]
0x1800dbd8e  test    rcx, rcx
0x1800dbd91  jz      short loc_1800DBDA0
0x1800dbd93  mov     rax, [rcx]
0x1800dbd96  mov     rax, [rax+10h]
0x1800dbd9a  call    _guard_dispatch_icall
0x1800dbd9f  nop
0x1800dbda0  lea     r15, xmmword_180150E20
0x1800dbda7  mov     rdx, [rbp+57h+var_38]
0x1800dbdab  test    rdx, rdx
0x1800dbdae  jz      loc_1800DBE94
0x1800dbdb4  mov     rbx, [rbp+57h+var_40]
0x1800dbdb8  test    rbx, rbx
0x1800dbdbb  jz      loc_1800DBE73
0x1800dbdc1  xorps   xmm0, xmm0
0x1800dbdc4  movups  cs:xmmword_180150E20, xmm0
0x1800dbdcb  mov     cs:qword_180150E30, r12
0x1800dbdd2  mov     cs:qword_180150E38, r12
0x1800dbdd9  mov     r8, rsi
0x1800dbddc  inc     r8
0x1800dbddf  cmp     [rdx+r8*2], r12w
0x1800dbde4  jnz     short loc_1800DBDDC
0x1800dbde6  mov     rcx, r15
0x1800dbde9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dbdee  nop
0x1800dbdef  xorps   xmm0, xmm0
0x1800dbdf2  movups  cs:xmmword_180150E40, xmm0
0x1800dbdf9  mov     cs:qword_180150E50, r12
0x1800dbe00  mov     cs:qword_180150E58, r12
0x1800dbe07  inc     rsi
0x1800dbe0a  cmp     [rbx+rsi*2], r12w
0x1800dbe0f  jnz     short loc_1800DBE07
0x1800dbe11  mov     r8, rsi
0x1800dbe14  mov     rdx, rbx
0x1800dbe17  lea     rcx, xmmword_180150E40
0x1800dbe1e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dbe23  nop
0x1800dbe24  mov     rcx, [rbp+57h+var_40]; pv
0x1800dbe28  test    rcx, rcx
0x1800dbe2b  jz      short loc_1800DBE34
0x1800dbe2d  call    cs:__imp_CoTaskMemFree
0x1800dbe33  nop
0x1800dbe34  mov     rcx, [rbp+57h+var_38]; pv
0x1800dbe38  test    rcx, rcx
0x1800dbe3b  jz      short loc_1800DBE43
0x1800dbe3d  call    cs:__imp_CoTaskMemFree
0x1800dbe43  mov     rax, r15
0x1800dbe46  mov     rcx, [rbp+57h+var_28]
0x1800dbe4a  xor     rcx, rsp; StackCookie
0x1800dbe4d  call    __security_check_cookie
0x1800dbe52  lea     r11, [rsp+0C0h+var_20]
0x1800dbe5a  mov     rbx, [r11+38h]
0x1800dbe5e  mov     rsi, [r11+40h]
0x1800dbe62  mov     rdi, [r11+48h]
0x1800dbe66  mov     rsp, r11
0x1800dbe69  pop     r15
0x1800dbe6b  pop     r14
0x1800dbe6d  pop     r13
0x1800dbe6f  pop     r12
0x1800dbe71  pop     rbp
0x1800dbe72  retn
0x1800dbe73  lea     rdx, aNoOsVersionPre; "No OS version present."
0x1800dbe7a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800dbe7e  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800dbe83  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800dbe8a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800dbe8e  call    _CxxThrowException
0x1800dbe94  lea     rdx, aNoOsProductPre; "No OS product present."
0x1800dbe9b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800dbe9f  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800dbea4  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800dbeab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800dbeaf  call    _CxxThrowException
0x1800dbeb5  mov     r9d, eax; char *
0x1800dbeb8  mov     r8, r13; unsigned int
0x1800dbebb  mov     edx, 54h ; 'T'; void *
0x1800dbec0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

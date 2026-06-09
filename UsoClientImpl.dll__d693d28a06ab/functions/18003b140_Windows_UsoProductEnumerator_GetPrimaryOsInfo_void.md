# Windows::UsoProductEnumerator::GetPrimaryOsInfo(void)

- ea: `0x18003b140`
- end: `0x18003b55c`
- name: `?GetPrimaryOsInfo@UsoProductEnumerator@Windows@@QEAA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@XZ`
- size: `1052`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180009380`
- `0x1800338a4`
- `0x1800345b0`
- `0x180034a30`
- `0x18003b140`
- `0x18003b914`
- `0x18003b9a8`
- `0x18003ba14`
- `0x180056500`
- `0x180058abc`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b33d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b3bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003b3ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b27b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b3c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b27b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b2e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b3c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b423`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4d5`

## string_xrefs

- `0x18003b1b8`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b209`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b260`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b3f7`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x18003b54a`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::UsoProductEnumerator::GetPrimaryOsInfo(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // r14
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r8
  int v14; // ebx
  __int64 *v15; // rbx
  __int64 (__fastcall *v16)(__int64 *, LPVOID *); // r12
  void *v17; // r15
  DWORD LastError; // edi
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, LPVOID *); // r12
  void *v26; // r15
  DWORD v27; // edi
  _WORD *v28; // rdx
  _WORD *v29; // rbx
  __int64 v30; // r8
  int v32; // [rsp+20h] [rbp-69h]
  _OWORD pExceptionObject[3]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v34; // [rsp+60h] [rbp-29h]
  __int64 *v35; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v36; // [rsp+78h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-9h] BYREF
  LPVOID v38; // [rsp+88h] [rbp-1h] BYREF
  LPVOID v39; // [rsp+90h] [rbp+7h] BYREF
  __int64 v40; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v34 = a2;
  v39 = 0;
  v38 = 0;
  v4 = 0;
  if ( !*(_DWORD *)a1 )
    goto LABEL_56;
  v5 = -1;
  while ( 1 )
  {
    v35 = 0;
    v6 = *(__int64 **)(a1 + 24);
    v7 = *v6;
    v35 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v7 + 32))(v6, v4, &v35);
    if ( v8 >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v8,
      v32);
LABEL_22:
    if ( v35 )
      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
    if ( ++v4 >= *(_DWORD *)a1 )
      goto LABEL_44;
  }
  v36 = 0;
  v9 = *v35;
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v9 + 40))(v35, L"PrimaryOSProduct", &v36);
  if ( (int)wil::details::in1diag3::Log_IfFailedWithExpected(
              retaddr,
              (void *)0x47,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
              (const char *)v10,
              1,
              2) < 0 )
  {
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    goto LABEL_22;
  }
  pv = 0;
  v11 = *v36;
  pv = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v11 + 32))(v36, &pv);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v12,
      v32);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    goto LABEL_22;
  }
  memset(pExceptionObject, 0, 32);
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)pv + v13) );
  std::wstring::_Construct<1,wchar_t const *>(pExceptionObject);
  v14 = std::stoi((wchar_t *)pExceptionObject);
  std::wstring::~wstring(pExceptionObject);
  if ( v14 != 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v36 )
      (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    goto LABEL_22;
  }
  v15 = v35;
  v16 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v35 + 24);
  v17 = v39;
  if ( v39 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v17);
    SetLastError(LastError);
  }
  v39 = 0;
  v19 = v16(v15, &v39);
  if ( v19 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v19,
      v32);
  v40 = 0;
  v20 = *v35;
  v40 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v20 + 40))(v35, L"Version", &v40);
  v22 = retaddr;
  if ( v21 < 0 )
  {
    v23 = 87;
    goto LABEL_35;
  }
  v24 = v40;
  v25 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 32LL);
  v26 = v38;
  if ( v38 )
  {
    v27 = GetLastError();
    CoTaskMemFree(v26);
    SetLastError(v27);
  }
  v38 = 0;
  v21 = v25(v24, &v38);
  v22 = retaddr;
  if ( v21 < 0 )
  {
    v23 = 89;
LABEL_35:
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v21,
      v32);
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v36 )
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
  if ( v35 )
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
LABEL_44:
  v28 = v39;
  if ( !v39 )
  {
LABEL_56:
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS product present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v29 = v38;
  if ( !v38 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "No OS version present.");
    throw (std::runtime_error *)pExceptionObject;
  }
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  v30 = -1;
  do
    ++v30;
  while ( v28[v30] );
  std::wstring::_Construct<1,wchar_t const *>(a2);
  *(_OWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  *(_QWORD *)(a2 + 56) = 0;
  do
    ++v5;
  while ( v29[v5] );
  std::wstring::_Construct<1,wchar_t const *>(a2 + 32);
  if ( v38 )
    CoTaskMemFree(v38);
  if ( v39 )
    CoTaskMemFree(v39);
  return a2;
}

```

## disassembly

```asm
0x18003b140  mov     [rsp-8+arg_10], rbx
0x18003b145  push    rbp
0x18003b146  push    rsi
0x18003b147  push    rdi
0x18003b148  push    r12
0x18003b14a  push    r13
0x18003b14c  push    r14
0x18003b14e  push    r15
0x18003b150  lea     rbp, [rsp-27h]
0x18003b155  sub     rsp, 0B0h
0x18003b15c  mov     rax, cs:__security_cookie
0x18003b163  xor     rax, rsp
0x18003b166  mov     [rbp+57h+var_40], rax
0x18003b16a  mov     rsi, rdx
0x18003b16d  mov     r15, rcx
0x18003b170  mov     [rbp+57h+var_80], rdx
0x18003b174  xor     r13d, r13d
0x18003b177  mov     [rbp+57h+var_50], r13
0x18003b17b  mov     [rbp+57h+var_58], r13
0x18003b17f  mov     edi, r13d
0x18003b182  cmp     [rcx], r13d
0x18003b185  jbe     loc_18003B526
0x18003b18b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003b18f  mov     [rbp+57h+var_70], r13
0x18003b193  mov     rcx, [r15+18h]
0x18003b197  mov     rax, [rcx]
0x18003b19a  mov     [rbp+57h+var_70], r13
0x18003b19e  lea     r8, [rbp+57h+var_70]
0x18003b1a2  mov     edx, edi
0x18003b1a4  mov     rax, [rax+20h]
0x18003b1a8  call    _guard_dispatch_icall
0x18003b1ad  mov     rcx, [rbp+5Fh]; this
0x18003b1b1  test    eax, eax
0x18003b1b3  jns     short loc_18003B1CF
0x18003b1b5  mov     r9d, eax; char *
0x18003b1b8  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b1bf  mov     edx, 40h ; '@'; void *
0x18003b1c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b1c9  nop
0x18003b1ca  jmp     loc_18003B303
0x18003b1cf  mov     [rbp+57h+var_68], r13
0x18003b1d3  mov     rcx, [rbp+57h+var_70]
0x18003b1d7  mov     rax, [rcx]
0x18003b1da  mov     [rbp+57h+var_68], r13
0x18003b1de  lea     r8, [rbp+57h+var_68]
0x18003b1e2  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x18003b1e9  mov     rax, [rax+28h]
0x18003b1ed  call    _guard_dispatch_icall
0x18003b1f2  mov     rcx, [rbp+5Fh]; this
0x18003b1f6  mov     dword ptr [rsp+0E0h+var_B8], 80070002h; char
0x18003b1fe  mov     [rsp+0E0h+var_C0], 1; int
0x18003b206  mov     r9d, eax; char *
0x18003b209  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b210  mov     edx, 47h ; 'G'; void *
0x18003b215  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x18003b21a  test    eax, eax
0x18003b21c  jns     short loc_18003B239
0x18003b21e  mov     rcx, [rbp+57h+var_68]
0x18003b222  test    rcx, rcx
0x18003b225  jz      short loc_18003B234
0x18003b227  mov     rax, [rcx]
0x18003b22a  mov     rax, [rax+10h]
0x18003b22e  call    _guard_dispatch_icall
0x18003b233  nop
0x18003b234  jmp     loc_18003B303
0x18003b239  mov     [rbp+57h+pv], r13
0x18003b23d  mov     rcx, [rbp+57h+var_68]
0x18003b241  mov     rax, [rcx]
0x18003b244  mov     [rbp+57h+pv], r13
0x18003b248  lea     rdx, [rbp+57h+pv]
0x18003b24c  mov     rax, [rax+20h]
0x18003b250  call    _guard_dispatch_icall
0x18003b255  mov     rcx, [rbp+5Fh]; this
0x18003b259  test    eax, eax
0x18003b25b  jns     short loc_18003B29A
0x18003b25d  mov     r9d, eax; char *
0x18003b260  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b267  mov     edx, 4Dh ; 'M'; void *
0x18003b26c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b271  nop
0x18003b272  mov     rcx, [rbp+57h+pv]; pv
0x18003b276  test    rcx, rcx
0x18003b279  jz      short loc_18003B282
0x18003b27b  call    cs:__imp_CoTaskMemFree
0x18003b281  nop
0x18003b282  mov     rcx, [rbp+57h+var_68]
0x18003b286  test    rcx, rcx
0x18003b289  jz      short loc_18003B298
0x18003b28b  mov     rax, [rcx]
0x18003b28e  mov     rax, [rax+10h]
0x18003b292  call    _guard_dispatch_icall
0x18003b297  nop
0x18003b298  jmp     short loc_18003B303
0x18003b29a  xorps   xmm0, xmm0
0x18003b29d  movups  [rbp+57h+pExceptionObject], xmm0
0x18003b2a1  xorps   xmm1, xmm1
0x18003b2a4  movdqu  [rbp+57h+var_A0], xmm1
0x18003b2a9  mov     rdx, [rbp+57h+pv]
0x18003b2ad  mov     r8, r14
0x18003b2b0  inc     r8
0x18003b2b3  cmp     [rdx+r8*2], r13w
0x18003b2b8  jnz     short loc_18003B2B0
0x18003b2ba  lea     rcx, [rbp+57h+pExceptionObject]
0x18003b2be  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003b2c3  nop
0x18003b2c4  lea     rcx, [rbp+57h+pExceptionObject]; String
0x18003b2c8  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x18003b2cd  mov     ebx, eax
0x18003b2cf  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x18003b2d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003b2d8  cmp     ebx, 1
0x18003b2db  jz      short loc_18003B329
0x18003b2dd  mov     rcx, [rbp+57h+pv]; pv
0x18003b2e1  test    rcx, rcx
0x18003b2e4  jz      short loc_18003B2ED
0x18003b2e6  call    cs:__imp_CoTaskMemFree
0x18003b2ec  nop
0x18003b2ed  mov     rcx, [rbp+57h+var_68]
0x18003b2f1  test    rcx, rcx
0x18003b2f4  jz      short loc_18003B303
0x18003b2f6  mov     rax, [rcx]
0x18003b2f9  mov     rax, [rax+10h]
0x18003b2fd  call    _guard_dispatch_icall
0x18003b302  nop
0x18003b303  mov     rcx, [rbp+57h+var_70]
0x18003b307  test    rcx, rcx
0x18003b30a  jz      short loc_18003B319
0x18003b30c  mov     rax, [rcx]
0x18003b30f  mov     rax, [rax+10h]
0x18003b313  call    _guard_dispatch_icall
0x18003b318  nop
0x18003b319  inc     edi
0x18003b31b  cmp     edi, [r15]
0x18003b31e  jb      loc_18003B18F
0x18003b324  jmp     loc_18003B456
0x18003b329  mov     rbx, [rbp+57h+var_70]
0x18003b32d  mov     rax, [rbx]
0x18003b330  mov     r12, [rax+18h]
0x18003b334  mov     r15, [rbp+57h+var_50]
0x18003b338  test    r15, r15
0x18003b33b  jz      short loc_18003B356
0x18003b33d  call    cs:__imp_GetLastError
0x18003b343  mov     edi, eax
0x18003b345  mov     rcx, r15; pv
0x18003b348  call    cs:__imp_CoTaskMemFree
0x18003b34e  mov     ecx, edi; dwErrCode
0x18003b350  call    cs:__imp_SetLastError
0x18003b356  mov     [rbp+57h+var_50], r13
0x18003b35a  lea     rdx, [rbp+57h+var_50]
0x18003b35e  mov     rcx, rbx
0x18003b361  mov     rax, r12
0x18003b364  call    _guard_dispatch_icall
0x18003b369  mov     rcx, [rbp+5Fh]; this
0x18003b36d  test    eax, eax
0x18003b36f  js      loc_18003B547
0x18003b375  mov     [rbp+57h+var_48], r13
0x18003b379  mov     rcx, [rbp+57h+var_70]
0x18003b37d  mov     rax, [rcx]
0x18003b380  mov     [rbp+57h+var_48], r13
0x18003b384  lea     r8, [rbp+57h+var_48]
0x18003b388  lea     rdx, aVersion_0; "Version"
0x18003b38f  mov     rax, [rax+28h]
0x18003b393  call    _guard_dispatch_icall
0x18003b398  mov     rcx, [rbp+5Fh]
0x18003b39c  test    eax, eax
0x18003b39e  jns     short loc_18003B3A7
0x18003b3a0  mov     edx, 57h ; 'W'
0x18003b3a5  jmp     short loc_18003B3F4
0x18003b3a7  mov     rbx, [rbp+57h+var_48]
0x18003b3ab  mov     rax, [rbx]
0x18003b3ae  mov     r12, [rax+20h]
0x18003b3b2  mov     r15, [rbp+57h+var_58]
0x18003b3b6  test    r15, r15
0x18003b3b9  jz      short loc_18003B3D4
0x18003b3bb  call    cs:__imp_GetLastError
0x18003b3c1  mov     edi, eax
0x18003b3c3  mov     rcx, r15; pv
0x18003b3c6  call    cs:__imp_CoTaskMemFree
0x18003b3cc  mov     ecx, edi; dwErrCode
0x18003b3ce  call    cs:__imp_SetLastError
0x18003b3d4  mov     [rbp+57h+var_58], r13
0x18003b3d8  lea     rdx, [rbp+57h+var_58]
0x18003b3dc  mov     rcx, rbx
0x18003b3df  mov     rax, r12
0x18003b3e2  call    _guard_dispatch_icall
0x18003b3e7  mov     rcx, [rbp+5Fh]; this
0x18003b3eb  test    eax, eax
0x18003b3ed  jns     short loc_18003B404
0x18003b3ef  mov     edx, 59h ; 'Y'; void *
0x18003b3f4  mov     r9d, eax; char *
0x18003b3f7  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b3fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b403  nop
0x18003b404  mov     rcx, [rbp+57h+var_48]
0x18003b408  test    rcx, rcx
0x18003b40b  jz      short loc_18003B41A
0x18003b40d  mov     rax, [rcx]
0x18003b410  mov     rax, [rax+10h]
0x18003b414  call    _guard_dispatch_icall
0x18003b419  nop
0x18003b41a  mov     rcx, [rbp+57h+pv]; pv
0x18003b41e  test    rcx, rcx
0x18003b421  jz      short loc_18003B42A
0x18003b423  call    cs:__imp_CoTaskMemFree
0x18003b429  nop
0x18003b42a  mov     rcx, [rbp+57h+var_68]
0x18003b42e  test    rcx, rcx
0x18003b431  jz      short loc_18003B440
0x18003b433  mov     rax, [rcx]
0x18003b436  mov     rax, [rax+10h]
0x18003b43a  call    _guard_dispatch_icall
0x18003b43f  nop
0x18003b440  mov     rcx, [rbp+57h+var_70]
0x18003b444  test    rcx, rcx
0x18003b447  jz      short loc_18003B456
0x18003b449  mov     rax, [rcx]
0x18003b44c  mov     rax, [rax+10h]
0x18003b450  call    _guard_dispatch_icall
0x18003b455  nop
0x18003b456  mov     rdx, [rbp+57h+var_50]
0x18003b45a  test    rdx, rdx
0x18003b45d  jz      loc_18003B526
0x18003b463  mov     rbx, [rbp+57h+var_58]
0x18003b467  test    rbx, rbx
0x18003b46a  jz      loc_18003B505
0x18003b470  xorps   xmm0, xmm0
0x18003b473  movups  xmmword ptr [rsi], xmm0
0x18003b476  mov     [rsi+10h], r13
0x18003b47a  mov     [rsi+18h], r13
0x18003b47e  mov     r8, r14
0x18003b481  inc     r8
0x18003b484  cmp     [rdx+r8*2], r13w
0x18003b489  jnz     short loc_18003B481
0x18003b48b  mov     rcx, rsi
0x18003b48e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003b493  nop
0x18003b494  lea     rcx, [rsi+20h]
0x18003b498  xorps   xmm0, xmm0
0x18003b49b  movups  xmmword ptr [rcx], xmm0
0x18003b49e  mov     [rcx+10h], r13
0x18003b4a2  mov     [rcx+18h], r13
0x18003b4a6  inc     r14
0x18003b4a9  cmp     [rbx+r14*2], r13w
0x18003b4ae  jnz     short loc_18003B4A6
0x18003b4b0  mov     r8, r14
0x18003b4b3  mov     rdx, rbx
0x18003b4b6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003b4bb  nop
0x18003b4bc  mov     rcx, [rbp+57h+var_58]; pv
0x18003b4c0  test    rcx, rcx
0x18003b4c3  jz      short loc_18003B4CC
0x18003b4c5  call    cs:__imp_CoTaskMemFree
0x18003b4cb  nop
0x18003b4cc  mov     rcx, [rbp+57h+var_50]; pv
0x18003b4d0  test    rcx, rcx
0x18003b4d3  jz      short loc_18003B4DB
0x18003b4d5  call    cs:__imp_CoTaskMemFree
0x18003b4db  mov     rax, rsi
0x18003b4de  mov     rcx, [rbp+57h+var_40]
0x18003b4e2  xor     rcx, rsp; StackCookie
0x18003b4e5  call    __security_check_cookie
0x18003b4ea  mov     rbx, [rsp+0E0h+arg_10]
0x18003b4f2  add     rsp, 0B0h
0x18003b4f9  pop     r15
0x18003b4fb  pop     r14
0x18003b4fd  pop     r13
0x18003b4ff  pop     r12
0x18003b501  pop     rdi
0x18003b502  pop     rsi
0x18003b503  pop     rbp
0x18003b504  retn
0x18003b505  lea     rdx, aNoOsVersionPre; "No OS version present."
0x18003b50c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003b510  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003b515  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003b51c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003b520  call    _CxxThrowException
0x18003b526  lea     rdx, aNoOsProductPre; "No OS product present."
0x18003b52d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18003b531  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003b536  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003b53d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003b541  call    _CxxThrowException
0x18003b547  mov     r9d, eax; char *
0x18003b54a  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003b551  mov     edx, 54h ; 'T'; void *
0x18003b556  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

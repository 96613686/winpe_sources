# Windows::UsoProductEnumerator::TryGetPrimaryOsInfo(void)

- ea: `0x14036fb60`
- end: `0x140370060`
- name: `?TryGetPrimaryOsInfo@UsoProductEnumerator@Windows@@QEAA?AU?$pair@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V12@@std@@XZ`
- size: `1280`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14023e320`

## callees

- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x1400c695c`
- `0x1401156f8`
- `0x14030535c`
- `0x14036fb60`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fd18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fd79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fe50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fd18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fd79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14036fe50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140370019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036fd81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036fdff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036fd81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14036fdff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036fd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036fdec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036fd6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14036fdec`

## string_xrefs

- `0x14036fbbb`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int128 *__fastcall Windows::UsoProductEnumerator::TryGetPrimaryOsInfo(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  __int64 v4; // r14
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r8
  int v13; // ebx
  __int64 v14; // rdx
  __int64 *v15; // rbx
  __int64 (__fastcall *v16)(__int64 *, LPVOID *); // r15
  void *v17; // rsi
  DWORD LastError; // edi
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rbx
  __int64 (__fastcall *v25)(__int64, LPVOID *); // r15
  void *v26; // rsi
  DWORD v27; // edi
  __int64 v28; // r8
  _BYTE *v29; // rdi
  char v30; // bl
  wchar_t *v31; // rax
  char v32; // bl
  char v33; // bl
  int v35; // [rsp+28h] [rbp-E0h]
  wchar_t String_8[8]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v37; // [rsp+50h] [rbp-B8h]
  _BYTE v38[40]; // [rsp+60h] [rbp-A8h] BYREF
  char v39; // [rsp+88h] [rbp-80h]
  _BYTE v40[32]; // [rsp+90h] [rbp-78h] BYREF
  char v41; // [rsp+B0h] [rbp-58h]
  _BYTE v42[32]; // [rsp+B8h] [rbp-50h] BYREF
  char v43; // [rsp+D8h] [rbp-30h]
  __int64 *v44; // [rsp+E0h] [rbp-28h] BYREF
  __int64 *v45; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v46; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+108h] [rbp+0h] BYREF
  LPVOID v48; // [rsp+110h] [rbp+8h] BYREF
  LPVOID v49; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v49 = 0;
  v48 = 0;
  v3 = 0;
  v4 = -1;
  if ( !*(_DWORD *)a1 )
    goto LABEL_47;
  while ( 1 )
  {
    v44 = 0;
    v5 = *(__int64 **)(a1 + 24);
    v6 = *v5;
    v44 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v6 + 32))(v5, v3, &v44);
    if ( v7 >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v7,
      v35);
LABEL_21:
    if ( v44 )
      (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
    if ( ++v3 >= *(_DWORD *)a1 )
      goto LABEL_43;
  }
  v45 = 0;
  v8 = *v44;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v8 + 40))(v44, L"PrimaryOSProduct", &v45);
  if ( wil::details::in1diag3::Log_IfFailedWithExpected(
         retaddr,
         (void *)0x7C,
         (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
         (const char *)v9,
         1,
         0x80070002) < 0 )
  {
    if ( v45 )
      (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
    goto LABEL_21;
  }
  pv = 0;
  v10 = *v45;
  pv = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v10 + 32))(v45, &pv);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v11,
      v35);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v45 )
      (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
    goto LABEL_21;
  }
  *(_OWORD *)String_8 = 0;
  v37 = 0;
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)pv + v12) );
  std::wstring::_Construct<1,wchar_t const *>(String_8, pv, v12);
  v13 = std::stoi(String_8);
  std::wstring::~wstring(String_8, v14);
  if ( v13 != 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v45 )
      (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
    goto LABEL_21;
  }
  v15 = v44;
  v16 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v44 + 24);
  v17 = v49;
  if ( v49 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v17);
    SetLastError(LastError);
  }
  v49 = 0;
  v19 = v16(v15, &v49);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v19,
      v35);
  v46 = 0;
  v20 = *v44;
  v46 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v20 + 40))(v44, L"Version", &v46);
  v22 = retaddr;
  if ( v21 < 0 )
  {
    v23 = 140;
    goto LABEL_34;
  }
  v24 = v46;
  v25 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v46 + 32LL);
  v26 = v48;
  if ( v48 )
  {
    v27 = GetLastError();
    CoTaskMemFree(v26);
    SetLastError(v27);
  }
  v48 = 0;
  v21 = v25(v24, &v48);
  v22 = retaddr;
  if ( v21 < 0 )
  {
    v23 = 142;
LABEL_34:
    wil::details::in1diag3::_Log_Hr(
      v22,
      (void *)v23,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v21,
      v35);
  }
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v45 )
    (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
  if ( v44 )
    (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
LABEL_43:
  if ( v49 )
  {
    memset(&v38[8], 0, 32);
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v49 + v28) );
    std::wstring::_Construct<1,wchar_t const *>(&v38[8], v49, v28);
    v39 = 1;
    v29 = &v38[8];
    v30 = 65;
    goto LABEL_48;
  }
LABEL_47:
  v43 = 0;
  v29 = v42;
  v30 = 2;
LABEL_48:
  if ( v48 )
  {
    *(_OWORD *)String_8 = 0;
    v37 = 0;
    do
      ++v4;
    while ( *((_WORD *)v48 + v4) );
    std::wstring::_Construct<1,wchar_t const *>(String_8, v48, v4);
    v38[0] = 1;
    v31 = String_8;
    v32 = v30 | 0x24;
  }
  else
  {
    v41 = 0;
    v31 = (wchar_t *)v40;
    v32 = v30 | 8;
  }
  byte_14054AAE0 = 0;
  if ( v29[32] )
  {
    xmmword_14054AAC0 = *(_OWORD *)v29;
    xmmword_14054AAD0 = *((_OWORD *)v29 + 1);
    *(_WORD *)v29 = 0;
    *((_QWORD *)v29 + 2) = 0;
    *((_QWORD *)v29 + 3) = 7;
    byte_14054AAE0 = 1;
  }
  byte_14054AB08 = 0;
  if ( *((_BYTE *)v31 + 32) )
  {
    xmmword_14054AAE8 = *(_OWORD *)v31;
    xmmword_14054AAF8 = *((_OWORD *)v31 + 1);
    *v31 = 0;
    *((_QWORD *)v31 + 2) = 0;
    *((_QWORD *)v31 + 3) = 7;
    byte_14054AB08 = 1;
  }
  v33 = v32 | 0x10;
  if ( (v33 & 8) != 0 )
  {
    v33 &= ~8u;
    if ( v41 )
      std::wstring::~wstring(v40, a2);
  }
  if ( (v33 & 4) != 0 )
  {
    v33 &= ~4u;
    if ( v38[0] )
      std::wstring::~wstring(String_8, a2);
  }
  if ( (v33 & 2) != 0 )
  {
    v33 &= ~2u;
    if ( v43 )
      std::wstring::~wstring(v42, a2);
  }
  if ( (v33 & 1) != 0 && v39 )
    std::wstring::~wstring(&v38[8], a2);
  if ( v48 )
    CoTaskMemFree(v48);
  if ( v49 )
    CoTaskMemFree(v49);
  return &xmmword_14054AAC0;
}

```

## disassembly

```asm
0x14036fb60  mov     rax, rsp
0x14036fb63  mov     [rax+10h], rbx
0x14036fb67  mov     [rax+18h], rsi
0x14036fb6b  mov     [rax+20h], rdi
0x14036fb6f  push    rbp
0x14036fb70  push    r12
0x14036fb72  push    r13
0x14036fb74  push    r14
0x14036fb76  push    r15
0x14036fb78  lea     rbp, [rax-48h]
0x14036fb7c  sub     rsp, 120h
0x14036fb83  mov     rax, cs:__security_cookie
0x14036fb8a  xor     rax, rsp
0x14036fb8d  mov     [rbp+40h+var_28], rax
0x14036fb91  mov     rsi, rcx
0x14036fb94  xor     r12d, r12d
0x14036fb97  mov     dword ptr [rsp+140h+String], r12d
0x14036fb9c  lea     r15, xmmword_14054AAC0
0x14036fba3  mov     [rbp+40h+var_30], r12
0x14036fba7  mov     [rbp+40h+var_38], r12
0x14036fbab  mov     edi, r12d
0x14036fbae  or      r14, 0FFFFFFFFFFFFFFFFh
0x14036fbb2  cmp     [rcx], r12d
0x14036fbb5  jbe     loc_14036FECF
0x14036fbbb  lea     r13, aCW1SSrcOrchest_97; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14036fbc2  mov     [rbp+40h+var_68], r12
0x14036fbc6  mov     rcx, [rsi+18h]
0x14036fbca  mov     rax, [rcx]
0x14036fbcd  mov     [rbp+40h+var_68], r12
0x14036fbd1  lea     r8, [rbp+40h+var_68]
0x14036fbd5  mov     edx, edi
0x14036fbd7  mov     rax, [rax+20h]
0x14036fbdb  call    _guard_dispatch_icall
0x14036fbe0  mov     rcx, [rbp+48h]; this
0x14036fbe4  test    eax, eax
0x14036fbe6  jns     short loc_14036FBFE
0x14036fbe8  mov     r9d, eax; char *
0x14036fbeb  mov     r8, r13; unsigned int
0x14036fbee  mov     edx, 75h ; 'u'; void *
0x14036fbf3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036fbf8  nop
0x14036fbf9  jmp     loc_14036FD35
0x14036fbfe  mov     [rbp+40h+var_60], r12
0x14036fc02  mov     rcx, [rbp+40h+var_68]
0x14036fc06  mov     rax, [rcx]
0x14036fc09  mov     [rbp+40h+var_60], r12
0x14036fc0d  lea     r8, [rbp+40h+var_60]
0x14036fc11  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x14036fc18  mov     rax, [rax+28h]
0x14036fc1c  call    _guard_dispatch_icall
0x14036fc21  mov     rcx, [rbp+48h]; this
0x14036fc25  mov     [rsp+140h+var_118], 80070002h; unsigned int
0x14036fc2d  mov     [rsp+140h+var_120], 1; int
0x14036fc35  mov     r9d, eax; char *
0x14036fc38  mov     r8, r13; unsigned int
0x14036fc3b  mov     edx, 7Ch ; '|'; void *
0x14036fc40  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x14036fc45  test    eax, eax
0x14036fc47  jns     short loc_14036FC64
0x14036fc49  mov     rcx, [rbp+40h+var_60]
0x14036fc4d  test    rcx, rcx
0x14036fc50  jz      short loc_14036FC5F
0x14036fc52  mov     rax, [rcx]
0x14036fc55  mov     rax, [rax+10h]
0x14036fc59  call    _guard_dispatch_icall
0x14036fc5e  nop
0x14036fc5f  jmp     loc_14036FD35
0x14036fc64  mov     [rbp+40h+pv], r12
0x14036fc68  mov     rcx, [rbp+40h+var_60]
0x14036fc6c  mov     rax, [rcx]
0x14036fc6f  mov     [rbp+40h+pv], r12
0x14036fc73  lea     rdx, [rbp+40h+pv]
0x14036fc77  mov     rax, [rax+20h]
0x14036fc7b  call    _guard_dispatch_icall
0x14036fc80  mov     rcx, [rbp+48h]; this
0x14036fc84  test    eax, eax
0x14036fc86  jns     short loc_14036FCC1
0x14036fc88  mov     r9d, eax; char *
0x14036fc8b  mov     r8, r13; unsigned int
0x14036fc8e  mov     edx, 82h; void *
0x14036fc93  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036fc98  nop
0x14036fc99  mov     rcx, [rbp+40h+pv]; pv
0x14036fc9d  test    rcx, rcx
0x14036fca0  jz      short loc_14036FCA9
0x14036fca2  call    cs:__imp_CoTaskMemFree
0x14036fca8  nop
0x14036fca9  mov     rcx, [rbp+40h+var_60]
0x14036fcad  test    rcx, rcx
0x14036fcb0  jz      short loc_14036FCBF
0x14036fcb2  mov     rax, [rcx]
0x14036fcb5  mov     rax, [rax+10h]
0x14036fcb9  call    _guard_dispatch_icall
0x14036fcbe  nop
0x14036fcbf  jmp     short loc_14036FD35
0x14036fcc1  xorps   xmm0, xmm0
0x14036fcc4  movups  xmmword ptr [rsp+140h+String+8], xmm0
0x14036fcc9  xorps   xmm1, xmm1
0x14036fccc  movdqu  xmmword ptr [rsp+140h+var_100+8], xmm1
0x14036fcd2  mov     rdx, [rbp+40h+pv]
0x14036fcd6  mov     r8, r14
0x14036fcd9  inc     r8
0x14036fcdc  cmp     [rdx+r8*2], r12w
0x14036fce1  jnz     short loc_14036FCD9
0x14036fce3  lea     rcx, [rsp+140h+String+8]
0x14036fce8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036fced  nop
0x14036fcee  mov     r8d, 0Ah
0x14036fcf4  lea     rcx, [rsp+140h+String+8]; String
0x14036fcf9  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x14036fcfe  mov     ebx, eax
0x14036fd00  lea     rcx, [rsp+140h+String+8]
0x14036fd05  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14036fd0a  cmp     ebx, 1
0x14036fd0d  jz      short loc_14036FD5A
0x14036fd0f  mov     rcx, [rbp+40h+pv]; pv
0x14036fd13  test    rcx, rcx
0x14036fd16  jz      short loc_14036FD1F
0x14036fd18  call    cs:__imp_CoTaskMemFree
0x14036fd1e  nop
0x14036fd1f  mov     rcx, [rbp+40h+var_60]
0x14036fd23  test    rcx, rcx
0x14036fd26  jz      short loc_14036FD35
0x14036fd28  mov     rax, [rcx]
0x14036fd2b  mov     rax, [rax+10h]
0x14036fd2f  call    _guard_dispatch_icall
0x14036fd34  nop
0x14036fd35  mov     rcx, [rbp+40h+var_68]
0x14036fd39  test    rcx, rcx
0x14036fd3c  jz      short loc_14036FD4B
0x14036fd3e  mov     rax, [rcx]
0x14036fd41  mov     rax, [rax+10h]
0x14036fd45  call    _guard_dispatch_icall
0x14036fd4a  nop
0x14036fd4b  inc     edi
0x14036fd4d  cmp     edi, [rsi]
0x14036fd4f  jb      loc_14036FBC2
0x14036fd55  jmp     loc_14036FE8A
0x14036fd5a  mov     rbx, [rbp+40h+var_68]
0x14036fd5e  mov     rax, [rbx]
0x14036fd61  mov     r15, [rax+18h]
0x14036fd65  mov     rsi, [rbp+40h+var_30]
0x14036fd69  test    rsi, rsi
0x14036fd6c  jz      short loc_14036FD87
0x14036fd6e  call    cs:__imp_GetLastError
0x14036fd74  mov     edi, eax
0x14036fd76  mov     rcx, rsi; pv
0x14036fd79  call    cs:__imp_CoTaskMemFree
0x14036fd7f  mov     ecx, edi; dwErrCode
0x14036fd81  call    cs:__imp_SetLastError
0x14036fd87  mov     [rbp+40h+var_30], r12
0x14036fd8b  lea     rdx, [rbp+40h+var_30]
0x14036fd8f  mov     rcx, rbx
0x14036fd92  mov     rax, r15
0x14036fd95  call    _guard_dispatch_icall
0x14036fd9a  mov     rcx, [rbp+48h]; this
0x14036fd9e  test    eax, eax
0x14036fda0  js      loc_14037004F
0x14036fda6  mov     [rbp+40h+var_50], r12
0x14036fdaa  mov     rcx, [rbp+40h+var_68]
0x14036fdae  mov     rax, [rcx]
0x14036fdb1  mov     [rbp+40h+var_50], r12
0x14036fdb5  lea     r8, [rbp+40h+var_50]
0x14036fdb9  lea     rdx, aVersion_0; "Version"
0x14036fdc0  mov     rax, [rax+28h]
0x14036fdc4  call    _guard_dispatch_icall
0x14036fdc9  mov     rcx, [rbp+48h]
0x14036fdcd  test    eax, eax
0x14036fdcf  jns     short loc_14036FDD8
0x14036fdd1  mov     edx, 8Ch
0x14036fdd6  jmp     short loc_14036FE25
0x14036fdd8  mov     rbx, [rbp+40h+var_50]
0x14036fddc  mov     rax, [rbx]
0x14036fddf  mov     r15, [rax+20h]
0x14036fde3  mov     rsi, [rbp+40h+var_38]
0x14036fde7  test    rsi, rsi
0x14036fdea  jz      short loc_14036FE05
0x14036fdec  call    cs:__imp_GetLastError
0x14036fdf2  mov     edi, eax
0x14036fdf4  mov     rcx, rsi; pv
0x14036fdf7  call    cs:__imp_CoTaskMemFree
0x14036fdfd  mov     ecx, edi; dwErrCode
0x14036fdff  call    cs:__imp_SetLastError
0x14036fe05  mov     [rbp+40h+var_38], r12
0x14036fe09  lea     rdx, [rbp+40h+var_38]
0x14036fe0d  mov     rcx, rbx
0x14036fe10  mov     rax, r15
0x14036fe13  call    _guard_dispatch_icall
0x14036fe18  mov     rcx, [rbp+48h]; this
0x14036fe1c  test    eax, eax
0x14036fe1e  jns     short loc_14036FE31
0x14036fe20  mov     edx, 8Eh; void *
0x14036fe25  mov     r9d, eax; char *
0x14036fe28  mov     r8, r13; unsigned int
0x14036fe2b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14036fe30  nop
0x14036fe31  mov     rcx, [rbp+40h+var_50]
0x14036fe35  test    rcx, rcx
0x14036fe38  jz      short loc_14036FE47
0x14036fe3a  mov     rax, [rcx]
0x14036fe3d  mov     rax, [rax+10h]
0x14036fe41  call    _guard_dispatch_icall
0x14036fe46  nop
0x14036fe47  mov     rcx, [rbp+40h+pv]; pv
0x14036fe4b  test    rcx, rcx
0x14036fe4e  jz      short loc_14036FE57
0x14036fe50  call    cs:__imp_CoTaskMemFree
0x14036fe56  nop
0x14036fe57  mov     rcx, [rbp+40h+var_60]
0x14036fe5b  test    rcx, rcx
0x14036fe5e  jz      short loc_14036FE6D
0x14036fe60  mov     rax, [rcx]
0x14036fe63  mov     rax, [rax+10h]
0x14036fe67  call    _guard_dispatch_icall
0x14036fe6c  nop
0x14036fe6d  mov     rcx, [rbp+40h+var_68]
0x14036fe71  test    rcx, rcx
0x14036fe74  jz      short loc_14036FE83
0x14036fe76  mov     rax, [rcx]
0x14036fe79  mov     rax, [rax+10h]
0x14036fe7d  call    _guard_dispatch_icall
0x14036fe82  nop
0x14036fe83  lea     r15, xmmword_14054AAC0
0x14036fe8a  mov     rcx, [rbp+40h+var_30]
0x14036fe8e  test    rcx, rcx
0x14036fe91  jz      short loc_14036FECF
0x14036fe93  xorps   xmm0, xmm0
0x14036fe96  movups  [rsp+140h+var_E8+8], xmm0
0x14036fe9b  xorps   xmm1, xmm1
0x14036fe9e  movdqu  [rsp+140h+var_D8+8], xmm1
0x14036fea4  mov     r8, r14
0x14036fea7  inc     r8
0x14036feaa  cmp     [rcx+r8*2], r12w
0x14036feaf  jnz     short loc_14036FEA7
0x14036feb1  mov     rdx, [rbp+40h+var_30]
0x14036feb5  lea     rcx, [rsp+140h+var_E8+8]
0x14036feba  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036febf  mov     [rbp+40h+var_C0], 1
0x14036fec3  lea     rdi, [rsp+140h+var_E8+8]
0x14036fec8  mov     ebx, 41h ; 'A'
0x14036fecd  jmp     short loc_14036FEDC
0x14036fecf  mov     [rbp+40h+var_70], r12b
0x14036fed3  lea     rdi, [rbp+40h+var_90]
0x14036fed7  mov     ebx, 2
0x14036fedc  mov     dword ptr [rsp+140h+String], ebx
0x14036fee0  mov     rcx, [rbp+40h+var_38]
0x14036fee4  test    rcx, rcx
0x14036fee7  jz      short loc_14036FF24
0x14036fee9  xorps   xmm0, xmm0
0x14036feec  movups  xmmword ptr [rsp+140h+String+8], xmm0
0x14036fef1  xorps   xmm1, xmm1
0x14036fef4  movdqu  xmmword ptr [rsp+140h+var_100+8], xmm1
0x14036fefa  inc     r14
0x14036fefd  cmp     [rcx+r14*2], r12w
0x14036ff02  jnz     short loc_14036FEFA
0x14036ff04  mov     r8, r14
0x14036ff07  mov     rdx, [rbp+40h+var_38]
0x14036ff0b  lea     rcx, [rsp+140h+String+8]
0x14036ff10  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14036ff15  mov     byte ptr [rsp+140h+var_E8], 1
0x14036ff1a  lea     rax, [rsp+140h+String+8]
0x14036ff1f  or      ebx, 24h
0x14036ff22  jmp     short loc_14036FF2F
0x14036ff24  mov     [rbp+40h+var_98], r12b
0x14036ff28  lea     rax, [rbp+40h+var_B8]
0x14036ff2c  or      ebx, 8
0x14036ff2f  mov     cs:byte_14054AAE0, r12b
0x14036ff36  mov     ecx, 7
0x14036ff3b  cmp     [rdi+20h], r12b
0x14036ff3f  jz      short loc_14036FF69
0x14036ff41  movups  xmm1, xmmword ptr [rdi]
0x14036ff44  movaps  cs:xmmword_14054AAC0, xmm1
0x14036ff4b  movups  xmm0, xmmword ptr [rdi+10h]
0x14036ff4f  movaps  cs:xmmword_14054AAD0, xmm0
0x14036ff56  mov     [rdi], r12w
0x14036ff5a  mov     [rdi+10h], r12
0x14036ff5e  mov     [rdi+18h], rcx
0x14036ff62  mov     cs:byte_14054AAE0, 1
0x14036ff69  mov     cs:byte_14054AB08, r12b
0x14036ff70  cmp     [rax+20h], r12b
0x14036ff74  jz      short loc_14036FF9E
0x14036ff76  movups  xmm1, xmmword ptr [rax]
0x14036ff79  movups  cs:xmmword_14054AAE8, xmm1
0x14036ff80  movups  xmm0, xmmword ptr [rax+10h]
0x14036ff84  movups  cs:xmmword_14054AAF8, xmm0
0x14036ff8b  mov     [rax], r12w
0x14036ff8f  mov     [rax+10h], r12
0x14036ff93  mov     [rax+18h], rcx
0x14036ff97  mov     cs:byte_14054AB08, 1
0x14036ff9e  or      ebx, 10h
0x14036ffa1  test    bl, 8
0x14036ffa4  jz      short loc_14036FFB8
0x14036ffa6  and     ebx, 0FFFFFFF7h
0x14036ffa9  cmp     [rbp+40h+var_98], r12b
0x14036ffad  jz      short loc_14036FFB8
0x14036ffaf  lea     rcx, [rbp+40h+var_B8]
0x14036ffb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14036ffb8  test    bl, 4
0x14036ffbb  jz      short loc_14036FFD2
0x14036ffbd  and     ebx, 0FFFFFFFBh
  ... truncated ...
```

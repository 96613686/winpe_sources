# JobHelper::GetJobs(std::list<_Job,std::allocator<_Job>> &)

- ea: `0x1400501a4`
- end: `0x1400505ce`
- name: `?GetJobs@JobHelper@@SAJAEAV?$list@U_Job@@V?$allocator@U_Job@@@std@@@std@@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x14004a9a4`

## callees

- `0x1400042f0`
- `0x1400045a8`
- `0x140004610`
- `0x1400095b4`
- `0x14001e784`
- `0x14001ed14`
- `0x140049f88`
- `0x14004f4d0`
- `0x14004f71c`
- `0x14004f798`
- `0x1400501a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140050289`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140050289`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400502fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005039c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400502fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005039c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050401`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400502c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400502c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050323`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140050323`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140050390`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140050390`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400503f5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400503f5`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400505c7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400505c7`

## string_xrefs

- `0x140050295`: `JobHelper::GetJobs: Failed to get CDNDownload Root Store path`
- `0x140050303`: `JobHelper::GetJobs: Failed to open regPath %1 with Status = %2!d!. GetLastError is %!winerr!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobHelper::GetJobs(void ***a1)
{
  void **v2; // rdx
  char **v3; // r14
  char *v4; // rdi
  __int64 v5; // r9
  int v6; // ebx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  DWORD LastError; // eax
  unsigned int v11; // ebx
  DWORD v12; // eax
  DWORD i; // r14d
  unsigned int v14; // ebx
  unsigned __int64 v15; // r8
  int Job; // ebx
  void **v17; // rdi
  void ***v18; // rbx
  void **v19; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  void ***v25; // [rsp+70h] [rbp-90h] BYREF
  void ***v26; // [rsp+78h] [rbp-88h]
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  __int128 v33; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  __int64 v39; // [rsp+110h] [rbp+10h]
  int v40; // [rsp+118h] [rbp+18h]
  __int64 v41; // [rsp+11Ch] [rbp+1Ch]
  __int128 v42; // [rsp+128h] [rbp+28h] BYREF
  __int64 v43; // [rsp+138h] [rbp+38h]
  __int64 v44; // [rsp+140h] [rbp+40h]
  __int128 v45; // [rsp+148h] [rbp+48h] BYREF
  __int64 v46; // [rsp+158h] [rbp+58h]
  __int64 v47; // [rsp+160h] [rbp+60h]
  __int128 v48; // [rsp+168h] [rbp+68h] BYREF
  __int64 v49; // [rsp+178h] [rbp+78h]
  __int64 v50; // [rsp+180h] [rbp+80h]
  WCHAR SubKey[256]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR Name[256]; // [rsp+390h] [rbp+290h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5C8h] [rbp+4C8h]

  hKey = 0;
  cSubKeys = 0;
  cchName = 255;
  v2 = *a1;
  *(_QWORD *)(*a1)[1] = 0;
  v3 = (char **)*v2;
  if ( *v2 )
  {
    do
    {
      v4 = *v3;
      std::wstring::~wstring(v3 + 27);
      std::wstring::~wstring(v3 + 23);
      std::wstring::~wstring(v3 + 19);
      std::wstring::~wstring(v3 + 10);
      std::wstring::~wstring(v3 + 6);
      std::wstring::~wstring(v3 + 2);
      operator delete(v3);
      v3 = (char **)v4;
    }
    while ( v4 );
  }
  **a1 = *a1;
  (*a1)[1] = *a1;
  a1[1] = 0;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(qword_14007E6C8 + 2 * v5) );
  v6 = _o_wcsncpy_s(SubKey, 255, qword_14007E6C8, v5);
  if ( v6 < 0 )
    LogTelemetryError(L"JobHelper::GetJobs: Failed to get CDNDownload Root Store path");
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      if ( v6 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\jobhelper.cpp",
          (const char *)(unsigned int)v6,
          phkResult);
      return (unsigned int)v6;
    }
    LastError = GetLastError();
    LogTelemetryError(
      L"JobHelper::GetJobs: Failed to open regPath %1 with Status = %2!d!. GetLastError is %!winerr!",
      SubKey,
      v8,
      LastError);
  }
  else
  {
    v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v11 )
    {
      v12 = GetLastError();
      LogTelemetryError(
        L"JobHelper::GetJobs: Failed to query subkeys under %1, failed with Status = %2!d!. GetLastError is %!winerr!",
        SubKey,
        v11,
        v12);
    }
    else
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 255;
        v14 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v14 )
        {
          LODWORD(phkResulta) = GetLastError();
          LogTelemetryError(
            L"JobHelper::GetJobs:Failed to enumerate subkey %1 under %2 failed with Status = %3!d!. GetLastError is %!winerr!",
            Name,
            SubKey,
            v14,
            phkResulta);
        }
        else
        {
          v30 = 0;
          v31 = 0;
          v32 = 7;
          LOWORD(v30) = 0;
          v33 = 0;
          v34 = 0;
          v35 = 7;
          LOWORD(v33) = 0;
          v36 = 0;
          v37 = 0;
          v38 = 7;
          LOWORD(v36) = 0;
          v42 = 0;
          v43 = 0;
          v44 = 7;
          LOWORD(v42) = 0;
          v45 = 0;
          v46 = 0;
          v47 = 7;
          LOWORD(v45) = 0;
          v48 = 0;
          v49 = 0;
          v50 = 7;
          LOWORD(v48) = 0;
          v39 = 0;
          v41 = 0;
          v40 = 0;
          v27 = 0;
          v28 = 0;
          v29 = 0;
          v15 = -1;
          do
            ++v15;
          while ( Name[v15] );
          std::wstring::_Construct<1,unsigned short const *>((char **)&v27, Name, v15);
          Job = JobHelper::GetJob(&v27, &v30);
          std::wstring::~wstring((char **)&v27);
          if ( Job >= 0 )
          {
            if ( a1[1] == (void **)0x108421084210842LL )
              std::_Xlength_error("list too long");
            v17 = *a1;
            v25 = a1;
            v26 = 0;
            v18 = (void ***)operator new(0xF8u);
            v26 = v18;
            _Job::_Job((_Job *)(v18 + 2), (const struct _Job *)&v30);
            a1[1] = (void **)((char *)a1[1] + 1);
            v19 = (void **)v17[1];
            *v18 = v17;
            v18[1] = v19;
            v26 = 0;
            v17[1] = v18;
            *v19 = v18;
            std::_List_node_emplace_op2<std::allocator<std::_List_node<_Job,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<_Job,void *>>>(&v25);
          }
          else
          {
            LogTelemetryError(
              L"JobHelper::GetJobs: Failed to get job for %1 with error 0x%2!x!",
              Name,
              (unsigned int)Job);
          }
          std::wstring::~wstring((char **)&v48);
          std::wstring::~wstring((char **)&v45);
          std::wstring::~wstring((char **)&v42);
          std::wstring::~wstring((char **)&v36);
          std::wstring::~wstring((char **)&v33);
          std::wstring::~wstring((char **)&v30);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1400501a4  mov     [rsp-8+arg_8], rbx
0x1400501a9  mov     [rsp-8+arg_10], rsi
0x1400501ae  push    rbp
0x1400501af  push    rdi
0x1400501b0  push    r13
0x1400501b2  push    r14
0x1400501b4  push    r15
0x1400501b6  lea     rbp, [rsp-4A0h]
0x1400501be  sub     rsp, 5A0h
0x1400501c5  mov     rax, cs:__security_cookie
0x1400501cc  xor     rax, rsp
0x1400501cf  mov     [rbp+4C0h+var_30], rax
0x1400501d6  mov     rsi, rcx
0x1400501d9  xor     r15d, r15d
0x1400501dc  mov     [rsp+5C0h+hKey], r15
0x1400501e1  mov     [rsp+5C0h+cSubKeys], r15d
0x1400501e6  mov     [rsp+5C0h+cchName], 0FFh
0x1400501ee  mov     rdx, [rcx]
0x1400501f1  mov     rax, [rdx+8]
0x1400501f5  mov     [rax], r15
0x1400501f8  mov     r14, [rdx]
0x1400501fb  test    r14, r14
0x1400501fe  jz      short loc_140050257
0x140050200  mov     rdi, [r14]
0x140050203  lea     rcx, [r14+0D8h]
0x14005020a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005020f  lea     rcx, [r14+0B8h]
0x140050216  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005021b  lea     rcx, [r14+98h]
0x140050222  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050227  lea     rcx, [r14+50h]
0x14005022b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050230  lea     rcx, [r14+30h]
0x140050234  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050239  lea     rcx, [r14+10h]
0x14005023d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050242  mov     edx, 0F8h
0x140050247  mov     rcx, r14; Block
0x14005024a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005024f  mov     r14, rdi
0x140050252  test    rdi, rdi
0x140050255  jnz     short loc_140050200
0x140050257  mov     rax, [rsi]
0x14005025a  mov     [rax], rax
0x14005025d  mov     rax, [rsi]
0x140050260  mov     [rax+8], rax
0x140050264  mov     [rsi+8], r15
0x140050268  mov     r8, cs:qword_14007E6C8
0x14005026f  or      r9, 0FFFFFFFFFFFFFFFFh
0x140050273  inc     r9
0x140050276  cmp     [r8+r9*2], r15w
0x14005027b  jnz     short loc_140050273
0x14005027d  mov     edx, 0FFh
0x140050282  lea     rcx, [rbp+4C0h+SubKey]
0x140050289  call    cs:__imp__o_wcsncpy_s
0x14005028f  mov     ebx, eax
0x140050291  test    eax, eax
0x140050293  jns     short loc_1400502A1
0x140050295  lea     rcx, aJobhelperGetjo_7; "JobHelper::GetJobs: Failed to get CDNDo"...
0x14005029c  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x1400502a1  lea     rax, [rsp+5C0h+hKey]
0x1400502a6  mov     [rsp+5C0h+phkResult], rax; int
0x1400502ab  mov     r9d, 20019h; samDesired
0x1400502b1  xor     r8d, r8d; ulOptions
0x1400502b4  lea     rdx, [rbp+4C0h+SubKey]; lpSubKey
0x1400502bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400502c2  call    cs:__imp_RegOpenKeyExW
0x1400502c8  mov     edi, eax
0x1400502ca  test    eax, eax
0x1400502cc  jz      loc_140050356
0x1400502d2  cmp     eax, 2
0x1400502d5  jnz     short loc_1400502FA
0x1400502d7  test    ebx, ebx
0x1400502d9  jns     short loc_1400502F6
0x1400502db  mov     rcx, [rbp+4C8h]; this
0x1400502e2  mov     r9d, ebx; char *
0x1400502e5  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x1400502ec  mov     edx, 146h; void *
0x1400502f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400502f6  mov     eax, ebx
0x1400502f8  jmp     short loc_14005032B
0x1400502fa  call    cs:__imp_GetLastError
0x140050300  mov     r8d, edi
0x140050303  lea     rcx, aJobhelperGetjo_3; "JobHelper::GetJobs: Failed to open regP"...
0x14005030a  lea     rdx, [rbp+4C0h+SubKey]
0x140050311  mov     r9d, eax
0x140050314  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x140050319  mov     rcx, [rsp+5C0h+hKey]; hKey
0x14005031e  test    rcx, rcx
0x140050321  jz      short loc_140050329
0x140050323  call    cs:__imp_RegCloseKey
0x140050329  xor     eax, eax
0x14005032b  mov     rcx, [rbp+4C0h+var_30]
0x140050332  xor     rcx, rsp; StackCookie
0x140050335  call    __security_check_cookie
0x14005033a  lea     r11, [rsp+5C0h+var_20]
0x140050342  mov     rbx, [r11+38h]
0x140050346  mov     rsi, [r11+40h]
0x14005034a  mov     rsp, r11
0x14005034d  pop     r15
0x14005034f  pop     r14
0x140050351  pop     r13
0x140050353  pop     rdi
0x140050354  pop     rbp
0x140050355  retn
0x140050356  mov     [rsp+5C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14005035b  mov     [rsp+5C0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140050360  mov     [rsp+5C0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140050365  mov     [rsp+5C0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14005036a  mov     [rsp+5C0h+lpcValues], r15; lpcValues
0x14005036f  mov     [rsp+5C0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140050374  mov     [rsp+5C0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140050379  lea     rax, [rsp+5C0h+cSubKeys]
0x14005037e  mov     [rsp+5C0h+phkResult], rax; lpcSubKeys
0x140050383  xor     r9d, r9d; lpReserved
0x140050386  xor     r8d, r8d; lpcchClass
0x140050389  xor     edx, edx; lpClass
0x14005038b  mov     rcx, [rsp+5C0h+hKey]; hKey
0x140050390  call    cs:__imp_RegQueryInfoKeyW
0x140050396  mov     ebx, eax
0x140050398  test    eax, eax
0x14005039a  jz      short loc_1400503B1
0x14005039c  call    cs:__imp_GetLastError
0x1400503a2  mov     r8d, ebx
0x1400503a5  lea     rcx, aJobhelperGetjo_1; "JobHelper::GetJobs: Failed to query sub"...
0x1400503ac  jmp     loc_14005030A
0x1400503b1  mov     r14d, r15d
0x1400503b4  cmp     [rsp+5C0h+cSubKeys], r15d
0x1400503b9  jbe     loc_140050319
0x1400503bf  mov     r13d, 7
0x1400503c5  mov     [rsp+5C0h+cchName], 0FFh
0x1400503cd  mov     [rsp+5C0h+lpcValues], r15; lpftLastWriteTime
0x1400503d2  mov     [rsp+5C0h+lpcbMaxClassLen], r15; lpcchClass
0x1400503d7  mov     [rsp+5C0h+lpcbMaxSubKeyLen], r15; lpClass
0x1400503dc  mov     [rsp+5C0h+phkResult], r15; lpReserved
0x1400503e1  lea     r9, [rsp+5C0h+cchName]; lpcchName
0x1400503e6  lea     r8, [rbp+4C0h+Name]; lpName
0x1400503ed  mov     edx, r14d; dwIndex
0x1400503f0  mov     rcx, [rsp+5C0h+hKey]; hKey
0x1400503f5  call    cs:__imp_RegEnumKeyExW
0x1400503fb  mov     ebx, eax
0x1400503fd  test    eax, eax
0x1400503ff  jz      short loc_14005042D
0x140050401  call    cs:__imp_GetLastError
0x140050407  mov     dword ptr [rsp+5C0h+phkResult], eax
0x14005040b  mov     r9d, ebx
0x14005040e  lea     r8, [rbp+4C0h+SubKey]
0x140050415  lea     rdx, [rbp+4C0h+Name]
0x14005041c  lea     rcx, aJobhelperGetjo_2; "JobHelper::GetJobs:Failed to enumerate "...
0x140050423  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x140050428  jmp     loc_1400505AD
0x14005042d  xorps   xmm0, xmm0
0x140050430  movups  [rbp+4C0h+var_520], xmm0
0x140050434  mov     [rbp+4C0h+var_510], r15
0x140050438  mov     [rbp+4C0h+var_508], r13
0x14005043c  mov     word ptr [rbp+4C0h+var_520], r15w
0x140050441  movups  [rbp+4C0h+var_500], xmm0
0x140050445  mov     [rbp+4C0h+var_4F0], r15
0x140050449  mov     [rbp+4C0h+var_4E8], r13
0x14005044d  mov     word ptr [rbp+4C0h+var_500], r15w
0x140050452  movups  [rbp+4C0h+var_4E0], xmm0
0x140050456  mov     [rbp+4C0h+var_4D0], r15
0x14005045a  mov     [rbp+4C0h+var_4C8], r13
0x14005045e  mov     word ptr [rbp+4C0h+var_4E0], r15w
0x140050463  movups  [rbp+4C0h+var_498], xmm0
0x140050467  mov     [rbp+4C0h+var_488], r15
0x14005046b  mov     [rbp+4C0h+var_480], r13
0x14005046f  mov     word ptr [rbp+4C0h+var_498], r15w
0x140050474  movups  [rbp+4C0h+var_478], xmm0
0x140050478  mov     [rbp+4C0h+var_468], r15
0x14005047c  mov     [rbp+4C0h+var_460], r13
0x140050480  mov     word ptr [rbp+4C0h+var_478], r15w
0x140050485  movups  [rbp+4C0h+var_458], xmm0
0x140050489  mov     [rbp+4C0h+var_448], r15
0x14005048d  mov     [rbp+4C0h+var_440], r13
0x140050494  mov     word ptr [rbp+4C0h+var_458], r15w
0x140050499  mov     [rbp+4C0h+var_4B0], r15
0x14005049d  mov     [rbp+4C0h+var_4A4], r15
0x1400504a1  mov     [rbp+4C0h+var_4A8], r15d
0x1400504a5  movups  [rbp+4C0h+var_540], xmm0
0x1400504a9  mov     [rbp+4C0h+var_530], r15
0x1400504ad  mov     [rbp+4C0h+var_528], r15
0x1400504b1  lea     rax, [rbp+4C0h+Name]
0x1400504b8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400504bc  inc     r8
0x1400504bf  cmp     [rax+r8*2], r15w
0x1400504c4  jnz     short loc_1400504BC
0x1400504c6  lea     rdx, [rbp+4C0h+Name]
0x1400504cd  lea     rcx, [rbp+4C0h+var_540]
0x1400504d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400504d6  nop
0x1400504d7  lea     rdx, [rbp+4C0h+var_520]
0x1400504db  lea     rcx, [rbp+4C0h+var_540]
0x1400504df  call    ?GetJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_Job@@@Z; JobHelper::GetJob(std::wstring const &,_Job &)
0x1400504e4  mov     ebx, eax
0x1400504e6  lea     rcx, [rbp+4C0h+var_540]
0x1400504ea  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400504ef  mov     ecx, ebx
0x1400504f1  shr     ecx, 1Fh
0x1400504f4  test    cl, cl
0x1400504f6  jz      short loc_140050510
0x1400504f8  mov     r8d, ebx
0x1400504fb  lea     rdx, [rbp+4C0h+Name]
0x140050502  lea     rcx, aJobhelperGetjo_4; "JobHelper::GetJobs: Failed to get job f"...
0x140050509  call    ?LogTelemetryError@@YAXPEBGZZ; LogTelemetryError(ushort const *,...)
0x14005050e  jmp     short loc_140050577
0x140050510  mov     rax, 108421084210842h
0x14005051a  cmp     [rsi+8], rax
0x14005051e  jz      loc_1400505C0
0x140050524  mov     rdi, [rsi]
0x140050527  mov     [rsp+5C0h+var_550], rsi
0x14005052c  mov     [rsp+5C0h+var_548], r15
0x140050531  mov     ecx, 0F8h; Size
0x140050536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005053b  mov     rbx, rax
0x14005053e  mov     [rsp+5C0h+var_548], rax
0x140050543  lea     rcx, [rax+10h]; this
0x140050547  lea     rdx, [rbp+4C0h+var_520]; struct _Job *
0x14005054b  call    ??0_Job@@QEAA@AEBU0@@Z; _Job::_Job(_Job const &)
0x140050550  nop
0x140050551  inc     qword ptr [rsi+8]
0x140050555  mov     rcx, [rdi+8]
0x140050559  mov     [rbx], rdi
0x14005055c  mov     [rbx+8], rcx
0x140050560  mov     [rsp+5C0h+var_548], r15
0x140050565  mov     [rdi+8], rbx
0x140050569  mov     [rcx], rbx
0x14005056c  lea     rcx, [rsp+5C0h+var_550]
0x140050571  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U_Job@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<_Job,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<_Job,void *>>>(void)
0x140050576  nop
0x140050577  lea     rcx, [rbp+4C0h+var_458]
0x14005057b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050580  lea     rcx, [rbp+4C0h+var_478]
0x140050584  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050589  lea     rcx, [rbp+4C0h+var_498]
0x14005058d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140050592  lea     rcx, [rbp+4C0h+var_4E0]
0x140050596  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005059b  lea     rcx, [rbp+4C0h+var_500]
0x14005059f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400505a4  lea     rcx, [rbp+4C0h+var_520]
0x1400505a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400505ad  inc     r14d
0x1400505b0  cmp     r14d, [rsp+5C0h+cSubKeys]
0x1400505b5  jb      loc_1400503C5
0x1400505bb  jmp     loc_140050319
0x1400505c0  lea     rcx, aListTooLong; "list too long"
0x1400505c7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```

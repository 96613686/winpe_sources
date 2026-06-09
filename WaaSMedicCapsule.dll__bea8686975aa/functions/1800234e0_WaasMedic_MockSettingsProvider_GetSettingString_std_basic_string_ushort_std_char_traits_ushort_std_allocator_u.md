# WaasMedic::MockSettingsProvider::GetSettingString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,WaasMedic::Setting<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> &)

- ea: `0x1800234e0`
- end: `0x180023790`
- name: `?GetSettingString@MockSettingsProvider@WaasMedic@@UEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAU?$Setting@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x180021c20`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x18000ab8c`
- `0x180022310`
- `0x180023114`
- `0x1800231d0`
- `0x1800234e0`
- `0x180024fc4`
- `0x1800251a8`
- `0x180031df4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800235c3`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800235c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002364b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800236a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002364b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800236a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002361f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002361f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800236fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800236fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::MockSettingsProvider::GetSettingString(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  const WCHAR *v8; // rsi
  const WCHAR *v9; // rbx
  BYTE *v10; // rdi
  REGSAM v11; // r9d
  LSTATUS v12; // eax
  void *v13; // rdx
  signed int v14; // ebx
  bool v15; // cc
  bool v16; // r8
  DWORD v17; // eax
  __int64 v19; // r8
  DWORD cbData; // [rsp+40h] [rbp-69h] BYREF
  DWORD Type; // [rsp+44h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-59h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-9h] BYREF

  v7 = a2[2];
  if ( v7 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(v25, a2, v7, a2, v7, L"_", 1);
  std::operator+<unsigned short>(lpValueName, v25, a3);
  std::wstring::~wstring(v25);
  v8 = (const WCHAR *)lpValueName;
  if ( lpValueName[3] > (LPCWSTR)7 )
    v8 = lpValueName[0];
  v9 = (const WCHAR *)(a1 + 8);
  if ( *((_QWORD *)v9 + 3) > 7u )
    v9 = *(const WCHAR **)v9;
  Type = 0;
  hKey = 0;
  cbData = 0;
  v10 = 0;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  v11 = 1;
  if ( dword_180098D54 )
    v11 = 257;
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, v11, &hKey);
  v14 = v12;
  v15 = v12 <= 0;
  if ( v12 || (v12 = RegQueryValueExW(hKey, v8, 0, &Type, 0, &cbData), v14 = v12, v15 = v12 <= 0, v12) )
  {
LABEL_24:
    if ( !v15 )
      v14 = (unsigned __int16)v12 | 0x80070000;
LABEL_26:
    if ( v14 >= 0 )
      goto LABEL_29;
    goto LABEL_27;
  }
  v17 = cbData;
  if ( !cbData )
    goto LABEL_26;
  if ( Type != 1 )
  {
    v14 = -2147024883;
    goto LABEL_27;
  }
  cbData += 2;
  v10 = (BYTE *)WaasMedic::SafeAlloc((WaasMedic *)(v17 + 2), (unsigned __int64)v13, v16);
  if ( v10 )
  {
    v12 = RegQueryValueExW(hKey, v8, 0, &Type, v10, &cbData);
    v14 = v12;
    v15 = v12 <= 0;
    if ( !v12 )
    {
      v14 = 0;
      *(_WORD *)&v10[cbData & 0xFFFFFFFE] = 0;
      goto LABEL_29;
    }
    goto LABEL_24;
  }
  v14 = -2147024882;
LABEL_27:
  WaasMedic::SafeFree((WaasMedic *)v10, v13);
  v10 = 0;
  if ( v14 != -2147024894 )
    WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(L"string", v8, v14);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 != -2147024894 )
  {
    if ( v14 < 0 )
    {
      std::wstring::~wstring(lpValueName);
      return (unsigned int)v14;
    }
    *(_DWORD *)(a4 + 32) = 5;
    memset(&SystemInfo, 0, 32);
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)&v10[2 * v19] );
    std::wstring::_Construct<1,unsigned short const *>(&SystemInfo, v10, v19);
    std::wstring::operator=(a4, &SystemInfo);
    std::wstring::~wstring(&SystemInfo);
  }
  std::wstring::~wstring(lpValueName);
  return 0;
}

```

## disassembly

```asm
0x1800234e0  push    rbp
0x1800234e2  push    rbx
0x1800234e3  push    rsi
0x1800234e4  push    rdi
0x1800234e5  push    r14
0x1800234e7  push    r15
0x1800234e9  lea     rbp, [rsp-2Fh]
0x1800234ee  sub     rsp, 0D8h
0x1800234f5  mov     rax, cs:__security_cookie
0x1800234fc  xor     rax, rsp
0x1800234ff  mov     [rbp+57h+var_40], rax
0x180023503  mov     r14, r9
0x180023506  mov     rdi, r8
0x180023509  mov     rbx, rcx
0x18002350c  xor     r15d, r15d
0x18002350f  mov     r8, [rdx+10h]
0x180023513  mov     rax, 7FFFFFFFFFFFFFFEh
0x18002351d  sub     rax, r8
0x180023520  cmp     rax, 1
0x180023524  jb      loc_18002378A
0x18002352a  cmp     qword ptr [rdx+18h], 7
0x18002352f  jbe     short loc_180023534
0x180023531  mov     rdx, [rdx]
0x180023534  mov     [rsp+100h+var_D0], 1
0x18002353d  lea     rax, asc_18006BB74; "_"
0x180023544  mov     [rsp+100h+lpcbData], rax
0x180023549  mov     [rsp+100h+phkResult], r8
0x18002354e  mov     r9, rdx
0x180023551  lea     rcx, [rbp+57h+var_60]
0x180023555  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002355a  nop
0x18002355b  mov     r8, rdi
0x18002355e  lea     rdx, [rbp+57h+var_60]
0x180023562  lea     rcx, [rbp+57h+lpValueName]
0x180023566  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002356b  nop
0x18002356c  lea     rcx, [rbp+57h+var_60]; void *
0x180023570  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023575  lea     rsi, [rbp+57h+lpValueName]
0x180023579  cmp     [rbp+57h+var_68], 7
0x18002357e  cmova   rsi, [rbp+57h+lpValueName]
0x180023583  add     rbx, 8
0x180023587  cmp     qword ptr [rbx+18h], 7
0x18002358c  jbe     short loc_180023591
0x18002358e  mov     rbx, [rbx]
0x180023591  mov     [rbp+57h+Type], r15d
0x180023595  mov     [rbp+57h+hKey], r15
0x180023599  mov     [rbp+57h+cbData], r15d
0x18002359d  mov     rdi, r15
0x1800235a0  cmp     cs:dword_180098D58, r15d
0x1800235a7  jnz     short loc_1800235F3
0x1800235a9  mov     cs:dword_180098D54, r15d
0x1800235b0  xorps   xmm0, xmm0
0x1800235b3  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x1800235b7  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800235bb  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800235bf  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x1800235c3  call    cs:__imp_GetNativeSystemInfo
0x1800235c9  mov     eax, 6
0x1800235ce  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x1800235d2  jz      short loc_1800235DF
0x1800235d4  mov     eax, 9
0x1800235d9  cmp     ax, word ptr [rbp+57h+SystemInfo]
0x1800235dd  jnz     short loc_1800235E9
0x1800235df  mov     cs:dword_180098D54, 1
0x1800235e9  mov     cs:dword_180098D58, 1
0x1800235f3  mov     eax, 101h
0x1800235f8  mov     r9d, 1
0x1800235fe  cmp     cs:dword_180098D54, r15d
0x180023605  cmovnz  r9d, eax; samDesired
0x180023609  lea     rax, [rbp+57h+hKey]
0x18002360d  mov     [rsp+100h+phkResult], rax; phkResult
0x180023612  xor     r8d, r8d; ulOptions
0x180023615  mov     rdx, rbx; lpSubKey
0x180023618  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002361f  call    cs:__imp_RegOpenKeyExW
0x180023625  mov     ebx, eax
0x180023627  test    eax, eax
0x180023629  jnz     loc_1800236C0
0x18002362f  lea     rax, [rbp+57h+cbData]
0x180023633  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180023638  mov     [rsp+100h+phkResult], r15; lpData
0x18002363d  lea     r9, [rbp+57h+Type]; lpType
0x180023641  xor     r8d, r8d; lpReserved
0x180023644  mov     rdx, rsi; lpValueName
0x180023647  mov     rcx, [rbp+57h+hKey]; hKey
0x18002364b  call    cs:__imp_RegQueryValueExW
0x180023651  mov     ebx, eax
0x180023653  test    eax, eax
0x180023655  jnz     short loc_1800236C0
0x180023657  mov     eax, [rbp+57h+cbData]
0x18002365a  test    eax, eax
0x18002365c  jz      short loc_1800236CB
0x18002365e  cmp     [rbp+57h+Type], 1
0x180023662  jz      short loc_18002366B
0x180023664  mov     ebx, 8007000Dh
0x180023669  jmp     short loc_1800236CF
0x18002366b  add     eax, 2
0x18002366e  mov     [rbp+57h+cbData], eax
0x180023671  mov     ecx, eax; this
0x180023673  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180023678  mov     rdi, rax
0x18002367b  test    rax, rax
0x18002367e  jnz     short loc_180023687
0x180023680  mov     ebx, 8007000Eh
0x180023685  jmp     short loc_1800236CF
0x180023687  lea     rax, [rbp+57h+cbData]
0x18002368b  mov     [rsp+100h+lpcbData], rax; lpcbData
0x180023690  mov     [rsp+100h+phkResult], rdi; lpData
0x180023695  lea     r9, [rbp+57h+Type]; lpType
0x180023699  xor     r8d, r8d; lpReserved
0x18002369c  mov     rdx, rsi; lpValueName
0x18002369f  mov     rcx, [rbp+57h+hKey]; hKey
0x1800236a3  call    cs:__imp_RegQueryValueExW
0x1800236a9  mov     ebx, eax
0x1800236ab  test    eax, eax
0x1800236ad  jnz     short loc_1800236C0
0x1800236af  mov     ebx, r15d
0x1800236b2  mov     ecx, [rbp+57h+cbData]
0x1800236b5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800236b9  mov     [rcx+rdi], r15w
0x1800236be  jmp     short loc_1800236F4
0x1800236c0  jle     short loc_1800236CB
0x1800236c2  movzx   ebx, ax
0x1800236c5  or      ebx, 80070000h
0x1800236cb  test    ebx, ebx
0x1800236cd  jns     short loc_1800236F4
0x1800236cf  mov     rcx, rdi; this
0x1800236d2  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x1800236d7  mov     rdi, r15
0x1800236da  cmp     ebx, 80070002h
0x1800236e0  jz      short loc_1800236F4
0x1800236e2  mov     r8d, ebx; int
0x1800236e5  mov     rdx, rsi; unsigned __int16 *
0x1800236e8  lea     rcx, aString_0; "string"
0x1800236ef  call    ?ReportRegUtilQueryValueFailed@TelemetryProvider@WaasMedic@@SAXPEBG0J@Z; WaasMedic::TelemetryProvider::ReportRegUtilQueryValueFailed(ushort const *,ushort const *,long)
0x1800236f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800236f8  test    rcx, rcx
0x1800236fb  jz      short loc_180023703
0x1800236fd  call    cs:__imp_RegCloseKey
0x180023703  cmp     ebx, 80070002h
0x180023709  jz      short loc_180023763
0x18002370b  test    ebx, ebx
0x18002370d  jns     short loc_18002371C
0x18002370f  lea     rcx, [rbp+57h+lpValueName]; void *
0x180023713  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023718  mov     eax, ebx
0x18002371a  jmp     short loc_18002376E
0x18002371c  mov     dword ptr [r14+20h], 5
0x180023724  xorps   xmm0, xmm0
0x180023727  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x18002372b  xorps   xmm1, xmm1
0x18002372e  movdqu  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm1
0x180023733  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023737  inc     r8
0x18002373a  cmp     [rdi+r8*2], r15w
0x18002373f  jnz     short loc_180023737
0x180023741  mov     rdx, rdi
0x180023744  lea     rcx, [rbp+57h+SystemInfo]
0x180023748  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002374d  lea     rdx, [rbp+57h+SystemInfo]
0x180023751  mov     rcx, r14
0x180023754  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023759  lea     rcx, [rbp+57h+SystemInfo]; void *
0x18002375d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023762  nop
0x180023763  lea     rcx, [rbp+57h+lpValueName]; void *
0x180023767  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002376c  xor     eax, eax
0x18002376e  mov     rcx, [rbp+57h+var_40]
0x180023772  xor     rcx, rsp; StackCookie
0x180023775  call    __security_check_cookie
0x18002377a  add     rsp, 0D8h
0x180023781  pop     r15
0x180023783  pop     r14
0x180023785  pop     rdi
0x180023786  pop     rsi
0x180023787  pop     rbx
0x180023788  pop     rbp
0x180023789  retn
0x18002378a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```

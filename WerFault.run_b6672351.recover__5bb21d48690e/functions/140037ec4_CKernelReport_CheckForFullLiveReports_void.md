# CKernelReport::CheckForFullLiveReports(void)

- ea: `0x140037ec4`
- end: `0x14003826c`
- name: `?CheckForFullLiveReports@CKernelReport@@AEAAJXZ`
- size: `936`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14003b784`

## callees

- `0x140002490`
- `0x14000551c`
- `0x1400372dc`
- `0x140037ec4`
- `0x140038760`
- `0x14003b56c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140037fd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140038105`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140037fd7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140038105`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140038065`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140038194`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140038065`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140038194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400381ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003821f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140038236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400381ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003821f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140038236`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140037f42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140037f8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003809f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140037f42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140037f8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003809f`

## string_xrefs

- `0x1400380b8`: `Failed to open the sub key %ws while reporting for all kernel reports`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CKernelReport::CheckForFullLiveReports(CKernelReport *this)
{
  HKEY *v2; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  HKEY *v6; // rax
  LSTATUS v7; // eax
  DWORD v8; // edi
  HKEY *v9; // rax
  LSTATUS v10; // eax
  __int64 v11; // rdx
  DWORD v12; // ebx
  LSTATUS v13; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulta; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultb; // [rsp+20h] [rbp-E0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v22; // [rsp+68h] [rbp-98h] BYREF
  HKEY v23; // [rsp+70h] [rbp-90h] BYREF
  HKEY v24; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[256]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v27[256]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v23 = 0;
  hKey[0] = 0;
  cSubKeys = 0;
  v22 = 0;
  cchName = 0;
  v27[0] = 0;
  Name[0] = 0;
  v2 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszLiveKernelReportsQueueRoot, 0, 0xF003Fu, v2);
  v4 = v3;
  v5 = v3 <= 0;
  if ( !v3 )
  {
    v6 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v23);
    v3 = RegOpenKeyExW(hKey[0], L"FullLiveKernelReports", 0, 0xF003Fu, v6);
    v4 = v3;
    v5 = v3 <= 0;
    if ( !v3 )
    {
      v7 = RegQueryInfoKeyW(v23, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v4 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        LODWORD(phkResult) = v4;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0xA75,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::CheckForFullLiveReports",
          phkResult,
          (int)"Failed to enumerate the report types",
          lpcbMaxClassLen);
        goto LABEL_25;
      }
      v8 = cSubKeys;
      while ( 1 )
      {
        do
        {
          if ( !v8 )
          {
            v4 = 0;
            goto LABEL_25;
          }
          cchName = 256;
          Name[0] = 0;
          --v8;
        }
        while ( RegEnumKeyExW(v23, v8, Name, &cchName, 0, 0, 0, 0) );
        v24 = 0;
        v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
        v10 = RegOpenKeyExW(v23, Name, 0, 0xF003Fu, v9);
        if ( v10 )
        {
          lpcbMaxSubKeyLen = "Failed to open the sub key %ws while reporting for all kernel reports";
          v11 = 2721;
        }
        else
        {
          v10 = RegQueryInfoKeyW(v24, 0, 0, 0, &v22, 0, 0, 0, 0, 0, 0, 0);
          if ( !v10 )
          {
            v12 = v22;
            while ( v12 )
            {
              cchName = 256;
              v27[0] = 0;
              v13 = RegEnumKeyExW(v24, --v12, v27, &cchName, 0, 0, 0, 0);
              if ( v13 )
              {
                LODWORD(phkResultb) = v13;
                wil::details::in1diag4::Log_Win32Msg(
                  retaddr,
                  (void *)0xACB,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                  "CKernelReport::CheckForFullLiveReports",
                  phkResultb,
                  (unsigned int)"Failed to enum the keys for full live kernel event %ws",
                  (const char *)Name);
              }
              else
              {
                CKernelReport::ConvertLiveDumpAndReport(this, Name, v27);
              }
            }
            goto LABEL_21;
          }
          lpcbMaxSubKeyLen = "Failed to query the report id count for %ws.";
          v11 = 2743;
        }
        LODWORD(phkResulta) = v10;
        wil::details::in1diag4::Log_Win32Msg(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::CheckForFullLiveReports",
          phkResulta,
          (unsigned int)lpcbMaxSubKeyLen,
          (const char *)Name);
LABEL_21:
        if ( v24 )
          RegCloseKey(v24);
      }
    }
  }
  if ( !v5 )
    v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_25:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v23 )
    RegCloseKey(v23);
  return v4;
}

```

## disassembly

```asm
0x140037ec4  mov     [rsp-8+arg_8], rbx
0x140037ec9  mov     [rsp-8+arg_10], rsi
0x140037ece  push    rbp
0x140037ecf  push    rdi
0x140037ed0  push    r14
0x140037ed2  lea     rbp, [rsp-3A0h]
0x140037eda  sub     rsp, 4A0h
0x140037ee1  mov     rax, cs:__security_cookie
0x140037ee8  xor     rax, rsp
0x140037eeb  mov     [rbp+3B0h+var_20], rax
0x140037ef2  mov     rsi, rcx
0x140037ef5  xor     r14d, r14d
0x140037ef8  mov     [rsp+4B0h+var_440], r14
0x140037efd  mov     [rbp+3B0h+hKey], r14
0x140037f01  mov     [rsp+4B0h+cSubKeys], r14d
0x140037f06  mov     [rsp+4B0h+var_448], r14d
0x140037f0b  mov     [rsp+4B0h+cchName], r14d
0x140037f10  mov     [rbp+3B0h+var_220], r14w
0x140037f18  mov     [rbp+3B0h+Name], r14w
0x140037f1d  lea     rcx, [rbp+3B0h+hKey]
0x140037f21  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140037f26  mov     [rsp+4B0h+phkResult], rax; phkResult
0x140037f2b  mov     r9d, 0F003Fh; samDesired
0x140037f31  xor     r8d, r8d; ulOptions
0x140037f34  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x140037f3b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140037f42  call    cs:__imp_RegOpenKeyExW
0x140037f49  nop     dword ptr [rax+rax+00h]
0x140037f4e  mov     ebx, eax
0x140037f50  test    eax, eax
0x140037f52  jz      short loc_140037F68
0x140037f54  jle     loc_140038216
0x140037f5a  movzx   ebx, ax
0x140037f5d  or      ebx, 80070000h
0x140037f63  jmp     loc_140038216
0x140037f68  lea     rcx, [rsp+4B0h+var_440]
0x140037f6d  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140037f72  mov     [rsp+4B0h+phkResult], rax; phkResult
0x140037f77  mov     r9d, 0F003Fh; samDesired
0x140037f7d  xor     r8d, r8d; ulOptions
0x140037f80  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x140037f87  mov     rcx, [rbp+3B0h+hKey]; hKey
0x140037f8b  call    cs:__imp_RegOpenKeyExW
0x140037f92  nop     dword ptr [rax+rax+00h]
0x140037f97  mov     ebx, eax
0x140037f99  test    eax, eax
0x140037f9b  jnz     short loc_140037F54
0x140037f9d  mov     [rsp+4B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140037fa2  mov     [rsp+4B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140037fa7  mov     [rsp+4B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140037fac  mov     [rsp+4B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140037fb1  mov     [rsp+4B0h+lpcValues], r14; lpcValues
0x140037fb6  mov     [rsp+4B0h+lpcbMaxClassLen], r14; char *
0x140037fbb  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140037fc0  lea     rax, [rsp+4B0h+cSubKeys]
0x140037fc5  mov     [rsp+4B0h+phkResult], rax; lpcSubKeys
0x140037fca  xor     r9d, r9d; lpReserved
0x140037fcd  xor     r8d, r8d; lpcchClass
0x140037fd0  xor     edx, edx; lpClass
0x140037fd2  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140037fd7  call    cs:__imp_RegQueryInfoKeyW
0x140037fde  nop     dword ptr [rax+rax+00h]
0x140037fe3  mov     ebx, eax
0x140037fe5  test    eax, eax
0x140037fe7  jz      short loc_140038028
0x140037fe9  jle     short loc_140037FF4
0x140037feb  movzx   ebx, ax
0x140037fee  or      ebx, 80070000h
0x140037ff4  mov     rcx, [rbp+3B8h]; this
0x140037ffb  lea     rax, aFailedToEnumer; "Failed to enumerate the report types"
0x140038002  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rax; int
0x140038007  mov     dword ptr [rsp+4B0h+phkResult], ebx; wil::details *
0x14003800b  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x140038012  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038019  mov     edx, 0A75h; void *
0x14003801e  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140038023  jmp     loc_140038216
0x140038028  mov     edi, [rsp+4B0h+cSubKeys]
0x14003802c  jmp     loc_14003820B
0x140038031  mov     [rsp+4B0h+cchName], 100h
0x140038039  mov     [rbp+3B0h+Name], r14w
0x14003803e  lea     edx, [rdi-1]; dwIndex
0x140038041  mov     edi, edx
0x140038043  mov     [rsp+4B0h+lpcValues], r14; lpftLastWriteTime
0x140038048  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcchClass
0x14003804d  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpClass
0x140038052  mov     [rsp+4B0h+phkResult], r14; lpReserved
0x140038057  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x14003805c  lea     r8, [rbp+3B0h+Name]; lpName
0x140038060  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140038065  call    cs:__imp_RegEnumKeyExW
0x14003806c  nop     dword ptr [rax+rax+00h]
0x140038071  test    eax, eax
0x140038073  jnz     loc_14003820B
0x140038079  mov     [rsp+4B0h+var_438], r14
0x14003807e  lea     rcx, [rsp+4B0h+var_438]
0x140038083  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140038088  mov     [rsp+4B0h+phkResult], rax; phkResult
0x14003808d  mov     r9d, 0F003Fh; samDesired
0x140038093  xor     r8d, r8d; ulOptions
0x140038096  lea     rdx, [rbp+3B0h+Name]; lpSubKey
0x14003809a  mov     rcx, [rsp+4B0h+var_440]; hKey
0x14003809f  call    cs:__imp_RegOpenKeyExW
0x1400380a6  nop     dword ptr [rax+rax+00h]
0x1400380ab  test    eax, eax
0x1400380ad  jz      short loc_1400380CB
0x1400380af  lea     rdx, [rbp+3B0h+Name]
0x1400380b3  mov     [rsp+4B0h+lpcbMaxClassLen], rdx
0x1400380b8  lea     rdx, aFailedToOpenTh; "Failed to open the sub key %ws while re"...
0x1400380bf  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx
0x1400380c4  mov     edx, 0AA1h
0x1400380c9  jmp     short loc_14003812F
0x1400380cb  mov     [rsp+4B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1400380d0  mov     [rsp+4B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400380d5  mov     [rsp+4B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400380da  mov     [rsp+4B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1400380df  mov     [rsp+4B0h+lpcValues], r14; lpcValues
0x1400380e4  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1400380e9  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1400380ee  lea     rax, [rsp+4B0h+var_448]
0x1400380f3  mov     [rsp+4B0h+phkResult], rax; lpcSubKeys
0x1400380f8  xor     r9d, r9d; lpReserved
0x1400380fb  xor     r8d, r8d; lpcchClass
0x1400380fe  xor     edx, edx; lpClass
0x140038100  mov     rcx, [rsp+4B0h+var_438]; hKey
0x140038105  call    cs:__imp_RegQueryInfoKeyW
0x14003810c  nop     dword ptr [rax+rax+00h]
0x140038111  test    eax, eax
0x140038113  jz      short loc_140038152
0x140038115  lea     rdx, [rbp+3B0h+Name]
0x140038119  mov     [rsp+4B0h+lpcbMaxClassLen], rdx; char *
0x14003811e  lea     rdx, aFailedToQueryT; "Failed to query the report id count for"...
0x140038125  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x14003812a  mov     edx, 0AB7h; void *
0x14003812f  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140038136  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x14003813d  mov     dword ptr [rsp+4B0h+phkResult], eax; wil::details *
0x140038141  mov     rcx, [rbp+3B8h]; this
0x140038148  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x14003814d  jmp     loc_1400381F5
0x140038152  mov     ebx, [rsp+4B0h+var_448]
0x140038156  jmp     loc_1400381ED
0x14003815b  mov     [rsp+4B0h+cchName], 100h
0x140038163  mov     [rbp+3B0h+var_220], r14w
0x14003816b  dec     ebx
0x14003816d  mov     [rsp+4B0h+lpcValues], r14; lpftLastWriteTime
0x140038172  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcchClass
0x140038177  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpClass
0x14003817c  mov     [rsp+4B0h+phkResult], r14; lpReserved
0x140038181  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x140038186  lea     r8, [rbp+3B0h+var_220]; lpName
0x14003818d  mov     edx, ebx; dwIndex
0x14003818f  mov     rcx, [rsp+4B0h+var_438]; hKey
0x140038194  call    cs:__imp_RegEnumKeyExW
0x14003819b  nop     dword ptr [rax+rax+00h]
0x1400381a0  lea     rdx, [rbp+3B0h+Name]; wchar_t *
0x1400381a4  test    eax, eax
0x1400381a6  jz      short loc_1400381DE
0x1400381a8  mov     rcx, [rbp+3B8h]; this
0x1400381af  mov     [rsp+4B0h+lpcbMaxClassLen], rdx; char *
0x1400381b4  lea     rdx, aFailedToEnumTh_0; "Failed to enum the keys for full live k"...
0x1400381bb  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x1400381c0  mov     dword ptr [rsp+4B0h+phkResult], eax; wil::details *
0x1400381c4  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x1400381cb  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400381d2  mov     edx, 0ACBh; void *
0x1400381d7  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x1400381dc  jmp     short loc_1400381ED
0x1400381de  lea     r8, [rbp+3B0h+var_220]; wchar_t *
0x1400381e5  mov     rcx, rsi; this
0x1400381e8  call    ?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)
0x1400381ed  test    ebx, ebx
0x1400381ef  jnz     loc_14003815B
0x1400381f5  mov     rcx, [rsp+4B0h+var_438]; hKey
0x1400381fa  test    rcx, rcx
0x1400381fd  jz      short loc_14003820B
0x1400381ff  call    cs:__imp_RegCloseKey
0x140038206  nop     dword ptr [rax+rax+00h]
0x14003820b  test    edi, edi
0x14003820d  jnz     loc_140038031
0x140038213  mov     ebx, r14d
0x140038216  mov     rcx, [rbp+3B0h+hKey]; hKey
0x14003821a  test    rcx, rcx
0x14003821d  jz      short loc_14003822C
0x14003821f  call    cs:__imp_RegCloseKey
0x140038226  nop     dword ptr [rax+rax+00h]
0x14003822b  nop
0x14003822c  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140038231  test    rcx, rcx
0x140038234  jz      short loc_140038242
0x140038236  call    cs:__imp_RegCloseKey
0x14003823d  nop     dword ptr [rax+rax+00h]
0x140038242  mov     eax, ebx
0x140038244  mov     rcx, [rbp+3B0h+var_20]
0x14003824b  xor     rcx, rsp; StackCookie
0x14003824e  call    __security_check_cookie
0x140038253  lea     r11, [rsp+4B0h+var_10]
0x14003825b  mov     rbx, [r11+28h]
0x14003825f  mov     rsi, [r11+30h]
0x140038263  mov     rsp, r11
0x140038266  pop     r14
0x140038268  pop     rdi
0x140038269  pop     rbp
0x14003826a  retn
```

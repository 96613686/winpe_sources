# CDsmCore::_GetRegistryParameters(void)

- ea: `0x180023e70`
- end: `0x1800240c7`
- name: `?_GetRegistryParameters@CDsmCore@@AEAAXXZ`
- size: `599`
- prototype: `void __fastcall(CDsmCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800238e8`

## callees

- `0x18000bfc0`
- `0x180017adc`
- `0x180018368`
- `0x180018508`
- `0x180023e70`
- `0x180025294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023eab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023eab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023ee2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024015`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024057`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023ee2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023f92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024015`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024057`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023fd4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023fd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023f28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023f28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024072`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023f55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024072`

## string_xrefs

- `0x180023ffc`: `MaxThreadCount`

## pseudocode

```c
void __fastcall CDsmCore::_GetRegistryParameters(CDsmCore *this)
{
  CDsmCore *v1; // rcx
  __int64 v2; // rdx
  bool v3; // zf
  int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  unsigned int CoreServiceMode; // eax
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  int Data; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY v12; // [rsp+78h] [rbp+38h] BYREF

  v9 = HIDWORD(this);
  Data = 0;
  cbData = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
    {
      cbData = 4;
      RegGetValueW(hKey, L"Status", L"AuditBoot", 0x20000018u, 0, &Data, &cbData);
      if ( Data )
      {
        v2 = 4;
      }
      else
      {
        cbData = 4;
        if ( !CDsmCore::_IsOOBEInProgress(v1, hKey) )
        {
LABEL_10:
          RegCloseKey(hKey);
          goto LABEL_11;
        }
        v2 = 3;
      }
    }
    else
    {
      v2 = 2;
    }
    CDsmCore::_set_CoreServiceMode(v1, v2);
    goto LABEL_10;
  }
LABEL_11:
  if ( (unsigned int)CDsmCore::get_CoreServiceMode() != 2 )
  {
    cbData = 4;
    v3 = RegQueryValueExW(g_hPersistentStateKey, L"SessionNumber", 0, 0, (LPBYTE)&Data, &cbData) == 0;
    v4 = Data;
    if ( !v3 )
      v4 = *(_DWORD *)&::Data;
    *(_DWORD *)&::Data = v4 + 1;
    RegSetValueExW(g_hPersistentStateKey, L"SessionNumber", 0, 3u, &::Data, 4u);
    v12 = 0;
    if ( (int)GetDeviceSetupKey(&v12) >= 0 )
    {
      cbData = 4;
      if ( !RegQueryValueExW(v12, L"MaxThreadCount", 0, 0, (LPBYTE)&Data, &cbData) )
        LODWORD(qword_180059E34) = Data;
      if ( !(unsigned int)CDsmCore::get_CoreServiceMode() )
      {
        cbData = 4;
        if ( !RegQueryValueExW(v12, L"ManualMode", 0, 0, (LPBYTE)&Data, &cbData) )
        {
          if ( Data )
            CDsmCore::_set_CoreServiceMode(v5, 1);
        }
      }
      RegCloseKey(v12);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = qword_180059E34;
    CoreServiceMode = CDsmCore::get_CoreServiceMode();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids,
      CoreServiceMode,
      v6);
  }
}

```

## disassembly

```asm
0x180023e70  mov     qword ptr [rsp-18h+cbData], rcx
0x180023e75  push    rbp
0x180023e76  push    rbx
0x180023e77  push    rdi
0x180023e78  mov     rbp, rsp
0x180023e7b  sub     rsp, 40h
0x180023e7f  xor     ebx, ebx
0x180023e81  lea     rax, [rbp+hKey]
0x180023e85  mov     r9d, 20019h; samDesired
0x180023e8b  mov     [rbp+Data], ebx
0x180023e8e  xor     r8d, r8d; ulOptions
0x180023e91  mov     [rbp+cbData], ebx
0x180023e94  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180023e9b  mov     [rbp+hKey], rbx
0x180023e9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023ea6  mov     [rsp+40h+phkResult], rax; phkResult
0x180023eab  call    cs:__imp_RegOpenKeyExW
0x180023eb1  lea     edi, [rbx+4]
0x180023eb4  test    eax, eax
0x180023eb6  jnz     loc_180023F5B
0x180023ebc  mov     rcx, [rbp+hKey]; hKey
0x180023ec0  lea     rax, [rbp+cbData]
0x180023ec4  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023ec9  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180023ed0  lea     rax, [rbp+Data]
0x180023ed4  mov     [rbp+cbData], edi
0x180023ed7  xor     r9d, r9d; lpType
0x180023eda  mov     [rsp+40h+phkResult], rax; lpData
0x180023edf  xor     r8d, r8d; lpReserved
0x180023ee2  call    cs:__imp_RegQueryValueExW
0x180023ee8  test    eax, eax
0x180023eea  jnz     short loc_180023EF6
0x180023eec  cmp     [rbp+Data], ebx
0x180023eef  jz      short loc_180023EF6
0x180023ef1  lea     edx, [rbx+2]
0x180023ef4  jmp     short loc_180023F4C
0x180023ef6  mov     rcx, [rbp+hKey]; hkey
0x180023efa  lea     rax, [rbp+cbData]
0x180023efe  mov     [rsp+40h+pcbData], rax; pcbData
0x180023f03  lea     r8, aAuditboot; "AuditBoot"
0x180023f0a  lea     rax, [rbp+Data]
0x180023f0e  mov     [rbp+cbData], edi
0x180023f11  mov     [rsp+40h+lpcbData], rax; pvData
0x180023f16  lea     rdx, aStatus; "Status"
0x180023f1d  mov     r9d, 20000018h; dwFlags
0x180023f23  mov     [rsp+40h+phkResult], rbx; pdwType
0x180023f28  call    cs:__imp_RegGetValueW
0x180023f2e  cmp     [rbp+Data], ebx
0x180023f31  jz      short loc_180023F37
0x180023f33  mov     edx, edi
0x180023f35  jmp     short loc_180023F4C
0x180023f37  mov     rdx, [rbp+hKey]; HKEY
0x180023f3b  mov     [rbp+cbData], edi
0x180023f3e  call    ?_IsOOBEInProgress@CDsmCore@@AEAA_NPEAUHKEY__@@@Z; CDsmCore::_IsOOBEInProgress(HKEY__ *)
0x180023f43  test    al, al
0x180023f45  jz      short loc_180023F51
0x180023f47  mov     edx, 3
0x180023f4c  call    ?_set_CoreServiceMode@CDsmCore@@AEAAXW4DSM_SERVICE_MODE@@@Z; CDsmCore::_set_CoreServiceMode(DSM_SERVICE_MODE)
0x180023f51  mov     rcx, [rbp+hKey]; hKey
0x180023f55  call    cs:__imp_RegCloseKey
0x180023f5b  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x180023f60  cmp     eax, 2
0x180023f63  jz      loc_180024078
0x180023f69  mov     rcx, cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA; hKey
0x180023f70  lea     rax, [rbp+cbData]
0x180023f74  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023f79  lea     rdx, aSessionnumber; "SessionNumber"
0x180023f80  lea     rax, [rbp+Data]
0x180023f84  mov     [rbp+cbData], edi
0x180023f87  xor     r9d, r9d; lpType
0x180023f8a  mov     [rsp+40h+phkResult], rax; lpData
0x180023f8f  xor     r8d, r8d; lpReserved
0x180023f92  call    cs:__imp_RegQueryValueExW
0x180023f98  test    eax, eax
0x180023f9a  mov     eax, [rbp+Data]
0x180023f9d  jz      short loc_180023FA5
0x180023f9f  mov     eax, dword ptr cs:Data
0x180023fa5  mov     rcx, cs:?g_hPersistentStateKey@@3PEAUHKEY__@@EA; hKey
0x180023fac  lea     rdx, aSessionnumber; "SessionNumber"
0x180023fb3  inc     eax
0x180023fb5  mov     dword ptr [rsp+40h+lpcbData], edi; cbData
0x180023fb9  mov     dword ptr cs:Data, eax
0x180023fbf  mov     r9d, 3; dwType
0x180023fc5  lea     rax, Data
0x180023fcc  xor     r8d, r8d; Reserved
0x180023fcf  mov     [rsp+40h+phkResult], rax; lpData
0x180023fd4  call    cs:__imp_RegSetValueExW
0x180023fda  lea     rcx, [rbp+arg_18]; phkResult
0x180023fde  mov     [rbp+arg_18], rbx
0x180023fe2  call    ?GetDeviceSetupKey@@YAJPEAPEAUHKEY__@@@Z; GetDeviceSetupKey(HKEY__ * *)
0x180023fe7  test    eax, eax
0x180023fe9  js      loc_180024078
0x180023fef  mov     rcx, [rbp+arg_18]; hKey
0x180023ff3  lea     rax, [rbp+cbData]
0x180023ff7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180023ffc  lea     rdx, aMaxthreadcount; "MaxThreadCount"
0x180024003  lea     rax, [rbp+Data]
0x180024007  mov     [rbp+cbData], edi
0x18002400a  xor     r9d, r9d; lpType
0x18002400d  mov     [rsp+40h+phkResult], rax; lpData
0x180024012  xor     r8d, r8d; lpReserved
0x180024015  call    cs:__imp_RegQueryValueExW
0x18002401b  test    eax, eax
0x18002401d  jnz     short loc_180024028
0x18002401f  mov     eax, [rbp+Data]
0x180024022  mov     dword ptr cs:qword_180059E34, eax
0x180024028  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x18002402d  test    eax, eax
0x18002402f  jnz     short loc_18002406E
0x180024031  mov     rcx, [rbp+arg_18]; hKey
0x180024035  lea     rax, [rbp+cbData]
0x180024039  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002403e  lea     rdx, aManualmode; "ManualMode"
0x180024045  lea     rax, [rbp+Data]
0x180024049  mov     [rbp+cbData], edi
0x18002404c  xor     r9d, r9d; lpType
0x18002404f  mov     [rsp+40h+phkResult], rax; lpData
0x180024054  xor     r8d, r8d; lpReserved
0x180024057  call    cs:__imp_RegQueryValueExW
0x18002405d  test    eax, eax
0x18002405f  jnz     short loc_18002406E
0x180024061  cmp     [rbp+Data], ebx
0x180024064  jz      short loc_18002406E
0x180024066  lea     edx, [rax+1]
0x180024069  call    ?_set_CoreServiceMode@CDsmCore@@AEAAXW4DSM_SERVICE_MODE@@@Z; CDsmCore::_set_CoreServiceMode(DSM_SERVICE_MODE)
0x18002406e  mov     rcx, [rbp+arg_18]; hKey
0x180024072  call    cs:__imp_RegCloseKey
0x180024078  mov     rax, cs:WPP_GLOBAL_Control
0x18002407f  lea     rcx, WPP_GLOBAL_Control
0x180024086  cmp     rax, rcx
0x180024089  jz      short loc_1800240BF
0x18002408b  test    byte ptr [rax+1Ch], 1
0x18002408f  jz      short loc_1800240BF
0x180024091  mov     ebx, dword ptr cs:qword_180059E34
0x180024097  call    ?get_CoreServiceMode@CDsmCore@@QEAA?AW4DSM_SERVICE_MODE@@XZ; CDsmCore::get_CoreServiceMode(void)
0x18002409c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240a3  lea     r8, WPP_4cc58cc6a1783bc275847d39a4303946_Traceguids
0x1800240aa  mov     edx, 1Eh
0x1800240af  mov     dword ptr [rsp+40h+phkResult], ebx
0x1800240b3  mov     r9d, eax
0x1800240b6  mov     rcx, [rcx+10h]
0x1800240ba  call    WPP_SF_Dd
0x1800240bf  add     rsp, 40h
0x1800240c3  pop     rdi
0x1800240c4  pop     rbx
0x1800240c5  pop     rbp
0x1800240c6  retn
```

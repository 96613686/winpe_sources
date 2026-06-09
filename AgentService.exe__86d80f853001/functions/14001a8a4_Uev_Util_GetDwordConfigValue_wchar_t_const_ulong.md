# Uev::Util::GetDwordConfigValue(wchar_t const *,ulong)

- ea: `0x14001a8a4`
- end: `0x14001a9c1`
- name: `?GetDwordConfigValue@Util@Uev@@SAKPEB_WK@Z`
- size: `285`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400125ac`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000acc4`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x14001a8a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001a8f6`
- `ADVAPI32!RegOpenKeyExW` at `0x14001a8f6`
- `ADVAPI32!RegQueryValueExW` at `0x14001a932`
- `ADVAPI32!RegQueryValueExW` at `0x14001a932`

## string_xrefs

- `0x14001a992`: `Attempting to use an invalid handle.`
- `0x14001a8e8`: `SOFTWARE\Microsoft\UEV\Agent\Configuration`
- `0x14001a949`: `AgentService.Util::GetDwordConfigValue: Unexpected value type, type = 0x%X`
- `0x14001a959`: `AgentService.Util::GetDwordConfigValue: Failed to open configuration key, status = 0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::Util::GetDwordConfigValue(LPCWSTR lpValueName, unsigned int a2)
{
  _QWORD v5[4]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-9h] BYREF
  DWORD Type; // [rsp+90h] [rbp+37h] BYREF
  BYTE Data[4]; // [rsp+94h] [rbp+3Bh] BYREF
  DWORD cbData; // [rsp+98h] [rbp+3Fh] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+47h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\UEV\\Agent\\Configuration", 0, 0x20019u, &hKey) )
  {
    DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.Util::GetDwordConfigValue: Failed to open configuration key, status = 0x%X");
  }
  else
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !hKey )
    {
      std::wstring::wstring(v5, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, v5);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    if ( !RegQueryValueExW(hKey, lpValueName, 0, &Type, Data, &cbData) )
    {
      if ( Type == 4 )
        a2 = *(_DWORD *)Data;
      else
        DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.Util::GetDwordConfigValue: Unexpected value type, type = 0x%X");
    }
  }
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  return a2;
}

```

## disassembly

```asm
0x14001a8a4  mov     [rsp-8+arg_8], rbx
0x14001a8a9  mov     [rsp-8+arg_10], rdi
0x14001a8ae  push    rbp
0x14001a8af  lea     rbp, [rsp-57h]
0x14001a8b4  sub     rsp, 0B0h
0x14001a8bb  mov     rax, cs:__security_cookie
0x14001a8c2  xor     rax, rsp
0x14001a8c5  mov     [rbp+57h+var_8], rax
0x14001a8c9  mov     ebx, edx
0x14001a8cb  mov     rdi, rcx
0x14001a8ce  mov     [rbp+57h+hKey], 0
0x14001a8d6  lea     rax, [rbp+57h+hKey]
0x14001a8da  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14001a8df  mov     r9d, 20019h; samDesired
0x14001a8e5  xor     r8d, r8d; ulOptions
0x14001a8e8  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\UEV\\Agent\\Config"...
0x14001a8ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001a8f6  call    cs:__imp_RegOpenKeyExW
0x14001a8fc  test    eax, eax
0x14001a8fe  jnz     short loc_14001A957
0x14001a900  mov     [rbp+57h+Type], eax
0x14001a903  mov     dword ptr [rbp+57h+Data], eax
0x14001a906  mov     [rbp+57h+cbData], 4
0x14001a90d  mov     rcx, [rbp+57h+hKey]; hKey
0x14001a911  test    rcx, rcx
0x14001a914  jz      short loc_14001A992
0x14001a916  lea     rax, [rbp+57h+cbData]
0x14001a91a  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x14001a91f  lea     rax, [rbp+57h+Data]
0x14001a923  mov     [rsp+0B0h+phkResult], rax; lpData
0x14001a928  lea     r9, [rbp+57h+Type]; lpType
0x14001a92c  xor     r8d, r8d; lpReserved
0x14001a92f  mov     rdx, rdi; lpValueName
0x14001a932  call    cs:__imp_RegQueryValueExW
0x14001a938  test    eax, eax
0x14001a93a  jnz     short loc_14001A966
0x14001a93c  mov     edx, [rbp+57h+Type]
0x14001a93f  cmp     edx, 4
0x14001a942  jnz     short loc_14001A949
0x14001a944  mov     ebx, dword ptr [rbp+57h+Data]
0x14001a947  jmp     short loc_14001A966
0x14001a949  lea     rcx, aAgentserviceUt_2; "AgentService.Util::GetDwordConfigValue:"...
0x14001a950  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001a955  jmp     short loc_14001A966
0x14001a957  mov     edx, eax
0x14001a959  lea     rcx, aAgentserviceUt_1; "AgentService.Util::GetDwordConfigValue:"...
0x14001a960  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001a965  nop
0x14001a966  lea     rcx, [rbp+57h+hKey]
0x14001a96a  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14001a96f  mov     eax, ebx
0x14001a971  mov     rcx, [rbp+57h+var_8]
0x14001a975  xor     rcx, rsp; StackCookie
0x14001a978  call    __security_check_cookie
0x14001a97d  lea     r11, [rsp+0B0h+var_s0]
0x14001a985  mov     rbx, [r11+18h]
0x14001a989  mov     rdi, [r11+20h]
0x14001a98d  mov     rsp, r11
0x14001a990  pop     rbp
0x14001a991  retn
0x14001a992  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14001a999  lea     rcx, [rbp+57h+var_80]
0x14001a99d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001a9a2  nop
0x14001a9a3  lea     rdx, [rbp+57h+var_80]
0x14001a9a7  lea     rcx, [rbp+57h+pExceptionObject]
0x14001a9ab  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14001a9b0  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14001a9b7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001a9bb  call    _CxxThrowException_0
```

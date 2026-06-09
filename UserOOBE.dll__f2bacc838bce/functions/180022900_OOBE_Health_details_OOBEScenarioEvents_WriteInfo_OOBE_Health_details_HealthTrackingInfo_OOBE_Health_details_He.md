# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x180022900`
- end: `0x180022a30`
- name: `??$WriteInfo@UHealthTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthTrackingInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800225a8`
- `0x18002261c`
- `0x18002307c`
- `0x180033b3c`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180018c98`
- `0x18001f168`
- `0x180022900`
- `0x180025b8c`
- `0x1800279b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800229eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800229eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800229b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800229b3`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(
        const WCHAR *a1,
        const BYTE *a2,
        HKEY a3,
        _BYTE *a4,
        _BYTE *a5)
{
  __int64 result; // rax
  int RedirectionKeyPath; // eax
  unsigned int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a3;
  lpSubKey = a1;
  result = (__int64)a5;
  if ( *a5 && *a4 )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpSubKey,
      0);
    RedirectionKeyPath = GetRedirectionKeyPath(
                           L"OOBEHealth",
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
                           (unsigned __int16 **)&lpSubKey);
    if ( RedirectionKeyPath < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)(unsigned int)RedirectionKeyPath,
        phkResult);
LABEL_11:
      *a4 = 0;
      return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    v10 = retaddr;
    if ( v9 )
    {
      v11 = 1074;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"Health", 0, 3u, a2, 0xACu);
      v10 = retaddr;
      if ( !v9 )
      {
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_11;
      }
      v11 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(
      v10,
      (void *)v11,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v9,
      phkResulta);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x180022900  mov     r11, rsp
0x180022903  mov     [r11+10h], rbx
0x180022907  mov     [r11+18h], r8
0x18002290b  mov     [r11+8], rcx
0x18002290f  push    rdi
0x180022910  sub     rsp, 30h
0x180022914  mov     rbx, r9
0x180022917  mov     rdi, rdx
0x18002291a  mov     rax, [rsp+38h+arg_20]
0x18002291f  cmp     byte ptr [rax], 0
0x180022922  jz      loc_180022A25
0x180022928  cmp     byte ptr [r9], 0
0x18002292c  jz      loc_180022A25
0x180022932  mov     qword ptr [r11+8], 0
0x18002293a  xor     edx, edx
0x18002293c  lea     rcx, [r11+8]
0x180022940  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180022945  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x18002294a  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022951  lea     rcx, aOobehealth; "OOBEHealth"
0x180022958  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x18002295d  mov     rcx, [rsp+38h]; this
0x180022962  test    eax, eax
0x180022964  jns     short loc_18002297F
0x180022966  mov     r9d, eax; char *
0x180022969  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022970  mov     edx, 42Fh; void *
0x180022975  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002297a  jmp     loc_180022A18
0x18002297f  mov     [rsp+38h+hKey], 0
0x180022988  xor     edx, edx
0x18002298a  lea     rcx, [rsp+38h+hKey]
0x18002298f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022994  lea     rax, [rsp+38h+hKey]
0x180022999  mov     [rsp+38h+phkResult], rax; phkResult
0x18002299e  mov     r9d, 0F003Fh; samDesired
0x1800229a4  xor     r8d, r8d; ulOptions
0x1800229a7  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x1800229ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800229b3  call    cs:__imp_RegOpenKeyExW
0x1800229b9  mov     rcx, [rsp+38h]
0x1800229be  test    eax, eax
0x1800229c0  jz      short loc_1800229C9
0x1800229c2  mov     edx, 432h
0x1800229c7  jmp     short loc_1800229FF
0x1800229c9  mov     [rsp+38h+cbData], 0ACh; cbData
0x1800229d1  mov     [rsp+38h+phkResult], rdi; unsigned int
0x1800229d6  mov     r9d, 3; dwType
0x1800229dc  xor     r8d, r8d; Reserved
0x1800229df  lea     rdx, aHealth; "Health"
0x1800229e6  mov     rcx, [rsp+38h+hKey]; hKey
0x1800229eb  call    cs:__imp_RegSetValueExW
0x1800229f1  mov     rcx, [rsp+38h]; this
0x1800229f6  test    eax, eax
0x1800229f8  jz      short loc_180022A0E
0x1800229fa  mov     edx, 435h; void *
0x1800229ff  mov     r9d, eax; char *
0x180022a02  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022a09  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180022a0e  lea     rcx, [rsp+38h+hKey]
0x180022a13  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022a18  mov     byte ptr [rbx], 0
0x180022a1b  lea     rcx, [rsp+38h+lpSubKey]
0x180022a20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022a25  mov     rbx, [rsp+38h+arg_8]
0x180022a2a  add     rsp, 30h
0x180022a2e  pop     rdi
0x180022a2f  retn
```

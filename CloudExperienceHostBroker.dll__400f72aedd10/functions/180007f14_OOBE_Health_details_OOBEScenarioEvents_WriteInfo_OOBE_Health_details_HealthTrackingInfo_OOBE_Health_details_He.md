# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x180007f14`
- end: `0x180008031`
- name: `??$WriteInfo@UHealthTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthTrackingInfo@123@AEA_N2PEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(HKEY, const BYTE *, const WCHAR *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020cc0`

## callees

- `0x180007f14`
- `0x180012408`
- `0x180018be8`
- `0x18001a980`
- `0x18002253c`
- `0x180024614`
- `0x18002646c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007ff3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007ff3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007fbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(
        HKEY a1,
        const BYTE *a2,
        const WCHAR *a3,
        _BYTE *a4,
        _BYTE *a5)
{
  __int64 result; // rax
  int RedirectionKeyPath; // eax
  unsigned int v9; // eax
  unsigned int v10; // r8d
  wil::details::in1diag3 *v11; // rcx
  __int64 v12; // rdx
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+18h] BYREF

  lpSubKey = a3;
  hKey = a1;
  result = (__int64)a5;
  if ( *a5 && *a4 )
  {
    lpSubKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
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
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
    v11 = retaddr;
    if ( v9 )
    {
      v12 = 1074;
    }
    else
    {
      v9 = RegSetValueExW(hKey, L"Health", 0, 3u, a2, 0xACu);
      v11 = retaddr;
      if ( !v9 )
      {
LABEL_10:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_11;
      }
      v12 = 1077;
    }
    wil::details::in1diag3::_Log_Win32(v11, (void *)v12, v10, (const char *)v9, phkResulta);
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x180007f14  mov     r11, rsp
0x180007f17  mov     [r11+10h], rbx
0x180007f1b  mov     [r11+18h], r8
0x180007f1f  mov     [r11+8], rcx
0x180007f23  push    rdi
0x180007f24  sub     rsp, 30h
0x180007f28  mov     rbx, r9
0x180007f2b  mov     rdi, rdx
0x180007f2e  mov     rax, [rsp+38h+arg_20]
0x180007f33  cmp     byte ptr [rax], 0
0x180007f36  jz      loc_180008026
0x180007f3c  cmp     byte ptr [r9], 0
0x180007f40  jz      loc_180008026
0x180007f46  mov     qword ptr [r11+18h], 0
0x180007f4e  xor     edx, edx
0x180007f50  lea     rcx, [r11+18h]
0x180007f54  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180007f59  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180007f5e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007f65  lea     rcx, aOobehealth; "OOBEHealth"
0x180007f6c  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180007f71  mov     rcx, [rsp+38h]; this
0x180007f76  test    eax, eax
0x180007f78  jns     short loc_180007F93
0x180007f7a  mov     r9d, eax; char *
0x180007f7d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180007f84  mov     edx, 42Fh; void *
0x180007f89  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007f8e  jmp     loc_180008019
0x180007f93  mov     [rsp+38h+hKey], 0
0x180007f9c  lea     rax, [rsp+38h+hKey]
0x180007fa1  mov     [rsp+38h+phkResult], rax; phkResult
0x180007fa6  mov     r9d, 0F003Fh; samDesired
0x180007fac  xor     r8d, r8d; ulOptions
0x180007faf  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180007fb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007fbb  call    cs:__imp_RegOpenKeyExW
0x180007fc1  mov     rcx, [rsp+38h]
0x180007fc6  test    eax, eax
0x180007fc8  jz      short loc_180007FD1
0x180007fca  mov     edx, 432h
0x180007fcf  jmp     short loc_180008007
0x180007fd1  mov     [rsp+38h+cbData], 0ACh; cbData
0x180007fd9  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180007fde  mov     r9d, 3; dwType
0x180007fe4  xor     r8d, r8d; Reserved
0x180007fe7  lea     rdx, ValueName; "Health"
0x180007fee  mov     rcx, [rsp+38h+hKey]; hKey
0x180007ff3  call    cs:__imp_RegSetValueExW
0x180007ff9  mov     rcx, [rsp+38h]; this
0x180007ffe  test    eax, eax
0x180008000  jz      short loc_18000800F
0x180008002  mov     edx, 435h; void *
0x180008007  mov     r9d, eax; char *
0x18000800a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000800f  lea     rcx, [rsp+38h+hKey]
0x180008014  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180008019  mov     byte ptr [rbx], 0
0x18000801c  lea     rcx, [rsp+38h+lpSubKey]
0x180008021  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008026  mov     rbx, [rsp+38h+arg_8]
0x18000802b  add     rsp, 30h
0x18000802f  pop     rdi
0x180008030  retn
```

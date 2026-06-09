# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::CensusTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x180022690`
- end: `0x1800227c0`
- name: `??$WriteInfo@UCensusTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUCensusTrackingInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021c8c`
- `0x18002307c`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180018c98`
- `0x18001f168`
- `0x180022690`
- `0x180025b8c`
- `0x1800279b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002277b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002277b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022743`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022743`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(
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
      v9 = RegSetValueExW(hKey, L"Census", 0, 3u, a2, 0x10u);
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
0x180022690  mov     r11, rsp
0x180022693  mov     [r11+10h], rbx
0x180022697  mov     [r11+18h], r8
0x18002269b  mov     [r11+8], rcx
0x18002269f  push    rdi
0x1800226a0  sub     rsp, 30h
0x1800226a4  mov     rbx, r9
0x1800226a7  mov     rdi, rdx
0x1800226aa  mov     rax, [rsp+38h+arg_20]
0x1800226af  cmp     byte ptr [rax], 0
0x1800226b2  jz      loc_1800227B5
0x1800226b8  cmp     byte ptr [r9], 0
0x1800226bc  jz      loc_1800227B5
0x1800226c2  mov     qword ptr [r11+8], 0
0x1800226ca  xor     edx, edx
0x1800226cc  lea     rcx, [r11+8]
0x1800226d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800226d5  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x1800226da  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800226e1  lea     rcx, aOobehealth; "OOBEHealth"
0x1800226e8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800226ed  mov     rcx, [rsp+38h]; this
0x1800226f2  test    eax, eax
0x1800226f4  jns     short loc_18002270F
0x1800226f6  mov     r9d, eax; char *
0x1800226f9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022700  mov     edx, 42Fh; void *
0x180022705  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002270a  jmp     loc_1800227A8
0x18002270f  mov     [rsp+38h+hKey], 0
0x180022718  xor     edx, edx
0x18002271a  lea     rcx, [rsp+38h+hKey]
0x18002271f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180022724  lea     rax, [rsp+38h+hKey]
0x180022729  mov     [rsp+38h+phkResult], rax; phkResult
0x18002272e  mov     r9d, 0F003Fh; samDesired
0x180022734  xor     r8d, r8d; ulOptions
0x180022737  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x18002273c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022743  call    cs:__imp_RegOpenKeyExW
0x180022749  mov     rcx, [rsp+38h]
0x18002274e  test    eax, eax
0x180022750  jz      short loc_180022759
0x180022752  mov     edx, 432h
0x180022757  jmp     short loc_18002278F
0x180022759  mov     [rsp+38h+cbData], 10h; cbData
0x180022761  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180022766  mov     r9d, 3; dwType
0x18002276c  xor     r8d, r8d; Reserved
0x18002276f  lea     rdx, ValueName; "Census"
0x180022776  mov     rcx, [rsp+38h+hKey]; hKey
0x18002277b  call    cs:__imp_RegSetValueExW
0x180022781  mov     rcx, [rsp+38h]; this
0x180022786  test    eax, eax
0x180022788  jz      short loc_18002279E
0x18002278a  mov     edx, 435h; void *
0x18002278f  mov     r9d, eax; char *
0x180022792  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022799  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002279e  lea     rcx, [rsp+38h+hKey]
0x1800227a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800227a8  mov     byte ptr [rbx], 0
0x1800227ab  lea     rcx, [rsp+38h+lpSubKey]
0x1800227b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800227b5  mov     rbx, [rsp+38h+arg_8]
0x1800227ba  add     rsp, 30h
0x1800227be  pop     rdi
0x1800227bf  retn
```

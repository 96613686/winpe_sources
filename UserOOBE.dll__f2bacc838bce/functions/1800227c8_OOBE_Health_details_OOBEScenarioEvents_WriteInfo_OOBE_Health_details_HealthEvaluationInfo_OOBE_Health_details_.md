# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthEvaluationInfo &,bool &,bool &,ushort const *)

- ea: `0x1800227c8`
- end: `0x1800228f8`
- name: `??$WriteInfo@UHealthEvaluationInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthEvaluationInfo@123@AEA_N2PEBG@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002307c`
- `0x180023e38`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180018c98`
- `0x18001f168`
- `0x1800227c8`
- `0x180025b8c`
- `0x1800279b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800228b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800228b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002287b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002287b`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(
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
      v9 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, a2, 0xCu);
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
0x1800227c8  mov     r11, rsp
0x1800227cb  mov     [r11+10h], rbx
0x1800227cf  mov     [r11+18h], r8
0x1800227d3  mov     [r11+8], rcx
0x1800227d7  push    rdi
0x1800227d8  sub     rsp, 30h
0x1800227dc  mov     rbx, r9
0x1800227df  mov     rdi, rdx
0x1800227e2  mov     rax, [rsp+38h+arg_20]
0x1800227e7  cmp     byte ptr [rax], 0
0x1800227ea  jz      loc_1800228ED
0x1800227f0  cmp     byte ptr [r9], 0
0x1800227f4  jz      loc_1800228ED
0x1800227fa  mov     qword ptr [r11+8], 0
0x180022802  xor     edx, edx
0x180022804  lea     rcx, [r11+8]
0x180022808  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002280d  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180022812  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022819  lea     rcx, aOobehealth; "OOBEHealth"
0x180022820  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180022825  mov     rcx, [rsp+38h]; this
0x18002282a  test    eax, eax
0x18002282c  jns     short loc_180022847
0x18002282e  mov     r9d, eax; char *
0x180022831  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180022838  mov     edx, 42Fh; void *
0x18002283d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022842  jmp     loc_1800228E0
0x180022847  mov     [rsp+38h+hKey], 0
0x180022850  xor     edx, edx
0x180022852  lea     rcx, [rsp+38h+hKey]
0x180022857  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002285c  lea     rax, [rsp+38h+hKey]
0x180022861  mov     [rsp+38h+phkResult], rax; phkResult
0x180022866  mov     r9d, 0F003Fh; samDesired
0x18002286c  xor     r8d, r8d; ulOptions
0x18002286f  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180022874  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002287b  call    cs:__imp_RegOpenKeyExW
0x180022881  mov     rcx, [rsp+38h]
0x180022886  test    eax, eax
0x180022888  jz      short loc_180022891
0x18002288a  mov     edx, 432h
0x18002288f  jmp     short loc_1800228C7
0x180022891  mov     [rsp+38h+cbData], 0Ch; cbData
0x180022899  mov     [rsp+38h+phkResult], rdi; unsigned int
0x18002289e  mov     r9d, 3; dwType
0x1800228a4  xor     r8d, r8d; Reserved
0x1800228a7  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x1800228ae  mov     rcx, [rsp+38h+hKey]; hKey
0x1800228b3  call    cs:__imp_RegSetValueExW
0x1800228b9  mov     rcx, [rsp+38h]; this
0x1800228be  test    eax, eax
0x1800228c0  jz      short loc_1800228D6
0x1800228c2  mov     edx, 435h; void *
0x1800228c7  mov     r9d, eax; char *
0x1800228ca  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800228d1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800228d6  lea     rcx, [rsp+38h+hKey]
0x1800228db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800228e0  mov     byte ptr [rbx], 0
0x1800228e3  lea     rcx, [rsp+38h+lpSubKey]
0x1800228e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800228ed  mov     rbx, [rsp+38h+arg_8]
0x1800228f2  add     rsp, 30h
0x1800228f6  pop     rdi
0x1800228f7  retn
```

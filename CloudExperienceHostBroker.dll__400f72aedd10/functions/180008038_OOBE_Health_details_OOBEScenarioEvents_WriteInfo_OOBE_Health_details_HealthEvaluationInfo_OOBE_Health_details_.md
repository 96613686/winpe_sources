# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthEvaluationInfo &,bool &,bool &,ushort const *)

- ea: `0x180008038`
- end: `0x180008155`
- name: `??$WriteInfo@UHealthEvaluationInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthEvaluationInfo@123@AEA_N2PEBG@Z`
- size: `285`
- prototype: `__int64 __fastcall(HKEY, const BYTE *, const WCHAR *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023984`

## callees

- `0x180008038`
- `0x180012408`
- `0x180018be8`
- `0x18001a980`
- `0x18002253c`
- `0x180024614`
- `0x18002646c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008117`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(
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
      v9 = RegSetValueExW(hKey, L"HealthEvaluation", 0, 3u, a2, 0xCu);
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
0x180008038  mov     r11, rsp
0x18000803b  mov     [r11+10h], rbx
0x18000803f  mov     [r11+18h], r8
0x180008043  mov     [r11+8], rcx
0x180008047  push    rdi
0x180008048  sub     rsp, 30h
0x18000804c  mov     rbx, r9
0x18000804f  mov     rdi, rdx
0x180008052  mov     rax, [rsp+38h+arg_20]
0x180008057  cmp     byte ptr [rax], 0
0x18000805a  jz      loc_18000814A
0x180008060  cmp     byte ptr [r9], 0
0x180008064  jz      loc_18000814A
0x18000806a  mov     qword ptr [r11+18h], 0
0x180008072  xor     edx, edx
0x180008074  lea     rcx, [r11+18h]
0x180008078  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000807d  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180008082  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180008089  lea     rcx, aOobehealth; "OOBEHealth"
0x180008090  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180008095  mov     rcx, [rsp+38h]; this
0x18000809a  test    eax, eax
0x18000809c  jns     short loc_1800080B7
0x18000809e  mov     r9d, eax; char *
0x1800080a1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800080a8  mov     edx, 42Fh; void *
0x1800080ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800080b2  jmp     loc_18000813D
0x1800080b7  mov     [rsp+38h+hKey], 0
0x1800080c0  lea     rax, [rsp+38h+hKey]
0x1800080c5  mov     [rsp+38h+phkResult], rax; phkResult
0x1800080ca  mov     r9d, 0F003Fh; samDesired
0x1800080d0  xor     r8d, r8d; ulOptions
0x1800080d3  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x1800080d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800080df  call    cs:__imp_RegOpenKeyExW
0x1800080e5  mov     rcx, [rsp+38h]
0x1800080ea  test    eax, eax
0x1800080ec  jz      short loc_1800080F5
0x1800080ee  mov     edx, 432h
0x1800080f3  jmp     short loc_18000812B
0x1800080f5  mov     [rsp+38h+cbData], 0Ch; cbData
0x1800080fd  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180008102  mov     r9d, 3; dwType
0x180008108  xor     r8d, r8d; Reserved
0x18000810b  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x180008112  mov     rcx, [rsp+38h+hKey]; hKey
0x180008117  call    cs:__imp_RegSetValueExW
0x18000811d  mov     rcx, [rsp+38h]; this
0x180008122  test    eax, eax
0x180008124  jz      short loc_180008133
0x180008126  mov     edx, 435h; void *
0x18000812b  mov     r9d, eax; char *
0x18000812e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180008133  lea     rcx, [rsp+38h+hKey]
0x180008138  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000813d  mov     byte ptr [rbx], 0
0x180008140  lea     rcx, [rsp+38h+lpSubKey]
0x180008145  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000814a  mov     rbx, [rsp+38h+arg_8]
0x18000814f  add     rsp, 30h
0x180008153  pop     rdi
0x180008154  retn
```

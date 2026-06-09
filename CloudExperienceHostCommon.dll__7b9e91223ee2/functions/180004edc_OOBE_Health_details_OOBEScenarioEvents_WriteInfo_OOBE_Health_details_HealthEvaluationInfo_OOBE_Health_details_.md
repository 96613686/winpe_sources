# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthEvaluationInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthEvaluationInfo &,bool &,bool &,ushort const *)

- ea: `0x180004edc`
- end: `0x180005000`
- name: `??$WriteInfo@UHealthEvaluationInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthEvaluationInfo@123@AEA_N2PEBG@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800240f8`

## callees

- `0x180004edc`
- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180024d70`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004fbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004fbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f83`

## pseudocode

```c
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
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
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
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
    }
    hKey = 0;
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
0x180004edc  mov     r11, rsp
0x180004edf  mov     [r11+10h], rbx
0x180004ee3  mov     [r11+18h], r8
0x180004ee7  mov     [r11+8], rcx
0x180004eeb  push    rdi
0x180004eec  sub     rsp, 30h
0x180004ef0  mov     rbx, r9
0x180004ef3  mov     rdi, rdx
0x180004ef6  mov     rax, [rsp+38h+arg_20]
0x180004efb  cmp     byte ptr [rax], 0
0x180004efe  jz      loc_180004FF5
0x180004f04  cmp     byte ptr [r9], 0
0x180004f08  jz      loc_180004FF5
0x180004f0e  mov     qword ptr [r11+18h], 0
0x180004f16  xor     edx, edx
0x180004f18  lea     rcx, [r11+18h]
0x180004f1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180004f21  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180004f26  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004f2d  lea     rcx, aOobehealth; "OOBEHealth"
0x180004f34  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180004f39  mov     rcx, [rsp+38h]; this
0x180004f3e  test    eax, eax
0x180004f40  jns     short loc_180004F5B
0x180004f42  mov     r9d, eax; char *
0x180004f45  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004f4c  mov     edx, 42Fh; void *
0x180004f51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004f56  jmp     loc_180004FE8
0x180004f5b  mov     [rsp+38h+hKey], 0
0x180004f64  lea     rax, [rsp+38h+hKey]
0x180004f69  mov     [rsp+38h+phkResult], rax; phkResult
0x180004f6e  mov     r9d, 0F003Fh; samDesired
0x180004f74  xor     r8d, r8d; ulOptions
0x180004f77  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180004f7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004f83  call    cs:__imp_RegOpenKeyExW
0x180004f89  mov     rcx, [rsp+38h]
0x180004f8e  test    eax, eax
0x180004f90  jz      short loc_180004F99
0x180004f92  mov     edx, 432h
0x180004f97  jmp     short loc_180004FCF
0x180004f99  mov     [rsp+38h+cbData], 0Ch; cbData
0x180004fa1  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180004fa6  mov     r9d, 3; dwType
0x180004fac  xor     r8d, r8d; Reserved
0x180004faf  lea     rdx, aHealthevaluati; "HealthEvaluation"
0x180004fb6  mov     rcx, [rsp+38h+hKey]; hKey
0x180004fbb  call    cs:__imp_RegSetValueExW
0x180004fc1  mov     rcx, [rsp+38h]; this
0x180004fc6  test    eax, eax
0x180004fc8  jz      short loc_180004FDE
0x180004fca  mov     edx, 435h; void *
0x180004fcf  mov     r9d, eax; char *
0x180004fd2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004fd9  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180004fde  lea     rcx, [rsp+38h+hKey]
0x180004fe3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180004fe8  mov     byte ptr [rbx], 0
0x180004feb  lea     rcx, [rsp+38h+lpSubKey]
0x180004ff0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004ff5  mov     rbx, [rsp+38h+arg_8]
0x180004ffa  add     rsp, 30h
0x180004ffe  pop     rdi
0x180004fff  retn
```

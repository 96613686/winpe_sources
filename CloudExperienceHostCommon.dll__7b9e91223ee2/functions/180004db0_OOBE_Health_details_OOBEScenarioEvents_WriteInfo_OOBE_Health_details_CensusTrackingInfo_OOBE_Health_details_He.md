# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::CensusTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x180004db0`
- end: `0x180004ed4`
- name: `??$WriteInfo@UCensusTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUCensusTrackingInfo@123@AEA_N2PEBG@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058ee8`

## callees

- `0x180004db0`
- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180024d70`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004e8f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004e8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004e57`

## pseudocode

```c
__int64 __fastcall OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::CensusTrackingInfo>(
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
0x180004db0  mov     r11, rsp
0x180004db3  mov     [r11+10h], rbx
0x180004db7  mov     [r11+18h], r8
0x180004dbb  mov     [r11+8], rcx
0x180004dbf  push    rdi
0x180004dc0  sub     rsp, 30h
0x180004dc4  mov     rbx, r9
0x180004dc7  mov     rdi, rdx
0x180004dca  mov     rax, [rsp+38h+arg_20]
0x180004dcf  cmp     byte ptr [rax], 0
0x180004dd2  jz      loc_180004EC9
0x180004dd8  cmp     byte ptr [r9], 0
0x180004ddc  jz      loc_180004EC9
0x180004de2  mov     qword ptr [r11+18h], 0
0x180004dea  xor     edx, edx
0x180004dec  lea     rcx, [r11+18h]
0x180004df0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180004df5  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180004dfa  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004e01  lea     rcx, aOobehealth; "OOBEHealth"
0x180004e08  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180004e0d  mov     rcx, [rsp+38h]; this
0x180004e12  test    eax, eax
0x180004e14  jns     short loc_180004E2F
0x180004e16  mov     r9d, eax; char *
0x180004e19  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004e20  mov     edx, 42Fh; void *
0x180004e25  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004e2a  jmp     loc_180004EBC
0x180004e2f  mov     [rsp+38h+hKey], 0
0x180004e38  lea     rax, [rsp+38h+hKey]
0x180004e3d  mov     [rsp+38h+phkResult], rax; phkResult
0x180004e42  mov     r9d, 0F003Fh; samDesired
0x180004e48  xor     r8d, r8d; ulOptions
0x180004e4b  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180004e50  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004e57  call    cs:__imp_RegOpenKeyExW
0x180004e5d  mov     rcx, [rsp+38h]
0x180004e62  test    eax, eax
0x180004e64  jz      short loc_180004E6D
0x180004e66  mov     edx, 432h
0x180004e6b  jmp     short loc_180004EA3
0x180004e6d  mov     [rsp+38h+cbData], 10h; cbData
0x180004e75  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180004e7a  mov     r9d, 3; dwType
0x180004e80  xor     r8d, r8d; Reserved
0x180004e83  lea     rdx, aCensus; "Census"
0x180004e8a  mov     rcx, [rsp+38h+hKey]; hKey
0x180004e8f  call    cs:__imp_RegSetValueExW
0x180004e95  mov     rcx, [rsp+38h]; this
0x180004e9a  test    eax, eax
0x180004e9c  jz      short loc_180004EB2
0x180004e9e  mov     edx, 435h; void *
0x180004ea3  mov     r9d, eax; char *
0x180004ea6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004ead  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180004eb2  lea     rcx, [rsp+38h+hKey]
0x180004eb7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180004ebc  mov     byte ptr [rbx], 0
0x180004ebf  lea     rcx, [rsp+38h+lpSubKey]
0x180004ec4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004ec9  mov     rbx, [rsp+38h+arg_8]
0x180004ece  add     rsp, 30h
0x180004ed2  pop     rdi
0x180004ed3  retn
```

# OOBE::Health::details::OOBEScenarioEvents::WriteInfo<OOBE::Health::details::HealthTrackingInfo>(OOBE::Health::details::HealthInfoHeader &,OOBE::Health::details::HealthTrackingInfo &,bool &,bool &,ushort const *)

- ea: `0x180004b80`
- end: `0x180004ca4`
- name: `??$WriteInfo@UHealthTrackingInfo@details@Health@OOBE@@@OOBEScenarioEvents@details@Health@OOBE@@AEAAXAEAUHealthInfoHeader@123@AEAUHealthTrackingInfo@123@AEA_N2PEBG@Z`
- size: `292`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002316c`
- `0x1800491bc`
- `0x180058f6c`

## callees

- `0x180004b80`
- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180024d70`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c27`

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
0x180004b80  mov     r11, rsp
0x180004b83  mov     [r11+10h], rbx
0x180004b87  mov     [r11+18h], r8
0x180004b8b  mov     [r11+8], rcx
0x180004b8f  push    rdi
0x180004b90  sub     rsp, 30h
0x180004b94  mov     rbx, r9
0x180004b97  mov     rdi, rdx
0x180004b9a  mov     rax, [rsp+38h+arg_20]
0x180004b9f  cmp     byte ptr [rax], 0
0x180004ba2  jz      loc_180004C99
0x180004ba8  cmp     byte ptr [r9], 0
0x180004bac  jz      loc_180004C99
0x180004bb2  mov     qword ptr [r11+18h], 0
0x180004bba  xor     edx, edx
0x180004bbc  lea     rcx, [r11+18h]
0x180004bc0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180004bc5  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180004bca  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180004bd1  lea     rcx, aOobehealth; "OOBEHealth"
0x180004bd8  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180004bdd  mov     rcx, [rsp+38h]; this
0x180004be2  test    eax, eax
0x180004be4  jns     short loc_180004BFF
0x180004be6  mov     r9d, eax; char *
0x180004be9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004bf0  mov     edx, 42Fh; void *
0x180004bf5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004bfa  jmp     loc_180004C8C
0x180004bff  mov     [rsp+38h+hKey], 0
0x180004c08  lea     rax, [rsp+38h+hKey]
0x180004c0d  mov     [rsp+38h+phkResult], rax; phkResult
0x180004c12  mov     r9d, 0F003Fh; samDesired
0x180004c18  xor     r8d, r8d; ulOptions
0x180004c1b  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180004c20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004c27  call    cs:__imp_RegOpenKeyExW
0x180004c2d  mov     rcx, [rsp+38h]
0x180004c32  test    eax, eax
0x180004c34  jz      short loc_180004C3D
0x180004c36  mov     edx, 432h
0x180004c3b  jmp     short loc_180004C73
0x180004c3d  mov     [rsp+38h+cbData], 0ACh; cbData
0x180004c45  mov     [rsp+38h+phkResult], rdi; unsigned int
0x180004c4a  mov     r9d, 3; dwType
0x180004c50  xor     r8d, r8d; Reserved
0x180004c53  lea     rdx, ValueName; "Health"
0x180004c5a  mov     rcx, [rsp+38h+hKey]; hKey
0x180004c5f  call    cs:__imp_RegSetValueExW
0x180004c65  mov     rcx, [rsp+38h]; this
0x180004c6a  test    eax, eax
0x180004c6c  jz      short loc_180004C82
0x180004c6e  mov     edx, 435h; void *
0x180004c73  mov     r9d, eax; char *
0x180004c76  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180004c7d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180004c82  lea     rcx, [rsp+38h+hKey]
0x180004c87  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180004c8c  mov     byte ptr [rbx], 0
0x180004c8f  lea     rcx, [rsp+38h+lpSubKey]
0x180004c94  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180004c99  mov     rbx, [rsp+38h+arg_8]
0x180004c9e  add     rsp, 30h
0x180004ca2  pop     rdi
0x180004ca3  retn
```

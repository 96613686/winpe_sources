# OOBE::Health::details::DeleteRegistryValue

- ea: `0x180023c4c`
- end: `0x180023d1e`
- name: `OOBE::Health::details::DeleteRegistryValue`
- size: `210`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022c50`
- `0x180048cb8`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180023c4c`
- `0x180024d70`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ccd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ccd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023cfe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023cfe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::DeleteRegistryValue(__int64 a1, HKEY a2)
{
  int RedirectionKeyPath; // eax
  unsigned int v3; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a2;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBEHealth",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Health",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
    if ( v3 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)v3,
        phkResulta);
    else
      RegDeleteValueW(hKey, L"UnexpectedReboot");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)(unsigned int)RedirectionKeyPath,
      phkResult);
  }
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180023c4c  mov     rax, rsp
0x180023c4f  mov     [rax+18h], r8
0x180023c53  mov     [rax+10h], rdx
0x180023c57  sub     rsp, 38h
0x180023c5b  mov     qword ptr [rax+18h], 0
0x180023c63  xor     edx, edx
0x180023c65  lea     rcx, [rax+18h]
0x180023c69  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023c6e  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180023c73  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023c7a  lea     rcx, aOobehealth; "OOBEHealth"
0x180023c81  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180023c86  mov     rcx, [rsp+38h]; this
0x180023c8b  test    eax, eax
0x180023c8d  jns     short loc_180023CA5
0x180023c8f  mov     r9d, eax; char *
0x180023c92  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180023c99  mov     edx, 19Bh; void *
0x180023c9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023ca3  jmp     short loc_180023D0F
0x180023ca5  mov     [rsp+38h+hKey], 0
0x180023cae  lea     rax, [rsp+38h+hKey]
0x180023cb3  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180023cb8  mov     r9d, 20006h; samDesired
0x180023cbe  xor     r8d, r8d; ulOptions
0x180023cc1  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180023cc6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023ccd  call    cs:__imp_RegOpenKeyExW
0x180023cd3  mov     rcx, [rsp+38h]; this
0x180023cd8  test    eax, eax
0x180023cda  jz      short loc_180023CF2
0x180023cdc  mov     r9d, eax; char *
0x180023cdf  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180023ce6  mov     edx, 19Eh; void *
0x180023ceb  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023cf0  jmp     short loc_180023D04
0x180023cf2  lea     rdx, aUnexpectedrebo; "UnexpectedReboot"
0x180023cf9  mov     rcx, [rsp+38h+hKey]; hKey
0x180023cfe  call    cs:__imp_RegDeleteValueW
0x180023d04  lea     rcx, [rsp+38h+hKey]
0x180023d09  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023d0e  nop
0x180023d0f  lea     rcx, [rsp+38h+lpSubKey]
0x180023d14  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023d19  add     rsp, 38h
0x180023d1d  retn
```

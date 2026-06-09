# OOBE::Health::details::DeleteRegistryValue

- ea: `0x180023b4c`
- end: `0x180023c2a`
- name: `OOBE::Health::details::DeleteRegistryValue`
- size: `222`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002197c`
- `0x180021a84`
- `0x180021b8c`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180018c98`
- `0x18001f168`
- `0x180023b4c`
- `0x180025b8c`
- `0x1800279b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023bd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023bd9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023c0a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180023c0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::DeleteRegistryValue(__int64 a1, __int64 a2, HKEY a3)
{
  int RedirectionKeyPath; // eax
  unsigned int v4; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  unsigned int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPCWSTR lpSubKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = a3;
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
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20006u, &hKey);
    if ( v4 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
        (const char *)v4,
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
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180023b4c  mov     rax, rsp
0x180023b4f  mov     [rax+18h], r8
0x180023b53  mov     [rax+10h], rdx
0x180023b57  sub     rsp, 38h
0x180023b5b  mov     qword ptr [rax+10h], 0
0x180023b63  xor     edx, edx
0x180023b65  lea     rcx, [rax+10h]
0x180023b69  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180023b6e  lea     r8, [rsp+38h+lpSubKey]; unsigned __int16 **
0x180023b73  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180023b7a  lea     rcx, aOobehealth; "OOBEHealth"
0x180023b81  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180023b86  mov     rcx, [rsp+38h]; this
0x180023b8b  test    eax, eax
0x180023b8d  jns     short loc_180023BA5
0x180023b8f  mov     r9d, eax; char *
0x180023b92  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180023b99  mov     edx, 19Bh; void *
0x180023b9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023ba3  jmp     short loc_180023C1B
0x180023ba5  mov     [rsp+38h+hKey], 0
0x180023bae  xor     edx, edx
0x180023bb0  lea     rcx, [rsp+38h+hKey]
0x180023bb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180023bba  lea     rax, [rsp+38h+hKey]
0x180023bbf  mov     qword ptr [rsp+38h+phkResult], rax; unsigned int
0x180023bc4  mov     r9d, 20006h; samDesired
0x180023bca  xor     r8d, r8d; ulOptions
0x180023bcd  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x180023bd2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023bd9  call    cs:__imp_RegOpenKeyExW
0x180023bdf  mov     rcx, [rsp+38h]; this
0x180023be4  test    eax, eax
0x180023be6  jz      short loc_180023BFE
0x180023be8  mov     r9d, eax; char *
0x180023beb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180023bf2  mov     edx, 19Eh; void *
0x180023bf7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023bfc  jmp     short loc_180023C10
0x180023bfe  lea     rdx, aUnexpectedrebo; "UnexpectedReboot"
0x180023c05  mov     rcx, [rsp+38h+hKey]; hKey
0x180023c0a  call    cs:__imp_RegDeleteValueW
0x180023c10  lea     rcx, [rsp+38h+hKey]
0x180023c15  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023c1a  nop
0x180023c1b  lea     rcx, [rsp+38h+lpSubKey]
0x180023c20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180023c25  add     rsp, 38h
0x180023c29  retn
```

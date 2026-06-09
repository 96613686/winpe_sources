# OOBE::Health::details::SetRegistryValue

- ea: `0x180026ab0`
- end: `0x180026bb0`
- name: `OOBE::Health::details::SetRegistryValue`
- size: `256`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180021b8c`
- `0x180022550`

## callees

- `0x18000a5c8`
- `0x18000e270`
- `0x18000e580`
- `0x180018c98`
- `0x18001f168`
- `0x180025b8c`
- `0x180026ab0`
- `0x1800279b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026b72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026b72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026b3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::SetRegistryValue(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        LPCWSTR lpValueName)
{
  int RedirectionKeyPath; // eax
  unsigned int v7; // eax
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  BYTE Data[8]; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  *(_DWORD *)Data = 1;
  lpSubKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(a1, a2, (unsigned __int16 **)lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x2001Fu, &hKey);
    v8 = retaddr;
    if ( v7 )
    {
      v9 = 400;
    }
    else
    {
      v7 = RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
      v8 = retaddr;
      if ( !v7 )
      {
LABEL_8:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpSubKey);
      }
      v9 = 402;
    }
    wil::details::in1diag3::_Log_Win32(
      v8,
      (void *)v9,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v7,
      phkResulta);
    goto LABEL_8;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x18D,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
    (const char *)(unsigned int)RedirectionKeyPath,
    phkResult);
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(lpSubKey);
}

```

## disassembly

```asm
0x180026ab0  push    rbp
0x180026ab2  push    rbx
0x180026ab3  push    rsi
0x180026ab4  push    rdi
0x180026ab5  mov     rbp, rsp
0x180026ab8  sub     rsp, 58h
0x180026abc  mov     rsi, r8
0x180026abf  mov     rbx, rdx
0x180026ac2  mov     rdi, rcx
0x180026ac5  mov     dword ptr [rbp+Data], 1
0x180026acc  mov     [rbp+lpSubKey], 0
0x180026ad4  xor     edx, edx
0x180026ad6  lea     rcx, [rbp+lpSubKey]
0x180026ada  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026adf  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180026ae3  mov     rdx, rbx; unsigned __int16 *
0x180026ae6  mov     rcx, rdi; unsigned __int16 *
0x180026ae9  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x180026aee  mov     rcx, [rbp+20h]; this
0x180026af2  test    eax, eax
0x180026af4  jns     short loc_180026B0F
0x180026af6  mov     r9d, eax; char *
0x180026af9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180026b00  mov     edx, 18Dh; void *
0x180026b05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026b0a  jmp     loc_180026B9E
0x180026b0f  mov     [rbp+hKey], 0
0x180026b17  xor     edx, edx
0x180026b19  lea     rcx, [rbp+hKey]
0x180026b1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026b22  lea     rax, [rbp+hKey]
0x180026b26  mov     [rsp+58h+phkResult], rax; phkResult
0x180026b2b  mov     r9d, 2001Fh; samDesired
0x180026b31  xor     r8d, r8d; ulOptions
0x180026b34  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180026b38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026b3f  call    cs:__imp_RegOpenKeyExW
0x180026b45  mov     rcx, [rbp+20h]
0x180026b49  test    eax, eax
0x180026b4b  jz      short loc_180026B54
0x180026b4d  mov     edx, 190h
0x180026b52  jmp     short loc_180026B85
0x180026b54  mov     r9d, 4; dwType
0x180026b5a  mov     [rsp+58h+cbData], r9d; cbData
0x180026b5f  lea     rax, [rbp+Data]
0x180026b63  mov     [rsp+58h+phkResult], rax; unsigned int
0x180026b68  xor     r8d, r8d; Reserved
0x180026b6b  mov     rdx, rsi; lpValueName
0x180026b6e  mov     rcx, [rbp+hKey]; hKey
0x180026b72  call    cs:__imp_RegSetValueExW
0x180026b78  mov     rcx, [rbp+20h]; this
0x180026b7c  test    eax, eax
0x180026b7e  jz      short loc_180026B94
0x180026b80  mov     edx, 192h; void *
0x180026b85  mov     r9d, eax; char *
0x180026b88  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180026b8f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026b94  lea     rcx, [rbp+hKey]
0x180026b98  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026b9d  nop
0x180026b9e  lea     rcx, [rbp+lpSubKey]
0x180026ba2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026ba7  add     rsp, 58h
0x180026bab  pop     rdi
0x180026bac  pop     rsi
0x180026bad  pop     rbx
0x180026bae  pop     rbp
0x180026baf  retn
```

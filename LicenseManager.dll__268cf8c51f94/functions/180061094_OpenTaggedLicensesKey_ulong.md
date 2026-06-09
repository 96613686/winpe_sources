# OpenTaggedLicensesKey(ulong)

- ea: `0x180061094`
- end: `0x180061184`
- name: `?OpenTaggedLicensesKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `240`
- prototype: `__int64 __fastcall(PHKEY phkResult, REGSAM samDesired)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060240`
- `0x180060354`
- `0x180060d94`
- `0x180074730`

## callees

- `0x180004644`
- `0x180061094`
- `0x180061eec`
- `0x180090f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800610de`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800610de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061144`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061144`

## string_xrefs

- `0x1800610f0`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`
- `0x180061156`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHKEY __fastcall OpenTaggedLicensesKey(PHKEY phkResult, REGSAM samDesired)
{
  unsigned int v4; // eax
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY phkResulta; // [rsp+80h] [rbp+18h] BYREF

  phkResulta = 0;
  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResulta,
    0);
  v4 = RegOpenCurrentUser(4u, &phkResulta);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
      (const char *)v4,
      dwOptions);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  Key = RegCreateKeyExW(
          phkResulta,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Licenses\\Tagged",
          0,
          0,
          0,
          samDesired,
          0,
          phkResult,
          0);
  if ( Key )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
      (const char *)Key,
      dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResulta);
  return phkResult;
}

```

## disassembly

```asm
0x180061094  mov     rax, rsp
0x180061097  mov     [rax+10h], rbx
0x18006109b  mov     [rax+8], rcx
0x18006109f  push    rdi
0x1800610a0  sub     rsp, 60h
0x1800610a4  mov     edi, edx
0x1800610a6  mov     rbx, rcx
0x1800610a9  mov     dword ptr [rax-18h], 0
0x1800610b0  mov     qword ptr [rax+18h], 0
0x1800610b8  mov     qword ptr [rcx], 0
0x1800610bf  mov     dword ptr [rax-18h], 1
0x1800610c6  xor     edx, edx
0x1800610c8  lea     rcx, [rax+18h]
0x1800610cc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800610d1  lea     rdx, [rsp+68h+phkResult]; phkResult
0x1800610d9  mov     ecx, 4; samDesired
0x1800610de  call    cs:__imp_RegOpenCurrentUser
0x1800610e4  mov     rcx, [rsp+68h]; this
0x1800610e9  test    eax, eax
0x1800610eb  jz      short loc_180061102
0x1800610ed  mov     r9d, eax; char *
0x1800610f0  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800610f7  mov     edx, 0Eh; void *
0x1800610fc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180061102  xor     edx, edx
0x180061104  mov     rcx, rbx
0x180061107  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006110c  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180061115  mov     [rsp+68h+var_30], rbx; phkResult
0x18006111a  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180061123  mov     [rsp+68h+samDesired], edi; samDesired
0x180061127  mov     [rsp+68h+dwOptions], 0; unsigned int
0x18006112f  xor     r9d, r9d; lpClass
0x180061132  xor     r8d, r8d; Reserved
0x180061135  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18006113c  mov     rcx, [rsp+68h+phkResult]; hKey
0x180061144  call    cs:__imp_RegCreateKeyExW
0x18006114a  mov     rcx, [rsp+68h]; this
0x18006114f  test    eax, eax
0x180061151  jz      short loc_180061168
0x180061153  mov     r9d, eax; char *
0x180061156  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006115d  mov     edx, 1Ah; void *
0x180061162  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180061168  lea     rcx, [rsp+68h+phkResult]
0x180061170  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061175  mov     rax, rbx
0x180061178  mov     rbx, [rsp+68h+arg_8]
0x18006117d  add     rsp, 60h
0x180061181  pop     rdi
0x180061182  retn
```

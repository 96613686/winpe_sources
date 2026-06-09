# BioPolicy::EnableVbs(void)

- ea: `0x180076f54`
- end: `0x180077058`
- name: `?EnableVbs@BioPolicy@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(BioPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077060`

## callees

- `0x18000d62c`
- `0x18006fa64`
- `0x18006ffd4`
- `0x180076f54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076fc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076fc5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180077010`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180077010`

## string_xrefs

- `0x180077033`: `onecore\ds\security\biometrics\credprov\common\policy.cpp`

## pseudocode

```c
__int64 __fastcall BioPolicy::EnableVbs(BioPolicy *this)
{
  LSTATUS v1; // eax
  signed int v2; // ebx
  __int64 v3; // rdx
  LSTATUS v4; // eax
  int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  BioPolicy *dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  dwDisposition = this;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  hKey = 0;
  LODWORD(dwDisposition) = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\DeviceGuard\\Scenarios\\WindowsHelloSecureBiometrics",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         (LPDWORD)&dwDisposition);
  v2 = v1;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
    LODWORD(dwDisposition) = 1;
    v4 = RegSetKeyValueW(hKey, 0, L"Enabled", 4u, &dwDisposition, 4u);
    v2 = v4;
    if ( v4 > 0 )
      v2 = (unsigned __int16)v4 | 0x80070000;
    if ( v2 >= 0 )
    {
      v2 = 0;
      goto LABEL_11;
    }
    v3 = 945;
  }
  else
  {
    v3 = 944;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\ds\\security\\biometrics\\credprov\\common\\policy.cpp",
    (const char *)(unsigned int)v2,
    dwOptions);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180076f54  mov     [rsp+dwDisposition], rcx
0x180076f59  push    rbx
0x180076f5a  sub     rsp, 50h
0x180076f5e  xor     edx, edx
0x180076f60  mov     [rsp+58h+hKey], 0
0x180076f69  lea     rcx, [rsp+58h+hKey]
0x180076f6e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180076f73  lea     rax, [rsp+58h+dwDisposition]
0x180076f78  mov     [rsp+58h+hKey], 0
0x180076f81  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180076f86  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Dev"...
0x180076f8d  lea     rax, [rsp+58h+hKey]
0x180076f92  mov     dword ptr [rsp+58h+dwDisposition], 0
0x180076f9a  mov     [rsp+58h+phkResult], rax; phkResult
0x180076f9f  xor     r9d, r9d; lpClass
0x180076fa2  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180076fab  xor     r8d, r8d; Reserved
0x180076fae  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180076fb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076fbd  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180076fc5  call    cs:__imp_RegCreateKeyExW
0x180076fcb  mov     ebx, eax
0x180076fcd  test    eax, eax
0x180076fcf  jle     short loc_180076FDA
0x180076fd1  movzx   ebx, ax
0x180076fd4  or      ebx, 80070000h
0x180076fda  test    ebx, ebx
0x180076fdc  jns     short loc_180076FE5
0x180076fde  mov     edx, 3B0h
0x180076fe3  jmp     short loc_18007702E
0x180076fe5  mov     rcx, [rsp+58h+hKey]; hKey
0x180076fea  lea     rax, [rsp+58h+dwDisposition]
0x180076fef  mov     r9d, 4; dwType
0x180076ff5  mov     dword ptr [rsp+58h+dwDisposition], 1
0x180076ffd  mov     [rsp+58h+samDesired], r9d; cbData
0x180077002  lea     r8, aEnabled; "Enabled"
0x180077009  xor     edx, edx; lpSubKey
0x18007700b  mov     qword ptr [rsp+58h+dwOptions], rax; int
0x180077010  call    cs:__imp_RegSetKeyValueW
0x180077016  mov     ebx, eax
0x180077018  test    eax, eax
0x18007701a  jle     short loc_180077025
0x18007701c  movzx   ebx, ax
0x18007701f  or      ebx, 80070000h
0x180077025  test    ebx, ebx
0x180077027  jns     short loc_180077044
0x180077029  mov     edx, 3B1h; void *
0x18007702e  mov     rcx, [rsp+58h]; this
0x180077033  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\biometrics\\cred"...
0x18007703a  mov     r9d, ebx; char *
0x18007703d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077042  jmp     short loc_180077046
0x180077044  xor     ebx, ebx
0x180077046  lea     rcx, [rsp+58h+hKey]
0x18007704b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180077050  mov     eax, ebx
0x180077052  add     rsp, 50h
0x180077056  pop     rbx
0x180077057  retn
```

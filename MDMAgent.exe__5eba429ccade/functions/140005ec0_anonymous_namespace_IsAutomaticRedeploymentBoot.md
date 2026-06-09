# _anonymous_namespace_::IsAutomaticRedeploymentBoot

- ea: `0x140005ec0`
- end: `0x140005f79`
- name: `_anonymous_namespace_::IsAutomaticRedeploymentBoot`
- size: `185`
- prototype: `bool()`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004ef4`
- `0x140007f34`

## callees

- `0x140004b0c`
- `0x140005ec0`
- `0x140007b34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140005f49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140005f49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005efa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005efa`

## string_xrefs

- `0x140005f1f`: `InstallType`

## pseudocode

```c
bool anonymous_namespace_::IsAutomaticRedeploymentBoot()
{
  bool v0; // bl
  LSTATUS v1; // eax
  bool v2; // sf
  LSTATUS ValueW; // eax
  bool v4; // sf
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v0 = 0;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
         0,
         0x20019u,
         &hkey);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( !v2 )
  {
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"InstallType", 0x10u, 0, &pvData, &pcbData);
    v4 = ValueW < 0;
    if ( ValueW > 0 )
      v4 = 1;
    if ( !v4 )
      v0 = pvData == 17;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v0;
}

```

## disassembly

```asm
0x140005ec0  push    rbx
0x140005ec2  sub     rsp, 40h
0x140005ec6  xor     ebx, ebx
0x140005ec8  lea     rcx, [rsp+48h+hkey]
0x140005ecd  xor     edx, edx
0x140005ecf  mov     [rsp+48h+hkey], rbx
0x140005ed4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140005ed9  lea     rax, [rsp+48h+hkey]
0x140005ede  mov     r9d, 20019h; samDesired
0x140005ee4  xor     r8d, r8d; ulOptions
0x140005ee7  mov     [rsp+48h+phkResult], rax; phkResult
0x140005eec  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140005ef3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140005efa  call    cs:__imp_RegOpenKeyExW
0x140005f00  test    eax, eax
0x140005f02  jle     short loc_140005F0E
0x140005f04  movzx   eax, ax
0x140005f07  or      eax, 80070000h
0x140005f0c  test    eax, eax
0x140005f0e  js      short loc_140005F67
0x140005f10  mov     rcx, [rsp+48h+hkey]; hkey
0x140005f15  lea     rax, [rsp+48h+arg_8]
0x140005f1a  mov     [rsp+48h+pcbData], rax; pcbData
0x140005f1f  lea     r8, Value; "InstallType"
0x140005f26  lea     rax, [rsp+48h+arg_0]
0x140005f2b  mov     [rsp+48h+arg_0], ebx
0x140005f2f  mov     [rsp+48h+pvData], rax; pvData
0x140005f34  mov     r9d, 10h; dwFlags
0x140005f3a  xor     edx, edx; lpSubKey
0x140005f3c  mov     [rsp+48h+phkResult], rbx; pdwType
0x140005f41  mov     [rsp+48h+arg_8], 4
0x140005f49  call    cs:__imp_RegGetValueW
0x140005f4f  test    eax, eax
0x140005f51  jle     short loc_140005F5D
0x140005f53  movzx   eax, ax
0x140005f56  or      eax, 80070000h
0x140005f5b  test    eax, eax
0x140005f5d  js      short loc_140005F67
0x140005f5f  cmp     [rsp+48h+arg_0], 11h
0x140005f64  setz    bl
0x140005f67  lea     rcx, [rsp+48h+hkey]
0x140005f6c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140005f71  mov     al, bl
0x140005f73  add     rsp, 40h
0x140005f77  pop     rbx
0x140005f78  retn
```

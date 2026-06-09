# _anonymous_namespace_::IsAutomaticRedeploymentBoot

- ea: `0x1400060c8`
- end: `0x14000618e`
- name: `_anonymous_namespace_::IsAutomaticRedeploymentBoot`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004fa8`
- `0x14000829c`

## callees

- `0x140004b94`
- `0x1400060c8`
- `0x140007e3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006157`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140006157`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006102`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006102`

## string_xrefs

- `0x14000612d`: `InstallType`

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
0x1400060c8  push    rbx
0x1400060ca  sub     rsp, 40h
0x1400060ce  xor     ebx, ebx
0x1400060d0  lea     rcx, [rsp+48h+hkey]
0x1400060d5  xor     edx, edx
0x1400060d7  mov     [rsp+48h+hkey], rbx
0x1400060dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1400060e1  lea     rax, [rsp+48h+hkey]
0x1400060e6  mov     r9d, 20019h; samDesired
0x1400060ec  xor     r8d, r8d; ulOptions
0x1400060ef  mov     [rsp+48h+phkResult], rax; phkResult
0x1400060f4  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400060fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006102  call    cs:__imp_RegOpenKeyExW
0x140006109  nop     dword ptr [rax+rax+00h]
0x14000610e  test    eax, eax
0x140006110  jle     short loc_14000611C
0x140006112  movzx   eax, ax
0x140006115  or      eax, 80070000h
0x14000611a  test    eax, eax
0x14000611c  js      short loc_14000617B
0x14000611e  mov     rcx, [rsp+48h+hkey]; hkey
0x140006123  lea     rax, [rsp+48h+arg_8]
0x140006128  mov     [rsp+48h+pcbData], rax; pcbData
0x14000612d  lea     r8, Value; "InstallType"
0x140006134  lea     rax, [rsp+48h+arg_0]
0x140006139  mov     [rsp+48h+arg_0], ebx
0x14000613d  mov     [rsp+48h+pvData], rax; pvData
0x140006142  mov     r9d, 10h; dwFlags
0x140006148  xor     edx, edx; lpSubKey
0x14000614a  mov     [rsp+48h+phkResult], rbx; pdwType
0x14000614f  mov     [rsp+48h+arg_8], 4
0x140006157  call    cs:__imp_RegGetValueW
0x14000615e  nop     dword ptr [rax+rax+00h]
0x140006163  test    eax, eax
0x140006165  jle     short loc_140006171
0x140006167  movzx   eax, ax
0x14000616a  or      eax, 80070000h
0x14000616f  test    eax, eax
0x140006171  js      short loc_14000617B
0x140006173  cmp     [rsp+48h+arg_0], 11h
0x140006178  setz    bl
0x14000617b  lea     rcx, [rsp+48h+hkey]
0x140006180  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140006185  mov     al, bl
0x140006187  add     rsp, 40h
0x14000618b  pop     rbx
0x14000618c  retn
```

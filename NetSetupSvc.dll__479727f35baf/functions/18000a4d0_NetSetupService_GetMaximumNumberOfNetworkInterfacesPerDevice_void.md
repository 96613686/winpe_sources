# NetSetupService::GetMaximumNumberOfNetworkInterfacesPerDevice(void)

- ea: `0x18000a4d0`
- end: `0x18000a569`
- name: `?GetMaximumNumberOfNetworkInterfacesPerDevice@NetSetupService@@AEAAKXZ`
- size: `153`
- prototype: `__int64 __fastcall(NetSetupService *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x180008e3c`
- `0x18000a4d0`
- `0x1800275e4`
- `0x1800285cc`
- `0x1800286d8`

## pseudocode

```c
__int64 __fastcall NetSetupService::GetMaximumNumberOfNetworkInterfacesPerDevice(NetSetupService *this)
{
  unsigned int ValueDword; // ebx
  HKEY v3; // [rsp+30h] [rbp-18h] BYREF

  RegistryKey::TryOpenSubKey((char *)this + 280, &v3, L"Control\\NetworkSetup2\\Parameters", 1, 0);
  if ( v3 && RegistryKey::ValueExists((RegistryKey *)&v3, L"MaximumNumberOfNetworkInterfacesPerDevice") )
    ValueDword = RegistryKey::GetValueDword(&v3, L"MaximumNumberOfNetworkInterfacesPerDevice", 0, 0);
  else
    ValueDword = 256;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v3);
  return ValueDword;
}

```

## disassembly

```asm
0x18000a4d0  push    rbx
0x18000a4d2  sub     rsp, 40h
0x18000a4d6  mov     rax, cs:__security_cookie
0x18000a4dd  xor     rax, rsp
0x18000a4e0  mov     [rsp+48h+var_10], rax
0x18000a4e5  add     rcx, 118h
0x18000a4ec  mov     [rsp+48h+var_28], 0
0x18000a4f5  mov     r9d, 1
0x18000a4fb  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\Parameters"
0x18000a502  lea     rdx, [rsp+48h+var_18]
0x18000a507  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000a50c  nop
0x18000a50d  cmp     [rsp+48h+var_18], 0
0x18000a513  jz      short loc_18000A545
0x18000a515  lea     rdx, aMaximumnumbero; "MaximumNumberOfNetworkInterfacesPerDevi"...
0x18000a51c  lea     rcx, [rsp+48h+var_18]; this
0x18000a521  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18000a526  test    al, al
0x18000a528  jz      short loc_18000A545
0x18000a52a  xor     r9d, r9d
0x18000a52d  xor     r8d, r8d
0x18000a530  lea     rdx, aMaximumnumbero; "MaximumNumberOfNetworkInterfacesPerDevi"...
0x18000a537  lea     rcx, [rsp+48h+var_18]
0x18000a53c  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000a541  mov     ebx, eax
0x18000a543  jmp     short loc_18000A54A
0x18000a545  mov     ebx, 100h
0x18000a54a  lea     rcx, [rsp+48h+var_18]
0x18000a54f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a554  mov     eax, ebx
0x18000a556  mov     rcx, [rsp+48h+var_10]
0x18000a55b  xor     rcx, rsp; StackCookie
0x18000a55e  call    __security_check_cookie
0x18000a563  add     rsp, 40h
0x18000a567  pop     rbx
0x18000a568  retn
```

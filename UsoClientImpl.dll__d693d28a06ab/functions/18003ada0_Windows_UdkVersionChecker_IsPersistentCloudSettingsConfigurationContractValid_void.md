# Windows::UdkVersionChecker::IsPersistentCloudSettingsConfigurationContractValid(void)

- ea: `0x18003ada0`
- end: `0x18003ae21`
- name: `?IsPersistentCloudSettingsConfigurationContractValid@UdkVersionChecker@Windows@@YA_NXZ`
- size: `129`
- prototype: `bool __fastcall(Windows::UdkVersionChecker *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800412c0`
- `0x180041440`
- `0x180041480`

## callees

- `0x18003a7dc`
- `0x18003ac98`
- `0x18003ada0`
- `0x1800563c8`

## string_xrefs

- `0x18003adb5`: `WindowsUdk.Management.Update.ManagementUpdateContract`

## pseudocode

```c
char __fastcall Windows::UdkVersionChecker::IsPersistentCloudSettingsConfigurationContractValid(
        Windows::UdkVersionChecker *this)
{
  __int64 v1; // rcx
  char v2; // bl
  _DWORD *v4; // [rsp+20h] [rbp-28h] BYREF
  _DWORD v5[4]; // [rsp+28h] [rbp-20h] BYREF
  const wchar_t *v6; // [rsp+38h] [rbp-10h]

  if ( !(unsigned __int8)Windows::UdkVersionChecker::_anonymous_namespace_::IsUdkSupported(this) )
    return 0;
  v1 = -1;
  do
    ++v1;
  while ( winrt::WindowsUdk::Management::Update::ManagementUpdateContractName[v1] );
  v2 = 1;
  if ( (_DWORD)v1 )
  {
    if ( winrt::WindowsUdk::Management::Update::ManagementUpdateContractName[(unsigned int)v1] )
      abort();
    v5[0] = 1;
    v4 = v5;
    v5[1] = v1;
    v6 = L"WindowsUdk.Management.Update.ManagementUpdateContract";
  }
  else
  {
    v4 = 0;
  }
  if ( !(unsigned __int8)winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(
                           (const struct winrt::param::hstring *)&v4,
                           3u) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18003ada0  mov     [rsp+arg_0], rbx
0x18003ada5  push    rdi
0x18003ada6  sub     rsp, 40h
0x18003adaa  call    Windows__UdkVersionChecker___anonymous_namespace___IsUdkSupported
0x18003adaf  xor     edi, edi
0x18003adb1  test    al, al
0x18003adb3  jz      short loc_18003AE0B
0x18003adb5  lea     rdx, ?ManagementUpdateContractName@Update@Management@WindowsUdk@winrt@@3QB_WB; "WindowsUdk.Management.Update.Management"...
0x18003adbc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003adc0  inc     rcx
0x18003adc3  cmp     [rdx+rcx*2], di
0x18003adc7  jnz     short loc_18003ADC0
0x18003adc9  mov     ebx, 1
0x18003adce  test    ecx, ecx
0x18003add0  jnz     short loc_18003ADD9
0x18003add2  mov     [rsp+48h+var_28], rdi
0x18003add7  jmp     short loc_18003ADF8
0x18003add9  mov     eax, ecx
0x18003addb  cmp     [rdx+rax*2], di
0x18003addf  jnz     short loc_18003AE1B
0x18003ade1  lea     rax, [rsp+48h+var_20]
0x18003ade6  mov     [rsp+48h+var_20], ebx
0x18003adea  mov     [rsp+48h+var_28], rax
0x18003adef  mov     [rsp+48h+var_1C], ecx
0x18003adf3  mov     [rsp+48h+var_10], rdx
0x18003adf8  mov     edx, 3; unsigned __int16
0x18003adfd  lea     rcx, [rsp+48h+var_28]; struct winrt::param::hstring *
0x18003ae02  call    ?IsApiContractPresent@ApiInformation@Metadata@Foundation@WindowsUdk@winrt@@SA@AEBUhstring@param@5@G@Z; winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(winrt::param::hstring const &,ushort)
0x18003ae07  test    al, al
0x18003ae09  jnz     short loc_18003AE0E
0x18003ae0b  mov     bl, dil
0x18003ae0e  mov     al, bl
0x18003ae10  mov     rbx, [rsp+48h+arg_0]
0x18003ae15  add     rsp, 40h
0x18003ae19  pop     rdi
0x18003ae1a  retn
0x18003ae1b  call    abort
```

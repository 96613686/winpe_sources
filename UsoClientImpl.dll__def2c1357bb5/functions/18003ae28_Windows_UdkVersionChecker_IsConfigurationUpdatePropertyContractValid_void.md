# Windows::UdkVersionChecker::IsConfigurationUpdatePropertyContractValid(void)

- ea: `0x18003ae28`
- end: `0x18003aea9`
- name: `?IsConfigurationUpdatePropertyContractValid@UdkVersionChecker@Windows@@YA_NXZ`
- size: `129`
- prototype: `bool __fastcall(Windows::UdkVersionChecker *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180041540`
- `0x180041d00`

## callees

- `0x18003a7dc`
- `0x18003ac98`
- `0x18003ae28`
- `0x1800563c8`

## string_xrefs

- `0x18003ae3d`: `WindowsUdk.Management.Update.ManagementUpdateContract`

## pseudocode

```c
char __fastcall Windows::UdkVersionChecker::IsConfigurationUpdatePropertyContractValid(
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
                           4u) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18003ae28  mov     [rsp+arg_0], rbx
0x18003ae2d  push    rdi
0x18003ae2e  sub     rsp, 40h
0x18003ae32  call    Windows__UdkVersionChecker___anonymous_namespace___IsUdkSupported
0x18003ae37  xor     edi, edi
0x18003ae39  test    al, al
0x18003ae3b  jz      short loc_18003AE93
0x18003ae3d  lea     rdx, ?ManagementUpdateContractName@Update@Management@WindowsUdk@winrt@@3QB_WB; "WindowsUdk.Management.Update.Management"...
0x18003ae44  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ae48  inc     rcx
0x18003ae4b  cmp     [rdx+rcx*2], di
0x18003ae4f  jnz     short loc_18003AE48
0x18003ae51  mov     ebx, 1
0x18003ae56  test    ecx, ecx
0x18003ae58  jnz     short loc_18003AE61
0x18003ae5a  mov     [rsp+48h+var_28], rdi
0x18003ae5f  jmp     short loc_18003AE80
0x18003ae61  mov     eax, ecx
0x18003ae63  cmp     [rdx+rax*2], di
0x18003ae67  jnz     short loc_18003AEA3
0x18003ae69  lea     rax, [rsp+48h+var_20]
0x18003ae6e  mov     [rsp+48h+var_20], ebx
0x18003ae72  mov     [rsp+48h+var_28], rax
0x18003ae77  mov     [rsp+48h+var_1C], ecx
0x18003ae7b  mov     [rsp+48h+var_10], rdx
0x18003ae80  mov     edx, 4; unsigned __int16
0x18003ae85  lea     rcx, [rsp+48h+var_28]; struct winrt::param::hstring *
0x18003ae8a  call    ?IsApiContractPresent@ApiInformation@Metadata@Foundation@WindowsUdk@winrt@@SA@AEBUhstring@param@5@G@Z; winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(winrt::param::hstring const &,ushort)
0x18003ae8f  test    al, al
0x18003ae91  jnz     short loc_18003AE96
0x18003ae93  mov     bl, dil
0x18003ae96  mov     al, bl
0x18003ae98  mov     rbx, [rsp+48h+arg_0]
0x18003ae9d  add     rsp, 40h
0x18003aea1  pop     rdi
0x18003aea2  retn
0x18003aea3  call    abort
```

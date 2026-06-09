# SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::get_Description(HSTRING__ * *)

- ea: `0x1800211b0`
- end: `0x180021245`
- name: `?get_Description@CProvisioningPackageAddUsingPathSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `149`
- prototype: `int(SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x18001cbe4`
- `0x1800211b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002122b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021208`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002122b`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting::get_Description(
        SystemSettings::Prov::CProvisioningPackageAddUsingPathSetting *this,
        HSTRING *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  string = 0;
  v3 = Microsoft::WRL::Wrappers::HString::Set(
         (Microsoft::WRL::Wrappers::HString *)&string,
         L"SystemSettingsProvisioningAddPackagePage",
         0x28u);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *a2 = string;
    string = 0;
    WindowsDeleteString(0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x432,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)v3,
      v6);
    WindowsDeleteString(string);
    return v4;
  }
}

```

## disassembly

```asm
0x1800211b0  mov     [rsp+arg_0], rbx
0x1800211b5  push    rdi; int
0x1800211b6  sub     rsp, 20h
0x1800211ba  mov     rdi, rdx
0x1800211bd  mov     qword ptr [rdx], 0
0x1800211c4  lea     rdx, aSystemsettings_33; "SystemSettingsProvisioningAddPackagePag"...
0x1800211cb  mov     [rsp+28h+string], 0
0x1800211d4  mov     r8d, 28h ; '('; unsigned int
0x1800211da  lea     rcx, [rsp+28h+string]; this
0x1800211df  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800211e4  mov     ebx, eax
0x1800211e6  test    eax, eax
0x1800211e8  jns     short loc_180021218
0x1800211ea  mov     rcx, [rsp+28h]; this
0x1800211ef  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800211f6  mov     r9d, eax; char *
0x1800211f9  mov     edx, 432h; void *
0x1800211fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021203  mov     rcx, [rsp+28h+string]; string
0x180021208  call    cs:__imp_WindowsDeleteString
0x18002120f  nop     dword ptr [rax+rax+00h]
0x180021214  mov     eax, ebx
0x180021216  jmp     short loc_180021239
0x180021218  mov     rax, [rsp+28h+string]
0x18002121d  xor     ecx, ecx; string
0x18002121f  mov     [rdi], rax
0x180021222  mov     [rsp+28h+string], 0
0x18002122b  call    cs:__imp_WindowsDeleteString
0x180021232  nop     dword ptr [rax+rax+00h]
0x180021237  xor     eax, eax
0x180021239  mov     rbx, [rsp+28h+arg_0]
0x18002123e  add     rsp, 20h
0x180021242  pop     rdi
0x180021243  retn
```

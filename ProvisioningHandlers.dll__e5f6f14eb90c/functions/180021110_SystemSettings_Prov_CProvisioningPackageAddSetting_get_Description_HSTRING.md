# SystemSettings::Prov::CProvisioningPackageAddSetting::get_Description(HSTRING__ * *)

- ea: `0x180021110`
- end: `0x1800211a5`
- name: `?get_Description@CProvisioningPackageAddSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `149`
- prototype: `int(SystemSettings::Prov::CProvisioningPackageAddSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x18001cbe4`
- `0x180021110`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002118b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002118b`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageAddSetting::get_Description(
        SystemSettings::Prov::CProvisioningPackageAddSetting *this,
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
      (void *)0x40B,
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
0x180021110  mov     [rsp+arg_0], rbx
0x180021115  push    rdi; int
0x180021116  sub     rsp, 20h
0x18002111a  mov     rdi, rdx
0x18002111d  mov     qword ptr [rdx], 0
0x180021124  lea     rdx, aSystemsettings_33; "SystemSettingsProvisioningAddPackagePag"...
0x18002112b  mov     [rsp+28h+string], 0
0x180021134  mov     r8d, 28h ; '('; unsigned int
0x18002113a  lea     rcx, [rsp+28h+string]; this
0x18002113f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180021144  mov     ebx, eax
0x180021146  test    eax, eax
0x180021148  jns     short loc_180021178
0x18002114a  mov     rcx, [rsp+28h]; this
0x18002114f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180021156  mov     r9d, eax; char *
0x180021159  mov     edx, 40Bh; void *
0x18002115e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021163  mov     rcx, [rsp+28h+string]; string
0x180021168  call    cs:__imp_WindowsDeleteString
0x18002116f  nop     dword ptr [rax+rax+00h]
0x180021174  mov     eax, ebx
0x180021176  jmp     short loc_180021199
0x180021178  mov     rax, [rsp+28h+string]
0x18002117d  xor     ecx, ecx; string
0x18002117f  mov     [rdi], rax
0x180021182  mov     [rsp+28h+string], 0
0x18002118b  call    cs:__imp_WindowsDeleteString
0x180021192  nop     dword ptr [rax+rax+00h]
0x180021197  xor     eax, eax
0x180021199  mov     rbx, [rsp+28h+arg_0]
0x18002119e  add     rsp, 20h
0x1800211a2  pop     rdi
0x1800211a3  retn
```

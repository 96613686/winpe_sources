# SystemSettings::Prov::CProvisioningDeleteSetting::get_IsEnabled(uchar *)

- ea: `0x180021980`
- end: `0x1800219ef`
- name: `?get_IsEnabled@CProvisioningDeleteSetting@Prov@SystemSettings@@UEAAJPEAE@Z`
- size: `111`
- prototype: `int(SystemSettings::Prov::CProvisioningDeleteSetting *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x180021980`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800219a8`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800219a8`

## string_xrefs

- `0x1800219a1`: `Security`
- `0x180021995`: `AllowRemoveProvisioningPackage`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::CProvisioningDeleteSetting::get_IsEnabled(
        SystemSettings::Prov::CProvisioningDeleteSetting *this,
        bool *a2)
{
  int PolicyInt; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Security", L"AllowRemoveProvisioningPackage", &v8);
  v4 = PolicyInt;
  if ( PolicyInt >= 0 )
  {
    *a2 = v8 != 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)PolicyInt,
      v6);
    return v4;
  }
}

```

## disassembly

```asm
0x180021980  mov     [rsp+arg_0], rbx
0x180021985  push    rdi; int
0x180021986  sub     rsp, 20h
0x18002198a  mov     rdi, rdx
0x18002198d  mov     [rsp+28h+arg_10], 0
0x180021995  lea     rdx, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18002199c  lea     r8, [rsp+28h+arg_10]
0x1800219a1  lea     rcx, aSecurity; "Security"
0x1800219a8  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800219af  nop     dword ptr [rax+rax+00h]
0x1800219b4  mov     ebx, eax
0x1800219b6  test    eax, eax
0x1800219b8  jns     short loc_1800219D7
0x1800219ba  mov     rcx, [rsp+28h]; this
0x1800219bf  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800219c6  mov     r9d, eax; char *
0x1800219c9  mov     edx, 290h; void *
0x1800219ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800219d3  mov     eax, ebx
0x1800219d5  jmp     short loc_1800219E3
0x1800219d7  cmp     [rsp+28h+arg_10], 0
0x1800219dc  setnz   al
0x1800219df  mov     [rdi], al
0x1800219e1  xor     eax, eax
0x1800219e3  mov     rbx, [rsp+28h+arg_0]
0x1800219e8  add     rsp, 20h
0x1800219ec  pop     rdi
0x1800219ed  retn
```

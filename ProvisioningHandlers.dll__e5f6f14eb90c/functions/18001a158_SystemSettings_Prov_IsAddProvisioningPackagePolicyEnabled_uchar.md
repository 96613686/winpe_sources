# SystemSettings::Prov::IsAddProvisioningPackagePolicyEnabled(uchar *)

- ea: `0x18001a158`
- end: `0x18001a1c7`
- name: `?IsAddProvisioningPackagePolicyEnabled@Prov@SystemSettings@@YAJPEAE@Z`
- size: `111`
- prototype: `int(SystemSettings::Prov *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021a00`

## callees

- `0x1800087ec`
- `0x18001a158`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001a180`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001a180`

## string_xrefs

- `0x18001a16d`: `Security`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::IsAddProvisioningPackagePolicyEnabled(
        SystemSettings::Prov *this,
        unsigned __int8 *a2)
{
  int PolicyInt; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Security", L"AllowAddProvisioningPackage", &v8);
  v4 = PolicyInt;
  if ( PolicyInt >= 0 )
  {
    *(_BYTE *)this = v8 != 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x415,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)PolicyInt,
      v6);
    return v4;
  }
}

```

## disassembly

```asm
0x18001a158  mov     [rsp+arg_0], rbx
0x18001a15d  push    rdi; int
0x18001a15e  sub     rsp, 20h
0x18001a162  mov     rdi, rcx
0x18001a165  mov     [rsp+28h+arg_8], 0
0x18001a16d  lea     rcx, aSecurity; "Security"
0x18001a174  lea     r8, [rsp+28h+arg_8]
0x18001a179  lea     rdx, aAllowaddprovis; "AllowAddProvisioningPackage"
0x18001a180  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001a187  nop     dword ptr [rax+rax+00h]
0x18001a18c  mov     ebx, eax
0x18001a18e  test    eax, eax
0x18001a190  jns     short loc_18001A1AF
0x18001a192  mov     rcx, [rsp+28h]; this
0x18001a197  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x18001a19e  mov     r9d, eax; char *
0x18001a1a1  mov     edx, 415h; void *
0x18001a1a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a1ab  mov     eax, ebx
0x18001a1ad  jmp     short loc_18001A1BB
0x18001a1af  cmp     [rsp+28h+arg_8], 0
0x18001a1b4  setnz   al
0x18001a1b7  mov     [rdi], al
0x18001a1b9  xor     eax, eax
0x18001a1bb  mov     rbx, [rsp+28h+arg_0]
0x18001a1c0  add     rsp, 20h
0x18001a1c4  pop     rdi
0x18001a1c5  retn
```

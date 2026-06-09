# CloudExperienceHostBroker::Cortana::OOBECortanaManager::get_IsCortanaAllowedByPolicy(uchar *)

- ea: `0x180006630`
- end: `0x1800066d7`
- name: `?get_IsCortanaAllowedByPolicy@OOBECortanaManager@Cortana@CloudExperienceHostBroker@@UEAAJPEAE@Z`
- size: `167`
- prototype: `int(CloudExperienceHostBroker::Cortana::OOBECortanaManager *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006630`
- `0x180008344`

## import_xrefs

- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18000665b`
- `ext-ms-win-security-slc-l1-1-0!SLGetWindowsInformationDWORD` at `0x18000665b`
- `policymanager!PolicyManager_GetExperiencePolicy_AllowCortana` at `0x18000666d`
- `policymanager!PolicyManager_GetExperiencePolicy_AllowCortana` at `0x18000666d`
- `AutoPilot!AutoPilotIsLocalProfileAvailable` at `0x1800066ad`
- `AutoPilot!AutoPilotIsLocalProfileAvailable` at `0x1800066ad`

## string_xrefs

- `0x180006683`: `shell\cloudexperiencehost\broker\lib\oobecortanamanager.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Cortana::OOBECortanaManager::get_IsCortanaAllowedByPolicy(
        CloudExperienceHostBroker::Cortana::OOBECortanaManager *this,
        unsigned __int8 *a2)
{
  int ExperiencePolicy_AllowCortana; // edi
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD v8; // [rsp+38h] [rbp+10h] BYREF
  int v9; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+48h] [rbp+20h] BYREF

  *a2 = 0;
  v9 = 0;
  v8 = 1;
  SLGetWindowsInformationDWORD(L"Cortana-AllowCortana-Enabled", &v8);
  if ( v8 )
  {
    ExperiencePolicy_AllowCortana = PolicyManager_GetExperiencePolicy_AllowCortana(&v9);
    if ( ExperiencePolicy_AllowCortana < 0 )
    {
      v4 = 97;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\oobecortanamanager.cpp",
        (const char *)(unsigned int)ExperiencePolicy_AllowCortana,
        v6);
      return (unsigned int)ExperiencePolicy_AllowCortana;
    }
  }
  if ( !v9 )
    goto LABEL_9;
  *a2 = 1;
  v10 = 0;
  ExperiencePolicy_AllowCortana = AutoPilotIsLocalProfileAvailable(&v10);
  if ( ExperiencePolicy_AllowCortana < 0 )
  {
    v4 = 110;
    goto LABEL_4;
  }
  if ( v10 )
LABEL_9:
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x180006630  mov     rax, rsp
0x180006633  mov     [rax+8], rbx
0x180006637  push    rdi; int
0x180006638  sub     rsp, 20h
0x18000663c  mov     rbx, rdx
0x18000663f  mov     byte ptr [rdx], 0
0x180006642  lea     rdx, [rax+10h]; pdwValue
0x180006646  mov     dword ptr [rax+18h], 0
0x18000664d  lea     rcx, pwszValueName; "Cortana-AllowCortana-Enabled"
0x180006654  mov     dword ptr [rax+10h], 1
0x18000665b  call    cs:__imp_SLGetWindowsInformationDWORD
0x180006661  cmp     [rsp+28h+arg_8], 0
0x180006666  jz      short loc_180006696
0x180006668  lea     rcx, [rsp+28h+arg_10]
0x18000666d  call    cs:__imp_PolicyManager_GetExperiencePolicy_AllowCortana
0x180006673  mov     edi, eax
0x180006675  test    eax, eax
0x180006677  jns     short loc_180006696
0x180006679  mov     edx, 61h ; 'a'; void *
0x18000667e  mov     rcx, [rsp+28h]; this
0x180006683  lea     r8, aShellCloudexpe_0; "shell\\cloudexperiencehost\\broker\\lib"...
0x18000668a  mov     r9d, edi; char *
0x18000668d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006692  mov     eax, edi
0x180006694  jmp     short loc_1800066CC
0x180006696  cmp     [rsp+28h+arg_10], 0
0x18000669b  jz      short loc_1800066C7
0x18000669d  lea     rcx, [rsp+28h+arg_18]
0x1800066a2  mov     byte ptr [rbx], 1
0x1800066a5  mov     [rsp+28h+arg_18], 0
0x1800066ad  call    cs:__imp_AutoPilotIsLocalProfileAvailable
0x1800066b3  mov     edi, eax
0x1800066b5  test    eax, eax
0x1800066b7  jns     short loc_1800066C0
0x1800066b9  mov     edx, 6Eh ; 'n'
0x1800066be  jmp     short loc_18000667E
0x1800066c0  cmp     [rsp+28h+arg_18], 0
0x1800066c5  jz      short loc_1800066CA
0x1800066c7  mov     byte ptr [rbx], 0
0x1800066ca  xor     eax, eax
0x1800066cc  mov     rbx, [rsp+28h+arg_0]
0x1800066d1  add     rsp, 20h
0x1800066d5  pop     rdi
0x1800066d6  retn
```

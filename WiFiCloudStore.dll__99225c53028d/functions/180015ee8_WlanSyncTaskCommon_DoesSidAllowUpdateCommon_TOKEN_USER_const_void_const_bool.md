# WlanSyncTaskCommon::DoesSidAllowUpdateCommon(_TOKEN_USER const &,void * const,bool)

- ea: `0x180015ee8`
- end: `0x180015fa2`
- name: `?DoesSidAllowUpdateCommon@WlanSyncTaskCommon@@CA_NAEBU_TOKEN_USER@@QEAX_N@Z`
- size: `186`
- prototype: `char __fastcall(const struct _TOKEN_USER *, void *const, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800272cc`

## callees

- `0x180015ee8`
- `0x180016118`
- `0x18002c138`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180015f00`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180015f00`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180015f73`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180015f83`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180015f73`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180015f83`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180015f29`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180015f29`

## string_xrefs

- `0x180015f59`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall WlanSyncTaskCommon::DoesSidAllowUpdateCommon(const struct _TOKEN_USER *a1, void *const a2, char a3)
{
  int OwnerSecurityOfSid; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v9; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 1;
  if ( EqualSid(a1->User.Sid, a2) )
    return 1;
  v9 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v9, 0);
  if ( v9 == 14
    && (IsWellKnownSid(a2, WinWorldSid) || IsWellKnownSid(a2, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid)) )
  {
    return 1;
  }
  OwnerSecurityOfSid = Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(a2);
  if ( OwnerSecurityOfSid == 1 )
    return 0;
  if ( OwnerSecurityOfSid == 2 )
    return 1;
  if ( OwnerSecurityOfSid != 3 )
  {
    if ( OwnerSecurityOfSid != 4 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        v7);
    return 1;
  }
  return a3;
}

```

## disassembly

```asm
0x180015ee8  mov     [rsp+arg_0], rbx
0x180015eed  push    rdi
0x180015eee  sub     rsp, 20h
0x180015ef2  mov     dil, r8b
0x180015ef5  mov     rbx, rdx
0x180015ef8  test    rdx, rdx
0x180015efb  jz      short loc_180015F0A
0x180015efd  mov     rcx, [rcx]; pSid1
0x180015f00  call    cs:__imp_EqualSid
0x180015f06  test    eax, eax
0x180015f08  jz      short loc_180015F17
0x180015f0a  mov     al, 1
0x180015f0c  mov     rbx, [rsp+28h+arg_0]
0x180015f11  add     rsp, 20h
0x180015f15  pop     rdi
0x180015f16  retn
0x180015f17  xor     r8d, r8d
0x180015f1a  mov     [rsp+28h+arg_8], 0
0x180015f22  lea     rdx, [rsp+28h+arg_8]
0x180015f27  xor     ecx, ecx
0x180015f29  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180015f2f  cmp     [rsp+28h+arg_8], 0Eh
0x180015f34  jz      short loc_180015F6B
0x180015f36  mov     rcx, rbx
0x180015f39  call    ?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z; Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)
0x180015f3e  mov     ecx, eax
0x180015f40  sub     ecx, 1
0x180015f43  jz      short loc_180015F9B
0x180015f45  sub     ecx, 1
0x180015f48  jz      short loc_180015F0A
0x180015f4a  sub     ecx, 1
0x180015f4d  jz      short loc_180015F93
0x180015f4f  cmp     ecx, 1
0x180015f52  jz      short loc_180015F0A
0x180015f54  mov     rcx, [rsp+28h]; this
0x180015f59  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180015f60  mov     edx, 86h; void *
0x180015f65  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015f6b  mov     edx, 1; WellKnownSidType
0x180015f70  mov     rcx, rbx; pSid
0x180015f73  call    cs:__imp_IsWellKnownSid
0x180015f79  test    eax, eax
0x180015f7b  jnz     short loc_180015F0A
0x180015f7d  lea     edx, [rax+6Eh]; WellKnownSidType
0x180015f80  mov     rcx, rbx; pSid
0x180015f83  call    cs:__imp_IsWellKnownSid
0x180015f89  test    eax, eax
0x180015f8b  jnz     loc_180015F0A
0x180015f91  jmp     short loc_180015F36
0x180015f93  mov     al, dil
0x180015f96  jmp     loc_180015F0C
0x180015f9b  xor     al, al
0x180015f9d  jmp     loc_180015F0C
```

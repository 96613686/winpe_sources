# WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(_TOKEN_USER const &,_GUID const &,_GUID const &,bool)

- ea: `0x180015fa8`
- end: `0x180016111`
- name: `?DoesSidAllowUpdateWithProfileGuid@WlanSyncTaskCommon@@SA_NAEBU_TOKEN_USER@@AEBU_GUID@@1_N@Z`
- size: `361`
- prototype: `char __fastcall(const struct _TOKEN_USER *, const struct _GUID *, const struct _GUID *, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014d70`
- `0x1800211b0`

## callees

- `0x180015fa8`
- `0x180016118`
- `0x18002c138`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016043`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180016043`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800160e5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800160f9`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800160e5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800160f9`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180016081`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180016081`
- `wlanapi!WlanFreeMemory` at `0x180016026`
- `wlanapi!WlanFreeMemory` at `0x180016060`
- `wlanapi!WlanFreeMemory` at `0x180016026`
- `wlanapi!WlanFreeMemory` at `0x180016060`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180016005`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180016005`

## string_xrefs

- `0x180015ff5`: `CreatorSid`
- `0x1800160ad`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800160cb`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WlanSyncTaskCommon::DoesSidAllowUpdateWithProfileGuid(
        const struct _TOKEN_USER *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        char a4)
{
  unsigned int ProfileMetadataWithProfileGuid; // edi
  PSID v7; // rcx
  PSID v8; // rdi
  PSID v9; // rcx
  int v11; // eax
  const char *v12; // r9
  int v13; // eax
  int v14; // eax
  int v15; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-34h] BYREF
  PSID pSid2; // [rsp+38h] [rbp-30h] BYREF
  PSID *p_pSid2; // [rsp+40h] [rbp-28h]
  void *v19; // [rsp+48h] [rbp-20h]
  char v20; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  pSid2 = 0;
  v16 = 0;
  p_pSid2 = &pSid2;
  v19 = 0;
  v20 = 1;
  ProfileMetadataWithProfileGuid = WlanGetProfileMetadataWithProfileGuid(a2, a3, 0, L"CreatorSid");
  if ( v20 )
  {
    v7 = *p_pSid2;
    *p_pSid2 = v19;
    if ( v7 )
      WlanFreeMemory(v7);
  }
  if ( ProfileMetadataWithProfileGuid )
  {
    if ( ProfileMetadataWithProfileGuid != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)ProfileMetadataWithProfileGuid,
        (unsigned int)&v16);
    goto LABEL_7;
  }
  v8 = pSid2;
  if ( !pSid2 )
    goto LABEL_7;
  if ( EqualSid(a1->User.Sid, pSid2) )
    goto LABEL_7;
  v15 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v15, 0);
  if ( v15 == 14
    && (IsWellKnownSid(v8, WinWorldSid) || IsWellKnownSid(v8, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid)) )
  {
    goto LABEL_7;
  }
  v11 = Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(v8) - 1;
  if ( !v11 )
  {
    a4 = 0;
    goto LABEL_8;
  }
  v13 = v11 - 1;
  if ( !v13 )
  {
LABEL_7:
    a4 = 1;
    goto LABEL_8;
  }
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 != 1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        v12);
    goto LABEL_7;
  }
LABEL_8:
  v9 = pSid2;
  pSid2 = 0;
  if ( v9 )
    WlanFreeMemory(v9);
  return a4;
}

```

## disassembly

```asm
0x180015fa8  push    rbp
0x180015faa  push    rbx
0x180015fab  push    rsi
0x180015fac  push    rdi
0x180015fad  mov     rbp, rsp
0x180015fb0  sub     rsp, 68h
0x180015fb4  mov     bl, r9b
0x180015fb7  mov     rax, r8
0x180015fba  mov     r10, rdx
0x180015fbd  mov     rsi, rcx
0x180015fc0  mov     [rbp+pSid2], 0
0x180015fc8  mov     [rbp+var_34], 0
0x180015fcf  lea     rcx, [rbp+pSid2]
0x180015fd3  mov     [rbp+var_28], rcx
0x180015fd7  mov     [rbp+var_20], 0
0x180015fdf  mov     [rbp+var_18], 1
0x180015fe3  lea     rcx, [rbp+var_20]
0x180015fe7  mov     [rsp+68h+var_40], rcx
0x180015fec  lea     rcx, [rbp+var_34]
0x180015ff0  mov     qword ptr [rsp+68h+var_48], rcx; unsigned int
0x180015ff5  lea     r9, aCreatorsid; "CreatorSid"
0x180015ffc  xor     r8d, r8d
0x180015fff  mov     rdx, rax
0x180016002  mov     rcx, r10
0x180016005  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x18001600b  mov     edi, eax
0x18001600d  cmp     [rbp+var_18], 0
0x180016011  jz      short loc_18001602C
0x180016013  mov     r8, [rbp+var_28]
0x180016017  mov     rcx, [r8]; pMemory
0x18001601a  mov     rdx, [rbp+var_20]
0x18001601e  mov     [r8], rdx
0x180016021  test    rcx, rcx
0x180016024  jz      short loc_18001602C
0x180016026  call    cs:__imp_WlanFreeMemory
0x18001602c  test    edi, edi
0x18001602e  jnz     loc_1800160BF
0x180016034  mov     rdi, [rbp+pSid2]
0x180016038  test    rdi, rdi
0x18001603b  jz      short loc_18001604D
0x18001603d  mov     rdx, rdi; pSid2
0x180016040  mov     rcx, [rsi]; pSid1
0x180016043  call    cs:__imp_EqualSid
0x180016049  test    eax, eax
0x18001604b  jz      short loc_180016071
0x18001604d  mov     bl, 1
0x18001604f  mov     rcx, [rbp+pSid2]; pMemory
0x180016053  mov     [rbp+pSid2], 0
0x18001605b  test    rcx, rcx
0x18001605e  jz      short loc_180016066
0x180016060  call    cs:__imp_WlanFreeMemory
0x180016066  mov     al, bl
0x180016068  add     rsp, 68h
0x18001606c  pop     rdi
0x18001606d  pop     rsi
0x18001606e  pop     rbx
0x18001606f  pop     rbp
0x180016070  retn
0x180016071  mov     [rbp+var_38], 0
0x180016078  xor     r8d, r8d
0x18001607b  lea     rdx, [rbp+var_38]
0x18001607f  xor     ecx, ecx
0x180016081  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180016087  cmp     [rbp+var_38], 0Eh
0x18001608b  jz      short loc_1800160DD
0x18001608d  mov     rcx, rdi
0x180016090  call    ?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z; Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)
0x180016095  sub     eax, 1
0x180016098  jz      short loc_180016109
0x18001609a  sub     eax, 1
0x18001609d  jz      short loc_18001604D
0x18001609f  sub     eax, 1
0x1800160a2  jz      short loc_18001604F
0x1800160a4  cmp     eax, 1
0x1800160a7  jz      short loc_18001604D
0x1800160a9  mov     rcx, [rbp+20h]; this
0x1800160ad  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800160b4  mov     edx, 86h; void *
0x1800160b9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800160bf  cmp     edi, 2
0x1800160c2  jz      short loc_18001604D
0x1800160c4  mov     rcx, [rbp+20h]; this
0x1800160c8  mov     r9d, edi; char *
0x1800160cb  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800160d2  mov     edx, 9Bh; void *
0x1800160d7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800160dd  mov     edx, 1; WellKnownSidType
0x1800160e2  mov     rcx, rdi; pSid
0x1800160e5  call    cs:__imp_IsWellKnownSid
0x1800160eb  test    eax, eax
0x1800160ed  jnz     loc_18001604D
0x1800160f3  lea     edx, [rax+6Eh]; WellKnownSidType
0x1800160f6  mov     rcx, rdi; pSid
0x1800160f9  call    cs:__imp_IsWellKnownSid
0x1800160ff  test    eax, eax
0x180016101  jnz     loc_18001604D
0x180016107  jmp     short loc_18001608D
0x180016109  xor     bl, bl
0x18001610b  jmp     loc_18001604F
```

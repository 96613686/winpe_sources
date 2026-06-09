# Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void * const)

- ea: `0x180016118`
- end: `0x180016371`
- name: `?GetOwnerSecurityOfSid@WiFiCloudStore@Internal@Windows@@YA?AW4ProfileOwnerSecurity@123@QEAX@Z`
- size: `601`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015ee8`
- `0x180015fa8`
- `0x18003651c`
- `0x18003c170`

## callees

- `0x18000b788`
- `0x18000b7f8`
- `0x180016118`
- `0x18001e1a0`
- `0x180031ce4`
- `0x180032254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016341`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016134`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016148`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001615c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016170`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016134`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016148`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001615c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180016170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800162b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800161bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001622c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800161bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001622c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180016267`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180016267`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180016337`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180016337`

## string_xrefs

- `0x1800161aa`: `DefaultAccountSID`
- `0x180016217`: `DefaultAccountSID`
- `0x18001623e`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`
- `0x180016276`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::WiFiCloudStore::GetOwnerSecurityOfSid(void *a1)
{
  char *v4; // rdi
  unsigned int ValueW; // eax
  const char *v6; // r9
  LPWSTR v7; // rcx
  char *v8; // r8
  int v9; // edx
  int v10; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD cchName; // [rsp+80h] [rbp+8h] BYREF
  _SID_NAME_USE peUse; // [rsp+88h] [rbp+10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp+20h] BYREF

  if ( !a1 )
    return 4;
  if ( IsWellKnownSid(a1, WinWorldSid) || IsWellKnownSid(a1, WinLocalSystemSid) )
    return 2;
  if ( IsWellKnownSid(a1, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid)
    || IsWellKnownSid(a1, WinLocalServiceSid) )
  {
    return 3;
  }
  cchName = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
          L"DefaultAccountSID",
          2u,
          0,
          0,
          &cchName) )
  {
    try
    {
      *(_OWORD *)pvData = 0;
      v13 = 0;
      std::vector<unsigned char>::_Construct_n<>(pvData, cchName);
      v4 = (char *)pvData[0];
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
                 L"DefaultAccountSID",
                 2u,
                 0,
                 pvData[0],
                 &cchName);
      if ( ValueW )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
          (const char *)ValueW,
          pdwType);
      StringSid = 0;
      if ( !ConvertSidToStringSidW(a1, &StringSid) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
          v6);
      v7 = StringSid;
      v8 = (char *)((char *)StringSid - v4);
      do
      {
        v9 = *(unsigned __int16 *)&v8[(_QWORD)v4];
        v10 = *(unsigned __int16 *)v4 - v9;
        if ( v10 )
          break;
        v4 += 2;
      }
      while ( v9 );
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
        v6);
      return 1;
    }
    if ( !v10 )
    {
      if ( v7 )
        LocalFree(v7);
      std::vector<unsigned char>::_Tidy(pvData);
      return 3;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    std::vector<unsigned char>::_Tidy(pvData);
  }
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = SidTypeUnknown;
  if ( LookupAccountSidW(0, a1, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 1332 )
    return 1;
  else
    return 3;
}

```

## disassembly

```asm
0x180016118  push    rbx
0x18001611a  push    rdi
0x18001611b  sub     rsp, 68h
0x18001611f  mov     rbx, rcx
0x180016122  test    rcx, rcx
0x180016125  jnz     short loc_18001612F
0x180016127  lea     eax, [rcx+4]
0x18001612a  jmp     loc_18001636A
0x18001612f  mov     edx, 1; WellKnownSidType
0x180016134  call    cs:__imp_IsWellKnownSid
0x18001613a  test    eax, eax
0x18001613c  jnz     loc_18001635E
0x180016142  lea     edx, [rax+16h]; WellKnownSidType
0x180016145  mov     rcx, rbx; pSid
0x180016148  call    cs:__imp_IsWellKnownSid
0x18001614e  test    eax, eax
0x180016150  jnz     loc_18001635E
0x180016156  lea     edx, [rax+6Eh]; WellKnownSidType
0x180016159  mov     rcx, rbx; pSid
0x18001615c  call    cs:__imp_IsWellKnownSid
0x180016162  test    eax, eax
0x180016164  jnz     loc_180016357
0x18001616a  lea     edx, [rax+17h]; WellKnownSidType
0x18001616d  mov     rcx, rbx; pSid
0x180016170  call    cs:__imp_IsWellKnownSid
0x180016176  test    eax, eax
0x180016178  jnz     loc_180016357
0x18001617e  mov     [rsp+78h+cchName], eax
0x180016185  lea     rax, [rsp+78h+cchName]
0x18001618d  mov     [rsp+78h+pcbData], rax; pcbData
0x180016192  mov     [rsp+78h+pvData], 0; pvData
0x18001619b  mov     [rsp+78h+pdwType], 0; pdwType
0x1800161a4  mov     r9d, 2; dwFlags
0x1800161aa  lea     r8, aDefaultaccount; "DefaultAccountSID"
0x1800161b1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800161b8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800161bf  call    cs:__imp_RegGetValueW
0x1800161c5  test    eax, eax
0x1800161c7  jnz     loc_1800162E3
0x1800161cd  xorps   xmm0, xmm0
0x1800161d0  movdqu  xmmword ptr [rsp+78h+var_38], xmm0
0x1800161d6  mov     [rsp+78h+var_28], 0
0x1800161df  mov     edx, [rsp+78h+cchName]
0x1800161e6  lea     rcx, [rsp+78h+var_38]
0x1800161eb  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x1800161f0  nop
0x1800161f1  lea     rax, [rsp+78h+cchName]
0x1800161f9  mov     [rsp+78h+pcbData], rax; pcbData
0x1800161fe  mov     rdi, [rsp+78h+var_38]
0x180016203  mov     [rsp+78h+pvData], rdi; pvData
0x180016208  mov     [rsp+78h+pdwType], 0; unsigned int
0x180016211  mov     r9d, 2; dwFlags
0x180016217  lea     r8, aDefaultaccount; "DefaultAccountSID"
0x18001621e  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180016225  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001622c  call    cs:__imp_RegGetValueW
0x180016232  mov     rcx, [rsp+78h]; this
0x180016237  test    eax, eax
0x180016239  jz      short loc_180016250
0x18001623b  mov     r9d, eax; char *
0x18001623e  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180016245  mov     edx, 4Eh ; 'N'; void *
0x18001624a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180016250  mov     [rsp+78h+StringSid], 0
0x18001625c  lea     rdx, [rsp+78h+StringSid]; StringSid
0x180016264  mov     rcx, rbx; Sid
0x180016267  call    cs:__imp_ConvertSidToStringSidW
0x18001626d  mov     rcx, [rsp+78h]; this
0x180016272  test    eax, eax
0x180016274  jnz     short loc_180016285
0x180016276  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18001627d  lea     edx, [rax+51h]; void *
0x180016280  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180016285  mov     rcx, [rsp+78h+StringSid]; hMem
0x18001628d  mov     r8, rcx
0x180016290  sub     r8, rdi
0x180016293  movzx   eax, word ptr [rdi]
0x180016296  movzx   edx, word ptr [rdi+r8]
0x18001629b  sub     eax, edx
0x18001629d  jnz     short loc_1800162A7
0x18001629f  add     rdi, 2
0x1800162a3  test    edx, edx
0x1800162a5  jnz     short loc_180016293
0x1800162a7  test    eax, eax
0x1800162a9  jnz     short loc_1800162CB
0x1800162ab  test    rcx, rcx
0x1800162ae  jz      short loc_1800162B7
0x1800162b0  call    cs:__imp_LocalFree
0x1800162b6  nop
0x1800162b7  lea     rcx, [rsp+78h+var_38]
0x1800162bc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800162c1  mov     eax, 3
0x1800162c6  jmp     loc_18001636A
0x1800162cb  lea     rcx, [rsp+78h+StringSid]
0x1800162d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800162d8  nop
0x1800162d9  lea     rcx, [rsp+78h+var_38]
0x1800162de  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800162e3  mov     [rsp+78h+cchName], 0
0x1800162ee  mov     [rsp+78h+cchReferencedDomainName], 0
0x1800162f9  mov     [rsp+78h+peUse], 8
0x180016304  lea     rax, [rsp+78h+peUse]
0x18001630c  mov     [rsp+78h+pcbData], rax; peUse
0x180016311  lea     rax, [rsp+78h+cchReferencedDomainName]
0x180016319  mov     [rsp+78h+pvData], rax; cchReferencedDomainName
0x18001631e  mov     [rsp+78h+pdwType], 0; ReferencedDomainName
0x180016327  lea     r9, [rsp+78h+cchName]; cchName
0x18001632f  xor     r8d, r8d; Name
0x180016332  mov     rdx, rbx; Sid
0x180016335  xor     ecx, ecx; lpSystemName
0x180016337  call    cs:__imp_LookupAccountSidW
0x18001633d  test    eax, eax
0x18001633f  jnz     short loc_180016355
0x180016341  call    cs:__imp_GetLastError
0x180016347  cmp     eax, 534h
0x18001634c  jnz     short loc_180016355
0x18001634e  mov     eax, 3
0x180016353  jmp     short loc_18001636A
0x180016355  jmp     short loc_180016365
0x180016357  mov     eax, 3
0x18001635c  jmp     short loc_18001636A
0x18001635e  mov     eax, 2
0x180016363  jmp     short loc_18001636A
0x180016365  mov     eax, 1
0x18001636a  add     rsp, 68h
0x18001636e  pop     rdi
0x18001636f  pop     rbx
0x180016370  retn
```

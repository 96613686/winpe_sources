# AgentAccountHelpers2::AddUserSecurityGroup(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180040874`
- end: `0x180040c88`
- name: `?AddUserSecurityGroup@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAV23@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(const WCHAR *groupname, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037064`
- `0x18005da50`
- `0x18005f3bc`

## callees

- `0x180002520`
- `0x180011e18`
- `0x180021564`
- `0x180040874`

## import_xrefs

- `NETAPI32!NetLocalGroupAddMembers` at `0x180040bc0`
- `NETAPI32!NetLocalGroupAddMembers` at `0x180040bc0`
- `NETAPI32!NetLocalGroupAdd` at `0x1800408f9`
- `NETAPI32!NetLocalGroupAdd` at `0x1800408f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800409dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040b67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040a93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040b3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040a93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040b3e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040b09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040b09`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040a5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040a8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040b8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040c60`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800409c2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800409c2`

## string_xrefs

- `0x18004091c`: `Failed to create Group %s: %#x`
- `0x180040967`: `Obtain group's identity in the form of SID`
- `0x180040953`: `Local Group %s successfully created with status = %d`
- `0x180040a15`: `SID is not of type SitTypeAlias, but = %d. Failing request`
- `0x1800409cc`: `Failed to obtain SID for the local group`
- `0x180040abe`: `Group identity computed %s`
- `0x180040aad`: `Failed to convert local group's SID to string form`
- `0x180040b57`: `Failed converting StringSid to SID`
- `0x180040acd`: `Adding agent user to the local group`
- `0x180040c1a`: `Success. Added agent user = %s to the group = %s.`
- `0x180040c46`: `AddUserSecurityGroup completed successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AgentAccountHelpers2::AddUserSecurityGroup(
        const WCHAR *groupname,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // r14
  const WCHAR *v6; // rdi
  const WCHAR *v7; // r8
  const WCHAR *v8; // rax
  DWORD v9; // eax
  signed int v10; // ebx
  const WCHAR *v12; // r8
  const WCHAR *v13; // rdx
  signed int v14; // eax
  BOOL v15; // r13d
  LPWSTR v16; // r12
  _QWORD *v17; // r14
  void *v18; // r15
  DWORD LastError; // ebx
  const WCHAR *v20; // rcx
  BOOL v21; // r13d
  LPWSTR v22; // r12
  _QWORD *v23; // r14
  void *v24; // r15
  DWORD v25; // ebx
  signed int v26; // eax
  const WCHAR *v27; // rdx
  DWORD v28; // eax
  BYTE buf[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  void **p_hMem; // [rsp+58h] [rbp-A8h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  char v34; // [rsp+68h] [rbp-98h]
  DWORD cchReferencedDomainName[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  WCHAR ReferencedDomainName[20]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE Sid[80]; // [rsp+B0h] [rbp-50h] BYREF

  v37 = a4;
  v4 = a3;
  v36 = a3;
  v6 = groupname;
  *(_QWORD *)buf = 0;
  if ( *((_QWORD *)groupname + 3) <= 7u )
    v7 = groupname;
  else
    v7 = *(const WCHAR **)groupname;
  Log(4u, L"Ensure group exist for the client %s", v7);
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v8 = v6;
  else
    v8 = *(const WCHAR **)v6;
  *(_QWORD *)buf = v8;
  v9 = NetLocalGroupAdd(0, 0, buf, 0);
  v10 = v9;
  if ( v9 != 1379 && v9 )
  {
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(const WCHAR **)v6;
    Log(2u, L"Failed to create Group %s: %#x", v6, v9);
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
    return (unsigned int)v10;
  }
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v12 = v6;
  else
    v12 = *(const WCHAR **)v6;
  Log(4u, L"Local Group %s successfully created with status = %d", v12, v9);
  hMem = 0;
  Log(4u, L"Obtain group's identity in the form of SID");
  *(_DWORD *)buf = 68;
  cchReferencedDomainName[0] = 16;
  peUse = 0;
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v13 = v6;
  else
    v13 = *(const WCHAR **)v6;
  if ( !LookupAccountNameW(0, v13, Sid, (LPDWORD)buf, ReferencedDomainName, cchReferencedDomainName, &peUse) )
  {
    Log(2u, L"Failed to obtain SID for the local group");
    goto LABEL_22;
  }
  if ( peUse != SidTypeAlias )
  {
    Log(2u, L"SID is not of type SitTypeAlias, but = %d. Failing request");
    if ( hMem )
      LocalFree(hMem);
    return 2147942405LL;
  }
  p_hMem = &hMem;
  StringSid = 0;
  v34 = 1;
  v15 = ConvertSidToStringSidW(Sid, &StringSid);
  if ( v34 )
  {
    v16 = StringSid;
    v17 = p_hMem;
    v18 = *p_hMem;
    if ( *p_hMem )
    {
      LastError = GetLastError();
      LocalFree(v18);
      SetLastError(LastError);
    }
    *v17 = v16;
    v4 = v36;
  }
  if ( !v15 )
  {
    Log(2u, L"Failed to convert local group's SID to string form");
LABEL_22:
    v14 = GetLastError();
    v10 = v14;
    if ( v14 > 0 )
      v10 = (unsigned __int16)v14 | 0x80070000;
LABEL_24:
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)v10;
  }
  Log(4u, L"Group identity computed %s", hMem);
  Log(4u, L"Adding agent user to the local group");
  *(_QWORD *)buf = 0;
  p_hMem = (void **)buf;
  StringSid = 0;
  v34 = 1;
  if ( *(_QWORD *)(v4 + 24) <= 7u )
    v20 = (const WCHAR *)v4;
  else
    v20 = *(const WCHAR **)v4;
  v21 = ConvertStringSidToSidW(v20, (PSID *)&StringSid);
  if ( v34 )
  {
    v22 = StringSid;
    v23 = p_hMem;
    v24 = *p_hMem;
    if ( *p_hMem )
    {
      v25 = GetLastError();
      LocalFree(v24);
      SetLastError(v25);
    }
    *v23 = v22;
    v4 = v36;
  }
  if ( !v21 )
  {
    Log(2u, L"Failed converting StringSid to SID");
    v26 = GetLastError();
    v10 = v26;
    if ( v26 <= 0 )
      goto LABEL_47;
    v10 = (unsigned __int16)v26;
LABEL_46:
    v10 |= 0x80070000;
LABEL_47:
    if ( *(_QWORD *)buf )
      LocalFree(*(HLOCAL *)buf);
    goto LABEL_24;
  }
  *(_QWORD *)cchReferencedDomainName = *(_QWORD *)buf;
  if ( *((_QWORD *)v6 + 3) <= 7u )
    v27 = v6;
  else
    v27 = *(const WCHAR **)v6;
  v28 = NetLocalGroupAddMembers(0, v27, 0, (LPBYTE)cchReferencedDomainName, 1u);
  v10 = v28;
  if ( v28 != 1378 && v28 )
  {
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    Log(2u, L"Failed to add user %s to the group. Error =  %#x", a2, v28);
    if ( v10 <= 0 )
      goto LABEL_47;
    v10 = (unsigned __int16)v10;
    goto LABEL_46;
  }
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(const WCHAR **)v6;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  Log(4u, L"Success. Added agent user = %s to the group = %s.", a2, v6);
  if ( *(_QWORD *)buf )
    LocalFree(*(HLOCAL *)buf);
  std::wstring::operator=(v37, v4);
  Log(4u, L"AddUserSecurityGroup completed successfully");
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180040874  push    rbp
0x180040876  push    rbx
0x180040877  push    rsi
0x180040878  push    rdi
0x180040879  push    r12
0x18004087b  push    r13
0x18004087d  push    r14
0x18004087f  push    r15
0x180040881  lea     rbp, [rsp-18h]
0x180040886  sub     rsp, 118h
0x18004088d  mov     rax, cs:__security_cookie
0x180040894  xor     rax, rsp
0x180040897  mov     [rbp+50h+var_50], rax
0x18004089b  mov     [rbp+50h+var_D0], r9
0x18004089f  mov     r14, r8
0x1800408a2  mov     [rsp+150h+var_D8], r8
0x1800408a7  mov     rsi, rdx
0x1800408aa  mov     rdi, rcx
0x1800408ad  xor     r15d, r15d
0x1800408b0  mov     qword ptr [rsp+150h+buf], r15
0x1800408b5  cmp     qword ptr [rcx+18h], 7
0x1800408ba  jbe     short loc_1800408C1
0x1800408bc  mov     r8, [rcx]
0x1800408bf  jmp     short loc_1800408C4
0x1800408c1  mov     r8, rdi
0x1800408c4  lea     rdx, aEnsureGroupExi; "Ensure group exist for the client %s"
0x1800408cb  mov     r12d, 4
0x1800408d1  mov     ecx, r12d; unsigned __int8
0x1800408d4  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800408d9  cmp     qword ptr [rdi+18h], 7
0x1800408de  jbe     short loc_1800408E5
0x1800408e0  mov     rax, [rdi]
0x1800408e3  jmp     short loc_1800408E8
0x1800408e5  mov     rax, rdi
0x1800408e8  mov     qword ptr [rsp+150h+buf], rax
0x1800408ed  xor     r9d, r9d; parm_err
0x1800408f0  lea     r8, [rsp+150h+buf]; buf
0x1800408f5  xor     edx, edx; level
0x1800408f7  xor     ecx, ecx; servername
0x1800408f9  call    cs:__imp_NetLocalGroupAdd
0x1800408ff  mov     ebx, eax
0x180040901  cmp     eax, 563h
0x180040906  jz      short loc_180040941
0x180040908  test    eax, eax
0x18004090a  jz      short loc_180040941
0x18004090c  cmp     qword ptr [rdi+18h], 7
0x180040911  jbe     short loc_180040916
0x180040913  mov     rdi, [rdi]
0x180040916  mov     r9d, ebx
0x180040919  mov     r8, rdi
0x18004091c  lea     rdx, aFailedToCreate_0; "Failed to create Group %s: %#x"
0x180040923  mov     ecx, 2; unsigned __int8
0x180040928  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004092d  test    ebx, ebx
0x18004092f  jle     short loc_18004093A
0x180040931  movzx   ebx, bx
0x180040934  or      ebx, 80070000h
0x18004093a  mov     eax, ebx
0x18004093c  jmp     loc_180040C68
0x180040941  cmp     qword ptr [rdi+18h], 7
0x180040946  jbe     short loc_18004094D
0x180040948  mov     r8, [rdi]
0x18004094b  jmp     short loc_180040950
0x18004094d  mov     r8, rdi
0x180040950  mov     r9d, ebx
0x180040953  lea     rdx, aLocalGroupSSuc; "Local Group %s successfully created wit"...
0x18004095a  mov     ecx, r12d; unsigned __int8
0x18004095d  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040962  mov     [rsp+150h+hMem], r15
0x180040967  lea     rdx, aObtainGroupSId; "Obtain group's identity in the form of "...
0x18004096e  mov     ecx, r12d; unsigned __int8
0x180040971  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040976  mov     dword ptr [rsp+150h+buf], 44h ; 'D'
0x18004097e  mov     [rsp+150h+var_E0], 10h
0x180040986  mov     [rsp+150h+var_100], r15d
0x18004098b  cmp     qword ptr [rdi+18h], 7
0x180040990  jbe     short loc_180040997
0x180040992  mov     rdx, [rdi]
0x180040995  jmp     short loc_18004099A
0x180040997  mov     rdx, rdi; lpAccountName
0x18004099a  lea     rax, [rsp+150h+var_100]
0x18004099f  mov     [rsp+150h+peUse], rax; peUse
0x1800409a4  lea     rax, [rsp+150h+var_E0]
0x1800409a9  mov     [rsp+150h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800409ae  lea     rax, [rbp+50h+var_C8]
0x1800409b2  mov     [rsp+150h+ReferencedDomainName], rax; ReferencedDomainName
0x1800409b7  lea     r9, [rsp+150h+buf]; cbSid
0x1800409bc  lea     r8, [rbp+50h+Sid]; Sid
0x1800409c0  xor     ecx, ecx; lpSystemName
0x1800409c2  call    cs:__imp_LookupAccountNameW
0x1800409c8  test    eax, eax
0x1800409ca  jnz     short loc_180040A0B
0x1800409cc  lea     rdx, aFailedToObtain; "Failed to obtain SID for the local grou"...
0x1800409d3  mov     ecx, 2; unsigned __int8
0x1800409d8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800409dd  call    cs:__imp_GetLastError
0x1800409e3  test    eax, eax
0x1800409e5  mov     ebx, eax
0x1800409e7  jle     short loc_1800409F2
0x1800409e9  movzx   ebx, ax
0x1800409ec  or      ebx, 80070000h
0x1800409f2  mov     rcx, [rsp+150h+hMem]; hMem
0x1800409f7  test    rcx, rcx
0x1800409fa  jz      loc_18004093A
0x180040a00  call    cs:__imp_LocalFree
0x180040a06  jmp     loc_18004093A
0x180040a0b  mov     r8d, [rsp+150h+var_100]
0x180040a10  cmp     r8d, r12d
0x180040a13  jz      short loc_180040A41
0x180040a15  lea     rdx, aSidIsNotOfType; "SID is not of type SitTypeAlias, but = "...
0x180040a1c  mov     ecx, 2; unsigned __int8
0x180040a21  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040a26  nop
0x180040a27  mov     rcx, [rsp+150h+hMem]; hMem
0x180040a2c  test    rcx, rcx
0x180040a2f  jz      short loc_180040A37
0x180040a31  call    cs:__imp_LocalFree
0x180040a37  mov     eax, 80070005h
0x180040a3c  jmp     loc_180040C68
0x180040a41  lea     rax, [rsp+150h+hMem]
0x180040a46  mov     [rsp+150h+var_F8], rax
0x180040a4b  mov     [rsp+150h+StringSid], r15
0x180040a50  mov     [rsp+150h+var_E8], 1
0x180040a55  lea     rdx, [rsp+150h+StringSid]; StringSid
0x180040a5a  lea     rcx, [rbp+50h+Sid]; Sid
0x180040a5e  call    cs:__imp_ConvertSidToStringSidW
0x180040a64  mov     r13d, eax
0x180040a67  cmp     [rsp+150h+var_E8], r15b
0x180040a6c  jz      short loc_180040AA8
0x180040a6e  mov     r12, [rsp+150h+StringSid]
0x180040a73  mov     r14, [rsp+150h+var_F8]
0x180040a78  mov     r15, [r14]
0x180040a7b  test    r15, r15
0x180040a7e  jz      short loc_180040A99
0x180040a80  call    cs:__imp_GetLastError
0x180040a86  mov     ebx, eax
0x180040a88  mov     rcx, r15; hMem
0x180040a8b  call    cs:__imp_LocalFree
0x180040a91  mov     ecx, ebx; dwErrCode
0x180040a93  call    cs:__imp_SetLastError
0x180040a99  mov     [r14], r12
0x180040a9c  mov     r14, [rsp+150h+var_D8]
0x180040aa1  xor     r15d, r15d
0x180040aa4  lea     r12d, [r15+4]
0x180040aa8  test    r13d, r13d
0x180040aab  jnz     short loc_180040AB9
0x180040aad  lea     rdx, aFailedToConver; "Failed to convert local group's SID to "...
0x180040ab4  jmp     loc_1800409D3
0x180040ab9  mov     r8, [rsp+150h+hMem]
0x180040abe  lea     rdx, aGroupIdentityC; "Group identity computed %s"
0x180040ac5  mov     ecx, r12d; unsigned __int8
0x180040ac8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040acd  lea     rdx, aAddingAgentUse; "Adding agent user to the local group"
0x180040ad4  mov     ecx, r12d; unsigned __int8
0x180040ad7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040adc  mov     qword ptr [rsp+150h+buf], r15
0x180040ae1  lea     rax, [rsp+150h+buf]
0x180040ae6  mov     [rsp+150h+var_F8], rax
0x180040aeb  mov     [rsp+150h+StringSid], r15
0x180040af0  mov     [rsp+150h+var_E8], 1
0x180040af5  cmp     qword ptr [r14+18h], 7
0x180040afa  jbe     short loc_180040B01
0x180040afc  mov     rcx, [r14]
0x180040aff  jmp     short loc_180040B04
0x180040b01  mov     rcx, r14; StringSid
0x180040b04  lea     rdx, [rsp+150h+StringSid]; Sid
0x180040b09  call    cs:__imp_ConvertStringSidToSidW
0x180040b0f  mov     r13d, eax
0x180040b12  cmp     [rsp+150h+var_E8], r15b
0x180040b17  jz      short loc_180040B52
0x180040b19  mov     r12, [rsp+150h+StringSid]
0x180040b1e  mov     r14, [rsp+150h+var_F8]
0x180040b23  mov     r15, [r14]
0x180040b26  test    r15, r15
0x180040b29  jz      short loc_180040B44
0x180040b2b  call    cs:__imp_GetLastError
0x180040b31  mov     ebx, eax
0x180040b33  mov     rcx, r15; hMem
0x180040b36  call    cs:__imp_LocalFree
0x180040b3c  mov     ecx, ebx; dwErrCode
0x180040b3e  call    cs:__imp_SetLastError
0x180040b44  mov     [r14], r12
0x180040b47  mov     r14, [rsp+150h+var_D8]
0x180040b4c  mov     r12d, 4
0x180040b52  test    r13d, r13d
0x180040b55  jnz     short loc_180040B95
0x180040b57  lea     rdx, aFailedConverti; "Failed converting StringSid to SID"
0x180040b5e  lea     ecx, [r13+2]; unsigned __int8
0x180040b62  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040b67  call    cs:__imp_GetLastError
0x180040b6d  mov     ebx, eax
0x180040b6f  test    eax, eax
0x180040b71  jle     short loc_180040B7C
0x180040b73  movzx   ebx, ax
0x180040b76  or      ebx, 80070000h
0x180040b7c  mov     rcx, qword ptr [rsp+150h+buf]; hMem
0x180040b81  test    rcx, rcx
0x180040b84  jz      loc_1800409F2
0x180040b8a  call    cs:__imp_LocalFree
0x180040b90  jmp     loc_1800409F2
0x180040b95  mov     rax, qword ptr [rsp+150h+buf]
0x180040b9a  mov     qword ptr [rsp+150h+var_E0], rax
0x180040b9f  cmp     qword ptr [rdi+18h], 7
0x180040ba4  jbe     short loc_180040BAB
0x180040ba6  mov     rdx, [rdi]
0x180040ba9  jmp     short loc_180040BAE
0x180040bab  mov     rdx, rdi; groupname
0x180040bae  mov     dword ptr [rsp+150h+ReferencedDomainName], 1; totalentries
0x180040bb6  lea     r9, [rsp+150h+var_E0]; buf
0x180040bbb  xor     r8d, r8d; level
0x180040bbe  xor     ecx, ecx; servername
0x180040bc0  call    cs:__imp_NetLocalGroupAddMembers
0x180040bc6  mov     ebx, eax
0x180040bc8  cmp     eax, 562h
0x180040bcd  jz      short loc_180040C00
0x180040bcf  test    eax, eax
0x180040bd1  jz      short loc_180040C00
0x180040bd3  cmp     qword ptr [rsi+18h], 7
0x180040bd8  jbe     short loc_180040BDD
0x180040bda  mov     rsi, [rsi]
0x180040bdd  mov     r9d, ebx
0x180040be0  mov     r8, rsi
0x180040be3  lea     rdx, aFailedToAddUse; "Failed to add user %s to the group. Err"...
0x180040bea  mov     ecx, 2; unsigned __int8
0x180040bef  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040bf4  test    ebx, ebx
0x180040bf6  jle     short loc_180040B7C
0x180040bf8  movzx   ebx, bx
0x180040bfb  jmp     loc_180040B76
0x180040c00  cmp     qword ptr [rdi+18h], 7
0x180040c05  jbe     short loc_180040C0A
0x180040c07  mov     rdi, [rdi]
0x180040c0a  cmp     qword ptr [rsi+18h], 7
0x180040c0f  jbe     short loc_180040C14
0x180040c11  mov     rsi, [rsi]
0x180040c14  mov     r9, rdi
0x180040c17  mov     r8, rsi
0x180040c1a  lea     rdx, aSuccessAddedAg; "Success. Added agent user = %s to the g"...
0x180040c21  mov     ecx, r12d; unsigned __int8
0x180040c24  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040c29  nop
0x180040c2a  mov     rcx, qword ptr [rsp+150h+buf]; hMem
0x180040c2f  test    rcx, rcx
0x180040c32  jz      short loc_180040C3A
0x180040c34  call    cs:__imp_LocalFree
0x180040c3a  mov     rdx, r14
0x180040c3d  mov     rcx, [rbp+50h+var_D0]
0x180040c41  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180040c46  lea     rdx, aAddusersecurit; "AddUserSecurityGroup completed successf"...
0x180040c4d  mov     ecx, r12d; unsigned __int8
0x180040c50  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040c55  nop
0x180040c56  mov     rcx, [rsp+150h+hMem]; hMem
0x180040c5b  test    rcx, rcx
0x180040c5e  jz      short loc_180040C66
0x180040c60  call    cs:__imp_LocalFree
0x180040c66  xor     eax, eax
0x180040c68  mov     rcx, [rbp+50h+var_50]
0x180040c6c  xor     rcx, rsp; StackCookie
0x180040c6f  call    __security_check_cookie
0x180040c74  add     rsp, 118h
0x180040c7b  pop     r15
0x180040c7d  pop     r14
0x180040c7f  pop     r13
0x180040c81  pop     r12
0x180040c83  pop     rdi
0x180040c84  pop     rsi
0x180040c85  pop     rbx
0x180040c86  pop     rbp
0x180040c87  retn
```

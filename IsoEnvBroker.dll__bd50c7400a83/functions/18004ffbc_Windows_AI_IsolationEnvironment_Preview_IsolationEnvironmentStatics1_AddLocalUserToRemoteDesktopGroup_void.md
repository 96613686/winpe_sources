# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::AddLocalUserToRemoteDesktopGroup(void *)

- ea: `0x18004ffbc`
- end: `0x1800501b0`
- name: `?AddLocalUserToRemoteDesktopGroup@IsolationEnvironmentStatics1@Preview@IsolationEnvironment@AI@Windows@@AEAAJPEAX@Z`
- size: `500`
- prototype: `int(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1 *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800507a8`

## callees

- `0x180002520`
- `0x180011e18`
- `0x18004ffbc`

## import_xrefs

- `NETAPI32!NetLocalGroupAddMembers` at `0x1800500b3`
- `NETAPI32!NetLocalGroupAddMembers` at `0x1800500b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005010e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005012f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005010e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005012f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180050121`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800500ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800500ec`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050007`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180050007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050179`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050179`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18005007f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18005007f`

## string_xrefs

- `0x180050017`: `Failed to create well known SID for Remote Desktop Group: %#x`
- `0x180050138`: `Failed to convert AU SID to string: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::AddLocalUserToRemoteDesktopGroup(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1 *this,
        void *a2)
{
  DWORD LastError; // eax
  const wchar_t *v4; // rdx
  int v5; // ebx
  DWORD v7; // edi
  BOOL v8; // r12d
  LPWSTR v9; // r15
  _QWORD *v10; // rsi
  HLOCAL v11; // r14
  DWORD v12; // ebx
  DWORD v13; // eax
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-C4h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL *p_hMem; // [rsp+48h] [rbp-B8h]
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  BYTE buf[8]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[20]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[256]; // [rsp+E0h] [rbp-20h] BYREF

  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinRemoteDesktopUsersSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    v4 = L"Failed to create well known SID for Remote Desktop Group: %#x";
LABEL_3:
    v5 = LastError;
    Log(2u, v4, LastError);
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    return (unsigned int)v5;
  }
  cchName = 256;
  cchReferencedDomainName = 15;
  peUse = 0;
  if ( !LookupAccountSidLocalW(pSid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    LastError = GetLastError();
    v4 = L"Failed to look up Remote Desktop group group name: %#x";
    goto LABEL_3;
  }
  *(_QWORD *)buf = a2;
  v7 = NetLocalGroupAddMembers(0, Name, 0, buf, 1u);
  if ( !v7 )
    return 0;
  hMem = 0;
  p_hMem = &hMem;
  StringSid = 0;
  v21 = 1;
  v8 = ConvertSidToStringSidW(a2, &StringSid);
  if ( v21 )
  {
    v9 = StringSid;
    v10 = p_hMem;
    v11 = *p_hMem;
    if ( *p_hMem )
    {
      v12 = GetLastError();
      LocalFree(v11);
      SetLastError(v12);
    }
    *v10 = v9;
  }
  if ( !v8 )
  {
    v13 = GetLastError();
    Log(2u, L"Failed to convert AU SID to string: %#x", v13);
  }
  Log(2u, L"Failed to add AU '%s' to Remote Desktop Group: %#x", hMem, v7);
  if ( (int)v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( hMem )
    LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x18004ffbc  mov     [rsp-8+arg_0], rbx
0x18004ffc1  mov     [rsp-8+arg_10], rsi
0x18004ffc6  push    rbp
0x18004ffc7  push    rdi
0x18004ffc8  push    r12
0x18004ffca  push    r14
0x18004ffcc  push    r15
0x18004ffce  lea     rbp, [rsp-1F0h]
0x18004ffd6  sub     rsp, 2F0h
0x18004ffdd  mov     rax, cs:__security_cookie
0x18004ffe4  xor     rax, rsp
0x18004ffe7  mov     [rbp+210h+var_30], rax
0x18004ffee  mov     rbx, rdx
0x18004fff1  mov     [rsp+310h+cbSid], 44h ; 'D'
0x18004fff9  lea     r9, [rsp+310h+cbSid]; cbSid
0x18004fffe  lea     r8, [rbp+210h+pSid]; pSid
0x180050002  xor     edx, edx; DomainSid
0x180050004  lea     ecx, [rdx+24h]; WellKnownSidType
0x180050007  call    cs:__imp_CreateWellKnownSid
0x18005000d  test    eax, eax
0x18005000f  jnz     short loc_180050041
0x180050011  call    cs:__imp_GetLastError
0x180050017  lea     rdx, aFailedToCreate; "Failed to create well known SID for Rem"...
0x18005001e  mov     r8d, eax
0x180050021  mov     ebx, eax
0x180050023  mov     ecx, 2; unsigned __int8
0x180050028  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005002d  test    ebx, ebx
0x18005002f  jle     short loc_18005003A
0x180050031  movzx   ebx, bx
0x180050034  or      ebx, 80070000h
0x18005003a  mov     eax, ebx
0x18005003c  jmp     loc_180050185
0x180050041  mov     [rsp+310h+cchName], 100h
0x180050049  mov     [rsp+310h+var_2D8], 0Fh
0x180050051  mov     [rsp+310h+var_2DC], 0
0x180050059  lea     rax, [rsp+310h+var_2DC]
0x18005005e  mov     [rsp+310h+peUse], rax; peUse
0x180050063  lea     rax, [rsp+310h+var_2D8]
0x180050068  mov     [rsp+310h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18005006d  lea     r9, [rsp+310h+ReferencedDomainName]; ReferencedDomainName
0x180050072  lea     r8, [rsp+310h+cchName]; cchName
0x180050077  lea     rdx, [rbp+210h+Name]; Name
0x18005007b  lea     rcx, [rbp+210h+pSid]; Sid
0x18005007f  call    cs:__imp_LookupAccountSidLocalW
0x180050085  test    eax, eax
0x180050087  jnz     short loc_180050098
0x180050089  call    cs:__imp_GetLastError
0x18005008f  lea     rdx, aFailedToLookUp; "Failed to look up Remote Desktop group "...
0x180050096  jmp     short loc_18005001E
0x180050098  mov     qword ptr [rsp+310h+buf], rbx
0x18005009d  mov     dword ptr [rsp+310h+cchReferencedDomainName], 1; totalentries
0x1800500a5  lea     r9, [rsp+310h+buf]; buf
0x1800500aa  xor     r8d, r8d; level
0x1800500ad  lea     rdx, [rbp+210h+Name]; groupname
0x1800500b1  xor     ecx, ecx; servername
0x1800500b3  call    cs:__imp_NetLocalGroupAddMembers
0x1800500b9  mov     edi, eax
0x1800500bb  test    eax, eax
0x1800500bd  jz      loc_180050183
0x1800500c3  mov     [rsp+310h+hMem], 0
0x1800500cc  lea     rax, [rsp+310h+hMem]
0x1800500d1  mov     [rsp+310h+var_2C8], rax
0x1800500d6  mov     [rsp+310h+StringSid], 0
0x1800500df  mov     [rsp+310h+var_2B8], 1
0x1800500e4  lea     rdx, [rsp+310h+StringSid]; StringSid
0x1800500e9  mov     rcx, rbx; Sid
0x1800500ec  call    cs:__imp_ConvertSidToStringSidW
0x1800500f2  mov     r12d, eax
0x1800500f5  cmp     [rsp+310h+var_2B8], 0
0x1800500fa  jz      short loc_18005012A
0x1800500fc  mov     r15, [rsp+310h+StringSid]
0x180050101  mov     rsi, [rsp+310h+var_2C8]
0x180050106  mov     r14, [rsi]
0x180050109  test    r14, r14
0x18005010c  jz      short loc_180050127
0x18005010e  call    cs:__imp_GetLastError
0x180050114  mov     ebx, eax
0x180050116  mov     rcx, r14; hMem
0x180050119  call    cs:__imp_LocalFree
0x18005011f  mov     ecx, ebx; dwErrCode
0x180050121  call    cs:__imp_SetLastError
0x180050127  mov     [rsi], r15
0x18005012a  test    r12d, r12d
0x18005012d  jnz     short loc_180050149
0x18005012f  call    cs:__imp_GetLastError
0x180050135  mov     r8d, eax
0x180050138  lea     rdx, aFailedToConver_0; "Failed to convert AU SID to string: %#x"
0x18005013f  lea     ecx, [r12+2]; unsigned __int8
0x180050144  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180050149  mov     r9d, edi
0x18005014c  mov     r8, [rsp+310h+hMem]
0x180050151  lea     rdx, aFailedToAddAuS; "Failed to add AU '%s' to Remote Desktop"...
0x180050158  mov     ecx, 2; unsigned __int8
0x18005015d  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180050162  test    edi, edi
0x180050164  jle     short loc_18005016F
0x180050166  movzx   edi, di
0x180050169  or      edi, 80070000h
0x18005016f  mov     rcx, [rsp+310h+hMem]; hMem
0x180050174  test    rcx, rcx
0x180050177  jz      short loc_18005017F
0x180050179  call    cs:__imp_LocalFree
0x18005017f  mov     eax, edi
0x180050181  jmp     short loc_180050185
0x180050183  xor     eax, eax
0x180050185  mov     rcx, [rbp+210h+var_30]
0x18005018c  xor     rcx, rsp; StackCookie
0x18005018f  call    __security_check_cookie
0x180050194  lea     r11, [rsp+310h+var_20]
0x18005019c  mov     rbx, [r11+30h]
0x1800501a0  mov     rsi, [r11+40h]
0x1800501a4  mov     rsp, r11
0x1800501a7  pop     r15
0x1800501a9  pop     r14
0x1800501ab  pop     r12
0x1800501ad  pop     rdi
0x1800501ae  pop     rbp
0x1800501af  retn
```

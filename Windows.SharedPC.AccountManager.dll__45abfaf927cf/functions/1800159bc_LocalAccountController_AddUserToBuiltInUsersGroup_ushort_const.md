# LocalAccountController::AddUserToBuiltInUsersGroup(ushort const *)

- ea: `0x1800159bc`
- end: `0x180015b32`
- name: `?AddUserToBuiltInUsersGroup@LocalAccountController@@AEAAXPEBG@Z`
- size: `374`
- prototype: `void __fastcall(LocalAccountController *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015b40`

## callees

- `0x180003530`
- `0x180003fc0`
- `0x18001138c`
- `0x1800159bc`
- `0x1800198d4`
- `0x1800237f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180015a0e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180015a0e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015aa1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x180015aa1`
- `samcli!NetLocalGroupAddMembers` at `0x180015ae5`
- `samcli!NetLocalGroupAddMembers` at `0x180015ae5`

## string_xrefs

- `0x180015a1f`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180015ab2`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`
- `0x180015afd`: `shellcommon\shell\sharedpc\accountmanager\Common\sharedpclocalaccountcontroller.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LocalAccountController::AddUserToBuiltInUsersGroup(
        LocalAccountController *this,
        const unsigned __int16 *a2)
{
  const char *v3; // r9
  const char *v4; // r9
  DWORD v5; // eax
  int v6; // eax
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE buf[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pSid[544]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v14[8]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v15; // [rsp+290h] [rbp+190h]
  WCHAR Name[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  memset_0(pSid, 0, sizeof(pSid));
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, pSid, &cbSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xFD,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      v3);
  cchName = 256;
  memset_0(Name, 0, 0x202u);
  cchReferencedDomainName = 15;
  peUse = 0;
  *(_OWORD *)v14 = 0;
  v15 = 0;
  if ( !LookupAccountSidW(0, pSid, Name, &cchName, v14, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x105,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      v4);
  *(_QWORD *)buf = a2;
  v5 = NetLocalGroupAddMembers(0, Name, 3u, buf, 1u);
  v6 = NetpApiStatusToNtStatus(v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x10A,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\Common\\sharedpclocalaccountcontroller.h",
      (const char *)(unsigned int)v6,
      ReferencedDomainName);
}

```

## disassembly

```asm
0x1800159bc  mov     [rsp-8+arg_0], rbx
0x1800159c1  push    rbp
0x1800159c2  lea     rbp, [rsp-3C0h]
0x1800159ca  sub     rsp, 4C0h
0x1800159d1  mov     rax, cs:__security_cookie
0x1800159d8  xor     rax, rsp
0x1800159db  mov     [rbp+3C0h+var_10], rax
0x1800159e2  mov     rbx, rdx
0x1800159e5  lea     rcx, [rsp+4C0h+pSid]; void *
0x1800159ea  xor     edx, edx; Val
0x1800159ec  mov     r8d, 220h; Size
0x1800159f2  call    memset_0
0x1800159f7  xor     edx, edx; DomainSid
0x1800159f9  mov     [rsp+4C0h+cbSid], 44h ; 'D'
0x180015a01  lea     r9, [rsp+4C0h+cbSid]; cbSid
0x180015a06  lea     r8, [rsp+4C0h+pSid]; pSid
0x180015a0b  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x180015a0e  call    cs:__imp_CreateWellKnownSid
0x180015a14  test    eax, eax
0x180015a16  jnz     short loc_180015A31
0x180015a18  mov     rcx, [rbp+3C8h]; this
0x180015a1f  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015a26  mov     edx, 0FDh; void *
0x180015a2b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015a31  xor     edx, edx; Val
0x180015a33  mov     [rsp+4C0h+cchName], 100h
0x180015a3b  mov     r8d, 202h; Size
0x180015a41  lea     rcx, [rbp+3C0h+Name]; void *
0x180015a48  call    memset_0
0x180015a4d  xorps   xmm0, xmm0
0x180015a50  mov     [rsp+4C0h+var_478], 0Fh
0x180015a58  lea     rax, [rsp+4C0h+var_47C]
0x180015a5d  mov     [rsp+4C0h+var_47C], 0
0x180015a65  mov     [rsp+4C0h+peUse], rax; peUse
0x180015a6a  lea     r9, [rsp+4C0h+cchName]; cchName
0x180015a6f  lea     rax, [rsp+4C0h+var_478]
0x180015a74  xor     ecx, ecx; lpSystemName
0x180015a76  mov     [rsp+4C0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180015a7b  lea     r8, [rbp+3C0h+Name]; Name
0x180015a82  lea     rax, [rbp+3C0h+var_240]
0x180015a89  lea     rdx, [rsp+4C0h+pSid]; Sid
0x180015a8e  mov     [rsp+4C0h+ReferencedDomainName], rax; ReferencedDomainName
0x180015a93  movups  xmmword ptr [rbp+3C0h+var_240], xmm0
0x180015a9a  movups  [rbp+3C0h+var_230], xmm0
0x180015aa1  call    cs:__imp_LookupAccountSidW
0x180015aa7  test    eax, eax
0x180015aa9  jnz     short loc_180015AC4
0x180015aab  mov     rcx, [rbp+3C8h]; this
0x180015ab2  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015ab9  mov     edx, 105h; void *
0x180015abe  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015ac4  lea     r9, [rsp+4C0h+buf]; buf
0x180015ac9  mov     qword ptr [rsp+4C0h+buf], rbx
0x180015ace  mov     r8d, 3; level
0x180015ad4  mov     dword ptr [rsp+4C0h+ReferencedDomainName], 1; int
0x180015adc  lea     rdx, [rbp+3C0h+Name]; groupname
0x180015ae3  xor     ecx, ecx; servername
0x180015ae5  call    cs:__imp_NetLocalGroupAddMembers
0x180015aeb  mov     ecx, eax
0x180015aed  call    NetpApiStatusToNtStatus
0x180015af2  test    eax, eax
0x180015af4  jns     short loc_180015B12
0x180015af6  mov     rcx, [rbp+3C8h]; this
0x180015afd  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\sharedpc\\accountma"...
0x180015b04  mov     r9d, eax; char *
0x180015b07  mov     edx, 10Ah; void *
0x180015b0c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180015b12  mov     rcx, [rbp+3C0h+var_10]
0x180015b19  xor     rcx, rsp; StackCookie
0x180015b1c  call    __security_check_cookie
0x180015b21  mov     rbx, [rsp+4C0h+arg_0]
0x180015b29  add     rsp, 4C0h
0x180015b30  pop     rbp
0x180015b31  retn
```

# Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)

- ea: `0x1801a59f0`
- end: `0x1801a5d6c`
- name: `?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180158d64`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x1800497c0`
- `0x18004be10`
- `0x18004d970`
- `0x18004f310`
- `0x18004fa00`
- `0x18004fb3c`
- `0x18004fe20`
- `0x18004ff58`
- `0x1801a59f0`
- `0x1801a5d74`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x1801a5aea`
- `ntdll!RtlCreateAcl` at `0x1801a5aea`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5b51`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5bb1`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5c0e`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5c6b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5cc5`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5b51`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5bb1`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5c0e`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5c6b`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801a5cc5`

## string_xrefs

- `0x1801a5b11`: `RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))`
- `0x1801a5b18`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5b7e`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5bdd`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5c3a`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5c97`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5cf1`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801a5bd6`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), System)`
- `0x1801a5b77`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000L) | (0x00100000L) | 0x1FF), TrustedInstaller)`
- `0x1801a5c90`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Users)`
- `0x1801a5c33`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Administrators)`
- `0x1801a5cea`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Lowbox)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(struct _ACL **a1)
{
  struct _SID **v2; // rdx
  int TrustedInstallerSid; // ebx
  int SystemSid; // eax
  struct _SID **v5; // rdx
  struct _SID **v6; // rdx
  struct _SID **v7; // rdx
  struct _ACL *v8; // rbx
  NTSTATUS v9; // edi
  __int128 *v10; // rcx
  __int128 v12; // [rsp+30h] [rbp-D0h] BYREF
  PACL Acl; // [rsp+40h] [rbp-C0h]
  const char *v14; // [rsp+48h] [rbp-B8h]
  PSID v15; // [rsp+50h] [rbp-B0h] BYREF
  PSID v16; // [rsp+58h] [rbp-A8h] BYREF
  PSID v17; // [rsp+60h] [rbp-A0h] BYREF
  PSID v18; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v19[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v20[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v22[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v23[4]; // [rsp+F0h] [rbp-10h] BYREF
  PSID pSid; // [rsp+110h] [rbp+10h] BYREF

  ((void (*)(void))Windows::Auto<_ACL>::Close)();
  pSid = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  TrustedInstallerSid = Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(&pSid);
  if ( TrustedInstallerSid < 0 )
    goto LABEL_25;
  SystemSid = Windows::WCP::Implementation::Rtl::GetSystemSid((Windows::WCP::Implementation::Rtl *)&v15, v2);
  if ( SystemSid < 0
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetAdministratorsSid(
                      (Windows::WCP::Implementation::Rtl *)&v16,
                      v5),
        SystemSid < 0)
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetUsersSid((Windows::WCP::Implementation::Rtl *)&v17, v6),
        SystemSid < 0)
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetLowboxSid((Windows::WCP::Implementation::Rtl *)&v18, v7),
        SystemSid < 0) )
  {
    TrustedInstallerSid = SystemSid;
LABEL_25:
    Windows::Auto<_ACL>::Close(&pSid);
    return (unsigned int)TrustedInstallerSid;
  }
  Acl = 0;
  v12 = 0;
  TrustedInstallerSid = RtlAllocateLBlob(408, &v12);
  if ( TrustedInstallerSid < 0 )
  {
    if ( Acl )
      anonymous_namespace_::OurRtlFreeStringRoutine(Acl);
    goto LABEL_25;
  }
  v8 = Acl;
  v9 = RtlCreateAcl(Acl, 0x198u, 2u);
  if ( v9 < 0 )
  {
    Acl = (PACL)482;
    *(_QWORD *)&v12 = "onecore\\base\\wcp\\library\\security.cpp";
    v14 = "RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))";
    *((_QWORD *)&v12 + 1) = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = &v12;
LABEL_22:
    RtlReportErrorOrigination(v10, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    if ( v8 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v8);
    TrustedInstallerSid = v9;
    goto LABEL_25;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1F01FFu, pSid);
  if ( v9 < 0 )
  {
    v19[2] = 489;
    v19[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v19[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000L) | (0x"
             "00100000L) | 0x1FF), TrustedInstaller)";
    v19[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = (__int128 *)v19;
    goto LABEL_22;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v15);
  if ( v9 < 0 )
  {
    v20[2] = 496;
    v20[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v20[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), System)";
    v20[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = (__int128 *)v20;
    goto LABEL_22;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v16);
  if ( v9 < 0 )
  {
    v21[2] = 503;
    v21[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v21[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), Administrators)";
    v21[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = (__int128 *)v21;
    goto LABEL_22;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v17);
  if ( v9 < 0 )
  {
    v22[2] = 510;
    v22[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v22[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Users)";
    v22[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = (__int128 *)v22;
    goto LABEL_22;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v18);
  if ( v9 < 0 )
  {
    v23[2] = 517;
    v23[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v23[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), Lowbox)";
    v23[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v10 = (__int128 *)v23;
    goto LABEL_22;
  }
  if ( *a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801A5D6BLL);
  }
  *a1 = v8;
  Windows::Auto<_ACL>::Close(&pSid);
  return 0;
}

```

## disassembly

```asm
0x1801a59f0  push    rbp
0x1801a59f2  push    rbx
0x1801a59f3  push    rsi
0x1801a59f4  push    rdi
0x1801a59f5  push    r12
0x1801a59f7  push    r15
0x1801a59f9  lea     rbp, [rsp-28h]
0x1801a59fe  sub     rsp, 128h
0x1801a5a05  mov     rax, cs:__security_cookie
0x1801a5a0c  xor     rax, rsp
0x1801a5a0f  mov     [rbp+50h+var_38], rax
0x1801a5a13  mov     rsi, rcx
0x1801a5a16  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801a5a1b  lea     rcx, [rbp+50h+var_40]
0x1801a5a1f  mov     [rbp+50h+var_40], 0
0x1801a5a27  mov     [rsp+150h+var_100], 0
0x1801a5a30  mov     [rsp+150h+var_F8], 0
0x1801a5a39  mov     [rsp+150h+var_F0], 0
0x1801a5a42  mov     [rsp+150h+var_E8], 0
0x1801a5a4b  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x1801a5a50  mov     ebx, eax
0x1801a5a52  test    eax, eax
0x1801a5a54  js      loc_1801A5D22
0x1801a5a5a  lea     rcx, [rsp+150h+var_100]; this
0x1801a5a5f  call    ?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)
0x1801a5a64  test    eax, eax
0x1801a5a66  jns     short loc_1801A5A6F
0x1801a5a68  mov     ebx, eax
0x1801a5a6a  jmp     loc_1801A5D22
0x1801a5a6f  lea     rcx, [rsp+150h+var_F8]; this
0x1801a5a74  call    ?GetAdministratorsSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetAdministratorsSid(_SID * *)
0x1801a5a79  test    eax, eax
0x1801a5a7b  js      short loc_1801A5A68
0x1801a5a7d  lea     rcx, [rsp+150h+var_F0]; this
0x1801a5a82  call    ?GetUsersSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetUsersSid(_SID * *)
0x1801a5a87  test    eax, eax
0x1801a5a89  js      short loc_1801A5A68
0x1801a5a8b  lea     rcx, [rsp+150h+var_E8]; this
0x1801a5a90  call    ?GetLowboxSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetLowboxSid(_SID * *)
0x1801a5a95  test    eax, eax
0x1801a5a97  js      short loc_1801A5A68
0x1801a5a99  xorps   xmm0, xmm0
0x1801a5a9c  lea     rdx, [rsp+150h+var_120]
0x1801a5aa1  xor     eax, eax
0x1801a5aa3  mov     edi, 198h
0x1801a5aa8  mov     ecx, edi
0x1801a5aaa  mov     [rsp+150h+Acl], rax
0x1801a5aaf  movups  [rsp+150h+var_120], xmm0
0x1801a5ab4  call    RtlAllocateLBlob
0x1801a5ab9  mov     ebx, eax
0x1801a5abb  test    eax, eax
0x1801a5abd  jns     short loc_1801A5AD7
0x1801a5abf  mov     rcx, [rsp+150h+Acl]
0x1801a5ac4  test    rcx, rcx
0x1801a5ac7  jz      loc_1801A5D22
0x1801a5acd  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801a5ad2  jmp     loc_1801A5D22
0x1801a5ad7  mov     rbx, [rsp+150h+Acl]
0x1801a5adc  mov     r15d, 2
0x1801a5ae2  mov     r8d, r15d; AclRevision
0x1801a5ae5  mov     rcx, rbx; Acl
0x1801a5ae8  mov     edx, edi; AclSize
0x1801a5aea  call    cs:__imp_RtlCreateAcl
0x1801a5af1  nop     dword ptr [rax+rax+00h]
0x1801a5af6  mov     edi, eax
0x1801a5af8  test    eax, eax
0x1801a5afa  jns     short loc_1801A5B33
0x1801a5afc  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5b03  mov     [rsp+150h+Acl], 1E2h
0x1801a5b0c  mov     qword ptr [rsp+150h+var_120], rcx
0x1801a5b11  lea     rax, aRtlcreateaclRe; "RtlCreateAcl( reinterpret_cast<PACL>(Da"...
0x1801a5b18  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5b1f  mov     [rsp+150h+var_108], rax
0x1801a5b24  mov     qword ptr [rsp+150h+var_120+8], rcx
0x1801a5b29  lea     rcx, [rsp+150h+var_120]
0x1801a5b2e  jmp     loc_1801A5D04
0x1801a5b33  mov     rax, [rbp+50h+var_40]
0x1801a5b37  mov     r12d, 3
0x1801a5b3d  mov     r8d, r12d; AceFlags
0x1801a5b40  mov     [rsp+150h+pSid], rax; pSid
0x1801a5b45  mov     r9d, 1F01FFh; AccessMask
0x1801a5b4b  mov     edx, r15d; dwAceRevision
0x1801a5b4e  mov     rcx, rbx; pAcl
0x1801a5b51  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801a5b58  nop     dword ptr [rax+rax+00h]
0x1801a5b5d  mov     edi, eax
0x1801a5b5f  test    eax, eax
0x1801a5b61  jns     short loc_1801A5B98
0x1801a5b63  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5b6a  mov     [rbp+50h+var_D0], 1E9h
0x1801a5b72  mov     [rsp+150h+var_E0], rcx
0x1801a5b77  lea     rax, aRtladdaccessal_1; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801a5b7e  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5b85  mov     [rbp+50h+var_C8], rax
0x1801a5b89  mov     [rsp+150h+var_D8], rcx
0x1801a5b8e  lea     rcx, [rsp+150h+var_E0]
0x1801a5b93  jmp     loc_1801A5D04
0x1801a5b98  mov     rax, [rsp+150h+var_100]
0x1801a5b9d  mov     r9d, 1200A9h; AccessMask
0x1801a5ba3  mov     r8d, r12d; AceFlags
0x1801a5ba6  mov     [rsp+150h+pSid], rax; pSid
0x1801a5bab  mov     edx, r15d; dwAceRevision
0x1801a5bae  mov     rcx, rbx; pAcl
0x1801a5bb1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801a5bb8  nop     dword ptr [rax+rax+00h]
0x1801a5bbd  mov     edi, eax
0x1801a5bbf  test    eax, eax
0x1801a5bc1  jns     short loc_1801A5BF5
0x1801a5bc3  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5bca  mov     [rbp+50h+var_B0], 1F0h
0x1801a5bd2  mov     [rbp+50h+var_C0], rcx
0x1801a5bd6  lea     rax, aRtladdaccessal_0; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801a5bdd  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5be4  mov     [rbp+50h+var_A8], rax
0x1801a5be8  mov     [rbp+50h+var_B8], rcx
0x1801a5bec  lea     rcx, [rbp+50h+var_C0]
0x1801a5bf0  jmp     loc_1801A5D04
0x1801a5bf5  mov     rax, [rsp+150h+var_F8]
0x1801a5bfa  mov     r9d, 1200A9h; AccessMask
0x1801a5c00  mov     r8d, r12d; AceFlags
0x1801a5c03  mov     [rsp+150h+pSid], rax; pSid
0x1801a5c08  mov     edx, r15d; dwAceRevision
0x1801a5c0b  mov     rcx, rbx; pAcl
0x1801a5c0e  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801a5c15  nop     dword ptr [rax+rax+00h]
0x1801a5c1a  mov     edi, eax
0x1801a5c1c  test    eax, eax
0x1801a5c1e  jns     short loc_1801A5C52
0x1801a5c20  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5c27  mov     [rbp+50h+var_90], 1F7h
0x1801a5c2f  mov     [rbp+50h+var_A0], rcx
0x1801a5c33  lea     rax, aRtladdaccessal_3; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801a5c3a  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5c41  mov     [rbp+50h+var_88], rax
0x1801a5c45  mov     [rbp+50h+var_98], rcx
0x1801a5c49  lea     rcx, [rbp+50h+var_A0]
0x1801a5c4d  jmp     loc_1801A5D04
0x1801a5c52  mov     rax, [rsp+150h+var_F0]
0x1801a5c57  mov     r9d, 1200A9h; AccessMask
0x1801a5c5d  mov     r8d, r12d; AceFlags
0x1801a5c60  mov     [rsp+150h+pSid], rax; pSid
0x1801a5c65  mov     edx, r15d; dwAceRevision
0x1801a5c68  mov     rcx, rbx; pAcl
0x1801a5c6b  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801a5c72  nop     dword ptr [rax+rax+00h]
0x1801a5c77  mov     edi, eax
0x1801a5c79  test    eax, eax
0x1801a5c7b  jns     short loc_1801A5CAC
0x1801a5c7d  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5c84  mov     [rbp+50h+var_70], 1FEh
0x1801a5c8c  mov     [rbp+50h+var_80], rcx
0x1801a5c90  lea     rax, aRtladdaccessal_2; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801a5c97  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5c9e  mov     [rbp+50h+var_68], rax
0x1801a5ca2  mov     [rbp+50h+var_78], rcx
0x1801a5ca6  lea     rcx, [rbp+50h+var_80]
0x1801a5caa  jmp     short loc_1801A5D04
0x1801a5cac  mov     rax, [rsp+150h+var_E8]
0x1801a5cb1  mov     r9d, 1200A9h; AccessMask
0x1801a5cb7  mov     r8d, r12d; AceFlags
0x1801a5cba  mov     [rsp+150h+pSid], rax; pSid
0x1801a5cbf  mov     edx, r15d; dwAceRevision
0x1801a5cc2  mov     rcx, rbx; pAcl
0x1801a5cc5  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801a5ccc  nop     dword ptr [rax+rax+00h]
0x1801a5cd1  mov     edi, eax
0x1801a5cd3  test    eax, eax
0x1801a5cd5  jns     short loc_1801A5D4A
0x1801a5cd7  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801a5cde  mov     [rbp+50h+var_50], 205h
0x1801a5ce6  mov     [rbp+50h+var_60], rcx
0x1801a5cea  lea     rax, aRtladdaccessal; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801a5cf1  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801a5cf8  mov     [rbp+50h+var_48], rax
0x1801a5cfc  mov     [rbp+50h+var_58], rcx
0x1801a5d00  lea     rcx, [rbp+50h+var_60]
0x1801a5d04  mov     r8d, edi
0x1801a5d07  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801a5d0e  call    RtlReportErrorOrigination
0x1801a5d13  test    rbx, rbx
0x1801a5d16  jz      short loc_1801A5D20
0x1801a5d18  mov     rcx, rbx
0x1801a5d1b  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1801a5d20  mov     ebx, edi
0x1801a5d22  lea     rcx, [rbp+50h+var_40]
0x1801a5d26  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801a5d2b  mov     eax, ebx
0x1801a5d2d  mov     rcx, [rbp+50h+var_38]
0x1801a5d31  xor     rcx, rsp; StackCookie
0x1801a5d34  call    __security_check_cookie
0x1801a5d39  add     rsp, 128h
0x1801a5d40  pop     r15
0x1801a5d42  pop     r12
0x1801a5d44  pop     rdi
0x1801a5d45  pop     rsi
0x1801a5d46  pop     rbx
0x1801a5d47  pop     rbp
0x1801a5d48  retn
0x1801a5d4a  xor     eax, eax
0x1801a5d4c  cmp     [rsi], rax
0x1801a5d4f  jnz     short loc_1801A5D61
0x1801a5d51  lea     rcx, [rbp+50h+var_40]
0x1801a5d55  mov     [rsi], rbx
0x1801a5d58  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801a5d5d  xor     eax, eax
0x1801a5d5f  jmp     short loc_1801A5D2D
0x1801a5d61  mov     ecx, 0C00000E5h; int
0x1801a5d66  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

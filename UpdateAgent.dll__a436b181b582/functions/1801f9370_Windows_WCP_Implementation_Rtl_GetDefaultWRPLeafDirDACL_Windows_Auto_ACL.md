# Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)

- ea: `0x1801f9370`
- end: `0x1801f9786`
- name: `?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801bc224`

## callees

- `0x1800059d0`
- `0x180022940`
- `0x1800692fc`
- `0x1801ea940`
- `0x1801efdc0`
- `0x1801f3840`
- `0x1801f3f30`
- `0x1801f406c`
- `0x1801f4350`
- `0x1801f4488`
- `0x1801f9370`
- `0x1801f978c`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x1801f946a`
- `ntdll!RtlCreateAcl` at `0x1801f946a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f94eb`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f9563`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f95db`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f9653`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f96c8`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f94eb`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f9563`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f95db`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f9653`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1801f96c8`

## string_xrefs

- `0x1801f949d`: `RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))`
- `0x1801f951b`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000L) | (0x00100000L) | 0x1FF), TrustedInstaller)`
- `0x1801f9593`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), System)`
- `0x1801f960b`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Administrators)`
- `0x1801f9683`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Users)`
- `0x1801f9488`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f9508`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f9580`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f95f8`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f9670`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f96e5`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1801f96f8`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Lowbox)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  PACL Acl; // [rsp+40h] [rbp-C0h]
  PSID v13; // [rsp+48h] [rbp-B8h] BYREF
  PSID v14; // [rsp+50h] [rbp-B0h] BYREF
  PSID v15; // [rsp+58h] [rbp-A8h] BYREF
  PSID v16; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v17[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v18[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v19[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v20[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v21[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v22[5]; // [rsp+108h] [rbp+8h] BYREF
  PSID pSid; // [rsp+130h] [rbp+30h] BYREF

  v22[4] = -2;
  ((void (*)(void))Windows::Auto<_ACL>::Close)();
  pSid = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  TrustedInstallerSid = Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(&pSid);
  if ( TrustedInstallerSid < 0 )
    goto LABEL_22;
  SystemSid = Windows::WCP::Implementation::Rtl::GetSystemSid((Windows::WCP::Implementation::Rtl *)&v13, v2);
  if ( SystemSid < 0
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetAdministratorsSid(
                      (Windows::WCP::Implementation::Rtl *)&v14,
                      v5),
        SystemSid < 0)
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetUsersSid((Windows::WCP::Implementation::Rtl *)&v15, v6),
        SystemSid < 0)
    || (SystemSid = Windows::WCP::Implementation::Rtl::GetLowboxSid((Windows::WCP::Implementation::Rtl *)&v16, v7),
        SystemSid < 0) )
  {
    TrustedInstallerSid = SystemSid;
LABEL_22:
    Windows::Auto<_ACL>::Close(&pSid);
    return (unsigned int)TrustedInstallerSid;
  }
  v11 = 0;
  Acl = 0;
  TrustedInstallerSid = RtlAllocateLBlob(408, &v11);
  if ( TrustedInstallerSid < 0 )
  {
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_22;
  }
  v8 = Acl;
  v9 = RtlCreateAcl(Acl, 0x198u, 2u);
  if ( v9 < 0 )
  {
    v17[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v17[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v17[2] = 482;
    v17[3] = "RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))";
    RtlReportErrorOrigination(v17, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
LABEL_21:
    TrustedInstallerSid = v9;
    goto LABEL_22;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1F01FFu, pSid);
  if ( v9 < 0 )
  {
    v18[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v18[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v18[2] = 489;
    v18[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000L) | (0x"
             "00100000L) | 0x1FF), TrustedInstaller)";
    RtlReportErrorOrigination(v18, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_21;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v13);
  if ( v9 < 0 )
  {
    v19[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v19[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v19[2] = 496;
    v19[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), System)";
    RtlReportErrorOrigination(v19, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_21;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v14);
  if ( v9 < 0 )
  {
    v20[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v20[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v20[2] = 503;
    v20[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), Administrators)";
    RtlReportErrorOrigination(v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_21;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v15);
  if ( v9 < 0 )
  {
    v21[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v21[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v21[2] = 510;
    v21[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Users)";
    RtlReportErrorOrigination(v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_21;
  }
  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v16);
  if ( v9 < 0 )
  {
    v22[0] = "onecore\\base\\wcp\\library\\security.cpp";
    v22[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
    v22[2] = 517;
    v22[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ("
             " 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x0010"
             "0000L)), Lowbox)";
    RtlReportErrorOrigination(v22, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v9);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
    goto LABEL_21;
  }
  v11 = 0;
  Acl = 0;
  if ( *a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1801F9785LL);
  }
  *a1 = v8;
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v11);
  Windows::Auto<_ACL>::Close(&pSid);
  return 0;
}

```

## disassembly

```asm
0x1801f9370  push    rbp
0x1801f9372  push    rbx
0x1801f9373  push    rsi
0x1801f9374  push    rdi
0x1801f9375  push    r12
0x1801f9377  push    r15
0x1801f9379  lea     rbp, [rsp-48h]
0x1801f937e  sub     rsp, 148h
0x1801f9385  mov     [rbp+70h+var_48], 0FFFFFFFFFFFFFFFEh
0x1801f938d  mov     rax, cs:__security_cookie
0x1801f9394  xor     rax, rsp
0x1801f9397  mov     [rbp+70h+var_38], rax
0x1801f939b  mov     rsi, rcx
0x1801f939e  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801f93a3  mov     [rbp+70h+var_40], 0
0x1801f93ab  mov     [rsp+170h+var_128], 0
0x1801f93b4  mov     [rsp+170h+var_120], 0
0x1801f93bd  mov     [rsp+170h+var_118], 0
0x1801f93c6  mov     [rsp+170h+var_110], 0
0x1801f93cf  lea     rcx, [rbp+70h+var_40]
0x1801f93d3  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x1801f93d8  mov     ebx, eax
0x1801f93da  test    eax, eax
0x1801f93dc  js      loc_1801F9724
0x1801f93e2  lea     rcx, [rsp+170h+var_128]; this
0x1801f93e7  call    ?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)
0x1801f93ec  test    eax, eax
0x1801f93ee  jns     short loc_1801F93F7
0x1801f93f0  mov     ebx, eax
0x1801f93f2  jmp     loc_1801F9724
0x1801f93f7  lea     rcx, [rsp+170h+var_120]; this
0x1801f93fc  call    ?GetAdministratorsSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetAdministratorsSid(_SID * *)
0x1801f9401  test    eax, eax
0x1801f9403  js      short loc_1801F93F0
0x1801f9405  lea     rcx, [rsp+170h+var_118]; this
0x1801f940a  call    ?GetUsersSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetUsersSid(_SID * *)
0x1801f940f  test    eax, eax
0x1801f9411  js      short loc_1801F93F0
0x1801f9413  lea     rcx, [rsp+170h+var_110]; this
0x1801f9418  call    ?GetLowboxSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetLowboxSid(_SID * *)
0x1801f941d  test    eax, eax
0x1801f941f  js      short loc_1801F93F0
0x1801f9421  xorps   xmm0, xmm0
0x1801f9424  xor     eax, eax
0x1801f9426  movups  [rsp+170h+var_140], xmm0
0x1801f942b  mov     [rsp+170h+Acl], rax
0x1801f9430  lea     rdx, [rsp+170h+var_140]
0x1801f9435  mov     edi, 198h
0x1801f943a  mov     ecx, edi
0x1801f943c  call    RtlAllocateLBlob
0x1801f9441  mov     ebx, eax
0x1801f9443  test    eax, eax
0x1801f9445  jns     short loc_1801F9457
0x1801f9447  lea     rcx, [rsp+170h+var_140]
0x1801f944c  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f9451  nop
0x1801f9452  jmp     loc_1801F9724
0x1801f9457  mov     rbx, [rsp+170h+Acl]
0x1801f945c  mov     r15d, 2
0x1801f9462  mov     r8d, r15d; AclRevision
0x1801f9465  mov     edx, edi; AclSize
0x1801f9467  mov     rcx, rbx; Acl
0x1801f946a  call    cs:__imp_RtlCreateAcl
0x1801f9471  nop     dword ptr [rax+rax+00h]
0x1801f9476  mov     edi, eax
0x1801f9478  test    eax, eax
0x1801f947a  jns     short loc_1801F94CD
0x1801f947c  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f9483  mov     [rsp+170h+var_108], rcx
0x1801f9488  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f948f  mov     [rsp+170h+var_100], rcx
0x1801f9494  mov     [rsp+170h+var_F8], 1E2h
0x1801f949d  lea     rax, aRtlcreateaclRe; "RtlCreateAcl( reinterpret_cast<PACL>(Da"...
0x1801f94a4  mov     [rbp+70h+var_F0], rax
0x1801f94a8  mov     r8d, edi
0x1801f94ab  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f94b2  lea     rcx, [rsp+170h+var_108]
0x1801f94b7  call    RtlReportErrorOrigination
0x1801f94bc  nop
0x1801f94bd  lea     rcx, [rsp+170h+var_140]
0x1801f94c2  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f94c7  nop
0x1801f94c8  jmp     loc_1801F9722
0x1801f94cd  mov     rax, [rbp+70h+var_40]
0x1801f94d1  mov     [rsp+170h+pSid], rax; pSid
0x1801f94d6  mov     r9d, 1F01FFh; AccessMask
0x1801f94dc  mov     r12d, 3
0x1801f94e2  mov     r8d, r12d; AceFlags
0x1801f94e5  mov     edx, r15d; dwAceRevision
0x1801f94e8  mov     rcx, rbx; pAcl
0x1801f94eb  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801f94f2  nop     dword ptr [rax+rax+00h]
0x1801f94f7  mov     edi, eax
0x1801f94f9  test    eax, eax
0x1801f94fb  jns     short loc_1801F954A
0x1801f94fd  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f9504  mov     [rbp+70h+var_E8], rcx
0x1801f9508  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f950f  mov     [rbp+70h+var_E0], rcx
0x1801f9513  mov     [rbp+70h+var_D8], 1E9h
0x1801f951b  lea     rax, aRtladdaccessal_1; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801f9522  mov     [rbp+70h+var_D0], rax
0x1801f9526  mov     r8d, edi
0x1801f9529  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f9530  lea     rcx, [rbp+70h+var_E8]
0x1801f9534  call    RtlReportErrorOrigination
0x1801f9539  nop
0x1801f953a  lea     rcx, [rsp+170h+var_140]
0x1801f953f  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f9544  nop
0x1801f9545  jmp     loc_1801F9722
0x1801f954a  mov     rax, [rsp+170h+var_128]
0x1801f954f  mov     [rsp+170h+pSid], rax; pSid
0x1801f9554  mov     r9d, 1200A9h; AccessMask
0x1801f955a  mov     r8d, r12d; AceFlags
0x1801f955d  mov     edx, r15d; dwAceRevision
0x1801f9560  mov     rcx, rbx; pAcl
0x1801f9563  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801f956a  nop     dword ptr [rax+rax+00h]
0x1801f956f  mov     edi, eax
0x1801f9571  test    eax, eax
0x1801f9573  jns     short loc_1801F95C2
0x1801f9575  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f957c  mov     [rbp+70h+var_C8], rcx
0x1801f9580  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f9587  mov     [rbp+70h+var_C0], rcx
0x1801f958b  mov     [rbp+70h+var_B8], 1F0h
0x1801f9593  lea     rax, aRtladdaccessal_0; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801f959a  mov     [rbp+70h+var_B0], rax
0x1801f959e  mov     r8d, edi
0x1801f95a1  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f95a8  lea     rcx, [rbp+70h+var_C8]
0x1801f95ac  call    RtlReportErrorOrigination
0x1801f95b1  nop
0x1801f95b2  lea     rcx, [rsp+170h+var_140]
0x1801f95b7  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f95bc  nop
0x1801f95bd  jmp     loc_1801F9722
0x1801f95c2  mov     rax, [rsp+170h+var_120]
0x1801f95c7  mov     [rsp+170h+pSid], rax; pSid
0x1801f95cc  mov     r9d, 1200A9h; AccessMask
0x1801f95d2  mov     r8d, r12d; AceFlags
0x1801f95d5  mov     edx, r15d; dwAceRevision
0x1801f95d8  mov     rcx, rbx; pAcl
0x1801f95db  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801f95e2  nop     dword ptr [rax+rax+00h]
0x1801f95e7  mov     edi, eax
0x1801f95e9  test    eax, eax
0x1801f95eb  jns     short loc_1801F963A
0x1801f95ed  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f95f4  mov     [rbp+70h+var_A8], rcx
0x1801f95f8  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f95ff  mov     [rbp+70h+var_A0], rcx
0x1801f9603  mov     [rbp+70h+var_98], 1F7h
0x1801f960b  lea     rax, aRtladdaccessal_3; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801f9612  mov     [rbp+70h+var_90], rax
0x1801f9616  mov     r8d, edi
0x1801f9619  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f9620  lea     rcx, [rbp+70h+var_A8]
0x1801f9624  call    RtlReportErrorOrigination
0x1801f9629  nop
0x1801f962a  lea     rcx, [rsp+170h+var_140]
0x1801f962f  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f9634  nop
0x1801f9635  jmp     loc_1801F9722
0x1801f963a  mov     rax, [rsp+170h+var_118]
0x1801f963f  mov     [rsp+170h+pSid], rax; pSid
0x1801f9644  mov     r9d, 1200A9h; AccessMask
0x1801f964a  mov     r8d, r12d; AceFlags
0x1801f964d  mov     edx, r15d; dwAceRevision
0x1801f9650  mov     rcx, rbx; pAcl
0x1801f9653  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801f965a  nop     dword ptr [rax+rax+00h]
0x1801f965f  mov     edi, eax
0x1801f9661  test    eax, eax
0x1801f9663  jns     short loc_1801F96AF
0x1801f9665  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f966c  mov     [rbp+70h+var_88], rcx
0x1801f9670  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f9677  mov     [rbp+70h+var_80], rcx
0x1801f967b  mov     [rbp+70h+var_78], 1FEh
0x1801f9683  lea     rax, aRtladdaccessal_2; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801f968a  mov     [rbp+70h+var_70], rax
0x1801f968e  mov     r8d, edi
0x1801f9691  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f9698  lea     rcx, [rbp+70h+var_88]
0x1801f969c  call    RtlReportErrorOrigination
0x1801f96a1  nop
0x1801f96a2  lea     rcx, [rsp+170h+var_140]
0x1801f96a7  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f96ac  nop
0x1801f96ad  jmp     short loc_1801F9722
0x1801f96af  mov     rax, [rsp+170h+var_110]
0x1801f96b4  mov     [rsp+170h+pSid], rax; pSid
0x1801f96b9  mov     r9d, 1200A9h; AccessMask
0x1801f96bf  mov     r8d, r12d; AceFlags
0x1801f96c2  mov     edx, r15d; dwAceRevision
0x1801f96c5  mov     rcx, rbx; pAcl
0x1801f96c8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1801f96cf  nop     dword ptr [rax+rax+00h]
0x1801f96d4  mov     edi, eax
0x1801f96d6  test    eax, eax
0x1801f96d8  jns     short loc_1801F9731
0x1801f96da  lea     rcx, a0123456789abcd+10h; "onecore\\base\\wcp\\library\\security.c"...
0x1801f96e1  mov     [rbp+70h+var_68], rcx
0x1801f96e5  lea     rcx, aWindowsWcpImpl_12; "Windows::WCP::Implementation::Rtl::GetD"...
0x1801f96ec  mov     [rbp+70h+var_60], rcx
0x1801f96f0  mov     [rbp+70h+var_58], 205h
0x1801f96f8  lea     rax, aRtladdaccessal; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1801f96ff  mov     [rbp+70h+var_50], rax
0x1801f9703  mov     r8d, edi
0x1801f9706  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f970d  lea     rcx, [rbp+70h+var_68]
0x1801f9711  call    RtlReportErrorOrigination
0x1801f9716  nop
0x1801f9717  lea     rcx, [rsp+170h+var_140]
0x1801f971c  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f9721  nop
0x1801f9722  mov     ebx, edi
0x1801f9724  lea     rcx, [rbp+70h+var_40]
0x1801f9728  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801f972d  mov     eax, ebx
0x1801f972f  jmp     short loc_1801F975E
0x1801f9731  xorps   xmm0, xmm0
0x1801f9734  xor     eax, eax
0x1801f9736  movups  [rsp+170h+var_140], xmm0
0x1801f973b  mov     [rsp+170h+Acl], rax
0x1801f9740  cmp     [rsi], rax
0x1801f9743  jnz     short loc_1801F977B
0x1801f9745  mov     [rsi], rbx
0x1801f9748  lea     rcx, [rsp+170h+var_140]
0x1801f974d  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x1801f9752  nop
0x1801f9753  lea     rcx, [rbp+70h+var_40]
0x1801f9757  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801f975c  xor     eax, eax
0x1801f975e  mov     rcx, [rbp+70h+var_38]
0x1801f9762  xor     rcx, rsp; StackCookie
0x1801f9765  call    __security_check_cookie
0x1801f976a  add     rsp, 148h
0x1801f9771  pop     r15
0x1801f9773  pop     r12
0x1801f9775  pop     rdi
0x1801f9776  pop     rsi
0x1801f9777  pop     rbx
0x1801f9778  pop     rbp
0x1801f9779  retn
0x1801f977b  mov     ecx, 0C00000E5h; int
0x1801f9780  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

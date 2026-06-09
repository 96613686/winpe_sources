# Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(Windows::Auto<_ACL> *)

- ea: `0x1802c5fbc`
- end: `0x1802c632e`
- name: `?GetDefaultWRPLeafDirDACL@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_ACL@@@4@@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180249b08`

## callees

- `0x180019bdc`
- `0x18003ec0c`
- `0x180094db4`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1801168e4`
- `0x1801169d0`
- `0x180116b34`
- `0x180116c20`
- `0x180117004`
- `0x1802c5fbc`
- `0x1802c6334`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x1802c60bd`
- `ntdll!RtlCreateAcl` at `0x1802c60bd`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c612c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c6184`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c61df`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c623a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c6295`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c612c`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c6184`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c61df`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c623a`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1802c6295`

## string_xrefs

- `0x1802c60cd`: `onecore\base\wcp\library\security.cpp`
- `0x1802c613c`: `onecore\base\wcp\library\security.cpp`
- `0x1802c6194`: `onecore\base\wcp\library\security.cpp`
- `0x1802c61ef`: `onecore\base\wcp\library\security.cpp`
- `0x1802c624a`: `onecore\base\wcp\library\security.cpp`
- `0x1802c62a5`: `onecore\base\wcp\library\security.cpp`
- `0x1802c626c`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Users)`
- `0x1802c62c7`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Lowbox)`
- `0x1802c61b6`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), System)`
- `0x1802c6211`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | ( 0x0020 ) | (0x00100000L)), Administrators)`
- `0x1802c60f3`: `RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))`
- `0x1802c60e7`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c6153`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c61ab`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c6206`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c6261`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c62bc`: `Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL`
- `0x1802c615e`: `RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000L) | (0x00100000L) | 0x1FF), TrustedInstaller)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL(__int64 a1)
{
  struct _SID **v2; // rdx
  int TrustedInstallerSid; // ebx
  int SystemSid; // eax
  struct _SID **v5; // rdx
  struct _SID **v6; // rdx
  struct _SID **v7; // rdx
  struct _ACL *v8; // rbx
  NTSTATUS v9; // eax
  _QWORD *v10; // rdx
  __int128 v12; // [rsp+30h] [rbp-D0h] BYREF
  PACL Acl; // [rsp+40h] [rbp-C0h]
  PSID v14; // [rsp+48h] [rbp-B8h] BYREF
  PSID v15; // [rsp+50h] [rbp-B0h] BYREF
  PSID v16; // [rsp+58h] [rbp-A8h] BYREF
  PSID v17; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v18[4]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v19[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v20[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v21[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v22[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v23[4]; // [rsp+108h] [rbp+8h] BYREF
  int v24; // [rsp+128h] [rbp+28h] BYREF
  PSID pSid; // [rsp+130h] [rbp+30h] BYREF

  v24 = 0;
  Windows::Auto<_ACL>::Close(a1);
  pSid = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  TrustedInstallerSid = Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(&pSid);
  if ( TrustedInstallerSid >= 0 )
  {
    SystemSid = Windows::WCP::Implementation::Rtl::GetSystemSid((Windows::WCP::Implementation::Rtl *)&v14, v2);
    if ( SystemSid < 0
      || (SystemSid = Windows::WCP::Implementation::Rtl::GetAdministratorsSid(
                        (Windows::WCP::Implementation::Rtl *)&v15,
                        v5),
          SystemSid < 0)
      || (SystemSid = Windows::WCP::Implementation::Rtl::GetUsersSid((Windows::WCP::Implementation::Rtl *)&v16, v6),
          SystemSid < 0)
      || (SystemSid = Windows::WCP::Implementation::Rtl::GetLowboxSid((Windows::WCP::Implementation::Rtl *)&v17, v7),
          SystemSid < 0) )
    {
      TrustedInstallerSid = SystemSid;
    }
    else
    {
      Acl = 0;
      v12 = 0;
      TrustedInstallerSid = RtlAllocateLBlob(408, &v12);
      if ( TrustedInstallerSid >= 0 )
      {
        v8 = Acl;
        v9 = RtlCreateAcl(Acl, 0x198u, 2u);
        if ( v9 >= 0 )
        {
          v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1F01FFu, pSid);
          if ( v9 >= 0 )
          {
            v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v14);
            if ( v9 >= 0 )
            {
              v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v15);
              if ( v9 >= 0 )
              {
                v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v16);
                if ( v9 >= 0 )
                {
                  v9 = RtlAddAccessAllowedAceEx(v8, 2u, 3u, 0x1200A9u, v17);
                  if ( v9 >= 0 )
                  {
                    Acl = 0;
                    v12 = 0;
                    Windows::Auto<_ACL>::TakeOwnership(a1, v8);
                    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v12);
                    TrustedInstallerSid = 0;
                    goto LABEL_23;
                  }
                  v23[2] = 517;
                  v23[0] = "onecore\\base\\wcp\\library\\security.cpp";
                  v10 = v23;
                  v23[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
                  v23[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x0"
                           "0020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0"
                           "080 ) | ( 0x0020 ) | (0x00100000L)), Lowbox)";
                }
                else
                {
                  v22[2] = 510;
                  v22[0] = "onecore\\base\\wcp\\library\\security.cpp";
                  v10 = v22;
                  v22[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
                  v22[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x0"
                           "0020000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0"
                           "080 ) | ( 0x0020 ) | (0x00100000L)), Users)";
                }
              }
              else
              {
                v21[2] = 503;
                v21[0] = "onecore\\base\\wcp\\library\\security.cpp";
                v10 = v21;
                v21[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
                v21[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x000"
                         "20000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 "
                         ") | ( 0x0020 ) | (0x00100000L)), Administrators)";
              }
            }
            else
            {
              v20[2] = 496;
              v20[0] = "onecore\\base\\wcp\\library\\security.cpp";
              v10 = v20;
              v20[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
              v20[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), (((0x00020"
                       "000L)) | ( 0x0001 ) | ( 0x0080 ) | ( 0x0008 ) | (0x00100000L)) | (((0x00020000L)) | ( 0x0080 ) | "
                       "( 0x0020 ) | (0x00100000L)), System)";
            }
          }
          else
          {
            v19[2] = 489;
            v19[0] = "onecore\\base\\wcp\\library\\security.cpp";
            v10 = v19;
            v19[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
            v19[3] = "RtlAddAccessAllowedAceEx( reinterpret_cast<PACL>(DaclBlob.Buffer), (2), (0x1) | (0x2), ((0x000F0000"
                     "L) | (0x00100000L) | 0x1FF), TrustedInstaller)";
          }
        }
        else
        {
          v18[2] = 482;
          v18[0] = "onecore\\base\\wcp\\library\\security.cpp";
          v10 = v18;
          v18[1] = "Windows::WCP::Implementation::Rtl::GetDefaultWRPLeafDirDACL";
          v18[3] = "RtlCreateAcl( reinterpret_cast<PACL>(DaclBlob.Buffer), cbDacl, (2))";
        }
        TrustedInstallerSid = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                                &v24,
                                v10,
                                (unsigned int)v9);
      }
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v12);
    }
  }
LABEL_23:
  Windows::Auto<_ACL>::Close(&pSid);
  return (unsigned int)TrustedInstallerSid;
}

```

## disassembly

```asm
0x1802c5fbc  mov     [rsp-8+arg_8], rbx
0x1802c5fc1  mov     [rsp-8+arg_10], rdi
0x1802c5fc6  push    rbp
0x1802c5fc7  push    r14
0x1802c5fc9  push    r15
0x1802c5fcb  lea     rbp, [rsp-40h]
0x1802c5fd0  sub     rsp, 140h
0x1802c5fd7  mov     rax, cs:__security_cookie
0x1802c5fde  xor     rax, rsp
0x1802c5fe1  mov     [rbp+50h+var_18], rax
0x1802c5fe5  mov     rdi, rcx
0x1802c5fe8  mov     [rbp+50h+var_28], 0
0x1802c5fef  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1802c5ff4  lea     rcx, [rbp+50h+var_20]
0x1802c5ff8  mov     [rbp+50h+var_20], 0
0x1802c6000  mov     [rsp+150h+var_108], 0
0x1802c6009  mov     [rsp+150h+var_100], 0
0x1802c6012  mov     [rsp+150h+var_F8], 0
0x1802c601b  mov     [rsp+150h+var_F0], 0
0x1802c6024  call    ?GetTrustedInstallerSid@Rtl@Implementation@WCP@Windows@@YAJPEAV?$Auto@U_SID@@@4@@Z; Windows::WCP::Implementation::Rtl::GetTrustedInstallerSid(Windows::Auto<_SID> *)
0x1802c6029  mov     ebx, eax
0x1802c602b  test    eax, eax
0x1802c602d  js      loc_1802C62FD
0x1802c6033  lea     rcx, [rsp+150h+var_108]; this
0x1802c6038  call    ?GetSystemSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetSystemSid(_SID * *)
0x1802c603d  test    eax, eax
0x1802c603f  jns     short loc_1802C6048
0x1802c6041  mov     ebx, eax
0x1802c6043  jmp     loc_1802C62FD
0x1802c6048  lea     rcx, [rsp+150h+var_100]; this
0x1802c604d  call    ?GetAdministratorsSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetAdministratorsSid(_SID * *)
0x1802c6052  test    eax, eax
0x1802c6054  js      short loc_1802C6041
0x1802c6056  lea     rcx, [rsp+150h+var_F8]; this
0x1802c605b  call    ?GetUsersSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetUsersSid(_SID * *)
0x1802c6060  test    eax, eax
0x1802c6062  js      short loc_1802C6041
0x1802c6064  lea     rcx, [rsp+150h+var_F0]; this
0x1802c6069  call    ?GetLowboxSid@Rtl@Implementation@WCP@Windows@@YAJPEAPEAU_SID@@@Z; Windows::WCP::Implementation::Rtl::GetLowboxSid(_SID * *)
0x1802c606e  test    eax, eax
0x1802c6070  js      short loc_1802C6041
0x1802c6072  xorps   xmm0, xmm0
0x1802c6075  lea     rdx, [rsp+150h+var_120]
0x1802c607a  xor     eax, eax
0x1802c607c  mov     r15d, 198h
0x1802c6082  mov     ecx, r15d
0x1802c6085  mov     [rsp+150h+Acl], rax
0x1802c608a  movups  [rsp+150h+var_120], xmm0
0x1802c608f  call    RtlAllocateLBlob
0x1802c6094  mov     ebx, eax
0x1802c6096  test    eax, eax
0x1802c6098  jns     short loc_1802C60A9
0x1802c609a  lea     rcx, [rsp+150h+var_120]
0x1802c609f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c60a4  jmp     loc_1802C62FD
0x1802c60a9  mov     rbx, [rsp+150h+Acl]
0x1802c60ae  mov     r14d, 2
0x1802c60b4  mov     r8d, r14d; AclRevision
0x1802c60b7  mov     rcx, rbx; Acl
0x1802c60ba  mov     edx, r15d; AclSize
0x1802c60bd  call    cs:__imp_RtlCreateAcl
0x1802c60c4  nop     dword ptr [rax+rax+00h]
0x1802c60c9  test    eax, eax
0x1802c60cb  jns     short loc_1802C610E
0x1802c60cd  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c60d4  mov     [rsp+150h+var_D8], 1E2h
0x1802c60dd  mov     [rsp+150h+var_E8], rcx
0x1802c60e2  lea     rdx, [rsp+150h+var_E8]
0x1802c60e7  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c60ee  mov     [rsp+150h+var_E0], rcx
0x1802c60f3  lea     rcx, aRtlcreateaclRe; "RtlCreateAcl( reinterpret_cast<PACL>(Da"...
0x1802c60fa  mov     [rbp+50h+var_D0], rcx
0x1802c60fe  mov     r8d, eax
0x1802c6101  lea     rcx, [rbp+50h+var_28]
0x1802c6105  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c610a  mov     ebx, eax
0x1802c610c  jmp     short loc_1802C609A
0x1802c610e  mov     rax, [rbp+50h+var_20]
0x1802c6112  mov     r15d, 3
0x1802c6118  mov     r8d, r15d; AceFlags
0x1802c611b  mov     [rsp+150h+pSid], rax; pSid
0x1802c6120  mov     r9d, 1F01FFh; AccessMask
0x1802c6126  mov     edx, r14d; dwAceRevision
0x1802c6129  mov     rcx, rbx; pAcl
0x1802c612c  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1802c6133  nop     dword ptr [rax+rax+00h]
0x1802c6138  test    eax, eax
0x1802c613a  jns     short loc_1802C616B
0x1802c613c  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c6143  mov     [rbp+50h+var_B8], 1E9h
0x1802c614b  mov     [rbp+50h+var_C8], rcx
0x1802c614f  lea     rdx, [rbp+50h+var_C8]
0x1802c6153  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c615a  mov     [rbp+50h+var_C0], rcx
0x1802c615e  lea     rcx, aRtladdaccessal_1; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1802c6165  mov     [rbp+50h+var_B0], rcx
0x1802c6169  jmp     short loc_1802C60FE
0x1802c616b  mov     rax, [rsp+150h+var_108]
0x1802c6170  mov     r9d, 1200A9h; AccessMask
0x1802c6176  mov     r8d, r15d; AceFlags
0x1802c6179  mov     [rsp+150h+pSid], rax; pSid
0x1802c617e  mov     edx, r14d; dwAceRevision
0x1802c6181  mov     rcx, rbx; pAcl
0x1802c6184  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1802c618b  nop     dword ptr [rax+rax+00h]
0x1802c6190  test    eax, eax
0x1802c6192  jns     short loc_1802C61C6
0x1802c6194  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c619b  mov     [rbp+50h+var_98], 1F0h
0x1802c61a3  mov     [rbp+50h+var_A8], rcx
0x1802c61a7  lea     rdx, [rbp+50h+var_A8]
0x1802c61ab  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c61b2  mov     [rbp+50h+var_A0], rcx
0x1802c61b6  lea     rcx, aRtladdaccessal_0; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1802c61bd  mov     [rbp+50h+var_90], rcx
0x1802c61c1  jmp     loc_1802C60FE
0x1802c61c6  mov     rax, [rsp+150h+var_100]
0x1802c61cb  mov     r9d, 1200A9h; AccessMask
0x1802c61d1  mov     r8d, r15d; AceFlags
0x1802c61d4  mov     [rsp+150h+pSid], rax; pSid
0x1802c61d9  mov     edx, r14d; dwAceRevision
0x1802c61dc  mov     rcx, rbx; pAcl
0x1802c61df  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1802c61e6  nop     dword ptr [rax+rax+00h]
0x1802c61eb  test    eax, eax
0x1802c61ed  jns     short loc_1802C6221
0x1802c61ef  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c61f6  mov     [rbp+50h+var_78], 1F7h
0x1802c61fe  mov     [rbp+50h+var_88], rcx
0x1802c6202  lea     rdx, [rbp+50h+var_88]
0x1802c6206  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c620d  mov     [rbp+50h+var_80], rcx
0x1802c6211  lea     rcx, aRtladdaccessal_3; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1802c6218  mov     [rbp+50h+var_70], rcx
0x1802c621c  jmp     loc_1802C60FE
0x1802c6221  mov     rax, [rsp+150h+var_F8]
0x1802c6226  mov     r9d, 1200A9h; AccessMask
0x1802c622c  mov     r8d, r15d; AceFlags
0x1802c622f  mov     [rsp+150h+pSid], rax; pSid
0x1802c6234  mov     edx, r14d; dwAceRevision
0x1802c6237  mov     rcx, rbx; pAcl
0x1802c623a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1802c6241  nop     dword ptr [rax+rax+00h]
0x1802c6246  test    eax, eax
0x1802c6248  jns     short loc_1802C627C
0x1802c624a  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c6251  mov     [rbp+50h+var_58], 1FEh
0x1802c6259  mov     [rbp+50h+var_68], rcx
0x1802c625d  lea     rdx, [rbp+50h+var_68]
0x1802c6261  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c6268  mov     [rbp+50h+var_60], rcx
0x1802c626c  lea     rcx, aRtladdaccessal_2; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1802c6273  mov     [rbp+50h+var_50], rcx
0x1802c6277  jmp     loc_1802C60FE
0x1802c627c  mov     rax, [rsp+150h+var_F0]
0x1802c6281  mov     r9d, 1200A9h; AccessMask
0x1802c6287  mov     r8d, r15d; AceFlags
0x1802c628a  mov     [rsp+150h+pSid], rax; pSid
0x1802c628f  mov     edx, r14d; dwAceRevision
0x1802c6292  mov     rcx, rbx; pAcl
0x1802c6295  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1802c629c  nop     dword ptr [rax+rax+00h]
0x1802c62a1  test    eax, eax
0x1802c62a3  jns     short loc_1802C62D7
0x1802c62a5  lea     rcx, aOnecoreBaseWcp_39; "onecore\\base\\wcp\\library\\security.c"...
0x1802c62ac  mov     [rbp+50h+var_38], 205h
0x1802c62b4  mov     [rbp+50h+var_48], rcx
0x1802c62b8  lea     rdx, [rbp+50h+var_48]
0x1802c62bc  lea     rcx, aWindowsWcpImpl_13; "Windows::WCP::Implementation::Rtl::GetD"...
0x1802c62c3  mov     [rbp+50h+var_40], rcx
0x1802c62c7  lea     rcx, aRtladdaccessal; "RtlAddAccessAllowedAceEx( reinterpret_c"...
0x1802c62ce  mov     [rbp+50h+var_30], rcx
0x1802c62d2  jmp     loc_1802C60FE
0x1802c62d7  xorps   xmm0, xmm0
0x1802c62da  xor     eax, eax
0x1802c62dc  mov     rdx, rbx
0x1802c62df  mov     [rsp+150h+Acl], rax
0x1802c62e4  mov     rcx, rdi
0x1802c62e7  movups  [rsp+150h+var_120], xmm0
0x1802c62ec  call    ?TakeOwnership@?$Auto@U_ACL@@@Windows@@QEAAXPEAU_ACL@@@Z; Windows::Auto<_ACL>::TakeOwnership(_ACL *)
0x1802c62f1  lea     rcx, [rsp+150h+var_120]
0x1802c62f6  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c62fb  xor     ebx, ebx
0x1802c62fd  lea     rcx, [rbp+50h+var_20]
0x1802c6301  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1802c6306  mov     eax, ebx
0x1802c6308  mov     rcx, [rbp+50h+var_18]
0x1802c630c  xor     rcx, rsp; StackCookie
0x1802c630f  call    __security_check_cookie
0x1802c6314  lea     r11, [rsp+150h+var_10]
0x1802c631c  mov     rbx, [r11+28h]
0x1802c6320  mov     rdi, [r11+30h]
0x1802c6324  mov     rsp, r11
0x1802c6327  pop     r15
0x1802c6329  pop     r14
0x1802c632b  pop     rbp
0x1802c632c  retn
```

# Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor(_SECURITY_DESCRIPTOR const *,ulong *,Windows::Auto<_SID> *,Windows::Auto<_SID> *,Windows::Auto<_ACL> *,Windows::Auto<_ACL> *,ushort *)

- ea: `0x180116538`
- end: `0x1801168db`
- name: `?DecomposeSecurityDescriptor@Rtl@Implementation@WCP@Windows@@YAJPEBU_SECURITY_DESCRIPTOR@@PEAKPEAV?$Auto@U_SID@@@4@2PEAV?$Auto@U_ACL@@@4@3PEAG@Z`
- size: `931`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180226d7c`

## callees

- `0x180094db4`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x180115cc0`
- `0x1801160a4`
- `0x180116538`

## import_xrefs

- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180116602`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180116602`
- `ntdll!RtlFindAceByType` at `0x180116798`
- `ntdll!RtlFindAceByType` at `0x180116798`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1801166f7`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1801166f7`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801166a7`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801166a7`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x180116657`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x180116657`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180116594`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180116594`

## string_xrefs

- `0x1801165a4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116612`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116667`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801166b7`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116707`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801165b9`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x180116627`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x18011667c`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x1801166cc`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x18011671c`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x1801166d8`: `RtlGetOwnerSecurityDescriptor( HackyTmp, &Owner, &OwnerDefaulted)`
- `0x180116688`: `RtlGetSaclSecurityDescriptor( HackyTmp, &SaclPresent, &Sacl, &SaclDefaulted)`
- `0x180116633`: `RtlGetDaclSecurityDescriptor( HackyTmp, &DaclPresent, &Dacl, &DaclDefaulted)`
- `0x1801165c5`: `RtlGetControlSecurityDescriptor(HackyTmp, &Control, &Revision)`
- `0x180116728`: `RtlGetGroupSecurityDescriptor( HackyTmp, &Group, &GroupDefaulted)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        _DWORD *a2,
        __int64 *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6)
{
  __int64 v6; // r15
  NTSTATUS ControlSecurityDescriptor; // eax
  const char *v11; // rcx
  PSID v13; // rdx
  int v14; // ebx
  __int64 AceByType; // rax
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // r14
  int v19; // edi
  int v20; // eax
  const char *v21; // [rsp+20h] [rbp-A1h] BYREF
  const char *v22; // [rsp+28h] [rbp-99h]
  __int64 v23; // [rsp+30h] [rbp-91h]
  const char *v24; // [rsp+38h] [rbp-89h]
  __int64 v25; // [rsp+40h] [rbp-81h] BYREF
  __int64 v26; // [rsp+48h] [rbp-79h] BYREF
  __int64 v27; // [rsp+50h] [rbp-71h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-69h]
  __int64 *v29; // [rsp+60h] [rbp-61h]
  _DWORD *v30; // [rsp+68h] [rbp-59h]
  PSID Owner; // [rsp+70h] [rbp-51h] BYREF
  PSID Group; // [rsp+78h] [rbp-49h] BYREF
  PACL Sacl; // [rsp+80h] [rbp-41h] BYREF
  PACL Dacl; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int8 DaclPresent; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int8 SaclPresent; // [rsp+91h] [rbp-30h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+92h] [rbp-2Fh] BYREF
  unsigned __int8 SaclDefaulted; // [rsp+93h] [rbp-2Eh] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+94h] [rbp-2Dh] BYREF
  unsigned __int8 GroupDefaulted[3]; // [rsp+95h] [rbp-2Ch] BYREF
  WORD Control; // [rsp+98h] [rbp-29h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-21h] BYREF
  ULONG Revision; // [rsp+A8h] [rbp-19h] BYREF

  v6 = 0;
  v29 = a6;
  v30 = a2;
  v28 = a5;
  LODWORD(v42) = 0;
  Control = 0;
  Revision = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(SecurityDescriptor, &Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v23 = 216;
    v21 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22 = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    v11 = "RtlGetControlSecurityDescriptor(HackyTmp, &Control, &Revision)";
LABEL_3:
    v24 = v11;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v42,
             &v21,
             (unsigned int)ControlSecurityDescriptor);
  }
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v23 = 226;
    v21 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22 = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    v11 = "RtlGetDaclSecurityDescriptor( HackyTmp, &DaclPresent, &Dacl, &DaclDefaulted)";
    goto LABEL_3;
  }
  Sacl = 0;
  SaclPresent = 0;
  SaclDefaulted = 0;
  ControlSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &SaclDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v23 = 236;
    v21 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22 = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    v11 = "RtlGetSaclSecurityDescriptor( HackyTmp, &SaclPresent, &Sacl, &SaclDefaulted)";
    goto LABEL_3;
  }
  Owner = 0;
  OwnerDefaulted = 0;
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v23 = 244;
    v21 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22 = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    v11 = "RtlGetOwnerSecurityDescriptor( HackyTmp, &Owner, &OwnerDefaulted)";
    goto LABEL_3;
  }
  Group = 0;
  GroupDefaulted[0] = 0;
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Group, GroupDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v23 = 252;
    v21 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v22 = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    v11 = "RtlGetGroupSecurityDescriptor( HackyTmp, &Group, &GroupDefaulted)";
    goto LABEL_3;
  }
  v13 = Owner;
  v14 = Owner != 0;
  if ( Group )
    v14 |= 2u;
  if ( DaclPresent )
  {
    if ( (Control & 0x1000) != 0 )
      v14 |= 0x80000004;
    else
      v14 |= 0x20000004u;
  }
  if ( SaclPresent )
  {
    v14 |= (Control & 0x2000) != 0 ? 1073741832 : 268435464;
    AceByType = RtlFindAceByType(Sacl, 17);
    v13 = Owner;
    if ( AceByType )
      v14 |= 0x10u;
  }
  v27 = 0;
  v16 = 0;
  v26 = 0;
  v17 = 0;
  v25 = 0;
  v18 = 0;
  v42 = 0;
  if ( !v13 )
  {
LABEL_24:
    if ( Group )
    {
      v20 = Windows::Auto<_SID>::Assign(&v26);
      if ( v20 < 0 )
      {
LABEL_26:
        v19 = v20;
        goto LABEL_45;
      }
      v17 = v26;
    }
    if ( Dacl )
    {
      v20 = Windows::Auto<_ACL>::Assign(&v25);
      if ( v20 < 0 )
        goto LABEL_26;
      v18 = v25;
    }
    if ( Sacl )
    {
      v20 = Windows::Auto<_ACL>::Assign(&v42);
      if ( v20 < 0 )
        goto LABEL_26;
      v6 = v42;
    }
    if ( v28 )
    {
      v25 = *v28;
      *v28 = v18;
    }
    if ( v29 )
    {
      v42 = *v29;
      *v29 = v6;
    }
    if ( a3 )
    {
      v27 = *a3;
      *a3 = v16;
    }
    if ( a4 )
    {
      v26 = *a4;
      *a4 = v17;
    }
    if ( v30 )
      *v30 = v14;
    v19 = 0;
    goto LABEL_45;
  }
  v19 = Windows::Auto<_SID>::Assign(&v27);
  if ( v19 >= 0 )
  {
    v16 = v27;
    goto LABEL_24;
  }
LABEL_45:
  Windows::Auto<_ACL>::Close(&v42);
  Windows::Auto<_ACL>::Close(&v25);
  Windows::Auto<_ACL>::Close(&v26);
  Windows::Auto<_ACL>::Close(&v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180116538  push    rbp
0x18011653a  push    rbx
0x18011653b  push    rsi
0x18011653c  push    rdi
0x18011653d  push    r12
0x18011653f  push    r13
0x180116541  push    r14
0x180116543  push    r15
0x180116545  lea     rbp, [rsp-7]
0x18011654a  sub     rsp, 0C8h
0x180116551  mov     rax, cs:__security_cookie
0x180116558  xor     rax, rsp
0x18011655b  mov     [rbp+3Fh+var_50], rax
0x18011655f  mov     rax, [rbp+3Fh+arg_28]
0x180116563  xor     r15d, r15d
0x180116566  mov     [rbp+3Fh+var_A0], rax
0x18011656a  mov     r13, r8
0x18011656d  mov     rax, [rbp+3Fh+arg_20]
0x180116571  lea     r8, [rbp+3Fh+Revision]; Revision
0x180116575  mov     [rbp+3Fh+var_98], rdx
0x180116579  mov     r12, r9
0x18011657c  lea     rdx, [rbp+3Fh+Control]; Control
0x180116580  mov     [rbp+3Fh+var_A8], rax
0x180116584  mov     rbx, rcx
0x180116587  mov     dword ptr [rbp+3Fh+var_60], r15d
0x18011658b  mov     [rbp+3Fh+Control], r15w
0x180116590  mov     [rbp+3Fh+Revision], r15d
0x180116594  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18011659b  nop     dword ptr [rax+rax+00h]
0x1801165a0  test    eax, eax
0x1801165a2  jns     short loc_1801165E7
0x1801165a4  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801165ab  mov     [rsp+100h+var_D0], 0D8h
0x1801165b4  mov     [rsp+100h+var_E0], rcx
0x1801165b9  lea     rcx, aWindowsWcpImpl_6; "Windows::WCP::Implementation::Rtl::Deco"...
0x1801165c0  mov     [rsp+100h+var_D8], rcx
0x1801165c5  lea     rcx, aRtlgetcontrols_1; "RtlGetControlSecurityDescriptor(HackyTm"...
0x1801165cc  mov     [rsp+100h+var_C8], rcx
0x1801165d1  lea     rdx, [rsp+100h+var_E0]
0x1801165d6  lea     rcx, [rbp+3Fh+var_60]
0x1801165da  mov     r8d, eax
0x1801165dd  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801165e2  jmp     loc_1801168BA
0x1801165e7  lea     r9, [rbp+3Fh+DaclDefaulted]; DaclDefaulted
0x1801165eb  mov     [rbp+3Fh+Dacl], r15
0x1801165ef  lea     r8, [rbp+3Fh+Dacl]; Dacl
0x1801165f3  mov     [rbp+3Fh+DaclPresent], r15b
0x1801165f7  lea     rdx, [rbp+3Fh+DaclPresent]; DaclPresent
0x1801165fb  mov     [rbp+3Fh+DaclDefaulted], r15b
0x1801165ff  mov     rcx, rbx; SecurityDescriptor
0x180116602  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180116609  nop     dword ptr [rax+rax+00h]
0x18011660e  test    eax, eax
0x180116610  jns     short loc_18011663C
0x180116612  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180116619  mov     [rsp+100h+var_D0], 0E2h
0x180116622  mov     [rsp+100h+var_E0], rcx
0x180116627  lea     rcx, aWindowsWcpImpl_6; "Windows::WCP::Implementation::Rtl::Deco"...
0x18011662e  mov     [rsp+100h+var_D8], rcx
0x180116633  lea     rcx, aRtlgetdaclsecu_1; "RtlGetDaclSecurityDescriptor( HackyTmp,"...
0x18011663a  jmp     short loc_1801165CC
0x18011663c  lea     r9, [rbp+3Fh+SaclDefaulted]; SaclDefaulted
0x180116640  mov     [rbp+3Fh+Sacl], r15
0x180116644  lea     r8, [rbp+3Fh+Sacl]; Sacl
0x180116648  mov     [rbp+3Fh+SaclPresent], r15b
0x18011664c  lea     rdx, [rbp+3Fh+SaclPresent]; SaclPresent
0x180116650  mov     [rbp+3Fh+SaclDefaulted], r15b
0x180116654  mov     rcx, rbx; SecurityDescriptor
0x180116657  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18011665e  nop     dword ptr [rax+rax+00h]
0x180116663  test    eax, eax
0x180116665  jns     short loc_180116694
0x180116667  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18011666e  mov     [rsp+100h+var_D0], 0ECh
0x180116677  mov     [rsp+100h+var_E0], rcx
0x18011667c  lea     rcx, aWindowsWcpImpl_6; "Windows::WCP::Implementation::Rtl::Deco"...
0x180116683  mov     [rsp+100h+var_D8], rcx
0x180116688  lea     rcx, aRtlgetsaclsecu_0; "RtlGetSaclSecurityDescriptor( HackyTmp,"...
0x18011668f  jmp     loc_1801165CC
0x180116694  lea     r8, [rbp+3Fh+OwnerDefaulted]; OwnerDefaulted
0x180116698  mov     [rbp+3Fh+Owner], r15
0x18011669c  lea     rdx, [rbp+3Fh+Owner]; Owner
0x1801166a0  mov     [rbp+3Fh+OwnerDefaulted], r15b
0x1801166a4  mov     rcx, rbx; SecurityDescriptor
0x1801166a7  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1801166ae  nop     dword ptr [rax+rax+00h]
0x1801166b3  test    eax, eax
0x1801166b5  jns     short loc_1801166E4
0x1801166b7  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801166be  mov     [rsp+100h+var_D0], 0F4h
0x1801166c7  mov     [rsp+100h+var_E0], rcx
0x1801166cc  lea     rcx, aWindowsWcpImpl_6; "Windows::WCP::Implementation::Rtl::Deco"...
0x1801166d3  mov     [rsp+100h+var_D8], rcx
0x1801166d8  lea     rcx, aRtlgetownersec_1; "RtlGetOwnerSecurityDescriptor( HackyTmp"...
0x1801166df  jmp     loc_1801165CC
0x1801166e4  lea     r8, [rbp+3Fh+GroupDefaulted]; GroupDefaulted
0x1801166e8  mov     [rbp+3Fh+Group], r15
0x1801166ec  lea     rdx, [rbp+3Fh+Group]; Group
0x1801166f0  mov     [rbp+3Fh+GroupDefaulted], r15b
0x1801166f4  mov     rcx, rbx; SecurityDescriptor
0x1801166f7  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1801166fe  nop     dword ptr [rax+rax+00h]
0x180116703  test    eax, eax
0x180116705  jns     short loc_180116734
0x180116707  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18011670e  mov     [rsp+100h+var_D0], 0FCh
0x180116717  mov     [rsp+100h+var_E0], rcx
0x18011671c  lea     rcx, aWindowsWcpImpl_6; "Windows::WCP::Implementation::Rtl::Deco"...
0x180116723  mov     [rsp+100h+var_D8], rcx
0x180116728  lea     rcx, aRtlgetgroupsec_0; "RtlGetGroupSecurityDescriptor( HackyTmp"...
0x18011672f  jmp     loc_1801165CC
0x180116734  mov     rdx, [rbp+3Fh+Owner]
0x180116738  mov     ebx, r15d
0x18011673b  test    rdx, rdx
0x18011673e  mov     eax, 1
0x180116743  cmovnz  ebx, eax
0x180116746  cmp     [rbp+3Fh+Group], r15
0x18011674a  jz      short loc_18011674F
0x18011674c  or      ebx, 2
0x18011674f  movzx   eax, [rbp+3Fh+Control]
0x180116753  cmp     [rbp+3Fh+DaclPresent], r15b
0x180116757  jz      short loc_18011676E
0x180116759  bt      ax, 0Ch
0x18011675e  jnb     short loc_180116768
0x180116760  or      ebx, 80000004h
0x180116766  jmp     short loc_18011676E
0x180116768  or      ebx, 20000004h
0x18011676e  cmp     [rbp+3Fh+SaclPresent], r15b
0x180116772  jz      short loc_1801167B0
0x180116774  mov     ecx, 2000h
0x180116779  and     ax, cx
0x18011677c  mov     rcx, [rbp+3Fh+Sacl]
0x180116780  neg     ax
0x180116783  sbb     eax, eax
0x180116785  xor     r8d, r8d
0x180116788  and     eax, 30000000h
0x18011678d  add     eax, 10000008h
0x180116792  or      ebx, eax
0x180116794  lea     edx, [r8+11h]
0x180116798  call    cs:__imp_RtlFindAceByType
0x18011679f  nop     dword ptr [rax+rax+00h]
0x1801167a4  mov     rdx, [rbp+3Fh+Owner]
0x1801167a8  test    rax, rax
0x1801167ab  jz      short loc_1801167B0
0x1801167ad  or      ebx, 10h
0x1801167b0  mov     [rbp+3Fh+var_B0], r15
0x1801167b4  mov     rdi, r15
0x1801167b7  mov     [rbp+3Fh+var_B8], r15
0x1801167bb  mov     rsi, r15
0x1801167be  mov     [rsp+100h+var_C0], r15
0x1801167c3  mov     r14, r15
0x1801167c6  mov     [rbp+3Fh+var_60], r15
0x1801167ca  test    rdx, rdx
0x1801167cd  jz      short loc_1801167E6
0x1801167cf  lea     rcx, [rbp+3Fh+var_B0]
0x1801167d3  call    ?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z; Windows::Auto<_SID>::Assign(_SID const *)
0x1801167d8  mov     edi, eax
0x1801167da  test    eax, eax
0x1801167dc  js      loc_180116893
0x1801167e2  mov     rdi, [rbp+3Fh+var_B0]
0x1801167e6  mov     rdx, [rbp+3Fh+Group]
0x1801167ea  test    rdx, rdx
0x1801167ed  jz      short loc_180116807
0x1801167ef  lea     rcx, [rbp+3Fh+var_B8]
0x1801167f3  call    ?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z; Windows::Auto<_SID>::Assign(_SID const *)
0x1801167f8  test    eax, eax
0x1801167fa  jns     short loc_180116803
0x1801167fc  mov     edi, eax
0x1801167fe  jmp     loc_180116893
0x180116803  mov     rsi, [rbp+3Fh+var_B8]
0x180116807  mov     rdx, [rbp+3Fh+Dacl]
0x18011680b  test    rdx, rdx
0x18011680e  jz      short loc_180116823
0x180116810  lea     rcx, [rsp+100h+var_C0]
0x180116815  call    ?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z; Windows::Auto<_ACL>::Assign(_ACL const *)
0x18011681a  test    eax, eax
0x18011681c  js      short loc_1801167FC
0x18011681e  mov     r14, [rsp+100h+var_C0]
0x180116823  mov     rdx, [rbp+3Fh+Sacl]
0x180116827  test    rdx, rdx
0x18011682a  jz      short loc_18011683D
0x18011682c  lea     rcx, [rbp+3Fh+var_60]
0x180116830  call    ?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z; Windows::Auto<_ACL>::Assign(_ACL const *)
0x180116835  test    eax, eax
0x180116837  js      short loc_1801167FC
0x180116839  mov     r15, [rbp+3Fh+var_60]
0x18011683d  mov     rcx, [rbp+3Fh+var_A8]
0x180116841  test    rcx, rcx
0x180116844  jz      short loc_180116851
0x180116846  mov     rax, [rcx]
0x180116849  mov     [rsp+100h+var_C0], rax
0x18011684e  mov     [rcx], r14
0x180116851  mov     rcx, [rbp+3Fh+var_A0]
0x180116855  test    rcx, rcx
0x180116858  jz      short loc_180116864
0x18011685a  mov     rax, [rcx]
0x18011685d  mov     [rbp+3Fh+var_60], rax
0x180116861  mov     [rcx], r15
0x180116864  test    r13, r13
0x180116867  jz      short loc_180116875
0x180116869  mov     rax, [r13+0]
0x18011686d  mov     [rbp+3Fh+var_B0], rax
0x180116871  mov     [r13+0], rdi
0x180116875  test    r12, r12
0x180116878  jz      short loc_180116886
0x18011687a  mov     rax, [r12]
0x18011687e  mov     [rbp+3Fh+var_B8], rax
0x180116882  mov     [r12], rsi
0x180116886  mov     rax, [rbp+3Fh+var_98]
0x18011688a  test    rax, rax
0x18011688d  jz      short loc_180116891
0x18011688f  mov     [rax], ebx
0x180116891  xor     edi, edi
0x180116893  lea     rcx, [rbp+3Fh+var_60]
0x180116897  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18011689c  lea     rcx, [rsp+100h+var_C0]
0x1801168a1  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801168a6  lea     rcx, [rbp+3Fh+var_B8]
0x1801168aa  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801168af  lea     rcx, [rbp+3Fh+var_B0]
0x1801168b3  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x1801168b8  mov     eax, edi
0x1801168ba  mov     rcx, [rbp+3Fh+var_50]
0x1801168be  xor     rcx, rsp; StackCookie
0x1801168c1  call    __security_check_cookie
0x1801168c6  add     rsp, 0C8h
0x1801168cd  pop     r15
0x1801168cf  pop     r14
0x1801168d1  pop     r13
0x1801168d3  pop     r12
0x1801168d5  pop     rdi
0x1801168d6  pop     rsi
0x1801168d7  pop     rbx
0x1801168d8  pop     rbp
0x1801168d9  retn
```

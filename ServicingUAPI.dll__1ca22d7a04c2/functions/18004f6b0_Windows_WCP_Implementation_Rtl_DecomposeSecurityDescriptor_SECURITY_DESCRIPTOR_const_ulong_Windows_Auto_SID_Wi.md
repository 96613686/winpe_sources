# Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor(_SECURITY_DESCRIPTOR const *,ulong *,Windows::Auto<_SID> *,Windows::Auto<_SID> *,Windows::Auto<_ACL> *,Windows::Auto<_ACL> *,ushort *)

- ea: `0x18004f6b0`
- end: `0x18004f9f8`
- name: `?DecomposeSecurityDescriptor@Rtl@Implementation@WCP@Windows@@YAJPEBU_SECURITY_DESCRIPTOR@@PEAKPEAV?$Auto@U_SID@@@4@2PEAV?$Auto@U_ACL@@@4@3PEAG@Z`
- size: `840`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18013131c`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x18004eb28`
- `0x18004ef0c`
- `0x18004f310`
- `0x18004f6b0`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18004f82f`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18004f82f`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004f77c`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18004f77c`
- `ntdll!RtlFindAceByType` at `0x18004f8ba`
- `ntdll!RtlFindAceByType` at `0x18004f8ba`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18004f7f5`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18004f7f5`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18004f7bb`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18004f7bb`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18004f708`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18004f708`

## string_xrefs

- `0x18004f72a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f741`: `Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor`
- `0x18004f723`: `RtlGetControlSecurityDescriptor(HackyTmp, &Control, &Revision)`
- `0x18004f810`: `RtlGetOwnerSecurityDescriptor( HackyTmp, &Owner, &OwnerDefaulted)`
- `0x18004f84a`: `RtlGetGroupSecurityDescriptor( HackyTmp, &Group, &GroupDefaulted)`
- `0x18004f797`: `RtlGetDaclSecurityDescriptor( HackyTmp, &DaclPresent, &Dacl, &DaclDefaulted)`
- `0x18004f7d6`: `RtlGetSaclSecurityDescriptor( HackyTmp, &SaclPresent, &Sacl, &SaclDefaulted)`

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
  __int64 v7; // r15
  NTSTATUS ControlSecurityDescriptor; // ebx
  const char *v11; // rax
  PSID v13; // rdx
  int v14; // ebx
  __int64 AceByType; // rax
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // r14
  int v19; // edi
  int v20; // eax
  _QWORD v21[2]; // [rsp+20h] [rbp-91h] BYREF
  __int64 v22; // [rsp+30h] [rbp-81h]
  const char *v23; // [rsp+38h] [rbp-79h]
  __int64 v24; // [rsp+40h] [rbp-71h] BYREF
  __int64 v25; // [rsp+48h] [rbp-69h] BYREF
  __int64 v26; // [rsp+50h] [rbp-61h] BYREF
  __int64 v27; // [rsp+58h] [rbp-59h] BYREF
  __int64 *v28; // [rsp+60h] [rbp-51h]
  __int64 *v29; // [rsp+68h] [rbp-49h]
  _DWORD *v30; // [rsp+70h] [rbp-41h]
  PSID Owner; // [rsp+78h] [rbp-39h] BYREF
  PSID Group; // [rsp+80h] [rbp-31h] BYREF
  PACL Sacl; // [rsp+88h] [rbp-29h] BYREF
  PACL Dacl; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int8 DaclPresent; // [rsp+98h] [rbp-19h] BYREF
  unsigned __int8 SaclPresent; // [rsp+99h] [rbp-18h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+9Ah] [rbp-17h] BYREF
  unsigned __int8 SaclDefaulted; // [rsp+9Bh] [rbp-16h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+9Ch] [rbp-15h] BYREF
  unsigned __int8 GroupDefaulted[3]; // [rsp+9Dh] [rbp-14h] BYREF
  WORD Control[2]; // [rsp+A0h] [rbp-11h] BYREF
  ULONG Revision; // [rsp+A4h] [rbp-Dh] BYREF

  v29 = a6;
  v7 = 0;
  v30 = a2;
  v28 = a5;
  Control[0] = 0;
  Revision = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(SecurityDescriptor, Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v22 = 216;
    v11 = "RtlGetControlSecurityDescriptor(HackyTmp, &Control, &Revision)";
LABEL_3:
    v23 = v11;
    v21[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v21[1] = "Windows::WCP::Implementation::Rtl::DecomposeSecurityDescriptor";
    RtlReportErrorOrigination(v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  Dacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v22 = 226;
    v11 = "RtlGetDaclSecurityDescriptor( HackyTmp, &DaclPresent, &Dacl, &DaclDefaulted)";
    goto LABEL_3;
  }
  Sacl = 0;
  SaclPresent = 0;
  SaclDefaulted = 0;
  ControlSecurityDescriptor = RtlGetSaclSecurityDescriptor(SecurityDescriptor, &SaclPresent, &Sacl, &SaclDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v22 = 236;
    v11 = "RtlGetSaclSecurityDescriptor( HackyTmp, &SaclPresent, &Sacl, &SaclDefaulted)";
    goto LABEL_3;
  }
  Owner = 0;
  OwnerDefaulted = 0;
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v22 = 244;
    v11 = "RtlGetOwnerSecurityDescriptor( HackyTmp, &Owner, &OwnerDefaulted)";
    goto LABEL_3;
  }
  Group = 0;
  GroupDefaulted[0] = 0;
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Group, GroupDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v22 = 252;
    v11 = "RtlGetGroupSecurityDescriptor( HackyTmp, &Group, &GroupDefaulted)";
    goto LABEL_3;
  }
  v13 = Owner;
  v14 = Owner != 0;
  if ( Group )
    v14 |= 2u;
  if ( DaclPresent )
  {
    if ( (Control[0] & 0x1000) != 0 )
      v14 |= 0x80000004;
    else
      v14 |= 0x20000004u;
  }
  if ( SaclPresent )
  {
    v14 |= (Control[0] & 0x2000) != 0 ? 1073741832 : 268435464;
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
  v24 = 0;
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
      v20 = Windows::Auto<_ACL>::Assign(&v24);
      if ( v20 < 0 )
        goto LABEL_26;
      v7 = v24;
    }
    if ( v28 )
    {
      v25 = *v28;
      *v28 = v18;
    }
    if ( v29 )
    {
      v24 = *v29;
      *v29 = v7;
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
  Windows::Auto<_ACL>::Close(&v24);
  Windows::Auto<_ACL>::Close(&v25);
  Windows::Auto<_ACL>::Close(&v26);
  Windows::Auto<_ACL>::Close(&v27);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18004f6b0  push    rbp
0x18004f6b2  push    rbx
0x18004f6b3  push    rsi
0x18004f6b4  push    rdi
0x18004f6b5  push    r12
0x18004f6b7  push    r13
0x18004f6b9  push    r14
0x18004f6bb  push    r15
0x18004f6bd  lea     rbp, [rsp-7]
0x18004f6c2  sub     rsp, 0B8h
0x18004f6c9  mov     rax, cs:__security_cookie
0x18004f6d0  xor     rax, rsp
0x18004f6d3  mov     [rbp+3Fh+var_48], rax
0x18004f6d7  mov     rax, [rbp+3Fh+arg_28]
0x18004f6db  mov     r13, r8
0x18004f6de  mov     [rbp+3Fh+var_88], rax
0x18004f6e2  lea     r8, [rbp+3Fh+Revision]; Revision
0x18004f6e6  mov     rax, [rbp+3Fh+arg_20]
0x18004f6ea  xor     r15d, r15d
0x18004f6ed  mov     [rbp+3Fh+var_80], rdx
0x18004f6f1  mov     r12, r9
0x18004f6f4  lea     rdx, [rbp+3Fh+Control]; Control
0x18004f6f8  mov     [rbp+3Fh+var_90], rax
0x18004f6fc  mov     rdi, rcx
0x18004f6ff  mov     [rbp+3Fh+Control], r15w
0x18004f704  mov     [rbp+3Fh+Revision], r15d
0x18004f708  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18004f70f  nop     dword ptr [rax+rax+00h]
0x18004f714  mov     ebx, eax
0x18004f716  test    eax, eax
0x18004f718  jns     short loc_18004F761
0x18004f71a  mov     [rsp+0F0h+var_C0], 0D8h
0x18004f723  lea     rax, aRtlgetcontrols_0; "RtlGetControlSecurityDescriptor(HackyTm"...
0x18004f72a  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f731  mov     [rbp+3Fh+var_B8], rax
0x18004f735  mov     [rsp+0F0h+var_D0], rcx
0x18004f73a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f741  lea     rcx, aWindowsWcpImpl_5; "Windows::WCP::Implementation::Rtl::Deco"...
0x18004f748  mov     r8d, ebx
0x18004f74b  mov     [rsp+0F0h+var_C8], rcx
0x18004f750  lea     rcx, [rsp+0F0h+var_D0]
0x18004f755  call    RtlReportErrorOrigination
0x18004f75a  mov     eax, ebx
0x18004f75c  jmp     loc_18004F9D7
0x18004f761  lea     r9, [rbp+3Fh+DaclDefaulted]; DaclDefaulted
0x18004f765  mov     [rbp+3Fh+Dacl], r15
0x18004f769  lea     r8, [rbp+3Fh+Dacl]; Dacl
0x18004f76d  mov     [rbp+3Fh+DaclPresent], r15b
0x18004f771  lea     rdx, [rbp+3Fh+DaclPresent]; DaclPresent
0x18004f775  mov     [rbp+3Fh+DaclDefaulted], r15b
0x18004f779  mov     rcx, rdi; SecurityDescriptor
0x18004f77c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18004f783  nop     dword ptr [rax+rax+00h]
0x18004f788  mov     ebx, eax
0x18004f78a  test    eax, eax
0x18004f78c  jns     short loc_18004F7A0
0x18004f78e  mov     [rsp+0F0h+var_C0], 0E2h
0x18004f797  lea     rax, aRtlgetdaclsecu_0; "RtlGetDaclSecurityDescriptor( HackyTmp,"...
0x18004f79e  jmp     short loc_18004F72A
0x18004f7a0  lea     r9, [rbp+3Fh+SaclDefaulted]; SaclDefaulted
0x18004f7a4  mov     [rbp+3Fh+Sacl], r15
0x18004f7a8  lea     r8, [rbp+3Fh+Sacl]; Sacl
0x18004f7ac  mov     [rbp+3Fh+SaclPresent], r15b
0x18004f7b0  lea     rdx, [rbp+3Fh+SaclPresent]; SaclPresent
0x18004f7b4  mov     [rbp+3Fh+SaclDefaulted], r15b
0x18004f7b8  mov     rcx, rdi; SecurityDescriptor
0x18004f7bb  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18004f7c2  nop     dword ptr [rax+rax+00h]
0x18004f7c7  mov     ebx, eax
0x18004f7c9  test    eax, eax
0x18004f7cb  jns     short loc_18004F7E2
0x18004f7cd  mov     [rsp+0F0h+var_C0], 0ECh
0x18004f7d6  lea     rax, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor( HackyTmp,"...
0x18004f7dd  jmp     loc_18004F72A
0x18004f7e2  lea     r8, [rbp+3Fh+OwnerDefaulted]; OwnerDefaulted
0x18004f7e6  mov     [rbp+3Fh+Owner], r15
0x18004f7ea  lea     rdx, [rbp+3Fh+Owner]; Owner
0x18004f7ee  mov     [rbp+3Fh+OwnerDefaulted], r15b
0x18004f7f2  mov     rcx, rdi; SecurityDescriptor
0x18004f7f5  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18004f7fc  nop     dword ptr [rax+rax+00h]
0x18004f801  mov     ebx, eax
0x18004f803  test    eax, eax
0x18004f805  jns     short loc_18004F81C
0x18004f807  mov     [rsp+0F0h+var_C0], 0F4h
0x18004f810  lea     rax, aRtlgetownersec_0; "RtlGetOwnerSecurityDescriptor( HackyTmp"...
0x18004f817  jmp     loc_18004F72A
0x18004f81c  lea     r8, [rbp+3Fh+GroupDefaulted]; GroupDefaulted
0x18004f820  mov     [rbp+3Fh+Group], r15
0x18004f824  lea     rdx, [rbp+3Fh+Group]; Group
0x18004f828  mov     [rbp+3Fh+GroupDefaulted], r15b
0x18004f82c  mov     rcx, rdi; SecurityDescriptor
0x18004f82f  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18004f836  nop     dword ptr [rax+rax+00h]
0x18004f83b  mov     ebx, eax
0x18004f83d  test    eax, eax
0x18004f83f  jns     short loc_18004F856
0x18004f841  mov     [rsp+0F0h+var_C0], 0FCh
0x18004f84a  lea     rax, aRtlgetgroupsec_0; "RtlGetGroupSecurityDescriptor( HackyTmp"...
0x18004f851  jmp     loc_18004F72A
0x18004f856  mov     rdx, [rbp+3Fh+Owner]
0x18004f85a  mov     ebx, r15d
0x18004f85d  test    rdx, rdx
0x18004f860  mov     eax, 1
0x18004f865  cmovnz  ebx, eax
0x18004f868  cmp     [rbp+3Fh+Group], r15
0x18004f86c  jz      short loc_18004F871
0x18004f86e  or      ebx, 2
0x18004f871  movzx   eax, [rbp+3Fh+Control]
0x18004f875  cmp     [rbp+3Fh+DaclPresent], r15b
0x18004f879  jz      short loc_18004F890
0x18004f87b  bt      ax, 0Ch
0x18004f880  jnb     short loc_18004F88A
0x18004f882  or      ebx, 80000004h
0x18004f888  jmp     short loc_18004F890
0x18004f88a  or      ebx, 20000004h
0x18004f890  cmp     [rbp+3Fh+SaclPresent], r15b
0x18004f894  jz      short loc_18004F8D2
0x18004f896  mov     ecx, 2000h
0x18004f89b  and     ax, cx
0x18004f89e  mov     rcx, [rbp+3Fh+Sacl]
0x18004f8a2  neg     ax
0x18004f8a5  sbb     eax, eax
0x18004f8a7  xor     r8d, r8d
0x18004f8aa  and     eax, 30000000h
0x18004f8af  add     eax, 10000008h
0x18004f8b4  or      ebx, eax
0x18004f8b6  lea     edx, [r8+11h]
0x18004f8ba  call    cs:__imp_RtlFindAceByType
0x18004f8c1  nop     dword ptr [rax+rax+00h]
0x18004f8c6  mov     rdx, [rbp+3Fh+Owner]
0x18004f8ca  test    rax, rax
0x18004f8cd  jz      short loc_18004F8D2
0x18004f8cf  or      ebx, 10h
0x18004f8d2  mov     [rbp+3Fh+var_98], r15
0x18004f8d6  mov     rdi, r15
0x18004f8d9  mov     [rbp+3Fh+var_A0], r15
0x18004f8dd  mov     rsi, r15
0x18004f8e0  mov     [rbp+3Fh+var_A8], r15
0x18004f8e4  mov     r14, r15
0x18004f8e7  mov     [rbp+3Fh+var_B0], r15
0x18004f8eb  test    rdx, rdx
0x18004f8ee  jz      short loc_18004F907
0x18004f8f0  lea     rcx, [rbp+3Fh+var_98]
0x18004f8f4  call    ?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z; Windows::Auto<_SID>::Assign(_SID const *)
0x18004f8f9  mov     edi, eax
0x18004f8fb  test    eax, eax
0x18004f8fd  js      loc_18004F9B1
0x18004f903  mov     rdi, [rbp+3Fh+var_98]
0x18004f907  mov     rdx, [rbp+3Fh+Group]
0x18004f90b  test    rdx, rdx
0x18004f90e  jz      short loc_18004F928
0x18004f910  lea     rcx, [rbp+3Fh+var_A0]
0x18004f914  call    ?Assign@?$Auto@U_SID@@@Windows@@QEAAJPEBU_SID@@@Z; Windows::Auto<_SID>::Assign(_SID const *)
0x18004f919  test    eax, eax
0x18004f91b  jns     short loc_18004F924
0x18004f91d  mov     edi, eax
0x18004f91f  jmp     loc_18004F9B1
0x18004f924  mov     rsi, [rbp+3Fh+var_A0]
0x18004f928  mov     rdx, [rbp+3Fh+Dacl]
0x18004f92c  test    rdx, rdx
0x18004f92f  jz      short loc_18004F942
0x18004f931  lea     rcx, [rbp+3Fh+var_A8]
0x18004f935  call    ?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z; Windows::Auto<_ACL>::Assign(_ACL const *)
0x18004f93a  test    eax, eax
0x18004f93c  js      short loc_18004F91D
0x18004f93e  mov     r14, [rbp+3Fh+var_A8]
0x18004f942  mov     rdx, [rbp+3Fh+Sacl]
0x18004f946  test    rdx, rdx
0x18004f949  jz      short loc_18004F95C
0x18004f94b  lea     rcx, [rbp+3Fh+var_B0]
0x18004f94f  call    ?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z; Windows::Auto<_ACL>::Assign(_ACL const *)
0x18004f954  test    eax, eax
0x18004f956  js      short loc_18004F91D
0x18004f958  mov     r15, [rbp+3Fh+var_B0]
0x18004f95c  mov     rcx, [rbp+3Fh+var_90]
0x18004f960  test    rcx, rcx
0x18004f963  jz      short loc_18004F96F
0x18004f965  mov     rax, [rcx]
0x18004f968  mov     [rbp+3Fh+var_A8], rax
0x18004f96c  mov     [rcx], r14
0x18004f96f  mov     rcx, [rbp+3Fh+var_88]
0x18004f973  test    rcx, rcx
0x18004f976  jz      short loc_18004F982
0x18004f978  mov     rax, [rcx]
0x18004f97b  mov     [rbp+3Fh+var_B0], rax
0x18004f97f  mov     [rcx], r15
0x18004f982  test    r13, r13
0x18004f985  jz      short loc_18004F993
0x18004f987  mov     rax, [r13+0]
0x18004f98b  mov     [rbp+3Fh+var_98], rax
0x18004f98f  mov     [r13+0], rdi
0x18004f993  test    r12, r12
0x18004f996  jz      short loc_18004F9A4
0x18004f998  mov     rax, [r12]
0x18004f99c  mov     [rbp+3Fh+var_A0], rax
0x18004f9a0  mov     [r12], rsi
0x18004f9a4  mov     rax, [rbp+3Fh+var_80]
0x18004f9a8  test    rax, rax
0x18004f9ab  jz      short loc_18004F9AF
0x18004f9ad  mov     [rax], ebx
0x18004f9af  xor     edi, edi
0x18004f9b1  lea     rcx, [rbp+3Fh+var_B0]
0x18004f9b5  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18004f9ba  lea     rcx, [rbp+3Fh+var_A8]
0x18004f9be  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18004f9c3  lea     rcx, [rbp+3Fh+var_A0]
0x18004f9c7  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18004f9cc  lea     rcx, [rbp+3Fh+var_98]
0x18004f9d0  call    ?Close@?$Auto@U_ACL@@@Windows@@QEAAXXZ; Windows::Auto<_ACL>::Close(void)
0x18004f9d5  mov     eax, edi
0x18004f9d7  mov     rcx, [rbp+3Fh+var_48]
0x18004f9db  xor     rcx, rsp; StackCookie
0x18004f9de  call    __security_check_cookie
0x18004f9e3  add     rsp, 0B8h
0x18004f9ea  pop     r15
0x18004f9ec  pop     r14
0x18004f9ee  pop     r13
0x18004f9f0  pop     r12
0x18004f9f2  pop     rdi
0x18004f9f3  pop     rsi
0x18004f9f4  pop     rbx
0x18004f9f5  pop     rbp
0x18004f9f6  retn
```

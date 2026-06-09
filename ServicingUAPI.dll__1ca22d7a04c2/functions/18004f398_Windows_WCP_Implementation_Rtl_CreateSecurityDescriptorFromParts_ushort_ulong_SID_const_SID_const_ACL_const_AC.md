# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x18004f398`
- end: `0x18004f6a9`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `785`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004fcf0`
- `0x180132ab4`
- `0x1801a2d90`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x18004ecdc`
- `0x18004f350`
- `0x18004f398`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x18004f3f1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18004f3f1`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18004f48d`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18004f48d`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18004f4dd`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18004f5a1`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18004f4dd`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18004f5a1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004f52a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004f52a`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004f455`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18004f455`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18004f600`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18004f600`

## string_xrefs

- `0x18004f412`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f4ef`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f5b3`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f612`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18004f472`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x18004f4a7`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x18004f421`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18004f502`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18004f5c6`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18004f62c`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18004f40b`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x18004f625`: `::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)`
- `0x18004f50d`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x18004f5d1`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x18004f544`: `::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int16 a1,
        int a2,
        void *a3,
        void *a4,
        struct _ACL *a5,
        PACL Sacl,
        __int64 a7)
{
  NTSTATUS v11; // edi
  const char *v12; // rax
  SECURITY_DESCRIPTOR_CONTROL v14; // r8
  int v15; // ebx
  char v16; // al
  SECURITY_DESCRIPTOR_CONTROL v17; // r8
  NTSTATUS v18; // ebx
  PACL v19; // rcx
  const char *v20; // rax
  const char *v21; // rcx
  PACL Dacl; // [rsp+20h] [rbp-50h] BYREF
  const char *v23; // [rsp+28h] [rbp-48h]
  __int64 v24; // [rsp+30h] [rbp-40h]
  const char *v25; // [rsp+38h] [rbp-38h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h]

  Dacl = a5;
  v27 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v11 < 0 )
  {
    v24 = 346;
    v12 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v25 = v12;
    Dacl = (PACL)"onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
LABEL_4:
    RtlReportErrorOrigination(&Dacl, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v11);
    return (unsigned int)v11;
  }
  if ( (a2 & 1) != 0 )
  {
    v11 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
    if ( v11 < 0 )
    {
      v24 = 355;
      v12 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 2) != 0 )
  {
    v11 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
    if ( v11 < 0 )
    {
      v24 = 363;
      v12 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 4) != 0 )
  {
    v14 = a1 & 0x1500 | (a2 >> 31) & 0x1000;
    v11 = RtlSetControlSecurityDescriptor(SecurityDescriptor, v14, v14);
    if ( v11 < 0 )
    {
      v24 = 371;
      Dacl = (PACL)"onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v25 = "::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)";
      goto LABEL_4;
    }
    v11 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
    if ( v11 < 0 )
    {
      v24 = 377;
      v12 = "::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 8) == 0 )
    goto LABEL_28;
  v15 = a2 & 0x40000000;
  if ( !Sacl || (v16 = 1, !Sacl->AceCount) )
    v16 = 0;
  if ( !v15 && !v16 && (a1 & 0x10) == 0 )
    goto LABEL_28;
  v17 = a1 & 0x2A00 | (v15 != 0 ? 0x2000 : 0);
  v18 = RtlSetControlSecurityDescriptor(SecurityDescriptor, v17, v17);
  if ( v18 >= 0 )
  {
    v18 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0);
    if ( v18 < 0 )
    {
      v24 = 406;
      Dacl = (PACL)"onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v25 = "::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      goto LABEL_25;
    }
LABEL_28:
    Dacl = 0;
    v23 = 0;
    v18 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&Dacl, SecurityDescriptor);
    if ( v18 >= 0 )
    {
      v19 = Dacl;
      v18 = 0;
      Dacl = *(PACL *)a7;
      v20 = *(const char **)(a7 + 8);
      *(_QWORD *)a7 = v19;
      v21 = v23;
      v23 = v20;
      *(_QWORD *)(a7 + 8) = v21;
    }
    Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&Dacl);
    return (unsigned int)v18;
  }
  v24 = 400;
  Dacl = (PACL)"onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
  v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
  v25 = "::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)";
LABEL_25:
  RtlReportErrorOrigination(&Dacl, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18004f398  mov     [rsp-38h+arg_8], rbx
0x18004f39d  push    rbp
0x18004f39e  push    rsi
0x18004f39f  push    rdi
0x18004f3a0  push    r12
0x18004f3a2  push    r13
0x18004f3a4  push    r14
0x18004f3a6  push    r15
0x18004f3a8  mov     rbp, rsp
0x18004f3ab  sub     rsp, 70h
0x18004f3af  mov     rax, cs:__security_cookie
0x18004f3b6  xor     rax, rsp
0x18004f3b9  mov     [rbp+var_8], rax
0x18004f3bd  mov     rax, [rbp+arg_20]
0x18004f3c1  xorps   xmm0, xmm0
0x18004f3c4  mov     r15, [rbp+Sacl]
0x18004f3c8  mov     ebx, edx
0x18004f3ca  mov     rsi, [rbp+arg_30]
0x18004f3ce  movzx   r14d, cx
0x18004f3d2  mov     [rbp+Dacl], rax
0x18004f3d6  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f3da  xor     eax, eax
0x18004f3dc  mov     r13, r9
0x18004f3df  mov     r12, r8
0x18004f3e2  mov     [rbp+var_10], rax
0x18004f3e6  movups  [rbp+SecurityDescriptor], xmm0
0x18004f3ea  lea     edx, [rax+1]; Revision
0x18004f3ed  movups  [rbp+var_20], xmm0
0x18004f3f1  call    cs:__imp_RtlCreateSecurityDescriptor
0x18004f3f8  nop     dword ptr [rax+rax+00h]
0x18004f3fd  mov     edi, eax
0x18004f3ff  test    eax, eax
0x18004f401  jns     short loc_18004F446
0x18004f403  mov     [rbp+var_40], 15Ah
0x18004f40b  lea     rax, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x18004f412  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f419  mov     [rbp+var_38], rax
0x18004f41d  mov     [rbp+Dacl], rcx
0x18004f421  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x18004f428  mov     [rbp+var_48], rcx
0x18004f42c  mov     r8d, edi
0x18004f42f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f436  lea     rcx, [rbp+Dacl]
0x18004f43a  call    RtlReportErrorOrigination
0x18004f43f  mov     eax, edi
0x18004f441  jmp     loc_18004F684
0x18004f446  test    bl, 1
0x18004f449  jz      short loc_18004F47B
0x18004f44b  xor     r8d, r8d; OwnerDefaulted
0x18004f44e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f452  mov     rdx, r12; Owner
0x18004f455  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18004f45c  nop     dword ptr [rax+rax+00h]
0x18004f461  xor     r12d, r12d
0x18004f464  mov     edi, eax
0x18004f466  test    eax, eax
0x18004f468  jns     short loc_18004F47E
0x18004f46a  mov     [rbp+var_40], 163h
0x18004f472  lea     rax, aRtlsetownersec_0; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x18004f479  jmp     short loc_18004F412
0x18004f47b  xor     r12d, r12d
0x18004f47e  test    bl, 2
0x18004f481  jz      short loc_18004F4B3
0x18004f483  xor     r8d, r8d; GroupDefaulted
0x18004f486  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f48a  mov     rdx, r13; Group
0x18004f48d  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18004f494  nop     dword ptr [rax+rax+00h]
0x18004f499  mov     edi, eax
0x18004f49b  test    eax, eax
0x18004f49d  jns     short loc_18004F4B3
0x18004f49f  mov     [rbp+var_40], 16Bh
0x18004f4a7  lea     rax, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x18004f4ae  jmp     loc_18004F412
0x18004f4b3  test    bl, 4
0x18004f4b6  jz      loc_18004F550
0x18004f4bc  mov     eax, 0FAFFh
0x18004f4c1  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f4c5  mov     edx, ebx
0x18004f4c7  sar     edx, 1Fh
0x18004f4ca  and     dx, ax
0x18004f4cd  mov     eax, 1500h
0x18004f4d2  or      dx, r14w
0x18004f4d6  and     dx, ax; ControlBitsOfInterest
0x18004f4d9  movzx   r8d, dx; ControlBitsToSet
0x18004f4dd  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18004f4e4  nop     dword ptr [rax+rax+00h]
0x18004f4e9  mov     edi, eax
0x18004f4eb  test    eax, eax
0x18004f4ed  jns     short loc_18004F51D
0x18004f4ef  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f4f6  mov     [rbp+var_40], 173h
0x18004f4fe  mov     [rbp+Dacl], rcx
0x18004f502  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x18004f509  mov     [rbp+var_48], rcx
0x18004f50d  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x18004f514  mov     [rbp+var_38], rcx
0x18004f518  jmp     loc_18004F42C
0x18004f51d  mov     r8, [rbp+Dacl]; Dacl
0x18004f521  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f525  xor     r9d, r9d; DaclDefaulted
0x18004f528  mov     dl, 1; DaclPresent
0x18004f52a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18004f531  nop     dword ptr [rax+rax+00h]
0x18004f536  mov     edi, eax
0x18004f538  test    eax, eax
0x18004f53a  jns     short loc_18004F550
0x18004f53c  mov     [rbp+var_40], 179h
0x18004f544  lea     rax, aRtlsetdaclsecu_0; "::RtlSetDaclSecurityDescriptor( &Absolu"...
0x18004f54b  jmp     loc_18004F412
0x18004f550  test    bl, 8
0x18004f553  jz      loc_18004F63D
0x18004f559  and     ebx, 40000000h
0x18004f55f  test    r15, r15
0x18004f562  jz      short loc_18004F56D
0x18004f564  mov     al, 1
0x18004f566  cmp     [r15+4], r12w
0x18004f56b  ja      short loc_18004F570
0x18004f56d  mov     al, r12b
0x18004f570  test    ebx, ebx
0x18004f572  jnz     short loc_18004F582
0x18004f574  test    al, al
0x18004f576  jnz     short loc_18004F582
0x18004f578  test    r14b, 10h
0x18004f57c  jz      loc_18004F63D
0x18004f582  mov     eax, 2A00h
0x18004f587  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f58b  neg     ebx
0x18004f58d  sbb     dx, dx
0x18004f590  and     r14w, ax
0x18004f594  and     dx, 2000h
0x18004f599  or      dx, r14w; ControlBitsOfInterest
0x18004f59d  movzx   r8d, dx; ControlBitsToSet
0x18004f5a1  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18004f5a8  nop     dword ptr [rax+rax+00h]
0x18004f5ad  mov     ebx, eax
0x18004f5af  test    eax, eax
0x18004f5b1  jns     short loc_18004F5F4
0x18004f5b3  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f5ba  mov     [rbp+var_40], 190h
0x18004f5c2  mov     [rbp+Dacl], rcx
0x18004f5c6  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x18004f5cd  mov     [rbp+var_48], rcx
0x18004f5d1  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x18004f5d8  mov     [rbp+var_38], rcx
0x18004f5dc  mov     r8d, ebx
0x18004f5df  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18004f5e6  lea     rcx, [rbp+Dacl]
0x18004f5ea  call    RtlReportErrorOrigination
0x18004f5ef  jmp     loc_18004F682
0x18004f5f4  xor     r9d, r9d; SaclDefaulted
0x18004f5f7  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004f5fb  mov     r8, r15; Sacl
0x18004f5fe  mov     dl, 1; SaclPresent
0x18004f600  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18004f607  nop     dword ptr [rax+rax+00h]
0x18004f60c  mov     ebx, eax
0x18004f60e  test    eax, eax
0x18004f610  jns     short loc_18004F63D
0x18004f612  lea     rcx, aOnecoreBaseWcp_46; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18004f619  mov     [rbp+var_40], 196h
0x18004f621  mov     [rbp+Dacl], rcx
0x18004f625  lea     rax, aRtlsetsaclsecu; "::RtlSetSaclSecurityDescriptor( &Absolu"...
0x18004f62c  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x18004f633  mov     [rbp+var_38], rax
0x18004f637  mov     [rbp+var_48], rcx
0x18004f63b  jmp     short loc_18004F5DC
0x18004f63d  lea     rdx, [rbp+SecurityDescriptor]
0x18004f641  mov     [rbp+Dacl], r12
0x18004f645  lea     rcx, [rbp+Dacl]
0x18004f649  mov     [rbp+var_48], r12
0x18004f64d  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x18004f652  mov     ebx, eax
0x18004f654  test    eax, eax
0x18004f656  js      short loc_18004F679
0x18004f658  mov     rcx, [rbp+Dacl]
0x18004f65c  mov     ebx, r12d
0x18004f65f  mov     rax, [rsi]
0x18004f662  mov     [rbp+Dacl], rax
0x18004f666  mov     rax, [rsi+8]
0x18004f66a  mov     [rsi], rcx
0x18004f66d  mov     rcx, [rbp+var_48]
0x18004f671  mov     [rbp+var_48], rax
0x18004f675  mov     [rsi+8], rcx
0x18004f679  lea     rcx, [rbp+Dacl]
0x18004f67d  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x18004f682  mov     eax, ebx
0x18004f684  mov     rcx, [rbp+var_8]
0x18004f688  xor     rcx, rsp; StackCookie
0x18004f68b  call    __security_check_cookie
0x18004f690  mov     rbx, [rsp+70h+arg_8]
0x18004f698  add     rsp, 70h
0x18004f69c  pop     r15
0x18004f69e  pop     r14
0x18004f6a0  pop     r13
0x18004f6a2  pop     r12
0x18004f6a4  pop     rdi
0x18004f6a5  pop     rsi
0x18004f6a6  pop     rbp
0x18004f6a7  retn
```

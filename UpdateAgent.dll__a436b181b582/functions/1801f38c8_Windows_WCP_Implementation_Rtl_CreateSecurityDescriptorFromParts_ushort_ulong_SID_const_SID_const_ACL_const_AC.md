# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x1801f38c8`
- end: `0x1801f3bd9`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `785`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180195d74`
- `0x1801f4220`
- `0x1801f6030`

## callees

- `0x1800059d0`
- `0x1801efdc0`
- `0x1801f320c`
- `0x1801f3880`
- `0x1801f38c8`

## import_xrefs

- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1801f3b30`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x1801f3b30`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801f3985`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801f3985`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801f3a5a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801f3a5a`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801f3a0d`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801f3ad1`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801f3a0d`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x1801f3ad1`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1801f39bd`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1801f39bd`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801f3921`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1801f3921`

## string_xrefs

- `0x1801f3942`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f3a1f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f3ae3`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f3b42`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801f393b`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x1801f3951`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801f3a32`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801f3af6`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801f3b5c`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801f3a74`: `::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)`
- `0x1801f3a3d`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x1801f3b01`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x1801f39d7`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x1801f39a2`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x1801f3b55`: `::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)`

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
0x1801f38c8  mov     [rsp-38h+arg_8], rbx
0x1801f38cd  push    rbp
0x1801f38ce  push    rsi
0x1801f38cf  push    rdi
0x1801f38d0  push    r12
0x1801f38d2  push    r13
0x1801f38d4  push    r14
0x1801f38d6  push    r15
0x1801f38d8  mov     rbp, rsp
0x1801f38db  sub     rsp, 70h
0x1801f38df  mov     rax, cs:__security_cookie
0x1801f38e6  xor     rax, rsp
0x1801f38e9  mov     [rbp+var_8], rax
0x1801f38ed  mov     rax, [rbp+arg_20]
0x1801f38f1  xorps   xmm0, xmm0
0x1801f38f4  mov     r15, [rbp+Sacl]
0x1801f38f8  mov     ebx, edx
0x1801f38fa  mov     rsi, [rbp+arg_30]
0x1801f38fe  movzx   r14d, cx
0x1801f3902  mov     [rbp+Dacl], rax
0x1801f3906  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f390a  xor     eax, eax
0x1801f390c  mov     r13, r9
0x1801f390f  mov     r12, r8
0x1801f3912  mov     [rbp+var_10], rax
0x1801f3916  movups  [rbp+SecurityDescriptor], xmm0
0x1801f391a  lea     edx, [rax+1]; Revision
0x1801f391d  movups  [rbp+var_20], xmm0
0x1801f3921  call    cs:__imp_RtlCreateSecurityDescriptor
0x1801f3928  nop     dword ptr [rax+rax+00h]
0x1801f392d  mov     edi, eax
0x1801f392f  test    eax, eax
0x1801f3931  jns     short loc_1801F3976
0x1801f3933  mov     [rbp+var_40], 15Ah
0x1801f393b  lea     rax, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x1801f3942  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f3949  mov     [rbp+var_38], rax
0x1801f394d  mov     [rbp+Dacl], rcx
0x1801f3951  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801f3958  mov     [rbp+var_48], rcx
0x1801f395c  mov     r8d, edi
0x1801f395f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f3966  lea     rcx, [rbp+Dacl]
0x1801f396a  call    RtlReportErrorOrigination
0x1801f396f  mov     eax, edi
0x1801f3971  jmp     loc_1801F3BB4
0x1801f3976  test    bl, 1
0x1801f3979  jz      short loc_1801F39AB
0x1801f397b  xor     r8d, r8d; OwnerDefaulted
0x1801f397e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f3982  mov     rdx, r12; Owner
0x1801f3985  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1801f398c  nop     dword ptr [rax+rax+00h]
0x1801f3991  xor     r12d, r12d
0x1801f3994  mov     edi, eax
0x1801f3996  test    eax, eax
0x1801f3998  jns     short loc_1801F39AE
0x1801f399a  mov     [rbp+var_40], 163h
0x1801f39a2  lea     rax, aRtlsetownersec_0; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x1801f39a9  jmp     short loc_1801F3942
0x1801f39ab  xor     r12d, r12d
0x1801f39ae  test    bl, 2
0x1801f39b1  jz      short loc_1801F39E3
0x1801f39b3  xor     r8d, r8d; GroupDefaulted
0x1801f39b6  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f39ba  mov     rdx, r13; Group
0x1801f39bd  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1801f39c4  nop     dword ptr [rax+rax+00h]
0x1801f39c9  mov     edi, eax
0x1801f39cb  test    eax, eax
0x1801f39cd  jns     short loc_1801F39E3
0x1801f39cf  mov     [rbp+var_40], 16Bh
0x1801f39d7  lea     rax, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x1801f39de  jmp     loc_1801F3942
0x1801f39e3  test    bl, 4
0x1801f39e6  jz      loc_1801F3A80
0x1801f39ec  mov     eax, 0FAFFh
0x1801f39f1  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f39f5  mov     edx, ebx
0x1801f39f7  sar     edx, 1Fh
0x1801f39fa  and     dx, ax
0x1801f39fd  mov     eax, 1500h
0x1801f3a02  or      dx, r14w
0x1801f3a06  and     dx, ax; ControlBitsOfInterest
0x1801f3a09  movzx   r8d, dx; ControlBitsToSet
0x1801f3a0d  call    cs:__imp_RtlSetControlSecurityDescriptor
0x1801f3a14  nop     dword ptr [rax+rax+00h]
0x1801f3a19  mov     edi, eax
0x1801f3a1b  test    eax, eax
0x1801f3a1d  jns     short loc_1801F3A4D
0x1801f3a1f  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f3a26  mov     [rbp+var_40], 173h
0x1801f3a2e  mov     [rbp+Dacl], rcx
0x1801f3a32  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801f3a39  mov     [rbp+var_48], rcx
0x1801f3a3d  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x1801f3a44  mov     [rbp+var_38], rcx
0x1801f3a48  jmp     loc_1801F395C
0x1801f3a4d  mov     r8, [rbp+Dacl]; Dacl
0x1801f3a51  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f3a55  xor     r9d, r9d; DaclDefaulted
0x1801f3a58  mov     dl, 1; DaclPresent
0x1801f3a5a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801f3a61  nop     dword ptr [rax+rax+00h]
0x1801f3a66  mov     edi, eax
0x1801f3a68  test    eax, eax
0x1801f3a6a  jns     short loc_1801F3A80
0x1801f3a6c  mov     [rbp+var_40], 179h
0x1801f3a74  lea     rax, aRtlsetdaclsecu_0; "::RtlSetDaclSecurityDescriptor( &Absolu"...
0x1801f3a7b  jmp     loc_1801F3942
0x1801f3a80  test    bl, 8
0x1801f3a83  jz      loc_1801F3B6D
0x1801f3a89  and     ebx, 40000000h
0x1801f3a8f  test    r15, r15
0x1801f3a92  jz      short loc_1801F3A9D
0x1801f3a94  mov     al, 1
0x1801f3a96  cmp     [r15+4], r12w
0x1801f3a9b  ja      short loc_1801F3AA0
0x1801f3a9d  mov     al, r12b
0x1801f3aa0  test    ebx, ebx
0x1801f3aa2  jnz     short loc_1801F3AB2
0x1801f3aa4  test    al, al
0x1801f3aa6  jnz     short loc_1801F3AB2
0x1801f3aa8  test    r14b, 10h
0x1801f3aac  jz      loc_1801F3B6D
0x1801f3ab2  mov     eax, 2A00h
0x1801f3ab7  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f3abb  neg     ebx
0x1801f3abd  sbb     dx, dx
0x1801f3ac0  and     r14w, ax
0x1801f3ac4  and     dx, 2000h
0x1801f3ac9  or      dx, r14w; ControlBitsOfInterest
0x1801f3acd  movzx   r8d, dx; ControlBitsToSet
0x1801f3ad1  call    cs:__imp_RtlSetControlSecurityDescriptor
0x1801f3ad8  nop     dword ptr [rax+rax+00h]
0x1801f3add  mov     ebx, eax
0x1801f3adf  test    eax, eax
0x1801f3ae1  jns     short loc_1801F3B24
0x1801f3ae3  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f3aea  mov     [rbp+var_40], 190h
0x1801f3af2  mov     [rbp+Dacl], rcx
0x1801f3af6  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801f3afd  mov     [rbp+var_48], rcx
0x1801f3b01  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x1801f3b08  mov     [rbp+var_38], rcx
0x1801f3b0c  mov     r8d, ebx
0x1801f3b0f  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801f3b16  lea     rcx, [rbp+Dacl]
0x1801f3b1a  call    RtlReportErrorOrigination
0x1801f3b1f  jmp     loc_1801F3BB2
0x1801f3b24  xor     r9d, r9d; SaclDefaulted
0x1801f3b27  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801f3b2b  mov     r8, r15; Sacl
0x1801f3b2e  mov     dl, 1; SaclPresent
0x1801f3b30  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x1801f3b37  nop     dword ptr [rax+rax+00h]
0x1801f3b3c  mov     ebx, eax
0x1801f3b3e  test    eax, eax
0x1801f3b40  jns     short loc_1801F3B6D
0x1801f3b42  lea     rcx, aOnecoreBaseWcp_45; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801f3b49  mov     [rbp+var_40], 196h
0x1801f3b51  mov     [rbp+Dacl], rcx
0x1801f3b55  lea     rax, aRtlsetsaclsecu; "::RtlSetSaclSecurityDescriptor( &Absolu"...
0x1801f3b5c  lea     rcx, aWindowsWcpImpl_17; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801f3b63  mov     [rbp+var_38], rax
0x1801f3b67  mov     [rbp+var_48], rcx
0x1801f3b6b  jmp     short loc_1801F3B0C
0x1801f3b6d  lea     rdx, [rbp+SecurityDescriptor]
0x1801f3b71  mov     [rbp+Dacl], r12
0x1801f3b75  lea     rcx, [rbp+Dacl]
0x1801f3b79  mov     [rbp+var_48], r12
0x1801f3b7d  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x1801f3b82  mov     ebx, eax
0x1801f3b84  test    eax, eax
0x1801f3b86  js      short loc_1801F3BA9
0x1801f3b88  mov     rcx, [rbp+Dacl]
0x1801f3b8c  mov     ebx, r12d
0x1801f3b8f  mov     rax, [rsi]
0x1801f3b92  mov     [rbp+Dacl], rax
0x1801f3b96  mov     rax, [rsi+8]
0x1801f3b9a  mov     [rsi], rcx
0x1801f3b9d  mov     rcx, [rbp+var_48]
0x1801f3ba1  mov     [rbp+var_48], rax
0x1801f3ba5  mov     [rsi+8], rcx
0x1801f3ba9  lea     rcx, [rbp+Dacl]
0x1801f3bad  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x1801f3bb2  mov     eax, ebx
0x1801f3bb4  mov     rcx, [rbp+var_8]
0x1801f3bb8  xor     rcx, rsp; StackCookie
0x1801f3bbb  call    __security_check_cookie
0x1801f3bc0  mov     rbx, [rsp+70h+arg_8]
0x1801f3bc8  add     rsp, 70h
0x1801f3bcc  pop     r15
0x1801f3bce  pop     r14
0x1801f3bd0  pop     r13
0x1801f3bd2  pop     r12
0x1801f3bd4  pop     rdi
0x1801f3bd5  pop     rsi
0x1801f3bd6  pop     rbp
0x1801f3bd7  retn
```

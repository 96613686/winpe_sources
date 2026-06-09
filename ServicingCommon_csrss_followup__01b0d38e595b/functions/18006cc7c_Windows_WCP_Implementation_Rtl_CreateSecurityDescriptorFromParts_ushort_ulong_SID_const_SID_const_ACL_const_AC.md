# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x18006cc7c`
- end: `0x18006cf87`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c2d8`

## callees

- `0x18001f840`
- `0x180021878`
- `0x18002d2b0`
- `0x18006c87c`
- `0x18006cc7c`

## import_xrefs

- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006cede`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006cede`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006cd37`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006cd37`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006ce2c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006ce2c`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cde6`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006ceb5`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cde6`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006ceb5`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006cd83`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006cd83`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006ccda`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006ccda`

## string_xrefs

- `0x18006ccea`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cd4a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cd93`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cdfe`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ce3c`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ceee`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ccfd`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cd5d`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cda6`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006ce09`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006ce4f`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cf01`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cd68`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x18006cd08`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x18006ce14`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x18006cdb1`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x18006cf0c`: `::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)`
- `0x18006ce5a`: `::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int16 a1,
        int a2,
        void *a3,
        void *a4,
        struct _ACL *Dacl,
        PACL Sacl,
        const char **a7)
{
  NTSTATUS v11; // eax
  const char *v12; // rcx
  SECURITY_DESCRIPTOR_CONTROL v14; // r8
  int v15; // ebx
  char v16; // al
  SECURITY_DESCRIPTOR_CONTROL v17; // r8
  int v18; // ebx
  const char *v19; // rcx
  const char *v20; // rax
  const char *v21; // rcx
  const char *v22; // [rsp+20h] [rbp-60h] BYREF
  const char *v23; // [rsp+28h] [rbp-58h]
  __int64 v24; // [rsp+30h] [rbp-50h]
  const char *v25; // [rsp+38h] [rbp-48h]
  int v26; // [rsp+40h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]

  v26 = 0;
  v28 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v11 < 0 )
  {
    v24 = 346;
    v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v12 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v25 = v12;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v26,
             &v22,
             (unsigned int)v11);
  }
  if ( (a2 & 1) != 0 )
  {
    v11 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
    if ( v11 < 0 )
    {
      v24 = 355;
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
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
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
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
LABEL_13:
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)";
      goto LABEL_3;
    }
    v11 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
    if ( v11 < 0 )
    {
      v24 = 377;
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 8) != 0 )
  {
    v15 = a2 & 0x40000000;
    if ( !Sacl || (v16 = 1, !Sacl->AceCount) )
      v16 = 0;
    if ( v15 || v16 || (a1 & 0x10) != 0 )
    {
      v17 = a1 & 0x2A00 | (v15 != 0 ? 0x2000 : 0);
      v11 = RtlSetControlSecurityDescriptor(SecurityDescriptor, v17, v17);
      if ( v11 < 0 )
      {
        v24 = 400;
        goto LABEL_13;
      }
      v11 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0);
      if ( v11 < 0 )
      {
        v24 = 406;
        v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
        v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
        v12 = "::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)";
        goto LABEL_3;
      }
    }
  }
  v22 = 0;
  v23 = 0;
  v18 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&v22, SecurityDescriptor);
  if ( v18 >= 0 )
  {
    v19 = v22;
    v18 = 0;
    v22 = *a7;
    v20 = a7[1];
    *a7 = v19;
    v21 = v23;
    v23 = v20;
    a7[1] = v21;
  }
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v22);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18006cc7c  mov     [rsp-38h+arg_8], rbx
0x18006cc81  push    rbp
0x18006cc82  push    rsi
0x18006cc83  push    rdi
0x18006cc84  push    r12
0x18006cc86  push    r13
0x18006cc88  push    r14
0x18006cc8a  push    r15
0x18006cc8c  mov     rbp, rsp
0x18006cc8f  sub     rsp, 80h
0x18006cc96  mov     rax, cs:__security_cookie
0x18006cc9d  xor     rax, rsp
0x18006cca0  mov     [rbp+var_10], rax
0x18006cca4  mov     r14, [rbp+Sacl]
0x18006cca8  xor     eax, eax
0x18006ccaa  mov     r13, [rbp+Dacl]
0x18006ccae  xorps   xmm0, xmm0
0x18006ccb1  mov     rdi, [rbp+arg_30]
0x18006ccb5  mov     ebx, edx
0x18006ccb7  movzx   esi, cx
0x18006ccba  mov     [rbp+var_40], 0
0x18006ccc1  lea     edx, [rax+1]; Revision
0x18006ccc4  mov     [rbp+var_18], rax
0x18006ccc8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cccc  mov     r12, r9
0x18006cccf  mov     r15, r8
0x18006ccd2  movups  [rbp+SecurityDescriptor], xmm0
0x18006ccd6  movups  [rbp+var_28], xmm0
0x18006ccda  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006cce1  nop     dword ptr [rax+rax+00h]
0x18006cce6  test    eax, eax
0x18006cce8  jns     short loc_18006CD28
0x18006ccea  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ccf1  mov     [rbp+var_50], 15Ah
0x18006ccf9  mov     [rbp+var_60], rcx
0x18006ccfd  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cd04  mov     [rbp+var_58], rcx
0x18006cd08  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x18006cd0f  mov     [rbp+var_48], rcx
0x18006cd13  lea     rdx, [rbp+var_60]
0x18006cd17  lea     rcx, [rbp+var_40]
0x18006cd1b  mov     r8d, eax
0x18006cd1e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006cd23  jmp     loc_18006CF5F
0x18006cd28  test    bl, 1
0x18006cd2b  jz      short loc_18006CD71
0x18006cd2d  xor     r8d, r8d; OwnerDefaulted
0x18006cd30  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cd34  mov     rdx, r15; Owner
0x18006cd37  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006cd3e  nop     dword ptr [rax+rax+00h]
0x18006cd43  xor     r15d, r15d
0x18006cd46  test    eax, eax
0x18006cd48  jns     short loc_18006CD74
0x18006cd4a  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cd51  mov     [rbp+var_50], 163h
0x18006cd59  mov     [rbp+var_60], rcx
0x18006cd5d  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cd64  mov     [rbp+var_58], rcx
0x18006cd68  lea     rcx, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x18006cd6f  jmp     short loc_18006CD0F
0x18006cd71  xor     r15d, r15d
0x18006cd74  test    bl, 2
0x18006cd77  jz      short loc_18006CDBD
0x18006cd79  xor     r8d, r8d; GroupDefaulted
0x18006cd7c  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cd80  mov     rdx, r12; Group
0x18006cd83  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006cd8a  nop     dword ptr [rax+rax+00h]
0x18006cd8f  test    eax, eax
0x18006cd91  jns     short loc_18006CDBD
0x18006cd93  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cd9a  mov     [rbp+var_50], 16Bh
0x18006cda2  mov     [rbp+var_60], rcx
0x18006cda6  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cdad  mov     [rbp+var_58], rcx
0x18006cdb1  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x18006cdb8  jmp     loc_18006CD0F
0x18006cdbd  test    bl, 4
0x18006cdc0  jz      loc_18006CE66
0x18006cdc6  mov     eax, 0FAFFh
0x18006cdcb  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cdcf  mov     edx, ebx
0x18006cdd1  sar     edx, 1Fh
0x18006cdd4  and     dx, ax
0x18006cdd7  mov     eax, 1500h
0x18006cddc  or      dx, si
0x18006cddf  and     dx, ax; ControlBitsOfInterest
0x18006cde2  movzx   r8d, dx; ControlBitsToSet
0x18006cde6  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18006cded  nop     dword ptr [rax+rax+00h]
0x18006cdf2  test    eax, eax
0x18006cdf4  jns     short loc_18006CE20
0x18006cdf6  mov     [rbp+var_50], 173h
0x18006cdfe  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ce05  mov     [rbp+var_60], rcx
0x18006ce09  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006ce10  mov     [rbp+var_58], rcx
0x18006ce14  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x18006ce1b  jmp     loc_18006CD0F
0x18006ce20  xor     r9d, r9d; DaclDefaulted
0x18006ce23  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006ce27  mov     r8, r13; Dacl
0x18006ce2a  mov     dl, 1; DaclPresent
0x18006ce2c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006ce33  nop     dword ptr [rax+rax+00h]
0x18006ce38  test    eax, eax
0x18006ce3a  jns     short loc_18006CE66
0x18006ce3c  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ce43  mov     [rbp+var_50], 179h
0x18006ce4b  mov     [rbp+var_60], rcx
0x18006ce4f  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006ce56  mov     [rbp+var_58], rcx
0x18006ce5a  lea     rcx, aRtlsetdaclsecu; "::RtlSetDaclSecurityDescriptor( &Absolu"...
0x18006ce61  jmp     loc_18006CD0F
0x18006ce66  test    bl, 8
0x18006ce69  jz      loc_18006CF18
0x18006ce6f  and     ebx, 40000000h
0x18006ce75  test    r14, r14
0x18006ce78  jz      short loc_18006CE83
0x18006ce7a  mov     al, 1
0x18006ce7c  cmp     [r14+4], r15w
0x18006ce81  ja      short loc_18006CE86
0x18006ce83  mov     al, r15b
0x18006ce86  test    ebx, ebx
0x18006ce88  jnz     short loc_18006CE98
0x18006ce8a  test    al, al
0x18006ce8c  jnz     short loc_18006CE98
0x18006ce8e  test    sil, 10h
0x18006ce92  jz      loc_18006CF18
0x18006ce98  mov     eax, 2A00h
0x18006ce9d  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cea1  neg     ebx
0x18006cea3  sbb     dx, dx
0x18006cea6  and     si, ax
0x18006cea9  and     dx, 2000h
0x18006ceae  or      dx, si; ControlBitsOfInterest
0x18006ceb1  movzx   r8d, dx; ControlBitsToSet
0x18006ceb5  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18006cebc  nop     dword ptr [rax+rax+00h]
0x18006cec1  test    eax, eax
0x18006cec3  jns     short loc_18006CED2
0x18006cec5  mov     [rbp+var_50], 190h
0x18006cecd  jmp     loc_18006CDFE
0x18006ced2  xor     r9d, r9d; SaclDefaulted
0x18006ced5  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006ced9  mov     r8, r14; Sacl
0x18006cedc  mov     dl, 1; SaclPresent
0x18006cede  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18006cee5  nop     dword ptr [rax+rax+00h]
0x18006ceea  test    eax, eax
0x18006ceec  jns     short loc_18006CF18
0x18006ceee  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cef5  mov     [rbp+var_50], 196h
0x18006cefd  mov     [rbp+var_60], rcx
0x18006cf01  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cf08  mov     [rbp+var_58], rcx
0x18006cf0c  lea     rcx, aRtlsetsaclsecu; "::RtlSetSaclSecurityDescriptor( &Absolu"...
0x18006cf13  jmp     loc_18006CD0F
0x18006cf18  lea     rdx, [rbp+SecurityDescriptor]
0x18006cf1c  mov     [rbp+var_60], r15
0x18006cf20  lea     rcx, [rbp+var_60]
0x18006cf24  mov     [rbp+var_58], r15
0x18006cf28  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x18006cf2d  mov     ebx, eax
0x18006cf2f  test    eax, eax
0x18006cf31  js      short loc_18006CF54
0x18006cf33  mov     rcx, [rbp+var_60]
0x18006cf37  mov     ebx, r15d
0x18006cf3a  mov     rax, [rdi]
0x18006cf3d  mov     [rbp+var_60], rax
0x18006cf41  mov     rax, [rdi+8]
0x18006cf45  mov     [rdi], rcx
0x18006cf48  mov     rcx, [rbp+var_58]
0x18006cf4c  mov     [rbp+var_58], rax
0x18006cf50  mov     [rdi+8], rcx
0x18006cf54  lea     rcx, [rbp+var_60]
0x18006cf58  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x18006cf5d  mov     eax, ebx
0x18006cf5f  mov     rcx, [rbp+var_10]
0x18006cf63  xor     rcx, rsp; StackCookie
0x18006cf66  call    __security_check_cookie
0x18006cf6b  mov     rbx, [rsp+80h+arg_8]
0x18006cf73  add     rsp, 80h
0x18006cf7a  pop     r15
0x18006cf7c  pop     r14
0x18006cf7e  pop     r13
0x18006cf80  pop     r12
0x18006cf82  pop     rdi
0x18006cf83  pop     rsi
0x18006cf84  pop     rbp
0x18006cf85  retn
```

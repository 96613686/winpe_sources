# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x18006cd8c`
- end: `0x18006d097`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c3f4`

## callees

- `0x18001f5d4`
- `0x18001f6c0`
- `0x1800293a0`
- `0x18006c994`
- `0x18006cd8c`

## import_xrefs

- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006cfee`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18006cfee`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006ce47`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18006ce47`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006cf3c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18006cf3c`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cef6`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cfc5`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cef6`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18006cfc5`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006ce93`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18006ce93`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006cdea`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006cdea`

## string_xrefs

- `0x18006cdfa`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ce5a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cea3`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cf0e`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cf4c`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006cffe`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006ce18`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x18006ce0d`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006ce6d`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006ceb6`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cf19`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cf5f`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006d011`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18006cec1`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x18006ce78`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x18006cf6a`: `::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)`
- `0x18006cf24`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x18006d01c`: `::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)`

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
0x18006cd8c  mov     [rsp-38h+arg_8], rbx
0x18006cd91  push    rbp
0x18006cd92  push    rsi
0x18006cd93  push    rdi
0x18006cd94  push    r12
0x18006cd96  push    r13
0x18006cd98  push    r14
0x18006cd9a  push    r15
0x18006cd9c  mov     rbp, rsp
0x18006cd9f  sub     rsp, 80h
0x18006cda6  mov     rax, cs:__security_cookie
0x18006cdad  xor     rax, rsp
0x18006cdb0  mov     [rbp+var_10], rax
0x18006cdb4  mov     r14, [rbp+Sacl]
0x18006cdb8  xor     eax, eax
0x18006cdba  mov     r13, [rbp+Dacl]
0x18006cdbe  xorps   xmm0, xmm0
0x18006cdc1  mov     rdi, [rbp+arg_30]
0x18006cdc5  mov     ebx, edx
0x18006cdc7  movzx   esi, cx
0x18006cdca  mov     [rbp+var_40], 0
0x18006cdd1  lea     edx, [rax+1]; Revision
0x18006cdd4  mov     [rbp+var_18], rax
0x18006cdd8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cddc  mov     r12, r9
0x18006cddf  mov     r15, r8
0x18006cde2  movups  [rbp+SecurityDescriptor], xmm0
0x18006cde6  movups  [rbp+var_28], xmm0
0x18006cdea  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006cdf1  nop     dword ptr [rax+rax+00h]
0x18006cdf6  test    eax, eax
0x18006cdf8  jns     short loc_18006CE38
0x18006cdfa  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ce01  mov     [rbp+var_50], 15Ah
0x18006ce09  mov     [rbp+var_60], rcx
0x18006ce0d  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006ce14  mov     [rbp+var_58], rcx
0x18006ce18  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x18006ce1f  mov     [rbp+var_48], rcx
0x18006ce23  lea     rdx, [rbp+var_60]
0x18006ce27  lea     rcx, [rbp+var_40]
0x18006ce2b  mov     r8d, eax
0x18006ce2e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006ce33  jmp     loc_18006D06F
0x18006ce38  test    bl, 1
0x18006ce3b  jz      short loc_18006CE81
0x18006ce3d  xor     r8d, r8d; OwnerDefaulted
0x18006ce40  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006ce44  mov     rdx, r15; Owner
0x18006ce47  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18006ce4e  nop     dword ptr [rax+rax+00h]
0x18006ce53  xor     r15d, r15d
0x18006ce56  test    eax, eax
0x18006ce58  jns     short loc_18006CE84
0x18006ce5a  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ce61  mov     [rbp+var_50], 163h
0x18006ce69  mov     [rbp+var_60], rcx
0x18006ce6d  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006ce74  mov     [rbp+var_58], rcx
0x18006ce78  lea     rcx, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x18006ce7f  jmp     short loc_18006CE1F
0x18006ce81  xor     r15d, r15d
0x18006ce84  test    bl, 2
0x18006ce87  jz      short loc_18006CECD
0x18006ce89  xor     r8d, r8d; GroupDefaulted
0x18006ce8c  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006ce90  mov     rdx, r12; Group
0x18006ce93  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x18006ce9a  nop     dword ptr [rax+rax+00h]
0x18006ce9f  test    eax, eax
0x18006cea1  jns     short loc_18006CECD
0x18006cea3  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006ceaa  mov     [rbp+var_50], 16Bh
0x18006ceb2  mov     [rbp+var_60], rcx
0x18006ceb6  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cebd  mov     [rbp+var_58], rcx
0x18006cec1  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x18006cec8  jmp     loc_18006CE1F
0x18006cecd  test    bl, 4
0x18006ced0  jz      loc_18006CF76
0x18006ced6  mov     eax, 0FAFFh
0x18006cedb  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cedf  mov     edx, ebx
0x18006cee1  sar     edx, 1Fh
0x18006cee4  and     dx, ax
0x18006cee7  mov     eax, 1500h
0x18006ceec  or      dx, si
0x18006ceef  and     dx, ax; ControlBitsOfInterest
0x18006cef2  movzx   r8d, dx; ControlBitsToSet
0x18006cef6  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18006cefd  nop     dword ptr [rax+rax+00h]
0x18006cf02  test    eax, eax
0x18006cf04  jns     short loc_18006CF30
0x18006cf06  mov     [rbp+var_50], 173h
0x18006cf0e  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cf15  mov     [rbp+var_60], rcx
0x18006cf19  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cf20  mov     [rbp+var_58], rcx
0x18006cf24  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x18006cf2b  jmp     loc_18006CE1F
0x18006cf30  xor     r9d, r9d; DaclDefaulted
0x18006cf33  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cf37  mov     r8, r13; Dacl
0x18006cf3a  mov     dl, 1; DaclPresent
0x18006cf3c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18006cf43  nop     dword ptr [rax+rax+00h]
0x18006cf48  test    eax, eax
0x18006cf4a  jns     short loc_18006CF76
0x18006cf4c  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006cf53  mov     [rbp+var_50], 179h
0x18006cf5b  mov     [rbp+var_60], rcx
0x18006cf5f  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006cf66  mov     [rbp+var_58], rcx
0x18006cf6a  lea     rcx, aRtlsetdaclsecu; "::RtlSetDaclSecurityDescriptor( &Absolu"...
0x18006cf71  jmp     loc_18006CE1F
0x18006cf76  test    bl, 8
0x18006cf79  jz      loc_18006D028
0x18006cf7f  and     ebx, 40000000h
0x18006cf85  test    r14, r14
0x18006cf88  jz      short loc_18006CF93
0x18006cf8a  mov     al, 1
0x18006cf8c  cmp     [r14+4], r15w
0x18006cf91  ja      short loc_18006CF96
0x18006cf93  mov     al, r15b
0x18006cf96  test    ebx, ebx
0x18006cf98  jnz     short loc_18006CFA8
0x18006cf9a  test    al, al
0x18006cf9c  jnz     short loc_18006CFA8
0x18006cf9e  test    sil, 10h
0x18006cfa2  jz      loc_18006D028
0x18006cfa8  mov     eax, 2A00h
0x18006cfad  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cfb1  neg     ebx
0x18006cfb3  sbb     dx, dx
0x18006cfb6  and     si, ax
0x18006cfb9  and     dx, 2000h
0x18006cfbe  or      dx, si; ControlBitsOfInterest
0x18006cfc1  movzx   r8d, dx; ControlBitsToSet
0x18006cfc5  call    cs:__imp_RtlSetControlSecurityDescriptor
0x18006cfcc  nop     dword ptr [rax+rax+00h]
0x18006cfd1  test    eax, eax
0x18006cfd3  jns     short loc_18006CFE2
0x18006cfd5  mov     [rbp+var_50], 190h
0x18006cfdd  jmp     loc_18006CF0E
0x18006cfe2  xor     r9d, r9d; SaclDefaulted
0x18006cfe5  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18006cfe9  mov     r8, r14; Sacl
0x18006cfec  mov     dl, 1; SaclPresent
0x18006cfee  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18006cff5  nop     dword ptr [rax+rax+00h]
0x18006cffa  test    eax, eax
0x18006cffc  jns     short loc_18006D028
0x18006cffe  lea     rcx, aOnecoreBaseWcp_21; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006d005  mov     [rbp+var_50], 196h
0x18006d00d  mov     [rbp+var_60], rcx
0x18006d011  lea     rcx, aWindowsWcpImpl_7; "Windows::WCP::Implementation::Rtl::Crea"...
0x18006d018  mov     [rbp+var_58], rcx
0x18006d01c  lea     rcx, aRtlsetsaclsecu; "::RtlSetSaclSecurityDescriptor( &Absolu"...
0x18006d023  jmp     loc_18006CE1F
0x18006d028  lea     rdx, [rbp+SecurityDescriptor]
0x18006d02c  mov     [rbp+var_60], r15
0x18006d030  lea     rcx, [rbp+var_60]
0x18006d034  mov     [rbp+var_58], r15
0x18006d038  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x18006d03d  mov     ebx, eax
0x18006d03f  test    eax, eax
0x18006d041  js      short loc_18006D064
0x18006d043  mov     rcx, [rbp+var_60]
0x18006d047  mov     ebx, r15d
0x18006d04a  mov     rax, [rdi]
0x18006d04d  mov     [rbp+var_60], rax
0x18006d051  mov     rax, [rdi+8]
0x18006d055  mov     [rdi], rcx
0x18006d058  mov     rcx, [rbp+var_58]
0x18006d05c  mov     [rbp+var_58], rax
0x18006d060  mov     [rdi+8], rcx
0x18006d064  lea     rcx, [rbp+var_60]
0x18006d068  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x18006d06d  mov     eax, ebx
0x18006d06f  mov     rcx, [rbp+var_10]
0x18006d073  xor     rcx, rsp; StackCookie
0x18006d076  call    __security_check_cookie
0x18006d07b  mov     rbx, [rsp+80h+arg_8]
0x18006d083  add     rsp, 80h
0x18006d08a  pop     r15
0x18006d08c  pop     r14
0x18006d08e  pop     r13
0x18006d090  pop     r12
0x18006d092  pop     rdi
0x18006d093  pop     rsi
0x18006d094  pop     rbp
0x18006d095  retn
```

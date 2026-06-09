# GetCustomSecurityDescriptor(ushort const *,ushort const *,void *)

- ea: `0x18002cc8c`
- end: `0x18002cf6a`
- name: `?GetCustomSecurityDescriptor@@YAJPEBG0PEAX@Z`
- size: `734`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800108f0`

## callees

- `0x1800130d0`
- `0x1800199fc`
- `0x18001a724`
- `0x18001bbe0`
- `0x18001bc20`
- `0x18002bda4`
- `0x18002bdf4`
- `0x18002bf68`
- `0x18002c264`
- `0x18002cc8c`
- `0x18002d314`
- `0x18002fb4c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18002ce19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18002cef2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18002ce19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18002cef2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002cd41`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18002cd41`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002cdf9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002ced2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002cdf9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002ced2`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002cdd0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002ce77`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002cdd0`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002ce77`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ceaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ceaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cf3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ccfb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002ccfb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ccc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ccc3`

## pseudocode

```c
__int64 __fastcall GetCustomSecurityDescriptor(const unsigned __int16 *a1, const unsigned __int16 *a2, void *a3)
{
  int Error; // ebx
  void *v5; // rax
  const unsigned __int16 *v6; // r8
  ATL::CAcl *v7; // rdi
  unsigned int v8; // r8d
  unsigned __int8 v9; // r9
  struct _ACL *PACL; // rax
  const unsigned __int16 *v11; // r8
  unsigned int v12; // r8d
  unsigned __int8 v13; // r9
  const struct _ACL *v14; // rbx
  unsigned int AclSize; // r14d
  struct _ACL *v16; // rax
  struct _ACL *v17; // rdi
  PSID Sid; // [rsp+20h] [rbp-E0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+28h] [rbp-D8h] BYREF
  WINBOOL bDaclPresent; // [rsp+2Ch] [rbp-D4h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-D0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[128]; // [rsp+80h] [rbp-80h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    SecurityDescriptor[0] = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;CO)(A;CI;KA;;;LA)(A;CIOI;KR;;;WD)",
            1u,
            SecurityDescriptor,
            0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_34;
    }
    pDacl = 0;
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor[0], &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_33:
        LocalFree(SecurityDescriptor[0]);
LABEL_34:
        LocalFree(Sid);
        return (unsigned int)Error;
      }
    }
    Error = -2147024882;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl'::`2'::impl) )
    {
      v5 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
      SecurityDescriptor[1] = v5;
      if ( v5 )
        v7 = (ATL::CAcl *)ATL::CDacl::CDacl((ATL::CDacl *)v5, pDacl);
      else
        v7 = 0;
      if ( v7 )
      {
        ATL::CSid::CSid((ATL::CSid *)v25, (const struct _SID *)Sid, v6);
        if ( ATL::CDacl::AddAllowedAce(v7, (const struct ATL::CSid *)v25, v8, v9) )
        {
          if ( InitializeSecurityDescriptor(a3, 1u) || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            PACL = (struct _ACL *)ATL::CAcl::GetPACL(v7);
            if ( SetSecurityDescriptorDacl(a3, 1, PACL, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
            {
              if ( SetSecurityDescriptorControl(a3, 0x1000u, 0x1000u) )
                Error = 0;
              else
                Error = ResultFromKnownLastError();
            }
          }
        }
        ATL::CSid::~CSid((ATL::CSid *)v25);
      }
      goto LABEL_33;
    }
    ATL::CDacl::CDacl((ATL::CDacl *)v24, pDacl);
    ATL::CSid::CSid((ATL::CSid *)v25, (const struct _SID *)Sid, v11);
    if ( ATL::CDacl::AddAllowedAce((ATL::CDacl *)v24, (const struct ATL::CSid *)v25, v12, v13) )
    {
      if ( InitializeSecurityDescriptor(a3, 1u) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        v14 = ATL::CAcl::GetPACL((ATL::CAcl *)v24);
        AclSize = v14->AclSize;
        v16 = (struct _ACL *)LocalAlloc(0x40u, v14->AclSize);
        v17 = v16;
        if ( !v16 )
        {
          Error = -2147024882;
          goto LABEL_32;
        }
        memcpy_0(v16, v14, AclSize);
        if ( SetSecurityDescriptorDacl(a3, 1, v17, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( SetSecurityDescriptorControl(a3, 0x1000u, 0x1000u) )
          {
            Error = 0;
            goto LABEL_32;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            goto LABEL_32;
        }
        LocalFree(v17);
      }
    }
LABEL_32:
    ATL::CSid::~CSid((ATL::CSid *)v25);
    ATL::CDacl::~CDacl((ATL::CDacl *)v24);
    goto LABEL_33;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002cc8c  mov     [rsp-8+arg_8], rbx
0x18002cc91  push    rbp
0x18002cc92  push    rsi
0x18002cc93  push    rdi
0x18002cc94  push    r12
0x18002cc96  push    r14
0x18002cc98  lea     rbp, [rsp-10h]
0x18002cc9d  sub     rsp, 110h
0x18002cca4  mov     rax, cs:__security_cookie
0x18002ccab  xor     rax, rsp
0x18002ccae  mov     [rbp+30h+var_30], rax
0x18002ccb2  mov     rsi, r8
0x18002ccb5  mov     [rsp+130h+Sid], 0
0x18002ccbe  lea     rdx, [rsp+130h+Sid]; Sid
0x18002ccc3  call    cs:__imp_ConvertStringSidToSidW
0x18002ccc9  test    eax, eax
0x18002cccb  jnz     short loc_18002CCDC
0x18002cccd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ccd2  mov     ebx, eax
0x18002ccd4  test    eax, eax
0x18002ccd6  js      loc_18002CF45
0x18002ccdc  mov     [rsp+130h+SecurityDescriptor], 0
0x18002cce5  xor     r9d, r9d; SecurityDescriptorSize
0x18002cce8  lea     r8, [rsp+130h+SecurityDescriptor]; SecurityDescriptor
0x18002cced  lea     r12d, [r9+1]
0x18002ccf1  mov     edx, r12d; StringSDRevision
0x18002ccf4  lea     rcx, aDACioiKaSyACio; "D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;CO)(A;CI"...
0x18002ccfb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002cd01  test    eax, eax
0x18002cd03  jnz     short loc_18002CD14
0x18002cd05  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cd0a  mov     ebx, eax
0x18002cd0c  test    eax, eax
0x18002cd0e  js      loc_18002CF3A
0x18002cd14  mov     [rsp+130h+pDacl], 0
0x18002cd1d  mov     [rsp+130h+bDaclDefaulted], 0
0x18002cd25  mov     [rsp+130h+bDaclPresent], 0
0x18002cd2d  lea     r9, [rsp+130h+bDaclDefaulted]; lpbDaclDefaulted
0x18002cd32  lea     r8, [rsp+130h+pDacl]; pDacl
0x18002cd37  lea     rdx, [rsp+130h+bDaclPresent]; lpbDaclPresent
0x18002cd3c  mov     rcx, [rsp+130h+SecurityDescriptor]; pSecurityDescriptor
0x18002cd41  call    cs:__imp_GetSecurityDescriptorDacl
0x18002cd47  test    eax, eax
0x18002cd49  jnz     short loc_18002CD5A
0x18002cd4b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cd50  mov     ebx, eax
0x18002cd52  test    eax, eax
0x18002cd54  js      loc_18002CF2F
0x18002cd5a  mov     ebx, 8007000Eh
0x18002cd5f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::GetImpl(void)'::`2'::impl
0x18002cd66  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_TextInputManagementServiceLeak>::__private_IsEnabled(void)
0x18002cd6b  test    al, al
0x18002cd6d  jnz     loc_18002CE3C
0x18002cd73  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cd7a  mov     ecx, 38h ; '8'; unsigned __int64
0x18002cd7f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cd84  mov     [rsp+130h+var_F0], rax
0x18002cd89  test    rax, rax
0x18002cd8c  jz      short loc_18002CDA0
0x18002cd8e  mov     rdx, [rsp+130h+pDacl]; struct _ACL *
0x18002cd93  mov     rcx, rax; this
0x18002cd96  call    ??0CDacl@ATL@@QEAA@AEBU_ACL@@@Z; ATL::CDacl::CDacl(_ACL const &)
0x18002cd9b  mov     rdi, rax
0x18002cd9e  jmp     short loc_18002CDA2
0x18002cda0  xor     edi, edi
0x18002cda2  test    rdi, rdi
0x18002cda5  jz      loc_18002CF2F
0x18002cdab  mov     rdx, [rsp+130h+Sid]; struct _SID *
0x18002cdb0  lea     rcx, [rbp+30h+var_B0]; this
0x18002cdb4  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18002cdb9  nop
0x18002cdba  lea     rdx, [rbp+30h+var_B0]; struct ATL::CSid *
0x18002cdbe  mov     rcx, rdi; this
0x18002cdc1  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002cdc6  test    al, al
0x18002cdc8  jz      short loc_18002CE2E
0x18002cdca  mov     edx, r12d; dwRevision
0x18002cdcd  mov     rcx, rsi; pSecurityDescriptor
0x18002cdd0  call    cs:__imp_InitializeSecurityDescriptor
0x18002cdd6  test    eax, eax
0x18002cdd8  jnz     short loc_18002CDE5
0x18002cdda  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cddf  mov     ebx, eax
0x18002cde1  test    eax, eax
0x18002cde3  js      short loc_18002CE2E
0x18002cde5  mov     rcx, rdi; this
0x18002cde8  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18002cded  xor     r9d, r9d; bDaclDefaulted
0x18002cdf0  mov     r8, rax; pDacl
0x18002cdf3  mov     edx, r12d; bDaclPresent
0x18002cdf6  mov     rcx, rsi; pSecurityDescriptor
0x18002cdf9  call    cs:__imp_SetSecurityDescriptorDacl
0x18002cdff  test    eax, eax
0x18002ce01  jnz     short loc_18002CE0E
0x18002ce03  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ce08  mov     ebx, eax
0x18002ce0a  test    eax, eax
0x18002ce0c  js      short loc_18002CE2E
0x18002ce0e  mov     edx, 1000h; ControlBitsOfInterest
0x18002ce13  mov     r8d, edx; ControlBitsToSet
0x18002ce16  mov     rcx, rsi; pSecurityDescriptor
0x18002ce19  call    cs:__imp_SetSecurityDescriptorControl
0x18002ce1f  test    eax, eax
0x18002ce21  jz      short loc_18002CE27
0x18002ce23  xor     ebx, ebx
0x18002ce25  jmp     short loc_18002CE2E
0x18002ce27  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ce2c  mov     ebx, eax
0x18002ce2e  lea     rcx, [rbp+30h+var_B0]; this
0x18002ce32  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ce37  jmp     loc_18002CF2F
0x18002ce3c  mov     rdx, [rsp+130h+pDacl]; struct _ACL *
0x18002ce41  lea     rcx, [rsp+130h+var_E8]; this
0x18002ce46  call    ??0CDacl@ATL@@QEAA@AEBU_ACL@@@Z; ATL::CDacl::CDacl(_ACL const &)
0x18002ce4b  nop
0x18002ce4c  mov     rdx, [rsp+130h+Sid]; struct _SID *
0x18002ce51  lea     rcx, [rbp+30h+var_B0]; this
0x18002ce55  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18002ce5a  nop
0x18002ce5b  lea     rdx, [rbp+30h+var_B0]; struct ATL::CSid *
0x18002ce5f  lea     rcx, [rsp+130h+var_E8]; this
0x18002ce64  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002ce69  test    al, al
0x18002ce6b  jz      loc_18002CF1B
0x18002ce71  mov     edx, r12d; dwRevision
0x18002ce74  mov     rcx, rsi; pSecurityDescriptor
0x18002ce77  call    cs:__imp_InitializeSecurityDescriptor
0x18002ce7d  test    eax, eax
0x18002ce7f  jnz     short loc_18002CE90
0x18002ce81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002ce86  mov     ebx, eax
0x18002ce88  test    eax, eax
0x18002ce8a  js      loc_18002CF1B
0x18002ce90  lea     rcx, [rsp+130h+var_E8]; this
0x18002ce95  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18002ce9a  mov     rbx, rax
0x18002ce9d  movzx   r14d, word ptr [rax+2]
0x18002cea2  mov     edx, r14d; uBytes
0x18002cea5  mov     ecx, 40h ; '@'; uFlags
0x18002ceaa  call    cs:__imp_LocalAlloc
0x18002ceb0  mov     rdi, rax
0x18002ceb3  test    rax, rax
0x18002ceb6  jz      short loc_18002CF16
0x18002ceb8  mov     r8d, r14d; Size
0x18002cebb  mov     rdx, rbx; Src
0x18002cebe  mov     rcx, rax; void *
0x18002cec1  call    memcpy_0
0x18002cec6  xor     r9d, r9d; bDaclDefaulted
0x18002cec9  mov     r8, rdi; pDacl
0x18002cecc  mov     edx, r12d; bDaclPresent
0x18002cecf  mov     rcx, rsi; pSecurityDescriptor
0x18002ced2  call    cs:__imp_SetSecurityDescriptorDacl
0x18002ced8  test    eax, eax
0x18002ceda  jnz     short loc_18002CEE7
0x18002cedc  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cee1  mov     ebx, eax
0x18002cee3  test    eax, eax
0x18002cee5  js      short loc_18002CF0B
0x18002cee7  mov     edx, 1000h; ControlBitsOfInterest
0x18002ceec  mov     r8d, edx; ControlBitsToSet
0x18002ceef  mov     rcx, rsi; pSecurityDescriptor
0x18002cef2  call    cs:__imp_SetSecurityDescriptorControl
0x18002cef8  test    eax, eax
0x18002cefa  jz      short loc_18002CF00
0x18002cefc  xor     ebx, ebx
0x18002cefe  jmp     short loc_18002CF1B
0x18002cf00  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002cf05  mov     ebx, eax
0x18002cf07  test    eax, eax
0x18002cf09  jns     short loc_18002CF1B
0x18002cf0b  mov     rcx, rdi; hMem
0x18002cf0e  call    cs:__imp_LocalFree
0x18002cf14  jmp     short loc_18002CF1B
0x18002cf16  mov     ebx, 8007000Eh
0x18002cf1b  lea     rcx, [rbp+30h+var_B0]; this
0x18002cf1f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002cf24  nop
0x18002cf25  lea     rcx, [rsp+130h+var_E8]; this
0x18002cf2a  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x18002cf2f  mov     rcx, [rsp+130h+SecurityDescriptor]; hMem
0x18002cf34  call    cs:__imp_LocalFree
0x18002cf3a  mov     rcx, [rsp+130h+Sid]; hMem
0x18002cf3f  call    cs:__imp_LocalFree
0x18002cf45  mov     eax, ebx
0x18002cf47  mov     rcx, [rbp+30h+var_30]
0x18002cf4b  xor     rcx, rsp; StackCookie
0x18002cf4e  call    __security_check_cookie
0x18002cf53  mov     rbx, [rsp+130h+arg_8]
0x18002cf5b  add     rsp, 110h
0x18002cf62  pop     r14
0x18002cf64  pop     r12
0x18002cf66  pop     rdi
0x18002cf67  pop     rsi
0x18002cf68  pop     rbp
0x18002cf69  retn
```

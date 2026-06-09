# DetermineLowRightsKeySecurityDescriptor(HKEY__ *,void * *)

- ea: `0x18001039c`
- end: `0x1800109c7`
- name: `?DetermineLowRightsKeySecurityDescriptor@@YAJPEAUHKEY__@@PEAPEAX@Z`
- size: `1579`
- prototype: `__int64 __fastcall(HKEY hKey, void **)`
- caller_count: `3`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f9d0`
- `0x1800101ac`
- `0x1800478e4`

## callees

- `0x18000f744`
- `0x18001039c`
- `0x1800109d0`
- `0x180010dc0`
- `0x180010e30`
- `0x180010fb0`
- `0x180011a30`
- `0x180011d78`
- `0x180011dc4`
- `0x180011f50`
- `0x180012070`
- `0x18001218c`
- `0x180012288`
- `0x18001f3b0`
- `0x18002bbac`
- `0x18002bd78`
- `0x18002bd9c`
- `0x18002c180`
- `0x18002c3d0`
- `0x18002c714`
- `0x18002ccf0`
- `0x180031960`
- `0x180031eb0`
- `0x180032736`
- `0x1800327e0`
- `0x1800327f8`
- `0x180047cb8`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001071b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010765`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001079e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010869`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800108a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010968`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001071b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010765`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001079e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010869`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800108a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010968`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010698`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180010698`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010945`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010945`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800103f0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180010431`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800103f0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x180010431`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180010705`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180010705`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800104fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010921`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800104fc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180010921`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800107aa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800107aa`

## pseudocode

```c
__int64 __fastcall DetermineLowRightsKeySecurityDescriptor(HKEY hKey, void **a2)
{
  struct _SECURITY_DESCRIPTOR *v4; // r15
  unsigned int v5; // edi
  struct _SECURITY_DESCRIPTOR *v6; // rax
  LSTATUS KeySecurity; // eax
  PSECURITY_DESCRIPTOR v8; // rcx
  const struct _ACL *v9; // rsi
  struct _ACL *PACL; // rsi
  const struct ATL::CSid *v11; // rdx
  unsigned int v12; // r8d
  unsigned __int8 v13; // r9
  PSECURITY_DESCRIPTOR v14; // rcx
  size_t Length; // r12
  struct _ACL *v16; // rsi
  const struct _ACL *v17; // rax
  int v18; // r12d
  BOOL v19; // edx
  unsigned __int64 SecurityDescriptorLength; // rsi
  void *v21; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  int Error; // ebx
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp-178h] BYREF
  void **v29; // [rsp+68h] [rbp-170h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+70h] [rbp-168h]
  WINBOOL bDaclPresent; // [rsp+78h] [rbp-160h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+7Ch] [rbp-15Ch] BYREF
  PACL pDacl; // [rsp+80h] [rbp-158h] BYREF
  void **v34; // [rsp+88h] [rbp-150h] BYREF
  void *Block; // [rsp+90h] [rbp-148h]
  char v36; // [rsp+98h] [rbp-140h]
  int v37; // [rsp+9Ch] [rbp-13Ch]
  __int128 v38; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-128h]
  int v40; // [rsp+B8h] [rbp-120h]
  void **v41; // [rsp+C0h] [rbp-118h] BYREF
  void *v42; // [rsp+C8h] [rbp-110h]
  char v43; // [rsp+D0h] [rbp-108h]
  int v44; // [rsp+D4h] [rbp-104h]
  __int128 v45; // [rsp+D8h] [rbp-100h] BYREF
  __int64 v46; // [rsp+E8h] [rbp-F0h]
  int v47; // [rsp+F0h] [rbp-E8h]
  struct _SECURITY_DESCRIPTOR *v48; // [rsp+F8h] [rbp-E0h]
  void **v49; // [rsp+100h] [rbp-D8h]
  struct _SID_IDENTIFIER_AUTHORITY v50; // [rsp+110h] [rbp-C8h] BYREF
  _BYTE v51[128]; // [rsp+120h] [rbp-B8h] BYREF

  v49 = a2;
  cbSecurityDescriptor = 0;
  v4 = 0;
  v5 = 0;
  if ( RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor) != 122 )
    goto LABEL_31;
  v6 = (struct _SECURITY_DESCRIPTOR *)operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v6;
  v48 = v6;
  if ( !v6 )
  {
    v5 = -2147024882;
    goto LABEL_31;
  }
  KeySecurity = RegGetKeySecurity(hKey, 4u, v6, &cbSecurityDescriptor);
  if ( KeySecurity )
  {
    if ( KeySecurity > 0 )
      v5 = (unsigned __int16)KeySecurity | 0x80070000;
    else
      v5 = KeySecurity;
    goto LABEL_31;
  }
  v29 = &ATL::CSecurityDesc::`vftable';
  pSecurityDescriptor = 0;
  *(_DWORD *)v50.Value = 0;
  *(_WORD *)&v50.Value[4] = 1280;
  v42 = 0;
  v43 = 0;
  v44 = 2;
  v41 = &ATL::CDacl::`vftable';
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v8 = 0;
  if ( v4 )
  {
    ((void (__fastcall *)(void ***))v29[1])(&v29);
    ATL::CSecurityDesc::Init((ATL::CSecurityDesc *)&v29, v4);
    v8 = pSecurityDescriptor;
  }
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( v8 && GetSecurityDescriptorDacl(v8, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    if ( bDaclPresent )
    {
      v9 = pDacl;
      if ( pDacl )
      {
        ((void (__fastcall *)(void ***))v41[2])(&v41);
        ATL::CDacl::Copy((ATL::CDacl *)&v41, v9);
      }
      else
      {
        ATL::CAcl::SetNull((ATL::CAcl *)&v41);
      }
    }
    else
    {
      ATL::CAcl::SetEmpty((ATL::CAcl *)&v41);
    }
  }
  PACL = (struct _ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)&v41);
  EditAppContainerMask(PACL);
  Block = 0;
  v36 = 0;
  v37 = 2;
  v34 = &ATL::CDacl::`vftable';
  v38 = 0;
  v39 = 0;
  v40 = 0;
  ATL::CDacl::Copy((ATL::CDacl *)&v34, PACL);
  v11 = (const struct ATL::CSid *)ATL::CSid::CSid((ATL::CSid *)v51, &v50, 6u);
  LOBYTE(PACL) = ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v34, v11, v12, v13);
  ATL::CSid::~CSid((ATL::CSid *)v51);
  if ( !(_BYTE)PACL )
  {
    v5 = -2147467259;
    v34 = &ATL::CDacl::`vftable';
    ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v34);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v38);
    v34 = &ATL::CAcl::`vftable';
    free(Block);
    v41 = &ATL::CDacl::`vftable';
    ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v41);
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v45);
    v41 = &ATL::CAcl::`vftable';
    free(v42);
    v29 = &ATL::CSecurityDesc::`vftable';
    ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v29);
    goto LABEL_31;
  }
  v14 = pSecurityDescriptor;
  if ( pSecurityDescriptor )
  {
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)&v29);
    v14 = pSecurityDescriptor;
  }
  pDacl = 0;
  if ( v14 )
  {
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(v14, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)&v29);
  }
  if ( !v36 && ((unsigned int (__fastcall *)(void ***))v34[1])(&v34) )
  {
    Length = ATL::CAcl::GetLength((ATL::CAcl *)&v34);
    v16 = (struct _ACL *)malloc(Length);
    if ( !v16 )
      ATL::AtlThrowImpl(-2147024882);
    v17 = ATL::CAcl::GetPACL((ATL::CAcl *)&v34);
    if ( Length )
    {
      if ( !v17 )
      {
        memset_0(v16, 0, (unsigned int)Length);
        v18 = 22;
        *(_DWORD *)_o__errno(v24, v23, v25, v26, -1618417719, 1911656217, -1669870755) = 22;
        invalid_parameter_noinfo();
        goto LABEL_23;
      }
      memcpy_0(v16, v17, (unsigned int)Length);
    }
    v18 = 0;
LABEL_23:
    ATL::AtlCrtErrorCheck(v18);
    goto LABEL_24;
  }
  v16 = 0;
LABEL_24:
  if ( v36 || (v19 = 0, v16) )
    v19 = 1;
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, v19, v16, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v16);
    ATL::AtlThrowImpl(Error);
  }
  free(pDacl);
  ATL::CSecurityDesc::MakeSelfRelative((ATL::CSecurityDesc *)&v29);
  v34 = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v34);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v38);
  v34 = &ATL::CAcl::`vftable';
  free(Block);
  v41 = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v41);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v45);
  v41 = &ATL::CAcl::`vftable';
  free(v42);
  SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
  v21 = operator new[](SecurityDescriptorLength, (const struct std::nothrow_t *)&std::nothrow);
  *a2 = v21;
  if ( v21 )
    memcpy_0(v21, pSecurityDescriptor, SecurityDescriptorLength);
  else
    v5 = -2147024882;
  v29 = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v29);
LABEL_31:
  operator delete(v4);
  return v5;
}

```

## disassembly

```asm
0x18001039c  mov     [rsp+arg_10], rbx
0x1800103a1  mov     [rsp+arg_18], rsi
0x1800103a6  push    rdi
0x1800103a7  push    r12
0x1800103a9  push    r13
0x1800103ab  push    r14
0x1800103ad  push    r15
0x1800103af  sub     rsp, 1B0h
0x1800103b6  mov     rax, cs:__security_cookie
0x1800103bd  xor     rax, rsp
0x1800103c0  mov     [rsp+1D8h+var_38], rax
0x1800103c8  mov     r13, rdx
0x1800103cb  mov     rsi, rcx
0x1800103ce  mov     [rsp+1D8h+var_D8], rdx
0x1800103d6  xor     ebx, ebx
0x1800103d8  mov     [rsp+1D8h+cbSecurityDescriptor], ebx
0x1800103dc  mov     r15d, ebx
0x1800103df  mov     edi, ebx
0x1800103e1  lea     r9, [rsp+1D8h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800103e6  xor     r8d, r8d; pSecurityDescriptor
0x1800103e9  lea     r14d, [rbx+4]
0x1800103ed  mov     edx, r14d; SecurityInformation
0x1800103f0  call    cs:__imp_RegGetKeySecurity
0x1800103f6  cmp     eax, 7Ah ; 'z'
0x1800103f9  jnz     loc_1800107E1
0x1800103ff  mov     ecx, [rsp+1D8h+cbSecurityDescriptor]; unsigned __int64
0x180010403  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001040a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001040f  mov     r15, rax
0x180010412  mov     [rsp+1D8h+var_E0], rax
0x18001041a  test    rax, rax
0x18001041d  jz      loc_1800109BD
0x180010423  lea     r9, [rsp+1D8h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180010428  mov     r8, rax; pSecurityDescriptor
0x18001042b  mov     edx, r14d; SecurityInformation
0x18001042e  mov     rcx, rsi; hKey
0x180010431  call    cs:__imp_RegGetKeySecurity
0x180010437  test    eax, eax
0x180010439  jnz     loc_1800108D2
0x18001043f  lea     r14, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x180010446  mov     [rsp+1D8h+var_170], r14
0x18001044b  mov     [rsp+1D8h+pSecurityDescriptor], rbx
0x180010450  mov     dword ptr [rsp+1D8h+var_C8.Value], ebx
0x180010457  mov     word ptr [rsp+1D8h+var_C8.Value+4], 500h
0x180010461  mov     [rsp+1D8h+var_110], rbx
0x180010469  mov     [rsp+1D8h+var_108], bl
0x180010470  lea     r12d, [rbx+2]
0x180010474  mov     [rsp+1D8h+var_104], r12d
0x18001047c  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180010483  mov     [rsp+1D8h+var_118], rax
0x18001048b  xorps   xmm0, xmm0
0x18001048e  movdqu  [rsp+1D8h+var_100], xmm0
0x180010497  mov     [rsp+1D8h+var_F0], rbx
0x18001049f  mov     [rsp+1D8h+var_E8], ebx
0x1800104a6  mov     rcx, [rsp+1D8h+pSecurityDescriptor]
0x1800104ab  cmp     rcx, r15
0x1800104ae  jz      short loc_1800104D5
0x1800104b0  mov     rax, [rsp+1D8h+var_170]
0x1800104b5  lea     rcx, [rsp+1D8h+var_170]
0x1800104ba  mov     rax, [rax+8]
0x1800104be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104c3  mov     rdx, r15; struct _SECURITY_DESCRIPTOR *
0x1800104c6  lea     rcx, [rsp+1D8h+var_170]; this
0x1800104cb  call    ?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z; ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)
0x1800104d0  mov     rcx, [rsp+1D8h+pSecurityDescriptor]; pSecurityDescriptor
0x1800104d5  mov     [rsp+1D8h+pDacl], rbx
0x1800104dd  mov     [rsp+1D8h+bDaclPresent], ebx
0x1800104e1  mov     [rsp+1D8h+bDaclDefaulted], ebx
0x1800104e5  test    rcx, rcx
0x1800104e8  jz      short loc_18001054A
0x1800104ea  lea     r9, [rsp+1D8h+bDaclDefaulted]; lpbDaclDefaulted
0x1800104ef  lea     r8, [rsp+1D8h+pDacl]; pDacl
0x1800104f7  lea     rdx, [rsp+1D8h+bDaclPresent]; lpbDaclPresent
0x1800104fc  call    cs:__imp_GetSecurityDescriptorDacl
0x180010502  test    eax, eax
0x180010504  jz      short loc_18001054A
0x180010506  lea     rcx, [rsp+1D8h+var_118]; this
0x18001050e  cmp     [rsp+1D8h+bDaclPresent], ebx
0x180010512  jz      loc_1800108E9
0x180010518  mov     rsi, [rsp+1D8h+pDacl]
0x180010520  test    rsi, rsi
0x180010523  jz      loc_180010818
0x180010529  mov     rax, [rsp+1D8h+var_118]
0x180010531  mov     rax, [rax+10h]
0x180010535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001053a  mov     rdx, rsi; struct _ACL *
0x18001053d  lea     rcx, [rsp+1D8h+var_118]; this
0x180010545  call    ?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z; ATL::CDacl::Copy(_ACL const &)
0x18001054a  lea     rcx, [rsp+1D8h+var_118]; this
0x180010552  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x180010557  mov     rsi, rax
0x18001055a  mov     rcx, rax; pAcl
0x18001055d  call    ?EditAppContainerMask@@YAXPEAU_ACL@@@Z; EditAppContainerMask(_ACL *)
0x180010562  mov     [rsp+1D8h+Block], rbx
0x18001056a  mov     [rsp+1D8h+var_140], bl
0x180010571  mov     [rsp+1D8h+var_13C], r12d
0x180010579  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180010580  mov     [rsp+1D8h+var_150], r12
0x180010588  xorps   xmm0, xmm0
0x18001058b  movdqu  [rsp+1D8h+var_138], xmm0
0x180010594  mov     [rsp+1D8h+var_128], rbx
0x18001059c  mov     [rsp+1D8h+var_120], ebx
0x1800105a3  mov     rdx, rsi; struct _ACL *
0x1800105a6  lea     rcx, [rsp+1D8h+var_150]; this
0x1800105ae  call    ?Copy@CDacl@ATL@@AEAAXAEBU_ACL@@@Z; ATL::CDacl::Copy(_ACL const &)
0x1800105b3  nop
0x1800105b4  mov     [rsp+1D8h+var_188], rbx
0x1800105b9  mov     [rsp+1D8h+var_190], rbx
0x1800105be  mov     [rsp+1D8h+var_198], 51771D47h
0x1800105c6  mov     [rsp+1D8h+var_1A0], 0F907DC14h
0x1800105ce  mov     [rsp+1D8h+var_1A8], 9C77CB5Dh
0x1800105d6  mov     [rsp+1D8h+var_1B0], 71F18F19h
0x1800105de  mov     [rsp+1D8h+var_1B8], 9F88E7C9h
0x1800105e6  mov     r9d, 50h ; 'P'
0x1800105ec  lea     r8d, [r9-4Ah]; unsigned __int8
0x1800105f0  lea     rdx, [rsp+1D8h+var_C8]; struct _SID_IDENTIFIER_AUTHORITY *
0x1800105f8  lea     rcx, [rsp+1D8h+var_B8]; this
0x180010600  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x180010605  nop
0x180010606  mov     rdx, rax; struct ATL::CSid *
0x180010609  lea     rcx, [rsp+1D8h+var_150]; this
0x180010611  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x180010616  mov     sil, al
0x180010619  lea     rcx, [rsp+1D8h+var_B8]; this
0x180010621  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180010626  test    sil, sil
0x180010629  jz      loc_18001082B
0x18001062f  mov     rcx, [rsp+1D8h+pSecurityDescriptor]; pSecurityDescriptor
0x180010634  test    rcx, rcx
0x180010637  jnz     loc_1800108F3
0x18001063d  mov     [rsp+1D8h+pDacl], rbx
0x180010645  test    rcx, rcx
0x180010648  jnz     loc_180010907
0x18001064e  lea     rcx, [rsp+1D8h+var_170]; this
0x180010653  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x180010658  cmp     [rsp+1D8h+var_140], bl
0x18001065f  jnz     loc_180010823
0x180010665  mov     rax, [rsp+1D8h+var_150]
0x18001066d  lea     rcx, [rsp+1D8h+var_150]
0x180010675  mov     rax, [rax+8]
0x180010679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001067e  test    eax, eax
0x180010680  jz      loc_180010823
0x180010686  lea     rcx, [rsp+1D8h+var_150]; this
0x18001068e  call    ?GetLength@CAcl@ATL@@QEBAIXZ; ATL::CAcl::GetLength(void)
0x180010693  mov     r12d, eax
0x180010696  mov     ecx, eax; Size
0x180010698  call    cs:__imp_malloc
0x18001069e  mov     rsi, rax
0x1800106a1  test    rax, rax
0x1800106a4  jz      loc_180010934
0x1800106aa  lea     rcx, [rsp+1D8h+var_150]; this
0x1800106b2  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1800106b7  test    r12, r12
0x1800106ba  jz      short loc_1800106D3
0x1800106bc  mov     r8d, r12d; Size
0x1800106bf  mov     rcx, rsi; void *
0x1800106c2  test    rax, rax
0x1800106c5  jz      loc_18001093E
0x1800106cb  mov     rdx, rax; Src
0x1800106ce  call    memcpy_0
0x1800106d3  mov     r12d, ebx
0x1800106d6  mov     ecx, r12d; int
0x1800106d9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800106de  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x1800106e5  cmp     [rsp+1D8h+var_140], bl
0x1800106ec  jnz     short loc_1800106F5
0x1800106ee  test    rsi, rsi
0x1800106f1  mov     edx, ebx
0x1800106f3  jz      short loc_1800106FA
0x1800106f5  mov     edx, 1; bDaclPresent
0x1800106fa  xor     r9d, r9d; bDaclDefaulted
0x1800106fd  mov     r8, rsi; pDacl
0x180010700  mov     rcx, [rsp+1D8h+pSecurityDescriptor]; pSecurityDescriptor
0x180010705  call    cs:__imp_SetSecurityDescriptorDacl
0x18001070b  test    eax, eax
0x18001070d  jz      loc_18001095E
0x180010713  mov     rcx, [rsp+1D8h+pDacl]; Block
0x18001071b  call    cs:__imp_free
0x180010721  lea     rcx, [rsp+1D8h+var_170]; this
0x180010726  call    ?MakeSelfRelative@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeSelfRelative(void)
0x18001072b  nop
0x18001072c  mov     [rsp+1D8h+var_150], r12
0x180010734  lea     rcx, [rsp+1D8h+var_150]; this
0x18001073c  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180010741  lea     rcx, [rsp+1D8h+var_138]
0x180010749  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x18001074e  lea     rsi, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180010755  mov     [rsp+1D8h+var_150], rsi
0x18001075d  mov     rcx, [rsp+1D8h+Block]; Block
0x180010765  call    cs:__imp_free
0x18001076b  nop
0x18001076c  mov     [rsp+1D8h+var_118], r12
0x180010774  lea     rcx, [rsp+1D8h+var_118]; this
0x18001077c  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180010781  lea     rcx, [rsp+1D8h+var_100]
0x180010789  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x18001078e  mov     [rsp+1D8h+var_118], rsi
0x180010796  mov     rcx, [rsp+1D8h+var_110]; Block
0x18001079e  call    cs:__imp_free
0x1800107a4  nop
0x1800107a5  mov     rcx, [rsp+1D8h+pSecurityDescriptor]; pSecurityDescriptor
0x1800107aa  call    cs:__imp_GetSecurityDescriptorLength
0x1800107b0  mov     esi, eax
0x1800107b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800107b9  mov     ecx, eax; unsigned __int64
0x1800107bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800107c0  mov     [r13+0], rax
0x1800107c4  test    rax, rax
0x1800107c7  jnz     loc_1800108BD
0x1800107cd  mov     edi, 8007000Eh
0x1800107d2  mov     [rsp+1D8h+var_170], r14
0x1800107d7  lea     rcx, [rsp+1D8h+var_170]; this
0x1800107dc  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800107e1  mov     rcx, r15; void *
0x1800107e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800107e9  mov     eax, edi
0x1800107eb  mov     rcx, [rsp+1D8h+var_38]
0x1800107f3  xor     rcx, rsp; StackCookie
0x1800107f6  call    __security_check_cookie
0x1800107fb  lea     r11, [rsp+1D8h+var_28]
0x180010803  mov     rbx, [r11+40h]
0x180010807  mov     rsi, [r11+48h]
0x18001080b  mov     rsp, r11
0x18001080e  pop     r15
0x180010810  pop     r14
0x180010812  pop     r13
0x180010814  pop     r12
0x180010816  pop     rdi
0x180010817  retn
0x180010818  call    ?SetNull@CAcl@ATL@@QEAAXXZ; ATL::CAcl::SetNull(void)
0x18001081d  nop
0x18001081e  jmp     loc_18001054A
0x180010823  mov     rsi, rbx
0x180010826  jmp     loc_1800106E5
0x18001082b  mov     edi, 80004005h
0x180010830  mov     [rsp+1D8h+var_150], r12
0x180010838  lea     rcx, [rsp+1D8h+var_150]; this
0x180010840  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180010845  lea     rcx, [rsp+1D8h+var_138]
0x18001084d  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180010852  lea     rsi, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180010859  mov     [rsp+1D8h+var_150], rsi
0x180010861  mov     rcx, [rsp+1D8h+Block]; Block
0x180010869  call    cs:__imp_free
0x18001086f  nop
0x180010870  mov     [rsp+1D8h+var_118], r12
0x180010878  lea     rcx, [rsp+1D8h+var_118]; this
0x180010880  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180010885  lea     rcx, [rsp+1D8h+var_100]
0x18001088d  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180010892  mov     [rsp+1D8h+var_118], rsi
0x18001089a  mov     rcx, [rsp+1D8h+var_110]; Block
0x1800108a2  call    cs:__imp_free
0x1800108a8  nop
0x1800108a9  mov     [rsp+1D8h+var_170], r14
0x1800108ae  lea     rcx, [rsp+1D8h+var_170]; this
0x1800108b3  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x1800108b8  jmp     loc_1800107E1
0x1800108bd  mov     r8, rsi; Size
0x1800108c0  mov     rdx, [rsp+1D8h+pSecurityDescriptor]; Src
0x1800108c5  mov     rcx, rax; void *
0x1800108c8  call    memcpy_0
0x1800108cd  jmp     loc_1800107D2
0x1800108d2  jg      short loc_1800108DB
0x1800108d4  mov     edi, eax
0x1800108d6  jmp     loc_1800107E1
0x1800108db  movzx   edi, ax
0x1800108de  or      edi, 80070000h
0x1800108e4  jmp     loc_1800107E1
0x1800108e9  call    ?SetEmpty@CAcl@ATL@@QEAAXXZ; ATL::CAcl::SetEmpty(void)
0x1800108ee  jmp     loc_18001054A
0x1800108f3  lea     rcx, [rsp+1D8h+var_170]; this
0x1800108f8  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x1800108fd  mov     rcx, [rsp+1D8h+pSecurityDescriptor]
0x180010902  jmp     loc_18001063D
0x180010907  mov     [rsp+1D8h+bDaclDefaulted], ebx
0x18001090b  mov     [rsp+1D8h+bDaclPresent], ebx
0x18001090f  lea     r9, [rsp+1D8h+bDaclDefaulted]; lpbDaclDefaulted
0x180010914  lea     r8, [rsp+1D8h+pDacl]; pDacl
0x18001091c  lea     rdx, [rsp+1D8h+bDaclPresent]; lpbDaclPresent
0x180010921  call    cs:__imp_GetSecurityDescriptorDacl
0x180010927  test    eax, eax
0x180010929  jnz     loc_180010658
0x18001092f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180010934  mov     ecx, 8007000Eh; int
0x180010939  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001093e  xor     edx, edx; Val
0x180010940  call    memset_0
0x180010945  call    cs:__imp__o__errno
0x18001094b  mov     r12d, 16h
0x180010951  mov     [rax], r12d
0x180010954  call    _invalid_parameter_noinfo
0x180010959  jmp     loc_1800106D6
0x18001095e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180010963  mov     ebx, eax
0x180010965  mov     rcx, rsi; Block
0x180010968  call    cs:__imp_free
0x18001096e  mov     ecx, ebx; int
0x180010970  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```

# Jot::CIndexerServer::CreateNewListeningPipe_Throw(void)

- ea: `0x180432b50`
- end: `0x180432fd0`
- name: `?CreateNewListeningPipe_Throw@CIndexerServer@Jot@@AEAAXXZ`
- size: `1152`
- prototype: `void __fastcall(Jot::CIndexerServer *this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180582180`

## callees

- `0x18005ccc0`
- `0x1802b0bc4`
- `0x1802e2251`
- `0x1802e3f10`
- `0x1802e5170`
- `0x1802e5190`
- `0x180432b50`
- `0x180432fd0`
- `0x180433134`
- `0x180433190`
- `0x18043331c`
- `0x180433380`
- `0x1804335a4`
- `0x180433848`
- `0x1804339ac`
- `0x180433a20`
- `0x180433a80`
- `0x180433ae4`
- `0x180433bd4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180432fa7`
- `KERNEL32!GetLastError` at `0x180432fbd`
- `KERNEL32!GetLastError` at `0x180432fa7`
- `KERNEL32!GetLastError` at `0x180432fbd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432d73`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432db9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432de9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432e6a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432e89`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432eb3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432ee1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f22`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f6d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f9c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432d73`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432db9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432de9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432e6a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432e89`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432eb3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432ee1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f22`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f6d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180432f9c`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180432e5f`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180432f17`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180432e5f`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x180432f17`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180432e7e`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180432f37`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180432e7e`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180432f37`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180432ea2`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180432f5c`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180432ea2`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180432f5c`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180432ecc`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180432f87`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180432ecc`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x180432f87`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180432d5a`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180432d9f`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180432d5a`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180432d9f`

## pseudocode

```c
void __fastcall Jot::CIndexerServer::CreateNewListeningPipe_Throw(
        Jot::CIndexerServer *this,
        unsigned __int64 a2,
        unsigned int a3)
{
  __int64 v4; // rcx
  ACL *v5; // rax
  unsigned int v6; // edx
  void *v7; // r8
  Jot::CNamedPipeServer *v8; // rbx
  void (__fastcall ***v9)(_QWORD); // rbx
  __int64 v10; // rcx
  unsigned int v11; // r8d
  unsigned __int8 v12; // r9
  bool v13; // r8
  PSECURITY_DESCRIPTOR v14; // rax
  Jot::CNamedPipeServer *v15; // rbx
  const WCHAR *v16; // rax
  LPSECURITY_ATTRIBUTES v17; // r8
  unsigned int v18; // r9d
  DWORD LastError; // eax
  unsigned int v20; // r8d
  DWORD v21; // eax
  unsigned int v22; // r8d
  DWORD dwRevision; // [rsp+30h] [rbp-D0h] BYREF
  WORD pControl[2]; // [rsp+34h] [rbp-CCh] BYREF
  BOOL bOwnerDefaulted; // [rsp+38h] [rbp-C8h] BYREF
  PACL pSacl; // [rsp+40h] [rbp-C0h] BYREF
  PSID pOwner; // [rsp+48h] [rbp-B8h] BYREF
  PSID pGroup; // [rsp+50h] [rbp-B0h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-A8h] BYREF
  void **v30; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR Block; // [rsp+68h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES v32; // [rsp+70h] [rbp-90h] BYREF
  void **v33; // [rsp+88h] [rbp-78h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+90h] [rbp-70h]
  void **v35; // [rsp+98h] [rbp-68h] BYREF
  void *v36; // [rsp+A0h] [rbp-60h]
  char v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+ACh] [rbp-54h]
  __int128 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  void **v42; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  _QWORD v45[9]; // [rsp+F0h] [rbp-10h] BYREF
  char v46; // [rsp+13Ch] [rbp+3Ch]
  int v47; // [rsp+140h] [rbp+40h]
  _BYTE v48[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v49[8]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v50[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v51[16]; // [rsp+160h] [rbp+60h] BYREF

  v4 = *((_QWORD *)this + 57);
  *((_QWORD *)this + 57) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v5 = (ACL *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x40, a2, a3);
  v8 = (Jot::CNamedPipeServer *)v5;
  pSacl = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x40u);
    v9 = (void (__fastcall ***)(_QWORD))Jot::CNamedPipeServer::CNamedPipeServer(v8);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
    (**v9)(v9);
  v10 = *((_QWORD *)this + 57);
  *((_QWORD *)this + 57) = v9;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v42 = &ATL::CAccessToken::`vftable';
  v43 = 0;
  v44 = 0;
  if ( !ATL::CAccessToken::GetProcessToken((ATL::CAccessToken *)&v42, v6, v7) )
  {
    LastError = GetLastError();
    MsoCF::ThrowWin32Tag((MsoCF *)LastError, 0x10623CCu, v20);
  }
  v45[0] = &ATL::CSid::`vftable';
  v46 = 0;
  v47 = 7;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v48);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v49);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v50);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v51);
  ATL::CAccessToken::GetLogonSid((ATL::CAccessToken *)&v42, (struct ATL::CSid *)v45);
  v36 = 0;
  v37 = 0;
  v38 = 2;
  v35 = &ATL::CDacl::`vftable';
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)&v35, (const struct ATL::CSid *)v45, v11, v12) )
  {
    v21 = GetLastError();
    MsoCF::ThrowWin32Tag((MsoCF *)v21, 0x10623CDu, v22);
  }
  v30 = &ATL::CSecurityDesc::`vftable';
  Block = 0;
  ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)&v30, (const struct ATL::CDacl *)&v35, v13);
  v33 = &ATL::CSecurityDesc::`vftable';
  v14 = 0;
  pSecurityDescriptor = 0;
  if ( Block )
  {
    ATL::CSecurityDesc::Init((ATL::CSecurityDesc *)&v33, (const struct _SECURITY_DESCRIPTOR *)Block);
    v14 = pSecurityDescriptor;
  }
  v32.nLength = 24;
  v32.lpSecurityDescriptor = v14;
  v32.bInheritHandle = 0;
  v15 = (Jot::CNamedPipeServer *)*((_QWORD *)this + 57);
  v16 = (const WCHAR *)Jot::CWzInBuffer::operator wchar_t *((char *)this + 368);
  Jot::CNamedPipeServer::Create(v15, v16, v17, v18, &v32);
  v33 = &ATL::CSecurityDesc::`vftable';
  if ( pSecurityDescriptor )
  {
    dwRevision = 0;
    pControl[0] = 0;
    if ( GetSecurityDescriptorControl(pSecurityDescriptor, pControl, &dwRevision) && (pControl[0] & 0x8000) == 0 )
    {
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      bOwnerDefaulted = 0;
      dwRevision = 0;
      GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(pSecurityDescriptor, (LPBOOL)&dwRevision, &pDacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pDacl);
      GetSecurityDescriptorSacl(pSecurityDescriptor, (LPBOOL)&dwRevision, &pSacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pSacl);
    }
    free(pSecurityDescriptor);
    pSecurityDescriptor = 0;
  }
  v30 = &ATL::CSecurityDesc::`vftable';
  if ( Block )
  {
    dwRevision = 0;
    pControl[0] = 0;
    if ( GetSecurityDescriptorControl(Block, pControl, &dwRevision) && (pControl[0] & 0x8000) == 0 )
    {
      pSacl = 0;
      pDacl = 0;
      pGroup = 0;
      pOwner = 0;
      dwRevision = 0;
      bOwnerDefaulted = 0;
      GetSecurityDescriptorOwner(Block, (PSID *)&pSacl, (LPBOOL)&dwRevision);
      free(pSacl);
      GetSecurityDescriptorGroup(Block, (PSID *)&pDacl, (LPBOOL)&dwRevision);
      free(pDacl);
      GetSecurityDescriptorDacl(Block, &bOwnerDefaulted, (PACL *)&pGroup, (LPBOOL)&dwRevision);
      if ( bOwnerDefaulted )
        free(pGroup);
      GetSecurityDescriptorSacl(Block, &bOwnerDefaulted, (PACL *)&pOwner, (LPBOOL)&dwRevision);
      if ( bOwnerDefaulted )
        free(pOwner);
    }
    free(Block);
    Block = 0;
  }
  v35 = &ATL::CDacl::`vftable';
  ATL::CDacl::RemoveAllAces((ATL::CDacl *)&v35);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(&v39);
  v35 = &ATL::CAcl::`vftable';
  free(v36);
  ATL::CSid::~CSid((ATL::CSid *)v45);
  v42 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v42);
}

```

## disassembly

```asm
0x180432b50  mov     [rsp-8+arg_8], rbx
0x180432b55  mov     [rsp-8+arg_10], rsi
0x180432b5a  push    rbp
0x180432b5b  push    rdi
0x180432b5c  push    r12
0x180432b5e  push    r14
0x180432b60  push    r15
0x180432b62  lea     rbp, [rsp-80h]
0x180432b67  sub     rsp, 180h
0x180432b6e  mov     rax, cs:__security_cookie
0x180432b75  xor     rax, rsp
0x180432b78  mov     [rbp+0A0h+var_30], rax
0x180432b7c  mov     rdi, rcx
0x180432b7f  mov     rcx, [rcx+1C8h]
0x180432b86  xor     esi, esi
0x180432b88  mov     [rdi+1C8h], rsi
0x180432b8f  test    rcx, rcx
0x180432b92  jz      short loc_180432BA2
0x180432b94  mov     rax, [rcx]
0x180432b97  mov     rax, [rax+8]
0x180432b9b  call    cs:__guard_dispatch_icall_fptr
0x180432ba1  nop
0x180432ba2  mov     r14d, 40h ; '@'
0x180432ba8  mov     ecx, r14d; this
0x180432bab  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180432bb0  mov     rbx, rax
0x180432bb3  mov     [rsp+1A0h+pSacl], rax
0x180432bb8  test    rax, rax
0x180432bbb  jz      loc_180432E2D
0x180432bc1  mov     r8d, r14d; Size
0x180432bc4  xor     edx, edx; Val
0x180432bc6  mov     rcx, rax; void *
0x180432bc9  call    memset_0
0x180432bce  mov     rcx, rbx; this
0x180432bd1  call    ??0CNamedPipeServer@Jot@@QEAA@XZ; Jot::CNamedPipeServer::CNamedPipeServer(void)
0x180432bd6  mov     rbx, rax
0x180432bd9  test    rbx, rbx
0x180432bdc  jz      short loc_180432BEE
0x180432bde  mov     rax, [rbx]
0x180432be1  mov     rcx, rbx
0x180432be4  mov     rax, [rax]
0x180432be7  call    cs:__guard_dispatch_icall_fptr
0x180432bed  nop
0x180432bee  mov     rcx, [rdi+1C8h]
0x180432bf5  mov     [rdi+1C8h], rbx
0x180432bfc  test    rcx, rcx
0x180432bff  jz      short loc_180432C0F
0x180432c01  mov     rax, [rcx]
0x180432c04  mov     rax, [rax+8]
0x180432c08  call    cs:__guard_dispatch_icall_fptr
0x180432c0e  nop
0x180432c0f  lea     r15, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180432c16  mov     [rbp+0A0h+var_D0], r15
0x180432c1a  xorps   xmm0, xmm0
0x180432c1d  movdqu  [rbp+0A0h+var_C8], xmm0
0x180432c22  mov     [rbp+0A0h+var_B8], rsi
0x180432c26  lea     rcx, [rbp+0A0h+var_D0]; this
0x180432c2a  call    ?GetProcessToken@CAccessToken@ATL@@QEAA_NKPEAX@Z; ATL::CAccessToken::GetProcessToken(ulong,void *)
0x180432c2f  test    al, al
0x180432c31  jz      loc_180432FA7
0x180432c37  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180432c3e  mov     [rbp+0A0h+var_B0], rax
0x180432c42  mov     [rbp+0A0h+var_64], sil
0x180432c46  mov     [rbp+0A0h+var_60], 7
0x180432c4d  lea     rcx, [rbp+0A0h+var_58]
0x180432c51  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180432c56  lea     rcx, [rbp+0A0h+var_50]
0x180432c5a  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180432c5f  lea     rcx, [rbp+0A0h+var_48]
0x180432c63  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180432c68  lea     rcx, [rbp+0A0h+var_40]
0x180432c6c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180432c71  lea     rdx, [rbp+0A0h+var_B0]; struct ATL::CSid *
0x180432c75  lea     rcx, [rbp+0A0h+var_D0]; this
0x180432c79  call    ?GetLogonSid@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z; ATL::CAccessToken::GetLogonSid(ATL::CSid *)
0x180432c7e  mov     [rbp+0A0h+var_100], rsi
0x180432c82  mov     [rbp+0A0h+var_F8], sil
0x180432c86  mov     [rbp+0A0h+var_F4], 2
0x180432c8d  lea     r12, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x180432c94  mov     [rbp+0A0h+var_108], r12
0x180432c98  xorps   xmm0, xmm0
0x180432c9b  movdqu  [rbp+0A0h+var_F0], xmm0
0x180432ca0  mov     [rbp+0A0h+var_E0], rsi
0x180432ca4  mov     [rbp+0A0h+var_D8], esi
0x180432ca7  lea     rdx, [rbp+0A0h+var_B0]; struct ATL::CSid *
0x180432cab  lea     rcx, [rbp+0A0h+var_108]; this
0x180432caf  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x180432cb4  test    al, al
0x180432cb6  jz      loc_180432FBD
0x180432cbc  lea     r14, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x180432cc3  mov     [rsp+1A0h+var_140], r14
0x180432cc8  mov     [rsp+1A0h+Block], rsi
0x180432ccd  lea     rdx, [rbp+0A0h+var_108]; struct ATL::CDacl *
0x180432cd1  lea     rcx, [rsp+1A0h+var_140]; this
0x180432cd6  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x180432cdb  mov     [rbp+0A0h+var_118], r14
0x180432cdf  mov     rax, rsi
0x180432ce2  mov     [rbp+0A0h+pSecurityDescriptor], rax
0x180432ce6  mov     rdx, [rsp+1A0h+Block]; struct _SECURITY_DESCRIPTOR *
0x180432ceb  test    rdx, rdx
0x180432cee  jz      short loc_180432CFD
0x180432cf0  lea     rcx, [rbp+0A0h+var_118]; this
0x180432cf4  call    ?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z; ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)
0x180432cf9  mov     rax, [rbp+0A0h+pSecurityDescriptor]
0x180432cfd  mov     [rsp+1A0h+var_130.nLength], 18h
0x180432d05  mov     [rsp+1A0h+var_130.lpSecurityDescriptor], rax
0x180432d0a  mov     [rbp+0A0h+var_130.bInheritHandle], esi
0x180432d0d  mov     rbx, [rdi+1C8h]
0x180432d14  lea     rcx, [rdi+170h]
0x180432d1b  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x180432d20  lea     rcx, [rsp+1A0h+var_130]
0x180432d25  mov     [rsp+1A0h+var_180], rcx; struct _SECURITY_ATTRIBUTES *
0x180432d2a  mov     rdx, rax; lpName
0x180432d2d  mov     rcx, rbx; this
0x180432d30  call    ?Create@CNamedPipeServer@Jot@@QEAAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@@Z; Jot::CNamedPipeServer::Create(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x180432d35  mov     [rbp+0A0h+var_118], r14
0x180432d39  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180432d3d  mov     ebx, 8000h
0x180432d42  test    rcx, rcx
0x180432d45  jz      short loc_180432D7D
0x180432d47  mov     [rsp+1A0h+dwRevision], esi
0x180432d4b  mov     [rsp+1A0h+pControl], si
0x180432d50  lea     r8, [rsp+1A0h+dwRevision]; lpdwRevision
0x180432d55  lea     rdx, [rsp+1A0h+pControl]; pControl
0x180432d5a  call    cs:__imp_GetSecurityDescriptorControl
0x180432d60  test    eax, eax
0x180432d62  jz      short loc_180432D6F
0x180432d64  test    [rsp+1A0h+pControl], bx
0x180432d69  jz      loc_180432E35
0x180432d6f  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; Block
0x180432d73  call    cs:__imp_free
0x180432d79  mov     [rbp+0A0h+pSecurityDescriptor], rsi
0x180432d7d  mov     [rsp+1A0h+var_140], r14
0x180432d82  mov     rcx, [rsp+1A0h+Block]; pSecurityDescriptor
0x180432d87  test    rcx, rcx
0x180432d8a  jz      short loc_180432DC4
0x180432d8c  mov     [rsp+1A0h+dwRevision], esi
0x180432d90  mov     [rsp+1A0h+pControl], si
0x180432d95  lea     r8, [rsp+1A0h+dwRevision]; lpdwRevision
0x180432d9a  lea     rdx, [rsp+1A0h+pControl]; pControl
0x180432d9f  call    cs:__imp_GetSecurityDescriptorControl
0x180432da5  test    eax, eax
0x180432da7  jz      short loc_180432DB4
0x180432da9  test    [rsp+1A0h+pControl], bx
0x180432dae  jz      loc_180432EEC
0x180432db4  mov     rcx, [rsp+1A0h+Block]; Block
0x180432db9  call    cs:__imp_free
0x180432dbf  mov     [rsp+1A0h+Block], rsi
0x180432dc4  mov     [rbp+0A0h+var_108], r12
0x180432dc8  lea     rcx, [rbp+0A0h+var_108]; this
0x180432dcc  call    ?RemoveAllAces@CDacl@ATL@@UEAAXXZ; ATL::CDacl::RemoveAllAces(void)
0x180432dd1  lea     rcx, [rbp+0A0h+var_F0]
0x180432dd5  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x180432dda  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x180432de1  mov     [rbp+0A0h+var_108], rax
0x180432de5  mov     rcx, [rbp+0A0h+var_100]; Block
0x180432de9  call    cs:__imp_free
0x180432def  lea     rcx, [rbp+0A0h+var_B0]; this
0x180432df3  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180432df8  mov     [rbp+0A0h+var_D0], r15
0x180432dfc  lea     rcx, [rbp+0A0h+var_D0]; this
0x180432e00  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180432e05  mov     rcx, [rbp+0A0h+var_30]
0x180432e09  xor     rcx, rsp; StackCookie
0x180432e0c  call    __security_check_cookie
0x180432e11  lea     r11, [rsp+1A0h+var_20]
0x180432e19  mov     rbx, [r11+38h]
0x180432e1d  mov     rsi, [r11+40h]
0x180432e21  mov     rsp, r11
0x180432e24  pop     r15
0x180432e26  pop     r14
0x180432e28  pop     r12
0x180432e2a  pop     rdi
0x180432e2b  pop     rbp
0x180432e2c  retn
0x180432e2d  mov     rbx, rsi
0x180432e30  jmp     loc_180432BD9
0x180432e35  mov     [rsp+1A0h+pOwner], rsi
0x180432e3a  mov     [rsp+1A0h+pGroup], rsi
0x180432e3f  mov     [rsp+1A0h+pDacl], rsi
0x180432e44  mov     [rsp+1A0h+pSacl], rsi
0x180432e49  mov     [rsp+1A0h+bOwnerDefaulted], esi
0x180432e4d  mov     [rsp+1A0h+dwRevision], esi
0x180432e51  lea     r8, [rsp+1A0h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180432e56  lea     rdx, [rsp+1A0h+pOwner]; pOwner
0x180432e5b  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180432e5f  call    cs:__imp_GetSecurityDescriptorOwner
0x180432e65  mov     rcx, [rsp+1A0h+pOwner]; Block
0x180432e6a  call    cs:__imp_free
0x180432e70  lea     r8, [rsp+1A0h+bOwnerDefaulted]; lpbGroupDefaulted
0x180432e75  lea     rdx, [rsp+1A0h+pGroup]; pGroup
0x180432e7a  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180432e7e  call    cs:__imp_GetSecurityDescriptorGroup
0x180432e84  mov     rcx, [rsp+1A0h+pGroup]; Block
0x180432e89  call    cs:__imp_free
0x180432e8f  lea     r9, [rsp+1A0h+bOwnerDefaulted]; lpbDaclDefaulted
0x180432e94  lea     r8, [rsp+1A0h+pDacl]; pDacl
0x180432e99  lea     rdx, [rsp+1A0h+dwRevision]; lpbDaclPresent
0x180432e9e  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180432ea2  call    cs:__imp_GetSecurityDescriptorDacl
0x180432ea8  cmp     [rsp+1A0h+dwRevision], esi
0x180432eac  jz      short loc_180432EB9
0x180432eae  mov     rcx, [rsp+1A0h+pDacl]; Block
0x180432eb3  call    cs:__imp_free
0x180432eb9  lea     r9, [rsp+1A0h+bOwnerDefaulted]; lpbSaclDefaulted
0x180432ebe  lea     r8, [rsp+1A0h+pSacl]; pSacl
0x180432ec3  lea     rdx, [rsp+1A0h+dwRevision]; lpbSaclPresent
0x180432ec8  mov     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180432ecc  call    cs:__imp_GetSecurityDescriptorSacl
0x180432ed2  cmp     [rsp+1A0h+dwRevision], esi
0x180432ed6  jz      loc_180432D6F
0x180432edc  mov     rcx, [rsp+1A0h+pSacl]; Block
0x180432ee1  call    cs:__imp_free
0x180432ee7  jmp     loc_180432D6F
0x180432eec  mov     [rsp+1A0h+pSacl], rsi
0x180432ef1  mov     [rsp+1A0h+pDacl], rsi
0x180432ef6  mov     [rsp+1A0h+pGroup], rsi
0x180432efb  mov     [rsp+1A0h+pOwner], rsi
0x180432f00  mov     [rsp+1A0h+dwRevision], esi
0x180432f04  mov     [rsp+1A0h+bOwnerDefaulted], esi
0x180432f08  lea     r8, [rsp+1A0h+dwRevision]; lpbOwnerDefaulted
0x180432f0d  lea     rdx, [rsp+1A0h+pSacl]; pOwner
0x180432f12  mov     rcx, [rsp+1A0h+Block]; pSecurityDescriptor
0x180432f17  call    cs:__imp_GetSecurityDescriptorOwner
0x180432f1d  mov     rcx, [rsp+1A0h+pSacl]; Block
0x180432f22  call    cs:__imp_free
0x180432f28  lea     r8, [rsp+1A0h+dwRevision]; lpbGroupDefaulted
0x180432f2d  lea     rdx, [rsp+1A0h+pDacl]; pGroup
0x180432f32  mov     rcx, [rsp+1A0h+Block]; pSecurityDescriptor
0x180432f37  call    cs:__imp_GetSecurityDescriptorGroup
0x180432f3d  mov     rcx, [rsp+1A0h+pDacl]; Block
0x180432f42  call    cs:__imp_free
0x180432f48  lea     r9, [rsp+1A0h+dwRevision]; lpbDaclDefaulted
0x180432f4d  lea     r8, [rsp+1A0h+pGroup]; pDacl
0x180432f52  lea     rdx, [rsp+1A0h+bOwnerDefaulted]; lpbDaclPresent
0x180432f57  mov     rcx, [rsp+1A0h+Block]; pSecurityDescriptor
0x180432f5c  call    cs:__imp_GetSecurityDescriptorDacl
0x180432f62  cmp     [rsp+1A0h+bOwnerDefaulted], esi
0x180432f66  jz      short loc_180432F73
0x180432f68  mov     rcx, [rsp+1A0h+pGroup]; Block
0x180432f6d  call    cs:__imp_free
0x180432f73  lea     r9, [rsp+1A0h+dwRevision]; lpbSaclDefaulted
0x180432f78  lea     r8, [rsp+1A0h+pOwner]; pSacl
0x180432f7d  lea     rdx, [rsp+1A0h+bOwnerDefaulted]; lpbSaclPresent
0x180432f82  mov     rcx, [rsp+1A0h+Block]; pSecurityDescriptor
0x180432f87  call    cs:__imp_GetSecurityDescriptorSacl
0x180432f8d  cmp     [rsp+1A0h+bOwnerDefaulted], esi
0x180432f91  jz      loc_180432DB4
0x180432f97  mov     rcx, [rsp+1A0h+pOwner]; Block
0x180432f9c  call    cs:__imp_free
0x180432fa2  jmp     loc_180432DB4
0x180432fa7  call    cs:__imp_GetLastError
0x180432fad  mov     ecx, eax; this
0x180432faf  mov     edx, 10623CCh; unsigned int
0x180432fb4  call    ?ThrowWin32Tag@MsoCF@@YAXKK@Z; MsoCF::ThrowWin32Tag(ulong,ulong)
0x180432fba  jmp     short $+2
0x180432fbc  nop
0x180432fbd  call    cs:__imp_GetLastError
0x180432fc3  mov     ecx, eax; this
0x180432fc5  mov     edx, 10623CDh; unsigned int
0x180432fca  call    ?ThrowWin32Tag@MsoCF@@YAXKK@Z; MsoCF::ThrowWin32Tag(ulong,ulong)
```

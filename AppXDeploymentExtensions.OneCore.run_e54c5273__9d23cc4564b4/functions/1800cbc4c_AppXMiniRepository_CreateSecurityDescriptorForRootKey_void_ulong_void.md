# AppXMiniRepository::CreateSecurityDescriptorForRootKey(void *,ulong *,void * *)

- ea: `0x1800cbc4c`
- end: `0x1800cc265`
- name: `?CreateSecurityDescriptorForRootKey@AppXMiniRepository@@SAJPEAXPEAKPEAPEAX@Z`
- size: `1561`
- prototype: `__int64 __fastcall(PSID Sid, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001ce24`
- `0x18005dfb8`

## callees

- `0x1800cbc4c`
- `0x1800ce12c`
- `0x1800f0700`
- `0x1800f073c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc0c2`
- `ntdll!RtlLengthSid` at `0x1800cbe31`
- `ntdll!RtlLengthSid` at `0x1800cbe3d`
- `ntdll!RtlLengthSid` at `0x1800cbe49`
- `ntdll!RtlLengthSid` at `0x1800cbe55`
- `ntdll!RtlLengthSid` at `0x1800cbe61`
- `ntdll!RtlLengthSid` at `0x1800cbe6d`
- `ntdll!RtlLengthSid` at `0x1800cbe31`
- `ntdll!RtlLengthSid` at `0x1800cbe3d`
- `ntdll!RtlLengthSid` at `0x1800cbe49`
- `ntdll!RtlLengthSid` at `0x1800cbe55`
- `ntdll!RtlLengthSid` at `0x1800cbe61`
- `ntdll!RtlLengthSid` at `0x1800cbe6d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbcb9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbd0e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbd62`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbdb3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbe08`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbcb9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbd0e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbd62`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbdb3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800cbe08`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbf9c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbfbd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbfe2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc007`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc02c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc055`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbf9c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbfbd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cbfe2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc007`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc02c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800cc055`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cc0bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cc166`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cc0bc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800cc166`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800cc09e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800cc09e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800cc087`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800cc087`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800cc070`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800cc070`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800cbebe`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800cbebe`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800cbf1e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800cbf1e`

## pseudocode

```c
__int64 __fastcall AppXMiniRepository::CreateSecurityDescriptorForRootKey(PSID Sid, unsigned int *a2, void **a3)
{
  void *v4; // rax
  void *pSid; // r13
  Common *v7; // rcx
  unsigned int HResultFromLastError; // r14d
  void *v9; // rax
  void *v10; // rbx
  void *v11; // rcx
  Common *v12; // rcx
  void *v13; // rax
  void *v14; // rdi
  void *v15; // rcx
  Common *v16; // rcx
  void *v17; // rax
  void *v18; // rsi
  void *v19; // rcx
  Common *v20; // rcx
  void *v21; // rax
  void *v22; // r12
  void *v23; // rcx
  Common *v24; // rcx
  ULONG v25; // eax
  ULONG v26; // eax
  ULONG v27; // eax
  ULONG v28; // eax
  ULONG v29; // eax
  ULONG v30; // eax
  void *v31; // rax
  void *v32; // r15
  void *v33; // rcx
  Common *v34; // rcx
  struct _ACL *v35; // rax
  struct _ACL *v36; // r14
  Common *v37; // rcx
  unsigned int v38; // eax
  signed int LastError; // eax
  void *v40; // rax
  void *v41; // r13
  Common *v42; // rcx
  unsigned int v43; // [rsp+30h] [rbp-18h]
  unsigned int v44; // [rsp+30h] [rbp-18h]
  void *v45; // [rsp+38h] [rbp-10h]
  DWORD cbSid; // [rsp+A8h] [rbp+60h] BYREF

  cbSid = 68;
  v4 = operator new[](0x44u, (const struct std::nothrow_t *)std::nothrow);
  v45 = v4;
  pSid = v4;
  if ( !v4 )
  {
    operator delete(0, 0xCu);
    return 2147942414LL;
  }
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, v4, &cbSid) )
  {
    cbSid = 68;
    v9 = operator new[](0x44u, (const struct std::nothrow_t *)std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      v11 = 0;
LABEL_7:
      operator delete(v11, 0xCu);
      HResultFromLastError = -2147024882;
      goto LABEL_58;
    }
    if ( !CreateWellKnownSid(WinLocalServiceSid, 0, v9, &cbSid) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v12);
LABEL_10:
      operator delete(v10, 0xCu);
      goto LABEL_58;
    }
    cbSid = 68;
    v13 = operator new[](0x44u, (const struct std::nothrow_t *)std::nothrow);
    v14 = v13;
    if ( !v13 )
    {
      v15 = 0;
LABEL_13:
      operator delete(v15, 0xCu);
      v11 = v10;
      goto LABEL_7;
    }
    if ( !CreateWellKnownSid(WinNetworkServiceSid, 0, v13, &cbSid) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v16);
LABEL_16:
      operator delete(v14, 0xCu);
      goto LABEL_10;
    }
    cbSid = 68;
    v17 = operator new[](0x44u, (const struct std::nothrow_t *)std::nothrow);
    v18 = v17;
    if ( !v17 )
    {
      v19 = 0;
LABEL_19:
      operator delete(v19, 0xCu);
      v15 = v14;
      goto LABEL_13;
    }
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v17, &cbSid) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v20);
LABEL_22:
      operator delete(v18, 0xCu);
      goto LABEL_16;
    }
    cbSid = 68;
    v21 = operator new[](0x44u, (const struct std::nothrow_t *)std::nothrow);
    v22 = v21;
    if ( !v21 )
    {
      v23 = 0;
LABEL_25:
      operator delete(v23, 0xCu);
      v19 = v18;
      goto LABEL_19;
    }
    if ( !CreateWellKnownSid(WinCreatorOwnerSid, 0, v21, &cbSid) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v24);
LABEL_28:
      operator delete(v22, 0xCu);
      goto LABEL_22;
    }
    cbSid = 80;
    v25 = RtlLengthSid(v18);
    cbSid += v25;
    v26 = RtlLengthSid(v22);
    cbSid += v26;
    v27 = RtlLengthSid(v10);
    cbSid += v27;
    v28 = RtlLengthSid(v14);
    cbSid += v28;
    v29 = RtlLengthSid(pSid);
    cbSid += v29;
    v30 = RtlLengthSid(Sid);
    cbSid = (v30 + cbSid + 3) & 0xFFFFFFFC;
    v31 = operator new[](0x28u, (const struct std::nothrow_t *)std::nothrow);
    v32 = v31;
    if ( !v31 )
    {
      v33 = 0;
LABEL_31:
      operator delete(v33, 0x28u);
      v23 = v22;
      goto LABEL_25;
    }
    if ( !InitializeSecurityDescriptor(v31, 1u) )
    {
      HResultFromLastError = Common::GetHResultFromLastError(v34);
      operator delete(v32, 0x28u);
      goto LABEL_28;
    }
    v35 = (struct _ACL *)operator new[](cbSid, (const struct std::nothrow_t *)std::nothrow);
    v36 = v35;
    if ( !v35 )
    {
      operator delete(0, 8u);
      v33 = v32;
      goto LABEL_31;
    }
    if ( InitializeAcl(v35, cbSid, 2u)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0xF003Fu, pSid)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0x20019u, v10)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0x20019u, v14)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0x20019u, v22)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0x20019u, v18)
      && AddAccessAllowedAceEx(v36, 2u, 3u, 0x20019u, Sid)
      && SetSecurityDescriptorDacl(v32, 1, v36, 0)
      && SetSecurityDescriptorOwner(v32, pSid, 0)
      && SetSecurityDescriptorGroup(v32, pSid, 0) )
    {
      cbSid = 0;
      MakeSelfRelativeSD(v32, 0, &cbSid);
      LastError = GetLastError();
      v43 = LastError;
      if ( LastError == 122 )
      {
        v40 = operator new[](cbSid, (const struct std::nothrow_t *)std::nothrow);
        v41 = v40;
        if ( v40 )
        {
          if ( MakeSelfRelativeSD(v32, v40, &cbSid) )
          {
            *a2 = -2147483641;
            *a3 = v41;
            operator delete(0, 0x28u);
            operator delete(v36, 8u);
            operator delete(v32, 0x28u);
            operator delete(v22, 0xCu);
            operator delete(v18, 0xCu);
            operator delete(v14, 0xCu);
            operator delete(v10, 0xCu);
            HResultFromLastError = 0;
          }
          else
          {
            v44 = Common::GetHResultFromLastError(v42);
            operator delete(v41, 0x28u);
            operator delete(v36, 8u);
            operator delete(v32, 0x28u);
            operator delete(v22, 0xCu);
            operator delete(v18, 0xCu);
            operator delete(v14, 0xCu);
            operator delete(v10, 0xCu);
            HResultFromLastError = v44;
          }
        }
        else
        {
          operator delete(0, 0x28u);
          operator delete(v36, 8u);
          operator delete(v32, 0x28u);
          operator delete(v22, 0xCu);
          operator delete(v18, 0xCu);
          operator delete(v14, 0xCu);
          operator delete(v10, 0xCu);
          HResultFromLastError = -2147024882;
        }
        pSid = v45;
        goto LABEL_58;
      }
      if ( LastError <= 0 )
        goto LABEL_39;
      v38 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v38 = Common::GetHResultFromLastError(v37);
    }
    v43 = v38;
LABEL_39:
    operator delete(v36, 8u);
    operator delete(v32, 0x28u);
    operator delete(v22, 0xCu);
    operator delete(v18, 0xCu);
    operator delete(v14, 0xCu);
    operator delete(v10, 0xCu);
    HResultFromLastError = v43;
    goto LABEL_58;
  }
  HResultFromLastError = Common::GetHResultFromLastError(v7);
LABEL_58:
  operator delete(pSid, 0xCu);
  return HResultFromLastError;
}

```

## disassembly

```asm
0x1800cbc4c  mov     [rsp-40h+arg_10], r8
0x1800cbc51  mov     [rsp-40h+arg_8], rdx
0x1800cbc56  mov     [rsp-40h+arg_0], rcx
0x1800cbc5b  push    rbp
0x1800cbc5c  push    rbx
0x1800cbc5d  push    rsi
0x1800cbc5e  push    rdi
0x1800cbc5f  push    r12
0x1800cbc61  push    r13
0x1800cbc63  push    r14
0x1800cbc65  push    r15
0x1800cbc67  mov     rbp, rsp
0x1800cbc6a  sub     rsp, 48h
0x1800cbc6e  mov     r12d, 44h ; 'D'
0x1800cbc74  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800cbc7b  mov     r14, rcx
0x1800cbc7e  mov     [rbp+cbSid], r12d
0x1800cbc82  mov     rdx, rsi; struct std::nothrow_t *
0x1800cbc85  mov     ecx, r12d; unsigned __int64
0x1800cbc88  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbc8d  mov     [rbp+var_10], rax
0x1800cbc91  mov     r13, rax
0x1800cbc94  test    rax, rax
0x1800cbc97  jnz     short loc_1800CBCAD
0x1800cbc99  lea     edx, [rax+0Ch]; unsigned __int64
0x1800cbc9c  xor     ecx, ecx; void *
0x1800cbc9e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbca3  mov     eax, 8007000Eh
0x1800cbca8  jmp     loc_1800CC254
0x1800cbcad  xor     edx, edx; DomainSid
0x1800cbcaf  lea     r9, [rbp+cbSid]; cbSid
0x1800cbcb3  mov     r8, r13; pSid
0x1800cbcb6  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800cbcb9  call    cs:__imp_CreateWellKnownSid
0x1800cbcbf  mov     r15d, 0Ch
0x1800cbcc5  test    eax, eax
0x1800cbcc7  jnz     short loc_1800CBCD6
0x1800cbcc9  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbcce  mov     r14d, eax
0x1800cbcd1  jmp     loc_1800CC246
0x1800cbcd6  mov     rdx, rsi; struct std::nothrow_t *
0x1800cbcd9  mov     [rbp+cbSid], r12d
0x1800cbcdd  mov     rcx, r12; unsigned __int64
0x1800cbce0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbce5  mov     rbx, rax
0x1800cbce8  test    rax, rax
0x1800cbceb  jnz     short loc_1800CBD02
0x1800cbced  xor     ecx, ecx; void *
0x1800cbcef  mov     rdx, r15; unsigned __int64
0x1800cbcf2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbcf7  mov     r14d, 8007000Eh
0x1800cbcfd  jmp     loc_1800CC246
0x1800cbd02  xor     edx, edx; DomainSid
0x1800cbd04  lea     r9, [rbp+cbSid]; cbSid
0x1800cbd08  mov     r8, rbx; pSid
0x1800cbd0b  lea     ecx, [rdx+17h]; WellKnownSidType
0x1800cbd0e  call    cs:__imp_CreateWellKnownSid
0x1800cbd14  test    eax, eax
0x1800cbd16  jnz     short loc_1800CBD30
0x1800cbd18  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbd1d  mov     r14d, eax
0x1800cbd20  mov     rdx, r15; unsigned __int64
0x1800cbd23  mov     rcx, rbx; void *
0x1800cbd26  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbd2b  jmp     loc_1800CC246
0x1800cbd30  mov     rdx, rsi; struct std::nothrow_t *
0x1800cbd33  mov     [rbp+cbSid], r12d
0x1800cbd37  mov     rcx, r12; unsigned __int64
0x1800cbd3a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbd3f  mov     rdi, rax
0x1800cbd42  test    rax, rax
0x1800cbd45  jnz     short loc_1800CBD56
0x1800cbd47  xor     ecx, ecx; void *
0x1800cbd49  mov     rdx, r15; unsigned __int64
0x1800cbd4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbd51  mov     rcx, rbx
0x1800cbd54  jmp     short loc_1800CBCEF
0x1800cbd56  xor     edx, edx; DomainSid
0x1800cbd58  lea     r9, [rbp+cbSid]; cbSid
0x1800cbd5c  mov     r8, rdi; pSid
0x1800cbd5f  lea     ecx, [rdx+18h]; WellKnownSidType
0x1800cbd62  call    cs:__imp_CreateWellKnownSid
0x1800cbd68  test    eax, eax
0x1800cbd6a  jnz     short loc_1800CBD81
0x1800cbd6c  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbd71  mov     r14d, eax
0x1800cbd74  mov     rdx, r15; unsigned __int64
0x1800cbd77  mov     rcx, rdi; void *
0x1800cbd7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbd7f  jmp     short loc_1800CBD20
0x1800cbd81  mov     rdx, rsi; struct std::nothrow_t *
0x1800cbd84  mov     [rbp+cbSid], r12d
0x1800cbd88  mov     rcx, r12; unsigned __int64
0x1800cbd8b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbd90  mov     rsi, rax
0x1800cbd93  test    rax, rax
0x1800cbd96  jnz     short loc_1800CBDA7
0x1800cbd98  xor     ecx, ecx; void *
0x1800cbd9a  mov     rdx, r15; unsigned __int64
0x1800cbd9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbda2  mov     rcx, rdi
0x1800cbda5  jmp     short loc_1800CBD49
0x1800cbda7  xor     edx, edx; DomainSid
0x1800cbda9  lea     r9, [rbp+cbSid]; cbSid
0x1800cbdad  mov     r8, rsi; pSid
0x1800cbdb0  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800cbdb3  call    cs:__imp_CreateWellKnownSid
0x1800cbdb9  test    eax, eax
0x1800cbdbb  jnz     short loc_1800CBDD2
0x1800cbdbd  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbdc2  mov     r14d, eax
0x1800cbdc5  mov     rdx, r15; unsigned __int64
0x1800cbdc8  mov     rcx, rsi; void *
0x1800cbdcb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbdd0  jmp     short loc_1800CBD74
0x1800cbdd2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbdd9  mov     [rbp+cbSid], r12d
0x1800cbddd  mov     rcx, r12; unsigned __int64
0x1800cbde0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbde5  mov     r12, rax
0x1800cbde8  test    rax, rax
0x1800cbdeb  jnz     short loc_1800CBDFC
0x1800cbded  xor     ecx, ecx; void *
0x1800cbdef  mov     rdx, r15; unsigned __int64
0x1800cbdf2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbdf7  mov     rcx, rsi
0x1800cbdfa  jmp     short loc_1800CBD9A
0x1800cbdfc  xor     edx, edx; DomainSid
0x1800cbdfe  lea     r9, [rbp+cbSid]; cbSid
0x1800cbe02  mov     r8, r12; pSid
0x1800cbe05  lea     ecx, [rdx+3]; WellKnownSidType
0x1800cbe08  call    cs:__imp_CreateWellKnownSid
0x1800cbe0e  test    eax, eax
0x1800cbe10  jnz     short loc_1800CBE27
0x1800cbe12  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbe17  mov     r14d, eax
0x1800cbe1a  mov     rdx, r15; unsigned __int64
0x1800cbe1d  mov     rcx, r12; void *
0x1800cbe20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbe25  jmp     short loc_1800CBDC5
0x1800cbe27  mov     rcx, rsi; Sid
0x1800cbe2a  mov     [rbp+cbSid], 50h ; 'P'
0x1800cbe31  call    cs:__imp_RtlLengthSid
0x1800cbe37  add     [rbp+cbSid], eax
0x1800cbe3a  mov     rcx, r12; Sid
0x1800cbe3d  call    cs:__imp_RtlLengthSid
0x1800cbe43  add     [rbp+cbSid], eax
0x1800cbe46  mov     rcx, rbx; Sid
0x1800cbe49  call    cs:__imp_RtlLengthSid
0x1800cbe4f  add     [rbp+cbSid], eax
0x1800cbe52  mov     rcx, rdi; Sid
0x1800cbe55  call    cs:__imp_RtlLengthSid
0x1800cbe5b  add     [rbp+cbSid], eax
0x1800cbe5e  mov     rcx, r13; Sid
0x1800cbe61  call    cs:__imp_RtlLengthSid
0x1800cbe67  add     [rbp+cbSid], eax
0x1800cbe6a  mov     rcx, r14; Sid
0x1800cbe6d  call    cs:__imp_RtlLengthSid
0x1800cbe73  mov     edx, [rbp+cbSid]
0x1800cbe76  mov     r14d, 28h ; '('
0x1800cbe7c  add     edx, 3
0x1800cbe7f  mov     ecx, r14d; unsigned __int64
0x1800cbe82  add     edx, eax
0x1800cbe84  and     edx, 0FFFFFFFCh
0x1800cbe87  mov     [rbp+cbSid], edx
0x1800cbe8a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbe91  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbe96  mov     r15, rax
0x1800cbe99  test    rax, rax
0x1800cbe9c  jnz     short loc_1800CBEB6
0x1800cbe9e  mov     edx, r14d; unsigned __int64
0x1800cbea1  xor     ecx, ecx; void *
0x1800cbea3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbea8  mov     rcx, r12
0x1800cbeab  mov     r15d, 0Ch
0x1800cbeb1  jmp     loc_1800CBDEF
0x1800cbeb6  mov     edx, 1; dwRevision
0x1800cbebb  mov     rcx, r15; pSecurityDescriptor
0x1800cbebe  call    cs:__imp_InitializeSecurityDescriptor
0x1800cbec4  test    eax, eax
0x1800cbec6  jnz     short loc_1800CBEE8
0x1800cbec8  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbecd  mov     edx, 28h ; '('; unsigned __int64
0x1800cbed2  mov     rcx, r15; void *
0x1800cbed5  mov     r14d, eax
0x1800cbed8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbedd  mov     r15d, 0Ch
0x1800cbee3  jmp     loc_1800CBE1A
0x1800cbee8  mov     ecx, [rbp+cbSid]; unsigned __int64
0x1800cbeeb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cbef2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cbef7  mov     r14, rax
0x1800cbefa  test    rax, rax
0x1800cbefd  jnz     short loc_1800CBF12
0x1800cbeff  lea     edx, [rax+8]; unsigned __int64
0x1800cbf02  xor     ecx, ecx; void *
0x1800cbf04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf09  lea     edx, [r14+28h]
0x1800cbf0d  mov     rcx, r15
0x1800cbf10  jmp     short loc_1800CBEA3
0x1800cbf12  mov     edx, [rbp+cbSid]; nAclLength
0x1800cbf15  mov     r8d, 2; dwAclRevision
0x1800cbf1b  mov     rcx, r14; pAcl
0x1800cbf1e  call    cs:__imp_InitializeAcl
0x1800cbf24  test    eax, eax
0x1800cbf26  jnz     short loc_1800CBF85
0x1800cbf28  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x1800cbf2d  mov     [rbp+var_18], eax
0x1800cbf30  mov     edx, 8; unsigned __int64
0x1800cbf35  mov     rcx, r14; void *
0x1800cbf38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf3d  mov     edx, 28h ; '('; unsigned __int64
0x1800cbf42  mov     rcx, r15; void *
0x1800cbf45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf4a  mov     r15d, 0Ch
0x1800cbf50  mov     rcx, r12; void *
0x1800cbf53  mov     edx, r15d; unsigned __int64
0x1800cbf56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf5b  mov     edx, r15d; unsigned __int64
0x1800cbf5e  mov     rcx, rsi; void *
0x1800cbf61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf66  mov     edx, r15d; unsigned __int64
0x1800cbf69  mov     rcx, rdi; void *
0x1800cbf6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf71  mov     edx, r15d; unsigned __int64
0x1800cbf74  mov     rcx, rbx; void *
0x1800cbf77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cbf7c  mov     r14d, [rbp+var_18]
0x1800cbf80  jmp     loc_1800CC246
0x1800cbf85  mov     edx, 2; dwAceRevision
0x1800cbf8a  mov     [rsp+48h+pSid], r13; pSid
0x1800cbf8f  mov     r9d, 0F003Fh; AccessMask
0x1800cbf95  mov     rcx, r14; pAcl
0x1800cbf98  lea     r8d, [rdx+1]; AceFlags
0x1800cbf9c  call    cs:__imp_AddAccessAllowedAceEx
0x1800cbfa2  test    eax, eax
0x1800cbfa4  jz      short loc_1800CBF28
0x1800cbfa6  mov     edx, 2; dwAceRevision
0x1800cbfab  mov     [rsp+48h+pSid], rbx; pSid
0x1800cbfb0  mov     r9d, 20019h; AccessMask
0x1800cbfb6  mov     rcx, r14; pAcl
0x1800cbfb9  lea     r8d, [rdx+1]; AceFlags
0x1800cbfbd  call    cs:__imp_AddAccessAllowedAceEx
0x1800cbfc3  test    eax, eax
0x1800cbfc5  jz      loc_1800CBF28
0x1800cbfcb  mov     edx, 2; dwAceRevision
0x1800cbfd0  mov     [rsp+48h+pSid], rdi; pSid
0x1800cbfd5  mov     r9d, 20019h; AccessMask
0x1800cbfdb  mov     rcx, r14; pAcl
0x1800cbfde  lea     r8d, [rdx+1]; AceFlags
0x1800cbfe2  call    cs:__imp_AddAccessAllowedAceEx
0x1800cbfe8  test    eax, eax
0x1800cbfea  jz      loc_1800CBF28
0x1800cbff0  mov     edx, 2; dwAceRevision
0x1800cbff5  mov     [rsp+48h+pSid], r12; pSid
0x1800cbffa  mov     r9d, 20019h; AccessMask
0x1800cc000  mov     rcx, r14; pAcl
0x1800cc003  lea     r8d, [rdx+1]; AceFlags
0x1800cc007  call    cs:__imp_AddAccessAllowedAceEx
0x1800cc00d  test    eax, eax
0x1800cc00f  jz      loc_1800CBF28
0x1800cc015  mov     edx, 2; dwAceRevision
0x1800cc01a  mov     [rsp+48h+pSid], rsi; pSid
0x1800cc01f  mov     r9d, 20019h; AccessMask
0x1800cc025  mov     rcx, r14; pAcl
0x1800cc028  lea     r8d, [rdx+1]; AceFlags
0x1800cc02c  call    cs:__imp_AddAccessAllowedAceEx
0x1800cc032  test    eax, eax
0x1800cc034  jz      loc_1800CBF28
0x1800cc03a  mov     rax, [rbp+arg_0]
0x1800cc03e  mov     edx, 2; dwAceRevision
0x1800cc043  mov     r9d, 20019h; AccessMask
0x1800cc049  mov     [rsp+48h+pSid], rax; pSid
0x1800cc04e  mov     rcx, r14; pAcl
0x1800cc051  lea     r8d, [rdx+1]; AceFlags
0x1800cc055  call    cs:__imp_AddAccessAllowedAceEx
0x1800cc05b  test    eax, eax
0x1800cc05d  jz      loc_1800CBF28
0x1800cc063  xor     r9d, r9d; bDaclDefaulted
0x1800cc066  mov     r8, r14; pDacl
0x1800cc069  mov     rcx, r15; pSecurityDescriptor
0x1800cc06c  lea     edx, [r9+1]; bDaclPresent
0x1800cc070  call    cs:__imp_SetSecurityDescriptorDacl
0x1800cc076  test    eax, eax
0x1800cc078  jz      loc_1800CBF28
0x1800cc07e  xor     r8d, r8d; bOwnerDefaulted
0x1800cc081  mov     rdx, r13; pOwner
0x1800cc084  mov     rcx, r15; pSecurityDescriptor
0x1800cc087  call    cs:__imp_SetSecurityDescriptorOwner
0x1800cc08d  test    eax, eax
0x1800cc08f  jz      loc_1800CBF28
0x1800cc095  xor     r8d, r8d; bGroupDefaulted
0x1800cc098  mov     rdx, r13; pGroup
0x1800cc09b  mov     rcx, r15; pSecurityDescriptor
0x1800cc09e  call    cs:__imp_SetSecurityDescriptorGroup
0x1800cc0a4  test    eax, eax
0x1800cc0a6  jz      loc_1800CBF28
0x1800cc0ac  lea     r8, [rbp+cbSid]; lpdwBufferLength
0x1800cc0b0  mov     [rbp+cbSid], 0
0x1800cc0b7  xor     edx, edx; pSelfRelativeSecurityDescriptor
  ... truncated ...
```

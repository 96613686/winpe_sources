# Catalog::UpdateFrontDoor(IRequestContext &)

- ea: `0x18007a248`
- end: `0x18007aa1a`
- name: `?UpdateFrontDoor@Catalog@@AEAA_NAEAVIRequestContext@@@Z`
- size: `2002`
- prototype: `char __fastcall(PSECURITY_DESCRIPTOR *this, struct IRequestContext *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b9850`
- `0x1800ee08c`

## callees

- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x18007a248`
- `0x18007aa20`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a953`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a2cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a3bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a65a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a89b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a953`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18007a2ba`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18007a2ba`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18007a7b5`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18007a7b5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18007a942`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18007a942`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18007a569`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x18007a569`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007a783`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007a783`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007a758`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007a758`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007a500`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18007a500`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18007a490`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18007a490`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18007a649`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18007a649`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007a343`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18007a343`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007a427`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18007a427`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18007a3ac`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18007a3ac`

## pseudocode

```c
char __fastcall Catalog::UpdateFrontDoor(PSECURITY_DESCRIPTOR *this, struct IRequestContext *a2)
{
  char v4; // r14
  void (__fastcall *v5)(struct IRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  void (__fastcall *v9)(struct IRequestContext *, _QWORD); // rbx
  DWORD v10; // eax
  void (__fastcall *v11)(struct IRequestContext *, _QWORD); // rbx
  DWORD v12; // eax
  void (__fastcall *v13)(struct IRequestContext *, _QWORD); // rbx
  DWORD v14; // eax
  void (__fastcall *v15)(struct IRequestContext *, _QWORD); // rbx
  DWORD v16; // eax
  void (__fastcall *v17)(struct IRequestContext *, _QWORD); // rbx
  DWORD v18; // eax
  void (__fastcall *v19)(struct IRequestContext *, _QWORD); // rbx
  DWORD v20; // eax
  struct _ACL *v22; // rax
  struct _ACL *v23; // rsi
  void (__fastcall *v24)(struct IRequestContext *, _QWORD); // rbx
  DWORD v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdx
  _QWORD *i; // rax
  _QWORD *v29; // r12
  __int64 j; // r13
  void *v31; // rcx
  signed int k; // r15d
  void (__fastcall *v33)(struct IRequestContext *, _QWORD); // rbx
  DWORD v34; // eax
  PVOID *v35; // rax
  unsigned int v36; // eax
  __int64 v37; // rdx
  void (__fastcall *v38)(struct IRequestContext *, _QWORD); // rbx
  DWORD v39; // eax
  void (__fastcall *v40)(struct IRequestContext *, _QWORD); // rbx
  DWORD v41; // eax
  void (__fastcall *v42)(struct IRequestContext *, _QWORD); // rbx
  DWORD v43; // eax
  BOOL bDaclPresent; // [rsp+30h] [rbp-49h] BYREF
  PSID pOwner; // [rsp+38h] [rbp-41h] BYREF
  BOOL bDaclDefaulted; // [rsp+40h] [rbp-39h] BYREF
  PACL pSacl; // [rsp+48h] [rbp-31h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-29h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v50; // [rsp+60h] [rbp-19h]
  struct _ACL *v51; // [rsp+68h] [rbp-11h] BYREF
  __int128 pSecurityDescriptor; // [rsp+70h] [rbp-9h] BYREF
  __int128 v53; // [rsp+80h] [rbp+7h]
  void *v54; // [rsp+90h] [rbp+17h]
  BOOL bOwnerDefaulted; // [rsp+F0h] [rbp+77h] BYREF
  BOOL bSaclPresent; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, this);
  pSecurityDescriptor = 0;
  v53 = 0;
  v54 = 0;
  v4 = 1;
  if ( !InitializeSecurityDescriptor(&pSecurityDescriptor, 1u) )
  {
    v5 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    LastError = GetLastError();
    v5(a2, LastError);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 37;
LABEL_32:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v7);
    return 0;
  }
  pSacl = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  bSaclPresent = 0;
  if ( !GetSecurityDescriptorOwner(this[23], &pOwner, &bOwnerDefaulted) )
  {
    v9 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v10 = GetLastError();
    v9(a2, v10);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 38;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorOwner(&pSecurityDescriptor, pOwner, bOwnerDefaulted) )
  {
    v11 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v12 = GetLastError();
    v11(a2, v12);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 39;
    goto LABEL_32;
  }
  pOwner = 0;
  bOwnerDefaulted = 0;
  if ( !GetSecurityDescriptorGroup(this[23], &pOwner, &bOwnerDefaulted) )
  {
    v13 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v14 = GetLastError();
    v13(a2, v14);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 40;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorGroup(&pSecurityDescriptor, pOwner, bOwnerDefaulted) )
  {
    v15 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v16 = GetLastError();
    v15(a2, v16);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 41;
    goto LABEL_32;
  }
  if ( !GetSecurityDescriptorSacl(this[23], &bSaclPresent, &pSacl, &bOwnerDefaulted) )
  {
    v17 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v18 = GetLastError();
    v17(a2, v18);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 42;
    goto LABEL_32;
  }
  if ( !SetSecurityDescriptorSacl(&pSecurityDescriptor, bSaclPresent, pSacl, bOwnerDefaulted) )
  {
    v19 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v20 = GetLastError();
    v19(a2, v20);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0 )
      return 0;
    v7 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    v8 = 43;
    goto LABEL_32;
  }
  v22 = (struct _ACL *)WSManMemory::Alloc(65530, 0, 0);
  v23 = v22;
  v51 = v22;
  if ( !v22 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids);
    goto LABEL_82;
  }
  if ( !InitializeAcl(v22, 0xFFFAu, 2u) )
  {
    v24 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v25 = GetLastError();
    v24(a2, v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v26 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      v27 = 45;
      goto LABEL_81;
    }
    goto LABEL_82;
  }
  if ( !Catalog::AddAllowAces(v23, this[23], a2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v26 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      v27 = 46;
      goto LABEL_81;
    }
    goto LABEL_82;
  }
  for ( i = this[1]; ; i = (_QWORD *)v50[9] )
  {
    v50 = i;
    if ( !i )
      break;
    v29 = (_QWORD *)i[10];
LABEL_49:
    if ( v29 )
    {
      for ( j = v29[1]; ; j = *(_QWORD *)(j + 40) )
      {
        if ( !j )
        {
          v29 = (_QWORD *)*v29;
          goto LABEL_49;
        }
        v31 = *(void **)(j + 16);
        if ( v31 )
        {
          bDaclDefaulted = 0;
          bDaclPresent = 0;
          pDacl = 0;
          pAce = 0;
          if ( !GetSecurityDescriptorDacl(v31, &bDaclPresent, &pDacl, &bDaclDefaulted) )
          {
            v40 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
            v41 = GetLastError();
            v40(a2, v41);
            v35 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
              {
                v36 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
                v37 = 62;
LABEL_73:
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v37,
                  &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids,
                  v36);
                v35 = (PVOID *)WPP_GLOBAL_Control;
              }
LABEL_74:
              if ( v35 != &WPP_GLOBAL_Control && (*((_DWORD *)v35 + 7) & 0x40000) != 0 )
              {
                v26 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
                v27 = 47;
                goto LABEL_81;
              }
            }
            goto LABEL_82;
          }
          if ( bDaclPresent )
          {
            for ( k = 0; k < pDacl->AceCount; ++k )
            {
              if ( !GetAce(pDacl, k, &pAce) )
              {
                v38 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
                v39 = GetLastError();
                v38(a2, v39);
                v35 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  goto LABEL_82;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
                {
                  v36 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
                  v37 = 63;
                  goto LABEL_73;
                }
                goto LABEL_74;
              }
              if ( !*(_BYTE *)pAce
                && !AddAccessAllowedAceEx(
                      v23,
                      2u,
                      *((unsigned __int8 *)pAce + 1),
                      *((_DWORD *)pAce + 1),
                      (char *)pAce + 8) )
              {
                v33 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
                v34 = GetLastError();
                v33(a2, v34);
                v35 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
                  goto LABEL_82;
                if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
                {
                  v36 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
                  v37 = 64;
                  goto LABEL_73;
                }
                goto LABEL_74;
              }
            }
          }
        }
      }
    }
  }
  if ( SetSecurityDescriptorDacl(&pSecurityDescriptor, 1, v23, 0) )
  {
    *((_OWORD *)this + 12) = pSecurityDescriptor;
    *((_OWORD *)this + 13) = v53;
    this[28] = v54;
    v51 = 0;
    AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(this + 29, v23);
  }
  else
  {
    v42 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    v43 = GetLastError();
    v42(a2, v43);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      v26 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      v27 = 48;
LABEL_81:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids, v26);
    }
LABEL_82:
    v4 = 0;
  }
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v51);
  return v4;
}

```

## disassembly

```asm
0x18007a248  mov     [rsp-8+arg_0], rbx
0x18007a24d  push    rbp
0x18007a24e  push    rsi
0x18007a24f  push    rdi
0x18007a250  push    r12
0x18007a252  push    r13
0x18007a254  push    r14
0x18007a256  push    r15
0x18007a258  lea     rbp, [rsp-27h]
0x18007a25d  sub     rsp, 0A0h
0x18007a264  mov     rdi, rdx
0x18007a267  mov     rbx, rcx
0x18007a26a  lea     r12, WPP_GLOBAL_Control
0x18007a271  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a278  cmp     rcx, r12
0x18007a27b  jz      short loc_18007A29E
0x18007a27d  test    dword ptr [rcx+1Ch], 20000h
0x18007a284  jz      short loc_18007A29E
0x18007a286  mov     edx, 24h ; '$'
0x18007a28b  mov     r9, rbx
0x18007a28e  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18007a295  mov     rcx, [rcx+10h]
0x18007a299  call    WPP_SF_q
0x18007a29e  xorps   xmm0, xmm0
0x18007a2a1  xor     eax, eax
0x18007a2a3  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18007a2a7  movups  [rbp+57h+var_50], xmm0
0x18007a2ab  mov     [rbp+57h+var_40], rax
0x18007a2af  lea     r14d, [rax+1]
0x18007a2b3  mov     edx, r14d; dwRevision
0x18007a2b6  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007a2ba  call    cs:__imp_InitializeSecurityDescriptor
0x18007a2c0  test    eax, eax
0x18007a2c2  jnz     short loc_18007A316
0x18007a2c4  mov     rax, [rdi]
0x18007a2c7  mov     rbx, [rax+48h]
0x18007a2cb  call    cs:__imp_GetLastError
0x18007a2d1  mov     edx, eax
0x18007a2d3  mov     rcx, rdi
0x18007a2d6  mov     rax, rbx
0x18007a2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2de  mov     rax, cs:WPP_GLOBAL_Control
0x18007a2e5  cmp     rax, r12
0x18007a2e8  jz      loc_18007A5D3
0x18007a2ee  test    dword ptr [rax+1Ch], 40000h
0x18007a2f5  jz      loc_18007A5D3
0x18007a2fb  mov     rax, [rdi]
0x18007a2fe  mov     rcx, rdi
0x18007a301  mov     rax, [rax+98h]
0x18007a308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a30d  lea     edx, [r14+24h]
0x18007a311  jmp     loc_18007A5B9
0x18007a316  mov     [rbp+57h+pSacl], 0
0x18007a31e  mov     [rbp+57h+pOwner], 0
0x18007a326  mov     [rbp+57h+bOwnerDefaulted], 0
0x18007a32d  mov     [rbp+57h+bSaclPresent], 0
0x18007a334  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18007a338  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18007a33c  mov     rcx, [rbx+0B8h]; pSecurityDescriptor
0x18007a343  call    cs:__imp_GetSecurityDescriptorOwner
0x18007a349  test    eax, eax
0x18007a34b  jnz     short loc_18007A3A0
0x18007a34d  mov     rax, [rdi]
0x18007a350  mov     rbx, [rax+48h]
0x18007a354  call    cs:__imp_GetLastError
0x18007a35a  mov     edx, eax
0x18007a35c  mov     rcx, rdi
0x18007a35f  mov     rax, rbx
0x18007a362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a367  mov     rax, cs:WPP_GLOBAL_Control
0x18007a36e  cmp     rax, r12
0x18007a371  jz      loc_18007A5D3
0x18007a377  test    dword ptr [rax+1Ch], 40000h
0x18007a37e  jz      loc_18007A5D3
0x18007a384  mov     rax, [rdi]
0x18007a387  mov     rcx, rdi
0x18007a38a  mov     rax, [rax+98h]
0x18007a391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a396  mov     edx, 26h ; '&'
0x18007a39b  jmp     loc_18007A5B9
0x18007a3a0  mov     r8d, [rbp+57h+bOwnerDefaulted]; bOwnerDefaulted
0x18007a3a4  mov     rdx, [rbp+57h+pOwner]; pOwner
0x18007a3a8  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007a3ac  call    cs:__imp_SetSecurityDescriptorOwner
0x18007a3b2  test    eax, eax
0x18007a3b4  jnz     short loc_18007A409
0x18007a3b6  mov     rax, [rdi]
0x18007a3b9  mov     rbx, [rax+48h]
0x18007a3bd  call    cs:__imp_GetLastError
0x18007a3c3  mov     edx, eax
0x18007a3c5  mov     rcx, rdi
0x18007a3c8  mov     rax, rbx
0x18007a3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3d0  mov     rax, cs:WPP_GLOBAL_Control
0x18007a3d7  cmp     rax, r12
0x18007a3da  jz      loc_18007A5D3
0x18007a3e0  test    dword ptr [rax+1Ch], 40000h
0x18007a3e7  jz      loc_18007A5D3
0x18007a3ed  mov     rax, [rdi]
0x18007a3f0  mov     rcx, rdi
0x18007a3f3  mov     rax, [rax+98h]
0x18007a3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a3ff  mov     edx, 27h ; '''
0x18007a404  jmp     loc_18007A5B9
0x18007a409  mov     [rbp+57h+pOwner], 0
0x18007a411  mov     [rbp+57h+bOwnerDefaulted], 0
0x18007a418  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbGroupDefaulted
0x18007a41c  lea     rdx, [rbp+57h+pOwner]; pGroup
0x18007a420  mov     rcx, [rbx+0B8h]; pSecurityDescriptor
0x18007a427  call    cs:__imp_GetSecurityDescriptorGroup
0x18007a42d  test    eax, eax
0x18007a42f  jnz     short loc_18007A484
0x18007a431  mov     rax, [rdi]
0x18007a434  mov     rbx, [rax+48h]
0x18007a438  call    cs:__imp_GetLastError
0x18007a43e  mov     edx, eax
0x18007a440  mov     rcx, rdi
0x18007a443  mov     rax, rbx
0x18007a446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a44b  mov     rax, cs:WPP_GLOBAL_Control
0x18007a452  cmp     rax, r12
0x18007a455  jz      loc_18007A5D3
0x18007a45b  test    dword ptr [rax+1Ch], 40000h
0x18007a462  jz      loc_18007A5D3
0x18007a468  mov     rax, [rdi]
0x18007a46b  mov     rcx, rdi
0x18007a46e  mov     rax, [rax+98h]
0x18007a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a47a  mov     edx, 28h ; '('
0x18007a47f  jmp     loc_18007A5B9
0x18007a484  mov     r8d, [rbp+57h+bOwnerDefaulted]; bGroupDefaulted
0x18007a488  mov     rdx, [rbp+57h+pOwner]; pGroup
0x18007a48c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007a490  call    cs:__imp_SetSecurityDescriptorGroup
0x18007a496  test    eax, eax
0x18007a498  jnz     short loc_18007A4ED
0x18007a49a  mov     rax, [rdi]
0x18007a49d  mov     rbx, [rax+48h]
0x18007a4a1  call    cs:__imp_GetLastError
0x18007a4a7  mov     edx, eax
0x18007a4a9  mov     rcx, rdi
0x18007a4ac  mov     rax, rbx
0x18007a4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4b4  mov     rax, cs:WPP_GLOBAL_Control
0x18007a4bb  cmp     rax, r12
0x18007a4be  jz      loc_18007A5D3
0x18007a4c4  test    dword ptr [rax+1Ch], 40000h
0x18007a4cb  jz      loc_18007A5D3
0x18007a4d1  mov     rax, [rdi]
0x18007a4d4  mov     rcx, rdi
0x18007a4d7  mov     rax, [rax+98h]
0x18007a4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4e3  mov     edx, 29h ; ')'
0x18007a4e8  jmp     loc_18007A5B9
0x18007a4ed  lea     r9, [rbp+57h+bOwnerDefaulted]; lpbSaclDefaulted
0x18007a4f1  lea     r8, [rbp+57h+pSacl]; pSacl
0x18007a4f5  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18007a4f9  mov     rcx, [rbx+0B8h]; pSecurityDescriptor
0x18007a500  call    cs:__imp_GetSecurityDescriptorSacl
0x18007a506  test    eax, eax
0x18007a508  jnz     short loc_18007A55A
0x18007a50a  mov     rax, [rdi]
0x18007a50d  mov     rbx, [rax+48h]
0x18007a511  call    cs:__imp_GetLastError
0x18007a517  mov     edx, eax
0x18007a519  mov     rcx, rdi
0x18007a51c  mov     rax, rbx
0x18007a51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a524  mov     rax, cs:WPP_GLOBAL_Control
0x18007a52b  cmp     rax, r12
0x18007a52e  jz      loc_18007A5D3
0x18007a534  test    dword ptr [rax+1Ch], 40000h
0x18007a53b  jz      loc_18007A5D3
0x18007a541  mov     rax, [rdi]
0x18007a544  mov     rcx, rdi
0x18007a547  mov     rax, [rax+98h]
0x18007a54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a553  mov     edx, 2Ah ; '*'
0x18007a558  jmp     short loc_18007A5B9
0x18007a55a  mov     r9d, [rbp+57h+bOwnerDefaulted]; bSaclDefaulted
0x18007a55e  mov     r8, [rbp+57h+pSacl]; pSacl
0x18007a562  mov     edx, [rbp+57h+bSaclPresent]; bSaclPresent
0x18007a565  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007a569  call    cs:__imp_SetSecurityDescriptorSacl
0x18007a56f  test    eax, eax
0x18007a571  jnz     short loc_18007A5DA
0x18007a573  mov     rax, [rdi]
0x18007a576  mov     rbx, [rax+48h]
0x18007a57a  call    cs:__imp_GetLastError
0x18007a580  mov     edx, eax
0x18007a582  mov     rcx, rdi
0x18007a585  mov     rax, rbx
0x18007a588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a58d  mov     rax, cs:WPP_GLOBAL_Control
0x18007a594  cmp     rax, r12
0x18007a597  jz      short loc_18007A5D3
0x18007a599  test    dword ptr [rax+1Ch], 40000h
0x18007a5a0  jz      short loc_18007A5D3
0x18007a5a2  mov     rax, [rdi]
0x18007a5a5  mov     rcx, rdi
0x18007a5a8  mov     rax, [rax+98h]
0x18007a5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5b4  mov     edx, 2Bh ; '+'
0x18007a5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a5c0  mov     r9d, eax
0x18007a5c3  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18007a5ca  mov     rcx, [rcx+10h]
0x18007a5ce  call    WPP_SF_d
0x18007a5d3  xor     al, al
0x18007a5d5  jmp     loc_18007A9FF
0x18007a5da  xor     r8d, r8d
0x18007a5dd  xor     edx, edx
0x18007a5df  mov     r15d, 0FFFAh
0x18007a5e5  mov     ecx, r15d
0x18007a5e8  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x18007a5ed  mov     rsi, rax
0x18007a5f0  mov     [rbp+57h+var_68], rax
0x18007a5f4  test    rax, rax
0x18007a5f7  jnz     short loc_18007A63D
0x18007a5f9  mov     rax, [rdi]
0x18007a5fc  mov     rcx, rdi
0x18007a5ff  mov     rax, [rax+18h]
0x18007a603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a608  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a60f  cmp     rcx, r12
0x18007a612  jz      loc_18007A9B3
0x18007a618  test    dword ptr [rcx+1Ch], 40000h
0x18007a61f  jz      loc_18007A9B3
0x18007a625  lea     edx, [rsi+2Ch]
0x18007a628  lea     r8, WPP_da7ed40d09913eb0c9debd1bc41fe78b_Traceguids
0x18007a62f  mov     rcx, [rcx+10h]
0x18007a633  call    WPP_SF_
0x18007a638  jmp     loc_18007A9B3
0x18007a63d  mov     r8d, 2; dwAclRevision
0x18007a643  mov     edx, r15d; nAclLength
0x18007a646  mov     rcx, rsi; pAcl
0x18007a649  call    cs:__imp_InitializeAcl
0x18007a64f  test    eax, eax
0x18007a651  jnz     short loc_18007A6A6
0x18007a653  mov     rax, [rdi]
0x18007a656  mov     rbx, [rax+48h]
0x18007a65a  call    cs:__imp_GetLastError
0x18007a660  mov     edx, eax
0x18007a662  mov     rcx, rdi
0x18007a665  mov     rax, rbx
0x18007a668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a66d  mov     rax, cs:WPP_GLOBAL_Control
0x18007a674  cmp     rax, r12
0x18007a677  jz      loc_18007A9B3
0x18007a67d  test    dword ptr [rax+1Ch], 40000h
0x18007a684  jz      loc_18007A9B3
0x18007a68a  mov     rax, [rdi]
0x18007a68d  mov     rcx, rdi
0x18007a690  mov     rax, [rax+98h]
0x18007a697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a69c  mov     edx, 2Dh ; '-'
0x18007a6a1  jmp     loc_18007A999
0x18007a6a6  mov     r8, rdi; struct IRequestContext *
0x18007a6a9  mov     rdx, [rbx+0B8h]; pSecurityDescriptor
0x18007a6b0  mov     rcx, rsi; pAcl
0x18007a6b3  call    ?AddAllowAces@Catalog@@CA_NPEAU_ACL@@PEAXAEAVIRequestContext@@@Z; Catalog::AddAllowAces(_ACL *,void *,IRequestContext &)
0x18007a6b8  test    al, al
0x18007a6ba  jnz     short loc_18007A6F5
0x18007a6bc  mov     rax, cs:WPP_GLOBAL_Control
0x18007a6c3  cmp     rax, r12
0x18007a6c6  jz      loc_18007A9B3
0x18007a6cc  test    dword ptr [rax+1Ch], 40000h
0x18007a6d3  jz      loc_18007A9B3
0x18007a6d9  mov     rax, [rdi]
0x18007a6dc  mov     rcx, rdi
0x18007a6df  mov     rax, [rax+98h]
0x18007a6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a6eb  mov     edx, 2Eh ; '.'
0x18007a6f0  jmp     loc_18007A999
0x18007a6f5  mov     rax, [rbx+8]
0x18007a6f9  mov     [rbp+57h+var_70], rax
0x18007a6fd  test    rax, rax
0x18007a700  jz      loc_18007A935
0x18007a706  mov     r12, [rax+50h]
0x18007a70a  test    r12, r12
0x18007a70d  jz      loc_18007A7D6
0x18007a713  mov     r13, [r12+8]
0x18007a718  test    r13, r13
0x18007a71b  jz      loc_18007A7CD
0x18007a721  mov     rcx, [r13+10h]; pSecurityDescriptor
0x18007a725  test    rcx, rcx
0x18007a728  jz      loc_18007A7C4
0x18007a72e  mov     [rbp+57h+bDaclDefaulted], 0
0x18007a735  mov     [rbp+57h+bDaclPresent], 0
0x18007a73c  mov     [rbp+57h+pDacl], 0
0x18007a744  mov     [rbp+57h+pAce], 0
0x18007a74c  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18007a750  lea     r8, [rbp+57h+pDacl]; pDacl
0x18007a754  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18007a758  call    cs:__imp_GetSecurityDescriptorDacl
0x18007a75e  test    eax, eax
0x18007a760  jz      loc_18007A894
0x18007a766  cmp     [rbp+57h+bDaclPresent], 0
0x18007a76a  jz      short loc_18007A7C4
0x18007a76c  xor     r15d, r15d
  ... truncated ...
```

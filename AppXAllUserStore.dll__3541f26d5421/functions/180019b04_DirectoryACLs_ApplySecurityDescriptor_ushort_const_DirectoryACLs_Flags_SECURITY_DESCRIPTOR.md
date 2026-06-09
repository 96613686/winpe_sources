# DirectoryACLs::ApplySecurityDescriptor(ushort const *,DirectoryACLs::Flags,_SECURITY_DESCRIPTOR *)

- ea: `0x180019b04`
- end: `0x180019e41`
- name: `?ApplySecurityDescriptor@DirectoryACLs@@YAJPEBGW4Flags@1@PEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(WCHAR *, char, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004a070`
- `0x18004a138`
- `0x18004a294`

## callees

- `0x1800036d4`
- `0x180007a10`
- `0x180018248`
- `0x180018f3c`
- `0x180019b04`
- `0x180019e48`
- `0x180019eb4`
- `0x18001a604`
- `0x180020248`
- `0x180020290`
- `0x18004a834`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180019ccb`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x180019ccb`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019dc8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180019dc8`

## string_xrefs

- `0x180019c06`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180019cd9`: `onecore\admin\appmodel\common\directoryacls.cpp`
- `0x180019d5b`: `onecore\admin\appmodel\common\directoryacls.cpp`

## pseudocode

```c
__int64 __fastcall DirectoryACLs::ApplySecurityDescriptor(WCHAR *a1, char a2, __int64 a3)
{
  char v4; // r8
  const WCHAR *v5; // r10
  __int16 v6; // ax
  void *v7; // r12
  void *v8; // r13
  struct _ACL *v9; // rsi
  struct _ACL *v10; // r15
  int v11; // r14d
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  int v15; // ecx
  __int16 v16; // ax
  int v17; // edi
  SECURITY_INFORMATION v18; // edi
  struct _ACL *v19; // r14
  DWORD NamedSecurityInfoW; // eax
  int v21; // eax
  unsigned int v22; // ebx
  signed int v23; // eax
  const unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  int ppsidGroup; // [rsp+20h] [rbp-49h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-49h]
  int ppsidGroupb; // [rsp+20h] [rbp-49h]
  PSECURITY_DESCRIPTOR P; // [rsp+40h] [rbp-29h] BYREF
  struct _ACL *v31; // [rsp+48h] [rbp-21h] BYREF
  PACL pAcl; // [rsp+50h] [rbp-19h] BYREF
  void *TokenHandle[2]; // [rsp+58h] [rbp-11h] BYREF
  char v34; // [rsp+68h] [rbp-1h]
  char v35; // [rsp+70h] [rbp+7h]
  __int64 v36; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  char v40; // [rsp+E0h] [rbp+77h]
  bool v41; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a2;
  v5 = a1;
  v6 = *(_WORD *)(a3 + 2);
  if ( v6 >= 0 )
  {
    v7 = *(void **)(a3 + 8);
    v8 = *(void **)(a3 + 16);
  }
  else
  {
    if ( *(_DWORD *)(a3 + 4) )
      v7 = (void *)(a3 + *(unsigned int *)(a3 + 4));
    else
      v7 = 0;
    if ( *(_DWORD *)(a3 + 8) )
      v8 = (void *)(a3 + *(unsigned int *)(a3 + 8));
    else
      v8 = 0;
  }
  if ( (v6 & 4) == 0 )
    goto LABEL_10;
  if ( v6 >= 0 )
  {
    v9 = *(struct _ACL **)(a3 + 32);
  }
  else
  {
    if ( !*(_DWORD *)(a3 + 16) )
    {
LABEL_10:
      v9 = 0;
      goto LABEL_15;
    }
    v9 = (struct _ACL *)(a3 + *(unsigned int *)(a3 + 16));
  }
LABEL_15:
  if ( (v6 & 0x10) == 0 )
  {
LABEL_16:
    v10 = 0;
    goto LABEL_21;
  }
  if ( v6 >= 0 )
  {
    v10 = *(struct _ACL **)(a3 + 24);
  }
  else
  {
    if ( !*(_DWORD *)(a3 + 12) )
      goto LABEL_16;
    v10 = (struct _ACL *)(a3 + *(unsigned int *)(a3 + 12));
  }
LABEL_21:
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v11 = v9 != 0 ? 4 : 0;
  *(_OWORD *)TokenHandle = 0;
  if ( v10 )
  {
    v12 = Common::Deployment::Privilege::Initialize(TokenHandle, 8);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 1072;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
        (const char *)(unsigned int)v12,
        ppsidGroup);
      goto LABEL_58;
    }
    v12 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)TokenHandle);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 1073;
      goto LABEL_26;
    }
    v4 = a2;
    v11 |= 0x18u;
    v5 = a1;
  }
  v15 = v11 | 1;
  if ( !v7 )
    v15 = v11;
  v16 = *(_WORD *)(a3 + 2) & 0x1000;
  v17 = v15 | 2;
  v40 = v16 != 0;
  if ( !v8 )
    v17 = v15;
  v18 = (v16 != 0 ? 0x80000000 : 0x20000000) | v17;
  if ( (*(_WORD *)(a3 + 2) & 0x2000) != 0 )
  {
    v18 |= 0x40000000u;
    v40 = 1;
  }
  else if ( v10 )
  {
    v18 |= 0x10000000u;
  }
  else
  {
    v40 = v16 != 0;
  }
  v41 = 1;
  v19 = 0;
  v31 = 0;
  if ( (v4 & 2) != 0 )
  {
    pAcl = 0;
    P = 0;
    NamedSecurityInfoW = GetNamedSecurityInfoW(v5, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &P);
    if ( NamedSecurityInfoW )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x460,
              (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
              (const char *)NamedSecurityInfoW,
              ppsidGroupa);
      AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(P);
      goto LABEL_58;
    }
    if ( pAcl )
    {
      v21 = CalculateNewDacl(
              pAcl,
              v9,
              v40,
              ((*(_WORD *)(a3 + 2) ^ *((_WORD *)P + 1)) & 0x3300) == 0,
              (a2 & 0x20) != 0,
              &v41,
              &v31);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x471,
          (unsigned int)"onecore\\admin\\appmodel\\common\\directoryacls.cpp",
          (const char *)(unsigned int)v21,
          ppsidGroupb);
        AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(P);
        if ( v31 )
          Common::GlobalHeap::Free(v31);
        v13 = v22;
        goto LABEL_58;
      }
      v19 = v31;
      if ( v31 )
        v9 = v31;
    }
    AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(P);
    if ( !v41 )
      goto LABEL_55;
  }
  v23 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, v18, v7, v8, v9, v10);
  v13 = v23;
  if ( v23 > 0 )
    v13 = (unsigned __int16)v23 | 0x80070000;
  if ( (v13 & 0x80000000) == 0 )
  {
LABEL_55:
    if ( v19 )
      Common::GlobalHeap::Free(v19);
    v13 = 0;
  }
  else
  {
    if ( Microsoft_Windows_AppXDeployment_ServerEnableBits < 0 )
    {
      v24 = RemovePIIfromFilePath(a1);
      McTemplateU0zd_EventWriteTransfer(v25, ChangingAccessRightsFailed, v24, v13);
    }
    if ( v19 )
      Common::GlobalHeap::Free(v19);
  }
LABEL_58:
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
  return v13;
}

```

## disassembly

```asm
0x180019b04  mov     [rsp-8+arg_8], rdx
0x180019b09  mov     [rsp-8+pObjectName], rcx
0x180019b0e  push    rbp
0x180019b0f  push    rbx
0x180019b10  push    rsi
0x180019b11  push    rdi
0x180019b12  push    r12
0x180019b14  push    r13
0x180019b16  push    r14
0x180019b18  push    r15
0x180019b1a  lea     rbp, [rsp-1Fh]
0x180019b1f  sub     rsp, 88h
0x180019b26  mov     rbx, r8
0x180019b29  xor     r9d, r9d
0x180019b2c  mov     r8, rdx
0x180019b2f  mov     r10, rcx
0x180019b32  movzx   eax, word ptr [rbx+2]
0x180019b36  test    ax, ax
0x180019b39  jns     short loc_180019B61
0x180019b3b  cmp     [rbx+4], r9d
0x180019b3f  jnz     short loc_180019B46
0x180019b41  mov     r12d, r9d
0x180019b44  jmp     short loc_180019B4D
0x180019b46  mov     r12d, [rbx+4]
0x180019b4a  add     r12, rbx
0x180019b4d  cmp     [rbx+8], r9d
0x180019b51  jnz     short loc_180019B58
0x180019b53  mov     r13, r9
0x180019b56  jmp     short loc_180019B69
0x180019b58  mov     r13d, [rbx+8]
0x180019b5c  add     r13, rbx
0x180019b5f  jmp     short loc_180019B69
0x180019b61  mov     r12, [rbx+8]
0x180019b65  mov     r13, [rbx+10h]
0x180019b69  test    al, 4
0x180019b6b  jnz     short loc_180019B72
0x180019b6d  mov     rsi, r9
0x180019b70  jmp     short loc_180019B89
0x180019b72  test    ax, ax
0x180019b75  jns     short loc_180019B85
0x180019b77  cmp     [rbx+10h], r9d
0x180019b7b  jz      short loc_180019B6D
0x180019b7d  mov     esi, [rbx+10h]
0x180019b80  add     rsi, rbx
0x180019b83  jmp     short loc_180019B89
0x180019b85  mov     rsi, [rbx+20h]
0x180019b89  test    al, 10h
0x180019b8b  jnz     short loc_180019B92
0x180019b8d  mov     r15, r9
0x180019b90  jmp     short loc_180019BAA
0x180019b92  test    ax, ax
0x180019b95  jns     short loc_180019BA6
0x180019b97  cmp     [rbx+0Ch], r9d
0x180019b9b  jz      short loc_180019B8D
0x180019b9d  mov     r15d, [rbx+0Ch]
0x180019ba1  add     r15, rbx
0x180019ba4  jmp     short loc_180019BAA
0x180019ba6  mov     r15, [rbx+18h]
0x180019baa  mov     rax, rsi
0x180019bad  mov     [rbp+57h+var_58], r9b
0x180019bb1  neg     rax
0x180019bb4  mov     [rbp+57h+var_50], r9b
0x180019bb8  xorps   xmm0, xmm0
0x180019bbb  mov     [rbp+57h+var_48], r9
0x180019bbf  sbb     r14d, r14d
0x180019bc2  and     r14d, 4
0x180019bc6  movdqu  xmmword ptr [rbp+57h+TokenHandle], xmm0
0x180019bcb  test    r15, r15
0x180019bce  jz      short loc_180019C26
0x180019bd0  mov     edx, 8; int
0x180019bd5  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180019bd9  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x180019bde  mov     edi, eax
0x180019be0  test    eax, eax
0x180019be2  jns     short loc_180019BEB
0x180019be4  mov     edx, 430h
0x180019be9  jmp     short loc_180019C02
0x180019beb  lea     rcx, [rbp+57h+TokenHandle]; this
0x180019bef  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x180019bf4  xor     r9d, r9d
0x180019bf7  mov     edi, eax
0x180019bf9  test    eax, eax
0x180019bfb  jns     short loc_180019C1A
0x180019bfd  mov     edx, 431h; void *
0x180019c02  mov     rcx, [rbp+5Fh]; this
0x180019c06  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180019c0d  mov     r9d, eax; char *
0x180019c10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c15  jmp     loc_180019E22
0x180019c1a  mov     r8, [rbp+57h+arg_8]
0x180019c1e  or      r14d, 18h
0x180019c22  mov     r10, [rbp+57h+pObjectName]
0x180019c26  movzx   eax, word ptr [rbx+2]
0x180019c2a  mov     edx, 1000h
0x180019c2f  mov     ecx, r14d
0x180019c32  or      ecx, 1
0x180019c35  test    r12, r12
0x180019c38  cmovz   ecx, r14d
0x180019c3c  and     ax, dx
0x180019c3f  mov     edi, ecx
0x180019c41  setnz   dl
0x180019c44  or      edi, 2
0x180019c47  test    r13, r13
0x180019c4a  mov     [rbp+57h+arg_10], dl
0x180019c4d  cmovz   edi, ecx
0x180019c50  neg     ax
0x180019c53  sbb     eax, eax
0x180019c55  and     eax, 60000000h
0x180019c5a  add     eax, 20000000h
0x180019c5f  or      edi, eax
0x180019c61  mov     eax, 2000h
0x180019c66  test    [rbx+2], ax
0x180019c6a  jz      short loc_180019C76
0x180019c6c  bts     edi, 1Eh
0x180019c70  mov     [rbp+57h+arg_10], 1
0x180019c74  jmp     short loc_180019C84
0x180019c76  test    r15, r15
0x180019c79  jz      short loc_180019C81
0x180019c7b  bts     edi, 1Ch
0x180019c7f  jmp     short loc_180019C84
0x180019c81  mov     [rbp+57h+arg_10], dl
0x180019c84  mov     [rbp+57h+arg_18], 1
0x180019c88  mov     r14, r9
0x180019c8b  mov     [rbp+57h+var_78], r9
0x180019c8f  test    r8b, 2
0x180019c93  jz      loc_180019DA7
0x180019c99  lea     rax, [rbp+57h+P]
0x180019c9d  mov     [rbp+57h+pAcl], r9
0x180019ca1  mov     [rsp+0C0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180019ca6  mov     rcx, r10; pObjectName
0x180019ca9  mov     [rsp+0C0h+ppSacl], r9; ppSacl
0x180019cae  lea     rax, [rbp+57h+pAcl]
0x180019cb2  mov     [rsp+0C0h+ppDacl], rax; ppDacl
0x180019cb7  mov     [rsp+0C0h+ppsidGroup], r9; unsigned int
0x180019cbc  mov     [rbp+57h+P], r9
0x180019cc0  xor     r9d, r9d; ppsidOwner
0x180019cc3  lea     edx, [r9+1]; ObjectType
0x180019cc7  lea     r8d, [r9+4]; SecurityInfo
0x180019ccb  call    cs:__imp_GetNamedSecurityInfoW
0x180019cd1  test    eax, eax
0x180019cd3  jz      short loc_180019CFD
0x180019cd5  mov     rcx, [rbp+5Fh]; this
0x180019cd9  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180019ce0  mov     r9d, eax; char *
0x180019ce3  mov     edx, 460h; void *
0x180019ce8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019ced  mov     rcx, [rbp+57h+P]; P
0x180019cf1  mov     edi, eax
0x180019cf3  call    ??$AutoPtrRtlHeapDeallocate@U_SECURITY_DESCRIPTOR@@@@YAXPEAU_SECURITY_DESCRIPTOR@@@Z; AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(_SECURITY_DESCRIPTOR *)
0x180019cf8  jmp     loc_180019E22
0x180019cfd  mov     rcx, [rbp+57h+pAcl]; pAcl
0x180019d01  test    rcx, rcx
0x180019d04  jz      loc_180019D98
0x180019d0a  mov     rax, [rbp+57h+P]
0x180019d0e  mov     r8, [rbp+57h+arg_8]
0x180019d12  shr     r8b, 5
0x180019d16  and     r8b, 1
0x180019d1a  movzx   edx, word ptr [rax+2]
0x180019d1e  mov     eax, 3300h
0x180019d23  xor     dx, [rbx+2]
0x180019d27  test    ax, dx
0x180019d2a  lea     rax, [rbp+57h+var_78]
0x180019d2e  mov     [rsp+0C0h+ppSacl], rax; struct _ACL **
0x180019d33  mov     rdx, rsi; Source
0x180019d36  lea     rax, [rbp+57h+arg_18]
0x180019d3a  setz    r9b; bool
0x180019d3e  mov     [rsp+0C0h+ppDacl], rax; bool *
0x180019d43  mov     byte ptr [rsp+0C0h+ppsidGroup], r8b; int
0x180019d48  mov     r8b, [rbp+57h+arg_10]; bool
0x180019d4c  call    ?CalculateNewDacl@@YAJPEAU_ACL@@QEAU1@_N22PEA_NPEAPEAU1@@Z; CalculateNewDacl(_ACL *,_ACL * const,bool,bool,bool,bool *,_ACL * *)
0x180019d51  mov     ebx, eax
0x180019d53  test    eax, eax
0x180019d55  jns     short loc_180019D8D
0x180019d57  mov     rcx, [rbp+5Fh]; this
0x180019d5b  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\common\\direc"...
0x180019d62  mov     r9d, eax; char *
0x180019d65  mov     edx, 471h; void *
0x180019d6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d6f  mov     rcx, [rbp+57h+P]; P
0x180019d73  call    ??$AutoPtrRtlHeapDeallocate@U_SECURITY_DESCRIPTOR@@@@YAXPEAU_SECURITY_DESCRIPTOR@@@Z; AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(_SECURITY_DESCRIPTOR *)
0x180019d78  mov     rcx, [rbp+57h+var_78]; void *
0x180019d7c  test    rcx, rcx
0x180019d7f  jz      short loc_180019D86
0x180019d81  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019d86  mov     edi, ebx
0x180019d88  jmp     loc_180019E22
0x180019d8d  mov     r14, [rbp+57h+var_78]
0x180019d91  test    r14, r14
0x180019d94  cmovnz  rsi, r14
0x180019d98  mov     rcx, [rbp+57h+P]; P
0x180019d9c  call    ??$AutoPtrRtlHeapDeallocate@U_SECURITY_DESCRIPTOR@@@@YAXPEAU_SECURITY_DESCRIPTOR@@@Z; AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(_SECURITY_DESCRIPTOR *)
0x180019da1  cmp     [rbp+57h+arg_18], 0
0x180019da5  jz      short loc_180019E13
0x180019da7  mov     rbx, [rbp+57h+pObjectName]
0x180019dab  mov     r9, r12; psidOwner
0x180019dae  mov     [rsp+0C0h+ppSacl], r15; pSacl
0x180019db3  mov     rcx, rbx; pObjectName
0x180019db6  mov     [rsp+0C0h+ppDacl], rsi; pDacl
0x180019dbb  mov     r8d, edi; SecurityInfo
0x180019dbe  mov     edx, 1; ObjectType
0x180019dc3  mov     [rsp+0C0h+ppsidGroup], r13; psidGroup
0x180019dc8  call    cs:__imp_SetNamedSecurityInfoW
0x180019dce  mov     edi, eax
0x180019dd0  test    eax, eax
0x180019dd2  jle     short loc_180019DDD
0x180019dd4  movzx   edi, ax
0x180019dd7  or      edi, 80070000h
0x180019ddd  test    edi, edi
0x180019ddf  jns     short loc_180019E13
0x180019de1  cmp     cs:Microsoft_Windows_AppXDeployment_ServerEnableBits, 0
0x180019de8  jge     short loc_180019E04
0x180019dea  mov     rcx, rbx; unsigned __int16 *
0x180019ded  call    ?RemovePIIfromFilePath@@YAPEBGPEBG@Z; RemovePIIfromFilePath(ushort const *)
0x180019df2  mov     r8, rax
0x180019df5  lea     rdx, ChangingAccessRightsFailed
0x180019dfc  mov     r9d, edi
0x180019dff  call    McTemplateU0zd_EventWriteTransfer
0x180019e04  test    r14, r14
0x180019e07  jz      short loc_180019E22
0x180019e09  mov     rcx, r14; void *
0x180019e0c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019e11  jmp     short loc_180019E22
0x180019e13  test    r14, r14
0x180019e16  jz      short loc_180019E20
0x180019e18  mov     rcx, r14; void *
0x180019e1b  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180019e20  xor     edi, edi
0x180019e22  lea     rcx, [rbp+57h+TokenHandle]; this
0x180019e26  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x180019e2b  mov     eax, edi
0x180019e2d  add     rsp, 88h
0x180019e34  pop     r15
0x180019e36  pop     r14
0x180019e38  pop     r13
0x180019e3a  pop     r12
0x180019e3c  pop     rdi
0x180019e3d  pop     rsi
0x180019e3e  pop     rbx
0x180019e3f  pop     rbp
0x180019e40  retn
```

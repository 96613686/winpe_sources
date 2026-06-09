# KdcBuildAuthzContext(_KDC_TICKET_INFO *,KERB_ENCRYPTED_TICKET *,uchar,AUTHZ_CLIENT_CONTEXT_HANDLE__ * *,_KDC_AUTHZ_INFO *,_KDC_AUTHZ_GROUP_BUFFERS *,long *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)

- ea: `0x1800276cc`
- end: `0x180027a71`
- name: `?KdcBuildAuthzContext@@YAJPEAU_KDC_TICKET_INFO@@PEAUKERB_ENCRYPTED_TICKET@@EPEAPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_KDC_AUTHZ_INFO@@PEAU_KDC_AUTHZ_GROUP_BUFFERS@@PEAJPEAU_UNICODE_STRING@@6PEAPEAX@Z`
- size: `933`
- prototype: `__int64 __fastcall(struct _KDC_TICKET_INFO *, struct KERB_ENCRYPTED_TICKET *, unsigned __int8, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **, struct _KDC_AUTHZ_INFO *DynamicGroupArgs, struct _KDC_AUTHZ_GROUP_BUFFERS *, int *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180024ffc`

## callees

- `0x180003908`
- `0x1800101ec`
- `0x1800276cc`
- `0x180047d28`
- `0x1800485e4`
- `0x18007dc20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027984`
- `AUTHZ!AuthzModifyClaims` at `0x180027961`
- `AUTHZ!AuthzModifyClaims` at `0x180027961`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800278d4`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x1800278d4`
- `AUTHZ!AuthzFreeContext` at `0x180027932`
- `AUTHZ!AuthzFreeContext` at `0x180027932`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcBuildAuthzContext(
        struct _KDC_TICKET_INFO *a1,
        struct KERB_ENCRYPTED_TICKET *a2,
        unsigned __int8 a3,
        struct AUTHZ_CLIENT_CONTEXT_HANDLE__ **a4,
        struct _KDC_AUTHZ_INFO *DynamicGroupArgs,
        struct _KDC_AUTHZ_GROUP_BUFFERS *a6,
        int *a7,
        struct _UNICODE_STRING *a8,
        struct _UNICODE_STRING *a9,
        void **a10)
{
  int *v13; // r12
  struct _UNICODE_STRING *v14; // r15
  struct _UNICODE_STRING *v15; // rdi
  unsigned int SidsFromTgt; // ebx
  CSecurityData *v17; // rcx
  __int64 v18; // rdx
  DWORD LastError; // eax
  __int64 v20; // rdx
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  LUID Identifier; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING v25; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v26; // [rsp+80h] [rbp-80h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h] BYREF
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h]
  __int128 v31; // [rsp+D0h] [rbp-30h]
  __int128 v32; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v33; // [rsp+F0h] [rbp-10h]
  __int128 v34; // [rsp+100h] [rbp+0h]
  __int128 v35; // [rsp+110h] [rbp+10h]
  __int128 v36; // [rsp+120h] [rbp+20h]
  AUTHZ_CLIENT_CONTEXT_HANDLE *p_hAuthzClientContext; // [rsp+130h] [rbp+30h]
  __int128 *v38; // [rsp+138h] [rbp+38h]
  struct _UNICODE_STRING *v39; // [rsp+140h] [rbp+40h]
  struct _UNICODE_STRING *v40; // [rsp+148h] [rbp+48h]
  char v41; // [rsp+150h] [rbp+50h]

  Identifier = 0;
  hAuthzClientContext = 0;
  memset_0(&v27, 0, 0x50u);
  v23 = 0;
  v25 = 0;
  v26 = 0;
  p_hAuthzClientContext = &hAuthzClientContext;
  v38 = &v27;
  v39 = &v25;
  v40 = &v26;
  v41 = 1;
  v13 = a7;
  *a7 = 0;
  *a4 = 0;
  memset_0(&v32, 0, 0x50u);
  *(_OWORD *)a6 = v32;
  *((_OWORD *)a6 + 1) = v33;
  *((_OWORD *)a6 + 2) = v34;
  *((_OWORD *)a6 + 3) = v35;
  *((_OWORD *)a6 + 4) = v36;
  v14 = a8;
  if ( a8 )
    *a8 = 0;
  v15 = a9;
  if ( a9 )
    *a9 = 0;
  if ( !KdcGlobalCDC && *((_BYTE *)a1 + 104) )
    goto LABEL_35;
  SidsFromTgt = KdcGetSidsFromTgt(
                  a2,
                  a1,
                  a3,
                  DynamicGroupArgs,
                  (struct _KDC_AUTHZ_GROUP_BUFFERS *)&v27,
                  &v23,
                  &v25,
                  &v26,
                  a10);
  if ( SidsFromTgt )
  {
    if ( v23 >= 0 )
    {
      SidsFromTgt = 0;
      goto LABEL_24;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 102;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, SidsFromTgt);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  SidsFromTgt = 60;
  if ( *(_QWORD *)DynamicGroupArgs )
  {
    if ( !AuthzInitializeContextFromSid(
            2u,
            **(PSID **)DynamicGroupArgs,
            KdcAuthzRM,
            0,
            Identifier,
            DynamicGroupArgs,
            &hAuthzClientContext) )
    {
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_23;
      LastError = GetLastError();
      v20 = 104;
LABEL_22:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
LABEL_23:
      *v13 = -1073741595;
      goto LABEL_24;
    }
    if ( *((_QWORD *)DynamicGroupArgs + 2) )
    {
      LODWORD(a7) = 1;
      if ( !(unsigned int)AuthzModifyClaims(hAuthzClientContext, 13, &a7) )
      {
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_23;
        }
        LastError = GetLastError();
        v20 = 105;
        goto LABEL_22;
      }
    }
    *a4 = hAuthzClientContext;
    hAuthzClientContext = 0;
    *(_OWORD *)a6 = v27;
    *((_OWORD *)a6 + 1) = v28;
    *((_OWORD *)a6 + 2) = v29;
    *((_OWORD *)a6 + 3) = v30;
    *((_OWORD *)a6 + 4) = v31;
    memset_0(&v32, 0, 0x50u);
    v27 = v32;
    v28 = v33;
    v29 = v34;
    v30 = v35;
    v31 = v36;
    if ( v14 )
    {
      *v14 = v25;
      v25 = 0;
    }
    if ( v15 )
    {
      *v15 = v26;
      v26 = 0;
    }
LABEL_35:
    SidsFromTgt = 0;
    goto LABEL_36;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 103;
    goto LABEL_17;
  }
LABEL_24:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
LABEL_36:
  KdcFreeAuthzInfo((struct _KDC_AUTHZ_GROUP_BUFFERS *)&v27);
  KerbFreeString(&v25);
  KerbFreeString(&v26);
  return SidsFromTgt;
}

```

## disassembly

```asm
0x1800276cc  mov     [rsp-8+arg_0], rbx
0x1800276d1  mov     [rsp-8+arg_18], r9
0x1800276d6  mov     [rsp-8+arg_8], rdx
0x1800276db  push    rbp
0x1800276dc  push    rsi
0x1800276dd  push    rdi
0x1800276de  push    r12
0x1800276e0  push    r13
0x1800276e2  push    r14
0x1800276e4  push    r15
0x1800276e6  lea     rbp, [rsp-60h]
0x1800276eb  sub     rsp, 160h
0x1800276f2  mov     rdi, r9
0x1800276f5  mov     r13b, r8b
0x1800276f8  mov     rbx, rcx
0x1800276fb  xor     esi, esi
0x1800276fd  mov     qword ptr [rsp+190h+var_130.LowPart], rsi
0x180027702  mov     [rsp+190h+hAuthzClientContext], rsi
0x180027707  lea     r14d, [rsi+50h]
0x18002770b  mov     r8d, r14d; Size
0x18002770e  xor     edx, edx; Val
0x180027710  lea     rcx, [rbp+90h+var_100]; void *
0x180027714  call    memset_0
0x180027719  mov     [rsp+190h+var_138], esi
0x18002771d  xorps   xmm0, xmm0
0x180027720  movups  xmmword ptr [rsp+190h+var_120.Length], xmm0
0x180027725  xorps   xmm1, xmm1
0x180027728  movups  xmmword ptr [rbp+90h+var_110.Length], xmm1
0x18002772c  lea     rax, [rsp+190h+hAuthzClientContext]
0x180027731  mov     [rbp+90h+var_60], rax
0x180027735  lea     rax, [rbp+90h+var_100]
0x180027739  mov     [rbp+90h+var_58], rax
0x18002773d  lea     rax, [rsp+190h+var_120]
0x180027742  mov     [rbp+90h+var_50], rax
0x180027746  lea     rax, [rbp+90h+var_110]
0x18002774a  mov     [rbp+90h+var_48], rax
0x18002774e  mov     [rbp+90h+var_40], 1
0x180027752  mov     r12, [rbp+90h+arg_30]
0x180027759  mov     [r12], esi
0x18002775d  mov     [rdi], rsi
0x180027760  mov     r8d, r14d; Size
0x180027763  xor     edx, edx; Val
0x180027765  lea     rcx, [rbp+90h+var_B0]; void *
0x180027769  call    memset_0
0x18002776e  mov     r14, [rbp+90h+arg_28]
0x180027775  movups  xmm0, [rbp+90h+var_B0]
0x180027779  movaps  xmmword ptr [r14], xmm0
0x18002777d  movups  xmm1, [rbp+90h+var_A0]
0x180027781  movaps  xmmword ptr [r14+10h], xmm1
0x180027786  movups  xmm0, [rbp+90h+var_90]
0x18002778a  movaps  xmmword ptr [r14+20h], xmm0
0x18002778f  movups  xmm1, [rbp+90h+var_80]
0x180027793  movaps  xmmword ptr [r14+30h], xmm1
0x180027798  movups  xmm0, [rbp+90h+var_70]
0x18002779c  movaps  xmmword ptr [r14+40h], xmm0
0x1800277a1  mov     r15, [rbp+90h+arg_38]
0x1800277a8  test    r15, r15
0x1800277ab  jz      short loc_1800277B5
0x1800277ad  xorps   xmm0, xmm0
0x1800277b0  movdqu  xmmword ptr [r15], xmm0
0x1800277b5  mov     rdi, [rbp+90h+arg_40]
0x1800277bc  test    rdi, rdi
0x1800277bf  jz      short loc_1800277C8
0x1800277c1  xorps   xmm0, xmm0
0x1800277c4  movdqu  xmmword ptr [rdi], xmm0
0x1800277c8  cmp     cs:?KdcGlobalCDC@@3HA, esi; int KdcGlobalCDC
0x1800277ce  jnz     short loc_1800277DA
0x1800277d0  cmp     [rbx+68h], sil
0x1800277d4  jnz     loc_180027A36
0x1800277da  mov     rax, [rbp+90h+arg_48]
0x1800277e1  mov     [rsp+190h+var_150], rax; void **
0x1800277e6  lea     rax, [rbp+90h+var_110]
0x1800277ea  mov     [rsp+190h+var_158], rax; struct _UNICODE_STRING *
0x1800277ef  lea     rax, [rsp+190h+var_120]
0x1800277f4  mov     [rsp+190h+phAuthzClientContext], rax; struct _UNICODE_STRING *
0x1800277f9  lea     rax, [rsp+190h+var_138]
0x1800277fe  mov     [rsp+190h+DynamicGroupArgs], rax; int *
0x180027803  lea     rax, [rbp+90h+var_100]
0x180027807  mov     qword ptr [rsp+190h+Identifier.LowPart], rax; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x18002780c  mov     rsi, [rbp+90h+arg_20]
0x180027813  mov     r9, rsi; struct _KDC_AUTHZ_INFO *
0x180027816  mov     r8b, r13b; unsigned __int8
0x180027819  mov     rdx, rbx; struct _KDC_TICKET_INFO *
0x18002781c  mov     rcx, [rbp+90h+arg_8]; struct KERB_ENCRYPTED_TICKET *
0x180027823  call    ?KdcGetSidsFromTgt@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAU_KDC_TICKET_INFO@@EPEAU_KDC_AUTHZ_INFO@@PEAU_KDC_AUTHZ_GROUP_BUFFERS@@PEAJPEAU_UNICODE_STRING@@5PEAPEAX@Z; KdcGetSidsFromTgt(KERB_ENCRYPTED_TICKET *,_KDC_TICKET_INFO *,uchar,_KDC_AUTHZ_INFO *,_KDC_AUTHZ_GROUP_BUFFERS *,long *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x180027828  mov     ebx, eax
0x18002782a  test    eax, eax
0x18002782c  jz      short loc_180027864
0x18002782e  cmp     [rsp+190h+var_138], 0
0x180027833  jl      short loc_18002783C
0x180027835  xor     ebx, ebx
0x180027837  jmp     loc_180027924
0x18002783c  lea     rax, WPP_GLOBAL_Control
0x180027843  mov     rcx, cs:WPP_GLOBAL_Control
0x18002784a  cmp     rcx, rax
0x18002784d  jz      loc_180027924
0x180027853  test    byte ptr [rcx+1Ch], 1
0x180027857  jz      loc_180027924
0x18002785d  mov     edx, 66h ; 'f'
0x180027862  jmp     short loc_180027895
0x180027864  mov     rdx, [rsi]
0x180027867  mov     ebx, 3Ch ; '<'
0x18002786c  test    rdx, rdx
0x18002786f  jnz     short loc_1800278AA
0x180027871  lea     rax, WPP_GLOBAL_Control
0x180027878  mov     rcx, cs:WPP_GLOBAL_Control
0x18002787f  cmp     rcx, rax
0x180027882  jz      loc_180027924
0x180027888  test    byte ptr [rcx+1Ch], 1
0x18002788c  jz      loc_180027924
0x180027892  lea     edx, [rbx+2Bh]
0x180027895  mov     r9d, ebx
0x180027898  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002789f  mov     rcx, [rcx+10h]
0x1800278a3  call    WPP_SF_d
0x1800278a8  jmp     short loc_180027924
0x1800278aa  lea     rax, [rsp+190h+hAuthzClientContext]
0x1800278af  mov     [rsp+190h+phAuthzClientContext], rax; phAuthzClientContext
0x1800278b4  mov     [rsp+190h+DynamicGroupArgs], rsi; DynamicGroupArgs
0x1800278b9  mov     rax, qword ptr [rsp+190h+var_130.LowPart]
0x1800278be  mov     qword ptr [rsp+190h+Identifier.LowPart], rax; Identifier
0x1800278c3  xor     r9d, r9d; pExpirationTime
0x1800278c6  mov     r8, cs:?KdcAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x1800278cd  mov     rdx, [rdx]; UserSid
0x1800278d0  lea     ecx, [r9+2]; Flags
0x1800278d4  call    cs:__imp_AuthzInitializeContextFromSid
0x1800278da  test    eax, eax
0x1800278dc  jnz     short loc_18002793D
0x1800278de  lea     rax, WPP_GLOBAL_Control
0x1800278e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278ec  cmp     rcx, rax
0x1800278ef  jz      short loc_18002791C
0x1800278f1  test    byte ptr [rcx+1Ch], 1
0x1800278f5  jz      short loc_18002791C
0x1800278f7  call    cs:__imp_GetLastError
0x1800278fd  mov     edx, 68h ; 'h'
0x180027902  mov     r9d, eax
0x180027905  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002790c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027913  mov     rcx, [rcx+10h]
0x180027917  call    WPP_SF_d
0x18002791c  mov     dword ptr [r12], 0C00000E5h
0x180027924  mov     rcx, [rsp+190h+hAuthzClientContext]; hAuthzClientContext
0x180027929  test    rcx, rcx
0x18002792c  jz      loc_180027A38
0x180027932  call    cs:__imp_AuthzFreeContext
0x180027938  jmp     loc_180027A38
0x18002793d  mov     r9, [rsi+10h]
0x180027941  xor     esi, esi
0x180027943  test    r9, r9
0x180027946  jz      short loc_180027992
0x180027948  mov     dword ptr [rbp+90h+arg_30], 1
0x180027952  lea     r8, [rbp+90h+arg_30]
0x180027959  lea     edx, [rsi+0Dh]
0x18002795c  mov     rcx, [rsp+190h+hAuthzClientContext]
0x180027961  call    cs:__imp_AuthzModifyClaims
0x180027967  test    eax, eax
0x180027969  jnz     short loc_180027992
0x18002796b  lea     rax, WPP_GLOBAL_Control
0x180027972  mov     rcx, cs:WPP_GLOBAL_Control
0x180027979  cmp     rcx, rax
0x18002797c  jz      short loc_18002791C
0x18002797e  test    byte ptr [rcx+1Ch], 1
0x180027982  jz      short loc_18002791C
0x180027984  call    cs:__imp_GetLastError
0x18002798a  lea     edx, [rsi+69h]
0x18002798d  jmp     loc_180027902
0x180027992  mov     rax, [rsp+190h+hAuthzClientContext]
0x180027997  mov     rcx, [rbp+90h+arg_18]
0x18002799e  mov     [rcx], rax
0x1800279a1  mov     [rsp+190h+hAuthzClientContext], rsi
0x1800279a6  movaps  xmm0, [rbp+90h+var_100]
0x1800279aa  movaps  xmmword ptr [r14], xmm0
0x1800279ae  movaps  xmm1, [rbp+90h+var_F0]
0x1800279b2  movaps  xmmword ptr [r14+10h], xmm1
0x1800279b7  movaps  xmm0, [rbp+90h+var_E0]
0x1800279bb  movaps  xmmword ptr [r14+20h], xmm0
0x1800279c0  movaps  xmm1, [rbp+90h+var_D0]
0x1800279c4  movaps  xmmword ptr [r14+30h], xmm1
0x1800279c9  movaps  xmm0, [rbp+90h+var_C0]
0x1800279cd  movaps  xmmword ptr [r14+40h], xmm0
0x1800279d2  xor     edx, edx; Val
0x1800279d4  lea     r8d, [rdx+50h]; Size
0x1800279d8  lea     rcx, [rbp+90h+var_B0]; void *
0x1800279dc  call    memset_0
0x1800279e1  movups  xmm0, [rbp+90h+var_B0]
0x1800279e5  movaps  [rbp+90h+var_100], xmm0
0x1800279e9  movups  xmm1, [rbp+90h+var_A0]
0x1800279ed  movaps  [rbp+90h+var_F0], xmm1
0x1800279f1  movups  xmm0, [rbp+90h+var_90]
0x1800279f5  movaps  [rbp+90h+var_E0], xmm0
0x1800279f9  movups  xmm1, [rbp+90h+var_80]
0x1800279fd  movaps  [rbp+90h+var_D0], xmm1
0x180027a01  movups  xmm0, [rbp+90h+var_70]
0x180027a05  movaps  [rbp+90h+var_C0], xmm0
0x180027a09  test    r15, r15
0x180027a0c  jz      short loc_180027A21
0x180027a0e  movaps  xmm0, xmmword ptr [rsp+190h+var_120.Length]
0x180027a13  movdqu  xmmword ptr [r15], xmm0
0x180027a18  xorps   xmm1, xmm1
0x180027a1b  movdqa  xmmword ptr [rsp+190h+var_120.Length], xmm1
0x180027a21  test    rdi, rdi
0x180027a24  jz      short loc_180027A36
0x180027a26  movaps  xmm0, xmmword ptr [rbp+90h+var_110.Length]
0x180027a2a  movdqu  xmmword ptr [rdi], xmm0
0x180027a2e  xorps   xmm1, xmm1
0x180027a31  movdqa  xmmword ptr [rbp+90h+var_110.Length], xmm1
0x180027a36  mov     ebx, esi
0x180027a38  lea     rcx, [rbp+90h+var_100]; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x180027a3c  call    ?KdcFreeAuthzInfo@@YAXPEAU_KDC_AUTHZ_GROUP_BUFFERS@@@Z; KdcFreeAuthzInfo(_KDC_AUTHZ_GROUP_BUFFERS *)
0x180027a41  lea     rcx, [rsp+190h+var_120]
0x180027a46  call    KerbFreeString
0x180027a4b  lea     rcx, [rbp+90h+var_110]
0x180027a4f  call    KerbFreeString
0x180027a54  mov     eax, ebx
0x180027a56  mov     rbx, [rsp+190h+arg_0]
0x180027a5e  add     rsp, 160h
0x180027a65  pop     r15
0x180027a67  pop     r14
0x180027a69  pop     r13
0x180027a6b  pop     r12
0x180027a6d  pop     rdi
0x180027a6e  pop     rsi
0x180027a6f  pop     rbp
0x180027a70  retn
```

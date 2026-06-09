# KdcGetS4UTicketInfo(_KDC_S4U_TICKET_INFO *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,KERB_EXT_ERROR *,_SAM_CLAIMS_BLOB *,_KDC_TICKET_INFO *)

- ea: `0x18002b910`
- end: `0x18002bdee`
- name: `?KdcGetS4UTicketInfo@@YAJPEAU_KDC_S4U_TICKET_INFO@@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAUKERB_EXT_ERROR@@PEAU_SAM_CLAIMS_BLOB@@PEAU_KDC_TICKET_INFO@@@Z`
- size: `1246`
- prototype: `__int64 __usercall@<rax>(struct _KDC_S4U_TICKET_INFO *@<rcx>, struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *@<rdx>, struct _USER_INTERNAL6_INFORMATION **@<r8>, struct _SID_AND_ATTRIBUTES_LIST *@<r9>, struct KERB_EXT_ERROR *, struct _SAM_CLAIMS_BLOB *, struct _KDC_TICKET_INFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180024ffc`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x180005cc0`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x1800210a8`
- `0x18002160c`
- `0x180027e50`
- `0x180028a60`
- `0x18002b910`
- `0x18002d944`
- `0x180059d38`
- `0x18006349c`
- `0x180072338`
- `0x18007c4d4`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x18002bd27`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x18002bd27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KdcGetS4UTicketInfo(
        struct _KDC_S4U_TICKET_INFO *a1,
        struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *a2,
        struct _USER_INTERNAL6_INFORMATION **a3,
        struct _SID_AND_ATTRIBUTES_LIST *a4,
        struct KERB_EXT_ERROR *a5,
        struct _SAM_CLAIMS_BLOB *a6,
        struct _KDC_TICKET_INFO *a7)
{
  unsigned int v11; // r10d
  unsigned int v12; // r14d
  int v13; // r9d
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  unsigned __int8 v16; // r8
  CSecurityData *v17; // rax
  __int64 v18; // rdx
  CSecurityData *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  struct _USER_INTERNAL6_INFORMATION *v22; // r9
  int v23; // eax
  unsigned __int8 v25[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v26; // [rsp+88h] [rbp-78h] BYREF
  int v27; // [rsp+90h] [rbp-70h] BYREF
  void *v28; // [rsp+98h] [rbp-68h] BYREF
  struct _KDC_TICKET_INFO *v29; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-38h] BYREF
  struct _SAM_CLAIMS_BLOB *v33; // [rsp+D0h] [rbp-30h]
  struct _UNICODE_STRING v34; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v35[6]; // [rsp+E8h] [rbp-18h] BYREF
  char v36; // [rsp+118h] [rbp+18h]
  _QWORD v37[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v38[44]; // [rsp+130h] [rbp+30h] BYREF
  int v39; // [rsp+15Ch] [rbp+5Ch]
  int v40; // [rsp+171h] [rbp+71h]
  __int16 v41; // [rsp+175h] [rbp+75h]
  char v42; // [rsp+177h] [rbp+77h]
  __int16 v43; // [rsp+189h] [rbp+89h]
  char v44; // [rsp+18Bh] [rbp+8Bh]
  int v45; // [rsp+194h] [rbp+94h]
  __int128 v46; // [rsp+1A0h] [rbp+A0h]
  __int64 v47; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v48; // [rsp+1C0h] [rbp+C0h]
  int v49; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v50[188]; // [rsp+1D4h] [rbp+D4h] BYREF

  v33 = a6;
  v29 = a7;
  v34 = 0;
  v25[0] = 0;
  v32 = 0;
  v31 = 0;
  v28 = 0;
  memset_0(&v49, 0, 0xC0u);
  v26 = 0;
  v37[0] = 0;
  v37[1] = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset_0(v38, 0, 0x88u);
  v47 = 0;
  v48 = 0;
  v30 = 0;
  v11 = (*((_DWORD *)a1 + 74) & 0x20000 | 0x8000u) >> 14;
  v35[0] = &v34;
  v35[1] = &v29;
  v35[2] = v37;
  v35[3] = &v30;
  v35[4] = &v26;
  v35[5] = &v28;
  v36 = 1;
  *a3 = 0;
  *(_OWORD *)a4 = 0;
  v12 = (*((_DWORD *)a1 + 74) & 0x400) != 0 ? 0xFFFFFFFC : 0;
  v13 = *((_DWORD *)a1 + 74) & 0x200000;
  v14 = v11 & 0xFFFFFFFD;
  if ( !v13 )
    v14 = v11;
  v15 = KdcNormalize(
          *((struct _KERB_INTERNAL_NAME **)a1 + 28),
          0,
          0,
          0,
          v13 != 0 ? 1045 : 85,
          v14,
          0,
          v25,
          &v34,
          (struct _KDC_TICKET_INFO *)v37,
          a5,
          &v28,
          (*((_DWORD *)a1 + 74) & 0x400) != 0 ? 826273743 : 826264527,
          (*((_DWORD *)a1 + 74) & 0x200000) != 0 ? 536870913 : 1,
          &v26,
          (struct _SID_AND_ATTRIBUTES_LIST *)&v30);
  if ( v15 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 14;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v15);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  if ( v25[0] )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v20 = 15;
LABEL_31:
    WPP_SF_(*((_QWORD *)v19 + 2), v20, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
LABEL_32:
    v15 = 6;
    goto LABEL_42;
  }
  v27 = KerbDuplicateStringEx(
          (struct _UNICODE_STRING *)((char *)a1 + 312),
          (const struct _UNICODE_STRING *)v26 + 3,
          v16);
  if ( v27 < 0 )
  {
    v15 = 60;
    goto LABEL_42;
  }
  v15 = KerbCheckLogonRestrictions((_DWORD)v28, 0, (_DWORD)v26, v12 + 7, (__int64)&v32, (__int64)&v31, (__int64)&v27);
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        (unsigned int)v27);
    FillExtendedError(v27, 3, 1028, 621, a5);
    goto LABEL_42;
  }
  if ( (*((_DWORD *)a1 + 74) & 0x200000) == 0 )
  {
    if ( (int)KdcCheckGroupExpansionAccess(a1, a2, v26) < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_32;
      v20 = 18;
      goto LABEL_31;
    }
LABEL_33:
    if ( (v38[24] & 1) == 0 )
      *((_DWORD *)a1 + 74) |= 8u;
    memset_0(v50, 0, sizeof(v50));
    v49 = 1145044992;
    v23 = SamIUpdateLogonStatistics(v28, &v49);
    if ( v23 < 0
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        (unsigned int)v23);
    }
    *a3 = v26;
    v26 = 0;
    *(_OWORD *)v33 = v46;
    v46 = 0;
    *(_OWORD *)a4 = v30;
    v30 = 0;
    if ( v29 )
      _KDC_TICKET_INFO::operator=(v29, v37);
    v15 = 0;
    goto LABEL_42;
  }
  v15 = KdcDmsaAuthzCheck(a2, *((PSECURITY_DESCRIPTOR *)v26 + 92));
  if ( !v15 )
    goto LABEL_33;
  v22 = v26;
  if ( v26 || (MicrosoftTelemetryAssertTriggeredNoArgs(v21), (v22 = v26) != 0) )
    KdcLogDmsaAuthzFailure((char *)a1 + 24, (char *)v22 + 48, v15, *((unsigned int *)v22 + 175));
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 17;
    goto LABEL_26;
  }
LABEL_42:
  v36 = 0;
  lambda_d6f26e50ab51d66d8b486b6b791740ab_::operator()(v35);
  std::vector<unsigned int>::_Tidy((__int64)&v47);
  return v15;
}

```

## disassembly

```asm
0x18002b910  push    rbp
0x18002b912  push    rbx
0x18002b913  push    rsi
0x18002b914  push    rdi
0x18002b915  push    r12
0x18002b917  push    r13
0x18002b919  push    r14
0x18002b91b  push    r15
0x18002b91d  lea     rbp, [rsp-1A8h]
0x18002b925  sub     rsp, 2A8h
0x18002b92c  mov     rax, cs:__security_cookie
0x18002b933  xor     rax, rsp
0x18002b936  mov     [rbp+1E0h+var_50], rax
0x18002b93d  mov     r13, r9
0x18002b940  mov     r12, r8
0x18002b943  mov     rsi, rdx
0x18002b946  mov     rdi, rcx
0x18002b949  mov     r15, [rbp+1E0h+arg_20]
0x18002b950  mov     rax, [rbp+1E0h+arg_28]
0x18002b957  mov     [rbp+1E0h+var_210], rax
0x18002b95b  mov     rax, [rbp+1E0h+arg_30]
0x18002b962  mov     [rbp+1E0h+var_240], rax
0x18002b966  xorps   xmm0, xmm0
0x18002b969  movups  xmmword ptr [rbp+1E0h+var_208.Length], xmm0
0x18002b96d  xor     ebx, ebx
0x18002b96f  mov     [rbp+1E0h+var_260], bl
0x18002b972  mov     [rbp+1E0h+var_218], rbx
0x18002b976  mov     [rbp+1E0h+var_220], rbx
0x18002b97a  mov     [rbp+1E0h+var_248], rbx
0x18002b97e  xor     edx, edx; Val
0x18002b980  mov     r8d, 0C0h; Size
0x18002b986  lea     rcx, [rbp+1E0h+var_110]; void *
0x18002b98d  call    memset_0
0x18002b992  mov     [rbp+1E0h+var_258], rbx
0x18002b996  mov     [rbp+1E0h+var_1C0], rbx
0x18002b99a  mov     [rbp+1E0h+var_1B8], rbx
0x18002b99e  xor     eax, eax
0x18002b9a0  mov     [rbp+1E0h+var_184], eax
0x18002b9a3  mov     [rbp+1E0h+var_16F], eax
0x18002b9a6  mov     [rbp+1E0h+var_16B], ax
0x18002b9aa  mov     [rbp+1E0h+var_169], al
0x18002b9ad  mov     [rbp+1E0h+var_157], ax
0x18002b9b4  mov     [rbp+1E0h+var_155], al
0x18002b9ba  mov     [rbp+1E0h+var_14C], eax
0x18002b9c0  xor     edx, edx; Val
0x18002b9c2  mov     r8d, 88h; Size
0x18002b9c8  lea     rcx, [rbp+1E0h+var_1B0]; void *
0x18002b9cc  call    memset_0
0x18002b9d1  mov     [rbp+1E0h+var_128], rbx
0x18002b9d8  xorps   xmm0, xmm0
0x18002b9db  movdqa  [rbp+1E0h+var_120], xmm0
0x18002b9e3  movups  [rbp+1E0h+var_230], xmm0
0x18002b9e7  mov     r10d, [rdi+128h]
0x18002b9ee  and     r10d, 20000h
0x18002b9f5  bts     r10d, 0Fh
0x18002b9fa  shr     r10d, 0Eh
0x18002b9fe  lea     rax, [rbp+1E0h+var_208]
0x18002ba02  mov     [rbp+1E0h+var_1F8], rax
0x18002ba06  lea     rax, [rbp+1E0h+var_240]
0x18002ba0a  mov     [rbp+1E0h+var_1F0], rax
0x18002ba0e  lea     rax, [rbp+1E0h+var_1C0]
0x18002ba12  mov     [rbp+1E0h+var_1E8], rax
0x18002ba16  lea     rax, [rbp+1E0h+var_230]
0x18002ba1a  mov     [rbp+1E0h+var_1E0], rax
0x18002ba1e  lea     rax, [rbp+1E0h+var_258]
0x18002ba22  mov     [rbp+1E0h+var_1D8], rax
0x18002ba26  lea     rax, [rbp+1E0h+var_248]
0x18002ba2a  mov     [rbp+1E0h+var_1D0], rax
0x18002ba2e  mov     [rbp+1E0h+var_1C8], 1
0x18002ba32  mov     [r12], rbx
0x18002ba36  movdqu  xmmword ptr [r13+0], xmm0
0x18002ba3c  mov     r9d, [rdi+128h]
0x18002ba43  mov     ecx, r9d
0x18002ba46  and     ecx, 400h
0x18002ba4c  mov     eax, ecx
0x18002ba4e  neg     eax
0x18002ba50  sbb     r14d, r14d
0x18002ba53  and     r14d, 0FFFFFFFCh
0x18002ba57  and     r9d, 200000h
0x18002ba5e  mov     eax, r9d
0x18002ba61  neg     eax
0x18002ba63  sbb     edx, edx
0x18002ba65  and     edx, 20000000h
0x18002ba6b  inc     edx
0x18002ba6d  neg     ecx
0x18002ba6f  sbb     eax, eax
0x18002ba71  and     eax, 2400h
0x18002ba76  add     eax, 313FCBCFh
0x18002ba7b  mov     r8d, r10d
0x18002ba7e  and     r8d, 0FFFFFFFDh
0x18002ba82  test    r9d, r9d
0x18002ba85  cmovz   r8d, r10d
0x18002ba89  neg     r9d
0x18002ba8c  sbb     ecx, ecx
0x18002ba8e  and     ecx, 3C0h
0x18002ba94  add     ecx, 55h ; 'U'
0x18002ba97  lea     r9, [rbp+1E0h+var_230]
0x18002ba9b  mov     [rsp+2E0h+var_268], r9; struct _SID_AND_ATTRIBUTES_LIST *
0x18002baa0  lea     r9, [rbp+1E0h+var_258]
0x18002baa4  mov     [rsp+2E0h+var_270], r9; struct _USER_INTERNAL6_INFORMATION **
0x18002baa9  mov     [rsp+2E0h+var_278], edx; unsigned int
0x18002baad  mov     [rsp+2E0h+var_280], eax; unsigned int
0x18002bab1  lea     rax, [rbp+1E0h+var_248]
0x18002bab5  mov     [rsp+2E0h+var_288], rax; void **
0x18002baba  mov     [rsp+2E0h+var_290], r15; struct KERB_EXT_ERROR *
0x18002babf  lea     rax, [rbp+1E0h+var_1C0]
0x18002bac3  mov     [rsp+2E0h+var_298], rax; struct _KDC_TICKET_INFO *
0x18002bac8  lea     rax, [rbp+1E0h+var_208]
0x18002bacc  mov     [rsp+2E0h+var_2A0], rax; struct _UNICODE_STRING *
0x18002bad1  lea     rax, [rbp+1E0h+var_260]
0x18002bad5  mov     [rsp+2E0h+var_2A8], rax; unsigned __int8 *
0x18002bada  mov     [rsp+2E0h+var_2B0], rbx; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18002badf  mov     [rsp+2E0h+var_2B8], r8d; unsigned int
0x18002bae4  mov     dword ptr [rsp+2E0h+var_2C0], ecx; unsigned int
0x18002bae8  xor     r9d, r9d; struct _UNICODE_STRING *
0x18002baeb  xor     r8d, r8d; struct _UNICODE_STRING *
0x18002baee  xor     edx, edx; struct _UNICODE_STRING *
0x18002baf0  mov     rcx, [rdi+0E0h]; struct _KERB_INTERNAL_NAME *
0x18002baf7  call    ?KdcNormalize@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@11KKPEAU_SAM_MAPPED_ATTRIBUTE_SET@@PEAE1PEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@@Z; KdcNormalize(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,_SAM_MAPPED_ATTRIBUTE_SET *,uchar *,_UNICODE_STRING *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *)
0x18002bafc  mov     ebx, eax
0x18002bafe  test    eax, eax
0x18002bb00  jz      short loc_18002BB2D
0x18002bb02  lea     rcx, WPP_GLOBAL_Control
0x18002bb09  mov     rax, cs:WPP_GLOBAL_Control
0x18002bb10  cmp     rax, rcx
0x18002bb13  jz      loc_18002BDAF
0x18002bb19  test    byte ptr [rax+1Ch], 1
0x18002bb1d  jz      loc_18002BDAF
0x18002bb23  mov     edx, 0Eh
0x18002bb28  jmp     loc_18002BC8E
0x18002bb2d  cmp     [rbp+1E0h+var_260], 0
0x18002bb31  jz      short loc_18002BB5E
0x18002bb33  lea     rcx, WPP_GLOBAL_Control
0x18002bb3a  mov     rax, cs:WPP_GLOBAL_Control
0x18002bb41  cmp     rax, rcx
0x18002bb44  jz      loc_18002BCE7
0x18002bb4a  test    byte ptr [rax+1Ch], 1
0x18002bb4e  jz      loc_18002BCE7
0x18002bb54  mov     edx, 0Fh
0x18002bb59  jmp     loc_18002BCD7
0x18002bb5e  mov     rdx, [rbp+1E0h+var_258]
0x18002bb62  add     rdx, 30h ; '0'; struct _UNICODE_STRING *
0x18002bb66  lea     rcx, [rdi+138h]; struct _UNICODE_STRING *
0x18002bb6d  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18002bb72  mov     [rbp+1E0h+var_250], eax
0x18002bb75  test    eax, eax
0x18002bb77  jns     short loc_18002BB83
0x18002bb79  mov     ebx, 3Ch ; '<'
0x18002bb7e  jmp     loc_18002BDAF
0x18002bb83  lea     rax, [rbp+1E0h+var_250]
0x18002bb87  mov     [rsp+2E0h+var_2B0], rax
0x18002bb8c  lea     rax, [rbp+1E0h+var_220]
0x18002bb90  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x18002bb95  lea     rax, [rbp+1E0h+var_218]
0x18002bb99  mov     [rsp+2E0h+var_2C0], rax
0x18002bb9e  lea     r9d, [r14+7]
0x18002bba2  mov     r8, [rbp+1E0h+var_258]
0x18002bba6  xor     edx, edx
0x18002bba8  mov     rcx, [rbp+1E0h+var_248]
0x18002bbac  call    KerbCheckLogonRestrictions
0x18002bbb1  mov     ebx, eax
0x18002bbb3  test    eax, eax
0x18002bbb5  jz      short loc_18002BC0D
0x18002bbb7  lea     rcx, WPP_GLOBAL_Control
0x18002bbbe  mov     r10, cs:WPP_GLOBAL_Control
0x18002bbc5  cmp     r10, rcx
0x18002bbc8  jz      short loc_18002BBEA
0x18002bbca  test    byte ptr [r10+1Ch], 1
0x18002bbcf  jz      short loc_18002BBEA
0x18002bbd1  mov     edx, 10h
0x18002bbd6  mov     r9d, [rbp+1E0h+var_250]
0x18002bbda  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002bbe1  mov     rcx, [r10+10h]
0x18002bbe5  call    WPP_SF_d
0x18002bbea  mov     [rsp+2E0h+var_2C0], r15; struct KERB_EXT_ERROR *
0x18002bbef  mov     edx, 3; unsigned int
0x18002bbf4  mov     r9d, 26Dh; unsigned int
0x18002bbfa  mov     r8d, 404h; unsigned int
0x18002bc00  mov     ecx, [rbp+1E0h+var_250]; int
0x18002bc03  call    ?FillExtendedError@@YAXJKKKPEAUKERB_EXT_ERROR@@@Z; FillExtendedError(long,ulong,ulong,ulong,KERB_EXT_ERROR *)
0x18002bc08  jmp     loc_18002BDAF
0x18002bc0d  test    dword ptr [rdi+128h], 200000h
0x18002bc17  jz      loc_18002BCA6
0x18002bc1d  mov     rdx, [rbp+1E0h+var_258]
0x18002bc21  mov     rdx, [rdx+2E0h]; pSecurityDescriptor
0x18002bc28  mov     rcx, rsi; hAuthzClientContext
0x18002bc2b  call    ?KdcDmsaAuthzCheck@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAE@Z; KdcDmsaAuthzCheck(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,uchar *)
0x18002bc30  mov     ebx, eax
0x18002bc32  test    eax, eax
0x18002bc34  jz      loc_18002BCF1
0x18002bc3a  mov     r9, [rbp+1E0h+var_258]
0x18002bc3e  test    r9, r9
0x18002bc41  jnz     short loc_18002BC51
0x18002bc43  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bc48  mov     r9, [rbp+1E0h+var_258]
0x18002bc4c  test    r9, r9
0x18002bc4f  jz      short loc_18002BC68
0x18002bc51  lea     rdx, [r9+30h]
0x18002bc55  lea     rcx, [rdi+18h]
0x18002bc59  mov     r9d, [r9+2BCh]
0x18002bc60  mov     r8d, ebx
0x18002bc63  call    ?KdcLogDmsaAuthzFailure@@YAXAEBU_UNICODE_STRING@@0JW4_SERVICE_ACCOUNT_STATE@@@Z; KdcLogDmsaAuthzFailure(_UNICODE_STRING const &,_UNICODE_STRING const &,long,_SERVICE_ACCOUNT_STATE)
0x18002bc68  lea     rcx, WPP_GLOBAL_Control
0x18002bc6f  mov     rax, cs:WPP_GLOBAL_Control
0x18002bc76  cmp     rax, rcx
0x18002bc79  jz      loc_18002BDAF
0x18002bc7f  test    byte ptr [rax+1Ch], 1
0x18002bc83  jz      loc_18002BDAF
0x18002bc89  mov     edx, 11h
0x18002bc8e  mov     r9d, ebx
0x18002bc91  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002bc98  mov     rcx, [rax+10h]
0x18002bc9c  call    WPP_SF_d
0x18002bca1  jmp     loc_18002BDAF
0x18002bca6  mov     r8, [rbp+1E0h+var_258]; struct _USER_INTERNAL6_INFORMATION *
0x18002bcaa  mov     rdx, rsi; struct AUTHZ_CLIENT_CONTEXT_HANDLE__ *
0x18002bcad  mov     rcx, rdi; struct _KDC_S4U_TICKET_INFO *
0x18002bcb0  call    ?KdcCheckGroupExpansionAccess@@YAJPEAU_KDC_S4U_TICKET_INFO@@PEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAU_USER_INTERNAL6_INFORMATION@@@Z; KdcCheckGroupExpansionAccess(_KDC_S4U_TICKET_INFO *,AUTHZ_CLIENT_CONTEXT_HANDLE__ *,_USER_INTERNAL6_INFORMATION *)
0x18002bcb5  test    eax, eax
0x18002bcb7  jns     short loc_18002BCF1
0x18002bcb9  lea     rcx, WPP_GLOBAL_Control
0x18002bcc0  mov     rax, cs:WPP_GLOBAL_Control
0x18002bcc7  cmp     rax, rcx
0x18002bcca  jz      short loc_18002BCE7
0x18002bccc  test    byte ptr [rax+1Ch], 1
0x18002bcd0  jz      short loc_18002BCE7
0x18002bcd2  mov     edx, 12h
0x18002bcd7  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002bcde  mov     rcx, [rax+10h]
0x18002bce2  call    WPP_SF_
0x18002bce7  mov     ebx, 6
0x18002bcec  jmp     loc_18002BDAF
0x18002bcf1  test    [rbp+1E0h+var_198], 1
0x18002bcf5  jnz     short loc_18002BCFE
0x18002bcf7  or      dword ptr [rdi+128h], 8
0x18002bcfe  xor     edx, edx; Val
0x18002bd00  mov     r8d, 0BCh; Size
0x18002bd06  lea     rcx, [rbp+1E0h+var_10C]; void *
0x18002bd0d  call    memset_0
0x18002bd12  mov     [rbp+1E0h+var_110], 44400000h
0x18002bd1c  lea     rdx, [rbp+1E0h+var_110]
0x18002bd23  mov     rcx, [rbp+1E0h+var_248]
0x18002bd27  call    cs:__imp_SamIUpdateLogonStatistics
0x18002bd2d  mov     r9d, eax
0x18002bd30  test    eax, eax
0x18002bd32  jns     short loc_18002BD62
0x18002bd34  lea     rcx, WPP_GLOBAL_Control
0x18002bd3b  mov     rax, cs:WPP_GLOBAL_Control
0x18002bd42  cmp     rax, rcx
0x18002bd45  jz      short loc_18002BD62
0x18002bd47  test    byte ptr [rax+1Ch], 1
0x18002bd4b  jz      short loc_18002BD62
0x18002bd4d  mov     edx, 13h
0x18002bd52  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002bd59  mov     rcx, [rax+10h]
0x18002bd5d  call    WPP_SF_d
0x18002bd62  mov     rax, [rbp+1E0h+var_258]
0x18002bd66  mov     [r12], rax
0x18002bd6a  mov     [rbp+1E0h+var_258], 0
0x18002bd72  movaps  xmm0, [rbp+1E0h+var_140]
0x18002bd79  mov     rax, [rbp+1E0h+var_210]
0x18002bd7d  movdqu  xmmword ptr [rax], xmm0
0x18002bd81  xorps   xmm1, xmm1
0x18002bd84  movdqu  [rbp+1E0h+var_140], xmm1
0x18002bd8c  movaps  xmm0, [rbp+1E0h+var_230]
0x18002bd90  movdqu  xmmword ptr [r13+0], xmm0
0x18002bd96  movdqa  [rbp+1E0h+var_230], xmm1
0x18002bd9b  mov     rcx, [rbp+1E0h+var_240]
0x18002bd9f  test    rcx, rcx
0x18002bda2  jz      short loc_18002BDAD
0x18002bda4  lea     rdx, [rbp+1E0h+var_1C0]
0x18002bda8  call    ??4_KDC_TICKET_INFO@@QEAAAEAU0@AEBU0@@Z; _KDC_TICKET_INFO::operator=(_KDC_TICKET_INFO const &)
0x18002bdad  xor     ebx, ebx
0x18002bdaf  mov     [rbp+1E0h+var_1C8], 0
0x18002bdb3  lea     rcx, [rbp+1E0h+var_1F8]
0x18002bdb7  call    _lambda_d6f26e50ab51d66d8b486b6b791740ab___operator__
0x18002bdbc  nop
0x18002bdbd  lea     rcx, [rbp+1E0h+var_128]
0x18002bdc4  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18002bdc9  mov     eax, ebx
0x18002bdcb  mov     rcx, [rbp+1E0h+var_50]
0x18002bdd2  xor     rcx, rsp; StackCookie
0x18002bdd5  call    __security_check_cookie
0x18002bdda  add     rsp, 2A8h
0x18002bde1  pop     r15
0x18002bde3  pop     r14
0x18002bde5  pop     r13
0x18002bde7  pop     r12
0x18002bde9  pop     rdi
0x18002bdea  pop     rsi
0x18002bdeb  pop     rbx
0x18002bdec  pop     rbp
0x18002bded  retn
```

# KdcUpdateAndVerifyS4UPacVerifier(_KDC_S4U_TICKET_INFO *,uchar * *,ulong *,KERB_ENCRYPTED_TICKET *)

- ea: `0x18004a41c`
- end: `0x18004a948`
- name: `?KdcUpdateAndVerifyS4UPacVerifier@@YAJPEAU_KDC_S4U_TICKET_INFO@@PEAPEAEPEAKPEAUKERB_ENCRYPTED_TICKET@@@Z`
- size: `1324`
- prototype: `__int64 __fastcall(struct _KDC_S4U_TICKET_INFO *, unsigned __int8 **, unsigned int *, struct KERB_ENCRYPTED_TICKET *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004ab84`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x1800206c0`
- `0x1800206e8`
- `0x180045368`
- `0x180049b1c`
- `0x18004a41c`
- `0x18004bc2c`
- `0x18005a090`
- `0x18006fc78`
- `0x18006fcac`
- `0x180070984`
- `0x180070f30`
- `0x180071868`
- `0x18007be44`
- `0x18007bef4`
- `0x18007c274`
- `0x18007c4d4`
- `0x18007c5ec`
- `0x18007da34`
- `0x18007db8c`
- `0x18007dbe8`
- `0x18007dc20`
- `0x18007f1e4`
- `0x180099be0`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18004a75f`
- `ntdll!RtlEqualUnicodeString` at `0x18004a7d8`
- `ntdll!RtlEqualUnicodeString` at `0x18004a75f`
- `ntdll!RtlEqualUnicodeString` at `0x18004a7d8`
- `ntdll!RtlInitUnicodeString` at `0x18004a72a`
- `ntdll!RtlInitUnicodeString` at `0x18004a737`
- `ntdll!RtlInitUnicodeString` at `0x18004a72a`
- `ntdll!RtlInitUnicodeString` at `0x18004a737`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcUpdateAndVerifyS4UPacVerifier(
        struct _KDC_S4U_TICKET_INFO *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        struct KERB_ENCRYPTED_TICKET *a4)
{
  __int64 v7; // rax
  struct _PACTYPE **v8; // r10
  struct _PACTYPE *v9; // r14
  unsigned int v10; // ebx
  struct _PAC_INFO_BUFFER *v11; // r8
  CSecurityData *v12; // rcx
  __int64 v13; // rdx
  struct _PAC_INFO_BUFFER *v14; // rax
  __int64 v16; // rsi
  unsigned __int64 v17; // rdi
  WCHAR *v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  WCHAR *v23; // rax
  int i; // ecx
  const WCHAR *v25; // rbx
  const WCHAR *v26; // rdx
  unsigned int v27; // ebx
  unsigned __int8 v28; // r8
  unsigned int Size; // eax
  unsigned int v30; // r11d
  __int64 v31; // [rsp+0h] [rbp-30h] BYREF
  struct _PACTYPE *v32; // [rsp+30h] [rbp+0h] BYREF
  PCWSTR SourceString[2]; // [rsp+38h] [rbp+8h] BYREF
  unsigned int v34; // [rsp+48h] [rbp+18h] BYREF
  union _LARGE_INTEGER Time; // [rsp+50h] [rbp+20h] BYREF
  struct _PACTYPE *v36; // [rsp+58h] [rbp+28h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int8 **v38; // [rsp+70h] [rbp+40h]
  UNICODE_STRING String1; // [rsp+78h] [rbp+48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp+58h] BYREF
  _BYTE v41[48]; // [rsp+A0h] [rbp+70h] BYREF
  char v42; // [rsp+D0h] [rbp+A0h] BYREF

  v38 = a2;
  v32 = 0;
  Time.QuadPart = 0;
  *(_OWORD *)SourceString = 0;
  String2 = 0;
  String1 = 0;
  DestinationString = 0;
  v36 = 0;
  v34 = 0;
  v7 = lambda_bde1109c27f1d473909aeaf58a3f4245_::_lambda_bde1109c27f1d473909aeaf58a3f4245_(
         (unsigned int)&v42,
         (unsigned int)&v36,
         (unsigned int)&v34,
         (unsigned int)SourceString,
         (__int64)&v32,
         (__int64)&String1);
  wil::scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___(v41, v7);
  v9 = *v8;
  v10 = *a3;
  if ( !PAC_UnMarshal(*v8, *a3) )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v13 = 35;
    goto LABEL_43;
  }
  v36 = v9;
  v34 = v10;
  v14 = PAC_Find(v9, 0xAu, v11);
  if ( !v14 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v13 = 36;
    goto LABEL_43;
  }
  if ( *((_DWORD *)v14 + 1) < 0xCu )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_3875113a630833a3e73becf979560e87_Traceguids,
        *((unsigned int *)v14 + 1),
        12);
    goto LABEL_13;
  }
  v16 = *((_QWORD *)v14 + 1);
  if ( (unsigned __int64)*(unsigned __int16 *)(v16 + 8) + 6 > *((unsigned int *)v14 + 1) )
  {
LABEL_13:
    wil::details::lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___::_lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___(v41);
    return 12;
  }
  KerbConvertGeneralizedTimeToLargeInt(&Time);
  if ( Time.QuadPart != *(_QWORD *)v16 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v13 = 38;
LABEL_43:
    WPP_SF_(*((_QWORD *)v12 + 2), v13, WPP_3875113a630833a3e73becf979560e87_Traceguids);
    goto LABEL_13;
  }
  LOWORD(SourceString[0]) = *(_WORD *)(v16 + 8);
  if ( (int)RtlUShortAdd(*(unsigned __int16 *)(v16 + 8), 2, (char *)SourceString + 2) < 0 )
    goto LABEL_60;
  v17 = WORD1(SourceString[0]);
  v18 = 0;
  if ( !WORD1(SourceString[0]) )
    goto LABEL_63;
  if ( WORD1(SourceString[0]) > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_63;
  v19 = WORD1(SourceString[0]) + g_ulAdditionalProbeSize + 8;
  if ( v19 < WORD1(SourceString[0]) || !(unsigned int)VerifyStackAvailable(v19) )
    goto LABEL_63;
  v20 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
  v22 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
  v18 = (WCHAR *)&v32;
  if ( &v31 == (__int64 *)-48LL || (LODWORD(v32) = 1801679955, (v18 = (WCHAR *)SourceString) == 0) )
  {
LABEL_63:
    if ( v17 + 8 >= v17 )
    {
      v23 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      v18 = v23;
      if ( v23 )
      {
        *(_DWORD *)v23 = 1885431112;
        v18 = v23 + 4;
      }
    }
  }
  SourceString[1] = v18;
  if ( v18 )
  {
    memcpy_0(v18, (const void *)(v16 + 10), LOWORD(SourceString[0]));
    SourceString[1][(unsigned __int64)LOWORD(SourceString[0]) >> 1] = 0;
    for ( i = LOWORD(SourceString[0]) >> 1; ; --i )
    {
      if ( i <= 0 )
        goto LABEL_57;
      if ( SourceString[1][i] == 64 )
      {
        SourceString[1][i] = 0;
        if ( i < LOWORD(SourceString[0]) >> 1 )
          break;
      }
    }
    v25 = SourceString[1];
    v26 = &SourceString[1][i + 1];
    if ( !v26 )
    {
LABEL_57:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 39;
        goto LABEL_43;
      }
      goto LABEL_13;
    }
    RtlInitUnicodeString(&DestinationString, v26);
    RtlInitUnicodeString(&String2, v25);
    if ( (*((_DWORD *)a1 + 74) & 0x1000) != 0 )
    {
      if ( !RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)((char *)a1 + 232), 1u) )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 40;
          goto LABEL_43;
        }
        goto LABEL_13;
      }
      v27 = KerbConvertKdcNameToString(&String1, *((struct _KERB_INTERNAL_NAME **)a1 + 28), 0);
      if ( v27 )
        goto LABEL_45;
      if ( !RtlEqualUnicodeString(&String1, &String2, 1u) )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 41;
          goto LABEL_43;
        }
        goto LABEL_13;
      }
    }
    else
    {
      KerbFreeString((char *)a1 + 232);
      KerbDuplicateStringEx((struct _UNICODE_STRING *)((char *)a1 + 232), &DestinationString, v28);
      KerbFreeSid((char *)a1 + 224);
      KerbConvertStringToKdcName((struct _KERB_INTERNAL_NAME **)a1 + 28, &String2);
      KerbFreePrincipalName((char *)a4 + 56);
      KerbConvertKdcNameToPrincipalName(
        (struct KERB_ENCRYPTED_TICKET *)((char *)a4 + 56),
        *((struct _KERB_INTERNAL_NAME **)a1 + 28));
      KerbFreeRealm((char *)a4 + 48);
      KerbConvertUnicodeStringToRealm((char *)a4 + 48, (char *)a1 + 232);
    }
    v27 = KdcReplacePacVerifier(&Time, &String2, v9, &v32);
    if ( v27 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_3875113a630833a3e73becf979560e87_Traceguids, v27);
      goto LABEL_45;
    }
    Size = PAC_GetSize(v32);
    if ( !PAC_ReMarshal(v32, Size) )
      goto LABEL_60;
    *v38 = (unsigned __int8 *)v32;
    v32 = 0;
    v36 = 0;
    *a3 = v30;
    MIDL_user_free(v9);
    wil::details::lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___::_lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___(v41);
    return 0;
  }
  else
  {
LABEL_60:
    v27 = 60;
LABEL_45:
    wil::details::lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___::_lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___(v41);
    return v27;
  }
}

```

## disassembly

```asm
0x18004a41c  push    rbp
0x18004a41e  push    rbx
0x18004a41f  push    rsi
0x18004a420  push    rdi
0x18004a421  push    r12
0x18004a423  push    r13
0x18004a425  push    r14
0x18004a427  push    r15
0x18004a429  sub     rsp, 108h
0x18004a430  lea     rbp, [rsp+30h]
0x18004a435  mov     rax, cs:__security_cookie
0x18004a43c  xor     rax, rbp
0x18004a43f  mov     [rbp+110h+var_48], rax
0x18004a446  mov     r13, r9
0x18004a449  mov     r12, r8
0x18004a44c  mov     r10, rdx
0x18004a44f  mov     [rbp+110h+var_D0], rdx
0x18004a453  mov     r15, rcx
0x18004a456  xor     edi, edi
0x18004a458  mov     [rbp+110h+var_110], rdi
0x18004a45c  mov     qword ptr [rbp+110h+Time], rdi
0x18004a460  xorps   xmm0, xmm0
0x18004a463  movups  xmmword ptr [rbp+110h+SourceString], xmm0
0x18004a467  xorps   xmm1, xmm1
0x18004a46a  movups  xmmword ptr [rbp+110h+String2.Length], xmm1
0x18004a46e  movups  xmmword ptr [rbp+110h+String1.Length], xmm0
0x18004a472  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm1
0x18004a476  mov     [rbp+110h+var_E8], rdi
0x18004a47a  mov     [rbp+110h+var_F8], edi
0x18004a47d  lea     rax, [rbp+110h+String1]
0x18004a481  mov     [rsp+140h+var_118], rax
0x18004a486  lea     rax, [rbp+110h+var_110]
0x18004a48a  mov     [rsp+140h+var_120], rax
0x18004a48f  lea     r9, [rbp+110h+SourceString]
0x18004a493  lea     r8, [rbp+110h+var_F8]
0x18004a497  lea     rdx, [rbp+110h+var_E8]
0x18004a49b  lea     rcx, [rbp+110h+var_70]
0x18004a4a2  call    _lambda_bde1109c27f1d473909aeaf58a3f4245____lambda_bde1109c27f1d473909aeaf58a3f4245_
0x18004a4a7  mov     rdx, rax
0x18004a4aa  lea     rcx, [rbp+110h+var_A0]
0x18004a4ae  call    wil__scope_exit__lambda_bde1109c27f1d473909aeaf58a3f4245___
0x18004a4b3  nop
0x18004a4b4  mov     r14, [r10]
0x18004a4b7  mov     ebx, [r12]
0x18004a4bb  mov     edx, ebx; unsigned int
0x18004a4bd  mov     rcx, r14; struct _PACTYPE *
0x18004a4c0  call    ?PAC_UnMarshal@@YAKPEAU_PACTYPE@@K@Z; PAC_UnMarshal(_PACTYPE *,ulong)
0x18004a4c5  test    eax, eax
0x18004a4c7  jnz     short loc_18004A4F2
0x18004a4c9  lea     rax, WPP_GLOBAL_Control
0x18004a4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4d7  cmp     rcx, rax
0x18004a4da  jz      loc_18004A571
0x18004a4e0  test    byte ptr [rcx+1Ch], 1
0x18004a4e4  jz      loc_18004A571
0x18004a4ea  lea     edx, [rdi+23h]
0x18004a4ed  jmp     loc_18004A78F
0x18004a4f2  mov     [rbp+110h+var_E8], r14
0x18004a4f6  mov     [rbp+110h+var_F8], ebx
0x18004a4f9  mov     edx, 0Ah; unsigned int
0x18004a4fe  mov     rcx, r14; struct _PACTYPE *
0x18004a501  call    ?PAC_Find@@YAPEAU_PAC_INFO_BUFFER@@PEAU_PACTYPE@@KPEAU1@@Z; PAC_Find(_PACTYPE *,ulong,_PAC_INFO_BUFFER *)
0x18004a506  mov     r9, rax
0x18004a509  test    rax, rax
0x18004a50c  jnz     short loc_18004A530
0x18004a50e  lea     rax, WPP_GLOBAL_Control
0x18004a515  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a51c  cmp     rcx, rax
0x18004a51f  jz      short loc_18004A571
0x18004a521  test    byte ptr [rcx+1Ch], 1
0x18004a525  jz      short loc_18004A571
0x18004a527  lea     edx, [r9+24h]
0x18004a52b  jmp     loc_18004A78F
0x18004a530  cmp     dword ptr [rax+4], 0Ch
0x18004a534  jnb     short loc_18004A5A2
0x18004a536  lea     rax, WPP_GLOBAL_Control
0x18004a53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a544  cmp     rcx, rax
0x18004a547  jz      short loc_18004A571
0x18004a549  test    byte ptr [rcx+1Ch], 1
0x18004a54d  jz      short loc_18004A571
0x18004a54f  mov     edx, 25h ; '%'
0x18004a554  mov     dword ptr [rsp+140h+var_120], 0Ch
0x18004a55c  mov     r9d, [r9+4]
0x18004a560  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004a567  mov     rcx, [rcx+10h]
0x18004a56b  call    WPP_SF_Dd
0x18004a570  nop
0x18004a571  lea     rcx, [rbp+110h+var_A0]
0x18004a575  call    wil__details__lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6______lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___
0x18004a57a  mov     eax, 0Ch
0x18004a57f  mov     rcx, [rbp+110h+var_48]
0x18004a586  xor     rcx, rbp; StackCookie
0x18004a589  call    __security_check_cookie
0x18004a58e  lea     rsp, [rbp+0D8h]
0x18004a595  pop     r15
0x18004a597  pop     r14
0x18004a599  pop     r13
0x18004a59b  pop     r12
0x18004a59d  pop     rdi
0x18004a59e  pop     rsi
0x18004a59f  pop     rbx
0x18004a5a0  pop     rbp
0x18004a5a1  retn
0x18004a5a2  mov     rsi, [rax+8]
0x18004a5a6  movzx   ecx, word ptr [rsi+8]
0x18004a5aa  add     rcx, 6
0x18004a5ae  mov     eax, [rax+4]
0x18004a5b1  cmp     rcx, rax
0x18004a5b4  ja      short loc_18004A571
0x18004a5b6  mov     rdx, [r15+0F8h]
0x18004a5bd  add     rdx, 60h ; '`'
0x18004a5c1  xor     r8d, r8d
0x18004a5c4  lea     rcx, [rbp+110h+Time]; Time
0x18004a5c8  call    KerbConvertGeneralizedTimeToLargeInt
0x18004a5cd  mov     rax, qword ptr [rbp+110h+Time]
0x18004a5d1  cmp     rax, [rsi]
0x18004a5d4  jz      short loc_18004A5F9
0x18004a5d6  lea     rax, WPP_GLOBAL_Control
0x18004a5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5e4  cmp     rcx, rax
0x18004a5e7  jz      short loc_18004A571
0x18004a5e9  test    byte ptr [rcx+1Ch], 1
0x18004a5ed  jz      short loc_18004A571
0x18004a5ef  mov     edx, 26h ; '&'
0x18004a5f4  jmp     loc_18004A78F
0x18004a5f9  movzx   eax, word ptr [rsi+8]
0x18004a5fd  mov     word ptr [rbp+110h+SourceString], ax
0x18004a601  mov     edx, 2
0x18004a606  lea     r8, [rbp+110h+SourceString+2]
0x18004a60a  movzx   ecx, word ptr [rsi+8]
0x18004a60e  call    RtlUShortAdd
0x18004a613  test    eax, eax
0x18004a615  js      loc_18004A93D
0x18004a61b  movzx   edi, word ptr [rbp+110h+SourceString+2]
0x18004a61f  xor     ebx, ebx
0x18004a621  test    rdi, rdi
0x18004a624  jz      short loc_18004A687
0x18004a626  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18004a62d  ja      short loc_18004A687
0x18004a62f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18004a636  add     rcx, 8
0x18004a63a  add     rcx, rdi
0x18004a63d  cmp     rcx, rdi
0x18004a640  jb      short loc_18004A687
0x18004a642  call    VerifyStackAvailable
0x18004a647  test    eax, eax
0x18004a649  jz      short loc_18004A687
0x18004a64b  lea     rax, [rdi+8]
0x18004a64f  lea     rcx, [rax+0Fh]
0x18004a653  cmp     rcx, rax
0x18004a656  ja      short loc_18004A662
0x18004a658  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18004a662  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004a666  mov     rax, rcx
0x18004a669  call    _alloca_probe
0x18004a66e  sub     rsp, rcx
0x18004a671  lea     rbx, [rsp+140h+var_110]
0x18004a676  test    rbx, rbx
0x18004a679  jz      short loc_18004A687
0x18004a67b  mov     dword ptr [rbx], 6B637453h
0x18004a681  add     rbx, 8
0x18004a685  jnz     short loc_18004A6AE
0x18004a687  lea     rcx, [rdi+8]
0x18004a68b  cmp     rcx, rdi
0x18004a68e  jb      short loc_18004A6AE
0x18004a690  mov     rax, cs:g_pfnAllocate
0x18004a697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a69c  mov     rbx, rax
0x18004a69f  test    rax, rax
0x18004a6a2  jz      short loc_18004A6AE
0x18004a6a4  mov     dword ptr [rax], 70616548h
0x18004a6aa  add     rbx, 8
0x18004a6ae  mov     [rbp+110h+SourceString+8], rbx
0x18004a6b2  test    rbx, rbx
0x18004a6b5  jz      loc_18004A93D
0x18004a6bb  movzx   r8d, word ptr [rbp+110h+SourceString]; Size
0x18004a6c0  lea     rdx, [rsi+0Ah]; Src
0x18004a6c4  mov     rcx, rbx; void *
0x18004a6c7  call    memcpy_0
0x18004a6cc  movzx   edx, word ptr [rbp+110h+SourceString]
0x18004a6d0  shr     rdx, 1
0x18004a6d3  xor     ecx, ecx
0x18004a6d5  mov     rax, [rbp+110h+SourceString+8]
0x18004a6d9  mov     [rax+rdx*2], cx
0x18004a6dd  movzx   ecx, word ptr [rbp+110h+SourceString]
0x18004a6e1  shr     ecx, 1
0x18004a6e3  test    ecx, ecx
0x18004a6e5  jle     loc_18004A912
0x18004a6eb  movsxd  rdx, ecx
0x18004a6ee  mov     r8, [rbp+110h+SourceString+8]
0x18004a6f2  cmp     word ptr [r8+rdx*2], 40h ; '@'
0x18004a6f8  jnz     short loc_18004A70B
0x18004a6fa  xor     eax, eax
0x18004a6fc  mov     [r8+rdx*2], ax
0x18004a701  movzx   eax, word ptr [rbp+110h+SourceString]
0x18004a705  shr     eax, 1
0x18004a707  cmp     ecx, eax
0x18004a709  jl      short loc_18004A70F
0x18004a70b  dec     ecx
0x18004a70d  jmp     short loc_18004A6E3
0x18004a70f  lea     eax, [rcx+1]
0x18004a712  movsxd  rcx, eax
0x18004a715  mov     rbx, [rbp+110h+SourceString+8]
0x18004a719  lea     rdx, [rbx+rcx*2]; SourceString
0x18004a71d  test    rdx, rdx
0x18004a720  jz      loc_18004A912
0x18004a726  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x18004a72a  call    cs:__imp_RtlInitUnicodeString
0x18004a730  mov     rdx, rbx; SourceString
0x18004a733  lea     rcx, [rbp+110h+String2]; DestinationString
0x18004a737  call    cs:__imp_RtlInitUnicodeString
0x18004a73d  lea     rsi, [r15+0E8h]
0x18004a744  test    dword ptr [r15+128h], 1000h
0x18004a74f  jz      loc_18004A80E
0x18004a755  mov     r8b, 1; CaseInsensitive
0x18004a758  mov     rdx, rsi; String2
0x18004a75b  lea     rcx, [rbp+110h+DestinationString]; String1
0x18004a75f  call    cs:__imp_RtlEqualUnicodeString
0x18004a765  test    al, al
0x18004a767  jnz     short loc_18004A7A4
0x18004a769  lea     rax, WPP_GLOBAL_Control
0x18004a770  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a777  cmp     rcx, rax
0x18004a77a  jz      loc_18004A571
0x18004a780  test    byte ptr [rcx+1Ch], 1
0x18004a784  jz      loc_18004A571
0x18004a78a  mov     edx, 28h ; '('
0x18004a78f  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004a796  mov     rcx, [rcx+10h]
0x18004a79a  call    WPP_SF_
0x18004a79f  jmp     loc_18004A571
0x18004a7a4  xor     r8d, r8d; struct _UNICODE_STRING *
0x18004a7a7  mov     rdx, [r15+0E0h]; struct _KERB_INTERNAL_NAME *
0x18004a7ae  lea     rcx, [rbp+110h+String1]; struct _UNICODE_STRING *
0x18004a7b2  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x18004a7b7  mov     ebx, eax
0x18004a7b9  test    eax, eax
0x18004a7bb  jz      short loc_18004A7CD
0x18004a7bd  lea     rcx, [rbp+110h+var_A0]
0x18004a7c1  call    wil__details__lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6______lambda_call__lambda_2e5dc414bd1f674388d7941268a259a6___
0x18004a7c6  mov     eax, ebx
0x18004a7c8  jmp     loc_18004A57F
0x18004a7cd  mov     r8b, 1; CaseInsensitive
0x18004a7d0  lea     rdx, [rbp+110h+String2]; String2
0x18004a7d4  lea     rcx, [rbp+110h+String1]; String1
0x18004a7d8  call    cs:__imp_RtlEqualUnicodeString
0x18004a7de  test    al, al
0x18004a7e0  jnz     loc_18004A867
0x18004a7e6  lea     rax, WPP_GLOBAL_Control
0x18004a7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a7f4  cmp     rcx, rax
0x18004a7f7  jz      loc_18004A571
0x18004a7fd  test    byte ptr [rcx+1Ch], 1
0x18004a801  jz      loc_18004A571
0x18004a807  mov     edx, 29h ; ')'
0x18004a80c  jmp     short loc_18004A78F
0x18004a80e  mov     rcx, rsi
0x18004a811  call    KerbFreeString
0x18004a816  lea     rdx, [rbp+110h+DestinationString]; struct _UNICODE_STRING *
0x18004a81a  mov     rcx, rsi; struct _UNICODE_STRING *
0x18004a81d  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18004a822  lea     rdi, [r15+0E0h]
0x18004a829  mov     rcx, rdi
0x18004a82c  call    KerbFreeSid
0x18004a831  lea     rdx, [rbp+110h+String2]; struct _UNICODE_STRING *
0x18004a835  mov     rcx, rdi; struct _KERB_INTERNAL_NAME **
0x18004a838  call    ?KerbConvertStringToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@@Z; KerbConvertStringToKdcName(_KERB_INTERNAL_NAME * *,_UNICODE_STRING *)
0x18004a83d  lea     rcx, [r13+38h]
0x18004a841  call    KerbFreePrincipalName
0x18004a846  mov     rdx, [rdi]; struct _KERB_INTERNAL_NAME *
0x18004a849  lea     rcx, [r13+38h]; struct KERB_PRINCIPAL_NAME *
0x18004a84d  call    ?KerbConvertKdcNameToPrincipalName@@YAJPEAUKERB_PRINCIPAL_NAME@@PEAU_KERB_INTERNAL_NAME@@@Z; KerbConvertKdcNameToPrincipalName(KERB_PRINCIPAL_NAME *,_KERB_INTERNAL_NAME *)
0x18004a852  lea     rcx, [r13+30h]
0x18004a856  call    KerbFreeRealm
0x18004a85b  mov     rdx, rsi
0x18004a85e  lea     rcx, [r13+30h]
0x18004a862  call    KerbConvertUnicodeStringToRealm
0x18004a867  lea     r9, [rbp+110h+var_110]; struct _PACTYPE **
0x18004a86b  mov     r8, r14; struct _PACTYPE *
0x18004a86e  lea     rdx, [rbp+110h+String2]; struct _UNICODE_STRING *
0x18004a872  lea     rcx, [rbp+110h+Time]; union _LARGE_INTEGER *
0x18004a876  call    ?KdcReplacePacVerifier@@YAJPEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@PEAU_PACTYPE@@PEAPEAU3@@Z; KdcReplacePacVerifier(_LARGE_INTEGER *,_UNICODE_STRING *,_PACTYPE *,_PACTYPE * *)
0x18004a87b  mov     ebx, eax
0x18004a87d  test    eax, eax
0x18004a87f  jz      short loc_18004A8BF
0x18004a881  lea     rax, WPP_GLOBAL_Control
0x18004a888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a88f  cmp     rcx, rax
0x18004a892  jz      loc_18004A7BD
0x18004a898  test    byte ptr [rcx+1Ch], 1
0x18004a89c  jz      loc_18004A7BD
0x18004a8a2  mov     edx, 2Bh ; '+'
0x18004a8a7  mov     r9d, ebx
0x18004a8aa  lea     r8, WPP_3875113a630833a3e73becf979560e87_Traceguids
0x18004a8b1  mov     rcx, [rcx+10h]
0x18004a8b5  call    WPP_SF_d
0x18004a8ba  jmp     loc_18004A7BD
0x18004a8bf  mov     rcx, [rbp+110h+var_110]; struct _PACTYPE *
0x18004a8c3  call    ?PAC_GetSize@@YAKPEAU_PACTYPE@@@Z; PAC_GetSize(_PACTYPE *)
  ... truncated ...
```

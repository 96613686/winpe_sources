# KdcCheckTicket(_KDC_TICKET_INFO *,KERB_ENCRYPTED_TICKET *)

- ea: `0x18005e9ac`
- end: `0x18005f02d`
- name: `?KdcCheckTicket@@YAJPEAU_KDC_TICKET_INFO@@PEAUKERB_ENCRYPTED_TICKET@@@Z`
- size: `1665`
- prototype: `__int64 __fastcall(struct _KDC_TICKET_INFO *, struct KERB_ENCRYPTED_TICKET *)`
- caller_count: `4`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002dd48`
- `0x18002e6c4`
- `0x180064ca0`
- `0x1800684f4`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18000b6ac`
- `0x18000e9a4`
- `0x18001cdc4`
- `0x18002005c`
- `0x180020380`
- `0x18004843c`
- `0x18005a090`
- `0x18005ad20`
- `0x18005c2a4`
- `0x18005cdac`
- `0x18005cf38`
- `0x18005d038`
- `0x18005e9ac`
- `0x18006349c`
- `0x180066464`
- `0x180066d10`
- `0x180066e74`
- `0x180067250`
- `0x180072338`
- `0x18007c054`
- `0x18007c5ec`
- `0x18007d714`
- `0x18007dc20`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18005ef99`
- `ntdll!RtlEqualSid` at `0x18005ef99`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x18005ec32`
- `SAMSRV!SamIQueryAccountSecretsCachability` at `0x18005ec32`

## pseudocode

```c
__int64 __fastcall KdcCheckTicket(struct _KDC_TICKET_INFO *a1, struct KERB_ENCRYPTED_TICKET *a2)
{
  CSecurityData *v4; // rcx
  unsigned int v5; // edi
  int v7; // r8d
  CSecurityData *v8; // rcx
  int v9; // r8d
  CSecurityData *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int RequestorIdFromTgtPac; // eax
  __int64 v15; // rcx
  int v16; // r14d
  char v17; // di
  int v18; // edx
  int v19; // r8d
  unsigned __int8 v20[8]; // [rsp+80h] [rbp-80h] BYREF
  struct _KERB_INTERNAL_NAME *v21; // [rsp+88h] [rbp-78h] BYREF
  char v22[4]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v23; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v24; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v25[48]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+FCh] [rbp-4h]
  int v28; // [rsp+111h] [rbp+11h]
  __int16 v29; // [rsp+115h] [rbp+15h]
  char v30; // [rsp+117h] [rbp+17h]
  __int16 v31; // [rsp+129h] [rbp+29h]
  char v32; // [rsp+12Bh] [rbp+2Bh]
  int v33; // [rsp+134h] [rbp+34h]
  __int64 v34; // [rsp+158h] [rbp+58h] BYREF
  __int128 v35; // [rsp+160h] [rbp+60h]
  struct _UNICODE_STRING *v36; // [rsp+170h] [rbp+70h]
  struct _UNICODE_STRING *v37; // [rsp+178h] [rbp+78h]
  struct _KERB_INTERNAL_NAME **v38; // [rsp+180h] [rbp+80h]
  _BYTE *v39; // [rsp+188h] [rbp+88h]
  PSID *p_Sid2; // [rsp+190h] [rbp+90h]
  char v41; // [rsp+198h] [rbp+98h]
  PSID Sid2; // [rsp+1A0h] [rbp+A0h] BYREF
  int v43; // [rsp+1A8h] [rbp+A8h]
  struct _UNICODE_STRING v44; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE Sid1[80]; // [rsp+1C0h] [rbp+C0h] BYREF

  if ( !KdcGlobalCDC && *((_BYTE *)a1 + 104) )
  {
    v44 = 0;
    v23 = 0;
    v21 = 0;
    Sid2 = 0;
    v43 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    memset_0(v25, 0, 0x98u);
    v34 = 0;
    v35 = 0;
    v36 = &v44;
    v37 = &v23;
    v38 = &v21;
    v39 = v25;
    LOBYTE(p_Sid2) = 1;
    v5 = KerbConvertRealmToUnicodeString(&v44, (char *)a2 + 48);
    if ( v5 )
    {
LABEL_4:
      KerbFreeString(&v44);
      KerbFreeString(&v23);
      KerbFreeSid(&v21);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v25);
LABEL_5:
      std::vector<unsigned int>::_Tidy((__int64)&v34);
      return v5;
    }
    if ( !CSecurityData::IsOurRealm(v4, &v44) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&v44,
          v7,
          (_DWORD)a1,
          *((_WORD *)a1 + 49),
          (__int64)&v44);
LABEL_29:
      v5 = 20;
      goto LABEL_4;
    }
    v5 = KerbConvertPrincipalNameToKdcName(&v21, (struct KERB_ENCRYPTED_TICKET *)((char *)a2 + 56));
    if ( v5 )
      goto LABEL_4;
    v20[0] = 0;
    v5 = KdcNormalize(
           v21,
           0,
           &v44,
           0,
           1u,
           6u,
           0,
           v20,
           &v23,
           (struct _KDC_TICKET_INFO *)v25,
           (struct KERB_EXT_ERROR *)&Sid2,
           0,
           0,
           0,
           0,
           0);
    if ( v5 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            176,
            (unsigned int)WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
            (_DWORD)a1,
            *((_WORD *)a1 + 49));
          v8 = WPP_GLOBAL_Control;
        }
        if ( v8 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
          WPP_SF__KERB_NAME_(*((_QWORD *)v8 + 2), 177, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v21);
      }
      if ( v5 != 6 )
        goto LABEL_4;
      goto LABEL_29;
    }
    *(_DWORD *)v22 = 0;
    if ( (int)SamIQueryAccountSecretsCachability(v26, *((unsigned __int16 *)a1 + 49), v22) < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZDZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          178,
          v9,
          (unsigned int)v25,
          v26,
          (__int64)a1,
          *((_WORD *)a1 + 49));
      v5 = 12;
      goto LABEL_4;
    }
    if ( !*(_DWORD *)v22 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ZDZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          179,
          v9,
          (unsigned int)v25,
          v26,
          (__int64)a1,
          *((_WORD *)a1 + 49));
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_ZDZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        v9,
        (unsigned int)v25,
        v26,
        (__int64)a1,
        *((_WORD *)a1 + 49));
    KerbFreeString(&v44);
    KerbFreeString(&v23);
    KerbFreeSid(&v21);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v25);
    std::vector<unsigned int>::_Tidy((__int64)&v34);
  }
  if ( _KDC_TICKET_INFO::IsAnyKrbtgt(a1) )
  {
    v23 = 0;
    v24 = 0;
    v21 = 0;
    *(_QWORD *)&v44.Length = 0;
    LODWORD(v44.Buffer) = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    memset_0(v25, 0, 0x98u);
    v34 = 0;
    v35 = 0;
    *(_DWORD *)v22 = 0;
    Sid2 = 0;
    v36 = &v23;
    v37 = &v24;
    v38 = &v21;
    v39 = v25;
    p_Sid2 = &Sid2;
    v41 = 1;
    v5 = KerbConvertRealmToUnicodeString(&v23, (char *)a2 + 48);
    if ( v5 )
    {
LABEL_36:
      KerbFreeString(&v23);
      KerbFreeString(&v24);
      KerbFreeSid(&v21);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v25);
      MIDL_user_free(Sid2);
      goto LABEL_5;
    }
    if ( CSecurityData::IsOurRealm(v10, &v23) )
    {
      v5 = KerbConvertPrincipalNameToKdcName(&v21, (struct KERB_ENCRYPTED_TICKET *)((char *)a2 + 56));
      if ( v5 )
        goto LABEL_36;
      v20[0] = 0;
      v11 = KdcNormalize(
              v21,
              0,
              &v23,
              0,
              1u,
              6u,
              0,
              v20,
              &v24,
              (struct _KDC_TICKET_INFO *)v25,
              (struct KERB_EXT_ERROR *)&v44,
              0,
              0,
              0,
              0,
              0);
      v5 = v11;
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF__KERB_NAME_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, v21, v11);
        }
        if ( v5 != 6 )
          goto LABEL_36;
        goto LABEL_57;
      }
      RequestorIdFromTgtPac = KdcGetRequestorIdFromTgtPac(a2, &Sid2, (int *)v22);
      v16 = RequestorIdFromTgtPac;
      if ( RequestorIdFromTgtPac )
      {
        v17 = v22[0];
        if ( RequestorIdFromTgtPac == 60 )
        {
          if ( !*(_DWORD *)v22 || *(_DWORD *)v22 == -1073741811 )
          {
LABEL_54:
            KdcAuditTicketWithoutPac(a2, a1);
            goto LABEL_57;
          }
          if ( *(_DWORD *)v22 == -1073741275 )
          {
            KdcAuditTicketWithoutRequestor(a2, a1);
LABEL_57:
            v5 = 20;
            goto LABEL_36;
          }
        }
        MicrosoftTelemetryAssertTriggeredNoArgs(v15);
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Dd_KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v16, v17, v21);
        }
        goto LABEL_54;
      }
      memset_0(Sid1, 0, 0x48u);
      KdcMakeAccountSid(Sid1, v26);
      if ( !RtlEqualSid(Sid1, Sid2) )
      {
        KdcAuditTicketRequestorMismatch(a2, a1, Sid1, Sid2);
        goto LABEL_57;
      }
    }
    KerbFreeString(&v23);
    KerbFreeString(&v24);
    KerbFreeSid(&v21);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v25);
    MIDL_user_free(Sid2);
    std::vector<unsigned int>::_Tidy((__int64)&v34);
  }
  return 0;
}

```

## disassembly

```asm
0x18005e9ac  mov     [rsp-8+arg_10], rbx
0x18005e9b1  mov     [rsp-8+arg_18], rsi
0x18005e9b6  push    rbp
0x18005e9b7  push    rdi
0x18005e9b8  push    r13
0x18005e9ba  push    r14
0x18005e9bc  push    r15
0x18005e9be  lea     rbp, [rsp-120h]
0x18005e9c6  sub     rsp, 220h
0x18005e9cd  mov     rax, cs:__security_cookie
0x18005e9d4  xor     rax, rsp
0x18005e9d7  mov     [rbp+140h+var_30], rax
0x18005e9de  mov     rsi, rdx
0x18005e9e1  mov     rbx, rcx
0x18005e9e4  lea     r13, WPP_GLOBAL_Control
0x18005e9eb  mov     r14d, 6
0x18005e9f1  xor     r15d, r15d
0x18005e9f4  cmp     cs:?KdcGlobalCDC@@3HA, r15d; int KdcGlobalCDC
0x18005e9fb  jnz     loc_18005ED30
0x18005ea01  cmp     [rcx+68h], r15b
0x18005ea05  jz      loc_18005ED30
0x18005ea0b  xorps   xmm0, xmm0
0x18005ea0e  movups  xmmword ptr [rbp+140h+var_90.Length], xmm0
0x18005ea15  xorps   xmm1, xmm1
0x18005ea18  movups  xmmword ptr [rbp+140h+var_1A8.Length], xmm1
0x18005ea1c  mov     [rbp+140h+var_1B8], r15
0x18005ea20  xor     eax, eax
0x18005ea22  mov     [rbp+140h+Sid2], rax
0x18005ea29  mov     [rbp+140h+var_98], eax
0x18005ea2f  mov     [rbp+140h+var_144], eax
0x18005ea32  mov     [rbp+140h+var_12F], eax
0x18005ea35  mov     [rbp+140h+var_12B], ax
0x18005ea39  mov     [rbp+140h+var_129], al
0x18005ea3c  mov     [rbp+140h+var_117], ax
0x18005ea40  mov     [rbp+140h+var_115], al
0x18005ea43  mov     [rbp+140h+var_10C], eax
0x18005ea46  xor     edx, edx; Val
0x18005ea48  mov     r8d, 98h; Size
0x18005ea4e  lea     rcx, [rbp+140h+var_180]; void *
0x18005ea52  call    memset_0
0x18005ea57  mov     [rbp+140h+var_E8], r15
0x18005ea5b  xorps   xmm0, xmm0
0x18005ea5e  movdqa  [rbp+140h+var_E0], xmm0
0x18005ea63  lea     rax, [rbp+140h+var_90]
0x18005ea6a  mov     [rbp+140h+var_D0], rax
0x18005ea6e  lea     rax, [rbp+140h+var_1A8]
0x18005ea72  mov     [rbp+140h+var_C8], rax
0x18005ea76  lea     rax, [rbp+140h+var_1B8]
0x18005ea7a  mov     [rbp+140h+var_C0], rax
0x18005ea81  lea     rax, [rbp+140h+var_180]
0x18005ea85  mov     [rbp+140h+var_B8], rax
0x18005ea8c  mov     byte ptr [rbp+140h+var_B0], 1
0x18005ea93  lea     rdx, [rsi+30h]
0x18005ea97  lea     rcx, [rbp+140h+var_90]
0x18005ea9e  call    KerbConvertRealmToUnicodeString
0x18005eaa3  mov     edi, eax
0x18005eaa5  test    eax, eax
0x18005eaa7  jz      short loc_18005EAE1
0x18005eaa9  lea     rcx, [rbp+140h+var_90]
0x18005eab0  call    KerbFreeString
0x18005eab5  lea     rcx, [rbp+140h+var_1A8]
0x18005eab9  call    KerbFreeString
0x18005eabe  lea     rcx, [rbp+140h+var_1B8]
0x18005eac2  call    KerbFreeSid
0x18005eac7  lea     rcx, [rbp+140h+var_180]; struct _KDC_TICKET_INFO *
0x18005eacb  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005ead0  nop
0x18005ead1  lea     rcx, [rbp+140h+var_E8]
0x18005ead5  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005eada  mov     eax, edi
0x18005eadc  jmp     loc_18005F002
0x18005eae1  lea     rdx, [rbp+140h+var_90]; struct _UNICODE_STRING *
0x18005eae8  call    ?IsOurRealm@CSecurityData@@QEAAEPEAU_UNICODE_STRING@@@Z; CSecurityData::IsOurRealm(_UNICODE_STRING *)
0x18005eaed  test    al, al
0x18005eaef  jnz     short loc_18005EB30
0x18005eaf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eaf8  cmp     rcx, r13
0x18005eafb  jz      loc_18005ECBC
0x18005eb01  test    byte ptr [rcx+1Ch], 1
0x18005eb05  jz      loc_18005ECBC
0x18005eb0b  movzx   eax, word ptr [rbx+62h]
0x18005eb0f  lea     rdx, [rbp+140h+var_90]
0x18005eb16  mov     [rsp+240h+var_218], rdx
0x18005eb1b  mov     dword ptr [rsp+240h+var_220], eax
0x18005eb1f  mov     r9, rbx
0x18005eb22  mov     rcx, [rcx+10h]
0x18005eb26  call    WPP_SF_ZDZ
0x18005eb2b  jmp     loc_18005ECBC
0x18005eb30  lea     rdx, [rsi+38h]; struct KERB_PRINCIPAL_NAME *
0x18005eb34  lea     rcx, [rbp+140h+var_1B8]; struct _KERB_INTERNAL_NAME **
0x18005eb38  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x18005eb3d  mov     edi, eax
0x18005eb3f  test    eax, eax
0x18005eb41  jnz     loc_18005EAA9
0x18005eb47  mov     [rbp+140h+var_1C0], r15b
0x18005eb4b  mov     [rsp+240h+var_1C8], r15; struct _SID_AND_ATTRIBUTES_LIST *
0x18005eb50  mov     [rsp+240h+var_1D0], r15; struct _USER_INTERNAL6_INFORMATION **
0x18005eb55  mov     [rsp+240h+var_1D8], r15d; unsigned int
0x18005eb5a  mov     [rsp+240h+var_1E0], r15d; unsigned int
0x18005eb5f  mov     [rsp+240h+var_1E8], r15; void **
0x18005eb64  lea     rax, [rbp+140h+Sid2]
0x18005eb6b  mov     [rsp+240h+var_1F0], rax; struct KERB_EXT_ERROR *
0x18005eb70  lea     rax, [rbp+140h+var_180]
0x18005eb74  mov     [rsp+240h+var_1F8], rax; struct _KDC_TICKET_INFO *
0x18005eb79  lea     rax, [rbp+140h+var_1A8]
0x18005eb7d  mov     [rsp+240h+var_200], rax; struct _UNICODE_STRING *
0x18005eb82  lea     rax, [rbp+140h+var_1C0]
0x18005eb86  mov     [rsp+240h+var_208], rax; unsigned __int8 *
0x18005eb8b  mov     [rsp+240h+var_210], r15; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18005eb90  mov     dword ptr [rsp+240h+var_218], r14d; unsigned int
0x18005eb95  mov     dword ptr [rsp+240h+var_220], 1; unsigned int
0x18005eb9d  xor     r9d, r9d; struct _UNICODE_STRING *
0x18005eba0  lea     r8, [rbp+140h+var_90]; struct _UNICODE_STRING *
0x18005eba7  xor     edx, edx; struct _UNICODE_STRING *
0x18005eba9  mov     rcx, [rbp+140h+var_1B8]; struct _KERB_INTERNAL_NAME *
0x18005ebad  call    ?KdcNormalize@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@11KKPEAU_SAM_MAPPED_ATTRIBUTE_SET@@PEAE1PEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@@Z; KdcNormalize(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,_SAM_MAPPED_ATTRIBUTE_SET *,uchar *,_UNICODE_STRING *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *)
0x18005ebb2  mov     edi, eax
0x18005ebb4  test    eax, eax
0x18005ebb6  jz      short loc_18005EC23
0x18005ebb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebbf  cmp     rcx, r13
0x18005ebc2  jz      short loc_18005EC15
0x18005ebc4  test    byte ptr [rcx+1Ch], 1
0x18005ebc8  jz      short loc_18005EBF1
0x18005ebca  movzx   eax, word ptr [rbx+62h]
0x18005ebce  mov     edx, 0B0h
0x18005ebd3  mov     dword ptr [rsp+240h+var_220], eax
0x18005ebd7  mov     r9, rbx
0x18005ebda  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005ebe1  mov     rcx, [rcx+10h]
0x18005ebe5  call    WPP_SF_Zd
0x18005ebea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebf1  cmp     rcx, r13
0x18005ebf4  jz      short loc_18005EC15
0x18005ebf6  test    byte ptr [rcx+1Ch], 1
0x18005ebfa  jz      short loc_18005EC15
0x18005ebfc  mov     edx, 0B1h
0x18005ec01  mov     r9, [rbp+140h+var_1B8]
0x18005ec05  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x18005ec0c  mov     rcx, [rcx+10h]
0x18005ec10  call    WPP_SF__KERB_NAME_
0x18005ec15  cmp     edi, r14d
0x18005ec18  jz      loc_18005ECBC
0x18005ec1e  jmp     loc_18005EAA9
0x18005ec23  mov     dword ptr [rbp+140h+var_1B0], r15d
0x18005ec27  movzx   edx, word ptr [rbx+62h]
0x18005ec2b  lea     r8, [rbp+140h+var_1B0]
0x18005ec2f  mov     ecx, [rbp+140h+var_150]
0x18005ec32  call    cs:__imp_SamIQueryAccountSecretsCachability
0x18005ec38  test    eax, eax
0x18005ec3a  jns     short loc_18005EC7E
0x18005ec3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec43  cmp     rcx, r13
0x18005ec46  jz      short loc_18005EC74
0x18005ec48  test    byte ptr [rcx+1Ch], 1
0x18005ec4c  jz      short loc_18005EC74
0x18005ec4e  movzx   eax, word ptr [rbx+62h]
0x18005ec52  mov     edx, 0B2h
0x18005ec57  mov     dword ptr [rsp+240h+var_210], eax
0x18005ec5b  mov     [rsp+240h+var_218], rbx
0x18005ec60  mov     eax, [rbp+140h+var_150]
0x18005ec63  mov     dword ptr [rsp+240h+var_220], eax
0x18005ec67  lea     r9, [rbp+140h+var_180]
0x18005ec6b  mov     rcx, [rcx+10h]
0x18005ec6f  call    WPP_SF_ZDZD
0x18005ec74  mov     edi, 0Ch
0x18005ec79  jmp     loc_18005EAA9
0x18005ec7e  cmp     dword ptr [rbp+140h+var_1B0], r15d
0x18005ec82  jnz     short loc_18005ECC6
0x18005ec84  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ec8b  cmp     rcx, r13
0x18005ec8e  jz      short loc_18005ECBC
0x18005ec90  test    byte ptr [rcx+1Ch], 1
0x18005ec94  jz      short loc_18005ECBC
0x18005ec96  movzx   eax, word ptr [rbx+62h]
0x18005ec9a  mov     edx, 0B3h
0x18005ec9f  mov     dword ptr [rsp+240h+var_210], eax
0x18005eca3  mov     [rsp+240h+var_218], rbx
0x18005eca8  mov     eax, [rbp+140h+var_150]
0x18005ecab  mov     dword ptr [rsp+240h+var_220], eax
0x18005ecaf  lea     r9, [rbp+140h+var_180]
0x18005ecb3  mov     rcx, [rcx+10h]
0x18005ecb7  call    WPP_SF_ZDZD
0x18005ecbc  mov     edi, 14h
0x18005ecc1  jmp     loc_18005EAA9
0x18005ecc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eccd  cmp     rcx, r13
0x18005ecd0  jz      short loc_18005ECFF
0x18005ecd2  test    byte ptr [rcx+1Ch], 1
0x18005ecd6  jz      short loc_18005ECFF
0x18005ecd8  movzx   eax, word ptr [rbx+62h]
0x18005ecdc  mov     edx, 0B4h
0x18005ece1  mov     dword ptr [rsp+240h+var_210], eax
0x18005ece5  mov     [rsp+240h+var_218], rbx
0x18005ecea  mov     eax, [rbp+140h+var_150]
0x18005eced  mov     dword ptr [rsp+240h+var_220], eax
0x18005ecf1  lea     r9, [rbp+140h+var_180]
0x18005ecf5  mov     rcx, [rcx+10h]
0x18005ecf9  call    WPP_SF_ZDZD
0x18005ecfe  nop
0x18005ecff  lea     rcx, [rbp+140h+var_90]
0x18005ed06  call    KerbFreeString
0x18005ed0b  lea     rcx, [rbp+140h+var_1A8]
0x18005ed0f  call    KerbFreeString
0x18005ed14  lea     rcx, [rbp+140h+var_1B8]
0x18005ed18  call    KerbFreeSid
0x18005ed1d  lea     rcx, [rbp+140h+var_180]; struct _KDC_TICKET_INFO *
0x18005ed21  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005ed26  nop
0x18005ed27  lea     rcx, [rbp+140h+var_E8]
0x18005ed2b  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18005ed30  mov     rcx, rbx; this
0x18005ed33  call    ?IsAnyKrbtgt@_KDC_TICKET_INFO@@QEBA_NXZ; _KDC_TICKET_INFO::IsAnyKrbtgt(void)
0x18005ed38  test    al, al
0x18005ed3a  jz      loc_18005F000
0x18005ed40  xorps   xmm0, xmm0
0x18005ed43  movups  xmmword ptr [rbp+140h+var_1A8.Length], xmm0
0x18005ed47  xorps   xmm1, xmm1
0x18005ed4a  movups  xmmword ptr [rbp+140h+var_198.Length], xmm1
0x18005ed4e  mov     [rbp+140h+var_1B8], r15
0x18005ed52  xor     eax, eax
0x18005ed54  mov     qword ptr [rbp+140h+var_90.Length], rax
0x18005ed5b  mov     dword ptr [rbp+140h+var_90.Buffer], eax
0x18005ed61  mov     [rbp+140h+var_144], eax
0x18005ed64  mov     [rbp+140h+var_12F], eax
0x18005ed67  mov     [rbp+140h+var_12B], ax
0x18005ed6b  mov     [rbp+140h+var_129], al
0x18005ed6e  mov     [rbp+140h+var_117], ax
0x18005ed72  mov     [rbp+140h+var_115], al
0x18005ed75  mov     [rbp+140h+var_10C], eax
0x18005ed78  xor     edx, edx; Val
0x18005ed7a  mov     r8d, 98h; Size
0x18005ed80  lea     rcx, [rbp+140h+var_180]; void *
0x18005ed84  call    memset_0
0x18005ed89  mov     [rbp+140h+var_E8], r15
0x18005ed8d  xorps   xmm0, xmm0
0x18005ed90  movdqa  [rbp+140h+var_E0], xmm0
0x18005ed95  mov     dword ptr [rbp+140h+var_1B0], r15d
0x18005ed99  mov     [rbp+140h+Sid2], r15
0x18005eda0  lea     rax, [rbp+140h+var_1A8]
0x18005eda4  mov     [rbp+140h+var_D0], rax
0x18005eda8  lea     rax, [rbp+140h+var_198]
0x18005edac  mov     [rbp+140h+var_C8], rax
0x18005edb0  lea     rax, [rbp+140h+var_1B8]
0x18005edb4  mov     [rbp+140h+var_C0], rax
0x18005edbb  lea     rax, [rbp+140h+var_180]
0x18005edbf  mov     [rbp+140h+var_B8], rax
0x18005edc6  lea     rax, [rbp+140h+Sid2]
0x18005edcd  mov     [rbp+140h+var_B0], rax
0x18005edd4  mov     [rbp+140h+var_A8], 1
0x18005eddb  lea     rdx, [rsi+30h]
0x18005eddf  lea     rcx, [rbp+140h+var_1A8]
0x18005ede3  call    KerbConvertRealmToUnicodeString
0x18005ede8  mov     edi, eax
0x18005edea  test    eax, eax
0x18005edec  jz      short loc_18005EE24
0x18005edee  lea     rcx, [rbp+140h+var_1A8]
0x18005edf2  call    KerbFreeString
0x18005edf7  lea     rcx, [rbp+140h+var_198]
0x18005edfb  call    KerbFreeString
0x18005ee00  lea     rcx, [rbp+140h+var_1B8]
0x18005ee04  call    KerbFreeSid
0x18005ee09  lea     rcx, [rbp+140h+var_180]; struct _KDC_TICKET_INFO *
0x18005ee0d  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18005ee12  mov     rcx, [rbp+140h+Sid2]; void *
0x18005ee19  call    MIDL_user_free
0x18005ee1e  nop
0x18005ee1f  jmp     loc_18005EAD1
0x18005ee24  lea     rdx, [rbp+140h+var_1A8]; struct _UNICODE_STRING *
0x18005ee28  call    ?IsOurRealm@CSecurityData@@QEAAEPEAU_UNICODE_STRING@@@Z; CSecurityData::IsOurRealm(_UNICODE_STRING *)
0x18005ee2d  test    al, al
0x18005ee2f  jz      loc_18005EFC6
0x18005ee35  lea     rdx, [rsi+38h]; struct KERB_PRINCIPAL_NAME *
0x18005ee39  lea     rcx, [rbp+140h+var_1B8]; struct _KERB_INTERNAL_NAME **
0x18005ee3d  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x18005ee42  mov     edi, eax
0x18005ee44  test    eax, eax
0x18005ee46  jnz     short loc_18005EDEE
0x18005ee48  mov     [rbp+140h+var_1C0], r15b
0x18005ee4c  mov     [rsp+240h+var_1C8], r15; struct _SID_AND_ATTRIBUTES_LIST *
0x18005ee51  mov     [rsp+240h+var_1D0], r15; struct _USER_INTERNAL6_INFORMATION **
0x18005ee56  mov     [rsp+240h+var_1D8], r15d; unsigned int
0x18005ee5b  mov     [rsp+240h+var_1E0], r15d; unsigned int
0x18005ee60  mov     [rsp+240h+var_1E8], r15; void **
0x18005ee65  lea     rax, [rbp+140h+var_90]
0x18005ee6c  mov     [rsp+240h+var_1F0], rax; struct KERB_EXT_ERROR *
0x18005ee71  lea     rax, [rbp+140h+var_180]
0x18005ee75  mov     [rsp+240h+var_1F8], rax; struct _KDC_TICKET_INFO *
0x18005ee7a  lea     rax, [rbp+140h+var_198]
0x18005ee7e  mov     [rsp+240h+var_200], rax; struct _UNICODE_STRING *
0x18005ee83  lea     rax, [rbp+140h+var_1C0]
0x18005ee87  mov     [rsp+240h+var_208], rax; unsigned __int8 *
0x18005ee8c  mov     [rsp+240h+var_210], r15; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x18005ee91  mov     dword ptr [rsp+240h+var_218], r14d; unsigned int
0x18005ee96  mov     dword ptr [rsp+240h+var_220], 1; unsigned int
0x18005ee9e  xor     r9d, r9d; struct _UNICODE_STRING *
0x18005eea1  lea     r8, [rbp+140h+var_1A8]; struct _UNICODE_STRING *
0x18005eea5  xor     edx, edx; struct _UNICODE_STRING *
0x18005eea7  mov     rcx, [rbp+140h+var_1B8]; struct _KERB_INTERNAL_NAME *
0x18005eeab  call    ?KdcNormalize@@YAJPEAU_KERB_INTERNAL_NAME@@PEAU_UNICODE_STRING@@11KKPEAU_SAM_MAPPED_ATTRIBUTE_SET@@PEAE1PEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@@Z; KdcNormalize(_KERB_INTERNAL_NAME *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,_SAM_MAPPED_ATTRIBUTE_SET *,uchar *,_UNICODE_STRING *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *)
  ... truncated ...
```

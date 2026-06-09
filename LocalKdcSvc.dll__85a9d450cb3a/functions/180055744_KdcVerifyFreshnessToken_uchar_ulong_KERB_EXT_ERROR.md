# KdcVerifyFreshnessToken(uchar *,ulong,KERB_EXT_ERROR *)

- ea: `0x180055744`
- end: `0x180055c2d`
- name: `?KdcVerifyFreshnessToken@@YAJPEAEKPEAUKERB_EXT_ERROR@@@Z`
- size: `1257`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, struct KERB_EXT_ERROR *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050e78`

## callees

- `0x180003908`
- `0x18000ab40`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x1800204e0`
- `0x180055744`
- `0x18005a3a4`
- `0x18005c2a4`
- `0x18005c334`
- `0x18007f0cc`
- `0x18007f1e4`
- `0x18007f5c4`
- `0x18007fa48`
- `0x180082a74`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055aab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180055aab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall KdcVerifyFreshnessToken(unsigned __int8 *a1, unsigned int a2, struct KERB_EXT_ERROR *a3)
{
  CSecurityData *v5; // rcx
  unsigned int KrbtgtTicketInfo; // ebx
  KerberosCryptoPolicy *v7; // rbx
  unsigned int v8; // esi
  unsigned __int64 v9; // rax
  CSecurityData *v10; // rcx
  __int64 v12; // [rsp+48h] [rbp-C0h] BYREF
  KerberosCryptoPolicy *v13; // [rsp+50h] [rbp-B8h] BYREF
  union _LARGE_INTEGER Time; // [rsp+58h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v16[60]; // [rsp+68h] [rbp-A0h] BYREF
  int v17; // [rsp+A4h] [rbp-64h]
  int v18; // [rsp+B9h] [rbp-4Fh]
  __int16 v19; // [rsp+BDh] [rbp-4Bh]
  char v20; // [rsp+BFh] [rbp-49h]
  __int16 v21; // [rsp+D1h] [rbp-37h]
  char v22; // [rsp+D3h] [rbp-35h]
  int v23; // [rsp+DCh] [rbp-2Ch]
  __int64 v24; // [rsp+100h] [rbp-8h] BYREF
  __int128 v25; // [rsp+108h] [rbp+0h]
  __int64 *v26; // [rsp+118h] [rbp+10h]
  __int64 *v27; // [rsp+120h] [rbp+18h]
  _BYTE *v28; // [rsp+128h] [rbp+20h]
  char v29; // [rsp+130h] [rbp+28h]
  struct KERB_EXT_ERROR *v30; // [rsp+168h] [rbp+60h] BYREF
  __int64 v31; // [rsp+170h] [rbp+68h] BYREF

  v30 = a3;
  v31 = 0;
  v12 = 0;
  SystemTimeAsFileTime = 0;
  Time.QuadPart = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset_0(v16, 0, 0x98u);
  v24 = 0;
  v25 = 0;
  v26 = &v31;
  v27 = &v12;
  v28 = v16;
  v29 = 1;
  KrbtgtTicketInfo = CSecurityData::GetKrbtgtTicketInfo(v5, (struct _KDC_TICKET_INFO *)v16);
  if ( KrbtgtTicketInfo )
  {
    KerbFreeData(7, v31);
    KerbFreeData(10, v12);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
LABEL_35:
    std::vector<unsigned int>::_Tidy((__int64)&v24);
    return KrbtgtTicketInfo;
  }
  KerberosCryptoPolicy::FromKdcTicketInfo(&v13, (const struct _KDC_TICKET_INFO *)v16);
  v7 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
    KerbFreeData(7, v31);
    KerbFreeData(10, v12);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
    KrbtgtTicketInfo = 60;
    goto LABEL_35;
  }
  if ( a2 < 2 || *(_WORD *)a1 )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
    KerbFreeData(7, v31);
    KerbFreeData(10, v12);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
    std::vector<unsigned int>::_Tidy((__int64)&v24);
    return 41;
  }
  else
  {
    v8 = KerbUnpackData(a1 + 2, a2 - 2, 7, &v31);
    if ( v8 )
    {
LABEL_11:
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
      KerbFreeData(7, v31);
      KerbFreeData(10, v12);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
      KrbtgtTicketInfo = v8;
      goto LABEL_35;
    }
    v9 = (unsigned __int64)*(unsigned int *)(v31 + 8) >> 16;
    if ( KdcGlobalCDC )
    {
      if ( (_WORD)v9 != KdcGlobalBranchID )
      {
        utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
        KerbFreeData(7, v31);
        KerbFreeData(10, v12);
        FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
        KrbtgtTicketInfo = -2147483641;
        goto LABEL_35;
      }
    }
    else if ( (_WORD)v9 )
    {
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
      KerbFreeData(7, v31);
      KerbFreeData(10, v12);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
      KrbtgtTicketInfo = 24;
      goto LABEL_35;
    }
    LODWORD(v30) = 0;
    if ( (unsigned int)KerberosCryptoPolicy::DecryptNoCopy(
                         (__int64)v7,
                         v31,
                         60,
                         (_DWORD *)(v31 + 16),
                         (void **)(v31 + 24),
                         (__int64)&v30,
                         0) )
    {
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
      KerbFreeData(7, v31);
      KerbFreeData(10, v12);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
      KrbtgtTicketInfo = 41;
      goto LABEL_35;
    }
    v8 = KerbUnpackData(*(_QWORD *)(v31 + 24), *(unsigned int *)(v31 + 16), 10, &v12);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, 67769836);
      goto LABEL_11;
    }
    KerbConvertGeneralizedTimeToLargeInt(&Time);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( !(unsigned __int8)KerbCheckTimeSkew(&SystemTimeAsFileTime, &Time) )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, 67769863);
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v10 + 28) & 1) != 0 )
          {
            WPP_SF__PDATE_TIME_(*((_QWORD *)v10 + 2), 158, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, &Time);
            v10 = WPP_GLOBAL_Control;
          }
          if ( v10 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
            WPP_SF__PDATE_TIME_(
              *((_QWORD *)v10 + 2),
              159,
              WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids,
              &SystemTimeAsFileTime);
        }
      }
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
      KerbFreeData(7, v31);
      KerbFreeData(10, v12);
      FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
      KrbtgtTicketInfo = 90;
      goto LABEL_35;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
    KerbFreeData(7, v31);
    KerbFreeData(10, v12);
    FreeTicketInfo((struct _KDC_TICKET_INFO *)v16);
    std::vector<unsigned int>::_Tidy((__int64)&v24);
    return 0;
  }
}

```

## disassembly

```asm
0x180055744  mov     rax, rsp
0x180055747  mov     [rax+8], rbx
0x18005574b  mov     [rax+10h], rsi
0x18005574f  mov     [rax+18h], r8
0x180055753  push    rbp
0x180055754  push    rdi
0x180055755  push    r14
0x180055757  lea     rbp, [rax-48h]
0x18005575b  sub     rsp, 130h
0x180055762  mov     edi, edx
0x180055764  mov     rsi, rcx
0x180055767  xor     r14d, r14d
0x18005576a  mov     [rbp+40h+arg_18], r14
0x18005576e  mov     [rsp+140h+var_100], r14
0x180055773  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180055778  mov     qword ptr [rsp+140h+Time], r14
0x18005577d  xor     eax, eax
0x18005577f  mov     [rbp+40h+var_A4], eax
0x180055782  mov     [rbp+40h+var_8F], eax
0x180055785  mov     [rbp+40h+var_8B], ax
0x180055789  mov     [rbp+40h+var_89], al
0x18005578c  mov     [rbp+40h+var_77], ax
0x180055790  mov     [rbp+40h+var_75], al
0x180055793  mov     [rbp+40h+var_6C], eax
0x180055796  xor     edx, edx; Val
0x180055798  mov     r8d, 98h; Size
0x18005579e  lea     rcx, [rsp+140h+var_E0]; void *
0x1800557a3  call    memset_0
0x1800557a8  mov     [rbp+40h+var_48], r14
0x1800557ac  xorps   xmm0, xmm0
0x1800557af  movdqa  [rbp+40h+var_40], xmm0
0x1800557b4  lea     rax, [rbp+40h+arg_18]
0x1800557b8  mov     [rbp+40h+var_30], rax
0x1800557bc  lea     rax, [rsp+140h+var_100]
0x1800557c1  mov     [rbp+40h+var_28], rax
0x1800557c5  lea     rax, [rsp+140h+var_E0]
0x1800557ca  mov     [rbp+40h+var_20], rax
0x1800557ce  mov     [rbp+40h+var_18], 1
0x1800557d2  lea     rdx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x1800557d7  call    ?GetKrbtgtTicketInfo@CSecurityData@@QEAAJPEAU_KDC_TICKET_INFO@@@Z; CSecurityData::GetKrbtgtTicketInfo(_KDC_TICKET_INFO *)
0x1800557dc  mov     ebx, eax
0x1800557de  test    eax, eax
0x1800557e0  jz      short loc_18005580D
0x1800557e2  mov     rdx, [rbp+40h+arg_18]
0x1800557e6  lea     ecx, [r14+7]
0x1800557ea  call    KerbFreeData
0x1800557ef  mov     rdx, [rsp+140h+var_100]
0x1800557f4  lea     ecx, [r14+0Ah]
0x1800557f8  call    KerbFreeData
0x1800557fd  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055802  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055807  nop
0x180055808  jmp     loc_180055B8A
0x18005580d  lea     rdx, [rsp+140h+var_E0]
0x180055812  lea     rcx, [rsp+140h+var_F8]
0x180055817  call    ?FromKdcTicketInfo@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEBU_KDC_TICKET_INFO@@@Z; KerberosCryptoPolicy::FromKdcTicketInfo(_KDC_TICKET_INFO const *)
0x18005581c  nop
0x18005581d  mov     rbx, [rsp+140h+var_F8]
0x180055822  test    rbx, rbx
0x180055825  jnz     short loc_180055893
0x180055827  lea     rbx, WPP_GLOBAL_Control
0x18005582e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055835  cmp     rcx, rbx
0x180055838  jz      short loc_180055856
0x18005583a  test    byte ptr [rcx+1Ch], 1
0x18005583e  jz      short loc_180055856
0x180055840  mov     edx, 9Bh
0x180055845  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18005584c  mov     rcx, [rcx+10h]
0x180055850  call    WPP_SF_
0x180055855  nop
0x180055856  lea     rcx, [rsp+140h+var_F8]
0x18005585b  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055860  nop
0x180055861  mov     rdx, [rbp+40h+arg_18]
0x180055865  mov     ecx, 7
0x18005586a  call    KerbFreeData
0x18005586f  mov     rdx, [rsp+140h+var_100]
0x180055874  mov     ecx, 0Ah
0x180055879  call    KerbFreeData
0x18005587e  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055883  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055888  nop
0x180055889  mov     ebx, 3Ch ; '<'
0x18005588e  jmp     loc_180055B8A
0x180055893  cmp     edi, 2
0x180055896  jb      loc_180055BD4
0x18005589c  cmp     [rsi], r14w
0x1800558a0  jnz     loc_180055BD4
0x1800558a6  lea     edx, [rdi-2]
0x1800558a9  lea     rcx, [rsi+2]
0x1800558ad  lea     r9, [rbp+40h+arg_18]
0x1800558b1  mov     edi, 7
0x1800558b6  mov     r8d, edi
0x1800558b9  call    KerbUnpackData
0x1800558be  mov     esi, eax
0x1800558c0  test    eax, eax
0x1800558c2  jz      short loc_1800558F9
0x1800558c4  lea     rcx, [rsp+140h+var_F8]
0x1800558c9  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x1800558ce  nop
0x1800558cf  mov     rdx, [rbp+40h+arg_18]
0x1800558d3  mov     ecx, edi
0x1800558d5  call    KerbFreeData
0x1800558da  mov     rdx, [rsp+140h+var_100]
0x1800558df  lea     ecx, [rdi+3]
0x1800558e2  call    KerbFreeData
0x1800558e7  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x1800558ec  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x1800558f1  nop
0x1800558f2  mov     ebx, esi
0x1800558f4  jmp     loc_180055B8A
0x1800558f9  mov     rdx, [rbp+40h+arg_18]
0x1800558fd  mov     eax, [rdx+8]
0x180055900  shr     rax, 10h
0x180055904  cmp     cs:?KdcGlobalCDC@@3HA, r14d; int KdcGlobalCDC
0x18005590b  jz      short loc_180055950
0x18005590d  cmp     ax, cs:?KdcGlobalBranchID@@3GA; ushort KdcGlobalBranchID
0x180055914  jz      short loc_18005598F
0x180055916  lea     rcx, [rsp+140h+var_F8]
0x18005591b  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055920  nop
0x180055921  mov     rdx, [rbp+40h+arg_18]
0x180055925  mov     ecx, edi
0x180055927  call    KerbFreeData
0x18005592c  mov     rdx, [rsp+140h+var_100]
0x180055931  mov     ecx, 0Ah
0x180055936  call    KerbFreeData
0x18005593b  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055940  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055945  nop
0x180055946  mov     ebx, 80000007h
0x18005594b  jmp     loc_180055B8A
0x180055950  test    ax, ax
0x180055953  jz      short loc_18005598F
0x180055955  lea     rcx, [rsp+140h+var_F8]
0x18005595a  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18005595f  nop
0x180055960  mov     rdx, [rbp+40h+arg_18]
0x180055964  mov     ecx, edi
0x180055966  call    KerbFreeData
0x18005596b  mov     rdx, [rsp+140h+var_100]
0x180055970  mov     ecx, 0Ah
0x180055975  call    KerbFreeData
0x18005597a  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x18005597f  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055984  nop
0x180055985  mov     ebx, 18h
0x18005598a  jmp     loc_180055B8A
0x18005598f  mov     dword ptr [rbp+40h+arg_10], r14d
0x180055993  lea     r9, [rdx+10h]
0x180055997  lea     rax, [r9+8]
0x18005599b  mov     [rsp+140h+var_110], r14d
0x1800559a0  lea     rcx, [rbp+40h+arg_10]
0x1800559a4  mov     qword ptr [rsp+140h+var_118], rcx
0x1800559a9  mov     [rsp+140h+var_120], rax
0x1800559ae  mov     r8d, 3Ch ; '<'
0x1800559b4  mov     rcx, rbx
0x1800559b7  call    ?DecryptNoCopy@KerberosCryptoPolicy@@AEAAJPEAUKERB_ENCRYPTED_DATA@@W4KeyUsage@Kerb3961@@PEAKPEAPEAX2W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::DecryptNoCopy(KERB_ENCRYPTED_DATA *,Kerb3961::KeyUsage,ulong *,void * *,ulong *,KdcPrincipalKeyState)
0x1800559bc  test    eax, eax
0x1800559be  jz      short loc_1800559FA
0x1800559c0  lea     rcx, [rsp+140h+var_F8]
0x1800559c5  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x1800559ca  nop
0x1800559cb  mov     rdx, [rbp+40h+arg_18]
0x1800559cf  mov     ecx, edi
0x1800559d1  call    KerbFreeData
0x1800559d6  mov     rdx, [rsp+140h+var_100]
0x1800559db  mov     ecx, 0Ah
0x1800559e0  call    KerbFreeData
0x1800559e5  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x1800559ea  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x1800559ef  nop
0x1800559f0  mov     ebx, 29h ; ')'
0x1800559f5  jmp     loc_180055B8A
0x1800559fa  lea     r9, [rsp+140h+var_100]
0x1800559ff  mov     r8d, 0Ah
0x180055a05  mov     rcx, [rbp+40h+arg_18]
0x180055a09  mov     edx, [rcx+10h]
0x180055a0c  mov     rcx, [rcx+18h]
0x180055a10  call    KerbUnpackData
0x180055a15  mov     esi, eax
0x180055a17  test    eax, eax
0x180055a19  jz      short loc_180055A85
0x180055a1b  lea     rbx, WPP_GLOBAL_Control
0x180055a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a29  cmp     rcx, rbx
0x180055a2c  jz      short loc_180055A50
0x180055a2e  test    byte ptr [rcx+1Ch], 2
0x180055a32  jz      short loc_180055A50
0x180055a34  mov     edx, 9Ch
0x180055a39  mov     r9d, 40A15ECh
0x180055a3f  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055a46  mov     rcx, [rcx+10h]
0x180055a4a  call    WPP_SF_d
0x180055a4f  nop
0x180055a50  lea     rcx, [rsp+140h+var_F8]
0x180055a55  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055a5a  nop
0x180055a5b  mov     rdx, [rbp+40h+arg_18]
0x180055a5f  mov     ecx, edi
0x180055a61  call    KerbFreeData
0x180055a66  mov     rdx, [rsp+140h+var_100]
0x180055a6b  mov     ecx, 0Ah
0x180055a70  call    KerbFreeData
0x180055a75  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055a7a  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055a7f  nop
0x180055a80  jmp     loc_1800558F2
0x180055a85  mov     rdx, [rsp+140h+var_100]
0x180055a8a  test    byte ptr [rdx], 80h
0x180055a8d  jz      short loc_180055A95
0x180055a8f  mov     r8d, [rdx+10h]
0x180055a93  jmp     short loc_180055A98
0x180055a95  mov     r8d, r14d
0x180055a98  add     rdx, 2
0x180055a9c  lea     rcx, [rsp+140h+Time]; Time
0x180055aa1  call    KerbConvertGeneralizedTimeToLargeInt
0x180055aa6  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180055aab  call    cs:__imp_GetSystemTimeAsFileTime
0x180055ab1  lea     rdx, [rsp+140h+Time]
0x180055ab6  lea     rcx, [rsp+140h+SystemTimeAsFileTime]
0x180055abb  call    KerbCheckTimeSkew
0x180055ac0  test    al, al
0x180055ac2  jnz     loc_180055B97
0x180055ac8  lea     rbx, WPP_GLOBAL_Control
0x180055acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ad6  cmp     rcx, rbx
0x180055ad9  jz      short loc_180055B55
0x180055adb  test    byte ptr [rcx+1Ch], 1
0x180055adf  jz      short loc_180055B03
0x180055ae1  mov     edx, 9Dh
0x180055ae6  mov     r9d, 40A1607h
0x180055aec  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055af3  mov     rcx, [rcx+10h]
0x180055af7  call    WPP_SF_d
0x180055afc  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b03  cmp     rcx, rbx
0x180055b06  jz      short loc_180055B55
0x180055b08  test    byte ptr [rcx+1Ch], 1
0x180055b0c  jz      short loc_180055B2F
0x180055b0e  mov     edx, 9Eh
0x180055b13  lea     r9, [rsp+140h+Time]
0x180055b18  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055b1f  mov     rcx, [rcx+10h]
0x180055b23  call    WPP_SF__PDATE_TIME_
0x180055b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b2f  cmp     rcx, rbx
0x180055b32  jz      short loc_180055B55
0x180055b34  test    byte ptr [rcx+1Ch], 1
0x180055b38  jz      short loc_180055B55
0x180055b3a  mov     edx, 9Fh
0x180055b3f  lea     r9, [rsp+140h+SystemTimeAsFileTime]
0x180055b44  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x180055b4b  mov     rcx, [rcx+10h]
0x180055b4f  call    WPP_SF__PDATE_TIME_
0x180055b54  nop
0x180055b55  lea     rcx, [rsp+140h+var_F8]
0x180055b5a  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055b5f  nop
0x180055b60  mov     rdx, [rbp+40h+arg_18]
0x180055b64  mov     ecx, edi
0x180055b66  call    KerbFreeData
0x180055b6b  mov     rdx, [rsp+140h+var_100]
0x180055b70  mov     ecx, 0Ah
0x180055b75  call    KerbFreeData
0x180055b7a  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055b7f  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055b84  nop
0x180055b85  mov     ebx, 5Ah ; 'Z'
0x180055b8a  lea     rcx, [rbp+40h+var_48]
0x180055b8e  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180055b93  mov     eax, ebx
0x180055b95  jmp     short loc_180055C15
0x180055b97  lea     rcx, [rsp+140h+var_F8]
0x180055b9c  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055ba1  nop
0x180055ba2  mov     rdx, [rbp+40h+arg_18]
0x180055ba6  mov     ecx, edi
0x180055ba8  call    KerbFreeData
0x180055bad  mov     rdx, [rsp+140h+var_100]
0x180055bb2  mov     ecx, 0Ah
0x180055bb7  call    KerbFreeData
0x180055bbc  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
0x180055bc1  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x180055bc6  nop
0x180055bc7  lea     rcx, [rbp+40h+var_48]
0x180055bcb  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180055bd0  xor     eax, eax
0x180055bd2  jmp     short loc_180055C15
0x180055bd4  lea     rcx, [rsp+140h+var_F8]
0x180055bd9  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180055bde  nop
0x180055bdf  mov     rdx, [rbp+40h+arg_18]
0x180055be3  mov     ecx, 7
0x180055be8  call    KerbFreeData
0x180055bed  mov     rdx, [rsp+140h+var_100]
0x180055bf2  mov     ecx, 0Ah
0x180055bf7  call    KerbFreeData
0x180055bfc  lea     rcx, [rsp+140h+var_E0]; struct _KDC_TICKET_INFO *
  ... truncated ...
```

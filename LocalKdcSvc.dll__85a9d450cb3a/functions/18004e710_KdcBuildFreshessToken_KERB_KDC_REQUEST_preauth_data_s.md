# KdcBuildFreshessToken(KERB_KDC_REQUEST_preauth_data_s * *)

- ea: `0x18004e710`
- end: `0x18004ea6d`
- name: `?KdcBuildFreshessToken@@YAJPEAPEAUKERB_KDC_REQUEST_preauth_data_s@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(struct KERB_KDC_REQUEST_preauth_data_s **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb2c`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x180003908`
- `0x18000ab40`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18004e710`
- `0x18005a060`
- `0x18005a090`
- `0x18005a3a4`
- `0x18005c2a4`
- `0x18005c334`
- `0x18007f3dc`
- `0x18007f78c`
- `0x180080e48`
- `0x180082c7c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e869`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e869`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall KdcBuildFreshessToken(struct KERB_KDC_REQUEST_preauth_data_s **a1)
{
  CSecurityData *v2; // rcx
  unsigned int KrbtgtTicketInfo; // ebx
  KerberosCryptoPolicy *v4; // rbx
  unsigned int v5; // r14d
  CSecurityData *v6; // rcx
  __int64 v7; // rdx
  struct KERB_KDC_REQUEST_preauth_data_s *v8; // rax
  size_t v9; // rbx
  KerberosCryptoPolicy *v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD Size[3]; // [rsp+3Ch] [rbp-C4h] BYREF
  void *v14; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  void *v17[2]; // [rsp+68h] [rbp-98h]
  _DWORD *v18; // [rsp+78h] [rbp-88h]
  __int128 *v19; // [rsp+80h] [rbp-80h]
  void **v20; // [rsp+88h] [rbp-78h]
  _QWORD *v21; // [rsp+90h] [rbp-70h]
  char v22; // [rsp+98h] [rbp-68h]
  _QWORD v23[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[44]; // [rsp+B0h] [rbp-50h] BYREF
  int v25; // [rsp+DCh] [rbp-24h]
  int v26; // [rsp+F1h] [rbp-Fh]
  __int16 v27; // [rsp+F5h] [rbp-Bh]
  char v28; // [rsp+F7h] [rbp-9h]
  int v29; // [rsp+100h] [rbp+0h]
  __int16 v30; // [rsp+109h] [rbp+9h]
  char v31; // [rsp+10Bh] [rbp+Bh]
  int v32; // [rsp+114h] [rbp+14h]
  __int64 v33; // [rsp+138h] [rbp+38h] BYREF
  __int128 v34; // [rsp+140h] [rbp+40h]
  __int128 v35; // [rsp+150h] [rbp+50h] BYREF
  int v36; // [rsp+160h] [rbp+60h] BYREF

  SystemTimeAsFileTime = 0;
  v35 = 0;
  v36 = 0;
  v12 = 0;
  v14 = 0;
  v16 = 0;
  *(_OWORD *)v17 = 0;
  memset(Size, 0, sizeof(Size));
  v23[0] = 0;
  v23[1] = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  memset_0(v24, 0, 0x88u);
  v33 = 0;
  v34 = 0;
  v18 = &Size[1];
  v19 = &v16;
  v20 = &v14;
  v21 = v23;
  v22 = 1;
  KrbtgtTicketInfo = CSecurityData::GetKrbtgtTicketInfo(v2, (struct _KDC_TICKET_INFO *)v23);
  if ( KrbtgtTicketInfo )
    goto LABEL_28;
  KerberosCryptoPolicy::FromKdcTicketInfo(&v11, (const struct _KDC_TICKET_INFO *)v23);
  v4 = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids);
LABEL_6:
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v11);
    KrbtgtTicketInfo = 60;
    goto LABEL_28;
  }
  if ( (unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v11, 60) )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v11);
    KrbtgtTicketInfo = 14;
    goto LABEL_28;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  KerbConvertLargeIntToGeneralizedTimeWrapper((char *)&v35 + 2, &v36, &SystemTimeAsFileTime);
  LOWORD(v35) = 128;
  v5 = KerbPackData(&v35, 10, &v12, &v14);
  if ( !v5 )
  {
    KrbtgtTicketInfo = KerberosCryptoPolicy::Encrypt(v4, &v16, v12, v14, v29, 60);
    if ( KrbtgtTicketInfo )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v7 = 153;
    }
    else
    {
      KrbtgtTicketInfo = KerbPackData(&v16, 7, Size, &Size[1]);
      if ( !KrbtgtTicketInfo )
      {
        v8 = (struct KERB_KDC_REQUEST_preauth_data_s *)MIDL_user_allocate(0x20u);
        *a1 = v8;
        if ( v8 )
        {
          v9 = Size[0];
          *((_QWORD *)*a1 + 3) = MIDL_user_allocate(Size[0] + 4LL);
          if ( *((_QWORD *)*a1 + 3) )
          {
            *((_DWORD *)*a1 + 2) = 150;
            *((_DWORD *)*a1 + 4) = v9 + 2;
            **((_WORD **)*a1 + 3) = 0;
            memcpy_0((void *)(*((_QWORD *)*a1 + 3) + 2LL), *(const void **)&Size[1], v9);
            utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v11);
            KrbtgtTicketInfo = 0;
            goto LABEL_28;
          }
          MIDL_user_free(*a1);
          *a1 = 0;
        }
        goto LABEL_6;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v11);
        goto LABEL_28;
      }
      v7 = 154;
    }
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, KrbtgtTicketInfo);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids, v5);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v11);
  KrbtgtTicketInfo = v5;
LABEL_28:
  MIDL_user_free(*(void **)&Size[1]);
  MIDL_user_free(v17[1]);
  MIDL_user_free(v14);
  FreeTicketInfo((struct _KDC_TICKET_INFO *)v23);
  std::vector<unsigned int>::_Tidy((__int64)&v33);
  return KrbtgtTicketInfo;
}

```

## disassembly

```asm
0x18004e710  push    rbp
0x18004e712  push    rbx
0x18004e713  push    rsi
0x18004e714  push    r14
0x18004e716  lea     rbp, [rsp-78h]
0x18004e71b  sub     rsp, 178h
0x18004e722  mov     rax, cs:__security_cookie
0x18004e729  xor     rax, rsp
0x18004e72c  mov     [rbp+90h+var_28], rax
0x18004e730  mov     rsi, rcx
0x18004e733  mov     qword ptr [rsp+190h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004e73c  xorps   xmm0, xmm0
0x18004e73f  xor     eax, eax
0x18004e741  movups  [rbp+90h+var_40], xmm0
0x18004e745  mov     [rbp+90h+var_30], eax
0x18004e748  mov     [rsp+190h+var_158], eax
0x18004e74c  mov     [rsp+190h+var_148], rax
0x18004e751  movups  [rsp+190h+var_138], xmm0
0x18004e756  movups  xmmword ptr [rsp+190h+var_128], xmm0
0x18004e75b  mov     dword ptr [rsp+190h+Size], eax
0x18004e75f  mov     qword ptr [rsp+190h+Size+4], rax
0x18004e764  mov     [rbp+90h+var_F0], rax
0x18004e768  mov     [rbp+90h+var_E8], rax
0x18004e76c  mov     [rbp+90h+var_B4], eax
0x18004e76f  mov     [rbp+90h+var_9F], eax
0x18004e772  mov     [rbp+90h+var_9B], ax
0x18004e776  mov     [rbp+90h+var_99], al
0x18004e779  mov     [rbp+90h+var_87], ax
0x18004e77d  mov     [rbp+90h+var_85], al
0x18004e780  mov     [rbp+90h+var_7C], eax
0x18004e783  xor     edx, edx; Val
0x18004e785  mov     r8d, 88h; Size
0x18004e78b  lea     rcx, [rbp+90h+var_E0]; void *
0x18004e78f  call    memset_0
0x18004e794  mov     [rbp+90h+var_58], 0
0x18004e79c  xorps   xmm0, xmm0
0x18004e79f  movdqa  [rbp+90h+var_50], xmm0
0x18004e7a4  lea     rax, [rsp+190h+Size+4]
0x18004e7a9  mov     [rsp+190h+var_118], rax
0x18004e7ae  lea     rax, [rsp+190h+var_138]
0x18004e7b3  mov     [rbp+90h+var_110], rax
0x18004e7b7  lea     rax, [rsp+190h+var_148]
0x18004e7bc  mov     [rbp+90h+var_108], rax
0x18004e7c0  lea     rax, [rbp+90h+var_F0]
0x18004e7c4  mov     [rbp+90h+var_100], rax
0x18004e7c8  mov     [rbp+90h+var_F8], 1
0x18004e7cc  lea     rdx, [rbp+90h+var_F0]; struct _KDC_TICKET_INFO *
0x18004e7d0  call    ?GetKrbtgtTicketInfo@CSecurityData@@QEAAJPEAU_KDC_TICKET_INFO@@@Z; CSecurityData::GetKrbtgtTicketInfo(_KDC_TICKET_INFO *)
0x18004e7d5  mov     ebx, eax
0x18004e7d7  test    eax, eax
0x18004e7d9  jnz     loc_18004EA21
0x18004e7df  lea     rdx, [rbp+90h+var_F0]
0x18004e7e3  lea     rcx, [rsp+190h+var_160]
0x18004e7e8  call    ?FromKdcTicketInfo@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEBU_KDC_TICKET_INFO@@@Z; KerberosCryptoPolicy::FromKdcTicketInfo(_KDC_TICKET_INFO const *)
0x18004e7ed  nop
0x18004e7ee  mov     rbx, [rsp+190h+var_160]
0x18004e7f3  test    rbx, rbx
0x18004e7f6  jnz     short loc_18004E83B
0x18004e7f8  lea     rax, WPP_GLOBAL_Control
0x18004e7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e806  cmp     rcx, rax
0x18004e809  jz      short loc_18004E827
0x18004e80b  test    byte ptr [rcx+1Ch], 1
0x18004e80f  jz      short loc_18004E827
0x18004e811  mov     edx, 97h
0x18004e816  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18004e81d  mov     rcx, [rcx+10h]
0x18004e821  call    WPP_SF_
0x18004e826  nop
0x18004e827  lea     rcx, [rsp+190h+var_160]
0x18004e82c  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18004e831  mov     ebx, 3Ch ; '<'
0x18004e836  jmp     loc_18004EA21
0x18004e83b  mov     edx, 3Ch ; '<'
0x18004e840  lea     r8d, [rdx-3Bh]
0x18004e844  mov     rcx, rbx
0x18004e847  call    ?HasCandidateKey@KerberosCryptoPolicy@@QEAA_NW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::HasCandidateKey(Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState)
0x18004e84c  test    al, al
0x18004e84e  jz      short loc_18004E864
0x18004e850  lea     rcx, [rsp+190h+var_160]
0x18004e855  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18004e85a  mov     ebx, 0Eh
0x18004e85f  jmp     loc_18004EA21
0x18004e864  lea     rcx, [rsp+190h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004e869  call    cs:__imp_GetSystemTimeAsFileTime
0x18004e86f  lea     r8, [rsp+190h+SystemTimeAsFileTime]
0x18004e874  lea     rdx, [rbp+90h+var_30]
0x18004e878  lea     rcx, [rbp+90h+var_40+2]
0x18004e87c  call    KerbConvertLargeIntToGeneralizedTimeWrapper
0x18004e881  mov     eax, 80h
0x18004e886  mov     word ptr [rbp+90h+var_40], ax
0x18004e88a  lea     r9, [rsp+190h+var_148]
0x18004e88f  lea     r8, [rsp+190h+var_158]
0x18004e894  lea     edx, [rax-76h]
0x18004e897  lea     rcx, [rbp+90h+var_40]
0x18004e89b  call    KerbPackData
0x18004e8a0  mov     r14d, eax
0x18004e8a3  test    eax, eax
0x18004e8a5  jz      short loc_18004E8EB
0x18004e8a7  lea     rax, WPP_GLOBAL_Control
0x18004e8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e8b5  cmp     rcx, rax
0x18004e8b8  jz      short loc_18004E8D9
0x18004e8ba  test    byte ptr [rcx+1Ch], 1
0x18004e8be  jz      short loc_18004E8D9
0x18004e8c0  mov     edx, 98h
0x18004e8c5  mov     r9d, r14d
0x18004e8c8  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18004e8cf  mov     rcx, [rcx+10h]
0x18004e8d3  call    WPP_SF_d
0x18004e8d8  nop
0x18004e8d9  lea     rcx, [rsp+190h+var_160]
0x18004e8de  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18004e8e3  mov     ebx, r14d
0x18004e8e6  jmp     loc_18004EA21
0x18004e8eb  mov     [rsp+190h+var_168], 3Ch ; '<'
0x18004e8f4  mov     eax, [rbp+90h+var_90]
0x18004e8f7  mov     [rsp+190h+var_170], eax
0x18004e8fb  mov     r9, [rsp+190h+var_148]
0x18004e900  mov     r8d, [rsp+190h+var_158]
0x18004e905  lea     rdx, [rsp+190h+var_138]
0x18004e90a  mov     rcx, rbx
0x18004e90d  call    ?Encrypt@KerberosCryptoPolicy@@QEAAJPEAUKERB_ENCRYPTED_DATA@@KPEAEKW4KeyUsage@Kerb3961@@@Z; KerberosCryptoPolicy::Encrypt(KERB_ENCRYPTED_DATA *,ulong,uchar *,ulong,Kerb3961::KeyUsage)
0x18004e912  mov     ebx, eax
0x18004e914  test    eax, eax
0x18004e916  jz      short loc_18004E959
0x18004e918  lea     rax, WPP_GLOBAL_Control
0x18004e91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e926  cmp     rcx, rax
0x18004e929  jz      short loc_18004E94A
0x18004e92b  test    byte ptr [rcx+1Ch], 1
0x18004e92f  jz      short loc_18004E94A
0x18004e931  mov     edx, 99h
0x18004e936  mov     r9d, ebx
0x18004e939  lea     r8, WPP_82c8cd1094813389f8097f3994d2fb76_Traceguids
0x18004e940  mov     rcx, [rcx+10h]
0x18004e944  call    WPP_SF_d
0x18004e949  nop
0x18004e94a  lea     rcx, [rsp+190h+var_160]
0x18004e94f  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18004e954  jmp     loc_18004EA21
0x18004e959  lea     r9, [rsp+190h+Size+4]
0x18004e95e  lea     r8, [rsp+190h+Size]
0x18004e963  mov     edx, 7
0x18004e968  lea     rcx, [rsp+190h+var_138]
0x18004e96d  call    KerbPackData
0x18004e972  mov     ebx, eax
0x18004e974  test    eax, eax
0x18004e976  jz      short loc_18004E998
0x18004e978  lea     rax, WPP_GLOBAL_Control
0x18004e97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e986  cmp     rcx, rax
0x18004e989  jz      short loc_18004E94A
0x18004e98b  test    byte ptr [rcx+1Ch], 1
0x18004e98f  jz      short loc_18004E94A
0x18004e991  mov     edx, 9Ah
0x18004e996  jmp     short loc_18004E936
0x18004e998  mov     ecx, 20h ; ' '; size
0x18004e99d  call    MIDL_user_allocate
0x18004e9a2  mov     [rsi], rax
0x18004e9a5  test    rax, rax
0x18004e9a8  jz      loc_18004E827
0x18004e9ae  mov     ebx, dword ptr [rsp+190h+Size]
0x18004e9b2  lea     rcx, [rbx+4]; size
0x18004e9b6  call    MIDL_user_allocate
0x18004e9bb  mov     rcx, [rsi]
0x18004e9be  mov     [rcx+18h], rax
0x18004e9c2  mov     rax, [rsi]
0x18004e9c5  cmp     qword ptr [rax+18h], 0
0x18004e9ca  jnz     short loc_18004E9E0
0x18004e9cc  mov     rcx, rax; void *
0x18004e9cf  call    MIDL_user_free
0x18004e9d4  mov     qword ptr [rsi], 0
0x18004e9db  jmp     loc_18004E827
0x18004e9e0  mov     dword ptr [rax+8], 96h
0x18004e9e7  lea     ecx, [rbx+2]
0x18004e9ea  mov     rax, [rsi]
0x18004e9ed  mov     [rax+10h], ecx
0x18004e9f0  mov     rax, [rsi]
0x18004e9f3  mov     rcx, [rax+18h]
0x18004e9f7  xor     eax, eax
0x18004e9f9  mov     [rcx], ax
0x18004e9fc  mov     rax, [rsi]
0x18004e9ff  mov     rcx, [rax+18h]
0x18004ea03  add     rcx, 2; void *
0x18004ea07  mov     r8, rbx; Size
0x18004ea0a  mov     rdx, qword ptr [rsp+190h+Size+4]; Src
0x18004ea0f  call    memcpy_0
0x18004ea14  nop
0x18004ea15  lea     rcx, [rsp+190h+var_160]
0x18004ea1a  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18004ea1f  xor     ebx, ebx
0x18004ea21  mov     rcx, qword ptr [rsp+190h+Size+4]; void *
0x18004ea26  call    MIDL_user_free
0x18004ea2b  mov     rcx, [rsp+190h+var_128+8]; void *
0x18004ea30  call    MIDL_user_free
0x18004ea35  mov     rcx, [rsp+190h+var_148]; void *
0x18004ea3a  call    MIDL_user_free
0x18004ea3f  lea     rcx, [rbp+90h+var_F0]; struct _KDC_TICKET_INFO *
0x18004ea43  call    ?FreeTicketInfo@@YAXPEAU_KDC_TICKET_INFO@@@Z; FreeTicketInfo(_KDC_TICKET_INFO *)
0x18004ea48  nop
0x18004ea49  lea     rcx, [rbp+90h+var_58]
0x18004ea4d  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18004ea52  mov     eax, ebx
0x18004ea54  mov     rcx, [rbp+90h+var_28]
0x18004ea58  xor     rcx, rsp; StackCookie
0x18004ea5b  call    __security_check_cookie
0x18004ea60  add     rsp, 178h
0x18004ea67  pop     r14
0x18004ea69  pop     rsi
0x18004ea6a  pop     rbx
0x18004ea6b  pop     rbp
0x18004ea6c  retn
```

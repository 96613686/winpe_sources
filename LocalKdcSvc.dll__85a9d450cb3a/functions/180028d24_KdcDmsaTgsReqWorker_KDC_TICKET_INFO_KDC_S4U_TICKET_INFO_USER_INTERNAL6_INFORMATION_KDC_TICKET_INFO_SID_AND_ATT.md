# KdcDmsaTgsReqWorker(_KDC_TICKET_INFO *,_KDC_S4U_TICKET_INFO *,_USER_INTERNAL6_INFORMATION *,_KDC_TICKET_INFO *,_SID_AND_ATTRIBUTES_LIST *,KERB_EXT_ERROR *,KERB_KDC_REQUEST_preauth_data_s * *,_SID_AND_ATTRIBUTES_LIST *)

- ea: `0x180028d24`
- end: `0x18002949f`
- name: `?KdcDmsaTgsReqWorker@@YAJPEAU_KDC_TICKET_INFO@@PEAU_KDC_S4U_TICKET_INFO@@PEAU_USER_INTERNAL6_INFORMATION@@0PEAU_SID_AND_ATTRIBUTES_LIST@@PEAUKERB_EXT_ERROR@@PEAPEAUKERB_KDC_REQUEST_preauth_data_s@@3@Z`
- size: `1915`
- prototype: `__int64 __fastcall(struct _KDC_TICKET_INFO *this, struct _KDC_S4U_TICKET_INFO *, struct _USER_INTERNAL6_INFORMATION *, struct _KDC_TICKET_INFO *, struct _SID_AND_ATTRIBUTES_LIST *, struct KERB_EXT_ERROR *, struct KERB_KDC_REQUEST_preauth_data_s **, struct _SID_AND_ATTRIBUTES_LIST *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024ffc`

## callees

- `0x180003908`
- `0x18000b6e0`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001cdc4`
- `0x18001e8c8`
- `0x180021668`
- `0x180028b94`
- `0x180028d24`
- `0x18002b668`
- `0x18002d9c0`
- `0x18005a060`
- `0x18005a090`
- `0x180060b5c`
- `0x180072288`

## import_xrefs

- `ntdll!RtlCopySidAndAttributesArray` at `0x1800291d5`
- `ntdll!RtlCopySidAndAttributesArray` at `0x180029263`
- `ntdll!RtlCopySidAndAttributesArray` at `0x1800291d5`
- `ntdll!RtlCopySidAndAttributesArray` at `0x180029263`
- `ntdll!RtlCopySid` at `0x1800292c6`
- `ntdll!RtlCopySid` at `0x1800292c6`

## string_xrefs

- `0x180028e16`: `kdcsvc.dll`
- `0x18002904b`: `kdcsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcDmsaTgsReqWorker(
        struct _KDC_TICKET_INFO *this,
        struct _KDC_S4U_TICKET_INFO *a2,
        struct _USER_INTERNAL6_INFORMATION *a3,
        struct _KDC_TICKET_INFO *a4,
        struct _SID_AND_ATTRIBUTES_LIST *a5,
        struct KERB_EXT_ERROR *a6,
        struct KERB_KDC_REQUEST_preauth_data_s **a7,
        struct _SID_AND_ATTRIBUTES_LIST *a8)
{
  __int64 v13; // rdx
  unsigned int KeylistWithTicketInfo; // ebx
  void *v15; // rax
  unsigned __int64 v16; // xmm6_8
  unsigned __int8 IsEnabled; // al
  unsigned int TicketInfo; // eax
  char v19; // r12
  ULONG v20; // edx
  unsigned int v21; // ebx
  ULONG v22; // r14d
  struct _SID_AND_ATTRIBUTES *v23; // rax
  NTSTATUS v24; // eax
  PSID SidArea; // rax
  ULONG v26; // r8d
  NTSTATUS v27; // eax
  _DWORD *v28; // rbx
  NTSTATUS v29; // eax
  ULONG SidAreaSize[2]; // [rsp+78h] [rbp-90h] BYREF
  PSID DestinationSid; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v32[5]; // [rsp+88h] [rbp-80h] BYREF
  char v33; // [rsp+B0h] [rbp-58h]
  struct KERB_DMSA_KEY_PACKAGE_previous_keys_s *v34; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-48h] BYREF
  struct KERB_DMSA_KEY_PACKAGE_current_keys_s *v36; // [rsp+C8h] [rbp-40h] BYREF
  ULONG Count[4]; // [rsp+D0h] [rbp-38h] BYREF
  struct _UNICODE_STRING v38; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v40[48]; // [rsp+108h] [rbp+0h] BYREF
  int v41; // [rsp+138h] [rbp+30h]
  int v42; // [rsp+144h] [rbp+3Ch]
  int v43; // [rsp+159h] [rbp+51h]
  __int16 v44; // [rsp+15Dh] [rbp+55h]
  char v45; // [rsp+15Fh] [rbp+57h]
  __int16 v46; // [rsp+171h] [rbp+69h]
  char v47; // [rsp+173h] [rbp+6Bh]
  int v48; // [rsp+17Ch] [rbp+74h]
  __int64 v49; // [rsp+1A0h] [rbp+98h] BYREF
  __int128 v50; // [rsp+1A8h] [rbp+A0h]

  v39 = 0;
  v36 = 0;
  v34 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  memset_0(v40, 0, 0x98u);
  v49 = 0;
  v50 = 0;
  *(_OWORD *)Count = 0;
  v35 = 0;
  v32[0] = &v36;
  v32[1] = &v34;
  v32[2] = v40;
  v32[3] = Count;
  v32[4] = &v35;
  v33 = 1;
  if ( !_KDC_TICKET_INFO::IsLocalKrbtgt(this) )
  {
    v33 = 0;
    lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
    std::vector<unsigned int>::_Tidy((__int64)&v49);
    return 60;
  }
  v13 = *((unsigned int *)a3 + 175);
  if ( (unsigned int)(v13 - 2) <= 1 )
  {
    *((_DWORD *)a2 + 74) &= ~1u;
    KeylistWithTicketInfo = KdcParseDmsaTimeintervals(a3, (struct KdcDmsaMetadata *)&v39);
    if ( KeylistWithTicketInfo )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          118,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          KeylistWithTicketInfo);
LABEL_30:
      v33 = 0;
      lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
      goto LABEL_78;
    }
    MIDL_user_free(*((void **)a2 + 25));
    *((_QWORD *)a2 + 25) = 0;
    v15 = MIDL_user_allocate(0x48u);
    *((_QWORD *)a2 + 25) = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_17;
    }
    KdcMakeAccountSid(v15, *((_DWORD *)a3 + 68));
    KeylistWithTicketInfo = KdcGetKeylistWithTicketInfo(a4, 0, &v36);
    if ( KeylistWithTicketInfo )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          KeylistWithTicketInfo);
      goto LABEL_30;
    }
    v16 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    if ( !*(_QWORD *)((char *)a3 + 684) && v16 == *(_QWORD *)((char *)a3 + 692) )
      goto LABEL_81;
    *(_QWORD *)&v38.Length = 1048592;
    v38.Buffer = (PWSTR)((char *)a3 + 684);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl'::`2'::impl);
    TicketInfo = KdcGetTicketInfo(
                   &v38,
                   0x100u,
                   0,
                   0,
                   0,
                   (struct _KDC_TICKET_INFO *)v40,
                   a6,
                   0,
                   0,
                   IsEnabled << 29,
                   (struct _USER_INTERNAL6_INFORMATION **)((unsigned __int64)&v35 & -(__int64)(IsEnabled != 0)),
                   (struct _SID_AND_ATTRIBUTES_LIST *)Count,
                   0);
    KeylistWithTicketInfo = TicketInfo;
    if ( TicketInfo )
    {
      MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", TicketInfo, 0);
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          121,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          KeylistWithTicketInfo);
      goto LABEL_30;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl'::`2'::impl)
      && (!*(_QWORD *)(v35 + 660) && v16 == *(_QWORD *)(v35 + 668)
       || *(_QWORD *)(v35 + 660) != *((_QWORD *)a3 + 94)
       || *(_QWORD *)(v35 + 668) != *((_QWORD *)a3 + 95)) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_17;
    }
    v19 = *((_BYTE *)a3 + 704);
    v20 = *(_DWORD *)a5 + Count[0] + 1;
    *(_DWORD *)a8 = v20;
    v21 = v20;
    v22 = 544 * v20;
    v23 = (struct _SID_AND_ATTRIBUTES *)MIDL_user_allocate(560 * v20);
    *((_QWORD *)a8 + 1) = v23;
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_17;
    }
    DestinationSid = &v23[v21];
    SidAreaSize[0] = 0;
    v24 = RtlCopySidAndAttributesArray(
            *(_DWORD *)a5,
            *((PSID_AND_ATTRIBUTES *)a5 + 1),
            v22,
            v23,
            DestinationSid,
            &DestinationSid,
            SidAreaSize);
    if ( v24 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          (unsigned int)v24);
LABEL_59:
      v33 = 0;
      lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
      goto LABEL_18;
    }
    SidArea = DestinationSid;
    DestinationSid = 0;
    v26 = SidAreaSize[0];
    SidAreaSize[0] = 0;
    v27 = RtlCopySidAndAttributesArray(
            Count[0],
            *(PSID_AND_ATTRIBUTES *)&Count[2],
            v26,
            (PSID_AND_ATTRIBUTES)(*((_QWORD *)a8 + 1) + 16LL * *(unsigned int *)a5),
            SidArea,
            &DestinationSid,
            SidAreaSize);
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          (unsigned int)v27);
      goto LABEL_59;
    }
    v28 = DestinationSid;
    v29 = RtlCopySid(0x44u, DestinationSid, GlobalDomainSid);
    if ( v29 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          (unsigned int)v29);
      goto LABEL_59;
    }
    v28[(unsigned __int8)(*((_BYTE *)v28 + 1))++ + 2] = v41;
    *(_QWORD *)(*((_QWORD *)a8 + 1) + 16LL * (unsigned int)(*(_DWORD *)a8 - 1)) = v28;
    *(_DWORD *)(*((_QWORD *)a8 + 1) + 16LL * (unsigned int)(*(_DWORD *)a8 - 1) + 8) = 7;
    if ( v19 )
    {
      KeylistWithTicketInfo = KdcGetKeylistWithTicketInfo((const struct _KDC_TICKET_INFO *)v40, 0, &v34);
      if ( KeylistWithTicketInfo )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            127,
            WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
            KeylistWithTicketInfo);
        }
LABEL_76:
        v33 = 0;
        lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
        goto LABEL_78;
      }
    }
    else
    {
LABEL_81:
      if ( *((_QWORD *)a4 + 9) )
      {
        KeylistWithTicketInfo = KdcGetKeylistWithTicketInfo(a4, 1, &v34);
        if ( KeylistWithTicketInfo )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              128,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              KeylistWithTicketInfo);
          }
          goto LABEL_76;
        }
      }
    }
    KeylistWithTicketInfo = KdcDmsaBuildPreAuthData(v36, v34, (struct KdcDmsaMetadata *)&v39, a7);
    if ( !KeylistWithTicketInfo )
    {
      v33 = 0;
      lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
      KeylistWithTicketInfo = 0;
      goto LABEL_78;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        KeylistWithTicketInfo);
    goto LABEL_76;
  }
  MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", v13, 0);
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
      *((unsigned int *)a3 + 175));
LABEL_17:
  v33 = 0;
  lambda_d9762ca334ff4b8dfd0dec1f6a62e701_::operator()(v32);
LABEL_18:
  KeylistWithTicketInfo = 60;
LABEL_78:
  std::vector<unsigned int>::_Tidy((__int64)&v49);
  return KeylistWithTicketInfo;
}

```

## disassembly

```asm
0x180028d24  mov     rax, rsp
0x180028d27  push    rbp
0x180028d28  push    rbx
0x180028d29  push    rsi
0x180028d2a  push    rdi
0x180028d2b  push    r12
0x180028d2d  push    r13
0x180028d2f  push    r14
0x180028d31  push    r15
0x180028d33  lea     rbp, [rax-108h]
0x180028d3a  sub     rsp, 1C8h
0x180028d41  movaps  xmmword ptr [rax-58h], xmm6
0x180028d45  mov     r15, r9
0x180028d48  mov     rdi, r8
0x180028d4b  mov     rsi, rdx
0x180028d4e  mov     rbx, rcx
0x180028d51  xorps   xmm0, xmm0
0x180028d54  movups  [rbp+100h+var_118], xmm0
0x180028d58  xor     r13d, r13d
0x180028d5b  mov     [rbp+100h+var_140], r13
0x180028d5f  mov     [rbp+100h+var_150], r13
0x180028d63  xor     eax, eax
0x180028d65  mov     [rbp+100h+var_C4], eax
0x180028d68  mov     [rbp+100h+var_AF], eax
0x180028d6b  mov     [rbp+100h+var_AB], ax
0x180028d6f  mov     [rbp+100h+var_A9], al
0x180028d72  mov     [rbp+100h+var_97], ax
0x180028d76  mov     [rbp+100h+var_95], al
0x180028d79  mov     [rbp+100h+var_8C], eax
0x180028d7c  xor     edx, edx; Val
0x180028d7e  mov     r8d, 98h; Size
0x180028d84  lea     rcx, [rbp+100h+var_100]; void *
0x180028d88  call    memset_0
0x180028d8d  mov     [rbp+100h+var_68], r13
0x180028d94  xorps   xmm0, xmm0
0x180028d97  movdqa  xmmword ptr [rbp+0A0h], xmm0
0x180028d9f  xorps   xmm6, xmm6
0x180028da2  movups  xmmword ptr [rbp+100h+Count], xmm0
0x180028da6  mov     [rbp+100h+var_148], r13
0x180028daa  lea     rax, [rbp+100h+var_140]
0x180028dae  mov     [rbp+100h+var_180], rax
0x180028db2  lea     rax, [rbp+100h+var_150]
0x180028db6  mov     [rbp+100h+var_178], rax
0x180028dba  lea     rax, [rbp+100h+var_100]
0x180028dbe  mov     [rbp+100h+var_170], rax
0x180028dc2  lea     rax, [rbp+100h+Count]
0x180028dc6  mov     [rbp+100h+var_168], rax
0x180028dca  lea     rax, [rbp+100h+var_148]
0x180028dce  mov     [rbp+100h+var_160], rax
0x180028dd2  mov     [rbp+100h+var_158], 1
0x180028dd6  mov     rcx, rbx; this
0x180028dd9  call    ?IsLocalKrbtgt@_KDC_TICKET_INFO@@QEBA_NXZ; _KDC_TICKET_INFO::IsLocalKrbtgt(void)
0x180028dde  test    al, al
0x180028de0  jnz     short loc_180028E05
0x180028de2  mov     [rbp+100h+var_158], r13b
0x180028de6  lea     rcx, [rbp+100h+var_180]
0x180028dea  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180028def  nop
0x180028df0  lea     rcx, [rbp+100h+var_68]
0x180028df7  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180028dfc  lea     eax, [r13+3Ch]
0x180028e00  jmp     loc_180029483
0x180028e05  mov     edx, [rdi+2BCh]
0x180028e0b  lea     eax, [rdx-2]
0x180028e0e  cmp     eax, 1
0x180028e11  jbe     short loc_180028E6B
0x180028e13  xor     r8d, r8d
0x180028e16  lea     rcx, aKdcsvcDll; "kdcsvc.dll"
0x180028e1d  call    MicrosoftTelemetryAssertTriggeredArgs
0x180028e22  lea     rax, WPP_GLOBAL_Control
0x180028e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e30  cmp     rcx, rax
0x180028e33  jz      short loc_180028E58
0x180028e35  test    byte ptr [rcx+1Ch], 1
0x180028e39  jz      short loc_180028E58
0x180028e3b  mov     edx, 75h ; 'u'
0x180028e40  mov     r9d, [rdi+2BCh]
0x180028e47  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028e4e  mov     rcx, [rcx+10h]
0x180028e52  call    WPP_SF_d
0x180028e57  nop
0x180028e58  mov     [rbp+100h+var_158], r13b
0x180028e5c  lea     rcx, [rbp+100h+var_180]
0x180028e60  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180028e65  nop
0x180028e66  jmp     loc_180028F2F
0x180028e6b  and     dword ptr [rsi+128h], 0FFFFFFFEh
0x180028e72  lea     rdx, [rbp+100h+var_118]; struct KdcDmsaMetadata *
0x180028e76  mov     rcx, rdi; struct _USER_INTERNAL6_INFORMATION *
0x180028e79  call    ?KdcParseDmsaTimeintervals@@YAJAEBU_USER_INTERNAL6_INFORMATION@@AEAUKdcDmsaMetadata@@@Z; KdcParseDmsaTimeintervals(_USER_INTERNAL6_INFORMATION const &,KdcDmsaMetadata &)
0x180028e7e  mov     ebx, eax
0x180028e80  test    eax, eax
0x180028e82  jz      short loc_180028EC9
0x180028e84  lea     rax, WPP_GLOBAL_Control
0x180028e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e92  cmp     rcx, rax
0x180028e95  jz      short loc_180028EB6
0x180028e97  test    byte ptr [rcx+1Ch], 1
0x180028e9b  jz      short loc_180028EB6
0x180028e9d  mov     edx, 76h ; 'v'
0x180028ea2  mov     r9d, ebx
0x180028ea5  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028eac  mov     rcx, [rcx+10h]
0x180028eb0  call    WPP_SF_d
0x180028eb5  nop
0x180028eb6  mov     [rbp+100h+var_158], r13b
0x180028eba  lea     rcx, [rbp+100h+var_180]
0x180028ebe  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180028ec3  nop
0x180028ec4  jmp     loc_180029475
0x180028ec9  mov     rcx, [rsi+0C8h]; void *
0x180028ed0  call    MIDL_user_free
0x180028ed5  mov     [rsi+0C8h], r13
0x180028edc  mov     ecx, 48h ; 'H'; size
0x180028ee1  call    MIDL_user_allocate
0x180028ee6  mov     [rsi+0C8h], rax
0x180028eed  test    rax, rax
0x180028ef0  jnz     short loc_180028F39
0x180028ef2  lea     rax, WPP_GLOBAL_Control
0x180028ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f00  cmp     rcx, rax
0x180028f03  jz      short loc_180028F21
0x180028f05  test    byte ptr [rcx+1Ch], 1
0x180028f09  jz      short loc_180028F21
0x180028f0b  mov     edx, 77h ; 'w'
0x180028f10  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028f17  mov     rcx, [rcx+10h]
0x180028f1b  call    WPP_SF_
0x180028f20  nop
0x180028f21  mov     [rbp+100h+var_158], r13b
0x180028f25  lea     rcx, [rbp+100h+var_180]
0x180028f29  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180028f2e  nop
0x180028f2f  mov     ebx, 3Ch ; '<'
0x180028f34  jmp     loc_180029475
0x180028f39  mov     edx, [rdi+110h]; unsigned int
0x180028f3f  mov     rcx, rax; Sid
0x180028f42  call    ?KdcMakeAccountSid@@YAXPEAXK@Z; KdcMakeAccountSid(void *,ulong)
0x180028f47  lea     r8, [rbp+100h+var_140]; struct KERB_KEY_LIST_REP_s **
0x180028f4b  xor     edx, edx; bool
0x180028f4d  mov     rcx, r15; struct _KDC_TICKET_INFO *
0x180028f50  call    ?KdcGetKeylistWithTicketInfo@@YAJAEBU_KDC_TICKET_INFO@@_NAEAPEAUKERB_KEY_LIST_REP_s@@@Z; KdcGetKeylistWithTicketInfo(_KDC_TICKET_INFO const &,bool,KERB_KEY_LIST_REP_s * &)
0x180028f55  mov     ebx, eax
0x180028f57  test    eax, eax
0x180028f59  jz      short loc_180028FA0
0x180028f5b  lea     rax, WPP_GLOBAL_Control
0x180028f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f69  cmp     rcx, rax
0x180028f6c  jz      short loc_180028F8D
0x180028f6e  test    byte ptr [rcx+1Ch], 1
0x180028f72  jz      short loc_180028F8D
0x180028f74  mov     edx, 78h ; 'x'
0x180028f79  mov     r9d, ebx
0x180028f7c  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028f83  mov     rcx, [rcx+10h]
0x180028f87  call    WPP_SF_d
0x180028f8c  nop
0x180028f8d  mov     [rbp+100h+var_158], r13b
0x180028f91  lea     rcx, [rbp+100h+var_180]
0x180028f95  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180028f9a  nop
0x180028f9b  jmp     loc_180029475
0x180028fa0  lea     rax, [rdi+2ACh]
0x180028fa7  movq    r14, xmm6
0x180028fac  psrldq  xmm6, 8
0x180028fb1  movq    rsi, xmm6
0x180028fb6  cmp     r14, [rax]
0x180028fb9  jnz     short loc_180028FC5
0x180028fbb  cmp     rsi, [rax+8]
0x180028fbf  jz      loc_1800293A8
0x180028fc5  mov     qword ptr [rbp+100h+var_128.Length], 100010h
0x180028fcd  mov     [rbp+100h+var_128.Buffer], rax
0x180028fd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl(void)'::`2'::impl
0x180028fd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled(void)
0x180028fdd  movzx   edx, al
0x180028fe0  mov     al, dl
0x180028fe2  neg     al
0x180028fe4  sbb     rcx, rcx
0x180028fe7  lea     rax, [rbp+100h+var_148]
0x180028feb  and     rcx, rax
0x180028fee  shl     edx, 1Dh
0x180028ff1  mov     [rsp+60h], r13; struct _SAM_MAPPED_ATTRIBUTE_SET *
0x180028ff6  lea     rax, [rbp+100h+Count]
0x180028ffa  mov     [rsp+200h+var_1A8], rax; struct _SID_AND_ATTRIBUTES_LIST *
0x180028fff  mov     [rsp+200h+var_1B0], rcx; struct _USER_INTERNAL6_INFORMATION **
0x180029004  mov     [rsp+200h+var_1B8], edx; unsigned int
0x180029008  mov     [rsp+200h+var_1C0], r13d; unsigned int
0x18002900d  mov     [rsp+200h+var_1C8], r13; void **
0x180029012  mov     rax, [rbp+100h+arg_28]
0x180029019  mov     [rsp+200h+RemainingSidAreaSize], rax; struct KERB_EXT_ERROR *
0x18002901e  lea     rax, [rbp+100h+var_100]
0x180029022  mov     [rsp+200h+RemainingSidArea], rax; struct _KDC_TICKET_INFO *
0x180029027  mov     [rsp+200h+SidArea], r13; char **
0x18002902c  xor     r9d, r9d; struct _KERB_INTERNAL_NAME *
0x18002902f  xor     r8d, r8d; unsigned int
0x180029032  mov     edx, 100h; unsigned int
0x180029037  lea     rcx, [rbp+100h+var_128]; struct _UNICODE_STRING *
0x18002903b  call    ?KdcGetTicketInfo@@YAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z; KdcGetTicketInfo(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)
0x180029040  mov     ebx, eax
0x180029042  test    eax, eax
0x180029044  jz      short loc_18002909C
0x180029046  xor     r8d, r8d
0x180029049  mov     edx, eax
0x18002904b  lea     rcx, aKdcsvcDll; "kdcsvc.dll"
0x180029052  call    MicrosoftTelemetryAssertTriggeredArgs
0x180029057  lea     rax, WPP_GLOBAL_Control
0x18002905e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029065  cmp     rcx, rax
0x180029068  jz      short loc_180029089
0x18002906a  test    byte ptr [rcx+1Ch], 1
0x18002906e  jz      short loc_180029089
0x180029070  mov     edx, 79h ; 'y'
0x180029075  mov     r9d, ebx
0x180029078  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002907f  mov     rcx, [rcx+10h]
0x180029083  call    WPP_SF_d
0x180029088  nop
0x180029089  mov     [rbp+100h+var_158], r13b
0x18002908d  lea     rcx, [rbp+100h+var_180]
0x180029091  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x180029096  nop
0x180029097  jmp     loc_180029475
0x18002909c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink> `wil::Feature<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::GetImpl(void)'::`2'::impl
0x1800290a3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_KdcDmsaVerifyLink>::__private_IsEnabled(void)
0x1800290a8  test    al, al
0x1800290aa  jz      short loc_180029124
0x1800290ac  mov     rcx, [rbp+100h+var_148]
0x1800290b0  cmp     r14, [rcx+294h]
0x1800290b7  jnz     short loc_1800290C2
0x1800290b9  cmp     rsi, [rcx+29Ch]
0x1800290c0  jz      short loc_1800290E2
0x1800290c2  mov     rax, [rcx+294h]
0x1800290c9  cmp     rax, [rdi+2F0h]
0x1800290d0  jnz     short loc_1800290E2
0x1800290d2  mov     rax, [rcx+29Ch]
0x1800290d9  cmp     rax, [rdi+2F8h]
0x1800290e0  jz      short loc_180029124
0x1800290e2  lea     rax, WPP_GLOBAL_Control
0x1800290e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800290f0  cmp     rcx, rax
0x1800290f3  jz      short loc_180029111
0x1800290f5  test    byte ptr [rcx+1Ch], 1
0x1800290f9  jz      short loc_180029111
0x1800290fb  mov     edx, 7Ah ; 'z'
0x180029100  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029107  mov     rcx, [rcx+10h]
0x18002910b  call    WPP_SF_
0x180029110  nop
0x180029111  mov     [rbp+100h+var_158], r13b
0x180029115  lea     rcx, [rbp+100h+var_180]
0x180029119  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x18002911e  nop
0x18002911f  jmp     loc_180028F2F
0x180029124  mov     r12b, [rdi+2C0h]
0x18002912b  mov     rsi, [rbp+100h+arg_20]
0x180029132  mov     edx, [rbp+100h+Count]
0x180029135  inc     edx
0x180029137  add     edx, [rsi]
0x180029139  mov     rdi, [rbp+100h+arg_38]
0x180029140  mov     [rdi], edx
0x180029142  mov     ebx, edx
0x180029144  shl     ebx, 4
0x180029147  imul    r14d, edx, 220h
0x18002914e  lea     ecx, [r14+rbx]; size
0x180029152  call    MIDL_user_allocate
0x180029157  mov     r9, rax; Dest
0x18002915a  mov     [rdi+8], rax
0x18002915e  test    rax, rax
0x180029161  jnz     short loc_1800291A4
0x180029163  lea     rax, WPP_GLOBAL_Control
0x18002916a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029171  cmp     rcx, rax
0x180029174  jz      short loc_180029191
0x180029176  test    byte ptr [rcx+1Ch], 1
0x18002917a  jz      short loc_180029191
0x18002917c  lea     edx, [r9+7Bh]
0x180029180  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180029187  mov     rcx, [rcx+10h]
0x18002918b  call    WPP_SF_
0x180029190  nop
0x180029191  mov     [rbp+100h+var_158], r13b
0x180029195  lea     rcx, [rbp+100h+var_180]
0x180029199  call    _lambda_d9762ca334ff4b8dfd0dec1f6a62e701___operator__
0x18002919e  nop
0x18002919f  jmp     loc_180028F2F
0x1800291a4  mov     ecx, ebx
0x1800291a6  add     rcx, r9
0x1800291a9  mov     [rsp+200h+DestinationSid], rcx
0x1800291ae  mov     [rsp+200h+SidAreaSize], r13d
0x1800291b3  lea     rax, [rsp+200h+SidAreaSize]
0x1800291b8  mov     [rsp+200h+RemainingSidAreaSize], rax; RemainingSidAreaSize
0x1800291bd  lea     rax, [rsp+200h+DestinationSid]
0x1800291c2  mov     [rsp+200h+RemainingSidArea], rax; RemainingSidArea
0x1800291c7  mov     [rsp+200h+SidArea], rcx; SidArea
0x1800291cc  mov     r8d, r14d; SidAreaSize
0x1800291cf  mov     rdx, [rsi+8]; Src
0x1800291d3  mov     ecx, [rsi]; Count
0x1800291d5  call    cs:__imp_RtlCopySidAndAttributesArray
0x1800291db  mov     r9d, eax
0x1800291de  test    eax, eax
  ... truncated ...
```

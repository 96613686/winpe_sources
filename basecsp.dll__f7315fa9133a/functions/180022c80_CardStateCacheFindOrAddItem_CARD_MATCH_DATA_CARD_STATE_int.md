# CardStateCacheFindOrAddItem(_CARD_MATCH_DATA *,_CARD_STATE * *,int *)

- ea: `0x180022c80`
- end: `0x18002317b`
- name: `?CardStateCacheFindOrAddItem@@YAKPEAU_CARD_MATCH_DATA@@PEAPEAU_CARD_STATE@@PEAH@Z`
- size: `1275`
- prototype: `unsigned int __fastcall(struct _CARD_MATCH_DATA *, struct _CARD_STATE **, int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180023954`

## callees

- `0x18000a772`
- `0x18000c67c`
- `0x18000ccb0`
- `0x180016e0c`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001d470`
- `0x18001e86c`
- `0x18001ee94`
- `0x18001efd8`
- `0x18001f3a4`
- `0x180022a88`
- `0x180022c80`
- `0x1800233e4`
- `0x1800247d0`
- `0x180027c7c`
- `0x18002bf00`
- `0x18002bf84`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall CardStateCacheFindOrAddItem(struct _CARD_MATCH_DATA *a1, struct _CARD_STATE **a2, int *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int CardLookupName; // ebx
  __int64 v9; // rcx
  unsigned int v10; // r8d
  int v11; // r9d
  __int64 v12; // rcx
  unsigned int v13; // eax
  struct _CARD_STATE *v14; // rdi
  int v15; // r13d
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rcx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  char *v23; // rcx
  struct _CARD_STATE *v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+38h] [rbp-C8h]
  void **v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  void **v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v31[264]; // [rsp+60h] [rbp-A0h] BYREF

  v25 = 0;
  memset_0(v31, 0, 0x208u);
  v26 = 0;
  v27 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v29 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v28 = 0;
  v30 = 0;
  WppTraceIndent(v6, 0);
  v7 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  if ( !a2 )
  {
    CardLookupName = 87;
    goto LABEL_47;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v29, (char *)*a2 + 624);
  if ( !*((_QWORD *)*a2 + 1) )
  {
    CardLookupName = 87;
    WppTraceIndent(v9, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        v11,
        (__int64)"(*ppCardState)->pCardData");
    }
    goto LABEL_47;
  }
  *a3 = 1;
  CardLookupName = GetCardLookupName(*a2, v31, v10);
  if ( CardLookupName )
  {
    WppTraceIndent(v12, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardLookupName);
    }
    goto LABEL_47;
  }
  v13 = ScCacheGetOrAddCardState(*((_QWORD *)a1 + 2), *a2, *((_QWORD *)a1 + 3), *((_QWORD *)*a2 + 69), v31, &v25);
  v14 = v25;
  CardLookupName = v13;
  if ( v13 )
  {
    v7 = v13 + 2146434960;
    v15 = 0;
    if ( (unsigned int)v7 <= 1 )
      CardLookupName = 0;
    goto LABEL_42;
  }
  v15 = 1;
  CardLookupName = CspEnterCriticalSection((char *)v25 + 624);
  if ( CardLookupName )
  {
    WppTraceIndent(v16, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 77;
LABEL_23:
      WPP_SF_sD(
        *(_QWORD *)(v7 + 16),
        v17,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        CardLookupName);
    }
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v27, (char *)v14 + 624);
    StringCbCopyW((unsigned __int16 *)v14 + 16, 0x208u, (const unsigned __int16 *)*a2 + 16);
    if ( !*((_QWORD *)v14 + 1) )
    {
      *((_QWORD *)v14 + 1) = *((_QWORD *)*a2 + 1);
      *((_QWORD *)*a2 + 1) = 0;
      *((_DWORD *)*a2 + 155) = 0;
      *(_QWORD *)(*((_QWORD *)v14 + 1) + 80LL) = v14;
      *a3 = 0;
    }
    CardLookupName = ValidateCardHandle(v14);
    if ( v26 )
      CspRemoveCachedPin((__int64)v14, *((_DWORD *)a1 + 303), 1u);
    if ( !CardLookupName )
      goto LABEL_39;
    CardLookupName = MakeCardHandles(
                       (struct _CARD_MATCH_DATA *)((char *)a1 + 56),
                       (unsigned __int64 *)(*((_QWORD *)v14 + 1) + 96LL),
                       (unsigned __int64 *)(*((_QWORD *)v14 + 1) + 104LL));
    if ( CardLookupName )
    {
      WppTraceIndent(v18, 2u);
      v7 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, v21, (char)v14, CardLookupName);
      }
      goto LABEL_42;
    }
    CardLookupName = GetCardActivityCount(*(_QWORD *)(*((_QWORD *)v14 + 1) + 96LL));
    if ( !CardLookupName )
    {
LABEL_39:
      v23 = (char *)*a2 + 624;
      v30 = 0;
      CspLeaveCriticalSection(v23);
      v28 = 0;
      CspLeaveCriticalSection((char *)v14 + 624);
      CardStateReleaseRef(*a2, 0);
      CspEnterCriticalSection((char *)v14 + 624);
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v27, (char *)v14 + 624);
      *a2 = v14;
      goto LABEL_47;
    }
    WppTraceIndent(v22, 2u);
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 79;
      goto LABEL_23;
    }
  }
LABEL_42:
  if ( v14 )
  {
    if ( v28 )
    {
      v28 = 0;
      CspLeaveCriticalSection((char *)v14 + 624);
    }
    if ( v15 )
      CardStateReleaseRef(v14, 0);
  }
LABEL_47:
  v28 = 0;
  v30 = 0;
  WppTraceIndent(v7, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
  v29 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v29);
  v27 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v27);
  return CardLookupName;
}

```

## disassembly

```asm
0x180022c80  mov     [rsp-8+arg_18], rbx
0x180022c85  push    rbp
0x180022c86  push    rsi
0x180022c87  push    rdi
0x180022c88  push    r12
0x180022c8a  push    r13
0x180022c8c  push    r14
0x180022c8e  push    r15
0x180022c90  lea     rbp, [rsp-180h]
0x180022c98  sub     rsp, 280h
0x180022c9f  mov     rax, cs:__security_cookie
0x180022ca6  xor     rax, rsp
0x180022ca9  mov     [rbp+1B0h+var_40], rax
0x180022cb0  mov     r12, r8
0x180022cb3  mov     [rsp+2B0h+var_280], 0
0x180022cbc  mov     rsi, rdx
0x180022cbf  mov     r15, rcx
0x180022cc2  xor     edx, edx; Val
0x180022cc4  lea     rcx, [rsp+2B0h+var_250]; void *
0x180022cc9  mov     r8d, 208h; Size
0x180022ccf  call    memset_0
0x180022cd4  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180022cdb  mov     [rsp+2B0h+var_278], 0
0x180022ce3  xor     edx, edx
0x180022ce5  mov     [rsp+2B0h+var_270], rdi
0x180022cea  mov     [rsp+2B0h+var_260], rdi
0x180022cef  mov     [rsp+2B0h+var_268], 0
0x180022cf8  mov     [rsp+2B0h+var_258], 0
0x180022d01  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d0d  lea     rax, WPP_GLOBAL_Control
0x180022d14  mov     r14d, 2
0x180022d1a  cmp     rcx, rax
0x180022d1d  jz      short loc_180022D46
0x180022d1f  test    [rcx+1Ch], r14b
0x180022d23  jz      short loc_180022D46
0x180022d25  cmp     byte ptr [rcx+19h], 5
0x180022d29  jb      short loc_180022D46
0x180022d2b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022d32  lea     edx, [r14+48h]
0x180022d36  mov     rcx, [rcx+10h]
0x180022d3a  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180022d41  call    WPP_SF_s
0x180022d46  test    rsi, rsi
0x180022d49  jnz     short loc_180022D5A
0x180022d4b  lea     ebx, [rsi+57h]
0x180022d4e  lea     rsi, WPP_GLOBAL_Control
0x180022d55  jmp     loc_1800230DD
0x180022d5a  mov     rdx, [rsi]
0x180022d5d  lea     rcx, [rsp+2B0h+var_260]
0x180022d62  add     rdx, 270h
0x180022d69  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180022d6e  mov     rax, [rsi]
0x180022d71  cmp     qword ptr [rax+8], 0
0x180022d76  jnz     short loc_180022DD4
0x180022d78  mov     edx, r14d
0x180022d7b  mov     ebx, 57h ; 'W'
0x180022d80  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d8c  lea     rsi, WPP_GLOBAL_Control
0x180022d93  cmp     rcx, rsi
0x180022d96  jz      loc_1800230DD
0x180022d9c  test    byte ptr [rcx+1Ch], 1
0x180022da0  jz      loc_1800230DD
0x180022da6  cmp     [rcx+19h], r14b
0x180022daa  jb      loc_1800230DD
0x180022db0  mov     rcx, [rcx+10h]
0x180022db4  lea     rax, aPpcardstatePca; "(*ppCardState)->pCardData"
0x180022dbb  lea     edx, [rbx-0Ch]
0x180022dbe  mov     [rsp+2B0h+var_290], rax
0x180022dc3  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180022dca  call    WPP_SF_ss
0x180022dcf  jmp     loc_1800230DD
0x180022dd4  mov     dword ptr [r12], 1
0x180022ddc  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180022de1  mov     rcx, [rsi]; struct _CARD_STATE *
0x180022de4  call    ?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z; GetCardLookupName(_CARD_STATE *,ushort *,ulong)
0x180022de9  mov     ebx, eax
0x180022deb  test    eax, eax
0x180022ded  jz      short loc_180022E47
0x180022def  mov     edx, r14d
0x180022df2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dfe  lea     rsi, WPP_GLOBAL_Control
0x180022e05  cmp     rcx, rsi
0x180022e08  jz      loc_1800230DD
0x180022e0e  test    byte ptr [rcx+1Ch], 1
0x180022e12  jz      loc_1800230DD
0x180022e18  cmp     [rcx+19h], r14b
0x180022e1c  jb      loc_1800230DD
0x180022e22  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022e29  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180022e30  mov     rcx, [rcx+10h]
0x180022e34  mov     edx, 4Ch ; 'L'
0x180022e39  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180022e3d  call    WPP_SF_sD
0x180022e42  jmp     loc_1800230DD
0x180022e47  mov     rdx, [rsi]
0x180022e4a  lea     rax, [rsp+2B0h+var_280]
0x180022e4f  mov     r8, [r15+18h]
0x180022e53  mov     rcx, [r15+10h]
0x180022e57  mov     [rsp+2B0h+var_288], rax
0x180022e5c  lea     rax, [rsp+2B0h+var_250]
0x180022e61  mov     r9, [rdx+228h]
0x180022e68  mov     [rsp+2B0h+var_290], rax
0x180022e6d  call    ScCacheGetOrAddCardState
0x180022e72  mov     rdi, [rsp+2B0h+var_280]
0x180022e77  mov     ebx, eax
0x180022e79  test    eax, eax
0x180022e7b  jnz     loc_18002308D
0x180022e81  lea     r14, [rdi+270h]
0x180022e88  mov     rcx, r14
0x180022e8b  lea     r13d, [rax+1]
0x180022e8f  call    CspEnterCriticalSection
0x180022e94  mov     ebx, eax
0x180022e96  test    eax, eax
0x180022e98  jz      short loc_180022EF5
0x180022e9a  lea     r14d, [r13+1]
0x180022e9e  mov     edx, r14d
0x180022ea1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ead  lea     rsi, WPP_GLOBAL_Control
0x180022eb4  cmp     rcx, rsi
0x180022eb7  jz      loc_1800230A5
0x180022ebd  test    [rcx+1Ch], r13b
0x180022ec1  jz      loc_1800230A5
0x180022ec7  cmp     [rcx+19h], r14b
0x180022ecb  jb      loc_1800230A5
0x180022ed1  lea     edx, [r13+4Ch]
0x180022ed5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022edc  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180022ee3  mov     rcx, [rcx+10h]
0x180022ee7  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180022eeb  call    WPP_SF_sD
0x180022ef0  jmp     loc_1800230A5
0x180022ef5  mov     rdx, r14
0x180022ef8  lea     rcx, [rsp+2B0h+var_270]
0x180022efd  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180022f02  mov     r8, [rsi]
0x180022f05  lea     rcx, [rdi+20h]; unsigned __int16 *
0x180022f09  add     r8, 20h ; ' '; unsigned __int16 *
0x180022f0d  mov     edx, 208h; unsigned __int64
0x180022f12  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180022f17  xor     edx, edx
0x180022f19  cmp     [rdi+8], rdx
0x180022f1d  jnz     short loc_180022F46
0x180022f1f  mov     rax, [rsi]
0x180022f22  mov     rcx, [rax+8]
0x180022f26  mov     [rdi+8], rcx
0x180022f2a  mov     rax, [rsi]
0x180022f2d  mov     [rax+8], rdx
0x180022f31  mov     rax, [rsi]
0x180022f34  mov     [rax+26Ch], edx
0x180022f3a  mov     rax, [rdi+8]
0x180022f3e  mov     [rax+50h], rdi
0x180022f42  mov     [r12], edx
0x180022f46  lea     r8, [rsp+2B0h+var_278]
0x180022f4b  mov     rcx, rdi; struct _CARD_STATE *
0x180022f4e  call    ValidateCardHandle
0x180022f53  cmp     [rsp+2B0h+var_278], 0
0x180022f58  mov     ebx, eax
0x180022f5a  jz      short loc_180022F6E
0x180022f5c  mov     edx, [r15+4BCh]
0x180022f63  mov     r8d, r13d
0x180022f66  mov     rcx, rdi
0x180022f69  call    CspRemoveCachedPin
0x180022f6e  test    ebx, ebx
0x180022f70  jz      loc_180023039
0x180022f76  mov     rdx, [rdi+8]
0x180022f7a  lea     rcx, [r15+38h]; struct _CARD_DATA_INFO *
0x180022f7e  lea     r8, [rdx+68h]; unsigned __int64 *
0x180022f82  add     rdx, 60h ; '`'; unsigned __int64 *
0x180022f86  call    ?MakeCardHandles@@YAKPEAU_CARD_DATA_INFO@@PEA_K1@Z; MakeCardHandles(_CARD_DATA_INFO *,unsigned __int64 *,unsigned __int64 *)
0x180022f8b  mov     ebx, eax
0x180022f8d  test    eax, eax
0x180022f8f  jz      short loc_180022FE1
0x180022f91  mov     r14d, 2
0x180022f97  mov     edx, r14d
0x180022f9a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022fa6  lea     rsi, WPP_GLOBAL_Control
0x180022fad  cmp     rcx, rsi
0x180022fb0  jz      loc_1800230A5
0x180022fb6  test    [rcx+1Ch], r13b
0x180022fba  jz      loc_1800230A5
0x180022fc0  cmp     [rcx+19h], r14b
0x180022fc4  jb      loc_1800230A5
0x180022fca  mov     rcx, [rcx+10h]
0x180022fce  mov     dword ptr [rsp+2B0h+var_288], ebx
0x180022fd2  mov     [rsp+2B0h+var_290], rdi
0x180022fd7  call    WPP_SF_sqD
0x180022fdc  jmp     loc_1800230A5
0x180022fe1  mov     rcx, [rdi+8]
0x180022fe5  lea     r8, [rdi+2C0h]
0x180022fec  lea     rdx, [rdi+20h]
0x180022ff0  mov     rcx, [rcx+60h]; hContext
0x180022ff4  call    GetCardActivityCount
0x180022ff9  mov     ebx, eax
0x180022ffb  test    eax, eax
0x180022ffd  jz      short loc_180023039
0x180022fff  mov     r14d, 2
0x180023005  mov     edx, r14d
0x180023008  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002300d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023014  lea     rsi, WPP_GLOBAL_Control
0x18002301b  cmp     rcx, rsi
0x18002301e  jz      loc_1800230A5
0x180023024  test    [rcx+1Ch], r13b
0x180023028  jz      short loc_1800230A5
0x18002302a  cmp     [rcx+19h], r14b
0x18002302e  jb      short loc_1800230A5
0x180023030  lea     edx, [r14+4Dh]
0x180023034  jmp     loc_180022ED5
0x180023039  mov     rcx, [rsi]
0x18002303c  add     rcx, 270h
0x180023043  mov     [rsp+2B0h+var_258], 0
0x18002304c  call    CspLeaveCriticalSection
0x180023051  mov     rcx, r14
0x180023054  mov     [rsp+2B0h+var_268], 0
0x18002305d  call    CspLeaveCriticalSection
0x180023062  mov     rcx, [rsi]
0x180023065  xor     edx, edx
0x180023067  call    CardStateReleaseRef
0x18002306c  mov     rcx, r14
0x18002306f  call    CspEnterCriticalSection
0x180023074  mov     rdx, r14
0x180023077  lea     rcx, [rsp+2B0h+var_270]
0x18002307c  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180023081  mov     [rsi], rdi
0x180023084  lea     rsi, WPP_GLOBAL_Control
0x18002308b  jmp     short loc_1800230D6
0x18002308d  lea     ecx, [rax+7FEFFF90h]
0x180023093  xor     r13d, r13d
0x180023096  xor     eax, eax
0x180023098  lea     rsi, WPP_GLOBAL_Control
0x18002309f  cmp     ecx, 1
0x1800230a2  cmovbe  ebx, eax
0x1800230a5  test    rdi, rdi
0x1800230a8  jz      short loc_1800230D6
0x1800230aa  cmp     [rsp+2B0h+var_268], 0
0x1800230b0  jz      short loc_1800230C7
0x1800230b2  lea     rcx, [rdi+270h]
0x1800230b9  mov     [rsp+2B0h+var_268], 0
0x1800230c2  call    CspLeaveCriticalSection
0x1800230c7  test    r13d, r13d
0x1800230ca  jz      short loc_1800230D6
0x1800230cc  xor     edx, edx
0x1800230ce  mov     rcx, rdi
0x1800230d1  call    CardStateReleaseRef
0x1800230d6  lea     rdi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800230dd  mov     edx, 1
0x1800230e2  mov     [rsp+2B0h+var_268], 0
0x1800230eb  mov     [rsp+2B0h+var_258], 0
0x1800230f4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800230f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023100  cmp     rcx, rsi
0x180023103  jz      short loc_180023131
0x180023105  test    byte ptr [rcx+1Ch], 2
0x180023109  jz      short loc_180023131
0x18002310b  cmp     byte ptr [rcx+19h], 5
0x18002310f  jb      short loc_180023131
0x180023111  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023118  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18002311f  mov     rcx, [rcx+10h]
0x180023123  mov     edx, 50h ; 'P'
0x180023128  mov     dword ptr [rsp+2B0h+var_290], ebx
0x18002312c  call    WPP_SF_sD
0x180023131  lea     rcx, [rsp+2B0h+var_260]
0x180023136  mov     [rsp+2B0h+var_260], rdi
0x18002313b  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180023140  lea     rcx, [rsp+2B0h+var_270]
0x180023145  mov     [rsp+2B0h+var_270], rdi
0x18002314a  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18002314f  mov     eax, ebx
0x180023151  mov     rcx, [rbp+1B0h+var_40]
0x180023158  xor     rcx, rsp; StackCookie
0x18002315b  call    __security_check_cookie
0x180023160  mov     rbx, [rsp+2B0h+arg_18]
0x180023168  add     rsp, 280h
0x18002316f  pop     r15
0x180023171  pop     r14
0x180023173  pop     r13
0x180023175  pop     r12
0x180023177  pop     rdi
0x180023178  pop     rsi
0x180023179  pop     rbp
0x18002317a  retn
```

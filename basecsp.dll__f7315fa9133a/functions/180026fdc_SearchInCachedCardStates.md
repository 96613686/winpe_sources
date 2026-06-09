# SearchInCachedCardStates

- ea: `0x180026fdc`
- end: `0x180027422`
- name: `SearchInCachedCardStates`
- size: `1094`
- prototype: `__int64 __fastcall(struct _CARD_MATCH_DATA *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180026728`

## callees

- `0x18000ccb0`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001e86c`
- `0x18001efd8`
- `0x180022888`
- `0x1800229ac`
- `0x180023d3c`
- `0x180024978`
- `0x180024fd0`
- `0x180025880`
- `0x180025c8c`
- `0x180026fdc`
- `0x180027b70`
- `0x18002bf00`
- `0x18002c788`
- `0x18002c858`

## pseudocode

```c
__int64 __fastcall SearchInCachedCardStates(struct _CARD_MATCH_DATA *a1, _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned int SessionID; // ebx
  _QWORD *v5; // rcx
  int v6; // edx
  __int64 v7; // rcx
  unsigned int v8; // r15d
  unsigned int v9; // eax
  void **v10; // r13
  unsigned int i; // r12d
  __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned __int16 *v14; // rcx
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rcx
  int v19; // edx
  __int64 v20; // rcx
  __int64 v21; // rcx
  union _LARGE_INTEGER v23; // [rsp+38h] [rbp-18h] BYREF
  void **v24; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+48h] [rbp-8h]
  unsigned int TokenInformation; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+58h] BYREF

  TokenInformation = 0;
  v23.QuadPart = 0;
  v28 = 0;
  v24 = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  SessionID = GetSessionID(&TokenInformation, &v23);
  if ( SessionID )
  {
    WppTraceIndent(v3, 2u);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 121;
LABEL_10:
      WPP_SF_sD(
        v5[2],
        v6,
        (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
        (_DWORD)WPP_pszIndent,
        SessionID);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  SessionID = RemoveStaleCardStatesFromCache(
                *((_QWORD *)a1 + 3),
                *((struct _RTL_CRITICAL_SECTION **)a1 + 2),
                TokenInformation,
                v23);
  if ( !SessionID )
  {
    v8 = 1168;
    v9 = ScCacheEnumCardStates(*((_QWORD *)a1 + 2), *((_QWORD *)a1 + 3), &v24, &v28);
    v10 = v24;
    SessionID = v9;
    if ( v9 )
    {
LABEL_51:
      if ( v10 )
        ScCacheFreeEnumCardStates(*((_QWORD *)a1 + 3), v10, v28);
      if ( v8 && !SessionID )
        SessionID = v8;
      goto LABEL_56;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= v28 || !v8 )
        goto LABEL_51;
      v12 = *(_QWORD *)v10[2 * i + 1];
      if ( TokenInformation == *(_DWORD *)(v12 + 716) )
        break;
LABEL_46:
      ;
    }
    SessionID = CspEnterCriticalSection(v12 + 624);
    if ( SessionID )
    {
      WppTraceIndent(v13, 2u);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          123,
          (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          (_DWORD)WPP_pszIndent,
          SessionID);
      }
      goto LABEL_51;
    }
    v14 = (unsigned __int16 *)*((_QWORD *)a1 + 145);
    v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    v25 = v12 + 624;
    if ( (unsigned int)MatchesRequiredReaderName(v14, (unsigned __int16 *)(v12 + 32))
      && (unsigned int)MatchesRequiredContainerNameInKnownContainers(
                         *((unsigned __int16 **)a1 + 146),
                         *(struct _CONTAINER_MAP_RECORD **)(v12 + 568),
                         *(_DWORD *)(v12 + 576)) )
    {
      if ( *(_QWORD *)(v12 + 8) )
        SessionID = ValidateCardHandle((struct _CARD_STATE *)v12);
      if ( !SessionID )
      {
        SessionID = TransactionManagerBegin((struct _CARD_STATE *)v12);
        if ( SessionID )
        {
          WppTraceIndent(v15, 2u);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_45;
          }
          v19 = 124;
          goto LABEL_32;
        }
        v8 = MatchBySerialAndUserParameters(a1, (struct _CARD_STATE *)v12);
        if ( v8 )
        {
          WppTraceIndent(v20, 2u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
              (_DWORD)WPP_pszIndent,
              v8);
          }
          SessionID = TransactionManagerEnd((struct _CARD_STATE *)v12);
          if ( !SessionID )
            goto LABEL_45;
          WppTraceIndent(v21, 2u);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_45;
          }
          v19 = 126;
LABEL_32:
          WPP_SF_sDq(v18[2], v19, v16, v17, SessionID, v12);
          goto LABEL_45;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 692));
        v25 = 0;
        *a2 = v12;
      }
    }
LABEL_45:
    v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
    goto LABEL_46;
  }
  WppTraceIndent(v7, 2u);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 122;
    goto LABEL_10;
  }
LABEL_56:
  WppTraceIndent((__int64)v5, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      127,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      SessionID);
  }
  return SessionID;
}

```

## disassembly

```asm
0x180026fdc  mov     [rsp-38h+arg_0], rbx
0x180026fe1  mov     [rsp-38h+arg_8], rdx
0x180026fe6  push    rbp
0x180026fe7  push    rsi
0x180026fe8  push    rdi
0x180026fe9  push    r12
0x180026feb  push    r13
0x180026fed  push    r14
0x180026fef  push    r15
0x180026ff1  mov     rbp, rsp
0x180026ff4  sub     rsp, 50h
0x180026ff8  xor     edx, edx
0x180026ffa  mov     [rbp+TokenInformation], 0
0x180027001  mov     r14, rcx
0x180027004  mov     qword ptr [rbp+var_18], 0
0x18002700c  mov     [rbp+arg_18], 0
0x180027013  mov     [rbp+var_10], 0
0x18002701b  mov     [rbp+var_20], 0
0x180027022  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027027  mov     rcx, cs:WPP_GLOBAL_Control
0x18002702e  lea     rsi, WPP_GLOBAL_Control
0x180027035  cmp     rcx, rsi
0x180027038  jz      short loc_180027062
0x18002703a  test    byte ptr [rcx+1Ch], 2
0x18002703e  jz      short loc_180027062
0x180027040  cmp     byte ptr [rcx+19h], 5
0x180027044  jb      short loc_180027062
0x180027046  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002704d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180027054  mov     rcx, [rcx+10h]
0x180027058  mov     edx, 78h ; 'x'
0x18002705d  call    WPP_SF_s
0x180027062  lea     rdx, [rbp+var_18]; union _LARGE_INTEGER *
0x180027066  lea     rcx, [rbp+TokenInformation]; TokenInformation
0x18002706a  call    ?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z; GetSessionID(ulong *,_LARGE_INTEGER *)
0x18002706f  mov     ebx, eax
0x180027071  test    eax, eax
0x180027073  jz      short loc_1800270C8
0x180027075  mov     edx, 2
0x18002707a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002707f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027086  cmp     rcx, rsi
0x180027089  jz      loc_1800273C6
0x18002708f  test    byte ptr [rcx+1Ch], 1
0x180027093  jz      loc_1800273C6
0x180027099  cmp     byte ptr [rcx+19h], 2
0x18002709d  jb      loc_1800273C6
0x1800270a3  mov     edx, 79h ; 'y'
0x1800270a8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800270af  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800270b6  mov     rcx, [rcx+10h]
0x1800270ba  mov     [rsp+50h+var_30], ebx
0x1800270be  call    WPP_SF_sD
0x1800270c3  jmp     loc_1800273C6
0x1800270c8  mov     r9, qword ptr [rbp+var_18]; union _LARGE_INTEGER
0x1800270cc  mov     r8d, [rbp+TokenInformation]; unsigned int
0x1800270d0  mov     rdx, [r14+10h]; struct _RTL_CRITICAL_SECTION *
0x1800270d4  mov     rcx, [r14+18h]; unsigned __int64
0x1800270d8  call    ?RemoveStaleCardStatesFromCache@@YAK_KPEAU_RTL_CRITICAL_SECTION@@KT_LARGE_INTEGER@@@Z; RemoveStaleCardStatesFromCache(unsigned __int64,_RTL_CRITICAL_SECTION *,ulong,_LARGE_INTEGER)
0x1800270dd  mov     ebx, eax
0x1800270df  test    eax, eax
0x1800270e1  jz      short loc_180027118
0x1800270e3  mov     edx, 2
0x1800270e8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800270ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270f4  cmp     rcx, rsi
0x1800270f7  jz      loc_1800273C6
0x1800270fd  test    byte ptr [rcx+1Ch], 1
0x180027101  jz      loc_1800273C6
0x180027107  cmp     byte ptr [rcx+19h], 2
0x18002710b  jb      loc_1800273C6
0x180027111  mov     edx, 7Ah ; 'z'
0x180027116  jmp     short loc_1800270A8
0x180027118  mov     rdx, [r14+18h]
0x18002711c  lea     r9, [rbp+arg_18]
0x180027120  mov     rcx, [r14+10h]
0x180027124  lea     r8, [rbp+var_10]
0x180027128  mov     r15d, 490h
0x18002712e  call    ScCacheEnumCardStates
0x180027133  mov     r13, [rbp+var_10]
0x180027137  mov     ebx, eax
0x180027139  test    eax, eax
0x18002713b  jnz     loc_1800273A6
0x180027141  xor     r12d, r12d
0x180027144  cmp     r12d, [rbp+arg_18]
0x180027148  jnb     loc_1800273A6
0x18002714e  test    r15d, r15d
0x180027151  jz      loc_1800273A6
0x180027157  mov     eax, r12d
0x18002715a  add     rax, rax
0x18002715d  mov     rax, [r13+rax*8+8]
0x180027162  mov     rdi, [rax]
0x180027165  mov     eax, [rdi+2CCh]
0x18002716b  cmp     [rbp+TokenInformation], eax
0x18002716e  jnz     loc_180027355
0x180027174  lea     rsi, [rdi+270h]
0x18002717b  mov     rcx, rsi
0x18002717e  call    CspEnterCriticalSection
0x180027183  mov     ebx, eax
0x180027185  test    eax, eax
0x180027187  jnz     loc_18002735D
0x18002718d  mov     rcx, [r14+488h]; unsigned __int16 *
0x180027194  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002719b  lea     rdx, [rdi+20h]; unsigned __int16 *
0x18002719f  mov     [rbp+var_10], rax
0x1800271a3  mov     [rbp+var_8], rsi
0x1800271a7  call    ?MatchesRequiredReaderName@@YAHPEAG0@Z; MatchesRequiredReaderName(ushort *,ushort *)
0x1800271ac  test    eax, eax
0x1800271ae  jz      loc_18002733A
0x1800271b4  mov     r8d, [rdi+240h]; unsigned int
0x1800271bb  mov     rdx, [rdi+238h]; struct _CONTAINER_MAP_RECORD *
0x1800271c2  mov     rcx, [r14+490h]; Buf1
0x1800271c9  call    ?MatchesRequiredContainerNameInKnownContainers@@YAHPEAGPEAU_CONTAINER_MAP_RECORD@@K@Z; MatchesRequiredContainerNameInKnownContainers(ushort *,_CONTAINER_MAP_RECORD *,ulong)
0x1800271ce  test    eax, eax
0x1800271d0  jz      loc_18002733A
0x1800271d6  cmp     qword ptr [rdi+8], 0
0x1800271db  jz      short loc_1800271EB
0x1800271dd  lea     r8, [rbp+var_20]
0x1800271e1  mov     rcx, rdi; struct _CARD_STATE *
0x1800271e4  call    ValidateCardHandle
0x1800271e9  mov     ebx, eax
0x1800271eb  cmp     [rbp+var_20], 1
0x1800271ef  jnz     short loc_18002720B
0x1800271f1  cmp     qword ptr [rdi+248h], 0
0x1800271f9  jz      short loc_18002720B
0x1800271fb  mov     edx, 1
0x180027200  mov     rcx, rdi
0x180027203  mov     r8d, edx
0x180027206  call    CspRemoveCachedPin
0x18002720b  test    ebx, ebx
0x18002720d  jnz     loc_18002733A
0x180027213  mov     rcx, rdi; struct _CARD_STATE *
0x180027216  call    TransactionManagerBegin
0x18002721b  mov     ebx, eax
0x18002721d  test    eax, eax
0x18002721f  jz      short loc_18002727A
0x180027221  mov     edx, 2
0x180027226  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002722b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027232  lea     rsi, WPP_GLOBAL_Control
0x180027239  cmp     rcx, rsi
0x18002723c  jz      short loc_180027261
0x18002723e  test    byte ptr [rcx+1Ch], 1
0x180027242  jz      short loc_180027261
0x180027244  cmp     byte ptr [rcx+19h], 4
0x180027248  jb      short loc_180027261
0x18002724a  mov     edx, 7Ch ; '|'
0x18002724f  mov     rcx, [rcx+10h]
0x180027253  mov     [rsp+50h+var_28], rdi
0x180027258  mov     [rsp+50h+var_30], ebx
0x18002725c  call    WPP_SF_sDq
0x180027261  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180027268  lea     rcx, [rbp+var_10]
0x18002726c  mov     [rbp+var_10], rax
0x180027270  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180027275  jmp     loc_180027355
0x18002727a  mov     rdx, rdi; struct _CARD_STATE *
0x18002727d  mov     rcx, r14; struct _CARD_MATCH_DATA *
0x180027280  call    ?MatchBySerialAndUserParameters@@YAKPEAU_CARD_MATCH_DATA@@PEAU_CARD_STATE@@@Z; MatchBySerialAndUserParameters(_CARD_MATCH_DATA *,_CARD_STATE *)
0x180027285  mov     r15d, eax
0x180027288  test    eax, eax
0x18002728a  jz      loc_180027324
0x180027290  mov     edx, 2
0x180027295  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002729a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272a1  lea     rsi, WPP_GLOBAL_Control
0x1800272a8  cmp     rcx, rsi
0x1800272ab  jz      short loc_1800272DA
0x1800272ad  test    byte ptr [rcx+1Ch], 1
0x1800272b1  jz      short loc_1800272DA
0x1800272b3  cmp     byte ptr [rcx+19h], 4
0x1800272b7  jb      short loc_1800272DA
0x1800272b9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800272c0  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800272c7  mov     rcx, [rcx+10h]
0x1800272cb  mov     edx, 7Dh ; '}'
0x1800272d0  mov     [rsp+50h+var_30], r15d
0x1800272d5  call    WPP_SF_sD
0x1800272da  mov     rcx, rdi; struct _CARD_STATE *
0x1800272dd  call    TransactionManagerEnd
0x1800272e2  mov     ebx, eax
0x1800272e4  test    eax, eax
0x1800272e6  jz      loc_180027261
0x1800272ec  mov     edx, 2
0x1800272f1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800272f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272fd  cmp     rcx, rsi
0x180027300  jz      loc_180027261
0x180027306  test    byte ptr [rcx+1Ch], 1
0x18002730a  jz      loc_180027261
0x180027310  cmp     byte ptr [rcx+19h], 4
0x180027314  jb      loc_180027261
0x18002731a  mov     edx, 7Eh ; '~'
0x18002731f  jmp     loc_18002724F
0x180027324  lock inc dword ptr [rdi+2B4h]
0x18002732b  mov     rax, [rbp+arg_8]
0x18002732f  mov     [rbp+var_8], 0
0x180027337  mov     [rax], rdi
0x18002733a  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180027341  lea     rcx, [rbp+var_10]
0x180027345  mov     [rbp+var_10], rax
0x180027349  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18002734e  lea     rsi, WPP_GLOBAL_Control
0x180027355  inc     r12d
0x180027358  jmp     loc_180027144
0x18002735d  mov     edx, 2
0x180027362  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027367  mov     rcx, cs:WPP_GLOBAL_Control
0x18002736e  lea     rsi, WPP_GLOBAL_Control
0x180027375  cmp     rcx, rsi
0x180027378  jz      short loc_1800273A6
0x18002737a  test    byte ptr [rcx+1Ch], 1
0x18002737e  jz      short loc_1800273A6
0x180027380  cmp     byte ptr [rcx+19h], 2
0x180027384  jb      short loc_1800273A6
0x180027386  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002738d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180027394  mov     rcx, [rcx+10h]
0x180027398  mov     edx, 7Bh ; '{'
0x18002739d  mov     [rsp+50h+var_30], ebx
0x1800273a1  call    WPP_SF_sD
0x1800273a6  test    r13, r13
0x1800273a9  jz      short loc_1800273BB
0x1800273ab  mov     r8d, [rbp+arg_18]
0x1800273af  mov     rdx, r13
0x1800273b2  mov     rcx, [r14+18h]
0x1800273b6  call    ScCacheFreeEnumCardStates
0x1800273bb  test    r15d, r15d
0x1800273be  jz      short loc_1800273C6
0x1800273c0  test    ebx, ebx
0x1800273c2  cmovz   ebx, r15d
0x1800273c6  mov     edx, 1
0x1800273cb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800273d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273d7  cmp     rcx, rsi
0x1800273da  jz      short loc_180027408
0x1800273dc  test    byte ptr [rcx+1Ch], 2
0x1800273e0  jz      short loc_180027408
0x1800273e2  cmp     byte ptr [rcx+19h], 5
0x1800273e6  jb      short loc_180027408
0x1800273e8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800273ef  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800273f6  mov     rcx, [rcx+10h]
0x1800273fa  mov     edx, 7Fh
0x1800273ff  mov     [rsp+50h+var_30], ebx
0x180027403  call    WPP_SF_sD
0x180027408  mov     eax, ebx
0x18002740a  mov     rbx, [rsp+50h+arg_0]
0x180027412  add     rsp, 50h
0x180027416  pop     r15
0x180027418  pop     r14
0x18002741a  pop     r13
0x18002741c  pop     r12
0x18002741e  pop     rdi
0x18002741f  pop     rsi
0x180027420  pop     rbp
0x180027421  retn
```

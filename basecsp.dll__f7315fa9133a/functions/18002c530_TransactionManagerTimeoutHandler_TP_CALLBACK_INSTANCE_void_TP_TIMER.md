# TransactionManagerTimeoutHandler(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18002c530`
- end: `0x18002c782`
- name: `?TransactionManagerTimeoutHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `594`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c67c`
- `0x18000ccb0`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001f3a4`
- `0x18002bf00`
- `0x18002bf84`
- `0x18002c530`
- `0x18002c920`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c5ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c5ab`
- `WinSCard!SCardDisconnect` at `0x18002c6da`
- `WinSCard!SCardDisconnect` at `0x18002c6da`

## pseudocode

```c
void __fastcall TransactionManagerTimeoutHandler(__int64 Instance, struct _CARD_STATE *Context, PTP_TIMER Timer)
{
  __int64 v5; // rcx
  int v6; // r9d
  char *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  char v11; // si
  __int64 v12; // rax
  SCARDHANDLE v13; // rsi
  bool v14; // zf
  LONG v15; // eax
  PVOID v16; // rcx
  char v17; // bl
  void **v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h]

  v19 = 0;
  v18 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  WppTraceIndent(Instance, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  SetThreadpoolTimer(Timer, 0, 0, 0);
  if ( *((_QWORD *)Context + 1) )
  {
    v7 = (char *)Context + 624;
    if ( (unsigned int)CspEnterCriticalSection((char *)Context + 624) )
    {
      WppTraceIndent(v8, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
          WPP_pszIndent);
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v18, (char *)Context + 624);
      v9 = TransactionManagerForceEndTransaction(Context);
      v11 = v9;
      if ( v9 )
      {
        WppTraceIndent(v10, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
            (_DWORD)WPP_pszIndent,
            v11);
        }
      }
    }
  }
  else
  {
    WppTraceIndent(v5, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        v6,
        (__int64)"pCardState->pCardData");
    }
    v7 = (char *)Context + 624;
  }
  v12 = *((_QWORD *)Context + 1);
  v13 = *(_QWORD *)(v12 + 104);
  *(_QWORD *)(v12 + 104) = 0;
  v14 = v19 == 0;
  *((_DWORD *)Context + 172) = 1;
  if ( !v14 )
  {
    v19 = 0;
    CspLeaveCriticalSection(v7);
  }
  v15 = SCardDisconnect(v13, 0);
  v17 = v15;
  if ( v15 )
  {
    WppTraceIndent((__int64)v16, 2u);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
        (_DWORD)WPP_pszIndent,
        v17);
    }
  }
  WppTraceIndent((__int64)v16, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      v17);
  }
  v18 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v18);
}

```

## disassembly

```asm
0x18002c530  push    rbx
0x18002c532  push    rbp
0x18002c533  push    rsi
0x18002c534  push    rdi
0x18002c535  push    r12
0x18002c537  push    r13
0x18002c539  sub     rsp, 48h
0x18002c53d  mov     rdi, rdx
0x18002c540  mov     [rsp+78h+var_40], 0
0x18002c549  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002c550  xor     edx, edx
0x18002c552  mov     [rsp+78h+var_48], rax
0x18002c557  mov     rbx, r8
0x18002c55a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c566  lea     r12, WPP_GLOBAL_Control
0x18002c56d  lea     r13, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002c574  mov     ebp, 2
0x18002c579  cmp     rcx, r12
0x18002c57c  jz      short loc_18002C5A0
0x18002c57e  test    [rcx+1Ch], bpl
0x18002c582  jz      short loc_18002C5A0
0x18002c584  cmp     byte ptr [rcx+19h], 5
0x18002c588  jb      short loc_18002C5A0
0x18002c58a  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c591  lea     edx, [rbp+14h]
0x18002c594  mov     rcx, [rcx+10h]
0x18002c598  mov     r8, r13
0x18002c59b  call    WPP_SF_s
0x18002c5a0  xor     r9d, r9d; msWindowLength
0x18002c5a3  xor     r8d, r8d; msPeriod
0x18002c5a6  xor     edx, edx; pftDueTime
0x18002c5a8  mov     rcx, rbx; pti
0x18002c5ab  call    cs:__imp_SetThreadpoolTimer
0x18002c5b1  cmp     qword ptr [rdi+8], 0
0x18002c5b6  jnz     short loc_18002C600
0x18002c5b8  mov     edx, ebp
0x18002c5ba  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5c6  cmp     rcx, r12
0x18002c5c9  jz      short loc_18002C5F4
0x18002c5cb  test    byte ptr [rcx+1Ch], 1
0x18002c5cf  jz      short loc_18002C5F4
0x18002c5d1  cmp     [rcx+19h], bpl
0x18002c5d5  jb      short loc_18002C5F4
0x18002c5d7  mov     rcx, [rcx+10h]
0x18002c5db  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18002c5e2  mov     edx, 17h
0x18002c5e7  mov     [rsp+78h+var_58], rax
0x18002c5ec  mov     r8, r13
0x18002c5ef  call    WPP_SF_ss
0x18002c5f4  lea     rbx, [rdi+270h]
0x18002c5fb  jmp     loc_18002C6A2
0x18002c600  lea     rbx, [rdi+270h]
0x18002c607  mov     rcx, rbx
0x18002c60a  call    CspEnterCriticalSection
0x18002c60f  test    eax, eax
0x18002c611  jz      short loc_18002C64C
0x18002c613  mov     edx, ebp
0x18002c615  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c621  cmp     rcx, r12
0x18002c624  jz      short loc_18002C6A2
0x18002c626  test    byte ptr [rcx+1Ch], 1
0x18002c62a  jz      short loc_18002C6A2
0x18002c62c  cmp     [rcx+19h], bpl
0x18002c630  jb      short loc_18002C6A2
0x18002c632  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c639  mov     edx, 18h
0x18002c63e  mov     rcx, [rcx+10h]
0x18002c642  mov     r8, r13
0x18002c645  call    WPP_SF_s
0x18002c64a  jmp     short loc_18002C6A2
0x18002c64c  mov     rdx, rbx
0x18002c64f  lea     rcx, [rsp+78h+var_48]
0x18002c654  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x18002c659  mov     rcx, rdi; struct _CARD_STATE *
0x18002c65c  call    TransactionManagerForceEndTransaction
0x18002c661  mov     esi, eax
0x18002c663  test    eax, eax
0x18002c665  jz      short loc_18002C6A2
0x18002c667  mov     edx, ebp
0x18002c669  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c66e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c675  cmp     rcx, r12
0x18002c678  jz      short loc_18002C6A2
0x18002c67a  test    byte ptr [rcx+1Ch], 1
0x18002c67e  jz      short loc_18002C6A2
0x18002c680  cmp     [rcx+19h], bpl
0x18002c684  jb      short loc_18002C6A2
0x18002c686  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c68d  mov     edx, 19h
0x18002c692  mov     rcx, [rcx+10h]
0x18002c696  mov     r8, r13
0x18002c699  mov     dword ptr [rsp+78h+var_58], esi
0x18002c69d  call    WPP_SF_sD
0x18002c6a2  mov     rax, [rdi+8]
0x18002c6a6  mov     rsi, [rax+68h]
0x18002c6aa  mov     qword ptr [rax+68h], 0
0x18002c6b2  cmp     [rsp+78h+var_40], 0
0x18002c6b8  mov     dword ptr [rdi+2B0h], 1
0x18002c6c2  jz      short loc_18002C6D5
0x18002c6c4  mov     rcx, rbx
0x18002c6c7  mov     [rsp+78h+var_40], 0
0x18002c6d0  call    CspLeaveCriticalSection
0x18002c6d5  xor     edx, edx; dwDisposition
0x18002c6d7  mov     rcx, rsi; hCard
0x18002c6da  call    cs:__imp_SCardDisconnect
0x18002c6e0  mov     ebx, eax
0x18002c6e2  test    eax, eax
0x18002c6e4  jz      short loc_18002C721
0x18002c6e6  mov     edx, ebp
0x18002c6e8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6f4  cmp     rcx, r12
0x18002c6f7  jz      short loc_18002C721
0x18002c6f9  test    byte ptr [rcx+1Ch], 1
0x18002c6fd  jz      short loc_18002C721
0x18002c6ff  cmp     [rcx+19h], bpl
0x18002c703  jb      short loc_18002C721
0x18002c705  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c70c  mov     edx, 1Ah
0x18002c711  mov     rcx, [rcx+10h]
0x18002c715  mov     r8, r13
0x18002c718  mov     dword ptr [rsp+78h+var_58], ebx
0x18002c71c  call    WPP_SF_sD
0x18002c721  mov     edx, 1
0x18002c726  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c732  cmp     rcx, r12
0x18002c735  jz      short loc_18002C75F
0x18002c737  test    [rcx+1Ch], bpl
0x18002c73b  jz      short loc_18002C75F
0x18002c73d  cmp     byte ptr [rcx+19h], 5
0x18002c741  jb      short loc_18002C75F
0x18002c743  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c74a  mov     edx, 1Bh
0x18002c74f  mov     rcx, [rcx+10h]
0x18002c753  mov     r8, r13
0x18002c756  mov     dword ptr [rsp+78h+var_58], ebx
0x18002c75a  call    WPP_SF_sD
0x18002c75f  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x18002c766  lea     rcx, [rsp+78h+var_48]
0x18002c76b  mov     [rsp+78h+var_48], rax
0x18002c770  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x18002c775  add     rsp, 48h
0x18002c779  pop     r13
0x18002c77b  pop     r12
0x18002c77d  pop     rdi
0x18002c77e  pop     rsi
0x18002c77f  pop     rbp
0x18002c780  pop     rbx
0x18002c781  retn
```

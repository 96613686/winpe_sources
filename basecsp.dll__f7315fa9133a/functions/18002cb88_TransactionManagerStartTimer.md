# TransactionManagerStartTimer

- ea: `0x18002cb88`
- end: `0x18002cc90`
- name: `TransactionManagerStartTimer`
- size: `264`
- prototype: `__int64 __fastcall(struct _CARD_STATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000d5c0`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18002c920`
- `0x18002cb88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cc1f`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002cbe9`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18002cbe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cc3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002cc3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cc0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002cc0d`

## pseudocode

```c
__int64 __fastcall TransactionManagerStartTimer(struct _CARD_STATE *a1)
{
  PFILETIME v1; // rsi
  DWORD LastError; // edi
  struct _TP_TIMER *v4; // rcx
  __int64 v5; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax

  v1 = g_pTransactionManagerState;
  LastError = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids, WPP_pszIndent);
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)a1 + 75);
  if ( !v4 || !IsThreadpoolTimerSet(v4) )
  {
    ThreadpoolTimer = (struct _TP_TIMER *)*((_QWORD *)a1 + 75);
    if ( ThreadpoolTimer
      || (ThreadpoolTimer = CreateThreadpoolTimer(TransactionManagerTimeoutHandler, a1, (PTP_CALLBACK_ENVIRON)&v1[2]),
          (*((_QWORD *)a1 + 75) = ThreadpoolTimer) != 0) )
    {
      SetThreadpoolTimer(ThreadpoolTimer, v1, 0, 0);
    }
    else
    {
      LastError = GetLastError();
      TransactionManagerForceEndTransaction(a1);
    }
  }
  WppTraceIndent(v5, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      (unsigned int)WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x18002cb88  push    rbx
0x18002cb8a  push    rbp
0x18002cb8b  push    rsi
0x18002cb8c  push    rdi
0x18002cb8d  sub     rsp, 38h
0x18002cb91  mov     rsi, cs:?g_pTransactionManagerState@@3PEAU_TRANSACTION_MANAGER_STATE@@EA; _TRANSACTION_MANAGER_STATE * g_pTransactionManagerState
0x18002cb98  xor     edi, edi
0x18002cb9a  xor     edx, edx
0x18002cb9c  mov     rbx, rcx
0x18002cb9f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbab  lea     rbp, WPP_GLOBAL_Control
0x18002cbb2  cmp     rcx, rbp
0x18002cbb5  jz      short loc_18002CBDD
0x18002cbb7  test    byte ptr [rcx+1Ch], 2
0x18002cbbb  jz      short loc_18002CBDD
0x18002cbbd  cmp     byte ptr [rcx+19h], 5
0x18002cbc1  jb      short loc_18002CBDD
0x18002cbc3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002cbca  lea     edx, [rdi+20h]
0x18002cbcd  mov     rcx, [rcx+10h]
0x18002cbd1  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002cbd8  call    WPP_SF_s
0x18002cbdd  mov     rcx, [rbx+258h]; pti
0x18002cbe4  test    rcx, rcx
0x18002cbe7  jz      short loc_18002CBF3
0x18002cbe9  call    cs:__imp_IsThreadpoolTimerSet
0x18002cbef  test    eax, eax
0x18002cbf1  jnz     short loc_18002CC43
0x18002cbf3  mov     rax, [rbx+258h]
0x18002cbfa  test    rax, rax
0x18002cbfd  jnz     short loc_18002CC31
0x18002cbff  lea     r8, [rsi+10h]; pcbe
0x18002cc03  mov     rdx, rbx; pv
0x18002cc06  lea     rcx, ?TransactionManagerTimeoutHandler@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002cc0d  call    cs:__imp_CreateThreadpoolTimer
0x18002cc13  mov     [rbx+258h], rax
0x18002cc1a  test    rax, rax
0x18002cc1d  jnz     short loc_18002CC31
0x18002cc1f  call    cs:__imp_GetLastError
0x18002cc25  mov     rcx, rbx; struct _CARD_STATE *
0x18002cc28  mov     edi, eax
0x18002cc2a  call    TransactionManagerForceEndTransaction
0x18002cc2f  jmp     short loc_18002CC43
0x18002cc31  xor     r9d, r9d; msWindowLength
0x18002cc34  xor     r8d, r8d; msPeriod
0x18002cc37  mov     rdx, rsi; pftDueTime
0x18002cc3a  mov     rcx, rax; pti
0x18002cc3d  call    cs:__imp_SetThreadpoolTimer
0x18002cc43  mov     edx, 1
0x18002cc48  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002cc4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc54  cmp     rcx, rbp
0x18002cc57  jz      short loc_18002CC85
0x18002cc59  test    byte ptr [rcx+1Ch], 2
0x18002cc5d  jz      short loc_18002CC85
0x18002cc5f  cmp     byte ptr [rcx+19h], 5
0x18002cc63  jb      short loc_18002CC85
0x18002cc65  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002cc6c  lea     r8, WPP_c71af58e9db6359151fab6997eb16e5e_Traceguids
0x18002cc73  mov     rcx, [rcx+10h]
0x18002cc77  mov     edx, 21h ; '!'
0x18002cc7c  mov     [rsp+58h+var_38], edi
0x18002cc80  call    WPP_SF_sD
0x18002cc85  mov     eax, edi
0x18002cc87  add     rsp, 38h
0x18002cc8b  pop     rdi
0x18002cc8c  pop     rsi
0x18002cc8d  pop     rbp
0x18002cc8e  pop     rbx
0x18002cc8f  retn
```

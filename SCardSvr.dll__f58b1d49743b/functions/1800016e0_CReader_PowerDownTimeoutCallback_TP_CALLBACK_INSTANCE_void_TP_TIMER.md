# CReader::PowerDownTimeoutCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800016e0`
- end: `0x1800018f6`
- name: `?PowerDownTimeoutCallback@CReader@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `534`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, struct _FILETIME *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800016e0`
- `0x180001900`
- `0x180003458`
- `0x1800075d0`
- `0x18000cd80`
- `0x1800170d0`
- `0x180028b78`
- `0x18002d4a4`
- `0x18002d928`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000175f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000175f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CReader::PowerDownTimeoutCallback(
        PTP_CALLBACK_INSTANCE Instance,
        struct _FILETIME *Context,
        PTP_TIMER Timer)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  const struct CReader::ActiveState *v7; // r8
  __int64 v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  ulong v11; // [rsp+20h] [rbp-28h] BYREF
  CReader *v14; // [rsp+68h] [rbp+20h] BYREF

  WppTraceIndent(Instance, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
  }
  CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
  SetThreadpoolTimer(Timer, 0, 0, 0);
  if ( !Context )
  {
    WppTraceIndent(v5, 2);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_27;
    }
    v10 = 18;
LABEL_26:
    WPP_SF_s(v9[2], v10, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    goto LABEL_27;
  }
  if ( (unsigned int)CReader::AvailabilityStatus((__int64)Context) != 5 )
  {
    WppTraceIndent(v6, 2);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_27;
    }
    v10 = 17;
    goto LABEL_26;
  }
  WppTraceIndent(v6, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
  }
  try
  {
    CTryLatchReader::CTryLatchReader((CTryLatchReader *)&v14, (struct CReader *)Context, v7);
    if ( (unsigned int)CReader::AvailabilityStatus((__int64)Context) == 5 )
    {
      CReader::SetActive((CReader *)Context, 0);
      CReader::PowerDown((CReader *)Context);
    }
    else
    {
      WppTraceIndent(v8, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
          WPP_pszIndent);
      }
    }
    CTryLatchReader::~CTryLatchReader(&v14);
  }
  catch ( ulong v11 )
  {
    if ( v11 == 1460 )
    {
      WppTraceIndent(v9, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
          WPP_pszIndent);
      }
      SetThreadpoolTimer(Timer, Context + 90, 0, 0);
      goto LABEL_27;
    }
    throw;
  }
LABEL_27:
  WppTraceIndent(v9, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
  }
}

```

## disassembly

```asm
0x1800016e0  mov     [rsp+arg_10], r8
0x1800016e5  mov     [rsp+arg_8], rdx
0x1800016ea  push    rbx
0x1800016eb  push    rsi
0x1800016ec  push    r14
0x1800016ee  sub     rsp, 30h
0x1800016f2  mov     r14, r8
0x1800016f5  mov     rbx, rdx
0x1800016f8  mov     edx, 2
0x1800016fd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180001702  lea     rsi, WPP_GLOBAL_Control
0x180001709  mov     rcx, cs:WPP_GLOBAL_Control
0x180001710  cmp     rcx, rsi
0x180001713  jz      short loc_18000173D
0x180001715  test    byte ptr [rcx+1Ch], 10h
0x180001719  jz      short loc_18000173D
0x18000171b  cmp     byte ptr [rcx+19h], 4
0x18000171f  jb      short loc_18000173D
0x180001721  mov     edx, 0Dh
0x180001726  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000172d  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180001734  mov     rcx, [rcx+10h]
0x180001738  call    WPP_SF_s
0x18000173d  mov     eax, 1
0x180001742  lock xadd cs:dword_18004BF90, eax
0x18000174a  inc     eax
0x18000174c  movsxd  rcx, eax; lpTlsValue
0x18000174f  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x180001754  xor     r9d, r9d; msWindowLength
0x180001757  xor     r8d, r8d; msPeriod
0x18000175a  xor     edx, edx; pftDueTime
0x18000175c  mov     rcx, r14; pti
0x18000175f  call    cs:__imp_SetThreadpoolTimer
0x180001765  nop
0x180001766  test    rbx, rbx
0x180001769  jz      loc_180001867
0x18000176f  mov     rcx, rbx
0x180001772  call    ?AvailabilityStatus@CReader@@QEAA?AW4AvailableState@1@XZ; CReader::AvailabilityStatus(void)
0x180001777  mov     edx, 2
0x18000177c  cmp     eax, 5
0x18000177f  jnz     loc_180001843
0x180001785  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000178a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001791  cmp     rcx, rsi
0x180001794  jz      short loc_1800017BF
0x180001796  test    byte ptr [rcx+1Ch], 10h
0x18000179a  jz      short loc_1800017BF
0x18000179c  cmp     byte ptr [rcx+19h], 4
0x1800017a0  jb      short loc_1800017BF
0x1800017a2  mov     edx, 0Eh
0x1800017a7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800017ae  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x1800017b5  mov     rcx, [rcx+10h]
0x1800017b9  call    WPP_SF_s
0x1800017be  nop
0x1800017bf  mov     rdx, rbx; struct CReader *
0x1800017c2  lea     rcx, [rsp+48h+arg_18]; this
0x1800017c7  call    ??0CTryLatchReader@@QEAA@PEAVCReader@@PEBUActiveState@1@@Z; CTryLatchReader::CTryLatchReader(CReader *,CReader::ActiveState const *)
0x1800017cc  nop
0x1800017cd  mov     rcx, rbx
0x1800017d0  call    ?AvailabilityStatus@CReader@@QEAA?AW4AvailableState@1@XZ; CReader::AvailabilityStatus(void)
0x1800017d5  cmp     eax, 5
0x1800017d8  jnz     short loc_1800017EE
0x1800017da  xor     edx, edx; unsigned int
0x1800017dc  mov     rcx, rbx; this
0x1800017df  call    ?SetActive@CReader@@QEAAXH@Z; CReader::SetActive(int)
0x1800017e4  mov     rcx, rbx; this
0x1800017e7  call    ?PowerDown@CReader@@IEAAXXZ; CReader::PowerDown(void)
0x1800017ec  jmp     short loc_18000182D
0x1800017ee  mov     edx, 2
0x1800017f3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800017f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017ff  cmp     rcx, rsi
0x180001802  jz      short loc_18000182D
0x180001804  test    byte ptr [rcx+1Ch], 10h
0x180001808  jz      short loc_18000182D
0x18000180a  cmp     byte ptr [rcx+19h], 4
0x18000180e  jb      short loc_18000182D
0x180001810  mov     edx, 0Fh
0x180001815  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000181c  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180001823  mov     rcx, [rcx+10h]
0x180001827  call    WPP_SF_s
0x18000182c  nop
0x18000182d  lea     rcx, [rsp+48h+arg_18]; this
0x180001832  call    ??1CTryLatchReader@@QEAA@XZ; CTryLatchReader::~CTryLatchReader(void)
0x180001837  nop
0x180001838  jmp     short loc_1800018A6
0x18000183a  lea     rsi, WPP_GLOBAL_Control
0x180001841  jmp     short loc_1800018A6
0x180001843  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180001848  mov     rcx, cs:WPP_GLOBAL_Control
0x18000184f  cmp     rcx, rsi
0x180001852  jz      short loc_1800018A6
0x180001854  test    byte ptr [rcx+1Ch], 10h
0x180001858  jz      short loc_1800018A6
0x18000185a  cmp     byte ptr [rcx+19h], 4
0x18000185e  jb      short loc_1800018A6
0x180001860  mov     edx, 11h
0x180001865  jmp     short loc_18000188E
0x180001867  mov     edx, 2
0x18000186c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180001871  mov     rcx, cs:WPP_GLOBAL_Control
0x180001878  cmp     rcx, rsi
0x18000187b  jz      short loc_1800018A6
0x18000187d  test    byte ptr [rcx+1Ch], 10h
0x180001881  jz      short loc_1800018A6
0x180001883  cmp     byte ptr [rcx+19h], 4
0x180001887  jb      short loc_1800018A6
0x180001889  mov     edx, 12h
0x18000188e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180001895  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18000189c  mov     rcx, [rcx+10h]
0x1800018a0  call    WPP_SF_s
0x1800018a5  nop
0x1800018a6  jmp     short loc_1800018AF
0x1800018a8  lea     rsi, WPP_GLOBAL_Control
0x1800018af  mov     edx, 2
0x1800018b4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800018b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018c0  cmp     rcx, rsi
0x1800018c3  jz      short loc_1800018ED
0x1800018c5  test    byte ptr [rcx+1Ch], 10h
0x1800018c9  jz      short loc_1800018ED
0x1800018cb  cmp     byte ptr [rcx+19h], 4
0x1800018cf  jb      short loc_1800018ED
0x1800018d1  mov     edx, 14h
0x1800018d6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800018dd  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x1800018e4  mov     rcx, [rcx+10h]
0x1800018e8  call    WPP_SF_s
0x1800018ed  add     rsp, 30h
0x1800018f1  pop     r14
0x1800018f3  pop     rsi
0x1800018f4  pop     rbx
0x1800018f5  retn
```

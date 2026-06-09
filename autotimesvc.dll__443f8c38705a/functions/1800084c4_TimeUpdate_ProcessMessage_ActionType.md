# TimeUpdate::ProcessMessage(ActionType)

- ea: `0x1800084c4`
- end: `0x180008790`
- name: `?ProcessMessage@TimeUpdate@@AEAAXW4ActionType@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(TimeUpdate *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180003b90`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005620`
- `0x180005eb0`
- `0x180006350`
- `0x180006598`
- `0x180006754`
- `0x180006ec4`
- `0x180007a5c`
- `0x1800084c4`
- `0x18000891c`
- `0x1800098d4`
- `0x180009934`
- `0x18000ad28`
- `0x180012010`

## string_xrefs

- `0x18000865d`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ProcessMessage(TimeUpdate *a1, int a2)
{
  _DWORD *v4; // r9
  __int64 *v5; // rdx
  unsigned __int8 v6; // r14
  char v7; // r15
  volatile signed __int32 *v8; // rsi
  __int64 Settings; // rax
  volatile signed __int32 *v10; // rdi
  char v11; // si
  char *v13; // [rsp+28h] [rbp-58h]
  int v14; // [rsp+30h] [rbp-50h]
  _BYTE v15[8]; // [rsp+38h] [rbp-48h] BYREF
  volatile signed __int32 *v16; // [rsp+40h] [rbp-40h]
  int v17; // [rsp+48h] [rbp-38h] BYREF
  char v18; // [rsp+4Ch] [rbp-34h]
  _BYTE v19[16]; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v20[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v17 = 0;
  v18 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v17);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    v14 = a2;
    if ( v18 && (v20[0] || v20[1] || v20[2] || v20[3]) )
      v4 = v20;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)&dword_180016614,
      (__int64)v19,
      (__int64)v4);
  }
  if ( TimeUpdate::IsRunning(a1) )
  {
    v6 = 1;
    if ( (a2 & 0x1000) != 0 )
    {
      v7 = 1;
      TimeUpdate::ReadSettings(a1, v15, &v17);
      v8 = v16;
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      a2 &= ~0x1000u;
    }
    else
    {
      v7 = 0;
    }
    switch ( a2 )
    {
      case 1:
        *((_BYTE *)a1 + 241) = 0;
        TimeUpdate::StopNtp(a1, 0);
        break;
      case 8:
        TimeUpdate::DoTimeSync((__int64)a1, &v17);
        break;
      case 16:
        *((_BYTE *)a1 + 241) = 1;
        Settings = TimeUpdate::GetSettings((__int64)a1, (__int64)v15);
        v10 = v16;
        v11 = *(_BYTE *)(*(_QWORD *)Settings + 6LL);
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
        if ( v11 )
          TimeUpdate::StartNtp(a1);
        break;
      case 64:
        TimeUpdate::DoNITZ(a1, &v17);
        break;
      default:
        if ( !a2 && v7 )
          v6 = 0;
        LODWORD(v13) = a2;
        wil::details::in1diag3::FailFast_IfMsg(
          retaddr,
          (void *)0x27A,
          (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
          (const char *)v6,
          (bool)"Unexpected action type %u",
          v13,
          v14);
        break;
    }
    TimeUpdate::ChangeServiceTimeoutTimer(a1);
    v17 = 2;
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
    {
      v5 = qword_1800164E0;
      goto LABEL_42;
    }
  }
  else
  {
    v17 = 2;
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
    {
      v5 = (__int64 *)byte_18001663D;
LABEL_42:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18001C010,
        (__int64)v5,
        (__int64)v19,
        0);
    }
  }
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v17);
}

```

## disassembly

```asm
0x1800084c4  mov     [rsp-28h+arg_10], rbx
0x1800084c9  mov     [rsp-28h+arg_18], rsi
0x1800084ce  push    rbp
0x1800084cf  push    rdi
0x1800084d0  push    r13
0x1800084d2  push    r14
0x1800084d4  push    r15
0x1800084d6  mov     rbp, rsp
0x1800084d9  sub     rsp, 80h
0x1800084e0  mov     rax, cs:__security_cookie
0x1800084e7  xor     rax, rsp
0x1800084ea  mov     [rbp+var_10], rax
0x1800084ee  mov     rbx, rcx
0x1800084f1  mov     [rbp+var_38], 0
0x1800084f8  lea     rcx, [rbp+var_38]
0x1800084fc  mov     [rbp+var_34], 0
0x180008500  mov     edi, edx
0x180008502  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)
0x180008507  mov     eax, cs:dword_18001C010
0x18000850d  lea     rsi, dword_18001C010
0x180008514  mov     r14d, 300h
0x18000851a  cmp     eax, 4
0x18000851d  jbe     short loc_180008574
0x18000851f  mov     edx, r14d
0x180008522  mov     rcx, rsi
0x180008525  call    _tlgKeywordOn
0x18000852a  test    al, al
0x18000852c  jz      short loc_180008574
0x18000852e  cmp     [rbp+var_34], 0
0x180008532  mov     [rbp+var_50], edi
0x180008535  jz      short loc_180008555
0x180008537  cmp     [rbp+var_20], 0
0x18000853b  jnz     short loc_18000854F
0x18000853d  cmp     [rbp+var_1C], 0
0x180008541  jnz     short loc_18000854F
0x180008543  cmp     [rbp+var_18], 0
0x180008547  jnz     short loc_18000854F
0x180008549  cmp     [rbp+var_14], 0
0x18000854d  jz      short loc_180008555
0x18000854f  lea     r9, [rbp+var_20]
0x180008553  jmp     short loc_180008558
0x180008555  xor     r9d, r9d
0x180008558  lea     rax, [rbp+var_50]
0x18000855c  mov     rcx, rsi
0x18000855f  lea     r8, [rbp+var_30]
0x180008563  mov     qword ptr [rsp+80h+var_60], rax
0x180008568  lea     rdx, dword_180016614
0x18000856f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180008574  mov     rcx, rbx; this
0x180008577  call    ?IsRunning@TimeUpdate@@AEBA_NXZ; TimeUpdate::IsRunning(void)
0x18000857c  test    al, al
0x18000857e  jnz     short loc_1800085B8
0x180008580  mov     eax, cs:dword_18001C010
0x180008586  mov     [rbp+var_38], 2
0x18000858d  cmp     eax, 4
0x180008590  jbe     loc_18000875F
0x180008596  mov     rdx, r14
0x180008599  mov     rcx, rsi
0x18000859c  call    _tlgKeywordOn
0x1800085a1  test    al, al
0x1800085a3  jz      loc_18000875F
0x1800085a9  lea     rdx, byte_18001663D
0x1800085b0  mov     rcx, rsi
0x1800085b3  jmp     loc_180008753
0x1800085b8  or      r13d, 0FFFFFFFFh
0x1800085bc  mov     r14d, 1
0x1800085c2  bt      edi, 0Ch
0x1800085c6  jnb     short loc_180008621
0x1800085c8  lea     r8, [rbp+var_38]
0x1800085cc  mov     rcx, rbx
0x1800085cf  lea     rdx, [rbp+var_48]
0x1800085d3  mov     r15b, r14b
0x1800085d6  call    ?ReadSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@AEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z; TimeUpdate::ReadSettings(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)
0x1800085db  mov     rsi, [rbp+var_40]
0x1800085df  test    rsi, rsi
0x1800085e2  jz      short loc_18000861B
0x1800085e4  mov     eax, r13d
0x1800085e7  lock xadd [rsi+8], eax
0x1800085ec  add     eax, r13d
0x1800085ef  jnz     short loc_18000861B
0x1800085f1  mov     rax, [rsi]
0x1800085f4  mov     rcx, rsi
0x1800085f7  mov     rax, [rax]
0x1800085fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ff  mov     eax, r13d
0x180008602  lock xadd [rsi+0Ch], eax
0x180008607  add     eax, r13d
0x18000860a  jnz     short loc_18000861B
0x18000860c  mov     rax, [rsi]
0x18000860f  mov     rcx, rsi
0x180008612  mov     rax, [rax+8]
0x180008616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000861b  btr     edi, 0Ch
0x18000861f  jmp     short loc_180008624
0x180008621  xor     r15b, r15b
0x180008624  mov     eax, edi
0x180008626  sub     eax, r14d
0x180008629  jz      loc_180008704
0x18000862f  sub     eax, 7
0x180008632  jz      loc_1800086F6
0x180008638  sub     eax, 8
0x18000863b  jz      short loc_18000868D
0x18000863d  cmp     eax, 30h ; '0'
0x180008640  jz      short loc_18000867C
0x180008642  test    edi, edi
0x180008644  jnz     short loc_18000864E
0x180008646  test    r15b, r15b
0x180008649  jz      short loc_18000864E
0x18000864b  xor     r14b, r14b
0x18000864e  mov     rcx, [rbp+28h]; this
0x180008652  lea     rax, aUnexpectedActi; "Unexpected action type %u"
0x180008659  mov     dword ptr [rsp+80h+var_58], edi; char *
0x18000865d  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180008664  movzx   r9d, r14b; char *
0x180008668  mov     edx, 27Ah; void *
0x18000866d  mov     qword ptr [rsp+80h+var_60], rax; bool
0x180008672  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180008677  jmp     loc_180008716
0x18000867c  lea     rdx, [rbp+var_38]
0x180008680  mov     rcx, rbx; this
0x180008683  call    ?DoNITZ@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z; TimeUpdate::DoNITZ(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)
0x180008688  jmp     loc_180008716
0x18000868d  xchg    r14b, [rbx+0F1h]
0x180008694  lea     rdx, [rbp+var_48]
0x180008698  mov     rcx, rbx
0x18000869b  call    ?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ; TimeUpdate::GetSettings(void)
0x1800086a0  mov     rdi, [rbp+var_40]
0x1800086a4  mov     rcx, [rax]
0x1800086a7  mov     sil, [rcx+6]
0x1800086ab  test    rdi, rdi
0x1800086ae  jz      short loc_1800086E7
0x1800086b0  mov     eax, r13d
0x1800086b3  lock xadd [rdi+8], eax
0x1800086b8  add     eax, r13d
0x1800086bb  jnz     short loc_1800086E7
0x1800086bd  mov     rax, [rdi]
0x1800086c0  mov     rcx, rdi
0x1800086c3  mov     rax, [rax]
0x1800086c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086cb  mov     eax, r13d
0x1800086ce  lock xadd [rdi+0Ch], eax
0x1800086d3  add     eax, r13d
0x1800086d6  jnz     short loc_1800086E7
0x1800086d8  mov     rax, [rdi]
0x1800086db  mov     rcx, rdi
0x1800086de  mov     rax, [rax+8]
0x1800086e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e7  test    sil, sil
0x1800086ea  jz      short loc_180008716
0x1800086ec  mov     rcx, rbx; this
0x1800086ef  call    ?StartNtp@TimeUpdate@@AEAAXXZ; TimeUpdate::StartNtp(void)
0x1800086f4  jmp     short loc_180008716
0x1800086f6  lea     rdx, [rbp+var_38]
0x1800086fa  mov     rcx, rbx
0x1800086fd  call    ?DoTimeSync@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z; TimeUpdate::DoTimeSync(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)
0x180008702  jmp     short loc_180008716
0x180008704  xor     eax, eax
0x180008706  xor     edx, edx; bool
0x180008708  xchg    al, [rbx+0F1h]
0x18000870e  mov     rcx, rbx; this
0x180008711  call    ?StopNtp@TimeUpdate@@AEAAX_N@Z; TimeUpdate::StopNtp(bool)
0x180008716  mov     rcx, rbx; this
0x180008719  call    ?ChangeServiceTimeoutTimer@TimeUpdate@@AEAAXXZ; TimeUpdate::ChangeServiceTimeoutTimer(void)
0x18000871e  mov     eax, cs:dword_18001C010
0x180008724  mov     [rbp+var_38], 2
0x18000872b  cmp     eax, 4
0x18000872e  jbe     short loc_18000875F
0x180008730  mov     edx, 300h
0x180008735  lea     rcx, dword_18001C010
0x18000873c  call    _tlgKeywordOn
0x180008741  test    al, al
0x180008743  jz      short loc_18000875F
0x180008745  lea     rdx, qword_1800164E0
0x18000874c  lea     rcx, dword_18001C010
0x180008753  xor     r9d, r9d
0x180008756  lea     r8, [rbp+var_30]
0x18000875a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000875f  lea     rcx, [rbp+var_38]
0x180008763  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)
0x180008768  mov     rcx, [rbp+var_10]
0x18000876c  xor     rcx, rsp; StackCookie
0x18000876f  call    __security_check_cookie
0x180008774  lea     r11, [rsp+80h+var_s0]
0x18000877c  mov     rbx, [r11+40h]
0x180008780  mov     rsi, [r11+48h]
0x180008784  mov     rsp, r11
0x180008787  pop     r15
0x180008789  pop     r14
0x18000878b  pop     r13
0x18000878d  pop     rdi
0x18000878e  pop     rbp
0x18000878f  retn
```

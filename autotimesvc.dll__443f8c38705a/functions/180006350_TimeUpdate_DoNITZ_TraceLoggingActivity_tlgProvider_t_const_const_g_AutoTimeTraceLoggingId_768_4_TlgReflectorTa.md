# TimeUpdate::DoNITZ(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)

- ea: `0x180006350`
- end: `0x1800064db`
- name: `?DoNITZ@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(TimeUpdate *this, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800084c4`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005620`
- `0x180006350`
- `0x180006ec4`
- `0x180009934`
- `0x18000ad28`
- `0x18000c3c8`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall TimeUpdate::DoNITZ(TimeUpdate *this, _DWORD *a2)
{
  int *v3; // r9
  volatile signed __int32 *v4; // rbx
  _BYTE v6[8]; // [rsp+38h] [rbp-48h] BYREF
  volatile signed __int32 *v7; // [rsp+40h] [rbp-40h]
  int v8; // [rsp+48h] [rbp-38h] BYREF
  char v9; // [rsp+4Ch] [rbp-34h]
  _BYTE v10[16]; // [rsp+50h] [rbp-30h] BYREF
  int v11; // [rsp+60h] [rbp-20h] BYREF
  int v12; // [rsp+64h] [rbp-1Ch]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]

  v11 = a2[2];
  v12 = a2[3];
  v13 = a2[4];
  v14 = a2[5];
  v8 = 0;
  v9 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v8);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    if ( v9 && (v11 || v12 || v13 || v14) )
      v3 = &v11;
    else
      v3 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)byte_18001643B,
      (__int64)v10,
      (__int64)v3);
  }
  TimeUpdate::GetSettings(this, v6);
  if ( !(unsigned int)AutoTimeUpdate::Run(v6) )
    TimeUpdate::StopNtp(this, 1);
  v8 = 2;
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)byte_180016795,
      (__int64)v10,
      0);
  v4 = v7;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v8);
}

```

## disassembly

```asm
0x180006350  mov     [rsp-8+arg_8], rbx
0x180006355  mov     [rsp-8+arg_10], rdi
0x18000635a  push    rbp
0x18000635b  mov     rbp, rsp
0x18000635e  sub     rsp, 80h
0x180006365  mov     rax, cs:__security_cookie
0x18000636c  xor     rax, rsp
0x18000636f  mov     [rbp+var_10], rax
0x180006373  mov     eax, [rdx+8]
0x180006376  mov     rdi, rcx
0x180006379  mov     [rbp+var_20], eax
0x18000637c  lea     rcx, [rbp+var_38]
0x180006380  mov     eax, [rdx+0Ch]
0x180006383  mov     [rbp+var_1C], eax
0x180006386  mov     eax, [rdx+10h]
0x180006389  mov     [rbp+var_18], eax
0x18000638c  mov     eax, [rdx+14h]
0x18000638f  mov     [rbp+var_14], eax
0x180006392  mov     [rbp+var_38], 0
0x180006399  mov     [rbp+var_34], 1
0x18000639d  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)
0x1800063a2  mov     eax, cs:dword_18001C010
0x1800063a8  cmp     eax, 4
0x1800063ab  jbe     short loc_180006400
0x1800063ad  mov     edx, 300h
0x1800063b2  lea     rcx, dword_18001C010
0x1800063b9  call    _tlgKeywordOn
0x1800063be  test    al, al
0x1800063c0  jz      short loc_180006400
0x1800063c2  cmp     [rbp+var_34], 0
0x1800063c6  jz      short loc_1800063E6
0x1800063c8  cmp     [rbp+var_20], 0
0x1800063cc  jnz     short loc_1800063E0
0x1800063ce  cmp     [rbp+var_1C], 0
0x1800063d2  jnz     short loc_1800063E0
0x1800063d4  cmp     [rbp+var_18], 0
0x1800063d8  jnz     short loc_1800063E0
0x1800063da  cmp     [rbp+var_14], 0
0x1800063de  jz      short loc_1800063E6
0x1800063e0  lea     r9, [rbp+var_20]
0x1800063e4  jmp     short loc_1800063E9
0x1800063e6  xor     r9d, r9d
0x1800063e9  lea     r8, [rbp+var_30]
0x1800063ed  lea     rdx, byte_18001643B
0x1800063f4  lea     rcx, dword_18001C010
0x1800063fb  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180006400  lea     rdx, [rbp+var_48]
0x180006404  mov     rcx, rdi
0x180006407  call    ?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ; TimeUpdate::GetSettings(void)
0x18000640c  lea     rcx, [rbp+var_48]
0x180006410  call    ?Run@AutoTimeUpdate@@SA?AW4SyncResult@@AEBV?$shared_ptr@VSettings@@@std@@@Z; AutoTimeUpdate::Run(std::shared_ptr<Settings> const &)
0x180006415  mov     ebx, eax
0x180006417  test    eax, eax
0x180006419  jnz     short loc_180006425
0x18000641b  mov     dl, 1; bool
0x18000641d  mov     rcx, rdi; this
0x180006420  call    ?StopNtp@TimeUpdate@@AEAAX_N@Z; TimeUpdate::StopNtp(bool)
0x180006425  mov     ecx, cs:dword_18001C010
0x18000642b  mov     [rbp+var_38], 2
0x180006432  cmp     ecx, 4
0x180006435  jbe     short loc_180006472
0x180006437  mov     edx, 300h
0x18000643c  lea     rcx, dword_18001C010
0x180006443  call    _tlgKeywordOn
0x180006448  test    al, al
0x18000644a  jz      short loc_180006472
0x18000644c  lea     rax, [rbp+var_50]
0x180006450  mov     [rbp+var_50], ebx
0x180006453  xor     r9d, r9d
0x180006456  mov     [rsp+80h+var_60], rax
0x18000645b  lea     r8, [rbp+var_30]
0x18000645f  lea     rdx, byte_180016795
0x180006466  lea     rcx, dword_18001C010
0x18000646d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180006472  mov     rbx, [rbp+var_40]
0x180006476  test    rbx, rbx
0x180006479  jz      short loc_1800064B1
0x18000647b  or      edi, 0FFFFFFFFh
0x18000647e  mov     eax, edi
0x180006480  lock xadd [rbx+8], eax
0x180006485  add     eax, edi
0x180006487  jnz     short loc_1800064B1
0x180006489  mov     rax, [rbx]
0x18000648c  mov     rcx, rbx
0x18000648f  mov     rax, [rax]
0x180006492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006497  mov     eax, edi
0x180006499  lock xadd [rbx+0Ch], eax
0x18000649e  add     eax, edi
0x1800064a0  jnz     short loc_1800064B1
0x1800064a2  mov     rax, [rbx]
0x1800064a5  mov     rcx, rbx
0x1800064a8  mov     rax, [rax+8]
0x1800064ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b1  lea     rcx, [rbp+var_38]
0x1800064b5  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)
0x1800064ba  mov     rcx, [rbp+var_10]
0x1800064be  xor     rcx, rsp; StackCookie
0x1800064c1  call    __security_check_cookie
0x1800064c6  lea     r11, [rsp+80h+var_s0]
0x1800064ce  mov     rbx, [r11+18h]
0x1800064d2  mov     rdi, [r11+20h]
0x1800064d6  mov     rsp, r11
0x1800064d9  pop     rbp
0x1800064da  retn
```

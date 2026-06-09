# TimeUpdate::ProcessNtp(ActionType)

- ea: `0x180008798`
- end: `0x1800088b3`
- name: `?ProcessNtp@TimeUpdate@@AEAAXW4ActionType@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(TimeUpdate *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x180003be0`

## callees

- `0x180001010`
- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x180005620`
- `0x180005eb0`
- `0x1800064e4`
- `0x180008798`
- `0x18000ad28`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ProcessNtp(TimeUpdate *a1)
{
  _DWORD *v2; // r9
  int v4; // [rsp+38h] [rbp-38h] BYREF
  char v5; // [rsp+3Ch] [rbp-34h]
  _BYTE v6[16]; // [rsp+40h] [rbp-30h] BYREF
  _DWORD v7[4]; // [rsp+50h] [rbp-20h] BYREF

  v4 = 0;
  v5 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v4);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    if ( v5 && (v7[0] || v7[1] || v7[2] || v7[3]) )
      v2 = v7;
    else
      v2 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&byte_18001667F,
      (__int64)v6,
      (__int64)v2);
  }
  TimeUpdate::DoNTPSync(a1);
  TimeUpdate::ChangeServiceTimeoutTimer(a1);
  v4 = 2;
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)&word_18001669E,
      (__int64)v6,
      0);
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v4);
}

```

## disassembly

```asm
0x180008798  mov     [rsp-8+arg_8], rbx
0x18000879d  mov     [rsp-8+arg_10], rdi
0x1800087a2  push    rbp
0x1800087a3  mov     rbp, rsp
0x1800087a6  sub     rsp, 70h
0x1800087aa  mov     rax, cs:__security_cookie
0x1800087b1  xor     rax, rsp
0x1800087b4  mov     [rbp+var_10], rax
0x1800087b8  mov     rdi, rcx
0x1800087bb  mov     [rbp+var_38], 0
0x1800087c2  lea     rcx, [rbp+var_38]
0x1800087c6  mov     [rbp+var_34], 0
0x1800087ca  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)
0x1800087cf  mov     eax, cs:dword_18001C010
0x1800087d5  cmp     eax, 4
0x1800087d8  jbe     short loc_18000882D
0x1800087da  mov     edx, 300h
0x1800087df  lea     rcx, dword_18001C010
0x1800087e6  call    _tlgKeywordOn
0x1800087eb  test    al, al
0x1800087ed  jz      short loc_18000882D
0x1800087ef  cmp     [rbp+var_34], 0
0x1800087f3  jz      short loc_180008813
0x1800087f5  cmp     [rbp+var_20], 0
0x1800087f9  jnz     short loc_18000880D
0x1800087fb  cmp     [rbp+var_1C], 0
0x1800087ff  jnz     short loc_18000880D
0x180008801  cmp     [rbp+var_18], 0
0x180008805  jnz     short loc_18000880D
0x180008807  cmp     [rbp+var_14], 0
0x18000880b  jz      short loc_180008813
0x18000880d  lea     r9, [rbp+var_20]
0x180008811  jmp     short loc_180008816
0x180008813  xor     r9d, r9d
0x180008816  lea     r8, [rbp+var_30]
0x18000881a  lea     rdx, byte_18001667F
0x180008821  lea     rcx, dword_18001C010
0x180008828  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000882d  mov     rcx, rdi
0x180008830  call    ?DoNTPSync@TimeUpdate@@AEAA?AW4SyncResult@@XZ; TimeUpdate::DoNTPSync(void)
0x180008835  mov     rcx, rdi; this
0x180008838  mov     ebx, eax
0x18000883a  call    ?ChangeServiceTimeoutTimer@TimeUpdate@@AEAAXXZ; TimeUpdate::ChangeServiceTimeoutTimer(void)
0x18000883f  mov     ecx, cs:dword_18001C010
0x180008845  mov     [rbp+var_38], 2
0x18000884c  cmp     ecx, 4
0x18000884f  jbe     short loc_18000888C
0x180008851  mov     edx, 300h
0x180008856  lea     rcx, dword_18001C010
0x18000885d  call    _tlgKeywordOn
0x180008862  test    al, al
0x180008864  jz      short loc_18000888C
0x180008866  lea     rax, [rbp+var_40]
0x18000886a  mov     [rbp+var_40], ebx
0x18000886d  xor     r9d, r9d
0x180008870  mov     [rsp+70h+var_50], rax
0x180008875  lea     r8, [rbp+var_30]
0x180008879  lea     rdx, word_18001669E
0x180008880  lea     rcx, dword_18001C010
0x180008887  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000888c  lea     rcx, [rbp+var_38]
0x180008890  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)
0x180008895  mov     rcx, [rbp+var_10]
0x180008899  xor     rcx, rsp; StackCookie
0x18000889c  call    __security_check_cookie
0x1800088a1  lea     r11, [rsp+70h+var_s0]
0x1800088a6  mov     rbx, [r11+18h]
0x1800088aa  mov     rdi, [r11+20h]
0x1800088ae  mov     rsp, r11
0x1800088b1  pop     rbp
0x1800088b2  retn
```

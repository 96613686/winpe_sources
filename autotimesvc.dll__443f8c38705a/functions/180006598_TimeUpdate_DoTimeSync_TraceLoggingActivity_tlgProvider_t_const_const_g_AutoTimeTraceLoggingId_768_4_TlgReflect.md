# TimeUpdate::DoTimeSync(TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider> const &)

- ea: `0x180006598`
- end: `0x18000674b`
- name: `?DoTimeSync@TimeUpdate@@AEAAXAEBV?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x1800084c4`

## callees

- `0x180001010`
- `0x180001270`
- `0x1800012f0`
- `0x180002a70`
- `0x180005620`
- `0x180006598`
- `0x180006ec4`
- `0x18000ad28`
- `0x18000b668`
- `0x18000ca60`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall TimeUpdate::DoTimeSync(__int64 a1, _DWORD *a2)
{
  int *v3; // r9
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  volatile signed __int32 *v7; // rbx
  __int64 v9; // [rsp+38h] [rbp-48h] BYREF
  volatile signed __int32 *v10; // [rsp+40h] [rbp-40h]
  int v11; // [rsp+48h] [rbp-38h] BYREF
  char v12; // [rsp+4Ch] [rbp-34h]
  _BYTE v13[16]; // [rsp+50h] [rbp-30h] BYREF
  int v14; // [rsp+60h] [rbp-20h] BYREF
  int v15; // [rsp+64h] [rbp-1Ch]
  int v16; // [rsp+68h] [rbp-18h]
  int v17; // [rsp+6Ch] [rbp-14h]

  v14 = a2[2];
  v15 = a2[3];
  v16 = a2[4];
  v17 = a2[5];
  v11 = 0;
  v12 = 1;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(&v11);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
  {
    if ( v12 && (v14 || v15 || v16 || v17) )
      v3 = &v14;
    else
      v3 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&word_180016776,
      (__int64)v13,
      (__int64)v3);
  }
  TimeUpdate::GetSettings(a1, &v9);
  v4 = LastSyncInfo::Run(&v9);
  LOBYTE(v6) = 0;
  if ( (unsigned int)(v4 - 3) <= 2 && *(_BYTE *)(v9 + 6) )
    LOBYTE(v6) = WNFNotificationDispatcher::Enqueue(a1 + 144, 32);
  v11 = 2;
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 768) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)word_180016542,
      (__int64)v13);
  v7 = v10;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v7)(v7, v5, v6);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(&v11);
}

```

## disassembly

```asm
0x180006598  mov     [rsp-8+arg_8], rbx
0x18000659d  mov     [rsp-8+arg_10], rdi
0x1800065a2  push    rbp
0x1800065a3  mov     rbp, rsp
0x1800065a6  sub     rsp, 80h
0x1800065ad  mov     rax, cs:__security_cookie
0x1800065b4  xor     rax, rsp
0x1800065b7  mov     [rbp+var_10], rax
0x1800065bb  mov     eax, [rdx+8]
0x1800065be  mov     rdi, rcx
0x1800065c1  mov     [rbp+var_20], eax
0x1800065c4  lea     rcx, [rbp+var_38]
0x1800065c8  mov     eax, [rdx+0Ch]
0x1800065cb  mov     [rbp+var_1C], eax
0x1800065ce  mov     eax, [rdx+10h]
0x1800065d1  mov     [rbp+var_18], eax
0x1800065d4  mov     eax, [rdx+14h]
0x1800065d7  mov     [rbp+var_14], eax
0x1800065da  mov     [rbp+var_38], 0
0x1800065e1  mov     [rbp+var_34], 1
0x1800065e5  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::zInternalStart(void)
0x1800065ea  mov     eax, cs:dword_18001C010
0x1800065f0  cmp     eax, 4
0x1800065f3  jbe     short loc_180006648
0x1800065f5  mov     edx, 300h
0x1800065fa  lea     rcx, dword_18001C010
0x180006601  call    _tlgKeywordOn
0x180006606  test    al, al
0x180006608  jz      short loc_180006648
0x18000660a  cmp     [rbp+var_34], 0
0x18000660e  jz      short loc_18000662E
0x180006610  cmp     [rbp+var_20], 0
0x180006614  jnz     short loc_180006628
0x180006616  cmp     [rbp+var_1C], 0
0x18000661a  jnz     short loc_180006628
0x18000661c  cmp     [rbp+var_18], 0
0x180006620  jnz     short loc_180006628
0x180006622  cmp     [rbp+var_14], 0
0x180006626  jz      short loc_18000662E
0x180006628  lea     r9, [rbp+var_20]
0x18000662c  jmp     short loc_180006631
0x18000662e  xor     r9d, r9d
0x180006631  lea     r8, [rbp+var_30]
0x180006635  lea     rdx, word_180016776
0x18000663c  lea     rcx, dword_18001C010
0x180006643  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180006648  lea     rdx, [rbp+var_48]
0x18000664c  mov     rcx, rdi
0x18000664f  call    ?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ; TimeUpdate::GetSettings(void)
0x180006654  lea     rcx, [rbp+var_48]
0x180006658  call    ?Run@LastSyncInfo@@SA?AW4SyncResult@@AEBV?$shared_ptr@VSettings@@@std@@@Z; LastSyncInfo::Run(std::shared_ptr<Settings> const &)
0x18000665d  xor     r8b, r8b
0x180006660  mov     ebx, eax
0x180006662  lea     ecx, [rax-3]
0x180006665  cmp     ecx, 2
0x180006668  ja      short loc_180006688
0x18000666a  mov     rcx, [rbp+var_48]
0x18000666e  cmp     [rcx+6], r8b
0x180006672  jz      short loc_180006688
0x180006674  lea     rcx, [rdi+90h]
0x18000667b  mov     edx, 20h ; ' '
0x180006680  call    ?Enqueue@WNFNotificationDispatcher@@QEAA_NW4ActionType@@@Z; WNFNotificationDispatcher::Enqueue(ActionType)
0x180006685  mov     r8b, al
0x180006688  mov     ecx, cs:dword_18001C010
0x18000668e  mov     [rbp+var_38], 2
0x180006695  cmp     ecx, 4
0x180006698  jbe     short loc_1800066E2
0x18000669a  mov     edx, 300h
0x18000669f  lea     rcx, dword_18001C010
0x1800066a6  call    _tlgKeywordOn
0x1800066ab  test    al, al
0x1800066ad  jz      short loc_1800066E2
0x1800066af  movzx   eax, r8b
0x1800066b3  lea     rdx, word_180016542
0x1800066ba  mov     [rbp+var_50], eax
0x1800066bd  lea     r8, [rbp+var_30]
0x1800066c1  lea     rax, [rbp+var_50]
0x1800066c5  mov     [rbp+var_4C], ebx
0x1800066c8  mov     [rsp+80h+var_58], rax
0x1800066cd  lea     rcx, dword_18001C010
0x1800066d4  lea     rax, [rbp+var_4C]
0x1800066d8  mov     [rsp+80h+var_60], rax
0x1800066dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800066e2  mov     rbx, [rbp+var_40]
0x1800066e6  test    rbx, rbx
0x1800066e9  jz      short loc_180006721
0x1800066eb  or      edi, 0FFFFFFFFh
0x1800066ee  mov     eax, edi
0x1800066f0  lock xadd [rbx+8], eax
0x1800066f5  add     eax, edi
0x1800066f7  jnz     short loc_180006721
0x1800066f9  mov     rax, [rbx]
0x1800066fc  mov     rcx, rbx
0x1800066ff  mov     rax, [rax]
0x180006702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006707  mov     eax, edi
0x180006709  lock xadd [rbx+0Ch], eax
0x18000670e  add     eax, edi
0x180006710  jnz     short loc_180006721
0x180006712  mov     rax, [rbx]
0x180006715  mov     rcx, rbx
0x180006718  mov     rax, [rax+8]
0x18000671c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006721  lea     rcx, [rbp+var_38]
0x180006725  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@$0DAA@$03@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>,768,4>(void)
0x18000672a  mov     rcx, [rbp+var_10]
0x18000672e  xor     rcx, rsp; StackCookie
0x180006731  call    __security_check_cookie
0x180006736  lea     r11, [rsp+80h+var_s0]
0x18000673e  mov     rbx, [r11+18h]
0x180006742  mov     rdi, [r11+20h]
0x180006746  mov     rsp, r11
0x180006749  pop     rbp
0x18000674a  retn
```

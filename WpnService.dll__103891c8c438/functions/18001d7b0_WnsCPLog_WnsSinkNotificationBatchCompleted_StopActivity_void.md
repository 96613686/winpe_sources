# WnsCPLog::WnsSinkNotificationBatchCompleted::StopActivity(void)

- ea: `0x18001d7b0`
- end: `0x18001d9df`
- name: `?StopActivity@WnsSinkNotificationBatchCompleted@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsSinkNotificationBatchCompleted *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18001d7b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d97d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d97d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkNotificationBatchCompleted::StopActivity(
        WnsCPLog::WnsSinkNotificationBatchCompleted *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // [rsp+C0h] [rbp-80h] BYREF
  int v12; // [rsp+C4h] [rbp-7Ch] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v15; // [rsp+D0h] [rbp-70h] BYREF
  int *v16; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v17; // [rsp+E0h] [rbp-60h] BYREF
  int *v18; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v20; // [rsp+F8h] [rbp-48h] BYREF
  int *v21; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v23; // [rsp+110h] [rbp-30h] BYREF
  __int64 v24; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v25[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v26; // [rsp+150h] [rbp+10h] BYREF
  int v27; // [rsp+158h] [rbp+18h] BYREF
  __int64 v28; // [rsp+160h] [rbp+20h] BYREF
  int v29; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v7 = *((_QWORD *)this + 34);
      LODWORD(v28) = v4[26];
      v18 = (int *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v11 = v4[8];
      v21 = (int *)*((_QWORD *)v4 + 3);
      v12 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v15 = v6;
      v26 = v4[17];
      v27 = v4[4];
      v16 = (int *)*((_QWORD *)v4 + 15);
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (unsigned __int8 *)word_1800420F2,
        (const GUID *)(v7 + 8),
        (__int64)v5,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v12,
        &v21,
        (__int64)&v11,
        &v20,
        (__int64)&v29,
        &v19,
        &v18,
        (__int64)&v28,
        &v17,
        &v16,
        (__int64)&v27,
        (__int64)&v26,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = WnsCPTracelogger::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v10 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (unsigned __int8 *)&unk_180042090,
        (const GUID *)(v10 + 8),
        0,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001d7b0  push    rbp
0x18001d7b2  push    rbx
0x18001d7b3  push    rdi
0x18001d7b4  lea     rbp, [rsp+10h]
0x18001d7b9  sub     rsp, 130h
0x18001d7c0  mov     rdi, [rcx+110h]
0x18001d7c7  mov     rbx, rcx
0x18001d7ca  mov     eax, [rdi+48h]
0x18001d7cd  test    eax, eax
0x18001d7cf  jns     loc_18001D969
0x18001d7d5  add     rdi, 50h ; 'P'
0x18001d7d9  cmp     eax, [rdi+8]
0x18001d7dc  jnz     loc_18001D969
0x18001d7e2  test    rdi, rdi
0x18001d7e5  jz      loc_18001D969
0x18001d7eb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001d7f0  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001d7f5  mov     r9, rax
0x18001d7f8  mov     ecx, [rax]
0x18001d7fa  cmp     ecx, 5
0x18001d7fd  jbe     loc_18001D9CD
0x18001d803  mov     rax, [rdi+70h]
0x18001d807  lea     rdx, word_1800420F2
0x18001d80e  mov     rcx, [rdi+30h]
0x18001d812  mov     [rbp+var_60], rax
0x18001d816  mov     eax, [rdi+68h]
0x18001d819  mov     r8, [rbx+110h]
0x18001d820  mov     dword ptr [rbp+arg_10], eax
0x18001d823  add     r8, 8
0x18001d827  mov     rax, [rdi+60h]
0x18001d82b  mov     [rbp+var_58], rax
0x18001d82f  mov     rax, [rdi+58h]
0x18001d833  mov     [rbp+var_50], rax
0x18001d837  mov     eax, [rdi+50h]
0x18001d83a  mov     [rbp+arg_18], eax
0x18001d83d  mov     rax, [rdi+48h]
0x18001d841  mov     [rbp+var_48], rax
0x18001d845  mov     eax, [rdi+20h]
0x18001d848  mov     [rbp+var_80], eax
0x18001d84b  mov     rax, [rdi+18h]
0x18001d84f  mov     [rbp+var_40], rax
0x18001d853  mov     eax, [rdi]
0x18001d855  mov     [rbp+var_7C], eax
0x18001d858  mov     rax, [rdi+80h]
0x18001d85f  mov     [rbp+var_38], rax
0x18001d863  mov     eax, [rdi+40h]
0x18001d866  mov     [rbp+var_78], eax
0x18001d869  mov     rax, [rdi+38h]
0x18001d86d  mov     [rbp+var_30], rax
0x18001d871  mov     eax, [rdi+8]
0x18001d874  mov     [rbp+var_74], eax
0x18001d877  lea     rax, [rbp+var_70]
0x18001d87b  mov     [rsp+140h+var_90], rax
0x18001d883  lea     rax, [rbp+arg_0]
0x18001d887  mov     [rsp+140h+var_98], rax
0x18001d88f  lea     rax, [rbp+arg_8]
0x18001d893  mov     [rsp+140h+var_A0], rax
0x18001d89b  lea     rax, [rbp+var_68]
0x18001d89f  mov     [rsp+140h+var_A8], rax
0x18001d8a7  lea     rax, [rbp+var_60]
0x18001d8ab  mov     [rsp+140h+var_B0], rax
0x18001d8b3  lea     rax, [rbp+arg_10]
0x18001d8b7  mov     [rsp+140h+var_B8], rax
0x18001d8bf  lea     rax, [rbp+var_58]
0x18001d8c3  mov     [rsp+140h+var_C0], rax
0x18001d8cb  lea     rax, [rbp+var_50]
0x18001d8cf  mov     [rsp+140h+var_C8], rax
0x18001d8d4  lea     rax, [rbp+arg_18]
0x18001d8d8  mov     [rsp+140h+var_D0], rax
0x18001d8dd  lea     rax, [rbp+var_48]
0x18001d8e1  mov     [rsp+140h+var_D8], rax
0x18001d8e6  lea     rax, [rbp+var_80]
0x18001d8ea  mov     [rsp+140h+var_E0], rax
0x18001d8ef  lea     rax, [rbp+var_40]
0x18001d8f3  mov     [rsp+140h+var_E8], rax
0x18001d8f8  lea     rax, [rbp+var_7C]
0x18001d8fc  mov     [rsp+140h+var_F0], rax
0x18001d901  lea     rax, [rbp+var_38]
0x18001d905  mov     [rsp+140h+var_F8], rax
0x18001d90a  lea     rax, [rbp+var_78]
0x18001d90e  mov     [rsp+140h+var_100], rax
0x18001d913  lea     rax, [rbp+var_30]
0x18001d917  mov     [rsp+140h+var_108], rax
0x18001d91c  lea     rax, [rbp+var_74]
0x18001d920  mov     [rbp+var_70], rcx
0x18001d924  mov     ecx, [rdi+44h]
0x18001d927  mov     [rsp+140h+var_110], rax
0x18001d92c  lea     rax, [rbp+var_28]
0x18001d930  mov     [rbp+arg_0], ecx
0x18001d933  mov     ecx, [rdi+10h]
0x18001d936  mov     [rbp+arg_8], ecx
0x18001d939  mov     rcx, [rdi+78h]
0x18001d93d  mov     [rsp+140h+var_118], rax
0x18001d942  lea     rax, [rbp+var_20]
0x18001d946  mov     [rbp+var_68], rcx
0x18001d94a  mov     rcx, r9
0x18001d94d  mov     [rsp+140h+var_120], rax
0x18001d952  mov     [rbp+var_28], 1000000h
0x18001d95a  mov     [rbp+var_20], 0
0x18001d962  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001d967  jmp     short loc_18001D9CD
0x18001d969  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001d96e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001d973  mov     rdi, rax
0x18001d976  mov     ecx, [rax]
0x18001d978  cmp     ecx, 5
0x18001d97b  jbe     short loc_18001D9CD
0x18001d97d  call    cs:__imp_GetCurrentThreadId
0x18001d983  mov     r8, [rbx+110h]
0x18001d98a  lea     rdx, unk_180042090
0x18001d991  mov     [rbp+arg_0], eax
0x18001d994  xor     r9d, r9d
0x18001d997  lea     rax, [rbp+arg_0]
0x18001d99b  mov     [rsp+140h+var_110], rax
0x18001d9a0  lea     rax, [rbp+arg_8]
0x18001d9a4  mov     ecx, [r8+48h]
0x18001d9a8  add     r8, 8
0x18001d9ac  mov     [rsp+140h+var_118], rax
0x18001d9b1  lea     rax, [rbp+arg_10]
0x18001d9b5  mov     [rbp+arg_8], ecx
0x18001d9b8  mov     rcx, rdi
0x18001d9bb  mov     [rsp+140h+var_120], rax
0x18001d9c0  mov     [rbp+arg_10], 0
0x18001d9c8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d9cd  mov     rcx, rbx
0x18001d9d0  add     rsp, 130h
0x18001d9d7  pop     rdi
0x18001d9d8  pop     rbx
0x18001d9d9  pop     rbp
0x18001d9da  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

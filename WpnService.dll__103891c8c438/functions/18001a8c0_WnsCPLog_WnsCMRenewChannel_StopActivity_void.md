# WnsCPLog::WnsCMRenewChannel::StopActivity(void)

- ea: `0x18001a8c0`
- end: `0x18001aaef`
- name: `?StopActivity@WnsCMRenewChannel@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMRenewChannel *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18001a8c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aa8d`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRenewChannel::StopActivity(WnsCPLog::WnsCMRenewChannel *this)
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
        (unsigned __int8 *)byte_18003ECEF,
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
        (unsigned __int8 *)byte_18003EC9D,
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
0x18001a8c0  push    rbp
0x18001a8c2  push    rbx
0x18001a8c3  push    rdi
0x18001a8c4  lea     rbp, [rsp+10h]
0x18001a8c9  sub     rsp, 130h
0x18001a8d0  mov     rdi, [rcx+110h]
0x18001a8d7  mov     rbx, rcx
0x18001a8da  mov     eax, [rdi+48h]
0x18001a8dd  test    eax, eax
0x18001a8df  jns     loc_18001AA79
0x18001a8e5  add     rdi, 50h ; 'P'
0x18001a8e9  cmp     eax, [rdi+8]
0x18001a8ec  jnz     loc_18001AA79
0x18001a8f2  test    rdi, rdi
0x18001a8f5  jz      loc_18001AA79
0x18001a8fb  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a900  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001a905  mov     r9, rax
0x18001a908  mov     ecx, [rax]
0x18001a90a  cmp     ecx, 5
0x18001a90d  jbe     loc_18001AADD
0x18001a913  mov     rax, [rdi+70h]
0x18001a917  lea     rdx, byte_18003ECEF
0x18001a91e  mov     rcx, [rdi+30h]
0x18001a922  mov     [rbp+var_60], rax
0x18001a926  mov     eax, [rdi+68h]
0x18001a929  mov     r8, [rbx+110h]
0x18001a930  mov     dword ptr [rbp+arg_10], eax
0x18001a933  add     r8, 8
0x18001a937  mov     rax, [rdi+60h]
0x18001a93b  mov     [rbp+var_58], rax
0x18001a93f  mov     rax, [rdi+58h]
0x18001a943  mov     [rbp+var_50], rax
0x18001a947  mov     eax, [rdi+50h]
0x18001a94a  mov     [rbp+arg_18], eax
0x18001a94d  mov     rax, [rdi+48h]
0x18001a951  mov     [rbp+var_48], rax
0x18001a955  mov     eax, [rdi+20h]
0x18001a958  mov     [rbp+var_80], eax
0x18001a95b  mov     rax, [rdi+18h]
0x18001a95f  mov     [rbp+var_40], rax
0x18001a963  mov     eax, [rdi]
0x18001a965  mov     [rbp+var_7C], eax
0x18001a968  mov     rax, [rdi+80h]
0x18001a96f  mov     [rbp+var_38], rax
0x18001a973  mov     eax, [rdi+40h]
0x18001a976  mov     [rbp+var_78], eax
0x18001a979  mov     rax, [rdi+38h]
0x18001a97d  mov     [rbp+var_30], rax
0x18001a981  mov     eax, [rdi+8]
0x18001a984  mov     [rbp+var_74], eax
0x18001a987  lea     rax, [rbp+var_70]
0x18001a98b  mov     [rsp+140h+var_90], rax
0x18001a993  lea     rax, [rbp+arg_0]
0x18001a997  mov     [rsp+140h+var_98], rax
0x18001a99f  lea     rax, [rbp+arg_8]
0x18001a9a3  mov     [rsp+140h+var_A0], rax
0x18001a9ab  lea     rax, [rbp+var_68]
0x18001a9af  mov     [rsp+140h+var_A8], rax
0x18001a9b7  lea     rax, [rbp+var_60]
0x18001a9bb  mov     [rsp+140h+var_B0], rax
0x18001a9c3  lea     rax, [rbp+arg_10]
0x18001a9c7  mov     [rsp+140h+var_B8], rax
0x18001a9cf  lea     rax, [rbp+var_58]
0x18001a9d3  mov     [rsp+140h+var_C0], rax
0x18001a9db  lea     rax, [rbp+var_50]
0x18001a9df  mov     [rsp+140h+var_C8], rax
0x18001a9e4  lea     rax, [rbp+arg_18]
0x18001a9e8  mov     [rsp+140h+var_D0], rax
0x18001a9ed  lea     rax, [rbp+var_48]
0x18001a9f1  mov     [rsp+140h+var_D8], rax
0x18001a9f6  lea     rax, [rbp+var_80]
0x18001a9fa  mov     [rsp+140h+var_E0], rax
0x18001a9ff  lea     rax, [rbp+var_40]
0x18001aa03  mov     [rsp+140h+var_E8], rax
0x18001aa08  lea     rax, [rbp+var_7C]
0x18001aa0c  mov     [rsp+140h+var_F0], rax
0x18001aa11  lea     rax, [rbp+var_38]
0x18001aa15  mov     [rsp+140h+var_F8], rax
0x18001aa1a  lea     rax, [rbp+var_78]
0x18001aa1e  mov     [rsp+140h+var_100], rax
0x18001aa23  lea     rax, [rbp+var_30]
0x18001aa27  mov     [rsp+140h+var_108], rax
0x18001aa2c  lea     rax, [rbp+var_74]
0x18001aa30  mov     [rbp+var_70], rcx
0x18001aa34  mov     ecx, [rdi+44h]
0x18001aa37  mov     [rsp+140h+var_110], rax
0x18001aa3c  lea     rax, [rbp+var_28]
0x18001aa40  mov     [rbp+arg_0], ecx
0x18001aa43  mov     ecx, [rdi+10h]
0x18001aa46  mov     [rbp+arg_8], ecx
0x18001aa49  mov     rcx, [rdi+78h]
0x18001aa4d  mov     [rsp+140h+var_118], rax
0x18001aa52  lea     rax, [rbp+var_20]
0x18001aa56  mov     [rbp+var_68], rcx
0x18001aa5a  mov     rcx, r9
0x18001aa5d  mov     [rsp+140h+var_120], rax
0x18001aa62  mov     [rbp+var_28], 1000000h
0x18001aa6a  mov     [rbp+var_20], 0
0x18001aa72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001aa77  jmp     short loc_18001AADD
0x18001aa79  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aa7e  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001aa83  mov     rdi, rax
0x18001aa86  mov     ecx, [rax]
0x18001aa88  cmp     ecx, 5
0x18001aa8b  jbe     short loc_18001AADD
0x18001aa8d  call    cs:__imp_GetCurrentThreadId
0x18001aa93  mov     r8, [rbx+110h]
0x18001aa9a  lea     rdx, byte_18003EC9D
0x18001aaa1  mov     [rbp+arg_0], eax
0x18001aaa4  xor     r9d, r9d
0x18001aaa7  lea     rax, [rbp+arg_0]
0x18001aaab  mov     [rsp+140h+var_110], rax
0x18001aab0  lea     rax, [rbp+arg_8]
0x18001aab4  mov     ecx, [r8+48h]
0x18001aab8  add     r8, 8
0x18001aabc  mov     [rsp+140h+var_118], rax
0x18001aac1  lea     rax, [rbp+arg_10]
0x18001aac5  mov     [rbp+arg_8], ecx
0x18001aac8  mov     rcx, rdi
0x18001aacb  mov     [rsp+140h+var_120], rax
0x18001aad0  mov     [rbp+arg_10], 0
0x18001aad8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001aadd  mov     rcx, rbx
0x18001aae0  add     rsp, 130h
0x18001aae7  pop     rdi
0x18001aae8  pop     rbx
0x18001aae9  pop     rbp
0x18001aaea  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

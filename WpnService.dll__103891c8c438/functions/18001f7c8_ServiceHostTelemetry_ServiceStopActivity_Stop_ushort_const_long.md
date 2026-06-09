# ServiceHostTelemetry::ServiceStopActivity::Stop(ushort const *,long)

- ea: `0x18001f7c8`
- end: `0x18001fa45`
- name: `?Stop@ServiceStopActivity@ServiceHostTelemetry@@QEAAXPEBGJ@Z`
- size: `637`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001f588`

## callees

- `0x1800023d8`
- `0x1800026d4`
- `0x18000f270`
- `0x180016b74`
- `0x1800172bc`
- `0x180018430`
- `0x18001f7c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f9cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f9cb`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::Stop(
        ServiceHostTelemetry::ServiceStopActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v3; // rdi
  int v6; // eax
  int *v7; // rdi
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+B0h] [rbp-80h] BYREF
  int v20; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v23; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v25; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v31; // [rsp+100h] [rbp-30h] BYREF
  __int64 v32; // [rsp+108h] [rbp-28h] BYREF
  _QWORD v33[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v34; // [rsp+140h] [rbp+10h] BYREF
  int v35; // [rsp+150h] [rbp+20h]
  int v36; // [rsp+158h] [rbp+28h] BYREF

  v35 = a3;
  v3 = *((_QWORD *)this + 34);
  v6 = *(_DWORD *)(v3 + 72);
  if ( v6 < 0 && (v7 = (int *)(v3 + 80), v6 == v7[2]) && v7 )
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = ServiceHostLogging::Provider();
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v9, v8) )
    {
      v26 = *((_QWORD *)v7 + 15);
      v27 = *((_QWORD *)v7 + 14);
      v11 = *((_QWORD *)this + 34);
      v34 = v7[26];
      v28 = *((_QWORD *)v7 + 12);
      v29 = *((_QWORD *)v7 + 11);
      v36 = v7[20];
      v30 = *((_QWORD *)v7 + 9);
      v19 = v7[8];
      v31 = *((_QWORD *)v7 + 3);
      v20 = *v7;
      v32 = *((_QWORD *)v7 + 16);
      v21 = v7[16];
      v33[0] = *((_QWORD *)v7 + 7);
      v22 = v7[2];
      v23 = 0x1000000;
      v24 = 0x1000000;
      v35 = 0;
      v25 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)byte_18003D0F3,
        v11 + 8,
        v10,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v22,
        v33,
        (__int64)&v21,
        &v32,
        (__int64)&v20,
        &v31,
        (__int64)&v19,
        &v30,
        (__int64)&v36,
        &v29,
        &v28,
        (__int64)&v34,
        &v27,
        &v26,
        &v25);
    }
  }
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = ServiceHostLogging::Provider();
    v15 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13, v14) )
    {
      v35 = 0;
      v24 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v34 = CurrentThreadId;
      v36 = *(_DWORD *)(v17 + 72);
      v23 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)&word_18003D08E,
        v17 + 8,
        v18,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v34,
        &v24);
    }
  }
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001f7c8  mov     [rsp-8+arg_8], rbx
0x18001f7cd  mov     [rsp-8+arg_10], r8d
0x18001f7d2  push    rbp
0x18001f7d3  push    rsi
0x18001f7d4  push    rdi
0x18001f7d5  lea     rbp, [rsp+10h]
0x18001f7da  sub     rsp, 120h
0x18001f7e1  mov     rdi, [rcx+110h]
0x18001f7e8  mov     rsi, rdx
0x18001f7eb  mov     rbx, rcx
0x18001f7ee  mov     eax, [rdi+48h]
0x18001f7f1  test    eax, eax
0x18001f7f3  jns     loc_18001F992
0x18001f7f9  add     rdi, 50h ; 'P'
0x18001f7fd  cmp     eax, [rdi+8]
0x18001f800  jnz     loc_18001F992
0x18001f806  test    rdi, rdi
0x18001f809  jz      loc_18001F992
0x18001f80f  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f814  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18001f819  mov     r9, rax
0x18001f81c  mov     ecx, [rax]
0x18001f81e  cmp     ecx, 5
0x18001f821  jbe     loc_18001FA2B
0x18001f827  mov     rdx, 400000000000h
0x18001f831  mov     rcx, rax
0x18001f834  call    _tlgKeywordOn
0x18001f839  test    al, al
0x18001f83b  jz      loc_18001FA2B
0x18001f841  mov     rax, [rdi+78h]
0x18001f845  lea     rdx, byte_18003D0F3
0x18001f84c  mov     [rbp+var_58], rax
0x18001f850  mov     rcx, r9
0x18001f853  mov     rax, [rdi+70h]
0x18001f857  mov     [rbp+var_50], rax
0x18001f85b  mov     eax, [rdi+68h]
0x18001f85e  mov     r8, [rbx+110h]
0x18001f865  mov     [rbp+arg_0], eax
0x18001f868  add     r8, 8
0x18001f86c  mov     rax, [rdi+60h]
0x18001f870  mov     [rbp+var_48], rax
0x18001f874  mov     rax, [rdi+58h]
0x18001f878  mov     [rbp+var_40], rax
0x18001f87c  mov     eax, [rdi+50h]
0x18001f87f  mov     [rbp+arg_18], eax
0x18001f882  mov     rax, [rdi+48h]
0x18001f886  mov     [rbp+var_38], rax
0x18001f88a  mov     eax, [rdi+20h]
0x18001f88d  mov     [rbp+var_80], eax
0x18001f890  mov     rax, [rdi+18h]
0x18001f894  mov     [rbp+var_30], rax
0x18001f898  mov     eax, [rdi]
0x18001f89a  mov     [rbp+var_7C], eax
0x18001f89d  mov     rax, [rdi+80h]
0x18001f8a4  mov     [rbp+var_28], rax
0x18001f8a8  mov     eax, [rdi+40h]
0x18001f8ab  mov     [rbp+var_78], eax
0x18001f8ae  mov     rax, [rdi+38h]
0x18001f8b2  mov     [rbp+var_20], rax
0x18001f8b6  mov     eax, [rdi+8]
0x18001f8b9  mov     [rbp+var_74], eax
0x18001f8bc  mov     eax, 1000000h
0x18001f8c1  mov     [rbp+var_70], rax
0x18001f8c5  mov     [rbp+var_68], rax
0x18001f8c9  lea     rax, [rbp+arg_10]
0x18001f8cd  mov     [rsp+130h+var_88], rax
0x18001f8d5  lea     rax, [rbp+var_60]
0x18001f8d9  mov     [rsp+130h+var_90], rax
0x18001f8e1  lea     rax, [rbp+var_58]
0x18001f8e5  mov     [rsp+130h+var_98], rax
0x18001f8ed  lea     rax, [rbp+var_50]
0x18001f8f1  mov     [rsp+130h+var_A0], rax
0x18001f8f9  lea     rax, [rbp+arg_0]
0x18001f8fd  mov     [rsp+130h+var_A8], rax
0x18001f905  lea     rax, [rbp+var_48]
0x18001f909  mov     [rsp+130h+var_B0], rax
0x18001f911  lea     rax, [rbp+var_40]
0x18001f915  mov     [rsp+130h+var_B8], rax
0x18001f91a  lea     rax, [rbp+arg_18]
0x18001f91e  mov     [rsp+130h+var_C0], rax
0x18001f923  lea     rax, [rbp+var_38]
0x18001f927  mov     [rsp+130h+var_C8], rax
0x18001f92c  lea     rax, [rbp+var_80]
0x18001f930  mov     [rsp+130h+var_D0], rax
0x18001f935  lea     rax, [rbp+var_30]
0x18001f939  mov     [rsp+130h+var_D8], rax
0x18001f93e  lea     rax, [rbp+var_7C]
0x18001f942  mov     [rsp+130h+var_E0], rax
0x18001f947  lea     rax, [rbp+var_28]
0x18001f94b  mov     [rsp+130h+var_E8], rax
0x18001f950  lea     rax, [rbp+var_78]
0x18001f954  mov     [rsp+130h+var_F0], rax
0x18001f959  lea     rax, [rbp+var_20]
0x18001f95d  mov     [rsp+130h+var_F8], rax
0x18001f962  lea     rax, [rbp+var_74]
0x18001f966  mov     [rsp+130h+var_100], rax
0x18001f96b  lea     rax, [rbp+var_70]
0x18001f96f  mov     [rsp+130h+var_108], rax
0x18001f974  lea     rax, [rbp+var_68]
0x18001f978  mov     [rsp+130h+var_110], rax
0x18001f97d  mov     [rbp+arg_10], 0
0x18001f984  mov     [rbp+var_60], rsi
0x18001f988  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001f98d  jmp     loc_18001FA2B
0x18001f992  call    ?zInternalStop@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f997  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18001f99c  mov     rdi, rax
0x18001f99f  mov     ecx, [rax]
0x18001f9a1  cmp     ecx, 5
0x18001f9a4  jbe     loc_18001FA2B
0x18001f9aa  mov     rdx, 400000000000h
0x18001f9b4  mov     rcx, rax
0x18001f9b7  call    _tlgKeywordOn
0x18001f9bc  test    al, al
0x18001f9be  jz      short loc_18001FA2B
0x18001f9c0  mov     [rbp+arg_10], 0
0x18001f9c7  mov     [rbp+var_68], rsi
0x18001f9cb  call    cs:__imp_GetCurrentThreadId
0x18001f9d1  mov     r8, [rbx+110h]
0x18001f9d8  lea     rdx, word_18003D08E
0x18001f9df  mov     [rbp+arg_0], eax
0x18001f9e2  mov     rcx, rdi
0x18001f9e5  mov     eax, [r8+48h]
0x18001f9e9  add     r8, 8
0x18001f9ed  mov     [rbp+arg_18], eax
0x18001f9f0  mov     eax, 1000000h
0x18001f9f5  mov     [rbp+var_70], rax
0x18001f9f9  lea     rax, [rbp+arg_10]
0x18001f9fd  mov     [rsp+130h+var_F0], rax
0x18001fa02  lea     rax, [rbp+var_68]
0x18001fa06  mov     [rsp+130h+var_F8], rax
0x18001fa0b  lea     rax, [rbp+arg_0]
0x18001fa0f  mov     [rsp+130h+var_100], rax
0x18001fa14  lea     rax, [rbp+arg_18]
0x18001fa18  mov     [rsp+130h+var_108], rax
0x18001fa1d  lea     rax, [rbp+var_70]
0x18001fa21  mov     [rsp+130h+var_110], rax
0x18001fa26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001fa2b  mov     rcx, rbx
0x18001fa2e  mov     rbx, [rsp+130h+arg_8]
0x18001fa36  add     rsp, 120h
0x18001fa3d  pop     rdi
0x18001fa3e  pop     rsi
0x18001fa3f  pop     rbp
0x18001fa40  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

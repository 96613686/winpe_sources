# WnsCPLog::WnsCMConnectivityProbe::StopActivity(void)

- ea: `0x18002ee30`
- end: `0x18002f05f`
- name: `?StopActivity@WnsCMConnectivityProbe@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMConnectivityProbe *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18002ee30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002effd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002effd`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConnectivityProbe::StopActivity(WnsCPLog::WnsCMConnectivityProbe *this)
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
        (unsigned __int8 *)byte_18003EEE9,
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
        (unsigned __int8 *)word_18003EE92,
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
0x18002ee30  push    rbp
0x18002ee32  push    rbx
0x18002ee33  push    rdi
0x18002ee34  lea     rbp, [rsp+10h]
0x18002ee39  sub     rsp, 130h
0x18002ee40  mov     rdi, [rcx+110h]
0x18002ee47  mov     rbx, rcx
0x18002ee4a  mov     eax, [rdi+48h]
0x18002ee4d  test    eax, eax
0x18002ee4f  jns     loc_18002EFE9
0x18002ee55  add     rdi, 50h ; 'P'
0x18002ee59  cmp     eax, [rdi+8]
0x18002ee5c  jnz     loc_18002EFE9
0x18002ee62  test    rdi, rdi
0x18002ee65  jz      loc_18002EFE9
0x18002ee6b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002ee70  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002ee75  mov     r9, rax
0x18002ee78  mov     ecx, [rax]
0x18002ee7a  cmp     ecx, 5
0x18002ee7d  jbe     loc_18002F04D
0x18002ee83  mov     rax, [rdi+70h]
0x18002ee87  lea     rdx, byte_18003EEE9
0x18002ee8e  mov     rcx, [rdi+30h]
0x18002ee92  mov     [rbp+var_60], rax
0x18002ee96  mov     eax, [rdi+68h]
0x18002ee99  mov     r8, [rbx+110h]
0x18002eea0  mov     dword ptr [rbp+arg_10], eax
0x18002eea3  add     r8, 8
0x18002eea7  mov     rax, [rdi+60h]
0x18002eeab  mov     [rbp+var_58], rax
0x18002eeaf  mov     rax, [rdi+58h]
0x18002eeb3  mov     [rbp+var_50], rax
0x18002eeb7  mov     eax, [rdi+50h]
0x18002eeba  mov     [rbp+arg_18], eax
0x18002eebd  mov     rax, [rdi+48h]
0x18002eec1  mov     [rbp+var_48], rax
0x18002eec5  mov     eax, [rdi+20h]
0x18002eec8  mov     [rbp+var_80], eax
0x18002eecb  mov     rax, [rdi+18h]
0x18002eecf  mov     [rbp+var_40], rax
0x18002eed3  mov     eax, [rdi]
0x18002eed5  mov     [rbp+var_7C], eax
0x18002eed8  mov     rax, [rdi+80h]
0x18002eedf  mov     [rbp+var_38], rax
0x18002eee3  mov     eax, [rdi+40h]
0x18002eee6  mov     [rbp+var_78], eax
0x18002eee9  mov     rax, [rdi+38h]
0x18002eeed  mov     [rbp+var_30], rax
0x18002eef1  mov     eax, [rdi+8]
0x18002eef4  mov     [rbp+var_74], eax
0x18002eef7  lea     rax, [rbp+var_70]
0x18002eefb  mov     [rsp+140h+var_90], rax
0x18002ef03  lea     rax, [rbp+arg_0]
0x18002ef07  mov     [rsp+140h+var_98], rax
0x18002ef0f  lea     rax, [rbp+arg_8]
0x18002ef13  mov     [rsp+140h+var_A0], rax
0x18002ef1b  lea     rax, [rbp+var_68]
0x18002ef1f  mov     [rsp+140h+var_A8], rax
0x18002ef27  lea     rax, [rbp+var_60]
0x18002ef2b  mov     [rsp+140h+var_B0], rax
0x18002ef33  lea     rax, [rbp+arg_10]
0x18002ef37  mov     [rsp+140h+var_B8], rax
0x18002ef3f  lea     rax, [rbp+var_58]
0x18002ef43  mov     [rsp+140h+var_C0], rax
0x18002ef4b  lea     rax, [rbp+var_50]
0x18002ef4f  mov     [rsp+140h+var_C8], rax
0x18002ef54  lea     rax, [rbp+arg_18]
0x18002ef58  mov     [rsp+140h+var_D0], rax
0x18002ef5d  lea     rax, [rbp+var_48]
0x18002ef61  mov     [rsp+140h+var_D8], rax
0x18002ef66  lea     rax, [rbp+var_80]
0x18002ef6a  mov     [rsp+140h+var_E0], rax
0x18002ef6f  lea     rax, [rbp+var_40]
0x18002ef73  mov     [rsp+140h+var_E8], rax
0x18002ef78  lea     rax, [rbp+var_7C]
0x18002ef7c  mov     [rsp+140h+var_F0], rax
0x18002ef81  lea     rax, [rbp+var_38]
0x18002ef85  mov     [rsp+140h+var_F8], rax
0x18002ef8a  lea     rax, [rbp+var_78]
0x18002ef8e  mov     [rsp+140h+var_100], rax
0x18002ef93  lea     rax, [rbp+var_30]
0x18002ef97  mov     [rsp+140h+var_108], rax
0x18002ef9c  lea     rax, [rbp+var_74]
0x18002efa0  mov     [rbp+var_70], rcx
0x18002efa4  mov     ecx, [rdi+44h]
0x18002efa7  mov     [rsp+140h+var_110], rax
0x18002efac  lea     rax, [rbp+var_28]
0x18002efb0  mov     [rbp+arg_0], ecx
0x18002efb3  mov     ecx, [rdi+10h]
0x18002efb6  mov     [rbp+arg_8], ecx
0x18002efb9  mov     rcx, [rdi+78h]
0x18002efbd  mov     [rsp+140h+var_118], rax
0x18002efc2  lea     rax, [rbp+var_20]
0x18002efc6  mov     [rbp+var_68], rcx
0x18002efca  mov     rcx, r9
0x18002efcd  mov     [rsp+140h+var_120], rax
0x18002efd2  mov     [rbp+var_28], 1000000h
0x18002efda  mov     [rbp+var_20], 0
0x18002efe2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002efe7  jmp     short loc_18002F04D
0x18002efe9  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002efee  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002eff3  mov     rdi, rax
0x18002eff6  mov     ecx, [rax]
0x18002eff8  cmp     ecx, 5
0x18002effb  jbe     short loc_18002F04D
0x18002effd  call    cs:__imp_GetCurrentThreadId
0x18002f003  mov     r8, [rbx+110h]
0x18002f00a  lea     rdx, word_18003EE92
0x18002f011  mov     [rbp+arg_0], eax
0x18002f014  xor     r9d, r9d
0x18002f017  lea     rax, [rbp+arg_0]
0x18002f01b  mov     [rsp+140h+var_110], rax
0x18002f020  lea     rax, [rbp+arg_8]
0x18002f024  mov     ecx, [r8+48h]
0x18002f028  add     r8, 8
0x18002f02c  mov     [rsp+140h+var_118], rax
0x18002f031  lea     rax, [rbp+arg_10]
0x18002f035  mov     [rbp+arg_8], ecx
0x18002f038  mov     rcx, rdi
0x18002f03b  mov     [rsp+140h+var_120], rax
0x18002f040  mov     [rbp+arg_10], 0
0x18002f048  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f04d  mov     rcx, rbx
0x18002f050  add     rsp, 130h
0x18002f057  pop     rdi
0x18002f058  pop     rbx
0x18002f059  pop     rbp
0x18002f05a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

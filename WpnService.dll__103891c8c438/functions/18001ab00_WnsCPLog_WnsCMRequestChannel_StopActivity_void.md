# WnsCPLog::WnsCMRequestChannel::StopActivity(void)

- ea: `0x18001ab00`
- end: `0x18001ad2f`
- name: `?StopActivity@WnsCMRequestChannel@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsCMRequestChannel *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x18001ab00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001accd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001accd`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMRequestChannel::StopActivity(WnsCPLog::WnsCMRequestChannel *this)
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
        (unsigned __int8 *)byte_18003F107,
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
        (unsigned __int8 *)byte_18003F0B3,
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
0x18001ab00  push    rbp
0x18001ab02  push    rbx
0x18001ab03  push    rdi
0x18001ab04  lea     rbp, [rsp+10h]
0x18001ab09  sub     rsp, 130h
0x18001ab10  mov     rdi, [rcx+110h]
0x18001ab17  mov     rbx, rcx
0x18001ab1a  mov     eax, [rdi+48h]
0x18001ab1d  test    eax, eax
0x18001ab1f  jns     loc_18001ACB9
0x18001ab25  add     rdi, 50h ; 'P'
0x18001ab29  cmp     eax, [rdi+8]
0x18001ab2c  jnz     loc_18001ACB9
0x18001ab32  test    rdi, rdi
0x18001ab35  jz      loc_18001ACB9
0x18001ab3b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001ab40  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001ab45  mov     r9, rax
0x18001ab48  mov     ecx, [rax]
0x18001ab4a  cmp     ecx, 5
0x18001ab4d  jbe     loc_18001AD1D
0x18001ab53  mov     rax, [rdi+70h]
0x18001ab57  lea     rdx, byte_18003F107
0x18001ab5e  mov     rcx, [rdi+30h]
0x18001ab62  mov     [rbp+var_60], rax
0x18001ab66  mov     eax, [rdi+68h]
0x18001ab69  mov     r8, [rbx+110h]
0x18001ab70  mov     dword ptr [rbp+arg_10], eax
0x18001ab73  add     r8, 8
0x18001ab77  mov     rax, [rdi+60h]
0x18001ab7b  mov     [rbp+var_58], rax
0x18001ab7f  mov     rax, [rdi+58h]
0x18001ab83  mov     [rbp+var_50], rax
0x18001ab87  mov     eax, [rdi+50h]
0x18001ab8a  mov     [rbp+arg_18], eax
0x18001ab8d  mov     rax, [rdi+48h]
0x18001ab91  mov     [rbp+var_48], rax
0x18001ab95  mov     eax, [rdi+20h]
0x18001ab98  mov     [rbp+var_80], eax
0x18001ab9b  mov     rax, [rdi+18h]
0x18001ab9f  mov     [rbp+var_40], rax
0x18001aba3  mov     eax, [rdi]
0x18001aba5  mov     [rbp+var_7C], eax
0x18001aba8  mov     rax, [rdi+80h]
0x18001abaf  mov     [rbp+var_38], rax
0x18001abb3  mov     eax, [rdi+40h]
0x18001abb6  mov     [rbp+var_78], eax
0x18001abb9  mov     rax, [rdi+38h]
0x18001abbd  mov     [rbp+var_30], rax
0x18001abc1  mov     eax, [rdi+8]
0x18001abc4  mov     [rbp+var_74], eax
0x18001abc7  lea     rax, [rbp+var_70]
0x18001abcb  mov     [rsp+140h+var_90], rax
0x18001abd3  lea     rax, [rbp+arg_0]
0x18001abd7  mov     [rsp+140h+var_98], rax
0x18001abdf  lea     rax, [rbp+arg_8]
0x18001abe3  mov     [rsp+140h+var_A0], rax
0x18001abeb  lea     rax, [rbp+var_68]
0x18001abef  mov     [rsp+140h+var_A8], rax
0x18001abf7  lea     rax, [rbp+var_60]
0x18001abfb  mov     [rsp+140h+var_B0], rax
0x18001ac03  lea     rax, [rbp+arg_10]
0x18001ac07  mov     [rsp+140h+var_B8], rax
0x18001ac0f  lea     rax, [rbp+var_58]
0x18001ac13  mov     [rsp+140h+var_C0], rax
0x18001ac1b  lea     rax, [rbp+var_50]
0x18001ac1f  mov     [rsp+140h+var_C8], rax
0x18001ac24  lea     rax, [rbp+arg_18]
0x18001ac28  mov     [rsp+140h+var_D0], rax
0x18001ac2d  lea     rax, [rbp+var_48]
0x18001ac31  mov     [rsp+140h+var_D8], rax
0x18001ac36  lea     rax, [rbp+var_80]
0x18001ac3a  mov     [rsp+140h+var_E0], rax
0x18001ac3f  lea     rax, [rbp+var_40]
0x18001ac43  mov     [rsp+140h+var_E8], rax
0x18001ac48  lea     rax, [rbp+var_7C]
0x18001ac4c  mov     [rsp+140h+var_F0], rax
0x18001ac51  lea     rax, [rbp+var_38]
0x18001ac55  mov     [rsp+140h+var_F8], rax
0x18001ac5a  lea     rax, [rbp+var_78]
0x18001ac5e  mov     [rsp+140h+var_100], rax
0x18001ac63  lea     rax, [rbp+var_30]
0x18001ac67  mov     [rsp+140h+var_108], rax
0x18001ac6c  lea     rax, [rbp+var_74]
0x18001ac70  mov     [rbp+var_70], rcx
0x18001ac74  mov     ecx, [rdi+44h]
0x18001ac77  mov     [rsp+140h+var_110], rax
0x18001ac7c  lea     rax, [rbp+var_28]
0x18001ac80  mov     [rbp+arg_0], ecx
0x18001ac83  mov     ecx, [rdi+10h]
0x18001ac86  mov     [rbp+arg_8], ecx
0x18001ac89  mov     rcx, [rdi+78h]
0x18001ac8d  mov     [rsp+140h+var_118], rax
0x18001ac92  lea     rax, [rbp+var_20]
0x18001ac96  mov     [rbp+var_68], rcx
0x18001ac9a  mov     rcx, r9
0x18001ac9d  mov     [rsp+140h+var_120], rax
0x18001aca2  mov     [rbp+var_28], 1000000h
0x18001acaa  mov     [rbp+var_20], 0
0x18001acb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001acb7  jmp     short loc_18001AD1D
0x18001acb9  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001acbe  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18001acc3  mov     rdi, rax
0x18001acc6  mov     ecx, [rax]
0x18001acc8  cmp     ecx, 5
0x18001accb  jbe     short loc_18001AD1D
0x18001accd  call    cs:__imp_GetCurrentThreadId
0x18001acd3  mov     r8, [rbx+110h]
0x18001acda  lea     rdx, byte_18003F0B3
0x18001ace1  mov     [rbp+arg_0], eax
0x18001ace4  xor     r9d, r9d
0x18001ace7  lea     rax, [rbp+arg_0]
0x18001aceb  mov     [rsp+140h+var_110], rax
0x18001acf0  lea     rax, [rbp+arg_8]
0x18001acf4  mov     ecx, [r8+48h]
0x18001acf8  add     r8, 8
0x18001acfc  mov     [rsp+140h+var_118], rax
0x18001ad01  lea     rax, [rbp+arg_10]
0x18001ad05  mov     [rbp+arg_8], ecx
0x18001ad08  mov     rcx, rdi
0x18001ad0b  mov     [rsp+140h+var_120], rax
0x18001ad10  mov     [rbp+arg_10], 0
0x18001ad18  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ad1d  mov     rcx, rbx
0x18001ad20  add     rsp, 130h
0x18001ad27  pop     rdi
0x18001ad28  pop     rbx
0x18001ad29  pop     rbp
0x18001ad2a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

# WnsCPLog::WnsSinkUnadviseCP::StopActivity(void)

- ea: `0x180033d00`
- end: `0x180033f2f`
- name: `?StopActivity@WnsSinkUnadviseCP@WnsCPLog@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(WnsCPLog::WnsSinkUnadviseCP *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000d830`
- `0x18000f270`
- `0x18000f2f0`
- `0x180010dd0`
- `0x180010e90`
- `0x180033d00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033ecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033ecd`

## pseudocode

```c
void __fastcall WnsCPLog::WnsSinkUnadviseCP::StopActivity(WnsCPLog::WnsSinkUnadviseCP *this)
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
        (unsigned __int8 *)byte_180041CF7,
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
        (unsigned __int8 *)byte_180041CA5,
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
0x180033d00  push    rbp
0x180033d02  push    rbx
0x180033d03  push    rdi
0x180033d04  lea     rbp, [rsp+10h]
0x180033d09  sub     rsp, 130h
0x180033d10  mov     rdi, [rcx+110h]
0x180033d17  mov     rbx, rcx
0x180033d1a  mov     eax, [rdi+48h]
0x180033d1d  test    eax, eax
0x180033d1f  jns     loc_180033EB9
0x180033d25  add     rdi, 50h ; 'P'
0x180033d29  cmp     eax, [rdi+8]
0x180033d2c  jnz     loc_180033EB9
0x180033d32  test    rdi, rdi
0x180033d35  jz      loc_180033EB9
0x180033d3b  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180033d40  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033d45  mov     r9, rax
0x180033d48  mov     ecx, [rax]
0x180033d4a  cmp     ecx, 5
0x180033d4d  jbe     loc_180033F1D
0x180033d53  mov     rax, [rdi+70h]
0x180033d57  lea     rdx, byte_180041CF7
0x180033d5e  mov     rcx, [rdi+30h]
0x180033d62  mov     [rbp+var_60], rax
0x180033d66  mov     eax, [rdi+68h]
0x180033d69  mov     r8, [rbx+110h]
0x180033d70  mov     dword ptr [rbp+arg_10], eax
0x180033d73  add     r8, 8
0x180033d77  mov     rax, [rdi+60h]
0x180033d7b  mov     [rbp+var_58], rax
0x180033d7f  mov     rax, [rdi+58h]
0x180033d83  mov     [rbp+var_50], rax
0x180033d87  mov     eax, [rdi+50h]
0x180033d8a  mov     [rbp+arg_18], eax
0x180033d8d  mov     rax, [rdi+48h]
0x180033d91  mov     [rbp+var_48], rax
0x180033d95  mov     eax, [rdi+20h]
0x180033d98  mov     [rbp+var_80], eax
0x180033d9b  mov     rax, [rdi+18h]
0x180033d9f  mov     [rbp+var_40], rax
0x180033da3  mov     eax, [rdi]
0x180033da5  mov     [rbp+var_7C], eax
0x180033da8  mov     rax, [rdi+80h]
0x180033daf  mov     [rbp+var_38], rax
0x180033db3  mov     eax, [rdi+40h]
0x180033db6  mov     [rbp+var_78], eax
0x180033db9  mov     rax, [rdi+38h]
0x180033dbd  mov     [rbp+var_30], rax
0x180033dc1  mov     eax, [rdi+8]
0x180033dc4  mov     [rbp+var_74], eax
0x180033dc7  lea     rax, [rbp+var_70]
0x180033dcb  mov     [rsp+140h+var_90], rax
0x180033dd3  lea     rax, [rbp+arg_0]
0x180033dd7  mov     [rsp+140h+var_98], rax
0x180033ddf  lea     rax, [rbp+arg_8]
0x180033de3  mov     [rsp+140h+var_A0], rax
0x180033deb  lea     rax, [rbp+var_68]
0x180033def  mov     [rsp+140h+var_A8], rax
0x180033df7  lea     rax, [rbp+var_60]
0x180033dfb  mov     [rsp+140h+var_B0], rax
0x180033e03  lea     rax, [rbp+arg_10]
0x180033e07  mov     [rsp+140h+var_B8], rax
0x180033e0f  lea     rax, [rbp+var_58]
0x180033e13  mov     [rsp+140h+var_C0], rax
0x180033e1b  lea     rax, [rbp+var_50]
0x180033e1f  mov     [rsp+140h+var_C8], rax
0x180033e24  lea     rax, [rbp+arg_18]
0x180033e28  mov     [rsp+140h+var_D0], rax
0x180033e2d  lea     rax, [rbp+var_48]
0x180033e31  mov     [rsp+140h+var_D8], rax
0x180033e36  lea     rax, [rbp+var_80]
0x180033e3a  mov     [rsp+140h+var_E0], rax
0x180033e3f  lea     rax, [rbp+var_40]
0x180033e43  mov     [rsp+140h+var_E8], rax
0x180033e48  lea     rax, [rbp+var_7C]
0x180033e4c  mov     [rsp+140h+var_F0], rax
0x180033e51  lea     rax, [rbp+var_38]
0x180033e55  mov     [rsp+140h+var_F8], rax
0x180033e5a  lea     rax, [rbp+var_78]
0x180033e5e  mov     [rsp+140h+var_100], rax
0x180033e63  lea     rax, [rbp+var_30]
0x180033e67  mov     [rsp+140h+var_108], rax
0x180033e6c  lea     rax, [rbp+var_74]
0x180033e70  mov     [rbp+var_70], rcx
0x180033e74  mov     ecx, [rdi+44h]
0x180033e77  mov     [rsp+140h+var_110], rax
0x180033e7c  lea     rax, [rbp+var_28]
0x180033e80  mov     [rbp+arg_0], ecx
0x180033e83  mov     ecx, [rdi+10h]
0x180033e86  mov     [rbp+arg_8], ecx
0x180033e89  mov     rcx, [rdi+78h]
0x180033e8d  mov     [rsp+140h+var_118], rax
0x180033e92  lea     rax, [rbp+var_20]
0x180033e96  mov     [rbp+var_68], rcx
0x180033e9a  mov     rcx, r9
0x180033e9d  mov     [rsp+140h+var_120], rax
0x180033ea2  mov     [rbp+var_28], 1000000h
0x180033eaa  mov     [rbp+var_20], 0
0x180033eb2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180033eb7  jmp     short loc_180033F1D
0x180033eb9  call    ?zInternalStop@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180033ebe  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x180033ec3  mov     rdi, rax
0x180033ec6  mov     ecx, [rax]
0x180033ec8  cmp     ecx, 5
0x180033ecb  jbe     short loc_180033F1D
0x180033ecd  call    cs:__imp_GetCurrentThreadId
0x180033ed3  mov     r8, [rbx+110h]
0x180033eda  lea     rdx, byte_180041CA5
0x180033ee1  mov     [rbp+arg_0], eax
0x180033ee4  xor     r9d, r9d
0x180033ee7  lea     rax, [rbp+arg_0]
0x180033eeb  mov     [rsp+140h+var_110], rax
0x180033ef0  lea     rax, [rbp+arg_8]
0x180033ef4  mov     ecx, [r8+48h]
0x180033ef8  add     r8, 8
0x180033efc  mov     [rsp+140h+var_118], rax
0x180033f01  lea     rax, [rbp+arg_10]
0x180033f05  mov     [rbp+arg_8], ecx
0x180033f08  mov     rcx, rdi
0x180033f0b  mov     [rsp+140h+var_120], rax
0x180033f10  mov     [rbp+arg_10], 0
0x180033f18  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180033f1d  mov     rcx, rbx
0x180033f20  add     rsp, 130h
0x180033f27  pop     rdi
0x180033f28  pop     rbx
0x180033f29  pop     rbp
0x180033f2a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

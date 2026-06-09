# PolicyTelemetry::MaxUserPolicyEvaluation::StopActivity(void)

- ea: `0x18001f150`
- end: `0x18001f375`
- name: `?StopActivity@MaxUserPolicyEvaluation@PolicyTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(PolicyTelemetry::MaxUserPolicyEvaluation *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001f150`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f312`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f312`

## pseudocode

```c
void __fastcall PolicyTelemetry::MaxUserPolicyEvaluation::StopActivity(PolicyTelemetry::MaxUserPolicyEvaluation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = SharedPCAccountManagerLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_18002E411,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&byte_18002E68F,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18001f150  push    rbp
0x18001f152  push    rbx
0x18001f153  push    rdi
0x18001f154  lea     rbp, [rsp-47h]
0x18001f159  sub     rsp, 100h
0x18001f160  mov     rdi, [rcx+110h]
0x18001f167  mov     rbx, rcx
0x18001f16a  mov     eax, [rdi+48h]
0x18001f16d  test    eax, eax
0x18001f16f  jns     loc_18001F2E8
0x18001f175  add     rdi, 50h ; 'P'
0x18001f179  cmp     eax, [rdi+8]
0x18001f17c  jnz     loc_18001F2E8
0x18001f182  test    rdi, rdi
0x18001f185  jz      loc_18001F2E8
0x18001f18b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f190  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001f195  mov     r9, rax
0x18001f198  mov     ecx, [rax]
0x18001f19a  cmp     ecx, 5
0x18001f19d  jbe     loc_18001F363
0x18001f1a3  mov     rdx, 400000000000h
0x18001f1ad  mov     rcx, rax
0x18001f1b0  call    _tlgKeywordOn
0x18001f1b5  test    al, al
0x18001f1b7  jz      loc_18001F363
0x18001f1bd  mov     rax, [rdi+70h]
0x18001f1c1  lea     rdx, byte_18002E411
0x18001f1c8  mov     rcx, [rdi+78h]
0x18001f1cc  mov     r8, [rbx+110h]
0x18001f1d3  mov     [rbp+57h+var_60], rax
0x18001f1d7  add     r8, 8
0x18001f1db  mov     eax, [rdi+68h]
0x18001f1de  mov     [rbp+57h+arg_0], eax
0x18001f1e1  mov     rax, [rdi+60h]
0x18001f1e5  mov     [rbp+57h+var_58], rax
0x18001f1e9  mov     rax, [rdi+58h]
0x18001f1ed  mov     [rbp+57h+var_50], rax
0x18001f1f1  mov     eax, [rdi+50h]
0x18001f1f4  mov     [rbp+57h+arg_8], eax
0x18001f1f7  mov     rax, [rdi+48h]
0x18001f1fb  mov     [rbp+57h+var_48], rax
0x18001f1ff  mov     eax, [rdi+20h]
0x18001f202  mov     dword ptr [rbp+57h+arg_10], eax
0x18001f205  mov     rax, [rdi+18h]
0x18001f209  mov     [rbp+57h+var_40], rax
0x18001f20d  mov     eax, [rdi]
0x18001f20f  mov     [rbp+57h+arg_18], eax
0x18001f212  mov     rax, [rdi+80h]
0x18001f219  mov     [rbp+57h+var_38], rax
0x18001f21d  mov     eax, [rdi+40h]
0x18001f220  mov     [rbp+57h+var_70], eax
0x18001f223  mov     rax, [rdi+38h]
0x18001f227  mov     [rbp+57h+var_30], rax
0x18001f22b  mov     eax, [rdi+8]
0x18001f22e  mov     [rbp+57h+var_6C], eax
0x18001f231  mov     eax, 1000000h
0x18001f236  mov     [rbp+57h+var_28], rax
0x18001f23a  mov     [rbp+57h+var_20], rax
0x18001f23e  lea     rax, [rbp+57h+var_68]
0x18001f242  mov     [rsp+110h+var_78], rax
0x18001f24a  lea     rax, [rbp+57h+var_60]
0x18001f24e  mov     [rsp+110h+var_80], rax
0x18001f256  lea     rax, [rbp+57h+arg_0]
0x18001f25a  mov     [rsp+110h+var_88], rax
0x18001f262  lea     rax, [rbp+57h+var_58]
0x18001f266  mov     [rsp+110h+var_90], rax
0x18001f26e  lea     rax, [rbp+57h+var_50]
0x18001f272  mov     [rsp+110h+var_98], rax
0x18001f277  lea     rax, [rbp+57h+arg_8]
0x18001f27b  mov     [rsp+110h+var_A0], rax
0x18001f280  lea     rax, [rbp+57h+var_48]
0x18001f284  mov     [rsp+110h+var_A8], rax
0x18001f289  lea     rax, [rbp+57h+arg_10]
0x18001f28d  mov     [rsp+110h+var_B0], rax
0x18001f292  lea     rax, [rbp+57h+var_40]
0x18001f296  mov     [rsp+110h+var_B8], rax
0x18001f29b  lea     rax, [rbp+57h+arg_18]
0x18001f29f  mov     [rsp+110h+var_C0], rax
0x18001f2a4  lea     rax, [rbp+57h+var_38]
0x18001f2a8  mov     [rsp+110h+var_C8], rax
0x18001f2ad  lea     rax, [rbp+57h+var_70]
0x18001f2b1  mov     [rsp+110h+var_D0], rax
0x18001f2b6  lea     rax, [rbp+57h+var_30]
0x18001f2ba  mov     [rsp+110h+var_D8], rax
0x18001f2bf  lea     rax, [rbp+57h+var_6C]
0x18001f2c3  mov     [rsp+110h+var_E0], rax
0x18001f2c8  lea     rax, [rbp+57h+var_28]
0x18001f2cc  mov     [rsp+110h+var_E8], rax
0x18001f2d1  lea     rax, [rbp+57h+var_20]
0x18001f2d5  mov     [rbp+57h+var_68], rcx
0x18001f2d9  mov     rcx, r9
0x18001f2dc  mov     [rsp+110h+var_F0], rax
0x18001f2e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001f2e6  jmp     short loc_18001F363
0x18001f2e8  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f2ed  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001f2f2  mov     rdi, rax
0x18001f2f5  mov     ecx, [rax]
0x18001f2f7  cmp     ecx, 5
0x18001f2fa  jbe     short loc_18001F363
0x18001f2fc  mov     rdx, 400000000000h
0x18001f306  mov     rcx, rax
0x18001f309  call    _tlgKeywordOn
0x18001f30e  test    al, al
0x18001f310  jz      short loc_18001F363
0x18001f312  call    cs:__imp_GetCurrentThreadId
0x18001f318  mov     r8, [rbx+110h]
0x18001f31f  lea     rdx, byte_18002E68F
0x18001f326  mov     [rbp+57h+arg_0], eax
0x18001f329  xor     r9d, r9d
0x18001f32c  mov     rcx, rdi
0x18001f32f  mov     eax, [r8+48h]
0x18001f333  add     r8, 8
0x18001f337  mov     [rbp+57h+arg_8], eax
0x18001f33a  mov     eax, 1000000h
0x18001f33f  mov     [rbp+57h+arg_10], rax
0x18001f343  lea     rax, [rbp+57h+arg_0]
0x18001f347  mov     [rsp+110h+var_E0], rax
0x18001f34c  lea     rax, [rbp+57h+arg_8]
0x18001f350  mov     [rsp+110h+var_E8], rax
0x18001f355  lea     rax, [rbp+57h+arg_10]
0x18001f359  mov     [rsp+110h+var_F0], rax
0x18001f35e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001f363  mov     rcx, rbx
0x18001f366  add     rsp, 100h
0x18001f36d  pop     rdi
0x18001f36e  pop     rbx
0x18001f36f  pop     rbp
0x18001f370  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

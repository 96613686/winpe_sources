# PolicyTelemetry::QueuePolicyEvaluation::StopActivity(void)

- ea: `0x180020aa0`
- end: `0x180020cc5`
- name: `?StopActivity@QueuePolicyEvaluation@PolicyTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(PolicyTelemetry::QueuePolicyEvaluation *__hidden this)`
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
- `0x180020aa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020c62`

## pseudocode

```c
void __fastcall PolicyTelemetry::QueuePolicyEvaluation::StopActivity(PolicyTelemetry::QueuePolicyEvaluation *this)
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
        (__int64)&word_18002EB2E,
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
        (__int64)&dword_18002ED1C,
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
0x180020aa0  push    rbp
0x180020aa2  push    rbx
0x180020aa3  push    rdi
0x180020aa4  lea     rbp, [rsp-47h]
0x180020aa9  sub     rsp, 100h
0x180020ab0  mov     rdi, [rcx+110h]
0x180020ab7  mov     rbx, rcx
0x180020aba  mov     eax, [rdi+48h]
0x180020abd  test    eax, eax
0x180020abf  jns     loc_180020C38
0x180020ac5  add     rdi, 50h ; 'P'
0x180020ac9  cmp     eax, [rdi+8]
0x180020acc  jnz     loc_180020C38
0x180020ad2  test    rdi, rdi
0x180020ad5  jz      loc_180020C38
0x180020adb  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020ae0  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180020ae5  mov     r9, rax
0x180020ae8  mov     ecx, [rax]
0x180020aea  cmp     ecx, 5
0x180020aed  jbe     loc_180020CB3
0x180020af3  mov     rdx, 400000000000h
0x180020afd  mov     rcx, rax
0x180020b00  call    _tlgKeywordOn
0x180020b05  test    al, al
0x180020b07  jz      loc_180020CB3
0x180020b0d  mov     rax, [rdi+70h]
0x180020b11  lea     rdx, word_18002EB2E
0x180020b18  mov     rcx, [rdi+78h]
0x180020b1c  mov     r8, [rbx+110h]
0x180020b23  mov     [rbp+57h+var_60], rax
0x180020b27  add     r8, 8
0x180020b2b  mov     eax, [rdi+68h]
0x180020b2e  mov     [rbp+57h+arg_0], eax
0x180020b31  mov     rax, [rdi+60h]
0x180020b35  mov     [rbp+57h+var_58], rax
0x180020b39  mov     rax, [rdi+58h]
0x180020b3d  mov     [rbp+57h+var_50], rax
0x180020b41  mov     eax, [rdi+50h]
0x180020b44  mov     [rbp+57h+arg_8], eax
0x180020b47  mov     rax, [rdi+48h]
0x180020b4b  mov     [rbp+57h+var_48], rax
0x180020b4f  mov     eax, [rdi+20h]
0x180020b52  mov     dword ptr [rbp+57h+arg_10], eax
0x180020b55  mov     rax, [rdi+18h]
0x180020b59  mov     [rbp+57h+var_40], rax
0x180020b5d  mov     eax, [rdi]
0x180020b5f  mov     [rbp+57h+arg_18], eax
0x180020b62  mov     rax, [rdi+80h]
0x180020b69  mov     [rbp+57h+var_38], rax
0x180020b6d  mov     eax, [rdi+40h]
0x180020b70  mov     [rbp+57h+var_70], eax
0x180020b73  mov     rax, [rdi+38h]
0x180020b77  mov     [rbp+57h+var_30], rax
0x180020b7b  mov     eax, [rdi+8]
0x180020b7e  mov     [rbp+57h+var_6C], eax
0x180020b81  mov     eax, 1000000h
0x180020b86  mov     [rbp+57h+var_28], rax
0x180020b8a  mov     [rbp+57h+var_20], rax
0x180020b8e  lea     rax, [rbp+57h+var_68]
0x180020b92  mov     [rsp+110h+var_78], rax
0x180020b9a  lea     rax, [rbp+57h+var_60]
0x180020b9e  mov     [rsp+110h+var_80], rax
0x180020ba6  lea     rax, [rbp+57h+arg_0]
0x180020baa  mov     [rsp+110h+var_88], rax
0x180020bb2  lea     rax, [rbp+57h+var_58]
0x180020bb6  mov     [rsp+110h+var_90], rax
0x180020bbe  lea     rax, [rbp+57h+var_50]
0x180020bc2  mov     [rsp+110h+var_98], rax
0x180020bc7  lea     rax, [rbp+57h+arg_8]
0x180020bcb  mov     [rsp+110h+var_A0], rax
0x180020bd0  lea     rax, [rbp+57h+var_48]
0x180020bd4  mov     [rsp+110h+var_A8], rax
0x180020bd9  lea     rax, [rbp+57h+arg_10]
0x180020bdd  mov     [rsp+110h+var_B0], rax
0x180020be2  lea     rax, [rbp+57h+var_40]
0x180020be6  mov     [rsp+110h+var_B8], rax
0x180020beb  lea     rax, [rbp+57h+arg_18]
0x180020bef  mov     [rsp+110h+var_C0], rax
0x180020bf4  lea     rax, [rbp+57h+var_38]
0x180020bf8  mov     [rsp+110h+var_C8], rax
0x180020bfd  lea     rax, [rbp+57h+var_70]
0x180020c01  mov     [rsp+110h+var_D0], rax
0x180020c06  lea     rax, [rbp+57h+var_30]
0x180020c0a  mov     [rsp+110h+var_D8], rax
0x180020c0f  lea     rax, [rbp+57h+var_6C]
0x180020c13  mov     [rsp+110h+var_E0], rax
0x180020c18  lea     rax, [rbp+57h+var_28]
0x180020c1c  mov     [rsp+110h+var_E8], rax
0x180020c21  lea     rax, [rbp+57h+var_20]
0x180020c25  mov     [rbp+57h+var_68], rcx
0x180020c29  mov     rcx, r9
0x180020c2c  mov     [rsp+110h+var_F0], rax
0x180020c31  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180020c36  jmp     short loc_180020CB3
0x180020c38  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020c3d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180020c42  mov     rdi, rax
0x180020c45  mov     ecx, [rax]
0x180020c47  cmp     ecx, 5
0x180020c4a  jbe     short loc_180020CB3
0x180020c4c  mov     rdx, 400000000000h
0x180020c56  mov     rcx, rax
0x180020c59  call    _tlgKeywordOn
0x180020c5e  test    al, al
0x180020c60  jz      short loc_180020CB3
0x180020c62  call    cs:__imp_GetCurrentThreadId
0x180020c68  mov     r8, [rbx+110h]
0x180020c6f  lea     rdx, dword_18002ED1C
0x180020c76  mov     [rbp+57h+arg_0], eax
0x180020c79  xor     r9d, r9d
0x180020c7c  mov     rcx, rdi
0x180020c7f  mov     eax, [r8+48h]
0x180020c83  add     r8, 8
0x180020c87  mov     [rbp+57h+arg_8], eax
0x180020c8a  mov     eax, 1000000h
0x180020c8f  mov     [rbp+57h+arg_10], rax
0x180020c93  lea     rax, [rbp+57h+arg_0]
0x180020c97  mov     [rsp+110h+var_E0], rax
0x180020c9c  lea     rax, [rbp+57h+arg_8]
0x180020ca0  mov     [rsp+110h+var_E8], rax
0x180020ca5  lea     rax, [rbp+57h+arg_10]
0x180020ca9  mov     [rsp+110h+var_F0], rax
0x180020cae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020cb3  mov     rcx, rbx
0x180020cb6  add     rsp, 100h
0x180020cbd  pop     rdi
0x180020cbe  pop     rbx
0x180020cbf  pop     rbp
0x180020cc0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

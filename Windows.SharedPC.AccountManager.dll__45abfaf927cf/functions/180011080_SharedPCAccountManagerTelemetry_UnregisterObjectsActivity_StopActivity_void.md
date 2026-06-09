# SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StopActivity(void)

- ea: `0x180011080`
- end: `0x1800112a5`
- name: `?StopActivity@UnregisterObjectsActivity@SharedPCAccountManagerTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x180011080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011242`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011242`

## pseudocode

```c
void __fastcall SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StopActivity(
        SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *this)
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
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
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
        (__int64)word_18002C392,
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
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002C169,
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
0x180011080  push    rbp
0x180011082  push    rbx
0x180011083  push    rdi
0x180011084  lea     rbp, [rsp-47h]
0x180011089  sub     rsp, 100h
0x180011090  mov     rdi, [rcx+110h]
0x180011097  mov     rbx, rcx
0x18001109a  mov     eax, [rdi+48h]
0x18001109d  test    eax, eax
0x18001109f  jns     loc_180011218
0x1800110a5  add     rdi, 50h ; 'P'
0x1800110a9  cmp     eax, [rdi+8]
0x1800110ac  jnz     loc_180011218
0x1800110b2  test    rdi, rdi
0x1800110b5  jz      loc_180011218
0x1800110bb  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800110c0  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800110c5  mov     r9, rax
0x1800110c8  mov     ecx, [rax]
0x1800110ca  cmp     ecx, 5
0x1800110cd  jbe     loc_180011293
0x1800110d3  mov     rdx, 200000000000h
0x1800110dd  mov     rcx, rax
0x1800110e0  call    _tlgKeywordOn
0x1800110e5  test    al, al
0x1800110e7  jz      loc_180011293
0x1800110ed  mov     rax, [rdi+70h]
0x1800110f1  lea     rdx, word_18002C392
0x1800110f8  mov     rcx, [rdi+78h]
0x1800110fc  mov     r8, [rbx+110h]
0x180011103  mov     [rbp+57h+var_60], rax
0x180011107  add     r8, 8
0x18001110b  mov     eax, [rdi+68h]
0x18001110e  mov     [rbp+57h+arg_0], eax
0x180011111  mov     rax, [rdi+60h]
0x180011115  mov     [rbp+57h+var_58], rax
0x180011119  mov     rax, [rdi+58h]
0x18001111d  mov     [rbp+57h+var_50], rax
0x180011121  mov     eax, [rdi+50h]
0x180011124  mov     [rbp+57h+arg_8], eax
0x180011127  mov     rax, [rdi+48h]
0x18001112b  mov     [rbp+57h+var_48], rax
0x18001112f  mov     eax, [rdi+20h]
0x180011132  mov     dword ptr [rbp+57h+arg_10], eax
0x180011135  mov     rax, [rdi+18h]
0x180011139  mov     [rbp+57h+var_40], rax
0x18001113d  mov     eax, [rdi]
0x18001113f  mov     [rbp+57h+arg_18], eax
0x180011142  mov     rax, [rdi+80h]
0x180011149  mov     [rbp+57h+var_38], rax
0x18001114d  mov     eax, [rdi+40h]
0x180011150  mov     [rbp+57h+var_70], eax
0x180011153  mov     rax, [rdi+38h]
0x180011157  mov     [rbp+57h+var_30], rax
0x18001115b  mov     eax, [rdi+8]
0x18001115e  mov     [rbp+57h+var_6C], eax
0x180011161  mov     eax, 1000000h
0x180011166  mov     [rbp+57h+var_28], rax
0x18001116a  mov     [rbp+57h+var_20], rax
0x18001116e  lea     rax, [rbp+57h+var_68]
0x180011172  mov     [rsp+110h+var_78], rax
0x18001117a  lea     rax, [rbp+57h+var_60]
0x18001117e  mov     [rsp+110h+var_80], rax
0x180011186  lea     rax, [rbp+57h+arg_0]
0x18001118a  mov     [rsp+110h+var_88], rax
0x180011192  lea     rax, [rbp+57h+var_58]
0x180011196  mov     [rsp+110h+var_90], rax
0x18001119e  lea     rax, [rbp+57h+var_50]
0x1800111a2  mov     [rsp+110h+var_98], rax
0x1800111a7  lea     rax, [rbp+57h+arg_8]
0x1800111ab  mov     [rsp+110h+var_A0], rax
0x1800111b0  lea     rax, [rbp+57h+var_48]
0x1800111b4  mov     [rsp+110h+var_A8], rax
0x1800111b9  lea     rax, [rbp+57h+arg_10]
0x1800111bd  mov     [rsp+110h+var_B0], rax
0x1800111c2  lea     rax, [rbp+57h+var_40]
0x1800111c6  mov     [rsp+110h+var_B8], rax
0x1800111cb  lea     rax, [rbp+57h+arg_18]
0x1800111cf  mov     [rsp+110h+var_C0], rax
0x1800111d4  lea     rax, [rbp+57h+var_38]
0x1800111d8  mov     [rsp+110h+var_C8], rax
0x1800111dd  lea     rax, [rbp+57h+var_70]
0x1800111e1  mov     [rsp+110h+var_D0], rax
0x1800111e6  lea     rax, [rbp+57h+var_30]
0x1800111ea  mov     [rsp+110h+var_D8], rax
0x1800111ef  lea     rax, [rbp+57h+var_6C]
0x1800111f3  mov     [rsp+110h+var_E0], rax
0x1800111f8  lea     rax, [rbp+57h+var_28]
0x1800111fc  mov     [rsp+110h+var_E8], rax
0x180011201  lea     rax, [rbp+57h+var_20]
0x180011205  mov     [rbp+57h+var_68], rcx
0x180011209  mov     rcx, r9
0x18001120c  mov     [rsp+110h+var_F0], rax
0x180011211  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180011216  jmp     short loc_180011293
0x180011218  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001121d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180011222  mov     rdi, rax
0x180011225  mov     ecx, [rax]
0x180011227  cmp     ecx, 5
0x18001122a  jbe     short loc_180011293
0x18001122c  mov     rdx, 200000000000h
0x180011236  mov     rcx, rax
0x180011239  call    _tlgKeywordOn
0x18001123e  test    al, al
0x180011240  jz      short loc_180011293
0x180011242  call    cs:__imp_GetCurrentThreadId
0x180011248  mov     r8, [rbx+110h]
0x18001124f  lea     rdx, byte_18002C169
0x180011256  mov     [rbp+57h+arg_0], eax
0x180011259  xor     r9d, r9d
0x18001125c  mov     rcx, rdi
0x18001125f  mov     eax, [r8+48h]
0x180011263  add     r8, 8
0x180011267  mov     [rbp+57h+arg_8], eax
0x18001126a  mov     eax, 1000000h
0x18001126f  mov     [rbp+57h+arg_10], rax
0x180011273  lea     rax, [rbp+57h+arg_0]
0x180011277  mov     [rsp+110h+var_E0], rax
0x18001127c  lea     rax, [rbp+57h+arg_8]
0x180011280  mov     [rsp+110h+var_E8], rax
0x180011285  lea     rax, [rbp+57h+arg_10]
0x180011289  mov     [rsp+110h+var_F0], rax
0x18001128e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011293  mov     rcx, rbx
0x180011296  add     rsp, 100h
0x18001129d  pop     rdi
0x18001129e  pop     rbx
0x18001129f  pop     rbp
0x1800112a0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

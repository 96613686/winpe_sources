# PolicyTelemetry::QueuePolicyEvaluation::Stop(uint,uint)

- ea: `0x1800205f0`
- end: `0x18002086a`
- name: `?Stop@QueuePolicyEvaluation@PolicyTelemetry@@QEAAXII@Z`
- size: `634`
- prototype: `void __fastcall(PolicyTelemetry::QueuePolicyEvaluation *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020070`

## callees

- `0x180001b0c`
- `0x180002414`
- `0x1800026ec`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x1800205f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800207eb`

## pseudocode

```c
void __fastcall PolicyTelemetry::QueuePolicyEvaluation::Stop(
        PolicyTelemetry::QueuePolicyEvaluation *this,
        int a2,
        int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v20; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  int v24; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  const WCHAR *v26; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp-58h] BYREF
  const WCHAR *v28; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-40h] BYREF
  const WCHAR *v31; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v32; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v33; // [rsp+108h] [rbp-28h] BYREF
  __int64 v34; // [rsp+110h] [rbp-20h] BYREF
  int v35; // [rsp+140h] [rbp+10h] BYREF
  int v36; // [rsp+158h] [rbp+28h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v11, v9) )
    {
      v26 = (const WCHAR *)*((_QWORD *)v8 + 15);
      v27 = (const unsigned __int16 *)*((_QWORD *)v8 + 14);
      v13 = *((_QWORD *)this + 34);
      v21 = v8[26];
      v28 = (const WCHAR *)*((_QWORD *)v8 + 12);
      v29 = (const unsigned __int16 *)*((_QWORD *)v8 + 11);
      v22 = v8[20];
      v30 = (const unsigned __int16 *)*((_QWORD *)v8 + 9);
      v23 = v8[8];
      v31 = (const WCHAR *)*((_QWORD *)v8 + 3);
      v24 = *v8;
      v32 = (const unsigned __int16 *)*((_QWORD *)v8 + 16);
      v19 = v8[16];
      v33 = (const unsigned __int16 *)*((_QWORD *)v8 + 7);
      v20 = v8[2];
      v34 = 0x1000000;
      v25 = 0x1000000;
      v35 = a3;
      v36 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&word_18002F02E,
        v13 + 8,
        v12,
        (__int64)&v25,
        (__int64)&v34,
        (__int64)&v20,
        &v33,
        (__int64)&v19,
        &v32,
        (__int64)&v24,
        &v31,
        (__int64)&v23,
        &v30,
        (__int64)&v22,
        &v29,
        &v28,
        (__int64)&v21,
        &v27,
        &v26,
        (__int64)&v36,
        (__int64)&v35);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = SharedPCAccountManagerLogging::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v11, v12) )
    {
      v35 = a3;
      v36 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v19 = *(_DWORD *)(v17 + 72);
      v25 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)&unk_18002F1C8,
        v17 + 8,
        v18,
        (__int64)&v25,
        (__int64)&v19,
        (__int64)&v20,
        (__int64)&v36,
        (__int64)&v35);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x1800205f0  mov     [rsp-8+arg_8], rbx
0x1800205f5  mov     [rsp-8+arg_10], rsi
0x1800205fa  push    rbp
0x1800205fb  push    rdi
0x1800205fc  push    r14
0x1800205fe  lea     rbp, [rsp+10h]
0x180020603  sub     rsp, 120h
0x18002060a  mov     rdi, [rcx+110h]
0x180020611  mov     esi, r8d
0x180020614  mov     r14d, edx
0x180020617  mov     rbx, rcx
0x18002061a  mov     eax, [rdi+48h]
0x18002061d  test    eax, eax
0x18002061f  jns     loc_1800207BA
0x180020625  add     rdi, 50h ; 'P'
0x180020629  cmp     eax, [rdi+8]
0x18002062c  jnz     loc_1800207BA
0x180020632  test    rdi, rdi
0x180020635  jz      loc_1800207BA
0x18002063b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020640  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180020645  mov     r9, rax
0x180020648  mov     ecx, [rax]
0x18002064a  cmp     ecx, 5
0x18002064d  jbe     loc_18002084B
0x180020653  mov     rdx, 400000000000h
0x18002065d  mov     rcx, rax
0x180020660  call    _tlgKeywordOn
0x180020665  test    al, al
0x180020667  jz      loc_18002084B
0x18002066d  mov     rax, [rdi+78h]
0x180020671  lea     rdx, word_18002F02E
0x180020678  mov     [rbp+var_60], rax
0x18002067c  mov     rcx, r9
0x18002067f  mov     rax, [rdi+70h]
0x180020683  mov     [rbp+var_58], rax
0x180020687  mov     eax, [rdi+68h]
0x18002068a  mov     r8, [rbx+110h]
0x180020691  mov     [rbp+var_78], eax
0x180020694  add     r8, 8
0x180020698  mov     rax, [rdi+60h]
0x18002069c  mov     [rbp+var_50], rax
0x1800206a0  mov     rax, [rdi+58h]
0x1800206a4  mov     [rbp+var_48], rax
0x1800206a8  mov     eax, [rdi+50h]
0x1800206ab  mov     [rbp+var_74], eax
0x1800206ae  mov     rax, [rdi+48h]
0x1800206b2  mov     [rbp+var_40], rax
0x1800206b6  mov     eax, [rdi+20h]
0x1800206b9  mov     [rbp+var_70], eax
0x1800206bc  mov     rax, [rdi+18h]
0x1800206c0  mov     [rbp+var_38], rax
0x1800206c4  mov     eax, [rdi]
0x1800206c6  mov     [rbp+var_6C], eax
0x1800206c9  mov     rax, [rdi+80h]
0x1800206d0  mov     [rbp+var_30], rax
0x1800206d4  mov     eax, [rdi+40h]
0x1800206d7  mov     [rbp+var_80], eax
0x1800206da  mov     rax, [rdi+38h]
0x1800206de  mov     [rbp+var_28], rax
0x1800206e2  mov     eax, [rdi+8]
0x1800206e5  mov     [rbp+var_7C], eax
0x1800206e8  mov     eax, 1000000h
0x1800206ed  mov     [rbp+var_20], rax
0x1800206f1  mov     [rbp+var_68], rax
0x1800206f5  lea     rax, [rbp+arg_0]
0x1800206f9  mov     [rsp+130h+var_88], rax
0x180020701  lea     rax, [rbp+arg_18]
0x180020705  mov     [rsp+130h+var_90], rax
0x18002070d  lea     rax, [rbp+var_60]
0x180020711  mov     [rsp+130h+var_98], rax
0x180020719  lea     rax, [rbp+var_58]
0x18002071d  mov     [rsp+130h+var_A0], rax
0x180020725  lea     rax, [rbp+var_78]
0x180020729  mov     [rsp+130h+var_A8], rax
0x180020731  lea     rax, [rbp+var_50]
0x180020735  mov     [rsp+130h+var_B0], rax
0x18002073d  lea     rax, [rbp+var_48]
0x180020741  mov     [rsp+130h+var_B8], rax
0x180020746  lea     rax, [rbp+var_74]
0x18002074a  mov     [rsp+130h+var_C0], rax
0x18002074f  lea     rax, [rbp+var_40]
0x180020753  mov     [rsp+130h+var_C8], rax
0x180020758  lea     rax, [rbp+var_70]
0x18002075c  mov     [rsp+130h+var_D0], rax
0x180020761  lea     rax, [rbp+var_38]
0x180020765  mov     [rsp+130h+var_D8], rax
0x18002076a  lea     rax, [rbp+var_6C]
0x18002076e  mov     [rsp+130h+var_E0], rax
0x180020773  lea     rax, [rbp+var_30]
0x180020777  mov     [rsp+130h+var_E8], rax
0x18002077c  lea     rax, [rbp+var_80]
0x180020780  mov     [rsp+130h+var_F0], rax
0x180020785  lea     rax, [rbp+var_28]
0x180020789  mov     [rsp+130h+var_F8], rax
0x18002078e  lea     rax, [rbp+var_7C]
0x180020792  mov     [rsp+130h+var_100], rax
0x180020797  lea     rax, [rbp+var_20]
0x18002079b  mov     [rsp+130h+var_108], rax
0x1800207a0  lea     rax, [rbp+var_68]
0x1800207a4  mov     [rsp+130h+var_110], rax
0x1800207a9  mov     [rbp+arg_0], esi
0x1800207ac  mov     [rbp+arg_18], r14d
0x1800207b0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800207b5  jmp     loc_18002084B
0x1800207ba  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800207bf  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800207c4  mov     rdi, rax
0x1800207c7  mov     ecx, [rax]
0x1800207c9  cmp     ecx, 5
0x1800207cc  jbe     short loc_18002084B
0x1800207ce  mov     rdx, 400000000000h
0x1800207d8  mov     rcx, rax
0x1800207db  call    _tlgKeywordOn
0x1800207e0  test    al, al
0x1800207e2  jz      short loc_18002084B
0x1800207e4  mov     [rbp+arg_0], esi
0x1800207e7  mov     [rbp+arg_18], r14d
0x1800207eb  call    cs:__imp_GetCurrentThreadId
0x1800207f1  mov     r8, [rbx+110h]
0x1800207f8  lea     rdx, unk_18002F1C8
0x1800207ff  mov     [rbp+var_7C], eax
0x180020802  mov     rcx, rdi
0x180020805  mov     eax, [r8+48h]
0x180020809  add     r8, 8
0x18002080d  mov     [rbp+var_80], eax
0x180020810  mov     eax, 1000000h
0x180020815  mov     [rbp+var_68], rax
0x180020819  lea     rax, [rbp+arg_0]
0x18002081d  mov     [rsp+130h+var_F0], rax
0x180020822  lea     rax, [rbp+arg_18]
0x180020826  mov     [rsp+130h+var_F8], rax
0x18002082b  lea     rax, [rbp+var_7C]
0x18002082f  mov     [rsp+130h+var_100], rax
0x180020834  lea     rax, [rbp+var_80]
0x180020838  mov     [rsp+130h+var_108], rax
0x18002083d  lea     rax, [rbp+var_68]
0x180020841  mov     [rsp+130h+var_110], rax
0x180020846  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002084b  mov     rcx, rbx
0x18002084e  lea     r11, [rsp+130h+var_10]
0x180020856  mov     rbx, [r11+28h]
0x18002085a  mov     rsi, [r11+30h]
0x18002085e  mov     rsp, r11
0x180020861  pop     r14
0x180020863  pop     rdi
0x180020864  pop     rbp
0x180020865  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

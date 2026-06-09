# PolicyTelemetry::SinglePolicyEvaluation::Stop(uint)

- ea: `0x18001c60c`
- end: `0x18001c85a`
- name: `?Stop@SinglePolicyEvaluation@PolicyTelemetry@@QEAAXI@Z`
- size: `590`
- prototype: `void __fastcall(PolicyTelemetry::SinglePolicyEvaluation *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001c238`

## callees

- `0x180001b0c`
- `0x1800020c0`
- `0x180002384`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001c60c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c7e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c7e9`

## pseudocode

```c
void __fastcall PolicyTelemetry::SinglePolicyEvaluation::Stop(PolicyTelemetry::SinglePolicyEvaluation *this, int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  int v19; // [rsp+B8h] [rbp-78h] BYREF
  int v20; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  const WCHAR *v22; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-60h] BYREF
  const WCHAR *v24; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  const WCHAR *v27; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30[3]; // [rsp+108h] [rbp-28h] BYREF
  int v31; // [rsp+130h] [rbp+0h] BYREF
  DWORD v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = SharedPCAccountManagerLogging::Provider();
    v10 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v9, v7) )
    {
      v22 = (const WCHAR *)*((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v32 = v6[26];
      v24 = (const WCHAR *)*((_QWORD *)v6 + 12);
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v33 = v6[20];
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v17 = v6[8];
      v27 = (const WCHAR *)*((_QWORD *)v6 + 3);
      v18 = *v6;
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v19 = v6[16];
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v20 = v6[2];
      v30[0] = 0x1000000;
      v21 = 0x1000000;
      v31 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)word_18002DEB2,
        v11 + 8,
        v10,
        (__int64)&v21,
        (__int64)v30,
        (__int64)&v20,
        &v29,
        (__int64)&v19,
        &v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v33,
        &v25,
        &v24,
        (__int64)&v32,
        &v23,
        &v22,
        (__int64)&v31);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = SharedPCAccountManagerLogging::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v9, v10) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v32 = CurrentThreadId;
      v33 = *(_DWORD *)(v15 + 72);
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)word_18002DC62,
        v15 + 8,
        v16,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x18001c60c  mov     [rsp-8+arg_8], rbx
0x18001c611  push    rbp
0x18001c612  push    rsi
0x18001c613  push    rdi
0x18001c614  lea     rbp, [rsp+20h]
0x18001c619  sub     rsp, 110h
0x18001c620  mov     rdi, [rcx+110h]
0x18001c627  mov     esi, edx
0x18001c629  mov     rbx, rcx
0x18001c62c  mov     eax, [rdi+48h]
0x18001c62f  test    eax, eax
0x18001c631  jns     loc_18001C7BC
0x18001c637  add     rdi, 50h ; 'P'
0x18001c63b  cmp     eax, [rdi+8]
0x18001c63e  jnz     loc_18001C7BC
0x18001c644  test    rdi, rdi
0x18001c647  jz      loc_18001C7BC
0x18001c64d  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001c652  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001c657  mov     r9, rax
0x18001c65a  mov     ecx, [rax]
0x18001c65c  cmp     ecx, 5
0x18001c65f  jbe     loc_18001C840
0x18001c665  mov     rdx, 400000000000h
0x18001c66f  mov     rcx, rax
0x18001c672  call    _tlgKeywordOn
0x18001c677  test    al, al
0x18001c679  jz      loc_18001C840
0x18001c67f  mov     rax, [rdi+78h]
0x18001c683  lea     rdx, word_18002DEB2
0x18001c68a  mov     [rbp-10h+var_58], rax
0x18001c68e  mov     rcx, r9
0x18001c691  mov     rax, [rdi+70h]
0x18001c695  mov     r8, [rbx+110h]
0x18001c69c  mov     [rbp-10h+var_50], rax
0x18001c6a0  add     r8, 8
0x18001c6a4  mov     eax, [rdi+68h]
0x18001c6a7  mov     [rbp-10h+arg_10], eax
0x18001c6aa  mov     rax, [rdi+60h]
0x18001c6ae  mov     [rbp-10h+var_48], rax
0x18001c6b2  mov     rax, [rdi+58h]
0x18001c6b6  mov     [rbp-10h+var_40], rax
0x18001c6ba  mov     eax, [rdi+50h]
0x18001c6bd  mov     [rbp-10h+arg_18], eax
0x18001c6c0  mov     rax, [rdi+48h]
0x18001c6c4  mov     [rbp-10h+var_38], rax
0x18001c6c8  mov     eax, [rdi+20h]
0x18001c6cb  mov     [rbp-10h+var_70], eax
0x18001c6ce  mov     rax, [rdi+18h]
0x18001c6d2  mov     [rbp-10h+var_30], rax
0x18001c6d6  mov     eax, [rdi]
0x18001c6d8  mov     [rbp-10h+var_6C], eax
0x18001c6db  mov     rax, [rdi+80h]
0x18001c6e2  mov     [rbp-10h+var_28], rax
0x18001c6e6  mov     eax, [rdi+40h]
0x18001c6e9  mov     [rbp-10h+var_68], eax
0x18001c6ec  mov     rax, [rdi+38h]
0x18001c6f0  mov     [rbp-10h+var_20], rax
0x18001c6f4  mov     eax, [rdi+8]
0x18001c6f7  mov     [rbp-10h+var_64], eax
0x18001c6fa  mov     eax, 1000000h
0x18001c6ff  mov     [rbp-10h+var_18], rax
0x18001c703  mov     [rbp-10h+var_60], rax
0x18001c707  lea     rax, [rbp-10h+arg_0]
0x18001c70b  mov     [rsp+120h+var_80], rax
0x18001c713  lea     rax, [rbp-10h+var_58]
0x18001c717  mov     [rsp+120h+var_88], rax
0x18001c71f  lea     rax, [rbp-10h+var_50]
0x18001c723  mov     [rsp+120h+var_90], rax
0x18001c72b  lea     rax, [rbp-10h+arg_10]
0x18001c72f  mov     [rsp+120h+var_98], rax
0x18001c737  lea     rax, [rbp-10h+var_48]
0x18001c73b  mov     [rsp+120h+var_A0], rax
0x18001c743  lea     rax, [rbp-10h+var_40]
0x18001c747  mov     [rsp+120h+var_A8], rax
0x18001c74c  lea     rax, [rbp-10h+arg_18]
0x18001c750  mov     [rsp+120h+var_B0], rax
0x18001c755  lea     rax, [rbp-10h+var_38]
0x18001c759  mov     [rsp+120h+var_B8], rax
0x18001c75e  lea     rax, [rbp-10h+var_70]
0x18001c762  mov     [rsp+120h+var_C0], rax
0x18001c767  lea     rax, [rbp-10h+var_30]
0x18001c76b  mov     [rsp+120h+var_C8], rax
0x18001c770  lea     rax, [rbp-10h+var_6C]
0x18001c774  mov     [rsp+120h+var_D0], rax
0x18001c779  lea     rax, [rbp-10h+var_28]
0x18001c77d  mov     [rsp+120h+var_D8], rax
0x18001c782  lea     rax, [rbp-10h+var_68]
0x18001c786  mov     [rsp+120h+var_E0], rax
0x18001c78b  lea     rax, [rbp-10h+var_20]
0x18001c78f  mov     [rsp+120h+var_E8], rax
0x18001c794  lea     rax, [rbp-10h+var_64]
0x18001c798  mov     [rsp+120h+var_F0], rax
0x18001c79d  lea     rax, [rbp-10h+var_18]
0x18001c7a1  mov     [rsp+120h+var_F8], rax
0x18001c7a6  lea     rax, [rbp-10h+var_60]
0x18001c7aa  mov     [rsp+120h+var_100], rax
0x18001c7af  mov     [rbp-10h+arg_0], esi
0x18001c7b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001c7b7  jmp     loc_18001C840
0x18001c7bc  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001c7c1  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001c7c6  mov     rdi, rax
0x18001c7c9  mov     ecx, [rax]
0x18001c7cb  cmp     ecx, 5
0x18001c7ce  jbe     short loc_18001C840
0x18001c7d0  mov     rdx, 400000000000h
0x18001c7da  mov     rcx, rax
0x18001c7dd  call    _tlgKeywordOn
0x18001c7e2  test    al, al
0x18001c7e4  jz      short loc_18001C840
0x18001c7e6  mov     [rbp-10h+arg_0], esi
0x18001c7e9  call    cs:__imp_GetCurrentThreadId
0x18001c7ef  mov     r8, [rbx+110h]
0x18001c7f6  lea     rdx, word_18002DC62
0x18001c7fd  mov     [rbp-10h+arg_10], eax
0x18001c800  mov     rcx, rdi
0x18001c803  mov     eax, [r8+48h]
0x18001c807  add     r8, 8
0x18001c80b  mov     [rbp-10h+arg_18], eax
0x18001c80e  mov     eax, 1000000h
0x18001c813  mov     [rbp-10h+var_60], rax
0x18001c817  lea     rax, [rbp-10h+arg_0]
0x18001c81b  mov     [rsp+120h+var_E8], rax
0x18001c820  lea     rax, [rbp-10h+arg_10]
0x18001c824  mov     [rsp+120h+var_F0], rax
0x18001c829  lea     rax, [rbp-10h+arg_18]
0x18001c82d  mov     [rsp+120h+var_F8], rax
0x18001c832  lea     rax, [rbp-10h+var_60]
0x18001c836  mov     [rsp+120h+var_100], rax
0x18001c83b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c840  mov     rcx, rbx
0x18001c843  mov     rbx, [rsp+120h+arg_8]
0x18001c84b  add     rsp, 110h
0x18001c852  pop     rdi
0x18001c853  pop     rsi
0x18001c854  pop     rbp
0x18001c855  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

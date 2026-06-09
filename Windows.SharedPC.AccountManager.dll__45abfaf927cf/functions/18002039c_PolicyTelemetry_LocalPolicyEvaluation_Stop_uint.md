# PolicyTelemetry::LocalPolicyEvaluation::Stop(uint)

- ea: `0x18002039c`
- end: `0x1800205ea`
- name: `?Stop@LocalPolicyEvaluation@PolicyTelemetry@@QEAAXI@Z`
- size: `590`
- prototype: `void __fastcall(PolicyTelemetry::LocalPolicyEvaluation *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001fcf4`

## callees

- `0x180001b0c`
- `0x1800020c0`
- `0x180002384`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18002039c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020579`

## pseudocode

```c
void __fastcall PolicyTelemetry::LocalPolicyEvaluation::Stop(PolicyTelemetry::LocalPolicyEvaluation *this, int a2)
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
        (__int64)&byte_18002EE9F,
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
        (__int64)byte_18002ECB1,
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
0x18002039c  mov     [rsp-8+arg_8], rbx
0x1800203a1  push    rbp
0x1800203a2  push    rsi
0x1800203a3  push    rdi
0x1800203a4  lea     rbp, [rsp+20h]
0x1800203a9  sub     rsp, 110h
0x1800203b0  mov     rdi, [rcx+110h]
0x1800203b7  mov     esi, edx
0x1800203b9  mov     rbx, rcx
0x1800203bc  mov     eax, [rdi+48h]
0x1800203bf  test    eax, eax
0x1800203c1  jns     loc_18002054C
0x1800203c7  add     rdi, 50h ; 'P'
0x1800203cb  cmp     eax, [rdi+8]
0x1800203ce  jnz     loc_18002054C
0x1800203d4  test    rdi, rdi
0x1800203d7  jz      loc_18002054C
0x1800203dd  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800203e2  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800203e7  mov     r9, rax
0x1800203ea  mov     ecx, [rax]
0x1800203ec  cmp     ecx, 5
0x1800203ef  jbe     loc_1800205D0
0x1800203f5  mov     rdx, 400000000000h
0x1800203ff  mov     rcx, rax
0x180020402  call    _tlgKeywordOn
0x180020407  test    al, al
0x180020409  jz      loc_1800205D0
0x18002040f  mov     rax, [rdi+78h]
0x180020413  lea     rdx, byte_18002EE9F
0x18002041a  mov     [rbp-10h+var_58], rax
0x18002041e  mov     rcx, r9
0x180020421  mov     rax, [rdi+70h]
0x180020425  mov     r8, [rbx+110h]
0x18002042c  mov     [rbp-10h+var_50], rax
0x180020430  add     r8, 8
0x180020434  mov     eax, [rdi+68h]
0x180020437  mov     [rbp-10h+arg_10], eax
0x18002043a  mov     rax, [rdi+60h]
0x18002043e  mov     [rbp-10h+var_48], rax
0x180020442  mov     rax, [rdi+58h]
0x180020446  mov     [rbp-10h+var_40], rax
0x18002044a  mov     eax, [rdi+50h]
0x18002044d  mov     [rbp-10h+arg_18], eax
0x180020450  mov     rax, [rdi+48h]
0x180020454  mov     [rbp-10h+var_38], rax
0x180020458  mov     eax, [rdi+20h]
0x18002045b  mov     [rbp-10h+var_70], eax
0x18002045e  mov     rax, [rdi+18h]
0x180020462  mov     [rbp-10h+var_30], rax
0x180020466  mov     eax, [rdi]
0x180020468  mov     [rbp-10h+var_6C], eax
0x18002046b  mov     rax, [rdi+80h]
0x180020472  mov     [rbp-10h+var_28], rax
0x180020476  mov     eax, [rdi+40h]
0x180020479  mov     [rbp-10h+var_68], eax
0x18002047c  mov     rax, [rdi+38h]
0x180020480  mov     [rbp-10h+var_20], rax
0x180020484  mov     eax, [rdi+8]
0x180020487  mov     [rbp-10h+var_64], eax
0x18002048a  mov     eax, 1000000h
0x18002048f  mov     [rbp-10h+var_18], rax
0x180020493  mov     [rbp-10h+var_60], rax
0x180020497  lea     rax, [rbp-10h+arg_0]
0x18002049b  mov     [rsp+120h+var_80], rax
0x1800204a3  lea     rax, [rbp-10h+var_58]
0x1800204a7  mov     [rsp+120h+var_88], rax
0x1800204af  lea     rax, [rbp-10h+var_50]
0x1800204b3  mov     [rsp+120h+var_90], rax
0x1800204bb  lea     rax, [rbp-10h+arg_10]
0x1800204bf  mov     [rsp+120h+var_98], rax
0x1800204c7  lea     rax, [rbp-10h+var_48]
0x1800204cb  mov     [rsp+120h+var_A0], rax
0x1800204d3  lea     rax, [rbp-10h+var_40]
0x1800204d7  mov     [rsp+120h+var_A8], rax
0x1800204dc  lea     rax, [rbp-10h+arg_18]
0x1800204e0  mov     [rsp+120h+var_B0], rax
0x1800204e5  lea     rax, [rbp-10h+var_38]
0x1800204e9  mov     [rsp+120h+var_B8], rax
0x1800204ee  lea     rax, [rbp-10h+var_70]
0x1800204f2  mov     [rsp+120h+var_C0], rax
0x1800204f7  lea     rax, [rbp-10h+var_30]
0x1800204fb  mov     [rsp+120h+var_C8], rax
0x180020500  lea     rax, [rbp-10h+var_6C]
0x180020504  mov     [rsp+120h+var_D0], rax
0x180020509  lea     rax, [rbp-10h+var_28]
0x18002050d  mov     [rsp+120h+var_D8], rax
0x180020512  lea     rax, [rbp-10h+var_68]
0x180020516  mov     [rsp+120h+var_E0], rax
0x18002051b  lea     rax, [rbp-10h+var_20]
0x18002051f  mov     [rsp+120h+var_E8], rax
0x180020524  lea     rax, [rbp-10h+var_64]
0x180020528  mov     [rsp+120h+var_F0], rax
0x18002052d  lea     rax, [rbp-10h+var_18]
0x180020531  mov     [rsp+120h+var_F8], rax
0x180020536  lea     rax, [rbp-10h+var_60]
0x18002053a  mov     [rsp+120h+var_100], rax
0x18002053f  mov     [rbp-10h+arg_0], esi
0x180020542  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180020547  jmp     loc_1800205D0
0x18002054c  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020551  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180020556  mov     rdi, rax
0x180020559  mov     ecx, [rax]
0x18002055b  cmp     ecx, 5
0x18002055e  jbe     short loc_1800205D0
0x180020560  mov     rdx, 400000000000h
0x18002056a  mov     rcx, rax
0x18002056d  call    _tlgKeywordOn
0x180020572  test    al, al
0x180020574  jz      short loc_1800205D0
0x180020576  mov     [rbp-10h+arg_0], esi
0x180020579  call    cs:__imp_GetCurrentThreadId
0x18002057f  mov     r8, [rbx+110h]
0x180020586  lea     rdx, byte_18002ECB1
0x18002058d  mov     [rbp-10h+arg_10], eax
0x180020590  mov     rcx, rdi
0x180020593  mov     eax, [r8+48h]
0x180020597  add     r8, 8
0x18002059b  mov     [rbp-10h+arg_18], eax
0x18002059e  mov     eax, 1000000h
0x1800205a3  mov     [rbp-10h+var_60], rax
0x1800205a7  lea     rax, [rbp-10h+arg_0]
0x1800205ab  mov     [rsp+120h+var_E8], rax
0x1800205b0  lea     rax, [rbp-10h+arg_10]
0x1800205b4  mov     [rsp+120h+var_F0], rax
0x1800205b9  lea     rax, [rbp-10h+arg_18]
0x1800205bd  mov     [rsp+120h+var_F8], rax
0x1800205c2  lea     rax, [rbp-10h+var_60]
0x1800205c6  mov     [rsp+120h+var_100], rax
0x1800205cb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800205d0  mov     rcx, rbx
0x1800205d3  mov     rbx, [rsp+120h+arg_8]
0x1800205db  add     rsp, 110h
0x1800205e2  pop     rdi
0x1800205e3  pop     rsi
0x1800205e4  pop     rbp
0x1800205e5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

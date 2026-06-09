# PolicyTelemetry::UserRequestPolicyEvaluation::Stop(uint,uint)

- ea: `0x18001d9f4`
- end: `0x18001dc6e`
- name: `?Stop@UserRequestPolicyEvaluation@PolicyTelemetry@@QEAAXII@Z`
- size: `634`
- prototype: `void __fastcall(PolicyTelemetry::UserRequestPolicyEvaluation *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001d480`

## callees

- `0x180001b0c`
- `0x180002414`
- `0x1800026ec`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001d9f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dbef`

## pseudocode

```c
void __fastcall PolicyTelemetry::UserRequestPolicyEvaluation::Stop(
        PolicyTelemetry::UserRequestPolicyEvaluation *this,
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
        (__int64)byte_18002DFF3,
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
        (__int64)&unk_18002E1A8,
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
0x18001d9f4  mov     [rsp-8+arg_8], rbx
0x18001d9f9  mov     [rsp-8+arg_10], rsi
0x18001d9fe  push    rbp
0x18001d9ff  push    rdi
0x18001da00  push    r14
0x18001da02  lea     rbp, [rsp+10h]
0x18001da07  sub     rsp, 120h
0x18001da0e  mov     rdi, [rcx+110h]
0x18001da15  mov     esi, r8d
0x18001da18  mov     r14d, edx
0x18001da1b  mov     rbx, rcx
0x18001da1e  mov     eax, [rdi+48h]
0x18001da21  test    eax, eax
0x18001da23  jns     loc_18001DBBE
0x18001da29  add     rdi, 50h ; 'P'
0x18001da2d  cmp     eax, [rdi+8]
0x18001da30  jnz     loc_18001DBBE
0x18001da36  test    rdi, rdi
0x18001da39  jz      loc_18001DBBE
0x18001da3f  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001da44  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001da49  mov     r9, rax
0x18001da4c  mov     ecx, [rax]
0x18001da4e  cmp     ecx, 5
0x18001da51  jbe     loc_18001DC4F
0x18001da57  mov     rdx, 400000000000h
0x18001da61  mov     rcx, rax
0x18001da64  call    _tlgKeywordOn
0x18001da69  test    al, al
0x18001da6b  jz      loc_18001DC4F
0x18001da71  mov     rax, [rdi+78h]
0x18001da75  lea     rdx, byte_18002DFF3
0x18001da7c  mov     [rbp+var_60], rax
0x18001da80  mov     rcx, r9
0x18001da83  mov     rax, [rdi+70h]
0x18001da87  mov     [rbp+var_58], rax
0x18001da8b  mov     eax, [rdi+68h]
0x18001da8e  mov     r8, [rbx+110h]
0x18001da95  mov     [rbp+var_78], eax
0x18001da98  add     r8, 8
0x18001da9c  mov     rax, [rdi+60h]
0x18001daa0  mov     [rbp+var_50], rax
0x18001daa4  mov     rax, [rdi+58h]
0x18001daa8  mov     [rbp+var_48], rax
0x18001daac  mov     eax, [rdi+50h]
0x18001daaf  mov     [rbp+var_74], eax
0x18001dab2  mov     rax, [rdi+48h]
0x18001dab6  mov     [rbp+var_40], rax
0x18001daba  mov     eax, [rdi+20h]
0x18001dabd  mov     [rbp+var_70], eax
0x18001dac0  mov     rax, [rdi+18h]
0x18001dac4  mov     [rbp+var_38], rax
0x18001dac8  mov     eax, [rdi]
0x18001daca  mov     [rbp+var_6C], eax
0x18001dacd  mov     rax, [rdi+80h]
0x18001dad4  mov     [rbp+var_30], rax
0x18001dad8  mov     eax, [rdi+40h]
0x18001dadb  mov     [rbp+var_80], eax
0x18001dade  mov     rax, [rdi+38h]
0x18001dae2  mov     [rbp+var_28], rax
0x18001dae6  mov     eax, [rdi+8]
0x18001dae9  mov     [rbp+var_7C], eax
0x18001daec  mov     eax, 1000000h
0x18001daf1  mov     [rbp+var_20], rax
0x18001daf5  mov     [rbp+var_68], rax
0x18001daf9  lea     rax, [rbp+arg_0]
0x18001dafd  mov     [rsp+130h+var_88], rax
0x18001db05  lea     rax, [rbp+arg_18]
0x18001db09  mov     [rsp+130h+var_90], rax
0x18001db11  lea     rax, [rbp+var_60]
0x18001db15  mov     [rsp+130h+var_98], rax
0x18001db1d  lea     rax, [rbp+var_58]
0x18001db21  mov     [rsp+130h+var_A0], rax
0x18001db29  lea     rax, [rbp+var_78]
0x18001db2d  mov     [rsp+130h+var_A8], rax
0x18001db35  lea     rax, [rbp+var_50]
0x18001db39  mov     [rsp+130h+var_B0], rax
0x18001db41  lea     rax, [rbp+var_48]
0x18001db45  mov     [rsp+130h+var_B8], rax
0x18001db4a  lea     rax, [rbp+var_74]
0x18001db4e  mov     [rsp+130h+var_C0], rax
0x18001db53  lea     rax, [rbp+var_40]
0x18001db57  mov     [rsp+130h+var_C8], rax
0x18001db5c  lea     rax, [rbp+var_70]
0x18001db60  mov     [rsp+130h+var_D0], rax
0x18001db65  lea     rax, [rbp+var_38]
0x18001db69  mov     [rsp+130h+var_D8], rax
0x18001db6e  lea     rax, [rbp+var_6C]
0x18001db72  mov     [rsp+130h+var_E0], rax
0x18001db77  lea     rax, [rbp+var_30]
0x18001db7b  mov     [rsp+130h+var_E8], rax
0x18001db80  lea     rax, [rbp+var_80]
0x18001db84  mov     [rsp+130h+var_F0], rax
0x18001db89  lea     rax, [rbp+var_28]
0x18001db8d  mov     [rsp+130h+var_F8], rax
0x18001db92  lea     rax, [rbp+var_7C]
0x18001db96  mov     [rsp+130h+var_100], rax
0x18001db9b  lea     rax, [rbp+var_20]
0x18001db9f  mov     [rsp+130h+var_108], rax
0x18001dba4  lea     rax, [rbp+var_68]
0x18001dba8  mov     [rsp+130h+var_110], rax
0x18001dbad  mov     [rbp+arg_0], esi
0x18001dbb0  mov     [rbp+arg_18], r14d
0x18001dbb4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001dbb9  jmp     loc_18001DC4F
0x18001dbbe  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001dbc3  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001dbc8  mov     rdi, rax
0x18001dbcb  mov     ecx, [rax]
0x18001dbcd  cmp     ecx, 5
0x18001dbd0  jbe     short loc_18001DC4F
0x18001dbd2  mov     rdx, 400000000000h
0x18001dbdc  mov     rcx, rax
0x18001dbdf  call    _tlgKeywordOn
0x18001dbe4  test    al, al
0x18001dbe6  jz      short loc_18001DC4F
0x18001dbe8  mov     [rbp+arg_0], esi
0x18001dbeb  mov     [rbp+arg_18], r14d
0x18001dbef  call    cs:__imp_GetCurrentThreadId
0x18001dbf5  mov     r8, [rbx+110h]
0x18001dbfc  lea     rdx, unk_18002E1A8
0x18001dc03  mov     [rbp+var_7C], eax
0x18001dc06  mov     rcx, rdi
0x18001dc09  mov     eax, [r8+48h]
0x18001dc0d  add     r8, 8
0x18001dc11  mov     [rbp+var_80], eax
0x18001dc14  mov     eax, 1000000h
0x18001dc19  mov     [rbp+var_68], rax
0x18001dc1d  lea     rax, [rbp+arg_0]
0x18001dc21  mov     [rsp+130h+var_F0], rax
0x18001dc26  lea     rax, [rbp+arg_18]
0x18001dc2a  mov     [rsp+130h+var_F8], rax
0x18001dc2f  lea     rax, [rbp+var_7C]
0x18001dc33  mov     [rsp+130h+var_100], rax
0x18001dc38  lea     rax, [rbp+var_80]
0x18001dc3c  mov     [rsp+130h+var_108], rax
0x18001dc41  lea     rax, [rbp+var_68]
0x18001dc45  mov     [rsp+130h+var_110], rax
0x18001dc4a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001dc4f  mov     rcx, rbx
0x18001dc52  lea     r11, [rsp+130h+var_10]
0x18001dc5a  mov     rbx, [r11+28h]
0x18001dc5e  mov     rsi, [r11+30h]
0x18001dc62  mov     rsp, r11
0x18001dc65  pop     r14
0x18001dc67  pop     rdi
0x18001dc68  pop     rbp
0x18001dc69  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

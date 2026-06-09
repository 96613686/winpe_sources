# PolicyTelemetry::ExemptionPolicyEvaluation::StopActivity(void)

- ea: `0x180021300`
- end: `0x180021525`
- name: `?StopActivity@ExemptionPolicyEvaluation@PolicyTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(PolicyTelemetry::ExemptionPolicyEvaluation *__hidden this)`
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
- `0x180021300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800214c2`

## pseudocode

```c
void __fastcall PolicyTelemetry::ExemptionPolicyEvaluation::StopActivity(
        PolicyTelemetry::ExemptionPolicyEvaluation *this)
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
        (__int64)&unk_18002F430,
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
        (__int64)&word_18002F3D6,
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
0x180021300  push    rbp
0x180021302  push    rbx
0x180021303  push    rdi
0x180021304  lea     rbp, [rsp-47h]
0x180021309  sub     rsp, 100h
0x180021310  mov     rdi, [rcx+110h]
0x180021317  mov     rbx, rcx
0x18002131a  mov     eax, [rdi+48h]
0x18002131d  test    eax, eax
0x18002131f  jns     loc_180021498
0x180021325  add     rdi, 50h ; 'P'
0x180021329  cmp     eax, [rdi+8]
0x18002132c  jnz     loc_180021498
0x180021332  test    rdi, rdi
0x180021335  jz      loc_180021498
0x18002133b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180021340  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180021345  mov     r9, rax
0x180021348  mov     ecx, [rax]
0x18002134a  cmp     ecx, 5
0x18002134d  jbe     loc_180021513
0x180021353  mov     rdx, 400000000000h
0x18002135d  mov     rcx, rax
0x180021360  call    _tlgKeywordOn
0x180021365  test    al, al
0x180021367  jz      loc_180021513
0x18002136d  mov     rax, [rdi+70h]
0x180021371  lea     rdx, unk_18002F430
0x180021378  mov     rcx, [rdi+78h]
0x18002137c  mov     r8, [rbx+110h]
0x180021383  mov     [rbp+57h+var_60], rax
0x180021387  add     r8, 8
0x18002138b  mov     eax, [rdi+68h]
0x18002138e  mov     [rbp+57h+arg_0], eax
0x180021391  mov     rax, [rdi+60h]
0x180021395  mov     [rbp+57h+var_58], rax
0x180021399  mov     rax, [rdi+58h]
0x18002139d  mov     [rbp+57h+var_50], rax
0x1800213a1  mov     eax, [rdi+50h]
0x1800213a4  mov     [rbp+57h+arg_8], eax
0x1800213a7  mov     rax, [rdi+48h]
0x1800213ab  mov     [rbp+57h+var_48], rax
0x1800213af  mov     eax, [rdi+20h]
0x1800213b2  mov     dword ptr [rbp+57h+arg_10], eax
0x1800213b5  mov     rax, [rdi+18h]
0x1800213b9  mov     [rbp+57h+var_40], rax
0x1800213bd  mov     eax, [rdi]
0x1800213bf  mov     [rbp+57h+arg_18], eax
0x1800213c2  mov     rax, [rdi+80h]
0x1800213c9  mov     [rbp+57h+var_38], rax
0x1800213cd  mov     eax, [rdi+40h]
0x1800213d0  mov     [rbp+57h+var_70], eax
0x1800213d3  mov     rax, [rdi+38h]
0x1800213d7  mov     [rbp+57h+var_30], rax
0x1800213db  mov     eax, [rdi+8]
0x1800213de  mov     [rbp+57h+var_6C], eax
0x1800213e1  mov     eax, 1000000h
0x1800213e6  mov     [rbp+57h+var_28], rax
0x1800213ea  mov     [rbp+57h+var_20], rax
0x1800213ee  lea     rax, [rbp+57h+var_68]
0x1800213f2  mov     [rsp+110h+var_78], rax
0x1800213fa  lea     rax, [rbp+57h+var_60]
0x1800213fe  mov     [rsp+110h+var_80], rax
0x180021406  lea     rax, [rbp+57h+arg_0]
0x18002140a  mov     [rsp+110h+var_88], rax
0x180021412  lea     rax, [rbp+57h+var_58]
0x180021416  mov     [rsp+110h+var_90], rax
0x18002141e  lea     rax, [rbp+57h+var_50]
0x180021422  mov     [rsp+110h+var_98], rax
0x180021427  lea     rax, [rbp+57h+arg_8]
0x18002142b  mov     [rsp+110h+var_A0], rax
0x180021430  lea     rax, [rbp+57h+var_48]
0x180021434  mov     [rsp+110h+var_A8], rax
0x180021439  lea     rax, [rbp+57h+arg_10]
0x18002143d  mov     [rsp+110h+var_B0], rax
0x180021442  lea     rax, [rbp+57h+var_40]
0x180021446  mov     [rsp+110h+var_B8], rax
0x18002144b  lea     rax, [rbp+57h+arg_18]
0x18002144f  mov     [rsp+110h+var_C0], rax
0x180021454  lea     rax, [rbp+57h+var_38]
0x180021458  mov     [rsp+110h+var_C8], rax
0x18002145d  lea     rax, [rbp+57h+var_70]
0x180021461  mov     [rsp+110h+var_D0], rax
0x180021466  lea     rax, [rbp+57h+var_30]
0x18002146a  mov     [rsp+110h+var_D8], rax
0x18002146f  lea     rax, [rbp+57h+var_6C]
0x180021473  mov     [rsp+110h+var_E0], rax
0x180021478  lea     rax, [rbp+57h+var_28]
0x18002147c  mov     [rsp+110h+var_E8], rax
0x180021481  lea     rax, [rbp+57h+var_20]
0x180021485  mov     [rbp+57h+var_68], rcx
0x180021489  mov     rcx, r9
0x18002148c  mov     [rsp+110h+var_F0], rax
0x180021491  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180021496  jmp     short loc_180021513
0x180021498  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002149d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800214a2  mov     rdi, rax
0x1800214a5  mov     ecx, [rax]
0x1800214a7  cmp     ecx, 5
0x1800214aa  jbe     short loc_180021513
0x1800214ac  mov     rdx, 400000000000h
0x1800214b6  mov     rcx, rax
0x1800214b9  call    _tlgKeywordOn
0x1800214be  test    al, al
0x1800214c0  jz      short loc_180021513
0x1800214c2  call    cs:__imp_GetCurrentThreadId
0x1800214c8  mov     r8, [rbx+110h]
0x1800214cf  lea     rdx, word_18002F3D6
0x1800214d6  mov     [rbp+57h+arg_0], eax
0x1800214d9  xor     r9d, r9d
0x1800214dc  mov     rcx, rdi
0x1800214df  mov     eax, [r8+48h]
0x1800214e3  add     r8, 8
0x1800214e7  mov     [rbp+57h+arg_8], eax
0x1800214ea  mov     eax, 1000000h
0x1800214ef  mov     [rbp+57h+arg_10], rax
0x1800214f3  lea     rax, [rbp+57h+arg_0]
0x1800214f7  mov     [rsp+110h+var_E0], rax
0x1800214fc  lea     rax, [rbp+57h+arg_8]
0x180021500  mov     [rsp+110h+var_E8], rax
0x180021505  lea     rax, [rbp+57h+arg_10]
0x180021509  mov     [rsp+110h+var_F0], rax
0x18002150e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021513  mov     rcx, rbx
0x180021516  add     rsp, 100h
0x18002151d  pop     rdi
0x18002151e  pop     rbx
0x18002151f  pop     rbp
0x180021520  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

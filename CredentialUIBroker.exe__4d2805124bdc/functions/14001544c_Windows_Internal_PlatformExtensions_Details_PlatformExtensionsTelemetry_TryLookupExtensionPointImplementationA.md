# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)

- ea: `0x14001544c`
- end: `0x14001569f`
- name: `?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z`
- size: `595`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017060`

## callees

- `0x140001d70`
- `0x140002554`
- `0x140002f8c`
- `0x14000e620`
- `0x140011aa0`
- `0x14001544c`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001562f`
- `KERNEL32!GetCurrentThreadId` at `0x14001562f`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        const unsigned __int16 *a2)
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
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  const unsigned __int16 *v33; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v10 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v9, v7) )
    {
      v11 = *((_QWORD *)this + 34);
      v22 = (const unsigned __int16 *)*((_QWORD *)v6 + 15);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v31 = v6[26];
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 12);
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v32 = v6[20];
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      LODWORD(v33) = v6[8];
      v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 3);
      v17 = *v6;
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v18 = v6[16];
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v19 = v6[2];
      v21 = a2;
      v30[0] = 0x1000000;
      v20 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v10,
        (__int64)byte_140024A0D,
        v11 + 8,
        v10,
        (__int64)&v20,
        (__int64)v30,
        (__int64)&v19,
        &v29,
        (__int64)&v18,
        &v28,
        (__int64)&v17,
        &v27,
        (__int64)&v33,
        &v26,
        (__int64)&v32,
        &v25,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        &v21);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v9, v10) )
    {
      v33 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v15 + 72);
      v20 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v13,
        (__int64)&unk_1400247C0,
        v15 + 8,
        v16,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        &v33);
    }
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x14001544c  mov     [rsp-8+arg_8], rbx
0x140015451  push    rbp
0x140015452  push    rsi
0x140015453  push    rdi
0x140015454  lea     rbp, [rsp+10h]
0x140015459  sub     rsp, 120h
0x140015460  mov     rdi, [rcx+110h]
0x140015467  mov     rsi, rdx
0x14001546a  mov     rbx, rcx
0x14001546d  mov     eax, [rdi+48h]
0x140015470  test    eax, eax
0x140015472  jns     loc_140015601
0x140015478  add     rdi, 50h ; 'P'
0x14001547c  cmp     eax, [rdi+8]
0x14001547f  jnz     loc_140015601
0x140015485  test    rdi, rdi
0x140015488  jz      loc_140015601
0x14001548e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015493  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140015498  mov     r9, rax
0x14001549b  mov     ecx, [rax]
0x14001549d  cmp     ecx, 5
0x1400154a0  jbe     loc_140015685
0x1400154a6  mov     rdx, 200000000000h
0x1400154b0  mov     rcx, rax
0x1400154b3  call    _tlgKeywordOn
0x1400154b8  test    al, al
0x1400154ba  jz      loc_140015685
0x1400154c0  mov     rax, [rdi+78h]
0x1400154c4  lea     rdx, byte_140024A0D
0x1400154cb  mov     r8, [rbx+110h]
0x1400154d2  mov     rcx, r9
0x1400154d5  mov     [rbp+var_60], rax
0x1400154d9  add     r8, 8
0x1400154dd  mov     rax, [rdi+70h]
0x1400154e1  mov     [rbp+var_58], rax
0x1400154e5  mov     eax, [rdi+68h]
0x1400154e8  mov     [rbp+arg_0], eax
0x1400154eb  mov     rax, [rdi+60h]
0x1400154ef  mov     [rbp+var_50], rax
0x1400154f3  mov     rax, [rdi+58h]
0x1400154f7  mov     [rbp+var_48], rax
0x1400154fb  mov     eax, [rdi+50h]
0x1400154fe  mov     [rbp+arg_10], eax
0x140015501  mov     rax, [rdi+48h]
0x140015505  mov     [rbp+var_40], rax
0x140015509  mov     eax, [rdi+20h]
0x14001550c  mov     dword ptr [rbp+arg_18], eax
0x14001550f  mov     rax, [rdi+18h]
0x140015513  mov     [rbp+var_38], rax
0x140015517  mov     eax, [rdi]
0x140015519  mov     [rbp+var_80], eax
0x14001551c  mov     rax, [rdi+80h]
0x140015523  mov     [rbp+var_30], rax
0x140015527  mov     eax, [rdi+40h]
0x14001552a  mov     [rbp+var_7C], eax
0x14001552d  mov     rax, [rdi+38h]
0x140015531  mov     [rbp+var_28], rax
0x140015535  mov     eax, [rdi+8]
0x140015538  mov     [rbp+var_78], eax
0x14001553b  lea     rax, [rbp+var_68]
0x14001553f  mov     [rsp+130h+var_90], rax
0x140015547  lea     rax, [rbp+var_60]
0x14001554b  mov     [rsp+130h+var_98], rax
0x140015553  lea     rax, [rbp+var_58]
0x140015557  mov     [rsp+130h+var_A0], rax
0x14001555f  lea     rax, [rbp+arg_0]
0x140015563  mov     [rsp+130h+var_A8], rax
0x14001556b  lea     rax, [rbp+var_50]
0x14001556f  mov     [rsp+130h+var_B0], rax
0x140015577  lea     rax, [rbp+var_48]
0x14001557b  mov     [rsp+130h+var_B8], rax
0x140015580  lea     rax, [rbp+arg_10]
0x140015584  mov     [rsp+130h+var_C0], rax
0x140015589  lea     rax, [rbp+var_40]
0x14001558d  mov     [rsp+130h+var_C8], rax
0x140015592  lea     rax, [rbp+arg_18]
0x140015596  mov     [rsp+130h+var_D0], rax
0x14001559b  lea     rax, [rbp+var_38]
0x14001559f  mov     [rsp+130h+var_D8], rax
0x1400155a4  lea     rax, [rbp+var_80]
0x1400155a8  mov     [rsp+130h+var_E0], rax
0x1400155ad  lea     rax, [rbp+var_30]
0x1400155b1  mov     [rsp+130h+var_E8], rax
0x1400155b6  lea     rax, [rbp+var_7C]
0x1400155ba  mov     [rsp+130h+var_F0], rax
0x1400155bf  lea     rax, [rbp+var_28]
0x1400155c3  mov     [rsp+130h+var_F8], rax
0x1400155c8  lea     rax, [rbp+var_78]
0x1400155cc  mov     [rsp+130h+var_100], rax
0x1400155d1  lea     rax, [rbp+var_20]
0x1400155d5  mov     [rsp+130h+var_108], rax
0x1400155da  lea     rax, [rbp+var_70]
0x1400155de  mov     [rsp+130h+var_110], rax
0x1400155e3  mov     [rbp+var_68], rsi
0x1400155e7  mov     [rbp+var_20], 1000000h
0x1400155ef  mov     [rbp+var_70], 0
0x1400155f7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400155fc  jmp     loc_140015685
0x140015601  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015606  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14001560b  mov     rdi, rax
0x14001560e  mov     ecx, [rax]
0x140015610  cmp     ecx, 5
0x140015613  jbe     short loc_140015685
0x140015615  mov     rdx, 200000000000h
0x14001561f  mov     rcx, rax
0x140015622  call    _tlgKeywordOn
0x140015627  test    al, al
0x140015629  jz      short loc_140015685
0x14001562b  mov     [rbp+arg_18], rsi
0x14001562f  call    cs:__imp_GetCurrentThreadId
0x140015635  mov     r8, [rbx+110h]
0x14001563c  lea     rdx, unk_1400247C0
0x140015643  mov     [rbp+arg_0], eax
0x140015646  mov     rcx, rdi
0x140015649  mov     eax, [r8+48h]
0x14001564d  add     r8, 8
0x140015651  mov     [rbp+arg_10], eax
0x140015654  lea     rax, [rbp+arg_18]
0x140015658  mov     [rsp+130h+var_F8], rax
0x14001565d  lea     rax, [rbp+arg_0]
0x140015661  mov     [rsp+130h+var_100], rax
0x140015666  lea     rax, [rbp+arg_10]
0x14001566a  mov     [rsp+130h+var_108], rax
0x14001566f  lea     rax, [rbp+var_70]
0x140015673  mov     [rsp+130h+var_110], rax
0x140015678  mov     [rbp+var_70], 0
0x140015680  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140015685  mov     rcx, rbx
0x140015688  mov     rbx, [rsp+130h+arg_8]
0x140015690  add     rsp, 120h
0x140015697  pop     rdi
0x140015698  pop     rsi
0x140015699  pop     rbp
0x14001569a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```

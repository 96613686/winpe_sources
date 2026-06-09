# ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity(void)

- ea: `0x18001139c`
- end: `0x1800114d0`
- name: `?StartActivity@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXXZ`
- size: `308`
- prototype: `void __fastcall(ControllerHostTelemetry::CreateVirtualTouchPad *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b314`

## callees

- `0x180001a44`
- `0x180001a54`
- `0x180001c6c`
- `0x180002bdc`
- `0x18000dd10`
- `0x18000ea48`
- `0x1800102f8`
- `0x18001139c`
- `0x18001266c`
- `0x1800126b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011418`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011418`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity(
        ControllerHostTelemetry::CreateVirtualTouchPad *this)
{
  DWORD CurrentThreadId; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v2[4]; // [rsp+3Ch] [rbp-4Ch] BYREF
  ControllerHostTelemetry::CreateVirtualTouchPad *v3; // [rsp+40h] [rbp-48h]
  const struct _tlgProvider_t *v4; // [rsp+48h] [rbp-40h]
  const struct _tlgProvider_t *v5; // [rsp+50h] [rbp-38h]
  _BYTE v6[8]; // [rsp+58h] [rbp-30h] BYREF
  _BYTE *v7; // [rsp+60h] [rbp-28h]
  _BYTE *v8; // [rsp+68h] [rbp-20h]
  __int64 v9; // [rsp+70h] [rbp-18h]
  __int64 v10; // [rsp+78h] [rbp-10h]

  v3 = this;
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
  v4 = ControllerHostLogging::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v2, &CurrentThreadId);
    v7 = v2;
    _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(
      v6,
      &`ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity'::`4'::_tlgActivityPrivacyTag);
    v8 = v6;
    v9 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(v3);
    v10 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v3);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v4,
      (unsigned int)byte_1800207BB,
      v10,
      v9,
      (__int64)v8,
      (__int64)v7);
  }
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001139c  mov     [rsp+arg_0], rcx
0x1800113a1  sub     rsp, 88h
0x1800113a8  mov     rax, [rsp+88h+arg_0]
0x1800113b0  mov     [rsp+88h+var_48], rax
0x1800113b5  mov     rcx, [rsp+88h+var_48]
0x1800113ba  call    ?zInternalStart@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800113bf  nop
0x1800113c0  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x1800113c5  mov     [rsp+88h+var_40], rax
0x1800113ca  mov     rax, [rsp+88h+var_40]
0x1800113cf  mov     [rsp+88h+var_38], rax
0x1800113d4  mov     [rsp+88h+var_58], 0
0x1800113dc  mov     rax, [rsp+88h+var_38]
0x1800113e1  mov     eax, [rax]
0x1800113e3  mov     [rsp+88h+var_58], eax
0x1800113e7  mov     eax, [rsp+88h+var_58]
0x1800113eb  mov     [rsp+88h+var_54], eax
0x1800113ef  mov     eax, [rsp+88h+var_54]
0x1800113f3  cmp     eax, 5
0x1800113f6  jbe     loc_1800114A6
0x1800113fc  mov     rdx, cs:qword_1800207BE
0x180011403  mov     rcx, [rsp+88h+var_40]
0x180011408  call    _tlgKeywordOn
0x18001140d  movzx   eax, al
0x180011410  test    eax, eax
0x180011412  jz      loc_1800114A6
0x180011418  call    cs:__imp_GetCurrentThreadId
0x18001141e  mov     [rsp+88h+var_50], eax
0x180011422  lea     rdx, [rsp+88h+var_50]
0x180011427  lea     rcx, [rsp+88h+var_4C]
0x18001142c  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011431  nop
0x180011432  lea     rax, [rsp+88h+var_4C]
0x180011437  mov     [rsp+88h+var_28], rax
0x18001143c  lea     rdx, ?_tlgActivityPrivacyTag@?3??StartActivity@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXXZ@4_KB; unsigned __int64 const `ControllerHostTelemetry::CreateVirtualTouchPad::StartActivity(void)'::`4'::_tlgActivityPrivacyTag
0x180011443  lea     rcx, [rsp+88h+var_30]
0x180011448  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x18001144d  nop
0x18001144e  lea     rax, [rsp+88h+var_30]
0x180011453  mov     [rsp+88h+var_20], rax
0x180011458  mov     rcx, [rsp+88h+var_48]
0x18001145d  call    ?zInternalRelatedId@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180011462  mov     [rsp+88h+var_18], rax
0x180011467  mov     rcx, [rsp+88h+var_48]
0x18001146c  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180011471  mov     [rsp+88h+var_10], rax
0x180011476  mov     rax, [rsp+88h+var_28]
0x18001147b  mov     [rsp+88h+var_60], rax
0x180011480  mov     rax, [rsp+88h+var_20]
0x180011485  mov     [rsp+88h+var_68], rax
0x18001148a  mov     r9, [rsp+88h+var_18]
0x18001148f  mov     r8, [rsp+88h+var_10]
0x180011494  lea     rdx, byte_1800207BB
0x18001149b  mov     rcx, [rsp+88h+var_40]
0x1800114a0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800114a5  nop
0x1800114a6  xor     eax, eax
0x1800114a8  test    eax, eax
0x1800114aa  jnz     loc_1800113C0
0x1800114b0  xor     eax, eax
0x1800114b2  test    eax, eax
0x1800114b4  jnz     loc_1800113A8
0x1800114ba  mov     rcx, [rsp+88h+arg_0]
0x1800114c2  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800114c7  nop
0x1800114c8  add     rsp, 88h
0x1800114cf  retn
```

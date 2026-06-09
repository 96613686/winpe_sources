# ControllerHostTelemetry::InputInjectionSession::StartActivity(void)

- ea: `0x180017884`
- end: `0x1800179b8`
- name: `?StartActivity@InputInjectionSession@ControllerHostTelemetry@@QEAAXXZ`
- size: `308`
- prototype: `void __fastcall(ControllerHostTelemetry::InputInjectionSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800174bc`

## callees

- `0x180001a44`
- `0x180001a54`
- `0x180001c6c`
- `0x180002bdc`
- `0x18000dd10`
- `0x18000ea48`
- `0x1800102f8`
- `0x18001266c`
- `0x1800126b4`
- `0x180017884`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017900`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::InputInjectionSession::StartActivity(
        ControllerHostTelemetry::InputInjectionSession *this)
{
  DWORD CurrentThreadId; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v2[4]; // [rsp+3Ch] [rbp-4Ch] BYREF
  ControllerHostTelemetry::InputInjectionSession *v3; // [rsp+40h] [rbp-48h]
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
      &`ControllerHostTelemetry::InputInjectionSession::StartActivity'::`4'::_tlgActivityPrivacyTag);
    v8 = v6;
    v9 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(v3);
    v10 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v3);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v4,
      (unsigned int)byte_1800213C0,
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
0x180017884  mov     [rsp+arg_0], rcx
0x180017889  sub     rsp, 88h
0x180017890  mov     rax, [rsp+88h+arg_0]
0x180017898  mov     [rsp+88h+var_48], rax
0x18001789d  mov     rcx, [rsp+88h+var_48]
0x1800178a2  call    ?zInternalStart@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800178a7  nop
0x1800178a8  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x1800178ad  mov     [rsp+88h+var_40], rax
0x1800178b2  mov     rax, [rsp+88h+var_40]
0x1800178b7  mov     [rsp+88h+var_38], rax
0x1800178bc  mov     [rsp+88h+var_58], 0
0x1800178c4  mov     rax, [rsp+88h+var_38]
0x1800178c9  mov     eax, [rax]
0x1800178cb  mov     [rsp+88h+var_58], eax
0x1800178cf  mov     eax, [rsp+88h+var_58]
0x1800178d3  mov     [rsp+88h+var_54], eax
0x1800178d7  mov     eax, [rsp+88h+var_54]
0x1800178db  cmp     eax, 5
0x1800178de  jbe     loc_18001798E
0x1800178e4  mov     rdx, cs:qword_1800213C3
0x1800178eb  mov     rcx, [rsp+88h+var_40]
0x1800178f0  call    _tlgKeywordOn
0x1800178f5  movzx   eax, al
0x1800178f8  test    eax, eax
0x1800178fa  jz      loc_18001798E
0x180017900  call    cs:__imp_GetCurrentThreadId
0x180017906  mov     [rsp+88h+var_50], eax
0x18001790a  lea     rdx, [rsp+88h+var_50]
0x18001790f  lea     rcx, [rsp+88h+var_4C]
0x180017914  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017919  nop
0x18001791a  lea     rax, [rsp+88h+var_4C]
0x18001791f  mov     [rsp+88h+var_28], rax
0x180017924  lea     rdx, ?_tlgActivityPrivacyTag@?3??StartActivity@InputInjectionSession@ControllerHostTelemetry@@QEAAXXZ@4_KB; unsigned __int64 const `ControllerHostTelemetry::InputInjectionSession::StartActivity(void)'::`4'::_tlgActivityPrivacyTag
0x18001792b  lea     rcx, [rsp+88h+var_30]
0x180017930  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180017935  nop
0x180017936  lea     rax, [rsp+88h+var_30]
0x18001793b  mov     [rsp+88h+var_20], rax
0x180017940  mov     rcx, [rsp+88h+var_48]
0x180017945  call    ?zInternalRelatedId@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x18001794a  mov     [rsp+88h+var_18], rax
0x18001794f  mov     rcx, [rsp+88h+var_48]
0x180017954  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180017959  mov     [rsp+88h+var_10], rax
0x18001795e  mov     rax, [rsp+88h+var_28]
0x180017963  mov     [rsp+88h+var_60], rax
0x180017968  mov     rax, [rsp+88h+var_20]
0x18001796d  mov     [rsp+88h+var_68], rax
0x180017972  mov     r9, [rsp+88h+var_18]
0x180017977  mov     r8, [rsp+88h+var_10]
0x18001797c  lea     rdx, byte_1800213C0
0x180017983  mov     rcx, [rsp+88h+var_40]
0x180017988  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001798d  nop
0x18001798e  xor     eax, eax
0x180017990  test    eax, eax
0x180017992  jnz     loc_1800178A8
0x180017998  xor     eax, eax
0x18001799a  test    eax, eax
0x18001799c  jnz     loc_180017890
0x1800179a2  mov     rcx, [rsp+88h+arg_0]
0x1800179aa  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800179af  nop
0x1800179b0  add     rsp, 88h
0x1800179b7  retn
```

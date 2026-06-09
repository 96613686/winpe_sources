# LUATelemetry::EnsurePackageShutdownActivity::StartActivity(void)

- ea: `0x180036dc8`
- end: `0x180036e5e`
- name: `?StartActivity@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002cf84`

## callees

- `0x18000cb30`
- `0x18000d7f0`
- `0x1800187bc`
- `0x180018a5c`
- `0x180018dcc`
- `0x18001ef50`
- `0x180033c0c`
- `0x180036dc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036dfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036dfd`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::StartActivity(
        LUATelemetry::EnsurePackageShutdownActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const GUID *v8; // rax
  const GUID *v9; // r9
  DWORD v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    v10 = CurrentThreadId;
    v5 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v8 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                         this,
                         v6,
                         v7,
                         v5);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      byte_18005330F,
      v8,
      v9,
      (__int64)&v11,
      (__int64)&v10);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180036dc8  mov     [rsp+arg_10], rbx
0x180036dcd  push    rdi
0x180036dce  sub     rsp, 30h
0x180036dd2  mov     rbx, rcx
0x180036dd5  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180036dda  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180036ddf  mov     rdi, rax
0x180036de2  cmp     dword ptr [rax], 5
0x180036de5  jbe     short loc_180036E4C
0x180036de7  mov     rdx, 200000000000h
0x180036df1  mov     rcx, rax
0x180036df4  call    _tlgKeywordOn
0x180036df9  test    al, al
0x180036dfb  jz      short loc_180036E4C
0x180036dfd  call    cs:__imp_GetCurrentThreadId
0x180036e04  nop     dword ptr [rax+rax+00h]
0x180036e09  and     [rsp+38h+arg_8], 0
0x180036e0f  mov     rcx, rbx
0x180036e12  mov     [rsp+38h+arg_0], eax
0x180036e16  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180036e1b  mov     rcx, rbx
0x180036e1e  mov     r9, rax
0x180036e21  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180036e26  lea     rcx, [rsp+38h+arg_0]
0x180036e2b  mov     r8, rax
0x180036e2e  mov     [rsp+38h+var_10], rcx
0x180036e33  lea     rdx, byte_18005330F
0x180036e3a  lea     rcx, [rsp+38h+arg_8]
0x180036e3f  mov     [rsp+38h+var_18], rcx
0x180036e44  mov     rcx, rdi
0x180036e47  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180036e4c  mov     rcx, rbx
0x180036e4f  mov     rbx, [rsp+38h+arg_10]
0x180036e54  add     rsp, 30h
0x180036e58  pop     rdi
0x180036e59  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

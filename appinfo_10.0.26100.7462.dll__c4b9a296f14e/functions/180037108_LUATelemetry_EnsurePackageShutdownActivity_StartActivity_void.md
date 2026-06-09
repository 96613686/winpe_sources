# LUATelemetry::EnsurePackageShutdownActivity::StartActivity(void)

- ea: `0x180037108`
- end: `0x18003719e`
- name: `?StartActivity@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002d054`

## callees

- `0x18000cb30`
- `0x18000d7f0`
- `0x1800187bc`
- `0x180018a5c`
- `0x180018dcc`
- `0x18001ef50`
- `0x180033ecc`
- `0x180037108`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003713d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003713d`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::StartActivity(
        LUATelemetry::EnsurePackageShutdownActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  const GUID *v5; // rax
  const GUID *v6; // r9
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v7 = CurrentThreadId;
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v5 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      byte_1800520B0,
      v5,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180037108  mov     [rsp+arg_10], rbx
0x18003710d  push    rdi
0x18003710e  sub     rsp, 30h
0x180037112  mov     rbx, rcx
0x180037115  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003711a  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003711f  mov     rdi, rax
0x180037122  cmp     dword ptr [rax], 5
0x180037125  jbe     short loc_18003718C
0x180037127  mov     rdx, 200000000000h
0x180037131  mov     rcx, rax
0x180037134  call    _tlgKeywordOn
0x180037139  test    al, al
0x18003713b  jz      short loc_18003718C
0x18003713d  call    cs:__imp_GetCurrentThreadId
0x180037144  nop     dword ptr [rax+rax+00h]
0x180037149  and     [rsp+38h+arg_8], 0
0x18003714f  mov     rcx, rbx
0x180037152  mov     [rsp+38h+arg_0], eax
0x180037156  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x18003715b  mov     rcx, rbx
0x18003715e  mov     r9, rax
0x180037161  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037166  lea     rcx, [rsp+38h+arg_0]
0x18003716b  mov     r8, rax
0x18003716e  mov     [rsp+38h+var_10], rcx
0x180037173  lea     rdx, byte_1800520B0
0x18003717a  lea     rcx, [rsp+38h+arg_8]
0x18003717f  mov     [rsp+38h+var_18], rcx
0x180037184  mov     rcx, rdi
0x180037187  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003718c  mov     rcx, rbx
0x18003718f  mov     rbx, [rsp+38h+arg_10]
0x180037194  add     rsp, 30h
0x180037198  pop     rdi
0x180037199  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

# LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(void)

- ea: `0x1800189c0`
- end: `0x180018a56`
- name: `?StartActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180027534`

## callees

- `0x18000cb30`
- `0x18000d7f0`
- `0x1800187bc`
- `0x1800189c0`
- `0x180018a5c`
- `0x180018dcc`
- `0x18001ef50`
- `0x180033ecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800189f5`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(
        LUATelemetry::GetPackageActivationTokenForFilePath *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  int v5; // eax
  int v6; // r9d
  DWORD v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v7 = CurrentThreadId;
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v5 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_180054039,
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
0x1800189c0  mov     [rsp+arg_10], rbx
0x1800189c5  push    rdi
0x1800189c6  sub     rsp, 30h
0x1800189ca  mov     rbx, rcx
0x1800189cd  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800189d2  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x1800189d7  mov     rdi, rax
0x1800189da  cmp     dword ptr [rax], 5
0x1800189dd  jbe     short loc_180018A44
0x1800189df  mov     rdx, 200000000000h
0x1800189e9  mov     rcx, rax
0x1800189ec  call    _tlgKeywordOn
0x1800189f1  test    al, al
0x1800189f3  jz      short loc_180018A44
0x1800189f5  call    cs:__imp_GetCurrentThreadId
0x1800189fc  nop     dword ptr [rax+rax+00h]
0x180018a01  and     [rsp+38h+arg_8], 0
0x180018a07  mov     rcx, rbx
0x180018a0a  mov     [rsp+38h+arg_0], eax
0x180018a0e  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180018a13  mov     rcx, rbx
0x180018a16  mov     r9, rax
0x180018a19  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180018a1e  lea     rcx, [rsp+38h+arg_0]
0x180018a23  mov     r8, rax
0x180018a26  mov     [rsp+38h+var_10], rcx
0x180018a2b  lea     rdx, unk_180054039
0x180018a32  lea     rcx, [rsp+38h+arg_8]
0x180018a37  mov     [rsp+38h+var_18], rcx
0x180018a3c  mov     rcx, rdi
0x180018a3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018a44  mov     rcx, rbx
0x180018a47  mov     rbx, [rsp+38h+arg_10]
0x180018a4c  add     rsp, 30h
0x180018a50  pop     rdi
0x180018a51  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

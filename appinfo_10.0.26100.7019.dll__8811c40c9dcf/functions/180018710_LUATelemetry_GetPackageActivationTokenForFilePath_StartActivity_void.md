# LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(void)

- ea: `0x180018710`
- end: `0x1800187a6`
- name: `?StartActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180029ce4`

## callees

- `0x18000cb30`
- `0x18000d7f0`
- `0x18001850c`
- `0x180018710`
- `0x1800187ac`
- `0x180018b1c`
- `0x18001eb10`
- `0x180033b5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018745`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018745`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::StartActivity(
        LUATelemetry::GetPackageActivationTokenForFilePath *this)
{
  const struct _tlgProvider_t *v2; // rax
  int v3; // edi
  DWORD CurrentThreadId; // eax
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  int v9; // r9d
  DWORD v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = LUATelemetry::Provider();
  v3 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    v10 = CurrentThreadId;
    v5 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    v8 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
           this,
           v6,
           v7,
           v5);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v3,
      (unsigned int)&unk_18004F9E5,
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
0x180018710  mov     [rsp+arg_10], rbx
0x180018715  push    rdi
0x180018716  sub     rsp, 30h
0x18001871a  mov     rbx, rcx
0x18001871d  call    ?zInternalStart@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180018722  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180018727  mov     rdi, rax
0x18001872a  cmp     dword ptr [rax], 5
0x18001872d  jbe     short loc_180018794
0x18001872f  mov     rdx, 200000000000h
0x180018739  mov     rcx, rax
0x18001873c  call    _tlgKeywordOn
0x180018741  test    al, al
0x180018743  jz      short loc_180018794
0x180018745  call    cs:__imp_GetCurrentThreadId
0x18001874c  nop     dword ptr [rax+rax+00h]
0x180018751  and     [rsp+38h+arg_8], 0
0x180018757  mov     rcx, rbx
0x18001875a  mov     [rsp+38h+arg_0], eax
0x18001875e  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180018763  mov     rcx, rbx
0x180018766  mov     r9, rax
0x180018769  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18001876e  lea     rcx, [rsp+38h+arg_0]
0x180018773  mov     r8, rax
0x180018776  mov     [rsp+38h+var_10], rcx
0x18001877b  lea     rdx, unk_18004F9E5
0x180018782  lea     rcx, [rsp+38h+arg_8]
0x180018787  mov     [rsp+38h+var_18], rcx
0x18001878c  mov     rcx, rdi
0x18001878f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018794  mov     rcx, rbx
0x180018797  mov     rbx, [rsp+38h+arg_10]
0x18001879c  add     rsp, 30h
0x1800187a0  pop     rdi
0x1800187a1  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

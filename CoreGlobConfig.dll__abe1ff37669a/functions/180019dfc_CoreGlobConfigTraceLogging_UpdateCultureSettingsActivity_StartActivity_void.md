# CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StartActivity(void)

- ea: `0x180019dfc`
- end: `0x180019eb5`
- name: `?StartActivity@UpdateCultureSettingsActivity@CoreGlobConfigTraceLogging@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18001b6e0`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x1800145ec`
- `0x180016fcc`
- `0x180019dfc`
- `0x18001effc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019e37`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StartActivity(
        CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = CoreGlobConfigTraceLogging::Provider();
  v4 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL, v3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 16779264;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (__int64)byte_180029F73,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180019dfc  mov     [rsp+arg_10], rbx
0x180019e01  push    rdi
0x180019e02  sub     rsp, 30h
0x180019e06  mov     rbx, rcx
0x180019e09  call    ?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180019e0e  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019e13  mov     rdi, rax
0x180019e16  mov     edx, [rax]
0x180019e18  cmp     edx, 5
0x180019e1b  jbe     loc_180019EA1
0x180019e21  mov     rdx, 200000000000h
0x180019e2b  mov     rcx, rax
0x180019e2e  call    _tlgKeywordOn
0x180019e33  test    al, al
0x180019e35  jz      short loc_180019EA1
0x180019e37  call    cs:__imp_GetCurrentThreadId
0x180019e3d  mov     [rsp+38h+arg_0], eax
0x180019e41  mov     [rsp+38h+arg_8], 1000800h
0x180019e4a  mov     r8, [rbx+110h]
0x180019e51  cmp     byte ptr [r8+4], 0
0x180019e56  jz      short loc_180019E77
0x180019e58  lea     r9, [r8+18h]
0x180019e5c  cmp     dword ptr [r9], 0
0x180019e60  jnz     short loc_180019E7A
0x180019e62  cmp     dword ptr [r9+4], 0
0x180019e67  jnz     short loc_180019E7A
0x180019e69  cmp     dword ptr [r9+8], 0
0x180019e6e  jnz     short loc_180019E7A
0x180019e70  cmp     dword ptr [r9+0Ch], 0
0x180019e75  jnz     short loc_180019E7A
0x180019e77  xor     r9d, r9d
0x180019e7a  add     r8, 8
0x180019e7e  lea     rax, [rsp+38h+arg_0]
0x180019e83  mov     [rsp+38h+var_10], rax
0x180019e88  lea     rax, [rsp+38h+arg_8]
0x180019e8d  mov     [rsp+38h+var_18], rax
0x180019e92  lea     rdx, byte_180029F73
0x180019e99  mov     rcx, rdi
0x180019e9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019ea1  mov     rcx, rbx
0x180019ea4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019ea9  nop
0x180019eaa  mov     rbx, [rsp+38h+arg_10]
0x180019eaf  add     rsp, 30h
0x180019eb3  pop     rdi
0x180019eb4  retn
```

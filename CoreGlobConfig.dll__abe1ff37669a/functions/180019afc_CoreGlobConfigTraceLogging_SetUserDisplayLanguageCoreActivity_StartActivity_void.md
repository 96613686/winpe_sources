# CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StartActivity(void)

- ea: `0x180019afc`
- end: `0x180019bb5`
- name: `?StartActivity@SetUserDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001ff10`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x1800145ec`
- `0x180016fcc`
- `0x180019afc`
- `0x18001effc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019b37`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity::StartActivity(
        CoreGlobConfigTraceLogging::SetUserDisplayLanguageCoreActivity *this)
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
      (__int64)&unk_180029FC8,
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
0x180019afc  mov     [rsp+arg_10], rbx
0x180019b01  push    rdi
0x180019b02  sub     rsp, 30h
0x180019b06  mov     rbx, rcx
0x180019b09  call    ?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180019b0e  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019b13  mov     rdi, rax
0x180019b16  mov     edx, [rax]
0x180019b18  cmp     edx, 5
0x180019b1b  jbe     loc_180019BA1
0x180019b21  mov     rdx, 200000000000h
0x180019b2b  mov     rcx, rax
0x180019b2e  call    _tlgKeywordOn
0x180019b33  test    al, al
0x180019b35  jz      short loc_180019BA1
0x180019b37  call    cs:__imp_GetCurrentThreadId
0x180019b3d  mov     [rsp+38h+arg_0], eax
0x180019b41  mov     [rsp+38h+arg_8], 1000800h
0x180019b4a  mov     r8, [rbx+110h]
0x180019b51  cmp     byte ptr [r8+4], 0
0x180019b56  jz      short loc_180019B77
0x180019b58  lea     r9, [r8+18h]
0x180019b5c  cmp     dword ptr [r9], 0
0x180019b60  jnz     short loc_180019B7A
0x180019b62  cmp     dword ptr [r9+4], 0
0x180019b67  jnz     short loc_180019B7A
0x180019b69  cmp     dword ptr [r9+8], 0
0x180019b6e  jnz     short loc_180019B7A
0x180019b70  cmp     dword ptr [r9+0Ch], 0
0x180019b75  jnz     short loc_180019B7A
0x180019b77  xor     r9d, r9d
0x180019b7a  add     r8, 8
0x180019b7e  lea     rax, [rsp+38h+arg_0]
0x180019b83  mov     [rsp+38h+var_10], rax
0x180019b88  lea     rax, [rsp+38h+arg_8]
0x180019b8d  mov     [rsp+38h+var_18], rax
0x180019b92  lea     rdx, unk_180029FC8
0x180019b99  mov     rcx, rdi
0x180019b9c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019ba1  mov     rcx, rbx
0x180019ba4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019ba9  nop
0x180019baa  mov     rbx, [rsp+38h+arg_10]
0x180019baf  add     rsp, 30h
0x180019bb3  pop     rdi
0x180019bb4  retn
```

# CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StartActivity(void)

- ea: `0x180019bbc`
- end: `0x180019c75`
- name: `?StartActivity@SyncLanguageDataFromCloudActivity@CoreGlobConfigTraceLogging@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180020010`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x1800145ec`
- `0x180016fcc`
- `0x180019bbc`
- `0x18001effc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bf7`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity::StartActivity(
        CoreGlobConfigTraceLogging::SyncLanguageDataFromCloudActivity *this)
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
      (__int64)byte_180029E61,
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
0x180019bbc  mov     [rsp+arg_10], rbx
0x180019bc1  push    rdi
0x180019bc2  sub     rsp, 30h
0x180019bc6  mov     rbx, rcx
0x180019bc9  call    ?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180019bce  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019bd3  mov     rdi, rax
0x180019bd6  mov     edx, [rax]
0x180019bd8  cmp     edx, 5
0x180019bdb  jbe     loc_180019C61
0x180019be1  mov     rdx, 200000000000h
0x180019beb  mov     rcx, rax
0x180019bee  call    _tlgKeywordOn
0x180019bf3  test    al, al
0x180019bf5  jz      short loc_180019C61
0x180019bf7  call    cs:__imp_GetCurrentThreadId
0x180019bfd  mov     [rsp+38h+arg_0], eax
0x180019c01  mov     [rsp+38h+arg_8], 1000800h
0x180019c0a  mov     r8, [rbx+110h]
0x180019c11  cmp     byte ptr [r8+4], 0
0x180019c16  jz      short loc_180019C37
0x180019c18  lea     r9, [r8+18h]
0x180019c1c  cmp     dword ptr [r9], 0
0x180019c20  jnz     short loc_180019C3A
0x180019c22  cmp     dword ptr [r9+4], 0
0x180019c27  jnz     short loc_180019C3A
0x180019c29  cmp     dword ptr [r9+8], 0
0x180019c2e  jnz     short loc_180019C3A
0x180019c30  cmp     dword ptr [r9+0Ch], 0
0x180019c35  jnz     short loc_180019C3A
0x180019c37  xor     r9d, r9d
0x180019c3a  add     r8, 8
0x180019c3e  lea     rax, [rsp+38h+arg_0]
0x180019c43  mov     [rsp+38h+var_10], rax
0x180019c48  lea     rax, [rsp+38h+arg_8]
0x180019c4d  mov     [rsp+38h+var_18], rax
0x180019c52  lea     rdx, byte_180029E61
0x180019c59  mov     rcx, rdi
0x180019c5c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019c61  mov     rcx, rbx
0x180019c64  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019c69  nop
0x180019c6a  mov     rbx, [rsp+38h+arg_10]
0x180019c6f  add     rsp, 30h
0x180019c73  pop     rdi
0x180019c74  retn
```

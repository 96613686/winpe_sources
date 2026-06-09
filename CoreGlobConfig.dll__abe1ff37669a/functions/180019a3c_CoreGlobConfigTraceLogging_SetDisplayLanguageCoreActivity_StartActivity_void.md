# CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StartActivity(void)

- ea: `0x180019a3c`
- end: `0x180019af5`
- name: `?StartActivity@SetDisplayLanguageCoreActivity@CoreGlobConfigTraceLogging@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001fe10`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x1800145ec`
- `0x180016fcc`
- `0x180019a3c`
- `0x18001effc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a77`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity::StartActivity(
        CoreGlobConfigTraceLogging::SetDisplayLanguageCoreActivity *this)
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
      (__int64)word_18002A022,
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
0x180019a3c  mov     [rsp+arg_10], rbx
0x180019a41  push    rdi
0x180019a42  sub     rsp, 30h
0x180019a46  mov     rbx, rcx
0x180019a49  call    ?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180019a4e  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019a53  mov     rdi, rax
0x180019a56  mov     edx, [rax]
0x180019a58  cmp     edx, 5
0x180019a5b  jbe     loc_180019AE1
0x180019a61  mov     rdx, 200000000000h
0x180019a6b  mov     rcx, rax
0x180019a6e  call    _tlgKeywordOn
0x180019a73  test    al, al
0x180019a75  jz      short loc_180019AE1
0x180019a77  call    cs:__imp_GetCurrentThreadId
0x180019a7d  mov     [rsp+38h+arg_0], eax
0x180019a81  mov     [rsp+38h+arg_8], 1000800h
0x180019a8a  mov     r8, [rbx+110h]
0x180019a91  cmp     byte ptr [r8+4], 0
0x180019a96  jz      short loc_180019AB7
0x180019a98  lea     r9, [r8+18h]
0x180019a9c  cmp     dword ptr [r9], 0
0x180019aa0  jnz     short loc_180019ABA
0x180019aa2  cmp     dword ptr [r9+4], 0
0x180019aa7  jnz     short loc_180019ABA
0x180019aa9  cmp     dword ptr [r9+8], 0
0x180019aae  jnz     short loc_180019ABA
0x180019ab0  cmp     dword ptr [r9+0Ch], 0
0x180019ab5  jnz     short loc_180019ABA
0x180019ab7  xor     r9d, r9d
0x180019aba  add     r8, 8
0x180019abe  lea     rax, [rsp+38h+arg_0]
0x180019ac3  mov     [rsp+38h+var_10], rax
0x180019ac8  lea     rax, [rsp+38h+arg_8]
0x180019acd  mov     [rsp+38h+var_18], rax
0x180019ad2  lea     rdx, word_18002A022
0x180019ad9  mov     rcx, rdi
0x180019adc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019ae1  mov     rcx, rbx
0x180019ae4  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019ae9  nop
0x180019aea  mov     rbx, [rsp+38h+arg_10]
0x180019aef  add     rsp, 30h
0x180019af3  pop     rdi
0x180019af4  retn
```

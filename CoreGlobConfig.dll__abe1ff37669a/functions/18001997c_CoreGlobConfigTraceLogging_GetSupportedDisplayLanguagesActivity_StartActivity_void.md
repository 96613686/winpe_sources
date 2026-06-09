# CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::StartActivity(void)

- ea: `0x18001997c`
- end: `0x180019a35`
- name: `?StartActivity@GetSupportedDisplayLanguagesActivity@CoreGlobConfigTraceLogging@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001fb70`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x1800145ec`
- `0x180016fcc`
- `0x18001997c`
- `0x18001effc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800199b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800199b7`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity::StartActivity(
        CoreGlobConfigTraceLogging::GetSupportedDisplayLanguagesActivity *this)
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
      (__int64)&unk_18002A078,
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
0x18001997c  mov     [rsp+arg_10], rbx
0x180019981  push    rdi
0x180019982  sub     rsp, 30h
0x180019986  mov     rbx, rcx
0x180019989  call    ?zInternalStart@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001998e  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x180019993  mov     rdi, rax
0x180019996  mov     edx, [rax]
0x180019998  cmp     edx, 5
0x18001999b  jbe     loc_180019A21
0x1800199a1  mov     rdx, 200000000000h
0x1800199ab  mov     rcx, rax
0x1800199ae  call    _tlgKeywordOn
0x1800199b3  test    al, al
0x1800199b5  jz      short loc_180019A21
0x1800199b7  call    cs:__imp_GetCurrentThreadId
0x1800199bd  mov     [rsp+38h+arg_0], eax
0x1800199c1  mov     [rsp+38h+arg_8], 1000800h
0x1800199ca  mov     r8, [rbx+110h]
0x1800199d1  cmp     byte ptr [r8+4], 0
0x1800199d6  jz      short loc_1800199F7
0x1800199d8  lea     r9, [r8+18h]
0x1800199dc  cmp     dword ptr [r9], 0
0x1800199e0  jnz     short loc_1800199FA
0x1800199e2  cmp     dword ptr [r9+4], 0
0x1800199e7  jnz     short loc_1800199FA
0x1800199e9  cmp     dword ptr [r9+8], 0
0x1800199ee  jnz     short loc_1800199FA
0x1800199f0  cmp     dword ptr [r9+0Ch], 0
0x1800199f5  jnz     short loc_1800199FA
0x1800199f7  xor     r9d, r9d
0x1800199fa  add     r8, 8
0x1800199fe  lea     rax, [rsp+38h+arg_0]
0x180019a03  mov     [rsp+38h+var_10], rax
0x180019a08  lea     rax, [rsp+38h+arg_8]
0x180019a0d  mov     [rsp+38h+var_18], rax
0x180019a12  lea     rdx, unk_18002A078
0x180019a19  mov     rcx, rdi
0x180019a1c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019a21  mov     rcx, rbx
0x180019a24  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019a29  nop
0x180019a2a  mov     rbx, [rsp+38h+arg_10]
0x180019a2f  add     rsp, 30h
0x180019a33  pop     rdi
0x180019a34  retn
```

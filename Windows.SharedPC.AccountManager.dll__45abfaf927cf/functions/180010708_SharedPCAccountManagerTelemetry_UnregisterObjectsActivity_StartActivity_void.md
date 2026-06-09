# SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StartActivity(void)

- ea: `0x180010708`
- end: `0x1800107ad`
- name: `?StartActivity@UnregisterObjectsActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180010060`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x18000ed2c`
- `0x180010708`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001073f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001073f`

## pseudocode

```c
void __fastcall SharedPCAccountManagerTelemetry::UnregisterObjectsActivity::StartActivity(
        SharedPCAccountManagerTelemetry::UnregisterObjectsActivity *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = SharedPCAccountManagerLogging::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x200000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_18002C4C3,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180010708  mov     [rsp+arg_10], rbx
0x18001070d  push    rdi
0x18001070e  sub     rsp, 30h
0x180010712  mov     rbx, rcx
0x180010715  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001071a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001071f  mov     rdi, rax
0x180010722  mov     edx, [rax]
0x180010724  cmp     edx, 5
0x180010727  jbe     short loc_180010799
0x180010729  mov     rdx, 200000000000h
0x180010733  mov     rcx, rax
0x180010736  call    _tlgKeywordOn
0x18001073b  test    al, al
0x18001073d  jz      short loc_180010799
0x18001073f  call    cs:__imp_GetCurrentThreadId
0x180010745  mov     [rsp+38h+arg_0], eax
0x180010749  mov     [rsp+38h+arg_8], 1000000h
0x180010752  mov     r8, [rbx+110h]
0x180010759  cmp     byte ptr [r8+4], 0
0x18001075e  jz      short loc_18001076D
0x180010760  lea     rcx, [r8+18h]; struct _GUID *
0x180010764  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180010769  test    al, al
0x18001076b  jz      short loc_18001076F
0x18001076d  xor     ecx, ecx
0x18001076f  add     r8, 8
0x180010773  lea     rax, [rsp+38h+arg_0]
0x180010778  mov     [rsp+38h+var_10], rax
0x18001077d  lea     rax, [rsp+38h+arg_8]
0x180010782  mov     [rsp+38h+var_18], rax
0x180010787  mov     r9, rcx
0x18001078a  lea     rdx, byte_18002C4C3
0x180010791  mov     rcx, rdi
0x180010794  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180010799  mov     rcx, rbx
0x18001079c  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800107a1  nop
0x1800107a2  mov     rbx, [rsp+38h+arg_10]
0x1800107a7  add     rsp, 30h
0x1800107ab  pop     rdi
0x1800107ac  retn
```

# PolicyTelemetry::UserRequestPolicyEvaluation::StartActivity(void)

- ea: `0x18001d948`
- end: `0x18001d9ed`
- name: `?StartActivity@UserRequestPolicyEvaluation@PolicyTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(PolicyTelemetry::UserRequestPolicyEvaluation *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001d480`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x18001d948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d97f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d97f`

## pseudocode

```c
void __fastcall PolicyTelemetry::UserRequestPolicyEvaluation::StartActivity(
        PolicyTelemetry::UserRequestPolicyEvaluation *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = SharedPCAccountManagerLogging::Provider();
  v5 = (__int64)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 0x400000000000LL, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_18002E155,
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
0x18001d948  mov     [rsp+arg_10], rbx
0x18001d94d  push    rdi
0x18001d94e  sub     rsp, 30h
0x18001d952  mov     rbx, rcx
0x18001d955  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001d95a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001d95f  mov     rdi, rax
0x18001d962  mov     edx, [rax]
0x18001d964  cmp     edx, 5
0x18001d967  jbe     short loc_18001D9D9
0x18001d969  mov     rdx, 400000000000h
0x18001d973  mov     rcx, rax
0x18001d976  call    _tlgKeywordOn
0x18001d97b  test    al, al
0x18001d97d  jz      short loc_18001D9D9
0x18001d97f  call    cs:__imp_GetCurrentThreadId
0x18001d985  mov     [rsp+38h+arg_0], eax
0x18001d989  mov     [rsp+38h+arg_8], 1000000h
0x18001d992  mov     r8, [rbx+110h]
0x18001d999  cmp     byte ptr [r8+4], 0
0x18001d99e  jz      short loc_18001D9AD
0x18001d9a0  lea     rcx, [r8+18h]; struct _GUID *
0x18001d9a4  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18001d9a9  test    al, al
0x18001d9ab  jz      short loc_18001D9AF
0x18001d9ad  xor     ecx, ecx
0x18001d9af  add     r8, 8
0x18001d9b3  lea     rax, [rsp+38h+arg_0]
0x18001d9b8  mov     [rsp+38h+var_10], rax
0x18001d9bd  lea     rax, [rsp+38h+arg_8]
0x18001d9c2  mov     [rsp+38h+var_18], rax
0x18001d9c7  mov     r9, rcx
0x18001d9ca  lea     rdx, byte_18002E155
0x18001d9d1  mov     rcx, rdi
0x18001d9d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001d9d9  mov     rcx, rbx
0x18001d9dc  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001d9e1  nop
0x18001d9e2  mov     rbx, [rsp+38h+arg_10]
0x18001d9e7  add     rsp, 30h
0x18001d9eb  pop     rdi
0x18001d9ec  retn
```

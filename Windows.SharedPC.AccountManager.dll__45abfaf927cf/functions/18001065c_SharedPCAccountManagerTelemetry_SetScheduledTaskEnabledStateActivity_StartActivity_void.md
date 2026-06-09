# SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::StartActivity(void)

- ea: `0x18001065c`
- end: `0x180010701`
- name: `?StartActivity@SetScheduledTaskEnabledStateActivity@SharedPCAccountManagerTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800101c0`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x18000ed2c`
- `0x18001065c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010693`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010693`

## pseudocode

```c
void __fastcall SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity::StartActivity(
        SharedPCAccountManagerTelemetry::SetScheduledTaskEnabledStateActivity *this)
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
      (__int64)byte_18002C10D,
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
0x18001065c  mov     [rsp+arg_10], rbx
0x180010661  push    rdi
0x180010662  sub     rsp, 30h
0x180010666  mov     rbx, rcx
0x180010669  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001066e  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180010673  mov     rdi, rax
0x180010676  mov     edx, [rax]
0x180010678  cmp     edx, 5
0x18001067b  jbe     short loc_1800106ED
0x18001067d  mov     rdx, 200000000000h
0x180010687  mov     rcx, rax
0x18001068a  call    _tlgKeywordOn
0x18001068f  test    al, al
0x180010691  jz      short loc_1800106ED
0x180010693  call    cs:__imp_GetCurrentThreadId
0x180010699  mov     [rsp+38h+arg_0], eax
0x18001069d  mov     [rsp+38h+arg_8], 1000000h
0x1800106a6  mov     r8, [rbx+110h]
0x1800106ad  cmp     byte ptr [r8+4], 0
0x1800106b2  jz      short loc_1800106C1
0x1800106b4  lea     rcx, [r8+18h]; struct _GUID *
0x1800106b8  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800106bd  test    al, al
0x1800106bf  jz      short loc_1800106C3
0x1800106c1  xor     ecx, ecx
0x1800106c3  add     r8, 8
0x1800106c7  lea     rax, [rsp+38h+arg_0]
0x1800106cc  mov     [rsp+38h+var_10], rax
0x1800106d1  lea     rax, [rsp+38h+arg_8]
0x1800106d6  mov     [rsp+38h+var_18], rax
0x1800106db  mov     r9, rcx
0x1800106de  lea     rdx, byte_18002C10D
0x1800106e5  mov     rcx, rdi
0x1800106e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800106ed  mov     rcx, rbx
0x1800106f0  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800106f5  nop
0x1800106f6  mov     rbx, [rsp+38h+arg_10]
0x1800106fb  add     rsp, 30h
0x1800106ff  pop     rdi
0x180010700  retn
```

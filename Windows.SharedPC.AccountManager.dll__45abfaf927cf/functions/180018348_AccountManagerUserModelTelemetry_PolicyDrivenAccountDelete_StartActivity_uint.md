# AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StartActivity(uint)

- ea: `0x180018348`
- end: `0x1800183f8`
- name: `?StartActivity@PolicyDrivenAccountDelete@AccountManagerUserModelTelemetry@@QEAAXI@Z`
- size: `176`
- prototype: `void __fastcall(AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180015ee0`

## callees

- `0x180001384`
- `0x180001b0c`
- `0x18000db54`
- `0x18000ebf4`
- `0x18001790c`
- `0x180018348`
- `0x180019b6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018385`

## pseudocode

```c
void __fastcall AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete::StartActivity(
        AccountManagerUserModelTelemetry::PolicyDrivenAccountDelete *this,
        int a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // [rsp+60h] [rbp+8h] BYREF
  DWORD v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = AccountManagerUserModelTelemetry::Provider();
  v6 = (__int64)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v7, v5) )
  {
    v11 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_18002D4C3,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180018348  push    rbx
0x18001834a  push    rsi
0x18001834b  push    rdi
0x18001834c  sub     rsp, 40h
0x180018350  mov     esi, edx
0x180018352  mov     rbx, rcx
0x180018355  call    ?zInternalStart@?$ActivityBase@VAccountManagerUserModelTelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AccountManagerUserModelTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001835a  call    ?Provider@AccountManagerUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountManagerUserModelTelemetry::Provider(void)
0x18001835f  mov     rdi, rax
0x180018362  mov     r8d, [rax]
0x180018365  cmp     r8d, 5
0x180018369  jbe     short loc_1800183E9
0x18001836b  mov     rdx, 200000000000h
0x180018375  mov     rcx, rax
0x180018378  call    _tlgKeywordOn
0x18001837d  test    al, al
0x18001837f  jz      short loc_1800183E9
0x180018381  mov     [rsp+58h+arg_0], esi
0x180018385  call    cs:__imp_GetCurrentThreadId
0x18001838b  mov     r8, [rbx+110h]
0x180018392  mov     [rsp+58h+arg_10], eax
0x180018396  mov     [rsp+58h+arg_18], 0
0x18001839f  cmp     byte ptr [r8+4], 0
0x1800183a4  jz      short loc_1800183B3
0x1800183a6  lea     rcx, [r8+18h]; struct _GUID *
0x1800183aa  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800183af  test    al, al
0x1800183b1  jz      short loc_1800183B5
0x1800183b3  xor     ecx, ecx
0x1800183b5  lea     rax, [rsp+58h+arg_0]
0x1800183ba  mov     r9, rcx
0x1800183bd  mov     [rsp+58h+var_28], rax
0x1800183c2  lea     rdx, byte_18002D4C3
0x1800183c9  lea     rax, [rsp+58h+arg_10]
0x1800183ce  add     r8, 8
0x1800183d2  mov     [rsp+58h+var_30], rax
0x1800183d7  mov     rcx, rdi
0x1800183da  lea     rax, [rsp+58h+arg_18]
0x1800183df  mov     [rsp+58h+var_38], rax
0x1800183e4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800183e9  mov     rcx, rbx
0x1800183ec  add     rsp, 40h
0x1800183f0  pop     rdi
0x1800183f1  pop     rsi
0x1800183f2  pop     rbx
0x1800183f3  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```

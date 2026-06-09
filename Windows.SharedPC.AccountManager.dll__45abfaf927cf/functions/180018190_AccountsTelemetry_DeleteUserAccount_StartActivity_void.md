# AccountsTelemetry::DeleteUserAccount::StartActivity(void)

- ea: `0x180018190`
- end: `0x180018235`
- name: `?StartActivity@DeleteUserAccount@AccountsTelemetry@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(AccountsTelemetry::DeleteUserAccount *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015ee0`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000db54`
- `0x18000e00c`
- `0x18000ebf4`
- `0x180013fbc`
- `0x180018190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800181c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800181c7`

## pseudocode

```c
void __fastcall AccountsTelemetry::DeleteUserAccount::StartActivity(AccountsTelemetry::DeleteUserAccount *this)
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
      (__int64)byte_18002D983,
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
0x180018190  mov     [rsp+arg_10], rbx
0x180018195  push    rdi
0x180018196  sub     rsp, 30h
0x18001819a  mov     rbx, rcx
0x18001819d  call    ?zInternalStart@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800181a2  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800181a7  mov     rdi, rax
0x1800181aa  mov     edx, [rax]
0x1800181ac  cmp     edx, 5
0x1800181af  jbe     short loc_180018221
0x1800181b1  mov     rdx, 400000000000h
0x1800181bb  mov     rcx, rax
0x1800181be  call    _tlgKeywordOn
0x1800181c3  test    al, al
0x1800181c5  jz      short loc_180018221
0x1800181c7  call    cs:__imp_GetCurrentThreadId
0x1800181cd  mov     [rsp+38h+arg_0], eax
0x1800181d1  mov     [rsp+38h+arg_8], 1000000h
0x1800181da  mov     r8, [rbx+110h]
0x1800181e1  cmp     byte ptr [r8+4], 0
0x1800181e6  jz      short loc_1800181F5
0x1800181e8  lea     rcx, [r8+18h]; struct _GUID *
0x1800181ec  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800181f1  test    al, al
0x1800181f3  jz      short loc_1800181F7
0x1800181f5  xor     ecx, ecx
0x1800181f7  add     r8, 8
0x1800181fb  lea     rax, [rsp+38h+arg_0]
0x180018200  mov     [rsp+38h+var_10], rax
0x180018205  lea     rax, [rsp+38h+arg_8]
0x18001820a  mov     [rsp+38h+var_18], rax
0x18001820f  mov     r9, rcx
0x180018212  lea     rdx, byte_18002D983
0x180018219  mov     rcx, rdi
0x18001821c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018221  mov     rcx, rbx
0x180018224  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180018229  nop
0x18001822a  mov     rbx, [rsp+38h+arg_10]
0x18001822f  add     rsp, 30h
0x180018233  pop     rdi
0x180018234  retn
```

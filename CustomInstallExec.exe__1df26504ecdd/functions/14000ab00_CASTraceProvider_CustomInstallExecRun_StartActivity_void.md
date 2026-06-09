# CASTraceProvider::CustomInstallExecRun::StartActivity(void)

- ea: `0x14000ab00`
- end: `0x14000abb9`
- name: `?StartActivity@CustomInstallExecRun@CASTraceProvider@@QEAAXXZ`
- size: `185`
- prototype: `void __fastcall(CASTraceProvider::CustomInstallExecRun *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a8a8`

## callees

- `0x140001b5c`
- `0x14000258c`
- `0x140008ba0`
- `0x14000a594`
- `0x14000ab00`
- `0x14000ba4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ab3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ab3b`

## pseudocode

```c
void __fastcall CASTraceProvider::CustomInstallExecRun::StartActivity(CASTraceProvider::CustomInstallExecRun *this)
{
  __int64 v2; // rcx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = CASTraceProvider::Provider(v2);
  v6 = (__int64)v3;
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = 0x1000000;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4)
      || (v8 = v7 + 24, !*(_DWORD *)(v7 + 24))
      && !*(_DWORD *)(v7 + 28)
      && !*(_DWORD *)(v7 + 32)
      && !*(_DWORD *)(v7 + 36) )
    {
      v8 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)byte_140011CA1,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000ab00  mov     [rsp+arg_10], rbx
0x14000ab05  push    rdi
0x14000ab06  sub     rsp, 30h
0x14000ab0a  mov     rbx, rcx
0x14000ab0d  call    ?zInternalStart@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x14000ab12  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000ab17  mov     rdi, rax
0x14000ab1a  mov     edx, [rax]
0x14000ab1c  cmp     edx, 5
0x14000ab1f  jbe     loc_14000ABA5
0x14000ab25  mov     rdx, 400000000000h
0x14000ab2f  mov     rcx, rax
0x14000ab32  call    _tlgKeywordOn
0x14000ab37  test    al, al
0x14000ab39  jz      short loc_14000ABA5
0x14000ab3b  call    cs:__imp_GetCurrentThreadId
0x14000ab41  mov     [rsp+38h+arg_0], eax
0x14000ab45  mov     [rsp+38h+arg_8], 1000000h
0x14000ab4e  mov     r8, [rbx+110h]
0x14000ab55  cmp     byte ptr [r8+4], 0
0x14000ab5a  jz      short loc_14000AB7B
0x14000ab5c  lea     r9, [r8+18h]
0x14000ab60  cmp     dword ptr [r9], 0
0x14000ab64  jnz     short loc_14000AB7E
0x14000ab66  cmp     dword ptr [r9+4], 0
0x14000ab6b  jnz     short loc_14000AB7E
0x14000ab6d  cmp     dword ptr [r9+8], 0
0x14000ab72  jnz     short loc_14000AB7E
0x14000ab74  cmp     dword ptr [r9+0Ch], 0
0x14000ab79  jnz     short loc_14000AB7E
0x14000ab7b  xor     r9d, r9d
0x14000ab7e  add     r8, 8
0x14000ab82  lea     rax, [rsp+38h+arg_0]
0x14000ab87  mov     [rsp+38h+var_10], rax
0x14000ab8c  lea     rax, [rsp+38h+arg_8]
0x14000ab91  mov     [rsp+38h+var_18], rax
0x14000ab96  lea     rdx, byte_140011CA1
0x14000ab9d  mov     rcx, rdi
0x14000aba0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14000aba5  mov     rcx, rbx
0x14000aba8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x14000abad  nop
0x14000abae  mov     rbx, [rsp+38h+arg_10]
0x14000abb3  add     rsp, 30h
0x14000abb7  pop     rdi
0x14000abb8  retn
```

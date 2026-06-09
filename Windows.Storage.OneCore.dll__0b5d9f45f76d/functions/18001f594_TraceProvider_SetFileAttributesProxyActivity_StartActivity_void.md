# TraceProvider::SetFileAttributesProxyActivity::StartActivity(void)

- ea: `0x18001f594`
- end: `0x18001f62c`
- name: `?StartActivity@SetFileAttributesProxyActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::SetFileAttributesProxyActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021a40`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001f594`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f5b5`

## pseudocode

```c
void __fastcall TraceProvider::SetFileAttributesProxyActivity::StartActivity(
        TraceProvider::SetFileAttributesProxyActivity *this)
{
  const struct _tlgProvider_t *v2; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = TraceProvider::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = 0;
    v3 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v3 + 4)
      || (v4 = v3 + 24, !*(_DWORD *)(v3 + 24))
      && !*(_DWORD *)(v3 + 28)
      && !*(_DWORD *)(v3 + 32)
      && !*(_DWORD *)(v3 + 36) )
    {
      v4 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v2,
      (__int64)&unk_18002BA88,
      v3 + 8,
      v4,
      (__int64)&v6,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x18001f594  mov     [rsp+arg_10], rbx
0x18001f599  push    rdi
0x18001f59a  sub     rsp, 30h
0x18001f59e  mov     rbx, rcx
0x18001f5a1  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001f5a6  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f5ab  mov     rdi, rax
0x18001f5ae  mov     edx, [rax]
0x18001f5b0  cmp     edx, 5
0x18001f5b3  jbe     short loc_18001F618
0x18001f5b5  call    cs:__imp_GetCurrentThreadId
0x18001f5bb  mov     [rsp+38h+arg_0], eax
0x18001f5bf  xor     eax, eax
0x18001f5c1  mov     [rsp+38h+arg_8], rax
0x18001f5c6  mov     r8, [rbx+110h]
0x18001f5cd  cmp     [r8+4], al
0x18001f5d1  jz      short loc_18001F5EE
0x18001f5d3  lea     r9, [r8+18h]
0x18001f5d7  cmp     [r9], eax
0x18001f5da  jnz     short loc_18001F5F1
0x18001f5dc  cmp     [r9+4], eax
0x18001f5e0  jnz     short loc_18001F5F1
0x18001f5e2  cmp     [r9+8], eax
0x18001f5e6  jnz     short loc_18001F5F1
0x18001f5e8  cmp     [r9+0Ch], eax
0x18001f5ec  jnz     short loc_18001F5F1
0x18001f5ee  mov     r9, rax
0x18001f5f1  add     r8, 8
0x18001f5f5  lea     rax, [rsp+38h+arg_0]
0x18001f5fa  mov     [rsp+38h+var_10], rax
0x18001f5ff  lea     rax, [rsp+38h+arg_8]
0x18001f604  mov     [rsp+38h+var_18], rax
0x18001f609  lea     rdx, unk_18002BA88
0x18001f610  mov     rcx, rdi
0x18001f613  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001f618  mov     rcx, rbx
0x18001f61b  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001f620  nop
0x18001f621  mov     rbx, [rsp+38h+arg_10]
0x18001f626  add     rsp, 30h
0x18001f62a  pop     rdi
0x18001f62b  retn
```

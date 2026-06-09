# TraceProvider::ReplaceFileProxyActivity::StartActivity(void)

- ea: `0x18001f4f4`
- end: `0x18001f58c`
- name: `?StartActivity@ReplaceFileProxyActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::ReplaceFileProxyActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021920`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001f4f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f515`

## pseudocode

```c
void __fastcall TraceProvider::ReplaceFileProxyActivity::StartActivity(TraceProvider::ReplaceFileProxyActivity *this)
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
      (__int64)&word_18002BADE,
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
0x18001f4f4  mov     [rsp+arg_10], rbx
0x18001f4f9  push    rdi
0x18001f4fa  sub     rsp, 30h
0x18001f4fe  mov     rbx, rcx
0x18001f501  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001f506  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f50b  mov     rdi, rax
0x18001f50e  mov     edx, [rax]
0x18001f510  cmp     edx, 5
0x18001f513  jbe     short loc_18001F578
0x18001f515  call    cs:__imp_GetCurrentThreadId
0x18001f51b  mov     [rsp+38h+arg_0], eax
0x18001f51f  xor     eax, eax
0x18001f521  mov     [rsp+38h+arg_8], rax
0x18001f526  mov     r8, [rbx+110h]
0x18001f52d  cmp     [r8+4], al
0x18001f531  jz      short loc_18001F54E
0x18001f533  lea     r9, [r8+18h]
0x18001f537  cmp     [r9], eax
0x18001f53a  jnz     short loc_18001F551
0x18001f53c  cmp     [r9+4], eax
0x18001f540  jnz     short loc_18001F551
0x18001f542  cmp     [r9+8], eax
0x18001f546  jnz     short loc_18001F551
0x18001f548  cmp     [r9+0Ch], eax
0x18001f54c  jnz     short loc_18001F551
0x18001f54e  mov     r9, rax
0x18001f551  add     r8, 8
0x18001f555  lea     rax, [rsp+38h+arg_0]
0x18001f55a  mov     [rsp+38h+var_10], rax
0x18001f55f  lea     rax, [rsp+38h+arg_8]
0x18001f564  mov     [rsp+38h+var_18], rax
0x18001f569  lea     rdx, word_18002BADE
0x18001f570  mov     rcx, rdi
0x18001f573  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001f578  mov     rcx, rbx
0x18001f57b  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001f580  nop
0x18001f581  mov     rbx, [rsp+38h+arg_10]
0x18001f586  add     rsp, 30h
0x18001f58a  pop     rdi
0x18001f58b  retn
```

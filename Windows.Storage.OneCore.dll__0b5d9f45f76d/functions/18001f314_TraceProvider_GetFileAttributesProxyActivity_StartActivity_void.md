# TraceProvider::GetFileAttributesProxyActivity::StartActivity(void)

- ea: `0x18001f314`
- end: `0x18001f3ac`
- name: `?StartActivity@GetFileAttributesProxyActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesProxyActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021610`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001f314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f335`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesProxyActivity::StartActivity(
        TraceProvider::GetFileAttributesProxyActivity *this)
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
      (__int64)byte_18002BBD3,
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
0x18001f314  mov     [rsp+arg_10], rbx
0x18001f319  push    rdi
0x18001f31a  sub     rsp, 30h
0x18001f31e  mov     rbx, rcx
0x18001f321  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001f326  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f32b  mov     rdi, rax
0x18001f32e  mov     edx, [rax]
0x18001f330  cmp     edx, 5
0x18001f333  jbe     short loc_18001F398
0x18001f335  call    cs:__imp_GetCurrentThreadId
0x18001f33b  mov     [rsp+38h+arg_0], eax
0x18001f33f  xor     eax, eax
0x18001f341  mov     [rsp+38h+arg_8], rax
0x18001f346  mov     r8, [rbx+110h]
0x18001f34d  cmp     [r8+4], al
0x18001f351  jz      short loc_18001F36E
0x18001f353  lea     r9, [r8+18h]
0x18001f357  cmp     [r9], eax
0x18001f35a  jnz     short loc_18001F371
0x18001f35c  cmp     [r9+4], eax
0x18001f360  jnz     short loc_18001F371
0x18001f362  cmp     [r9+8], eax
0x18001f366  jnz     short loc_18001F371
0x18001f368  cmp     [r9+0Ch], eax
0x18001f36c  jnz     short loc_18001F371
0x18001f36e  mov     r9, rax
0x18001f371  add     r8, 8
0x18001f375  lea     rax, [rsp+38h+arg_0]
0x18001f37a  mov     [rsp+38h+var_10], rax
0x18001f37f  lea     rax, [rsp+38h+arg_8]
0x18001f384  mov     [rsp+38h+var_18], rax
0x18001f389  lea     rdx, byte_18002BBD3
0x18001f390  mov     rcx, rdi
0x18001f393  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001f398  mov     rcx, rbx
0x18001f39b  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001f3a0  nop
0x18001f3a1  mov     rbx, [rsp+38h+arg_10]
0x18001f3a6  add     rsp, 30h
0x18001f3aa  pop     rdi
0x18001f3ab  retn
```

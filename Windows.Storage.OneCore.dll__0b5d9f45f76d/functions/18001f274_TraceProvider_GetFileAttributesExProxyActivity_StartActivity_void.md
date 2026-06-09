# TraceProvider::GetFileAttributesExProxyActivity::StartActivity(void)

- ea: `0x18001f274`
- end: `0x18001f30c`
- name: `?StartActivity@GetFileAttributesExProxyActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesExProxyActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021500`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001f274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f295`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesExProxyActivity::StartActivity(
        TraceProvider::GetFileAttributesExProxyActivity *this)
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
      (__int64)byte_18002BB7B,
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
0x18001f274  mov     [rsp+arg_10], rbx
0x18001f279  push    rdi
0x18001f27a  sub     rsp, 30h
0x18001f27e  mov     rbx, rcx
0x18001f281  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001f286  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f28b  mov     rdi, rax
0x18001f28e  mov     edx, [rax]
0x18001f290  cmp     edx, 5
0x18001f293  jbe     short loc_18001F2F8
0x18001f295  call    cs:__imp_GetCurrentThreadId
0x18001f29b  mov     [rsp+38h+arg_0], eax
0x18001f29f  xor     eax, eax
0x18001f2a1  mov     [rsp+38h+arg_8], rax
0x18001f2a6  mov     r8, [rbx+110h]
0x18001f2ad  cmp     [r8+4], al
0x18001f2b1  jz      short loc_18001F2CE
0x18001f2b3  lea     r9, [r8+18h]
0x18001f2b7  cmp     [r9], eax
0x18001f2ba  jnz     short loc_18001F2D1
0x18001f2bc  cmp     [r9+4], eax
0x18001f2c0  jnz     short loc_18001F2D1
0x18001f2c2  cmp     [r9+8], eax
0x18001f2c6  jnz     short loc_18001F2D1
0x18001f2c8  cmp     [r9+0Ch], eax
0x18001f2cc  jnz     short loc_18001F2D1
0x18001f2ce  mov     r9, rax
0x18001f2d1  add     r8, 8
0x18001f2d5  lea     rax, [rsp+38h+arg_0]
0x18001f2da  mov     [rsp+38h+var_10], rax
0x18001f2df  lea     rax, [rsp+38h+arg_8]
0x18001f2e4  mov     [rsp+38h+var_18], rax
0x18001f2e9  lea     rdx, byte_18002BB7B
0x18001f2f0  mov     rcx, rdi
0x18001f2f3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001f2f8  mov     rcx, rbx
0x18001f2fb  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001f300  nop
0x18001f301  mov     rbx, [rsp+38h+arg_10]
0x18001f306  add     rsp, 30h
0x18001f30a  pop     rdi
0x18001f30b  retn
```

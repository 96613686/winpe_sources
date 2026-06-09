# TraceProvider::RemoveDirectoryProxyActivity::StartActivity(void)

- ea: `0x18001f454`
- end: `0x18001f4ec`
- name: `?StartActivity@RemoveDirectoryProxyActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::RemoveDirectoryProxyActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021820`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001f454`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f475`

## pseudocode

```c
void __fastcall TraceProvider::RemoveDirectoryProxyActivity::StartActivity(
        TraceProvider::RemoveDirectoryProxyActivity *this)
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
      (__int64)&unk_18002B9E0,
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
0x18001f454  mov     [rsp+arg_10], rbx
0x18001f459  push    rdi
0x18001f45a  sub     rsp, 30h
0x18001f45e  mov     rbx, rcx
0x18001f461  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001f466  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f46b  mov     rdi, rax
0x18001f46e  mov     edx, [rax]
0x18001f470  cmp     edx, 5
0x18001f473  jbe     short loc_18001F4D8
0x18001f475  call    cs:__imp_GetCurrentThreadId
0x18001f47b  mov     [rsp+38h+arg_0], eax
0x18001f47f  xor     eax, eax
0x18001f481  mov     [rsp+38h+arg_8], rax
0x18001f486  mov     r8, [rbx+110h]
0x18001f48d  cmp     [r8+4], al
0x18001f491  jz      short loc_18001F4AE
0x18001f493  lea     r9, [r8+18h]
0x18001f497  cmp     [r9], eax
0x18001f49a  jnz     short loc_18001F4B1
0x18001f49c  cmp     [r9+4], eax
0x18001f4a0  jnz     short loc_18001F4B1
0x18001f4a2  cmp     [r9+8], eax
0x18001f4a6  jnz     short loc_18001F4B1
0x18001f4a8  cmp     [r9+0Ch], eax
0x18001f4ac  jnz     short loc_18001F4B1
0x18001f4ae  mov     r9, rax
0x18001f4b1  add     r8, 8
0x18001f4b5  lea     rax, [rsp+38h+arg_0]
0x18001f4ba  mov     [rsp+38h+var_10], rax
0x18001f4bf  lea     rax, [rsp+38h+arg_8]
0x18001f4c4  mov     [rsp+38h+var_18], rax
0x18001f4c9  lea     rdx, unk_18002B9E0
0x18001f4d0  mov     rcx, rdi
0x18001f4d3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001f4d8  mov     rcx, rbx
0x18001f4db  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001f4e0  nop
0x18001f4e1  mov     rbx, [rsp+38h+arg_10]
0x18001f4e6  add     rsp, 30h
0x18001f4ea  pop     rdi
0x18001f4eb  retn
```

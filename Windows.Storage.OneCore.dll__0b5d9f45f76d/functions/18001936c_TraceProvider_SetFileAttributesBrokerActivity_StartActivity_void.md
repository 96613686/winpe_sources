# TraceProvider::SetFileAttributesBrokerActivity::StartActivity(void)

- ea: `0x18001936c`
- end: `0x180019404`
- name: `?StartActivity@SetFileAttributesBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::SetFileAttributesBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016ee0`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001936c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001938d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001938d`

## pseudocode

```c
void __fastcall TraceProvider::SetFileAttributesBrokerActivity::StartActivity(
        TraceProvider::SetFileAttributesBrokerActivity *this)
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
      (__int64)word_18002A44A,
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
0x18001936c  mov     [rsp+arg_10], rbx
0x180019371  push    rdi
0x180019372  sub     rsp, 30h
0x180019376  mov     rbx, rcx
0x180019379  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001937e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019383  mov     rdi, rax
0x180019386  mov     edx, [rax]
0x180019388  cmp     edx, 5
0x18001938b  jbe     short loc_1800193F0
0x18001938d  call    cs:__imp_GetCurrentThreadId
0x180019393  mov     [rsp+38h+arg_0], eax
0x180019397  xor     eax, eax
0x180019399  mov     [rsp+38h+arg_8], rax
0x18001939e  mov     r8, [rbx+110h]
0x1800193a5  cmp     [r8+4], al
0x1800193a9  jz      short loc_1800193C6
0x1800193ab  lea     r9, [r8+18h]
0x1800193af  cmp     [r9], eax
0x1800193b2  jnz     short loc_1800193C9
0x1800193b4  cmp     [r9+4], eax
0x1800193b8  jnz     short loc_1800193C9
0x1800193ba  cmp     [r9+8], eax
0x1800193be  jnz     short loc_1800193C9
0x1800193c0  cmp     [r9+0Ch], eax
0x1800193c4  jnz     short loc_1800193C9
0x1800193c6  mov     r9, rax
0x1800193c9  add     r8, 8
0x1800193cd  lea     rax, [rsp+38h+arg_0]
0x1800193d2  mov     [rsp+38h+var_10], rax
0x1800193d7  lea     rax, [rsp+38h+arg_8]
0x1800193dc  mov     [rsp+38h+var_18], rax
0x1800193e1  lea     rdx, word_18002A44A
0x1800193e8  mov     rcx, rdi
0x1800193eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800193f0  mov     rcx, rbx
0x1800193f3  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x1800193f8  nop
0x1800193f9  mov     rbx, [rsp+38h+arg_10]
0x1800193fe  add     rsp, 30h
0x180019402  pop     rdi
0x180019403  retn
```

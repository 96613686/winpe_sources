# TraceProvider::MoveFileBrokerActivity::StartActivity(void)

- ea: `0x18001918c`
- end: `0x180019224`
- name: `?StartActivity@MoveFileBrokerActivity@TraceProvider@@QEAAXXZ`
- size: `152`
- prototype: `void __fastcall(TraceProvider::MoveFileBrokerActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016ca0`

## callees

- `0x1800015e0`
- `0x18000dfcc`
- `0x18000e964`
- `0x180011570`
- `0x18001918c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800191ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800191ad`

## pseudocode

```c
void __fastcall TraceProvider::MoveFileBrokerActivity::StartActivity(TraceProvider::MoveFileBrokerActivity *this)
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
      (__int64)word_18002A4F2,
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
0x18001918c  mov     [rsp+arg_10], rbx
0x180019191  push    rdi
0x180019192  sub     rsp, 30h
0x180019196  mov     rbx, rcx
0x180019199  call    ?zInternalStart@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18001919e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x1800191a3  mov     rdi, rax
0x1800191a6  mov     edx, [rax]
0x1800191a8  cmp     edx, 5
0x1800191ab  jbe     short loc_180019210
0x1800191ad  call    cs:__imp_GetCurrentThreadId
0x1800191b3  mov     [rsp+38h+arg_0], eax
0x1800191b7  xor     eax, eax
0x1800191b9  mov     [rsp+38h+arg_8], rax
0x1800191be  mov     r8, [rbx+110h]
0x1800191c5  cmp     [r8+4], al
0x1800191c9  jz      short loc_1800191E6
0x1800191cb  lea     r9, [r8+18h]
0x1800191cf  cmp     [r9], eax
0x1800191d2  jnz     short loc_1800191E9
0x1800191d4  cmp     [r9+4], eax
0x1800191d8  jnz     short loc_1800191E9
0x1800191da  cmp     [r9+8], eax
0x1800191de  jnz     short loc_1800191E9
0x1800191e0  cmp     [r9+0Ch], eax
0x1800191e4  jnz     short loc_1800191E9
0x1800191e6  mov     r9, rax
0x1800191e9  add     r8, 8
0x1800191ed  lea     rax, [rsp+38h+arg_0]
0x1800191f2  mov     [rsp+38h+var_10], rax
0x1800191f7  lea     rax, [rsp+38h+arg_8]
0x1800191fc  mov     [rsp+38h+var_18], rax
0x180019201  lea     rdx, word_18002A4F2
0x180019208  mov     rcx, rdi
0x18001920b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180019210  mov     rcx, rbx
0x180019213  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180019218  nop
0x180019219  mov     rbx, [rsp+38h+arg_10]
0x18001921e  add     rsp, 30h
0x180019222  pop     rdi
0x180019223  retn
```

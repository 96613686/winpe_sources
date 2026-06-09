# SPTelemetry::ModelUpdate::StopEventLocal(long,unsigned __int64)

- ea: `0x140008b80`
- end: `0x140008c12`
- name: `?StopEventLocal@ModelUpdate@SPTelemetry@@UEAAXJ_K@Z`
- size: `146`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x140008b80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bbb`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StopEventLocal(SPTelemetry::ModelUpdate *this, int a2, __int64 a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r9
  int v11; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v12[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v13; // [rsp+98h] [rbp+20h] BYREF

  v6 = SPTraceLoggingClass::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    v8 = *((_QWORD *)v6 + 3);
    if ( (*(_QWORD *)(v7 + 16) & 1) != 0 && (v8 & 1) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = a2;
      v12[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&word_140029BEE,
        (__int64)this + 32,
        v10,
        (__int64)v12,
        (__int64)&v11,
        (__int64)&v13);
    }
  }
}

```

## disassembly

```asm
0x140008b80  push    rbx
0x140008b82  push    rbp
0x140008b83  push    rsi
0x140008b84  push    rdi
0x140008b85  sub     rsp, 58h
0x140008b89  mov     rsi, r8
0x140008b8c  mov     ebp, edx
0x140008b8e  mov     rdi, rcx
0x140008b91  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140008b96  mov     rbx, rax
0x140008b99  mov     r9d, [rax]
0x140008b9c  cmp     r9d, 4
0x140008ba0  jbe     short loc_140008C09
0x140008ba2  mov     rax, [rax+18h]
0x140008ba6  mov     r9, [rbx+10h]
0x140008baa  test    r9b, 1
0x140008bae  jz      short loc_140008C09
0x140008bb0  mov     rcx, rax
0x140008bb3  and     ecx, 1
0x140008bb6  cmp     rcx, rax
0x140008bb9  jnz     short loc_140008C09
0x140008bbb  call    cs:__imp_GetCurrentThreadId
0x140008bc1  mov     r9, [rdi+30h]
0x140008bc5  lea     r8, [rdi+20h]
0x140008bc9  mov     [rsp+78h+arg_18], eax
0x140008bd0  lea     rdx, word_140029BEE
0x140008bd7  lea     rax, [rsp+78h+arg_18]
0x140008bdf  mov     [rsp+78h+var_38], ebp
0x140008be3  mov     [rsp+78h+var_48], rax
0x140008be8  mov     rcx, rbx
0x140008beb  lea     rax, [rsp+78h+var_38]
0x140008bf0  mov     [rsp+78h+var_30], rsi
0x140008bf5  mov     [rsp+78h+var_50], rax
0x140008bfa  lea     rax, [rsp+78h+var_30]
0x140008bff  mov     [rsp+78h+var_58], rax
0x140008c04  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140008c09  add     rsp, 58h
0x140008c0d  pop     rdi
0x140008c0e  pop     rsi
0x140008c0f  pop     rbp
0x140008c10  pop     rbx
0x140008c11  retn
```

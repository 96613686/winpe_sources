# SPTelemetry::ModelUpdate::StopEvent(long,unsigned __int64)

- ea: `0x140008ad0`
- end: `0x140008b6b`
- name: `?StopEvent@ModelUpdate@SPTelemetry@@UEAAXJ_K@Z`
- size: `155`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140001360`
- `0x1400077b0`
- `0x140008ad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008b14`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::StopEvent(SPTelemetry::ModelUpdate *this, int a2, __int64 a3)
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
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 6);
      v13 = CurrentThreadId;
      v11 = a2;
      v12[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_140029D69,
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
0x140008ad0  push    rbx
0x140008ad2  push    rbp
0x140008ad3  push    rsi
0x140008ad4  push    rdi
0x140008ad5  sub     rsp, 58h
0x140008ad9  mov     rsi, r8
0x140008adc  mov     ebp, edx
0x140008ade  mov     rdi, rcx
0x140008ae1  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140008ae6  mov     rbx, rax
0x140008ae9  mov     r9d, [rax]
0x140008aec  cmp     r9d, 4
0x140008af0  jbe     short loc_140008B62
0x140008af2  mov     rax, [rax+18h]
0x140008af6  mov     rdx, 400000000000h
0x140008b00  mov     r9, [rbx+10h]
0x140008b04  test    rdx, r9
0x140008b07  jz      short loc_140008B62
0x140008b09  mov     rcx, rax
0x140008b0c  and     rcx, rdx
0x140008b0f  cmp     rcx, rax
0x140008b12  jnz     short loc_140008B62
0x140008b14  call    cs:__imp_GetCurrentThreadId
0x140008b1a  mov     r9, [rdi+30h]
0x140008b1e  lea     r8, [rdi+20h]
0x140008b22  mov     [rsp+78h+arg_18], eax
0x140008b29  lea     rdx, byte_140029D69
0x140008b30  lea     rax, [rsp+78h+arg_18]
0x140008b38  mov     [rsp+78h+var_38], ebp
0x140008b3c  mov     [rsp+78h+var_48], rax
0x140008b41  mov     rcx, rbx
0x140008b44  lea     rax, [rsp+78h+var_38]
0x140008b49  mov     [rsp+78h+var_30], rsi
0x140008b4e  mov     [rsp+78h+var_50], rax
0x140008b53  lea     rax, [rsp+78h+var_30]
0x140008b58  mov     [rsp+78h+var_58], rax
0x140008b5d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140008b62  add     rsp, 58h
0x140008b66  pop     rdi
0x140008b67  pop     rsi
0x140008b68  pop     rbp
0x140008b69  pop     rbx
0x140008b6a  retn
```

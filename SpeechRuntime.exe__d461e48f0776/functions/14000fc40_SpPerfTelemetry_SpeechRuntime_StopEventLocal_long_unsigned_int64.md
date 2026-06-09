# SpPerfTelemetry::SpeechRuntime::StopEventLocal(long,unsigned __int64)

- ea: `0x14000fc40`
- end: `0x14000fcca`
- name: `?StopEventLocal@SpeechRuntime@SpPerfTelemetry@@UEAAXJ_K@Z`
- size: `138`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this, int, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001b28`
- `0x140001ffc`
- `0x14000d3ec`
- `0x14000fc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fc73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fc73`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::StopEventLocal(
        SpPerfTelemetry::SpeechRuntime *this,
        int a2,
        __int64 a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r9
  int v10; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v11[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v12; // [rsp+98h] [rbp+20h] BYREF

  v6 = SpPerfLogging::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v6, 1) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 6);
      v12 = CurrentThreadId;
      v10 = a2;
      v11[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&word_140042D6E,
        (_DWORD)this + 32,
        v9,
        (__int64)v11,
        (__int64)&v10,
        (__int64)&v12);
    }
  }
}

```

## disassembly

```asm
0x14000fc40  push    rbx
0x14000fc42  push    rbp
0x14000fc43  push    rsi
0x14000fc44  push    rdi
0x14000fc45  sub     rsp, 58h
0x14000fc49  mov     rsi, r8
0x14000fc4c  mov     ebp, edx
0x14000fc4e  mov     rdi, rcx
0x14000fc51  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x14000fc56  mov     rbx, rax
0x14000fc59  mov     r9d, [rax]
0x14000fc5c  cmp     r9d, 4
0x14000fc60  jbe     short loc_14000FCC1
0x14000fc62  mov     edx, 1
0x14000fc67  mov     rcx, rax
0x14000fc6a  call    _tlgKeywordOn
0x14000fc6f  test    al, al
0x14000fc71  jz      short loc_14000FCC1
0x14000fc73  call    cs:__imp_GetCurrentThreadId
0x14000fc79  mov     r9, [rdi+30h]
0x14000fc7d  lea     r8, [rdi+20h]
0x14000fc81  mov     [rsp+78h+arg_18], eax
0x14000fc88  lea     rdx, word_140042D6E
0x14000fc8f  lea     rax, [rsp+78h+arg_18]
0x14000fc97  mov     [rsp+78h+var_38], ebp
0x14000fc9b  mov     [rsp+78h+var_48], rax
0x14000fca0  mov     rcx, rbx
0x14000fca3  lea     rax, [rsp+78h+var_38]
0x14000fca8  mov     [rsp+78h+var_30], rsi
0x14000fcad  mov     [rsp+78h+var_50], rax
0x14000fcb2  lea     rax, [rsp+78h+var_30]
0x14000fcb7  mov     [rsp+78h+var_58], rax
0x14000fcbc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000fcc1  add     rsp, 58h
0x14000fcc5  pop     rdi
0x14000fcc6  pop     rsi
0x14000fcc7  pop     rbp
0x14000fcc8  pop     rbx
0x14000fcc9  retn
```

# SpPerfTelemetry::SpeechRuntime::StopEvent(long,unsigned __int64)

- ea: `0x14000fba0`
- end: `0x14000fc2f`
- name: `?StopEvent@SpeechRuntime@SpPerfTelemetry@@UEAAXJ_K@Z`
- size: `143`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this, int, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001b28`
- `0x140001ffc`
- `0x14000d3ec`
- `0x14000fba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fbd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fbd8`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::StopEvent(SpPerfTelemetry::SpeechRuntime *this, int a2, __int64 a3)
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
    if ( (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 6);
      v12 = CurrentThreadId;
      v10 = a2;
      v11[0] = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&byte_140043117,
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
0x14000fba0  push    rbx
0x14000fba2  push    rbp
0x14000fba3  push    rsi
0x14000fba4  push    rdi
0x14000fba5  sub     rsp, 58h
0x14000fba9  mov     rsi, r8
0x14000fbac  mov     ebp, edx
0x14000fbae  mov     rdi, rcx
0x14000fbb1  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x14000fbb6  mov     rbx, rax
0x14000fbb9  mov     r9d, [rax]
0x14000fbbc  cmp     r9d, 4
0x14000fbc0  jbe     short loc_14000FC26
0x14000fbc2  mov     rdx, 400000000000h
0x14000fbcc  mov     rcx, rax
0x14000fbcf  call    _tlgKeywordOn
0x14000fbd4  test    al, al
0x14000fbd6  jz      short loc_14000FC26
0x14000fbd8  call    cs:__imp_GetCurrentThreadId
0x14000fbde  mov     r9, [rdi+30h]
0x14000fbe2  lea     r8, [rdi+20h]
0x14000fbe6  mov     [rsp+78h+arg_18], eax
0x14000fbed  lea     rdx, byte_140043117
0x14000fbf4  lea     rax, [rsp+78h+arg_18]
0x14000fbfc  mov     [rsp+78h+var_38], ebp
0x14000fc00  mov     [rsp+78h+var_48], rax
0x14000fc05  mov     rcx, rbx
0x14000fc08  lea     rax, [rsp+78h+var_38]
0x14000fc0d  mov     [rsp+78h+var_30], rsi
0x14000fc12  mov     [rsp+78h+var_50], rax
0x14000fc17  lea     rax, [rsp+78h+var_30]
0x14000fc1c  mov     [rsp+78h+var_58], rax
0x14000fc21  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000fc26  add     rsp, 58h
0x14000fc2a  pop     rdi
0x14000fc2b  pop     rsi
0x14000fc2c  pop     rbp
0x14000fc2d  pop     rbx
0x14000fc2e  retn
```

# SpPerfTelemetry::SpeechRuntime::StartEvent(unsigned __int64,bool)

- ea: `0x14000f2e0`
- end: `0x14000f371`
- name: `?StartEvent@SpeechRuntime@SpPerfTelemetry@@UEAAX_K_N@Z`
- size: `145`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this, unsigned __int64, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001b28`
- `0x140001ffc`
- `0x14000d3ec`
- `0x14000f2e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f31a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f31a`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::StartEvent(
        SpPerfTelemetry::SpeechRuntime *this,
        __int64 a2,
        unsigned __int8 a3)
{
  int v3; // esi
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r9
  int v10; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v11[6]; // [rsp+48h] [rbp-30h] BYREF
  DWORD v12; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  v6 = SpPerfLogging::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 4u )
  {
    if ( (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 6);
      v12 = CurrentThreadId;
      v10 = v3;
      v11[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_1400428ED,
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
0x14000f2e0  push    rbx
0x14000f2e2  push    rbp
0x14000f2e3  push    rsi
0x14000f2e4  push    rdi
0x14000f2e5  sub     rsp, 58h
0x14000f2e9  movzx   esi, r8b
0x14000f2ed  mov     rbp, rdx
0x14000f2f0  mov     rdi, rcx
0x14000f2f3  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x14000f2f8  mov     rbx, rax
0x14000f2fb  mov     r9d, [rax]
0x14000f2fe  cmp     r9d, 4
0x14000f302  jbe     short loc_14000F368
0x14000f304  mov     rdx, 400000000000h
0x14000f30e  mov     rcx, rax
0x14000f311  call    _tlgKeywordOn
0x14000f316  test    al, al
0x14000f318  jz      short loc_14000F368
0x14000f31a  call    cs:__imp_GetCurrentThreadId
0x14000f320  mov     r9, [rdi+30h]
0x14000f324  lea     r8, [rdi+20h]
0x14000f328  mov     [rsp+78h+arg_18], eax
0x14000f32f  lea     rdx, byte_1400428ED
0x14000f336  lea     rax, [rsp+78h+arg_18]
0x14000f33e  mov     [rsp+78h+var_38], esi
0x14000f342  mov     [rsp+78h+var_48], rax
0x14000f347  mov     rcx, rbx
0x14000f34a  lea     rax, [rsp+78h+var_38]
0x14000f34f  mov     [rsp+78h+var_30], rbp
0x14000f354  mov     [rsp+78h+var_50], rax
0x14000f359  lea     rax, [rsp+78h+var_30]
0x14000f35e  mov     [rsp+78h+var_58], rax
0x14000f363  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000f368  add     rsp, 58h
0x14000f36c  pop     rdi
0x14000f36d  pop     rsi
0x14000f36e  pop     rbp
0x14000f36f  pop     rbx
0x14000f370  retn
```

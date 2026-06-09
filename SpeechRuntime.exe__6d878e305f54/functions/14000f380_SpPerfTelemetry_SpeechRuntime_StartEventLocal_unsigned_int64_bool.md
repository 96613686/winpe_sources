# SpPerfTelemetry::SpeechRuntime::StartEventLocal(unsigned __int64,bool)

- ea: `0x14000f380`
- end: `0x14000f40c`
- name: `?StartEventLocal@SpeechRuntime@SpPerfTelemetry@@UEAAX_K_N@Z`
- size: `140`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime *__hidden this, unsigned __int64, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001b28`
- `0x140001ffc`
- `0x14000d3ec`
- `0x14000f380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f3b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000f3b5`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::StartEventLocal(
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
    if ( (unsigned __int8)tlgKeywordOn(v6, 1) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 6);
      v12 = CurrentThreadId;
      v10 = v3;
      v11[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)word_14004381A,
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
0x14000f380  push    rbx
0x14000f382  push    rbp
0x14000f383  push    rsi
0x14000f384  push    rdi
0x14000f385  sub     rsp, 58h
0x14000f389  movzx   esi, r8b
0x14000f38d  mov     rbp, rdx
0x14000f390  mov     rdi, rcx
0x14000f393  call    ?Provider@SpPerfLogging@@SAPEBU_tlgProvider_t@@XZ; SpPerfLogging::Provider(void)
0x14000f398  mov     rbx, rax
0x14000f39b  mov     r9d, [rax]
0x14000f39e  cmp     r9d, 4
0x14000f3a2  jbe     short loc_14000F403
0x14000f3a4  mov     edx, 1
0x14000f3a9  mov     rcx, rax
0x14000f3ac  call    _tlgKeywordOn
0x14000f3b1  test    al, al
0x14000f3b3  jz      short loc_14000F403
0x14000f3b5  call    cs:__imp_GetCurrentThreadId
0x14000f3bb  mov     r9, [rdi+30h]
0x14000f3bf  lea     r8, [rdi+20h]
0x14000f3c3  mov     [rsp+78h+arg_18], eax
0x14000f3ca  lea     rdx, word_14004381A
0x14000f3d1  lea     rax, [rsp+78h+arg_18]
0x14000f3d9  mov     [rsp+78h+var_38], esi
0x14000f3dd  mov     [rsp+78h+var_48], rax
0x14000f3e2  mov     rcx, rbx
0x14000f3e5  lea     rax, [rsp+78h+var_38]
0x14000f3ea  mov     [rsp+78h+var_30], rbp
0x14000f3ef  mov     [rsp+78h+var_50], rax
0x14000f3f4  lea     rax, [rsp+78h+var_30]
0x14000f3f9  mov     [rsp+78h+var_58], rax
0x14000f3fe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000f403  add     rsp, 58h
0x14000f407  pop     rdi
0x14000f408  pop     rsi
0x14000f409  pop     rbp
0x14000f40a  pop     rbx
0x14000f40b  retn
```

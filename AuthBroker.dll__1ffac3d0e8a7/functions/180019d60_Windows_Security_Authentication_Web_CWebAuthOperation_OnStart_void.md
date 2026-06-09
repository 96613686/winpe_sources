# Windows::Security::Authentication::Web::CWebAuthOperation::OnStart(void)

- ea: `0x180019d60`
- end: `0x180019e00`
- name: `?OnStart@CWebAuthOperation@Web@Authentication@Security@Windows@@UEAAJXZ`
- size: `160`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019d60`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019dd9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019da0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180019d92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180019d92`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019dc9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019dc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180019de8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180019de8`

## pseudocode

```c
__int64 __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::OnStart(
        Windows::Security::Authentication::Web::CWebAuthOperation *this)
{
  wil::CallContextInfo **p_m_pCallContext; // rdi
  _TP_WORK *ThreadpoolWork; // rax
  _TP_WORK *v4; // rsi
  signed int LastError; // eax
  unsigned int refCount; // ebx

  p_m_pCallContext = &this[-1].m_WamBridgeBrokerActivity.m_callbackHolder.m_pCallContext;
  ((void (__fastcall *)(wil::CallContextInfo **))this[-1].m_WamBridgeBrokerActivity.m_callbackHolder.m_pCallContext->contextName)(&this[-1].m_WamBridgeBrokerActivity.m_callbackHolder.m_pCallContext);
  ThreadpoolWork = CreateThreadpoolWork(
                     Windows::Security::Authentication::Web::CWebAuthOperation::WebAuthenticationWorker,
                     p_m_pCallContext,
                     0);
  v4 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    WaitForSingleObject(*(HANDLE *)&this->gapA0, 0xFFFFFFFF);
    refCount = this->refCount_.refCount;
    CloseThreadpoolWork(v4);
  }
  else
  {
    LastError = GetLastError();
    refCount = LastError;
    if ( LastError > 0 )
      refCount = (unsigned __int16)LastError | 0x80070000;
    ((void (__fastcall *)(wil::CallContextInfo **))(*p_m_pCallContext)->contextMessage)(p_m_pCallContext);
  }
  return refCount;
}

```

## disassembly

```asm
0x180019d60  mov     [rsp+arg_0], rbx
0x180019d65  mov     [rsp+arg_8], rsi
0x180019d6a  push    rdi
0x180019d6b  sub     rsp, 20h
0x180019d6f  lea     rdi, [this-10h]
0x180019d73  mov     rbx, this
0x180019d76  mov     rax, [rdi]
0x180019d79  mov     this, rdi
0x180019d7c  mov     rax, [rax+8]
0x180019d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d85  xor     r8d, r8d; pcbe
0x180019d88  lea     this, ?WebAuthenticationWorker@CWebAuthOperation@Web@Authentication@Security@Windows@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180019d8f  mov     rdx, rdi; pv
0x180019d92  call    cs:__imp_CreateThreadpoolWork
0x180019d98  mov     rsi, rax
0x180019d9b  test    rax, rax
0x180019d9e  jnz     short loc_180019DC6
0x180019da0  call    cs:__imp_GetLastError
0x180019da6  mov     ebx, eax
0x180019da8  test    eax, eax
0x180019daa  jle     short loc_180019DB5
0x180019dac  movzx   ebx, ax
0x180019daf  or      ebx, 80070000h
0x180019db5  mov     rax, [rdi]
0x180019db8  mov     this, rdi
0x180019dbb  mov     rax, [rax+10h]
0x180019dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc4  jmp     short loc_180019DEE
0x180019dc6  mov     this, rsi; pwk
0x180019dc9  call    cs:__imp_SubmitThreadpoolWork
0x180019dcf  mov     this, [rbx+0A0h]; hHandle
0x180019dd6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019dd9  call    cs:__imp_WaitForSingleObject
0x180019ddf  mov     ebx, [rbx+0A8h]
0x180019de5  mov     this, rsi; pwk
0x180019de8  call    cs:__imp_CloseThreadpoolWork
0x180019dee  mov     rsi, [rsp+28h+arg_8]
0x180019df3  mov     eax, ebx
0x180019df5  mov     rbx, [rsp+28h+arg_0]
0x180019dfa  add     rsp, 20h
0x180019dfe  pop     rdi
0x180019dff  retn
```

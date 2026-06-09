# wil::details::static_lazy<WebAuthBridgeLogging>::Completer::~Completer(void)

- ea: `0x180017228`
- end: `0x180017282`
- name: `??1Completer@?$static_lazy@VWebAuthBridgeLogging@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `void __fastcall(wil::details::static_lazy<WebAuthBridgeLogging>::Completer *this, void (__fastcall *)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ba58`

## callees

- `0x180003dd0`
- `0x180017228`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001727b`

## pseudocode

```c
void __fastcall wil::details::static_lazy<WebAuthBridgeLogging>::Completer::~Completer(
        wil::details::static_lazy<WebAuthBridgeLogging>::Completer *this,
        void (__fastcall *a2)(const _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, _EVENT_FILTER_DESCRIPTOR *, void *),
        void *a3)
{
  wil::details::static_lazy<WebAuthBridgeLogging> *m_pSelf; // rbx
  const _tlgProvider_t *v5; // rcx
  __int64 v6; // rax

  if ( !this->m_flags )
  {
    m_pSelf = this->m_pSelf;
    v5 = *(const _tlgProvider_t **)&this->m_pSelf->m_storage[24];
    *(_QWORD *)&m_pSelf->m_storage[8] = v5;
    m_pSelf->m_storage[16] = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v5, a2, a3);
    v6 = *(_QWORD *)m_pSelf->m_storage;
    *(_DWORD *)&m_pSelf->m_storage[20] = 1;
    (*(void (__fastcall **)(unsigned __int8 *))(v6 + 8))(m_pSelf->m_storage);
  }
  InitOnceComplete(&this->m_pSelf->m_initOnce, this->m_flags, this->m_pSelf->m_storage);
}

```

## disassembly

```asm
0x180017228  mov     [rsp+arg_0], rbx
0x18001722d  push    rdi
0x18001722e  sub     rsp, 20h
0x180017232  cmp     dword ptr [this+8], 0
0x180017236  mov     rdi, this
0x180017239  jnz     short loc_180017267
0x18001723b  mov     rbx, [this]
0x18001723e  mov     this, [rbx+20h]; hProvider
0x180017242  mov     [rbx+10h], this
0x180017246  mov     byte ptr [rbx+18h], 1
0x18001724a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001724f  mov     rax, [rbx+8]
0x180017253  lea     this, [rbx+8]
0x180017257  mov     dword ptr [rbx+1Ch], 1
0x18001725e  mov     rax, [rax+8]
0x180017262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017267  mov     this, [rdi]
0x18001726a  mov     edx, [rdi+8]
0x18001726d  lea     r8, [this+8]
0x180017271  mov     rbx, [rsp+28h+arg_0]
0x180017276  add     rsp, 20h
0x18001727a  pop     rdi
0x18001727b  jmp     cs:__imp_InitOnceComplete
```

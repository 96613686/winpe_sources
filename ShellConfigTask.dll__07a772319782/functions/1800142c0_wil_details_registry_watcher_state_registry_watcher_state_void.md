# wil::details::registry_watcher_state::~registry_watcher_state(void)

- ea: `0x1800142c0`
- end: `0x18001435a`
- name: `??1registry_watcher_state@details@wil@@QEAA@XZ`
- size: `154`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001dd2c`
- `0x180021a48`
- `0x180021cb8`

## callees

- `0x18000c5d4`
- `0x1800142c0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001430a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001430a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800142ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800142ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800142f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800142f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800142e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800142e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001431d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001431d`

## string_xrefs

- `0x180014348`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::~registry_watcher_state(
        wil::details::registry_watcher_state *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  const char *v4; // r9
  HKEY v5; // rcx
  __int64 v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
  if ( v1 )
  {
    SetThreadpoolWait(*((PTP_WAIT *)this + 17), 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
  v3 = (void *)*((_QWORD *)this + 16);
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v5 = (HKEY)*((_QWORD *)this + 15);
  if ( v5 )
    RegCloseKey(v5);
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
}

```

## disassembly

```asm
0x1800142c0  mov     [rsp+arg_0], rbx
0x1800142c5  push    rdi
0x1800142c6  sub     rsp, 20h
0x1800142ca  mov     rdi, [rcx+88h]
0x1800142d1  mov     rbx, rcx
0x1800142d4  test    rdi, rdi
0x1800142d7  jz      short loc_1800142FE
0x1800142d9  xor     r8d, r8d; pftTimeout
0x1800142dc  xor     edx, edx; h
0x1800142de  mov     rcx, rdi; pwa
0x1800142e1  call    cs:__imp_SetThreadpoolWait
0x1800142e7  mov     edx, 1; fCancelPendingCallbacks
0x1800142ec  mov     rcx, rdi; pwa
0x1800142ef  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800142f5  mov     rcx, rdi; pwa
0x1800142f8  call    cs:__imp_CloseThreadpoolWait
0x1800142fe  mov     rcx, [rbx+80h]; hObject
0x180014305  test    rcx, rcx
0x180014308  jz      short loc_180014314
0x18001430a  call    cs:__imp_CloseHandle
0x180014310  test    eax, eax
0x180014312  jz      short loc_180014343
0x180014314  mov     rcx, [rbx+78h]; hKey
0x180014318  test    rcx, rcx
0x18001431b  jz      short loc_180014323
0x18001431d  call    cs:__imp_RegCloseKey
0x180014323  mov     rcx, [rbx+70h]
0x180014327  test    rcx, rcx
0x18001432a  jz      short loc_180014338
0x18001432c  mov     rax, [rcx]
0x18001432f  mov     rax, [rax+18h]
0x180014333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014338  mov     rbx, [rsp+28h+arg_0]
0x18001433d  add     rsp, 20h
0x180014341  pop     rdi
0x180014342  retn
0x180014343  mov     rcx, [rsp+28h]; this
0x180014348  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001434f  mov     edx, 0A0Bh; void *
0x180014354  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

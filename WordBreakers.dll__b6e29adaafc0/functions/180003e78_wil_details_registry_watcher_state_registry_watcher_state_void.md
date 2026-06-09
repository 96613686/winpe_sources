# wil::details::registry_watcher_state::~registry_watcher_state(void)

- ea: `0x180003e78`
- end: `0x180003f0b`
- name: `??1registry_watcher_state@details@wil@@QEAA@XZ`
- size: `147`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006e24`

## callees

- `0x180003e78`
- `0x1800066ac`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ed5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ed5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003ea7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003ea7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003eb0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003eb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003e99`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180003e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ec2`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::~registry_watcher_state(
        wil::details::registry_watcher_state *this)
{
  struct _TP_WAIT *v1; // rdi
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  HKEY v6; // rcx
  __int64 v7; // rcx
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
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (HKEY)*((_QWORD *)this + 15);
  if ( v6 )
    RegCloseKey(v6);
  v7 = *((_QWORD *)this + 14);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
}

```

## disassembly

```asm
0x180003e78  mov     [rsp+arg_0], rbx
0x180003e7d  push    rdi
0x180003e7e  sub     rsp, 20h
0x180003e82  mov     rdi, [rcx+88h]
0x180003e89  mov     rbx, rcx
0x180003e8c  test    rdi, rdi
0x180003e8f  jz      short loc_180003EB6
0x180003e91  xor     r8d, r8d; pftTimeout
0x180003e94  xor     edx, edx; h
0x180003e96  mov     rcx, rdi; pwa
0x180003e99  call    cs:__imp_SetThreadpoolWait
0x180003e9f  mov     edx, 1; fCancelPendingCallbacks
0x180003ea4  mov     rcx, rdi; pwa
0x180003ea7  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180003ead  mov     rcx, rdi; pwa
0x180003eb0  call    cs:__imp_CloseThreadpoolWait
0x180003eb6  mov     rcx, [rbx+80h]; hObject
0x180003ebd  test    rcx, rcx
0x180003ec0  jz      short loc_180003ECC
0x180003ec2  call    cs:__imp_CloseHandle
0x180003ec8  test    eax, eax
0x180003eca  jz      short loc_180003EFB
0x180003ecc  mov     rcx, [rbx+78h]; hKey
0x180003ed0  test    rcx, rcx
0x180003ed3  jz      short loc_180003EDB
0x180003ed5  call    cs:__imp_RegCloseKey
0x180003edb  mov     rcx, [rbx+70h]
0x180003edf  test    rcx, rcx
0x180003ee2  jz      short loc_180003EF0
0x180003ee4  mov     rax, [rcx]
0x180003ee7  mov     rax, [rax+18h]
0x180003eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ef0  mov     rbx, [rsp+28h+arg_0]
0x180003ef5  add     rsp, 20h
0x180003ef9  pop     rdi
0x180003efa  retn
0x180003efb  mov     rcx, [rsp+28h]; this
0x180003f00  mov     edx, 0A0Bh; void *
0x180003f05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

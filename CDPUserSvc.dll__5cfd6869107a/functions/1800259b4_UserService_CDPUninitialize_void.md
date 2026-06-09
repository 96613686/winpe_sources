# UserService::CDPUninitialize(void)

- ea: `0x1800259b4`
- end: `0x180025a0b`
- name: `?CDPUninitialize@UserService@@AEAAJXZ`
- size: `87`
- prototype: `__int64 __fastcall(UserService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000d124`

## callees

- `0x180006494`
- `0x1800097d0`
- `0x1800259b4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800259f2`
- `msvcp_win!_Mtx_unlock` at `0x1800259f2`
- `cdp!CDPShutdown` at `0x1800259fe`
- `cdp!CDPShutdown` at `0x1800259fe`
- `cdp!CDPUninitializeUserService` at `0x1800259f8`
- `cdp!CDPUninitializeUserService` at `0x1800259f8`

## pseudocode

```c
__int64 __fastcall UserService::CDPUninitialize(UserService *this)
{
  std::_Ref_count_base *v1; // rcx

  std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
  v1 = qword_1800A3E88;
  g_logger = 0;
  qword_1800A3E88 = 0;
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
  _Mtx_unlock((_Mtx_t)&g_loggerMutex);
  CDPUninitializeUserService();
  CDPShutdown();
  return 0;
}

```

## disassembly

```asm
0x1800259b4  sub     rsp, 28h
0x1800259b8  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; this
0x1800259bf  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800259c4  mov     rcx, cs:qword_1800A3E88; this
0x1800259cb  mov     cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A, 0; std::shared_ptr<ICDPLogger> g_logger
0x1800259d6  mov     cs:qword_1800A3E88, 0
0x1800259e1  test    rcx, rcx
0x1800259e4  jz      short loc_1800259EB
0x1800259e6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800259eb  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; _Mtx_t
0x1800259f2  call    cs:__imp__Mtx_unlock
0x1800259f8  call    cs:__imp_CDPUninitializeUserService
0x1800259fe  call    cs:__imp_CDPShutdown
0x180025a04  xor     eax, eax
0x180025a06  add     rsp, 28h
0x180025a0a  retn
```

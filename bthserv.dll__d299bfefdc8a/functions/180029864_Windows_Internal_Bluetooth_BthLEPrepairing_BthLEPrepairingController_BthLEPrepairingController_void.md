# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::~BthLEPrepairingController(void)

- ea: `0x180029864`
- end: `0x180029918`
- name: `??1BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@UEAA@XZ`
- size: `180`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180029e60`

## callees

- `0x180001b60`
- `0x180029864`
- `0x180029920`
- `0x18002aa5c`
- `0x18002ae90`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029889`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029889`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800298fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800298fe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180029907`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180029907`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::~BthLEPrepairingController(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  void *v2; // rbx
  volatile signed __int32 *v3; // rbx
  struct _TP_WORK *v4; // rbx

  *(_QWORD *)this = &Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::`vftable';
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(this);
  McGenEventUnregister_EventUnregister();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(*((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor **)this + 5));
    operator delete(v2, (const struct std::nothrow_t *)0x48);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (struct _TP_WORK *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 2), 1);
    CloseThreadpoolWork(v4);
  }
}

```

## disassembly

```asm
0x180029864  mov     [rsp+arg_0], rbx
0x180029869  push    rdi
0x18002986a  sub     rsp, 20h
0x18002986e  lea     rax, ??_7BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@6B@; const Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::`vftable'
0x180029875  mov     rdi, rcx
0x180029878  mov     [rcx], rax
0x18002987b  call    ?Stop@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(void)
0x180029880  call    McGenEventUnregister_EventUnregister
0x180029885  lea     rcx, [rdi+30h]; lpCriticalSection
0x180029889  call    cs:__imp_DeleteCriticalSection
0x18002988f  mov     rbx, [rdi+28h]
0x180029893  test    rbx, rbx
0x180029896  jz      short loc_1800298AD
0x180029898  mov     rcx, rbx; this
0x18002989b  call    ??1BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(void)
0x1800298a0  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x1800298a5  mov     rcx, rbx; void *
0x1800298a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800298ad  mov     rbx, [rdi+20h]
0x1800298b1  test    rbx, rbx
0x1800298b4  jz      short loc_1800298ED
0x1800298b6  or      eax, 0FFFFFFFFh
0x1800298b9  lock xadd [rbx+8], eax
0x1800298be  cmp     eax, 1
0x1800298c1  jnz     short loc_1800298ED
0x1800298c3  mov     rax, [rbx]
0x1800298c6  mov     rcx, rbx
0x1800298c9  mov     rax, [rax]
0x1800298cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298d1  or      eax, 0FFFFFFFFh
0x1800298d4  lock xadd [rbx+0Ch], eax
0x1800298d9  cmp     eax, 1
0x1800298dc  jnz     short loc_1800298ED
0x1800298de  mov     rax, [rbx]
0x1800298e1  mov     rcx, rbx
0x1800298e4  mov     rax, [rax+8]
0x1800298e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298ed  mov     rbx, [rdi+10h]
0x1800298f1  test    rbx, rbx
0x1800298f4  jz      short loc_18002990D
0x1800298f6  mov     edx, 1; fCancelPendingCallbacks
0x1800298fb  mov     rcx, rbx; pwk
0x1800298fe  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180029904  mov     rcx, rbx; pwk
0x180029907  call    cs:__imp_CloseThreadpoolWork
0x18002990d  mov     rbx, [rsp+28h+arg_0]
0x180029912  add     rsp, 20h
0x180029916  pop     rdi
0x180029917  retn
```

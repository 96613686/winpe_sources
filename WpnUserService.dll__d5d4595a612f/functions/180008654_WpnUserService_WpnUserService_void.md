# WpnUserService::~WpnUserService(void)

- ea: `0x180008654`
- end: `0x180008720`
- name: `??1WpnUserService@@UEAA@XZ`
- size: `204`
- prototype: `void __fastcall(WpnUserService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008930`

## callees

- `0x180008654`
- `0x18000ddf8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180008675`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180008675`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000867e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000867e`

## pseudocode

```c
void __fastcall WpnUserService::~WpnUserService(WpnUserService *this)
{
  struct _TP_WORK *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 29);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 29), 1);
    CloseThreadpoolWork(v2);
  }
  v3 = *((_QWORD *)this + 28);
  if ( v3 )
  {
    *((_QWORD *)this + 28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 27);
  if ( v4 )
  {
    *((_QWORD *)this + 27) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 26);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = *((_QWORD *)this + 24);
  if ( v6 )
  {
    *((_QWORD *)this + 24) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  ServiceBase::~ServiceBase(this);
}

```

## disassembly

```asm
0x180008654  mov     [rsp+arg_0], rbx
0x180008659  push    rdi
0x18000865a  sub     rsp, 20h
0x18000865e  mov     rbx, rcx
0x180008661  mov     rdi, [rcx+0E8h]
0x180008668  test    rdi, rdi
0x18000866b  jz      short loc_180008685
0x18000866d  mov     edx, 1; fCancelPendingCallbacks
0x180008672  mov     rcx, rdi; pwk
0x180008675  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000867b  mov     rcx, rdi; pwk
0x18000867e  call    cs:__imp_CloseThreadpoolWork
0x180008684  nop
0x180008685  mov     rcx, [rbx+0E0h]
0x18000868c  test    rcx, rcx
0x18000868f  jz      short loc_1800086A9
0x180008691  mov     qword ptr [rbx+0E0h], 0
0x18000869c  mov     rax, [rcx]
0x18000869f  mov     rax, [rax+10h]
0x1800086a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a8  nop
0x1800086a9  mov     rcx, [rbx+0D8h]
0x1800086b0  test    rcx, rcx
0x1800086b3  jz      short loc_1800086CD
0x1800086b5  mov     qword ptr [rbx+0D8h], 0
0x1800086c0  mov     rax, [rcx]
0x1800086c3  mov     rax, [rax+10h]
0x1800086c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086cc  nop
0x1800086cd  mov     rcx, [rbx+0D0h]
0x1800086d4  test    rcx, rcx
0x1800086d7  jz      short loc_1800086EA
0x1800086d9  mov     rax, [rcx]
0x1800086dc  mov     edx, 1
0x1800086e1  mov     rax, [rax]
0x1800086e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e9  nop
0x1800086ea  mov     rcx, [rbx+0C0h]
0x1800086f1  test    rcx, rcx
0x1800086f4  jz      short loc_18000870E
0x1800086f6  mov     qword ptr [rbx+0C0h], 0
0x180008701  mov     rax, [rcx]
0x180008704  mov     rax, [rax+10h]
0x180008708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870d  nop
0x18000870e  mov     rcx, rbx; this
0x180008711  mov     rbx, [rsp+28h+arg_0]
0x180008716  add     rsp, 20h
0x18000871a  pop     rdi
0x18000871b  jmp     ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
```

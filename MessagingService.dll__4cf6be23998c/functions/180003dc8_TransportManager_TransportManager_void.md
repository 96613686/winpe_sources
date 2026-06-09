# TransportManager::~TransportManager(void)

- ea: `0x180003dc8`
- end: `0x180003e95`
- name: `??1TransportManager@@MEAA@XZ`
- size: `205`
- prototype: `void __fastcall(TransportManager *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180003f20`
- `0x1800040d0`

## callees

- `0x18000266c`
- `0x180003dc8`
- `0x18000c010`

## pseudocode

```c
void __fastcall TransportManager::~TransportManager(TransportManager *this)
{
  __int64 v2; // rcx
  __int64 **v3; // rsi
  __int64 *v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  *(_QWORD *)this = &TransportManager::`vftable'{for `ITransportTaskScheduler'};
  *((_QWORD *)this + 1) = &TransportManager::`vftable'{for `ITransportTaskCallback'};
  *((_QWORD *)this + 2) = &TransportManager::`vftable'{for `IOneShotTimerCallback'};
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (__int64 **)((char *)this + 56);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (__int64 *)v3 )
      break;
    v5 = (__int64 *)v4[1];
    v6 = *v4;
    *v5 = *v4;
    *(_QWORD *)(v6 + 8) = v5;
    v7 = v4[2];
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)this + 9) = 0;
  v8 = *((_QWORD *)this + 6);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 5);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
}

```

## disassembly

```asm
0x180003dc8  mov     [rsp+arg_8], rbx
0x180003dcd  mov     [rsp+arg_10], rsi
0x180003dd2  push    rdi
0x180003dd3  sub     rsp, 20h
0x180003dd7  mov     rbx, rcx
0x180003dda  lea     rax, ??_7TransportManager@@6BITransportTaskScheduler@@@; const TransportManager::`vftable'{for `ITransportTaskScheduler'}
0x180003de1  mov     [rcx], rax
0x180003de4  lea     rax, ??_7TransportManager@@6BITransportTaskCallback@@@; const TransportManager::`vftable'{for `ITransportTaskCallback'}
0x180003deb  mov     [rcx+8], rax
0x180003def  lea     rax, ??_7TransportManager@@6BIOneShotTimerCallback@@@; const TransportManager::`vftable'{for `IOneShotTimerCallback'}
0x180003df6  mov     [rcx+10h], rax
0x180003dfa  mov     rcx, [rcx+50h]
0x180003dfe  test    rcx, rcx
0x180003e01  jz      short loc_180003E10
0x180003e03  mov     rax, [rcx]
0x180003e06  mov     rax, [rax+10h]
0x180003e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0f  nop
0x180003e10  lea     rsi, [rbx+38h]
0x180003e14  mov     rdi, [rsi]
0x180003e17  cmp     rdi, rsi
0x180003e1a  jz      short loc_180003E51
0x180003e1c  mov     rcx, [rdi+8]
0x180003e20  mov     rax, [rdi]
0x180003e23  mov     [rcx], rax
0x180003e26  mov     [rax+8], rcx
0x180003e2a  mov     rcx, [rdi+10h]
0x180003e2e  test    rcx, rcx
0x180003e31  jz      short loc_180003E40
0x180003e33  mov     rax, [rcx]
0x180003e36  mov     rax, [rax+10h]
0x180003e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3f  nop
0x180003e40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003e47  mov     rcx, rdi; void *
0x180003e4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003e4f  jmp     short loc_180003E14
0x180003e51  mov     qword ptr [rsi+10h], 0
0x180003e59  mov     rcx, [rbx+30h]
0x180003e5d  test    rcx, rcx
0x180003e60  jz      short loc_180003E6F
0x180003e62  mov     rax, [rcx]
0x180003e65  mov     rax, [rax+10h]
0x180003e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e6e  nop
0x180003e6f  mov     rcx, [rbx+28h]
0x180003e73  test    rcx, rcx
0x180003e76  jz      short loc_180003E85
0x180003e78  mov     rax, [rcx]
0x180003e7b  mov     rax, [rax+10h]
0x180003e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e84  nop
0x180003e85  mov     rbx, [rsp+28h+arg_8]
0x180003e8a  mov     rsi, [rsp+28h+arg_10]
0x180003e8f  add     rsp, 20h
0x180003e93  pop     rdi
0x180003e94  retn
```

# DdcTaskSchedulerWrapper::~DdcTaskSchedulerWrapper(void)

- ea: `0x18000b1c0`
- end: `0x18000b1de`
- name: `??1DdcTaskSchedulerWrapper@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(DdcTaskSchedulerWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000bd8d`

## callees

- `0x18000b1c0`
- `0x18000c010`

## pseudocode

```c
void __fastcall DdcTaskSchedulerWrapper::~DdcTaskSchedulerWrapper(DdcTaskSchedulerWrapper *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x18000b1c0  sub     rsp, 28h
0x18000b1c4  mov     rcx, [rcx]
0x18000b1c7  test    rcx, rcx
0x18000b1ca  jz      short loc_18000B1D9
0x18000b1cc  mov     rax, [rcx]
0x18000b1cf  mov     rax, [rax+10h]
0x18000b1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d8  nop
0x18000b1d9  add     rsp, 28h
0x18000b1dd  retn
```

# _APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor$1

- ea: `0x1800091fd`
- end: `0x180009210`
- name: `_APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor$1`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800054dc`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  LOCK::~LOCK((LOCK *)(*(_QWORD *)(a2 + 64) + 144LL));
}

```

## disassembly

```asm
0x1800091fd  mov     rcx, [rdx+40h]
0x180009204  add     rcx, 90h; this
0x18000920b  jmp     ??1LOCK@@QEAA@XZ; LOCK::~LOCK(void)
```

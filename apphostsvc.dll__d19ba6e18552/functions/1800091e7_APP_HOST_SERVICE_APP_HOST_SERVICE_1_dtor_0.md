# _APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor$0

- ea: `0x1800091e7`
- end: `0x1800091f7`
- name: `_APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor$0`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000840c`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::APP_HOST_SERVICE_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MULTI_WORK_QUEUE::~MULTI_WORK_QUEUE((MULTI_WORK_QUEUE *)(*(_QWORD *)(a2 + 64) + 24LL));
}

```

## disassembly

```asm
0x1800091e7  mov     rcx, [rdx+40h]
0x1800091ee  add     rcx, 18h; this
0x1800091f2  jmp     ??1MULTI_WORK_QUEUE@@UEAA@XZ; MULTI_WORK_QUEUE::~MULTI_WORK_QUEUE(void)
```

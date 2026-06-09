# _CThread::CThread_::_1_::dtor$1

- ea: `0x18000a443`
- end: `0x18000a453`
- name: `_CThread::CThread_::_1_::dtor$1`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a50`

## pseudocode

```c
void __fastcall CThread::CThread_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CNotifyEvent::~CNotifyEvent((CNotifyEvent *)(*(_QWORD *)(a2 + 112) + 112LL));
}

```

## disassembly

```asm
0x18000a443  mov     rcx, [rdx+70h]
0x18000a44a  add     rcx, 70h ; 'p'; this
0x18000a44e  jmp     ??1CNotifyEvent@@QEAA@XZ; CNotifyEvent::~CNotifyEvent(void)
```

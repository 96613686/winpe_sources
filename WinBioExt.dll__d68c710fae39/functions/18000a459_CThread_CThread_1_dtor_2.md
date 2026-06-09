# _CThread::CThread_::_1_::dtor$2

- ea: `0x18000a459`
- end: `0x18000a469`
- name: `_CThread::CThread_::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a50`

## pseudocode

```c
void __fastcall CThread::CThread_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CNotifyEvent::~CNotifyEvent((CNotifyEvent *)(*(_QWORD *)(a2 + 112) + 120LL));
}

```

## disassembly

```asm
0x18000a459  mov     rcx, [rdx+70h]
0x18000a460  add     rcx, 78h ; 'x'; this
0x18000a464  jmp     ??1CNotifyEvent@@QEAA@XZ; CNotifyEvent::~CNotifyEvent(void)
```

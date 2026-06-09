# Pal::Task::~Task(void)

- ea: `0x18001c068`
- end: `0x18001c0a3`
- name: `??1Task@Pal@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(Pal::Task *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001c0b0`

## callees

- `0x180010cc0`
- `0x180014cd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c090`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c090`

## pseudocode

```c
void __fastcall Pal::Task::~Task(Pal::Task *this)
{
  std::_Func_class<void,>::_Tidy((char *)this + 336);
  std::_Func_class<void,>::_Tidy((char *)this + 272);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  Pal::AsyncOperation<Core::DummyType>::~AsyncOperation<Core::DummyType>(this);
}

```

## disassembly

```asm
0x18001c068  push    rbx
0x18001c06a  sub     rsp, 20h
0x18001c06e  mov     rbx, rcx
0x18001c071  add     rcx, 150h
0x18001c078  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001c07d  lea     rcx, [rbx+110h]
0x18001c084  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001c089  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x18001c090  call    cs:__imp_DeleteCriticalSection
0x18001c096  mov     rcx, rbx; this
0x18001c099  add     rsp, 20h
0x18001c09d  pop     rbx
0x18001c09e  jmp     ??1?$AsyncOperation@UDummyType@Core@@@Pal@@UEAA@XZ; Pal::AsyncOperation<Core::DummyType>::~AsyncOperation<Core::DummyType>(void)
```

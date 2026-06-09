# EquationManager::~EquationManager(void)

- ea: `0x18000f7bc`
- end: `0x18000f7f8`
- name: `??1EquationManager@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(EquationManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800107d0`
- `0x18001a274`

## callees

- `0x18000f760`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f7df`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f7df`

## pseudocode

```c
void __fastcall EquationManager::~EquationManager(EquationManager *this)
{
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 556) + 16LL))(*((_QWORD *)this + 556));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4408));
  ApplicationMemory::~ApplicationMemory(this);
}

```

## disassembly

```asm
0x18000f7bc  push    rbx
0x18000f7be  sub     rsp, 20h
0x18000f7c2  mov     rbx, rcx
0x18000f7c5  mov     rcx, [rcx+1160h]
0x18000f7cc  mov     rax, [rcx]
0x18000f7cf  mov     rax, [rax+10h]
0x18000f7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d8  lea     rcx, [rbx+1138h]; lpCriticalSection
0x18000f7df  call    cs:__imp_DeleteCriticalSection
0x18000f7e6  nop     dword ptr [rax+rax+00h]
0x18000f7eb  mov     rcx, rbx; this
0x18000f7ee  add     rsp, 20h
0x18000f7f2  pop     rbx
0x18000f7f3  jmp     ??1ApplicationMemory@@QEAA@XZ; ApplicationMemory::~ApplicationMemory(void)
```

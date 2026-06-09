# CPlutonTasksHandler::`vector deleting destructor'(uint)

- ea: `0x180003bc0`
- end: `0x180003bfe`
- name: `??_ECPlutonTasksHandler@@UEAAPEAXI@Z`
- size: `62`
- prototype: `CPlutonTasksHandler *__fastcall(CPlutonTasksHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180002214`
- `0x180003774`
- `0x180003bc0`

## pseudocode

```c
CPlutonTasksHandler *__fastcall CPlutonTasksHandler::`vector deleting destructor'(CPlutonTasksHandler *this, char a2)
{
  *(_QWORD *)this = &CPlutonTasksHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_0], rbx
0x180003bc5  push    rdi
0x180003bc6  sub     rsp, 20h
0x180003bca  lea     rax, ??_7CPlutonTasksHandler@@6B@; const CPlutonTasksHandler::`vftable'
0x180003bd1  mov     ebx, edx
0x180003bd3  mov     [rcx], rax
0x180003bd6  mov     rdi, rcx
0x180003bd9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180003bde  test    bl, 1
0x180003be1  jz      short loc_180003BF0
0x180003be3  mov     edx, 38h ; '8'; unsigned __int64
0x180003be8  mov     rcx, rdi; void *
0x180003beb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003bf0  mov     rbx, [rsp+28h+arg_0]
0x180003bf5  mov     rax, rdi
0x180003bf8  add     rsp, 20h
0x180003bfc  pop     rdi
0x180003bfd  retn
```

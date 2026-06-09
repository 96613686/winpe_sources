# PlutonTasksTrace::`vector deleting destructor'(uint)

- ea: `0x180003c10`
- end: `0x180003c44`
- name: `??_EPlutonTasksTrace@@UEAAPEAXI@Z`
- size: `52`
- prototype: `PlutonTasksTrace *__fastcall(PlutonTasksTrace *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002214`
- `0x1800039b0`
- `0x180003c10`

## pseudocode

```c
PlutonTasksTrace *__fastcall PlutonTasksTrace::`vector deleting destructor'(PlutonTasksTrace *this, char a2)
{
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003c10  mov     [rsp+arg_0], rbx
0x180003c15  push    rdi
0x180003c16  sub     rsp, 20h
0x180003c1a  mov     ebx, edx
0x180003c1c  mov     rdi, rcx
0x180003c1f  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x180003c24  test    bl, 1
0x180003c27  jz      short loc_180003C36
0x180003c29  mov     edx, 20h ; ' '; unsigned __int64
0x180003c2e  mov     rcx, rdi; void *
0x180003c31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003c36  mov     rbx, [rsp+28h+arg_0]
0x180003c3b  mov     rax, rdi
0x180003c3e  add     rsp, 20h
0x180003c42  pop     rdi
0x180003c43  retn
```

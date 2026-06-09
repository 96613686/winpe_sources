# ComTrace::`vector deleting destructor'(uint)

- ea: `0x14000dbd0`
- end: `0x14000dc04`
- name: `??_EComTrace@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(ComTrace *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140008f38`
- `0x14000db9c`
- `0x14000dbd0`

## pseudocode

```c
ComTrace *__fastcall ComTrace::`vector deleting destructor'(ComTrace *this, char a2)
{
  wil::TraceLoggingProvider::~TraceLoggingProvider(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x14000dbd0  mov     [rsp+arg_0], rbx
0x14000dbd5  push    rdi
0x14000dbd6  sub     rsp, 20h
0x14000dbda  mov     ebx, edx
0x14000dbdc  mov     rdi, rcx
0x14000dbdf  call    ??1TraceLoggingProvider@wil@@MEAA@XZ; wil::TraceLoggingProvider::~TraceLoggingProvider(void)
0x14000dbe4  test    bl, 1
0x14000dbe7  jz      short loc_14000DBF6
0x14000dbe9  mov     edx, 20h ; ' '
0x14000dbee  mov     rcx, rdi; pv
0x14000dbf1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dbf6  mov     rbx, [rsp+28h+arg_0]
0x14000dbfb  mov     rax, rdi
0x14000dbfe  add     rsp, 20h
0x14000dc02  pop     rdi
0x14000dc03  retn
```

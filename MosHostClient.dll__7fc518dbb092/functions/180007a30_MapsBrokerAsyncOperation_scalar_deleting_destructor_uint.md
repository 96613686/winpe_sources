# MapsBrokerAsyncOperation::`scalar deleting destructor'(uint)

- ea: `0x180007a30`
- end: `0x180007a5f`
- name: `??_GMapsBrokerAsyncOperation@@UEAAPEAXI@Z`
- size: `47`
- prototype: `MapsBrokerAsyncOperation *__fastcall(MapsBrokerAsyncOperation *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002534`
- `0x180007948`
- `0x180007a30`

## pseudocode

```c
MapsBrokerAsyncOperation *__fastcall MapsBrokerAsyncOperation::`scalar deleting destructor'(
        MapsBrokerAsyncOperation *this,
        char a2)
{
  MapsBrokerAsyncOperation::~MapsBrokerAsyncOperation(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007a30  mov     [rsp+arg_0], rbx
0x180007a35  push    rdi
0x180007a36  sub     rsp, 20h
0x180007a3a  mov     ebx, edx
0x180007a3c  mov     rdi, rcx
0x180007a3f  call    ??1MapsBrokerAsyncOperation@@UEAA@XZ; MapsBrokerAsyncOperation::~MapsBrokerAsyncOperation(void)
0x180007a44  test    bl, 1
0x180007a47  jz      short loc_180007A51
0x180007a49  mov     rcx, rdi; Block
0x180007a4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007a51  mov     rbx, [rsp+28h+arg_0]
0x180007a56  mov     rax, rdi
0x180007a59  add     rsp, 20h
0x180007a5d  pop     rdi
0x180007a5e  retn
```

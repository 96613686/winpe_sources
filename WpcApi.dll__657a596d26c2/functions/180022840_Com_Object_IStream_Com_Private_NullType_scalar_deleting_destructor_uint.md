# Com::Object<IStream,Com::Private::NullType>::`scalar deleting destructor'(uint)

- ea: `0x180022840`
- end: `0x180022874`
- name: `??_G?$Object@UIStream@@UNullType@Private@Com@@@Com@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800036e4`
- `0x180022714`
- `0x180022840`

## pseudocode

```c
void *__fastcall Com::Object<IStream,Com::Private::NullType>::`scalar deleting destructor'(void *Block, char a2)
{
  Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180022840  mov     [rsp+arg_0], rbx
0x180022845  push    rdi
0x180022846  sub     rsp, 20h
0x18002284a  mov     ebx, edx
0x18002284c  mov     rdi, rcx
0x18002284f  call    ??1?$Object@UIStream@@UNullType@Private@Com@@@Com@@UEAA@XZ; Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>(void)
0x180022854  test    bl, 1
0x180022857  jz      short loc_180022866
0x180022859  mov     edx, 20h ; ' '
0x18002285e  mov     rcx, rdi; Block
0x180022861  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022866  mov     rbx, [rsp+28h+arg_0]
0x18002286b  mov     rax, rdi
0x18002286e  add     rsp, 20h
0x180022872  pop     rdi
0x180022873  retn
```

# OutputStreamComAdapter::`vector deleting destructor'(uint)

- ea: `0x180023ed0`
- end: `0x180023f04`
- name: `??_EOutputStreamComAdapter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `OutputStreamComAdapter *__fastcall(OutputStreamComAdapter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800036e4`
- `0x180022714`
- `0x180023ed0`

## pseudocode

```c
OutputStreamComAdapter *__fastcall OutputStreamComAdapter::`vector deleting destructor'(
        OutputStreamComAdapter *this,
        char a2)
{
  Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>((__int64)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180023ed0  mov     [rsp+arg_0], rbx
0x180023ed5  push    rdi
0x180023ed6  sub     rsp, 20h
0x180023eda  mov     ebx, edx
0x180023edc  mov     rdi, rcx
0x180023edf  call    ??1?$Object@UIStream@@UNullType@Private@Com@@@Com@@UEAA@XZ; Com::Object<IStream,Com::Private::NullType>::~Object<IStream,Com::Private::NullType>(void)
0x180023ee4  test    bl, 1
0x180023ee7  jz      short loc_180023EF6
0x180023ee9  mov     edx, 28h ; '('
0x180023eee  mov     rcx, rdi; Block
0x180023ef1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023ef6  mov     rbx, [rsp+28h+arg_0]
0x180023efb  mov     rax, rdi
0x180023efe  add     rsp, 20h
0x180023f02  pop     rdi
0x180023f03  retn
```

# Comms::SerializeBase::`vector deleting destructor'(uint)

- ea: `0x180003860`
- end: `0x180003886`
- name: `??_ESerializeBase@Comms@@UEAAPEAXI@Z`
- size: `38`
- prototype: `Comms::SerializeBase *__fastcall(Comms::SerializeBase *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180003860`

## pseudocode

```c
Comms::SerializeBase *__fastcall Comms::SerializeBase::`vector deleting destructor'(
        Comms::SerializeBase *this,
        char a2)
{
  *(_QWORD *)this = &Comms::SerializeBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003860  push    rbx
0x180003862  sub     rsp, 20h
0x180003866  lea     rax, ??_7SerializeBase@Comms@@6B@; const Comms::SerializeBase::`vftable'
0x18000386d  mov     rbx, rcx
0x180003870  mov     [rcx], rax
0x180003873  test    dl, 1
0x180003876  jz      short loc_18000387D
0x180003878  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000387d  mov     rax, rbx
0x180003880  add     rsp, 20h
0x180003884  pop     rbx
0x180003885  retn
```

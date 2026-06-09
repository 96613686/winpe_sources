# Broker::InvalidParameter::`vector deleting destructor'(uint)

- ea: `0x180014480`
- end: `0x1800144c2`
- name: `??_EInvalidParameter@Broker@@UEAAPEAXI@Z`
- size: `66`
- prototype: `Broker::InvalidParameter *__fastcall(Broker::InvalidParameter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800131e4`
- `0x180013882`
- `0x180014480`

## pseudocode

```c
Broker::InvalidParameter *__fastcall Broker::InvalidParameter::`vector deleting destructor'(
        Broker::InvalidParameter *this,
        char a2)
{
  *(_QWORD *)this = &std::exception::`vftable';
  o___std_exception_destroy_0((char *)this + 8);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180014480  mov     [rsp+arg_0], rbx
0x180014485  push    rdi
0x180014486  sub     rsp, 20h
0x18001448a  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180014491  mov     rdi, rcx
0x180014494  mov     [rcx], rax
0x180014497  mov     ebx, edx
0x180014499  add     rcx, 8
0x18001449d  call    _o___std_exception_destroy_0
0x1800144a2  test    bl, 1
0x1800144a5  jz      short loc_1800144B4
0x1800144a7  mov     edx, 20h ; ' '; unsigned __int64
0x1800144ac  mov     rcx, rdi; void *
0x1800144af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800144b4  mov     rbx, [rsp+28h+arg_0]
0x1800144b9  mov     rax, rdi
0x1800144bc  add     rsp, 20h
0x1800144c0  pop     rdi
0x1800144c1  retn
```

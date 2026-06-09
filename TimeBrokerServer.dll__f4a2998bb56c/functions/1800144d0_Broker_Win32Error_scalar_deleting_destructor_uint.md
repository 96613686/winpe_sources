# Broker::Win32Error::`scalar deleting destructor'(uint)

- ea: `0x1800144d0`
- end: `0x180014512`
- name: `??_GWin32Error@Broker@@UEAAPEAXI@Z`
- size: `66`
- prototype: `Broker::Win32Error *__fastcall(Broker::Win32Error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800131e4`
- `0x180013882`
- `0x1800144d0`

## pseudocode

```c
Broker::Win32Error *__fastcall Broker::Win32Error::`scalar deleting destructor'(Broker::Win32Error *this, char a2)
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
0x1800144d0  mov     [rsp+arg_0], rbx
0x1800144d5  push    rdi
0x1800144d6  sub     rsp, 20h
0x1800144da  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800144e1  mov     rdi, rcx
0x1800144e4  mov     [rcx], rax
0x1800144e7  mov     ebx, edx
0x1800144e9  add     rcx, 8
0x1800144ed  call    _o___std_exception_destroy_0
0x1800144f2  test    bl, 1
0x1800144f5  jz      short loc_180014504
0x1800144f7  mov     edx, 28h ; '('; unsigned __int64
0x1800144fc  mov     rcx, rdi; void *
0x1800144ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014504  mov     rbx, [rsp+28h+arg_0]
0x180014509  mov     rax, rdi
0x18001450c  add     rsp, 20h
0x180014510  pop     rdi
0x180014511  retn
```

# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$16

- ea: `0x18000ceae`
- end: `0x18000cece`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$16`
- size: `32`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x180001644`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 184));
}

```

## disassembly

```asm
0x18000ceae  push    rbp
0x18000ceb0  sub     rsp, 20h
0x18000ceb4  mov     rbp, rdx
0x18000ceb7  mov     edx, 28h ; '('; unsigned __int64
0x18000cebc  mov     rcx, [rbp+0B8h]; void *
0x18000cec3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cec8  add     rsp, 20h
0x18000cecc  pop     rbp
0x18000cecd  retn
```

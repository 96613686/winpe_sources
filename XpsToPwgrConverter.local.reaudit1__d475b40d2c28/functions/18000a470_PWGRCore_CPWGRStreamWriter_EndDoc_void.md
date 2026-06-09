# PWGRCore::CPWGRStreamWriter::EndDoc(void)

- ea: `0x18000a470`
- end: `0x18000a482`
- name: `?EndDoc@CPWGRStreamWriter@PWGRCore@@UEAAJXZ`
- size: `18`
- prototype: `__int64 __fastcall(PWGRCore::CPWGRStreamWriter *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall PWGRCore::CPWGRStreamWriter::EndDoc(PWGRCore::CPWGRStreamWriter *this)
{
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2), 0);
}

```

## disassembly

```asm
0x18000a470  mov     rcx, [rcx+10h]
0x18000a474  xor     edx, edx
0x18000a476  mov     rax, [rcx]
0x18000a479  mov     rax, [rax+40h]
0x18000a47d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

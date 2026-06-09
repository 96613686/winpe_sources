# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180010538`
- end: `0x180010555`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `29`
- prototype: `_com_error *__fastcall(_com_error *this, int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010608`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, int a2, struct IErrorInfo *a3)
{
  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_QWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x180010538  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18001053f  mov     [rcx], rax
0x180010542  mov     [rcx+8], edx
0x180010545  mov     [rcx+10h], r8
0x180010549  mov     qword ptr [rcx+18h], 0
0x180010551  mov     rax, rcx
0x180010554  retn
```

# _com_error::_com_error(long,IErrorInfo *,bool)

- ea: `0x180009988`
- end: `0x1800099ad`
- name: `??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z`
- size: `37`
- prototype: `_com_error *__fastcall(_com_error *__hidden this, int, struct IErrorInfo *, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800099f8`

## pseudocode

```c
_com_error *__fastcall _com_error::_com_error(_com_error *this, __int64 a2, struct IErrorInfo *a3)
{
  *(_QWORD *)this = &_com_error::`vftable';
  *((_DWORD *)this + 2) = -2147024882;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  return this;
}

```

## disassembly

```asm
0x180009988  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x18000998f  mov     [rcx], rax
0x180009992  mov     dword ptr [rcx+8], 8007000Eh
0x180009999  mov     qword ptr [rcx+10h], 0
0x1800099a1  mov     qword ptr [rcx+18h], 0
0x1800099a9  mov     rax, rcx
0x1800099ac  retn
```

# TOKEN_KEY::TOKEN_KEY(void)

- ea: `0x18000421c`
- end: `0x18000424c`
- name: `??0TOKEN_KEY@@QEAA@XZ`
- size: `48`
- prototype: `TOKEN_KEY *__fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800041a4`
- `0x1800043b8`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180004233`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000423d`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004233`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000423d`

## pseudocode

```c
TOKEN_KEY *__fastcall TOKEN_KEY::TOKEN_KEY(TOKEN_KEY *this)
{
  *(_QWORD *)this = &TOKEN_KEY::`vftable';
  STRU::STRU((TOKEN_KEY *)((char *)this + 8));
  STRU::STRU((TOKEN_KEY *)((char *)this + 64));
  return this;
}

```

## disassembly

```asm
0x18000421c  push    rbx
0x18000421e  sub     rsp, 20h
0x180004222  lea     rax, ??_7TOKEN_KEY@@6B@; const TOKEN_KEY::`vftable'
0x180004229  mov     rbx, rcx
0x18000422c  mov     [rcx], rax
0x18000422f  add     rcx, 8
0x180004233  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004239  lea     rcx, [rbx+40h]
0x18000423d  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004243  mov     rax, rbx
0x180004246  add     rsp, 20h
0x18000424a  pop     rbx
0x18000424b  retn
```

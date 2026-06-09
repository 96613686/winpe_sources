# TOKEN_KEY::~TOKEN_KEY(void)

- ea: `0x180004314`
- end: `0x180004337`
- name: `??1TOKEN_KEY@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004290`
- `0x1800043b8`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180004321`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004321`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004330`

## pseudocode

```c
void __fastcall TOKEN_KEY::~TOKEN_KEY(TOKEN_KEY *this)
{
  STRU::~STRU((TOKEN_KEY *)((char *)this + 64));
  STRU::~STRU((TOKEN_KEY *)((char *)this + 8));
}

```

## disassembly

```asm
0x180004314  push    rbx
0x180004316  sub     rsp, 20h
0x18000431a  mov     rbx, rcx
0x18000431d  add     rcx, 40h ; '@'
0x180004321  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004327  lea     rcx, [rbx+8]
0x18000432b  add     rsp, 20h
0x18000432f  pop     rbx
0x180004330  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```

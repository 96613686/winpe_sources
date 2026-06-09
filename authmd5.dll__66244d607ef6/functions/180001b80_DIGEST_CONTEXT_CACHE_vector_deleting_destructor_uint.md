# DIGEST_CONTEXT_CACHE::`vector deleting destructor'(uint)

- ea: `0x180001b80`
- end: `0x180001bd3`
- name: `??_EDIGEST_CONTEXT_CACHE@@UEAAPEAXI@Z`
- size: `83`
- prototype: `void *__fastcall(DIGEST_CONTEXT_CACHE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001064`
- `0x180001b80`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001bac`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180001bac`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180001ba2`
- `iisutil!?Clear@CLKRHashTable@@QEAAXXZ` at `0x180001ba2`

## pseudocode

```c
DIGEST_CONTEXT_CACHE *__fastcall DIGEST_CONTEXT_CACHE::`vector deleting destructor'(
        DIGEST_CONTEXT_CACHE *this,
        char a2)
{
  *(_QWORD *)this = &DIGEST_CONTEXT_CACHE::`vftable';
  CLKRHashTable::Clear((DIGEST_CONTEXT_CACHE *)((char *)this + 8));
  CLKRHashTable::~CLKRHashTable((DIGEST_CONTEXT_CACHE *)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180001b80  mov     [rsp+arg_0], rbx
0x180001b85  mov     [rsp+arg_8], rsi
0x180001b8a  push    rdi
0x180001b8b  sub     rsp, 20h
0x180001b8f  lea     rax, ??_7DIGEST_CONTEXT_CACHE@@6B@; const DIGEST_CONTEXT_CACHE::`vftable'
0x180001b96  mov     rsi, rcx
0x180001b99  mov     [rcx], rax
0x180001b9c  mov     edi, edx
0x180001b9e  add     rcx, 8
0x180001ba2  call    cs:__imp_?Clear@CLKRHashTable@@QEAAXXZ; CLKRHashTable::Clear(void)
0x180001ba8  lea     rcx, [rsi+8]
0x180001bac  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180001bb2  test    dil, 1
0x180001bb6  jz      short loc_180001BC0
0x180001bb8  mov     rcx, rsi; Block
0x180001bbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001bc0  mov     rbx, [rsp+28h+arg_0]
0x180001bc5  mov     rax, rsi
0x180001bc8  mov     rsi, [rsp+28h+arg_8]
0x180001bcd  add     rsp, 20h
0x180001bd1  pop     rdi
0x180001bd2  retn
```

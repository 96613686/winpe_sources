# ANON_META_STORED_CONTEXT::~ANON_META_STORED_CONTEXT(void)

- ea: `0x180003388`
- end: `0x1800033d8`
- name: `??1ANON_META_STORED_CONTEXT@@EEAA@XZ`
- size: `80`
- prototype: `void __fastcall(ANON_META_STORED_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033e0`

## callees

- `0x180003388`
- `0x180006010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033c2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033c2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033d1`

## pseudocode

```c
void __fastcall ANON_META_STORED_CONTEXT::~ANON_META_STORED_CONTEXT(ANON_META_STORED_CONTEXT *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &ANON_META_STORED_CONTEXT::`vftable';
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 56LL))(v2);
    *((_QWORD *)this + 17) = 0;
  }
  STRU::~STRU((ANON_META_STORED_CONTEXT *)((char *)this + 72));
  STRU::~STRU((ANON_META_STORED_CONTEXT *)((char *)this + 16));
}

```

## disassembly

```asm
0x180003388  push    rbx
0x18000338a  sub     rsp, 20h
0x18000338e  lea     rax, ??_7ANON_META_STORED_CONTEXT@@6B@; const ANON_META_STORED_CONTEXT::`vftable'
0x180003395  mov     rbx, rcx
0x180003398  mov     [rcx], rax
0x18000339b  mov     rcx, [rcx+88h]
0x1800033a2  test    rcx, rcx
0x1800033a5  jz      short loc_1800033BE
0x1800033a7  mov     rax, [rcx]
0x1800033aa  mov     rax, [rax+38h]
0x1800033ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b3  mov     qword ptr [rbx+88h], 0
0x1800033be  lea     rcx, [rbx+48h]
0x1800033c2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800033c8  lea     rcx, [rbx+10h]
0x1800033cc  add     rsp, 20h
0x1800033d0  pop     rbx
0x1800033d1  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```

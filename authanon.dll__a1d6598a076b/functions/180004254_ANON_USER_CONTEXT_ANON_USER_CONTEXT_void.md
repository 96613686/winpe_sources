# ANON_USER_CONTEXT::~ANON_USER_CONTEXT(void)

- ea: `0x180004254`
- end: `0x18000428a`
- name: `??1ANON_USER_CONTEXT@@EEAA@XZ`
- size: `54`
- prototype: `void __fastcall(ANON_USER_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004340`

## callees

- `0x180004254`
- `0x180006010`

## pseudocode

```c
void __fastcall ANON_USER_CONTEXT::~ANON_USER_CONTEXT(ANON_USER_CONTEXT *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &ANON_USER_CONTEXT::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180004254  push    rbx
0x180004256  sub     rsp, 20h
0x18000425a  lea     rax, ??_7ANON_USER_CONTEXT@@6B@; const ANON_USER_CONTEXT::`vftable'
0x180004261  mov     rbx, rcx
0x180004264  mov     [rcx], rax
0x180004267  mov     rcx, [rcx+10h]
0x18000426b  test    rcx, rcx
0x18000426e  jz      short loc_180004284
0x180004270  mov     rax, [rcx]
0x180004273  mov     rax, [rax+10h]
0x180004277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427c  mov     qword ptr [rbx+10h], 0
0x180004284  add     rsp, 20h
0x180004288  pop     rbx
0x180004289  retn
```

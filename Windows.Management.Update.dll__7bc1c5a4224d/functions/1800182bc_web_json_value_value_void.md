# web::json::value::~value(void)

- ea: `0x1800182bc`
- end: `0x1800182e1`
- name: `??1value@json@web@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(web::json::value *__hidden this)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800285dd`
- `0x1800285f0`
- `0x180028626`
- `0x180028667`
- `0x180028693`
- `0x1800286d1`
- `0x1800286fd`
- `0x180028729`
- `0x18002873b`
- `0x18002875f`
- `0x180028783`
- `0x1800287a7`
- `0x180028823`
- `0x180028859`
- `0x18002887d`
- `0x1800288b3`
- `0x180028923`
- `0x18002904a`

## callees

- `0x1800182bc`
- `0x18002a010`

## pseudocode

```c
void __fastcall web::json::value::~value(web::json::value *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 192LL))(v1, 1);
}

```

## disassembly

```asm
0x1800182bc  sub     rsp, 28h
0x1800182c0  mov     rcx, [rcx]
0x1800182c3  test    rcx, rcx
0x1800182c6  jz      short loc_1800182DC
0x1800182c8  mov     rax, [rcx]
0x1800182cb  mov     edx, 1
0x1800182d0  mov     rax, [rax+0C0h]
0x1800182d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182dc  add     rsp, 28h
0x1800182e0  retn
```

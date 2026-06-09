# CPrintCoreConfig::GetInfoHeader(void)

- ea: `0x180032ce4`
- end: `0x180032d09`
- name: `?GetInfoHeader@CPrintCoreConfig@@QEBAPEAU_INFOHEADER@@XZ`
- size: `37`
- prototype: `struct _INFOHEADER *__fastcall(CPrintCoreConfig *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002c484`
- `0x18002c5b0`
- `0x18002c6f0`
- `0x18002c7d0`
- `0x180032d10`

## callees

- `0x180032ce4`
- `0x18005d010`

## pseudocode

```c
struct _INFOHEADER *__fastcall CPrintCoreConfig::GetInfoHeader(CPrintCoreConfig *this)
{
  struct _INFOHEADER *result; // rax

  result = (struct _INFOHEADER *)*((_QWORD *)this + 132);
  if ( !result )
    return (struct _INFOHEADER *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 1) + 24LL))(*(_QWORD *)this);
  return result;
}

```

## disassembly

```asm
0x180032ce4  sub     rsp, 28h
0x180032ce8  mov     rax, [rcx+420h]
0x180032cef  test    rax, rax
0x180032cf2  jnz     short loc_180032D04
0x180032cf4  mov     rax, [rcx+8]
0x180032cf8  mov     rcx, [rcx]
0x180032cfb  mov     rax, [rax+18h]
0x180032cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d04  add     rsp, 28h
0x180032d08  retn
```

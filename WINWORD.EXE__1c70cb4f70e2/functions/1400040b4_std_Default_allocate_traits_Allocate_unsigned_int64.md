# std::_Default_allocate_traits::_Allocate(unsigned __int64)

- ea: `0x1400040b4`
- end: `0x1400040cf`
- name: `?_Allocate@_Default_allocate_traits@std@@SAPEAX_K@Z`
- size: `27`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003430`
- `0x14000345c`

## callees

- `0x1400040b4`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1400040c3`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x1400040c3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400040b8`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400040b8`

## pseudocode

```c
void *__fastcall std::_Default_allocate_traits::_Allocate(size_t a1)
{
  void *result; // rax

  result = malloc(a1);
  if ( !result )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x1400040b4  sub     rsp, 28h
0x1400040b8  call    cs:__imp_malloc
0x1400040be  test    rax, rax
0x1400040c1  jnz     short loc_1400040CA
0x1400040c3  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400040c9  int     3; Trap to Debugger
0x1400040ca  add     rsp, 28h
0x1400040ce  retn
```

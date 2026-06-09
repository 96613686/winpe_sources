# __scrt_release_startup_lock

- ea: `0x180003d44`
- end: `0x180003d68`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032e0`
- `0x1800033f8`

## callees

- `0x180003d44`
- `0x1800042e4`

## pseudocode

```c
_BOOL8 __fastcall _scrt_release_startup_lock(char a1)
{
  _BOOL8 result; // rax

  result = _scrt_is_ucrt_dll_in_use();
  if ( result && !a1 )
    _InterlockedExchange64(&_scrt_native_startup_lock, 0);
  return result;
}

```

## disassembly

```asm
0x180003d44  push    rbx
0x180003d46  sub     rsp, 20h
0x180003d4a  mov     bl, cl
0x180003d4c  call    __scrt_is_ucrt_dll_in_use
0x180003d51  xor     edx, edx
0x180003d53  test    eax, eax
0x180003d55  jz      short loc_180003D62
0x180003d57  test    bl, bl
0x180003d59  jnz     short loc_180003D62
0x180003d5b  xchg    rdx, cs:__scrt_native_startup_lock
0x180003d62  add     rsp, 20h
0x180003d66  pop     rbx
0x180003d67  retn
```

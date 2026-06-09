# __scrt_release_startup_lock

- ea: `0x140001538`
- end: `0x14000155c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001180`

## callees

- `0x140001538`
- `0x140001bfc`

## pseudocode

```c
__int64 __fastcall _scrt_release_startup_lock(char a1)
{
  __int64 result; // rax

  result = _scrt_is_ucrt_dll_in_use();
  if ( (_DWORD)result )
  {
    if ( !a1 )
      return _InterlockedExchange64(&_scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140001538  push    rbx
0x14000153a  sub     rsp, 20h
0x14000153e  mov     bl, cl
0x140001540  call    __scrt_is_ucrt_dll_in_use
0x140001545  test    eax, eax
0x140001547  jz      short loc_140001556
0x140001549  test    bl, bl
0x14000154b  jnz     short loc_140001556
0x14000154d  xor     eax, eax
0x14000154f  xchg    rax, cs:__scrt_native_startup_lock
0x140001556  add     rsp, 20h
0x14000155a  pop     rbx
0x14000155b  retn
```

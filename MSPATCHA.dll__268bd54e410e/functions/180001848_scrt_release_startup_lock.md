# __scrt_release_startup_lock

- ea: `0x180001848`
- end: `0x18000186c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010e8`
- `0x1800011e8`

## callees

- `0x180001848`
- `0x180001c08`

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
0x180001848  push    rbx
0x18000184a  sub     rsp, 20h
0x18000184e  mov     bl, cl
0x180001850  call    __scrt_is_ucrt_dll_in_use
0x180001855  test    eax, eax
0x180001857  jz      short loc_180001866
0x180001859  test    bl, bl
0x18000185b  jnz     short loc_180001866
0x18000185d  xor     eax, eax
0x18000185f  xchg    rax, cs:__scrt_native_startup_lock
0x180001866  add     rsp, 20h
0x18000186a  pop     rbx
0x18000186b  retn
```

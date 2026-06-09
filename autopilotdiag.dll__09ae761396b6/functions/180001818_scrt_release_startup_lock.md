# __scrt_release_startup_lock

- ea: `0x180001818`
- end: `0x18000183c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010e8`
- `0x1800011e8`

## callees

- `0x180001818`
- `0x180001bb0`

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
0x180001818  push    rbx
0x18000181a  sub     rsp, 20h
0x18000181e  mov     bl, cl
0x180001820  call    __scrt_is_ucrt_dll_in_use
0x180001825  test    eax, eax
0x180001827  jz      short loc_180001836
0x180001829  test    bl, bl
0x18000182b  jnz     short loc_180001836
0x18000182d  xor     eax, eax
0x18000182f  xchg    rax, cs:__scrt_native_startup_lock
0x180001836  add     rsp, 20h
0x18000183a  pop     rbx
0x18000183b  retn
```

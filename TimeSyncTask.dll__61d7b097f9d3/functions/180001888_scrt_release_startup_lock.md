# __scrt_release_startup_lock

- ea: `0x180001888`
- end: `0x1800018ac`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001148`
- `0x180001248`

## callees

- `0x180001888`
- `0x180001c44`

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
0x180001888  push    rbx
0x18000188a  sub     rsp, 20h
0x18000188e  mov     bl, cl
0x180001890  call    __scrt_is_ucrt_dll_in_use
0x180001895  test    eax, eax
0x180001897  jz      short loc_1800018A6
0x180001899  test    bl, bl
0x18000189b  jnz     short loc_1800018A6
0x18000189d  xor     eax, eax
0x18000189f  xchg    rax, cs:__scrt_native_startup_lock
0x1800018a6  add     rsp, 20h
0x1800018aa  pop     rbx
0x1800018ab  retn
```

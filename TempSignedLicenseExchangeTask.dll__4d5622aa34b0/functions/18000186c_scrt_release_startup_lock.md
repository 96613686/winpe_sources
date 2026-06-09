# __scrt_release_startup_lock

- ea: `0x18000186c`
- end: `0x180001890`
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

- `0x18000186c`
- `0x180001e20`

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
0x18000186c  push    rbx
0x18000186e  sub     rsp, 20h
0x180001872  mov     bl, cl
0x180001874  call    __scrt_is_ucrt_dll_in_use
0x180001879  test    eax, eax
0x18000187b  jz      short loc_18000188A
0x18000187d  test    bl, bl
0x18000187f  jnz     short loc_18000188A
0x180001881  xor     eax, eax
0x180001883  xchg    rax, cs:__scrt_native_startup_lock
0x18000188a  add     rsp, 20h
0x18000188e  pop     rbx
0x18000188f  retn
```

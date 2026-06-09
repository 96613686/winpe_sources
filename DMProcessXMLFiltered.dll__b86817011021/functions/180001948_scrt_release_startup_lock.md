# __scrt_release_startup_lock

- ea: `0x180001948`
- end: `0x18000196c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001208`
- `0x180001308`

## callees

- `0x180001948`
- `0x180001d4c`

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
0x180001948  push    rbx
0x18000194a  sub     rsp, 20h
0x18000194e  mov     bl, cl
0x180001950  call    __scrt_is_ucrt_dll_in_use
0x180001955  test    eax, eax
0x180001957  jz      short loc_180001966
0x180001959  test    bl, bl
0x18000195b  jnz     short loc_180001966
0x18000195d  xor     eax, eax
0x18000195f  xchg    rax, cs:__scrt_native_startup_lock
0x180001966  add     rsp, 20h
0x18000196a  pop     rbx
0x18000196b  retn
```

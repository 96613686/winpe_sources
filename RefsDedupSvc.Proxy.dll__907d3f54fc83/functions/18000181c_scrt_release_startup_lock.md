# __scrt_release_startup_lock

- ea: `0x18000181c`
- end: `0x180001840`
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

- `0x18000181c`
- `0x180001bd8`

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
0x18000181c  push    rbx
0x18000181e  sub     rsp, 20h
0x180001822  mov     bl, cl
0x180001824  call    __scrt_is_ucrt_dll_in_use
0x180001829  test    eax, eax
0x18000182b  jz      short loc_18000183A
0x18000182d  test    bl, bl
0x18000182f  jnz     short loc_18000183A
0x180001831  xor     eax, eax
0x180001833  xchg    rax, cs:__scrt_native_startup_lock
0x18000183a  add     rsp, 20h
0x18000183e  pop     rbx
0x18000183f  retn
```

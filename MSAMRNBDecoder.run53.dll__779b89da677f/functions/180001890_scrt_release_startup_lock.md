# __scrt_release_startup_lock

- ea: `0x180001890`
- end: `0x1800018b4`
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

- `0x180001890`
- `0x180001e4c`

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
0x180001890  push    rbx
0x180001892  sub     rsp, 20h
0x180001896  mov     bl, cl
0x180001898  call    __scrt_is_ucrt_dll_in_use
0x18000189d  test    eax, eax
0x18000189f  jz      short loc_1800018AE
0x1800018a1  test    bl, bl
0x1800018a3  jnz     short loc_1800018AE
0x1800018a5  xor     eax, eax
0x1800018a7  xchg    rax, cs:__scrt_native_startup_lock
0x1800018ae  add     rsp, 20h
0x1800018b2  pop     rbx
0x1800018b3  retn
```

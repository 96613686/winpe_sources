# __scrt_release_startup_lock

- ea: `0x1800018a4`
- end: `0x1800018c8`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001278`
- `0x180001378`

## callees

- `0x1800018a4`
- `0x180001e28`

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
0x1800018a4  push    rbx
0x1800018a6  sub     rsp, 20h
0x1800018aa  mov     bl, cl
0x1800018ac  call    __scrt_is_ucrt_dll_in_use
0x1800018b1  test    eax, eax
0x1800018b3  jz      short loc_1800018C2
0x1800018b5  test    bl, bl
0x1800018b7  jnz     short loc_1800018C2
0x1800018b9  xor     eax, eax
0x1800018bb  xchg    rax, cs:__scrt_native_startup_lock
0x1800018c2  add     rsp, 20h
0x1800018c6  pop     rbx
0x1800018c7  retn
```

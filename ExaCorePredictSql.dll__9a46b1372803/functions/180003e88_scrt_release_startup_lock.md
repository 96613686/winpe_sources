# __scrt_release_startup_lock

- ea: `0x180003e88`
- end: `0x180003eac`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003fd0`
- `0x1800040fc`

## callees

- `0x180003e88`
- `0x180004670`

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
0x180003e88  push    rbx
0x180003e8a  sub     rsp, 20h
0x180003e8e  mov     bl, cl
0x180003e90  call    __scrt_is_ucrt_dll_in_use
0x180003e95  xor     edx, edx
0x180003e97  test    eax, eax
0x180003e99  jz      short loc_180003EA6
0x180003e9b  test    bl, bl
0x180003e9d  jnz     short loc_180003EA6
0x180003e9f  xchg    rdx, cs:__scrt_native_startup_lock
0x180003ea6  add     rsp, 20h
0x180003eaa  pop     rbx
0x180003eab  retn
```

# __scrt_release_startup_lock

- ea: `0x180001930`
- end: `0x180001954`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011a0`
- `0x1800012b8`

## callees

- `0x180001930`
- `0x180001e94`

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
0x180001930  push    rbx
0x180001932  sub     rsp, 20h
0x180001936  mov     bl, cl
0x180001938  call    __scrt_is_ucrt_dll_in_use
0x18000193d  xor     edx, edx
0x18000193f  test    eax, eax
0x180001941  jz      short loc_18000194E
0x180001943  test    bl, bl
0x180001945  jnz     short loc_18000194E
0x180001947  xchg    rdx, cs:__scrt_native_startup_lock
0x18000194e  add     rsp, 20h
0x180001952  pop     rbx
0x180001953  retn
```

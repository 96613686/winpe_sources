# __scrt_release_startup_lock

- ea: `0x14000105c`
- end: `0x140001080`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001ac0`

## callees

- `0x14000105c`
- `0x1400022d4`

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
0x14000105c  push    rbx
0x14000105e  sub     rsp, 20h
0x140001062  mov     bl, cl
0x140001064  call    __scrt_is_ucrt_dll_in_use
0x140001069  xor     edx, edx
0x14000106b  test    eax, eax
0x14000106d  jz      short loc_14000107A
0x14000106f  test    bl, bl
0x140001071  jnz     short loc_14000107A
0x140001073  xchg    rdx, cs:__scrt_native_startup_lock
0x14000107a  add     rsp, 20h
0x14000107e  pop     rbx
0x14000107f  retn
```

# __scrt_release_startup_lock

- ea: `0x180001894`
- end: `0x1800018b8`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001128`
- `0x180001228`

## callees

- `0x180001894`
- `0x180001c54`

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
0x180001894  push    rbx
0x180001896  sub     rsp, 20h
0x18000189a  mov     bl, cl
0x18000189c  call    __scrt_is_ucrt_dll_in_use
0x1800018a1  test    eax, eax
0x1800018a3  jz      short loc_1800018B2
0x1800018a5  test    bl, bl
0x1800018a7  jnz     short loc_1800018B2
0x1800018a9  xor     eax, eax
0x1800018ab  xchg    rax, cs:__scrt_native_startup_lock
0x1800018b2  add     rsp, 20h
0x1800018b6  pop     rbx
0x1800018b7  retn
```

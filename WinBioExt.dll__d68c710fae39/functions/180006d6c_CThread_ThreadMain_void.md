# CThread::ThreadMain(void)

- ea: `0x180006d6c`
- end: `0x180006d92`
- name: `?ThreadMain@CThread@@AEAAJXZ`
- size: `38`
- prototype: `__int64 __fastcall(CThread *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006da0`

## callees

- `0x180006d6c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CThread::ThreadMain(CThread *this)
{
  __int64 v1; // rcx
  __int64 result; // rax
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 v5; // [rsp+0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *((_QWORD *)this + 10);
  if ( !v1 )
    return 0;
  try
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(retaddr, &v5, v3, v4);
  }
  return result;
}

```

## disassembly

```asm
0x180006d6c  sub     rsp, 28h
0x180006d70  mov     rdx, rcx
0x180006d73  mov     rcx, [rcx+50h]
0x180006d77  test    rcx, rcx
0x180006d7a  jnz     short loc_180006D83
0x180006d7c  xor     eax, eax
0x180006d7e  add     rsp, 28h
0x180006d82  retn
0x180006d83  mov     rax, [rcx]
0x180006d86  mov     rax, [rax+10h]
0x180006d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d8f  nop
0x180006d90  jmp     short loc_180006D7E
```

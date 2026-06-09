# __security_init_cookie

- ea: `0x180007aa8`
- end: `0x180007aec`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007820`

## callees

- `0x180007aa8`
- `0x180007af4`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    _security_init_cookie_ex(&_security_cookie);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x180007aa8  sub     rsp, 28h
0x180007aac  cmp     cs:__security_cookie, 0
0x180007ab4  jz      short loc_180007AC9
0x180007ab6  mov     rax, 2B992DDFA232h
0x180007ac0  cmp     cs:__security_cookie, rax
0x180007ac7  jnz     short loc_180007AD6
0x180007ac9  lea     rcx, __security_cookie
0x180007ad0  call    __security_init_cookie_ex
0x180007ad5  nop
0x180007ad6  mov     rax, cs:__security_cookie
0x180007add  not     rax
0x180007ae0  mov     cs:__security_cookie_complement, rax
0x180007ae7  add     rsp, 28h
0x180007aeb  retn
```

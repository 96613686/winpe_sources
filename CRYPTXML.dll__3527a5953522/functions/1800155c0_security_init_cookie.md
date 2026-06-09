# __security_init_cookie

- ea: `0x1800155c0`
- end: `0x180015604`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015418`

## callees

- `0x1800155c0`
- `0x18001560c`

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
0x1800155c0  sub     rsp, 28h
0x1800155c4  cmp     cs:__security_cookie, 0
0x1800155cc  jz      short loc_1800155E1
0x1800155ce  mov     rax, 2B992DDFA232h
0x1800155d8  cmp     cs:__security_cookie, rax
0x1800155df  jnz     short loc_1800155EE
0x1800155e1  lea     rcx, __security_cookie
0x1800155e8  call    __security_init_cookie_ex
0x1800155ed  nop
0x1800155ee  mov     rax, cs:__security_cookie
0x1800155f5  not     rax
0x1800155f8  mov     cs:__security_cookie_complement, rax
0x1800155ff  add     rsp, 28h
0x180015603  retn
```

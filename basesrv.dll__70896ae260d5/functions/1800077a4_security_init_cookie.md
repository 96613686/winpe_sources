# __security_init_cookie

- ea: `0x1800077a4`
- end: `0x1800077e7`
- name: `__security_init_cookie`
- size: `67`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007520`

## callees

- `0x1800077a4`
- `0x1800077f0`

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
0x1800077a4  sub     rsp, 28h
0x1800077a8  cmp     cs:__security_cookie, 0
0x1800077b0  jz      short loc_1800077C5
0x1800077b2  mov     rax, 2B992DDFA232h
0x1800077bc  cmp     cs:__security_cookie, rax
0x1800077c3  jnz     short loc_1800077D1
0x1800077c5  lea     rcx, __security_cookie
0x1800077cc  call    __security_init_cookie_ex
0x1800077d1  mov     rax, cs:__security_cookie
0x1800077d8  not     rax
0x1800077db  mov     cs:__security_cookie_complement, rax
0x1800077e2  add     rsp, 28h
0x1800077e6  retn
```

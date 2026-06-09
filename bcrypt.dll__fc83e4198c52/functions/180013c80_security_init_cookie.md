# __security_init_cookie

- ea: `0x180013c80`
- end: `0x180013cc4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013ad8`

## callees

- `0x180013c80`
- `0x180013ccc`

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
0x180013c80  sub     rsp, 28h
0x180013c84  cmp     cs:__security_cookie, 0
0x180013c8c  jz      short loc_180013CA1
0x180013c8e  mov     rax, 2B992DDFA232h
0x180013c98  cmp     cs:__security_cookie, rax
0x180013c9f  jnz     short loc_180013CAE
0x180013ca1  lea     rcx, __security_cookie
0x180013ca8  call    __security_init_cookie_ex
0x180013cad  nop
0x180013cae  mov     rax, cs:__security_cookie
0x180013cb5  not     rax
0x180013cb8  mov     cs:__security_cookie_complement, rax
0x180013cbf  add     rsp, 28h
0x180013cc3  retn
```

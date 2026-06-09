# __security_init_cookie

- ea: `0x140001620`
- end: `0x140001664`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007660`

## callees

- `0x140001620`
- `0x14000166c`

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
0x140001620  sub     rsp, 28h
0x140001624  cmp     cs:__security_cookie, 0
0x14000162c  jz      short loc_140001641
0x14000162e  mov     rax, 2B992DDFA232h
0x140001638  cmp     cs:__security_cookie, rax
0x14000163f  jnz     short loc_14000164E
0x140001641  lea     rcx, __security_cookie
0x140001648  call    __security_init_cookie_ex
0x14000164d  nop
0x14000164e  mov     rax, cs:__security_cookie
0x140001655  not     rax
0x140001658  mov     cs:__security_cookie_complement, rax
0x14000165f  add     rsp, 28h
0x140001663  retn
```

# __security_init_cookie

- ea: `0x140017044`
- end: `0x140017072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140017010`

## callees

- `0x140017044`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    __fastfail(6u);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x140017044  mov     rax, cs:__security_cookie
0x14001704b  test    rax, rax
0x14001704e  jz      short loc_14001706B
0x140017050  mov     rcx, 2B992DDFA232h
0x14001705a  cmp     rax, rcx
0x14001705d  jz      short loc_14001706B
0x14001705f  not     rax
0x140017062  mov     cs:__security_cookie_complement, rax
0x140017069  retn
0x14001706b  mov     ecx, 6
0x140017070  int     29h; Win8: RtlFailFast(ecx)
```

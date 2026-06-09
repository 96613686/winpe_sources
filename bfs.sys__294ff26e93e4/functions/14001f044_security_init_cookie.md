# __security_init_cookie

- ea: `0x14001f044`
- end: `0x14001f072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001f010`

## callees

- `0x14001f044`

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
0x14001f044  mov     rax, cs:__security_cookie
0x14001f04b  test    rax, rax
0x14001f04e  jz      short loc_14001F06B
0x14001f050  mov     rcx, 2B992DDFA232h
0x14001f05a  cmp     rax, rcx
0x14001f05d  jz      short loc_14001F06B
0x14001f05f  not     rax
0x14001f062  mov     cs:__security_cookie_complement, rax
0x14001f069  retn
0x14001f06b  mov     ecx, 6
0x14001f070  int     29h; Win8: RtlFailFast(ecx)
```

# __security_init_cookie

- ea: `0x18002e044`
- end: `0x18002e072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016204`
- `0x18002e010`

## callees

- `0x18002e044`

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
0x18002e044  mov     rax, cs:__security_cookie
0x18002e04b  test    rax, rax
0x18002e04e  jz      short loc_18002E06B
0x18002e050  mov     rcx, 2B992DDFA232h
0x18002e05a  cmp     rax, rcx
0x18002e05d  jz      short loc_18002E06B
0x18002e05f  not     rax
0x18002e062  mov     cs:__security_cookie_complement, rax
0x18002e069  retn
0x18002e06b  mov     ecx, 6
0x18002e070  int     29h; Win8: RtlFailFast(ecx)
```

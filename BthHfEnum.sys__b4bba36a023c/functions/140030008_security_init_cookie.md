# __security_init_cookie

- ea: `0x140030008`
- end: `0x140030036`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015790`

## callees

- `0x140030008`

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
0x140030008  mov     rax, cs:__security_cookie
0x14003000f  test    rax, rax
0x140030012  jz      short loc_14003002F
0x140030014  mov     rcx, 2B992DDFA232h
0x14003001e  cmp     rax, rcx
0x140030021  jz      short loc_14003002F
0x140030023  not     rax
0x140030026  mov     cs:__security_cookie_complement, rax
0x14003002d  retn
0x14003002f  mov     ecx, 6
0x140030034  int     29h; Win8: RtlFailFast(ecx)
```

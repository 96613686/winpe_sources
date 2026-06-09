# __security_init_cookie

- ea: `0x14001d008`
- end: `0x14001d036`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000be30`

## callees

- `0x14001d008`

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
0x14001d008  mov     rax, cs:__security_cookie
0x14001d00f  test    rax, rax
0x14001d012  jz      short loc_14001D02F
0x14001d014  mov     rcx, 2B992DDFA232h
0x14001d01e  cmp     rax, rcx
0x14001d021  jz      short loc_14001D02F
0x14001d023  not     rax
0x14001d026  mov     cs:__security_cookie_complement, rax
0x14001d02d  retn
0x14001d02f  mov     ecx, 6
0x14001d034  int     29h; Win8: RtlFailFast(ecx)
```

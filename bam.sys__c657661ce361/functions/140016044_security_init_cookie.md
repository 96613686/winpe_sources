# __security_init_cookie

- ea: `0x140016044`
- end: `0x140016072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140016010`

## callees

- `0x140016044`

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
0x140016044  mov     rax, cs:__security_cookie
0x14001604b  test    rax, rax
0x14001604e  jz      short loc_14001606B
0x140016050  mov     rcx, 2B992DDFA232h
0x14001605a  cmp     rax, rcx
0x14001605d  jz      short loc_14001606B
0x14001605f  not     rax
0x140016062  mov     cs:__security_cookie_complement, rax
0x140016069  retn
0x14001606b  mov     ecx, 6
0x140016070  int     29h; Win8: RtlFailFast(ecx)
```

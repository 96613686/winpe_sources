# __security_init_cookie

- ea: `0x140067008`
- end: `0x140067036`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140042040`

## callees

- `0x140067008`

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
0x140067008  mov     rax, cs:__security_cookie
0x14006700f  test    rax, rax
0x140067012  jz      short loc_14006702F
0x140067014  mov     rcx, 2B992DDFA232h
0x14006701e  cmp     rax, rcx
0x140067021  jz      short loc_14006702F
0x140067023  not     rax
0x140067026  mov     cs:__security_cookie_complement, rax
0x14006702d  retn
0x14006702f  mov     ecx, 6
0x140067034  int     29h; Win8: RtlFailFast(ecx)
```

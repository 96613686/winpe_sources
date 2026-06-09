# __security_check_cookie(x)

- ea: `0x40b3e3`
- end: `0x40b3f1`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x408220`
- `0x408306`
- `0x4087ac`
- `0x408ad2`
- `0x408d24`
- `0x408e31`
- `0x408f3a`
- `0x408ff9`
- `0x4090e0`
- `0x4091fd`
- `0x4092c3`
- `0x409375`
- `0x40949c`
- `0x4097aa`
- `0x4098ae`
- `0x409923`
- `0x4099f6`
- `0x409b18`
- `0x40a1cd`
- `0x40a274`
- `0x40ac17`
- `0x40aca2`
- `0x40c3c1`
- `0x40c77d`
- `0x40c9a0`
- `0x40d220`
- `0x40d6b0`
- `0x40dca8`
- `0x410078`
- `0x410354`
- `0x410760`
- `0x410afb`
- `0x4116ed`
- `0x412c0a`
- `0x412fe0`
- `0x4137a5`
- `0x413c2a`
- `0x413d05`
- `0x413dee`
- `0x4147b7`
- `0x415bbf`
- `0x415d11`

## callees

- `0x40b3e3`
- `0x40b419`

## pseudocode

```c
void __fastcall __security_check_cookie(uintptr_t StackCookie)
{
  if ( StackCookie != __security_cookie )
    __report_gsfailure();
}

```

## disassembly

```asm
0x40b3e3  cmp     ecx, ___security_cookie
0x40b3e9  jnz     short loc_40B3EC
0x40b3eb  retn
0x40b3ec  jmp     ___report_gsfailure
```

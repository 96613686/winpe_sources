# __security_check_cookie(x)

- ea: `0x40d08d`
- end: `0x40d09b`
- name: `@__security_check_cookie@4`
- size: `14`
- prototype: `void __fastcall(uintptr_t StackCookie)`
- caller_count: `143`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x401079`
- `0x401116`
- `0x401203`
- `0x401853`
- `0x4018e5`
- `0x4019cc`
- `0x401c67`
- `0x402488`
- `0x40255c`
- `0x4025ed`
- `0x402675`
- `0x4026d7`
- `0x40284a`
- `0x4029ea`
- `0x402a83`
- `0x402ad5`
- `0x402b86`
- `0x402c60`
- `0x402d9e`
- `0x402e3c`
- `0x403007`
- `0x403041`
- `0x403293`
- `0x40336f`
- `0x4035b2`
- `0x4039fd`
- `0x403b59`
- `0x403d00`
- `0x404008`
- `0x4040fb`
- `0x4042c0`
- `0x404458`
- `0x4044b7`
- `0x404782`
- `0x404866`
- `0x404994`
- `0x404a78`
- `0x404ad0`
- `0x404bf0`
- `0x404edf`
- `0x404f4a`
- `0x404fbe`
- `0x405054`
- `0x405120`
- `0x4054d6`
- `0x405ba1`
- `0x405cdb`
- `0x405d34`
- `0x405df0`
- `0x40607d`

## callees

- `0x40d08d`
- `0x40d772`

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
0x40d08d  cmp     ecx, ___security_cookie
0x40d093  jnz     short loc_40D096
0x40d095  retn
0x40d096  jmp     ___report_gsfailure
```

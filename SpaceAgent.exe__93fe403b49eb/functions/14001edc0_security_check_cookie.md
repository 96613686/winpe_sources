# __security_check_cookie

- ea: `0x14001edc0`
- end: `0x14001edde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `115`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000266c`
- `0x140002b98`
- `0x1400035c0`
- `0x140003bdc`
- `0x140003e78`
- `0x140004a3c`
- `0x140004ba4`
- `0x140004f00`
- `0x140005734`
- `0x140005ae8`
- `0x140006de8`
- `0x140006fcc`
- `0x1400076d4`
- `0x140008ba4`
- `0x140009754`
- `0x140009924`
- `0x140009a1c`
- `0x140009d10`
- `0x14000a440`
- `0x14000a8dc`
- `0x14000b39c`
- `0x14000b828`
- `0x14000b934`
- `0x14000ba08`
- `0x14000bb78`
- `0x14000c104`
- `0x14000c26c`
- `0x14000c590`
- `0x14000cf3c`
- `0x14000d29c`
- `0x14000d70c`
- `0x14000dbf4`
- `0x14000df58`
- `0x14000e018`
- `0x14000e158`
- `0x14000e298`
- `0x14000e3f8`
- `0x14000e860`
- `0x14000ecc8`
- `0x14000f0c4`
- `0x14000f450`
- `0x14000f6f8`
- `0x14000f818`
- `0x14000f8fc`
- `0x14000fa50`
- `0x14000fb94`
- `0x140010f8c`
- `0x140012ca0`
- `0x140012d38`
- `0x140012d94`

## callees

- `0x140001690`
- `0x14001edc0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14001edc0  cmp     rcx, cs:__security_cookie
0x14001edc7  jnz     short loc_14001EDD9
0x14001edc9  rol     rcx, 10h
0x14001edcd  test    cx, 0FFFFh
0x14001edd2  jnz     short loc_14001EDD5
0x14001edd4  retn
0x14001edd5  ror     rcx, 10h
0x14001edd9  jmp     __report_gsfailure
```

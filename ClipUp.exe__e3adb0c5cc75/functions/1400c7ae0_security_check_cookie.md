# __security_check_cookie

- ea: `0x1400c7ae0`
- end: `0x1400c7afe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400010ac`
- `0x140001158`
- `0x140001220`
- `0x140001288`
- `0x140001334`
- `0x140001540`
- `0x14000163c`
- `0x1400016b4`
- `0x140001750`
- `0x140001858`
- `0x140007864`
- `0x140007b1c`
- `0x140009130`
- `0x1400092a4`
- `0x14000a390`
- `0x14000b49c`
- `0x14000b774`
- `0x14000c57c`
- `0x14000cba4`
- `0x14000d664`
- `0x14000db58`
- `0x14000ea14`
- `0x14000ed68`
- `0x14000f2b0`
- `0x14000fb30`
- `0x1400104b0`
- `0x1400115f4`
- `0x140011ca0`
- `0x1400123f4`
- `0x140014888`
- `0x140015dec`
- `0x140016030`
- `0x140016704`
- `0x140016b9c`
- `0x14001f758`
- `0x140020124`
- `0x140024334`
- `0x140024578`
- `0x140024748`
- `0x140024ff4`
- `0x14002d5f4`
- `0x140032ec0`
- `0x1400363c0`
- `0x1400365ec`
- `0x14003aeec`
- `0x14003b108`
- `0x14003cca4`
- `0x14007c1a4`
- `0x14007c46c`

## callees

- `0x1400023b0`
- `0x1400c7ae0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_1400023B0(StackCookie);
}

```

## disassembly

```asm
0x1400c7ae0  cmp     rcx, cs:__security_cookie
0x1400c7ae7  jnz     short loc_1400C7AF9
0x1400c7ae9  rol     rcx, 10h
0x1400c7aed  test    cx, 0FFFFh
0x1400c7af2  jnz     short loc_1400C7AF5
0x1400c7af4  retn
0x1400c7af5  ror     rcx, 10h
0x1400c7af9  jmp     sub_1400023B0
```

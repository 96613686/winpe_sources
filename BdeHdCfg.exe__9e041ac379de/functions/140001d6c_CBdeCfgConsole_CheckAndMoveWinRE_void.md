# CBdeCfgConsole::CheckAndMoveWinRE(void)

- ea: `0x140001d6c`
- end: `0x140001db5`
- name: `?CheckAndMoveWinRE@CBdeCfgConsole@@AEAAJXZ`
- size: `73`
- prototype: `int __fastcall(CBdeCfgConsole *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001dbc`

## callees

- `0x140001d6c`

## import_xrefs

- `BDEHDCFGLIB!BdeCfgMoveWinRE` at `0x140001d97`
- `BDEHDCFGLIB!BdeCfgMoveWinRE` at `0x140001d97`
- `BDEHDCFGLIB!BdeCfgIsWinREOnOSVolume` at `0x140001d82`
- `BDEHDCFGLIB!BdeCfgIsWinREOnOSVolume` at `0x140001d82`

## pseudocode

```c
int __fastcall CBdeCfgConsole::CheckAndMoveWinRE(CBdeCfgConsole *this)
{
  int result; // eax
  int v2; // [rsp+40h] [rbp+8h] BYREF
  int v3; // [rsp+44h] [rbp+Ch]

  v3 = HIDWORD(this);
  v2 = 0;
  result = BdeCfgIsWinREOnOSVolume(&v2);
  if ( result >= 0 && v2 )
  {
    result = BdeCfgMoveWinRE();
    if ( result == 1 )
      return -1063256038;
  }
  return result;
}

```

## disassembly

```asm
0x140001d6c  mov     [rsp+arg_0], rcx
0x140001d71  sub     rsp, 38h
0x140001d75  mov     dword ptr [rsp+38h+arg_0], 0
0x140001d7d  lea     rcx, [rsp+38h+arg_0]
0x140001d82  call    cs:__imp_?BdeCfgIsWinREOnOSVolume@@YAJPEAH@Z; BdeCfgIsWinREOnOSVolume(int *)
0x140001d88  mov     [rsp+38h+var_18], eax
0x140001d8c  test    eax, eax
0x140001d8e  js      short loc_140001DB0
0x140001d90  cmp     dword ptr [rsp+38h+arg_0], 0
0x140001d95  jz      short loc_140001DB0
0x140001d97  call    cs:__imp_?BdeCfgMoveWinRE@@YAJXZ; BdeCfgMoveWinRE(void)
0x140001d9d  mov     [rsp+38h+var_18], eax
0x140001da1  mov     ecx, 0C0A0001Ah
0x140001da6  cmp     eax, 1
0x140001da9  cmovz   eax, ecx
0x140001dac  mov     [rsp+38h+var_18], eax
0x140001db0  add     rsp, 38h
0x140001db4  retn
0x140004604  push    rbp
0x140004606  sub     rsp, 20h
0x14000460a  mov     rbp, rdx
0x14000460d  add     rsp, 20h
0x140004611  pop     rbp
0x140004612  retn
```

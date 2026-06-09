# bDivByZeroCheck

- ea: `0x180045aa4`
- end: `0x180045adb`
- name: `bDivByZeroCheck`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b848`

## callees

- `0x180007220`
- `0x180045aa4`

## string_xrefs

- `0x180045aba`: `Command parameter: Explicit divide by zero detected.`

## pseudocode

```c
__int64 __fastcall bDivByZeroCheck(__int64 a1)
{
  if ( *(_DWORD *)(a1 + 4) != 7 || *(_DWORD *)(a1 - 4) || *(_DWORD *)(a1 - 8) )
    return 1;
  WriteDbgTraceErrorGpd((__int64)"bDivByZeroCheck", "Command parameter: Explicit divide by zero detected.");
  return 0;
}

```

## disassembly

```asm
0x180045aa4  sub     rsp, 28h
0x180045aa8  cmp     dword ptr [rcx+4], 7
0x180045aac  jnz     short loc_180045AD1
0x180045aae  cmp     dword ptr [rcx-4], 0
0x180045ab2  jnz     short loc_180045AD1
0x180045ab4  cmp     dword ptr [rcx-8], 0
0x180045ab8  jnz     short loc_180045AD1
0x180045aba  lea     rdx, aCommandParamet_11; "Command parameter: Explicit divide by z"...
0x180045ac1  lea     rcx, aBdivbyzerochec; "bDivByZeroCheck"
0x180045ac8  call    WriteDbgTraceErrorGpd
0x180045acd  xor     eax, eax
0x180045acf  jmp     short loc_180045AD6
0x180045ad1  mov     eax, 1
0x180045ad6  add     rsp, 28h
0x180045ada  retn
```

# wil::ProcessShutdownInProgress(void)

- ea: `0x180006868`
- end: `0x180006895`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800069bc`
- `0x1800088d4`
- `0x1800097e8`
- `0x1800098d4`
- `0x180009cc0`
- `0x18000a394`
- `0x18000ac30`
- `0x180017ce0`
- `0x180017d10`

## callees

- `0x180006868`
- `0x180018010`

## pseudocode

```c
bool __fastcall wil::ProcessShutdownInProgress(wil *this)
{
  return wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(this);
}

```

## disassembly

```asm
0x180006868  sub     rsp, 28h
0x18000686c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006873  jnz     short loc_18000688E
0x180006875  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000687c  test    rax, rax
0x18000687f  jz      short loc_18000688A
0x180006881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006886  test    al, al
0x180006888  jnz     short loc_18000688E
0x18000688a  xor     al, al
0x18000688c  jmp     short loc_180006890
0x18000688e  mov     al, 1
0x180006890  add     rsp, 28h
0x180006894  retn
```

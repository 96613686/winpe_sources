# wil::ProcessShutdownInProgress(void)

- ea: `0x18000b49c`
- end: `0x18000b4c9`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b8bc`
- `0x18000b9b0`
- `0x18000dcbc`
- `0x1800112e4`
- `0x180011364`
- `0x180011b1c`
- `0x180018a84`
- `0x18001ab30`
- `0x18001ab70`

## callees

- `0x18000b49c`
- `0x18001b010`

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
0x18000b49c  sub     rsp, 28h
0x18000b4a0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b4a7  jnz     short loc_18000B4C2
0x18000b4a9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b4b0  test    rax, rax
0x18000b4b3  jz      short loc_18000B4BE
0x18000b4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ba  test    al, al
0x18000b4bc  jnz     short loc_18000B4C2
0x18000b4be  xor     al, al
0x18000b4c0  jmp     short loc_18000B4C4
0x18000b4c2  mov     al, 1
0x18000b4c4  add     rsp, 28h
0x18000b4c8  retn
```

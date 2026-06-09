# wil::ProcessShutdownInProgress(void)

- ea: `0x1800063b0`
- end: `0x1800063dd`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003388`
- `0x18000340c`
- `0x180004b20`
- `0x1800064e4`
- `0x1800068ac`
- `0x180007f44`
- `0x1800098b0`

## callees

- `0x1800063b0`
- `0x18000a010`

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
0x1800063b0  sub     rsp, 28h
0x1800063b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800063bb  jnz     short loc_1800063D6
0x1800063bd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800063c4  test    rax, rax
0x1800063c7  jz      short loc_1800063D2
0x1800063c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ce  test    al, al
0x1800063d0  jnz     short loc_1800063D6
0x1800063d2  xor     al, al
0x1800063d4  jmp     short loc_1800063D8
0x1800063d6  mov     al, 1
0x1800063d8  add     rsp, 28h
0x1800063dc  retn
```

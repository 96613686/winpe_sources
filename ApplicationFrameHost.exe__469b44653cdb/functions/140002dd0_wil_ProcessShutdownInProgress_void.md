# wil::ProcessShutdownInProgress(void)

- ea: `0x140002dd0`
- end: `0x140002dfd`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005e84`
- `0x140007474`
- `0x140007744`
- `0x140007e88`
- `0x140007f08`
- `0x140008b88`

## callees

- `0x140002dd0`
- `0x14000b010`

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
0x140002dd0  sub     rsp, 28h
0x140002dd4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140002ddb  jnz     short loc_140002DF6
0x140002ddd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140002de4  test    rax, rax
0x140002de7  jz      short loc_140002DF2
0x140002de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002dee  test    al, al
0x140002df0  jnz     short loc_140002DF6
0x140002df2  xor     al, al
0x140002df4  jmp     short loc_140002DF8
0x140002df6  mov     al, 1
0x140002df8  add     rsp, 28h
0x140002dfc  retn
```

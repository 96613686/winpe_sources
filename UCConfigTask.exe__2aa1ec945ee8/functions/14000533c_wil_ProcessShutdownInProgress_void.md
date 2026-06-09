# wil::ProcessShutdownInProgress(void)

- ea: `0x14000533c`
- end: `0x140005369`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140002d38`
- `0x140003c24`
- `0x140005370`
- `0x14000572c`
- `0x140005e20`
- `0x1400068b4`
- `0x1400089a0`

## callees

- `0x14000533c`
- `0x140009010`

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
0x14000533c  sub     rsp, 28h
0x140005340  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140005347  jnz     short loc_140005362
0x140005349  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005350  test    rax, rax
0x140005353  jz      short loc_14000535E
0x140005355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000535a  test    al, al
0x14000535c  jnz     short loc_140005362
0x14000535e  xor     al, al
0x140005360  jmp     short loc_140005364
0x140005362  mov     al, 1
0x140005364  add     rsp, 28h
0x140005368  retn
```

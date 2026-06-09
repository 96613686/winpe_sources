# wil::ProcessShutdownInProgress(void)

- ea: `0x140001650`
- end: `0x14000167d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001a30`
- `0x140001b18`
- `0x1400045f4`
- `0x140005fa0`
- `0x140006020`
- `0x140006778`
- `0x140007a00`

## callees

- `0x140001650`
- `0x140008010`

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
0x140001650  sub     rsp, 28h
0x140001654  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000165b  jnz     short loc_140001676
0x14000165d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140001664  test    rax, rax
0x140001667  jz      short loc_140001672
0x140001669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000166e  test    al, al
0x140001670  jnz     short loc_140001676
0x140001672  xor     al, al
0x140001674  jmp     short loc_140001678
0x140001676  mov     al, 1
0x140001678  add     rsp, 28h
0x14000167c  retn
```

# wil::ProcessShutdownInProgress(void)

- ea: `0x18000d0b4`
- end: `0x18000d0e1`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d92c`
- `0x18000da14`
- `0x180010ef8`
- `0x180012eec`
- `0x180012f6c`
- `0x1800138f0`
- `0x180028630`
- `0x180028660`

## callees

- `0x18000d0b4`
- `0x180029010`

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
0x18000d0b4  sub     rsp, 28h
0x18000d0b8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d0bf  jnz     short loc_18000D0DA
0x18000d0c1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d0c8  test    rax, rax
0x18000d0cb  jz      short loc_18000D0D6
0x18000d0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0d2  test    al, al
0x18000d0d4  jnz     short loc_18000D0DA
0x18000d0d6  xor     al, al
0x18000d0d8  jmp     short loc_18000D0DC
0x18000d0da  mov     al, 1
0x18000d0dc  add     rsp, 28h
0x18000d0e0  retn
```

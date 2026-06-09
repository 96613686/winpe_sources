# wil::ProcessShutdownInProgress(void)

- ea: `0x1800065d4`
- end: `0x180006601`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800064b0`
- `0x180006590`
- `0x1800083d4`
- `0x18000b02c`
- `0x18000be04`
- `0x18000c1e4`
- `0x18000c264`

## callees

- `0x1800065d4`
- `0x18000e010`

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
0x1800065d4  sub     rsp, 28h
0x1800065d8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800065df  jnz     short loc_1800065FA
0x1800065e1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800065e8  test    rax, rax
0x1800065eb  jz      short loc_1800065F6
0x1800065ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065f2  test    al, al
0x1800065f4  jnz     short loc_1800065FA
0x1800065f6  xor     al, al
0x1800065f8  jmp     short loc_1800065FC
0x1800065fa  mov     al, 1
0x1800065fc  add     rsp, 28h
0x180006600  retn
```

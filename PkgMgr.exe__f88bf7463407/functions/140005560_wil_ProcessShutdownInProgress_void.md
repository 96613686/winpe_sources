# wil::ProcessShutdownInProgress(void)

- ea: `0x140005560`
- end: `0x14000558d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003cb0`
- `0x14000ee84`
- `0x14000f490`
- `0x14000f730`
- `0x14000fe98`
- `0x1400104b0`
- `0x140029ea0`

## callees

- `0x140005560`
- `0x14002a010`

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
0x140005560  sub     rsp, 28h
0x140005564  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000556b  jnz     short loc_140005586
0x14000556d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005574  test    rax, rax
0x140005577  jz      short loc_140005582
0x140005579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000557e  test    al, al
0x140005580  jnz     short loc_140005586
0x140005582  xor     al, al
0x140005584  jmp     short loc_140005588
0x140005586  mov     al, 1
0x140005588  add     rsp, 28h
0x14000558c  retn
```

# wil::ProcessShutdownInProgress(void)

- ea: `0x180005c40`
- end: `0x180005c6d`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000575c`
- `0x1800057b0`
- `0x1800057f4`
- `0x1800058c0`
- `0x180016ed4`

## callees

- `0x180005c40`
- `0x18001c010`

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
0x180005c40  sub     rsp, 28h
0x180005c44  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005c4b  jnz     short loc_180005C69
0x180005c4d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005c54  test    rax, rax
0x180005c57  jz      short loc_180005C62
0x180005c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c5e  test    al, al
0x180005c60  jnz     short loc_180005C69
0x180005c62  xor     al, al
0x180005c64  add     rsp, 28h
0x180005c68  retn
0x180005c69  mov     al, 1
0x180005c6b  jmp     short loc_180005C64
```

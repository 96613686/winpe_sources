# wil::ProcessShutdownInProgress(void)

- ea: `0x140003b84`
- end: `0x140003bb1`
- name: `?ProcessShutdownInProgress@wil@@YA_NXZ`
- size: `45`
- prototype: `bool __fastcall(wil *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003808`
- `0x140003950`
- `0x140007474`
- `0x140007a4c`
- `0x14000c180`
- `0x14000c3bc`
- `0x14000c43c`
- `0x14000f3e0`
- `0x14000f420`

## callees

- `0x140003b84`
- `0x140010010`

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
0x140003b84  sub     rsp, 28h
0x140003b88  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140003b8f  jnz     short loc_140003BAD
0x140003b91  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140003b98  test    rax, rax
0x140003b9b  jz      short loc_140003BA6
0x140003b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ba2  test    al, al
0x140003ba4  jnz     short loc_140003BAD
0x140003ba6  xor     al, al
0x140003ba8  add     rsp, 28h
0x140003bac  retn
0x140003bad  mov     al, 1
0x140003baf  jmp     short loc_140003BA8
```

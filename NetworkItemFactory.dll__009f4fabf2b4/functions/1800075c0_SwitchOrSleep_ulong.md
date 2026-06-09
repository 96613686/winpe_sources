# SwitchOrSleep(ulong)

- ea: `0x1800075c0`
- end: `0x1800075ea`
- name: `?SwitchOrSleep@@YAXK@Z`
- size: `42`
- prototype: `void __fastcall(DWORD dwMilliseconds)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075f0`
- `0x1800076c8`
- `0x1800077fc`

## callees

- `0x1800075c0`
- `0x18000b010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800075de`
- `KERNEL32!Sleep` at `0x1800075de`

## pseudocode

```c
void __fastcall SwitchOrSleep(DWORD dwMilliseconds)
{
  if ( dwMilliseconds || !g_pfnSwitchToThread() )
    Sleep(dwMilliseconds);
}

```

## disassembly

```asm
0x1800075c0  push    rbx
0x1800075c2  sub     rsp, 20h
0x1800075c6  mov     ebx, ecx
0x1800075c8  test    ecx, ecx
0x1800075ca  jnz     short loc_1800075DC
0x1800075cc  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x1800075d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d8  test    eax, eax
0x1800075da  jnz     short loc_1800075E4
0x1800075dc  mov     ecx, ebx; dwMilliseconds
0x1800075de  call    cs:__imp_Sleep
0x1800075e4  add     rsp, 20h
0x1800075e8  pop     rbx
0x1800075e9  retn
```

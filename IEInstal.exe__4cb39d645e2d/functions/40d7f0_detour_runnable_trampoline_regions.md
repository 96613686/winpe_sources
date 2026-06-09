# detour_runnable_trampoline_regions

- ea: `0x40d7f0`
- end: `0x40d830`
- name: `detour_runnable_trampoline_regions`
- size: `64`
- prototype: `HANDLE()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40de00`

## callees

- `0x40d7f0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x40d7f3`
- `KERNEL32!GetCurrentProcess` at `0x40d7f3`
- `KERNEL32!VirtualProtect` at `0x40d812`
- `KERNEL32!VirtualProtect` at `0x40d812`
- `KERNEL32!FlushInstructionCache` at `0x40d81f`
- `KERNEL32!FlushInstructionCache` at `0x40d81f`

## pseudocode

```c
HANDLE detour_runnable_trampoline_regions()
{
  HANDLE result; // eax
  _DWORD *v1; // esi
  void *v2; // edi
  DWORD flOldProtect; // [esp+8h] [ebp-4h] BYREF

  result = GetCurrentProcess();
  v1 = lpBaseAddress;
  v2 = result;
  if ( lpBaseAddress )
  {
    do
    {
      VirtualProtect(v1, 0x10000u, 0x20u, &flOldProtect);
      result = (HANDLE)FlushInstructionCache(v2, v1, 0x10000u);
      v1 = (_DWORD *)v1[1];
    }
    while ( v1 );
  }
  return result;
}

```

## disassembly

```asm
0x40d7f0  push    ecx
0x40d7f1  push    esi
0x40d7f2  push    edi
0x40d7f3  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40d7f9  mov     esi, lpBaseAddress
0x40d7ff  mov     edi, eax
0x40d801  test    esi, esi
0x40d803  jz      short loc_40D82C
0x40d805  lea     eax, [esp+0Ch+flOldProtect]
0x40d809  push    eax; lpflOldProtect
0x40d80a  push    20h ; ' '; flNewProtect
0x40d80c  push    10000h; dwSize
0x40d811  push    esi; lpAddress
0x40d812  call    ds:__imp__VirtualProtect@16; VirtualProtect(x,x,x,x)
0x40d818  push    10000h; dwSize
0x40d81d  push    esi; lpBaseAddress
0x40d81e  push    edi; hProcess
0x40d81f  call    ds:__imp__FlushInstructionCache@12; FlushInstructionCache(x,x,x)
0x40d825  mov     esi, [esi+4]
0x40d828  test    esi, esi
0x40d82a  jnz     short loc_40D805
0x40d82c  pop     edi
0x40d82d  pop     esi
0x40d82e  pop     ecx
0x40d82f  retn
```

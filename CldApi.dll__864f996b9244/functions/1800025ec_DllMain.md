# DllMain

- ea: `0x1800025ec`
- end: `0x180002626`
- name: `DllMain`
- size: `58`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800018f4`

## callees

- `0x1800025ec`
- `0x18001101c`
- `0x180011200`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000260e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000260e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      if ( !(unsigned __int8)GlobalInit(hinstDLL, fdwReason, lpvReserved) )
        return 0;
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    GlobalCleanup(hinstDLL, fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x1800025ec  push    rbx
0x1800025ee  sub     rsp, 20h
0x1800025f2  mov     rbx, rcx
0x1800025f5  test    edx, edx
0x1800025f7  jz      short loc_180002616
0x1800025f9  cmp     edx, 1
0x1800025fc  jnz     short loc_18000261B
0x1800025fe  call    GlobalInit
0x180002603  test    al, al
0x180002605  jnz     short loc_18000260B
0x180002607  xor     eax, eax
0x180002609  jmp     short loc_180002620
0x18000260b  mov     rcx, rbx; hLibModule
0x18000260e  call    cs:__imp_DisableThreadLibraryCalls
0x180002614  jmp     short loc_18000261B
0x180002616  call    GlobalCleanup
0x18000261b  mov     eax, 1
0x180002620  add     rsp, 20h
0x180002624  pop     rbx
0x180002625  retn
```

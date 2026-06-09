# DllMain(x,x,x)

- ea: `0x10007086`
- end: `0x100070ac`
- name: `_DllMain@12`
- size: `38`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x10010920`

## callees

- `0x10007086`
- `0x1000d4fe`
- `0x1000d50b`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
      sub_1000D50B(hinstDLL);
  }
  else
  {
    sub_1000D4FE();
  }
  return 1;
}

```

## disassembly

```asm
0x10007086  push    ebp
0x10007087  mov     ebp, esp
0x10007089  mov     eax, [ebp+fdwReason]
0x1000708c  sub     eax, 0
0x1000708f  jz      short loc_100070A0
0x10007091  sub     eax, 1
0x10007094  jnz     short loc_100070A5
0x10007096  push    [ebp+hinstDLL]
0x10007099  call    sub_1000D50B
0x1000709e  jmp     short loc_100070A5
0x100070a0  call    sub_1000D4FE
0x100070a5  xor     eax, eax
0x100070a7  inc     eax
0x100070a8  pop     ebp
0x100070a9  retn    0Ch
```

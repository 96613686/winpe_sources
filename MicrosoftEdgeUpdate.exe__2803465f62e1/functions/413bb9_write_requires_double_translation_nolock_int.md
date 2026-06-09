# write_requires_double_translation_nolock(int)

- ea: `0x413bb9`
- end: `0x413c2a`
- name: `?write_requires_double_translation_nolock@@YA_NH@Z`
- size: `113`
- prototype: `bool __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x414012`

## callees

- `0x40f9a9`
- `0x413bb9`
- `0x4142d7`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x413c16`
- `KERNEL32!GetConsoleMode` at `0x413c16`

## pseudocode

```c
bool __cdecl write_requires_double_translation_nolock(int FileHandle)
{
  int v1; // edi
  int v2; // esi
  bool result; // al
  DWORD Mode; // [esp+8h] [ebp-4h] BYREF

  result = _isatty(FileHandle)
        && (v1 = FileHandle >> 6, v2 = 56 * (FileHandle & 0x3F), *(char *)(dword_4181B0[FileHandle >> 6] + v2 + 40) < 0)
        && (*(_DWORD *)(*(_DWORD *)(__acrt_getptd() + 76) + 168) || *(_BYTE *)(dword_4181B0[v1] + v2 + 41))
        && GetConsoleMode(*(HANDLE *)(dword_4181B0[v1] + v2 + 24), &Mode);
  return result;
}

```

## disassembly

```asm
0x413bb9  mov     edi, edi
0x413bbb  push    ebp
0x413bbc  mov     ebp, esp
0x413bbe  push    ecx
0x413bbf  push    esi
0x413bc0  mov     esi, [ebp+FileHandle]
0x413bc3  push    edi
0x413bc4  push    esi; FileHandle
0x413bc5  call    __isatty
0x413bca  pop     ecx
0x413bcb  test    eax, eax
0x413bcd  jz      short loc_413C24
0x413bcf  mov     edi, esi
0x413bd1  and     esi, 3Fh
0x413bd4  sar     edi, 6
0x413bd7  imul    esi, 38h ; '8'
0x413bda  mov     eax, dword_4181B0[edi*4]
0x413be1  cmp     byte ptr [eax+esi+28h], 0
0x413be6  jge     short loc_413C24
0x413be8  call    ___acrt_getptd
0x413bed  mov     eax, [eax+4Ch]
0x413bf0  cmp     dword ptr [eax+0A8h], 0
0x413bf7  jnz     short loc_413C07
0x413bf9  mov     eax, dword_4181B0[edi*4]
0x413c00  cmp     byte ptr [eax+esi+29h], 0
0x413c05  jz      short loc_413C24
0x413c07  lea     eax, [ebp+Mode]
0x413c0a  push    eax; lpMode
0x413c0b  mov     eax, dword_4181B0[edi*4]
0x413c12  push    dword ptr [eax+esi+18h]; hConsoleHandle
0x413c16  call    ds:GetConsoleMode
0x413c1c  test    eax, eax
0x413c1e  jz      short loc_413C24
0x413c20  mov     al, 1
0x413c22  jmp     short loc_413C26
0x413c24  xor     al, al
0x413c26  pop     edi
0x413c27  pop     esi
0x413c28  leave
0x413c29  retn
```

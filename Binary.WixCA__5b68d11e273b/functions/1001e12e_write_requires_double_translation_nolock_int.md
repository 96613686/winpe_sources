# write_requires_double_translation_nolock(int)

- ea: `0x1001e12e`
- end: `0x1001e1a1`
- name: `?write_requires_double_translation_nolock@@YA_NH@Z`
- size: `115`
- prototype: `bool __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1001e585`

## callees

- `0x1001721d`
- `0x1001d215`
- `0x1001e12e`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x1001e18b`
- `KERNEL32!GetConsoleMode` at `0x1001e18b`

## pseudocode

```c
bool __cdecl write_requires_double_translation_nolock(int FileHandle)
{
  int v1; // edi
  int v2; // esi
  bool result; // al
  DWORD Mode; // [esp+8h] [ebp-4h] BYREF

  result = _isatty(FileHandle)
        && (v1 = FileHandle >> 6, v2 = 56 * (FileHandle & 0x3F),
                                  *(char *)(dword_10034F30[FileHandle >> 6] + v2 + 40) < 0)
        && (*(_DWORD *)(*(_DWORD *)(__acrt_getptd() + 76) + 168) || *(_BYTE *)(dword_10034F30[v1] + v2 + 41))
        && GetConsoleMode(*(HANDLE *)(dword_10034F30[v1] + v2 + 24), &Mode);
  return result;
}

```

## disassembly

```asm
0x1001e12e  mov     edi, edi
0x1001e130  push    ebp
0x1001e131  mov     ebp, esp
0x1001e133  push    ecx
0x1001e134  push    esi
0x1001e135  mov     esi, [ebp+FileHandle]
0x1001e138  push    edi
0x1001e139  push    esi; FileHandle
0x1001e13a  call    __isatty
0x1001e13f  pop     ecx
0x1001e140  test    eax, eax
0x1001e142  jz      short loc_1001E199
0x1001e144  mov     edi, esi
0x1001e146  and     esi, 3Fh
0x1001e149  sar     edi, 6
0x1001e14c  imul    esi, 38h ; '8'
0x1001e14f  mov     eax, dword_10034F30[edi*4]
0x1001e156  cmp     byte ptr [eax+esi+28h], 0
0x1001e15b  jge     short loc_1001E199
0x1001e15d  call    ___acrt_getptd
0x1001e162  mov     eax, [eax+4Ch]
0x1001e165  cmp     dword ptr [eax+0A8h], 0
0x1001e16c  jnz     short loc_1001E17C
0x1001e16e  mov     eax, dword_10034F30[edi*4]
0x1001e175  cmp     byte ptr [eax+esi+29h], 0
0x1001e17a  jz      short loc_1001E199
0x1001e17c  lea     eax, [ebp+Mode]
0x1001e17f  push    eax; lpMode
0x1001e180  mov     eax, dword_10034F30[edi*4]
0x1001e187  push    dword ptr [eax+esi+18h]; hConsoleHandle
0x1001e18b  call    ds:GetConsoleMode
0x1001e191  test    eax, eax
0x1001e193  jz      short loc_1001E199
0x1001e195  mov     al, 1
0x1001e197  jmp     short loc_1001E19B
0x1001e199  xor     al, al
0x1001e19b  pop     edi
0x1001e19c  pop     esi
0x1001e19d  mov     esp, ebp
0x1001e19f  pop     ebp
0x1001e1a0  retn
```

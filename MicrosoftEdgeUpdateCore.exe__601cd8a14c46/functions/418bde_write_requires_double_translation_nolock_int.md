# write_requires_double_translation_nolock(int)

- ea: `0x418bde`
- end: `0x418c4f`
- name: `?write_requires_double_translation_nolock@@YA_NH@Z`
- size: `113`
- prototype: `bool __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x419037`

## callees

- `0x413a39`
- `0x418bde`
- `0x4192fc`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x418c3b`
- `KERNEL32!GetConsoleMode` at `0x418c3b`

## pseudocode

```c
bool __cdecl write_requires_double_translation_nolock(int FileHandle)
{
  int v1; // edi
  int v2; // esi
  bool result; // al
  DWORD Mode; // [esp+8h] [ebp-4h] BYREF

  result = _isatty(FileHandle)
        && (v1 = FileHandle >> 6, v2 = 56 * (FileHandle & 0x3F), *(char *)(dword_43E588[FileHandle >> 6] + v2 + 40) < 0)
        && (*(_DWORD *)(*(_DWORD *)(__acrt_getptd() + 76) + 168) || *(_BYTE *)(dword_43E588[v1] + v2 + 41))
        && GetConsoleMode(*(HANDLE *)(dword_43E588[v1] + v2 + 24), &Mode);
  return result;
}

```

## disassembly

```asm
0x418bde  mov     edi, edi
0x418be0  push    ebp
0x418be1  mov     ebp, esp
0x418be3  push    ecx
0x418be4  push    esi
0x418be5  mov     esi, [ebp+FileHandle]
0x418be8  push    edi
0x418be9  push    esi; FileHandle
0x418bea  call    __isatty
0x418bef  pop     ecx
0x418bf0  test    eax, eax
0x418bf2  jz      short loc_418C49
0x418bf4  mov     edi, esi
0x418bf6  and     esi, 3Fh
0x418bf9  sar     edi, 6
0x418bfc  imul    esi, 38h ; '8'
0x418bff  mov     eax, dword_43E588[edi*4]
0x418c06  cmp     byte ptr [eax+esi+28h], 0
0x418c0b  jge     short loc_418C49
0x418c0d  call    ___acrt_getptd
0x418c12  mov     eax, [eax+4Ch]
0x418c15  cmp     dword ptr [eax+0A8h], 0
0x418c1c  jnz     short loc_418C2C
0x418c1e  mov     eax, dword_43E588[edi*4]
0x418c25  cmp     byte ptr [eax+esi+29h], 0
0x418c2a  jz      short loc_418C49
0x418c2c  lea     eax, [ebp+Mode]
0x418c2f  push    eax; lpMode
0x418c30  mov     eax, dword_43E588[edi*4]
0x418c37  push    dword ptr [eax+esi+18h]; hConsoleHandle
0x418c3b  call    ds:GetConsoleMode
0x418c41  test    eax, eax
0x418c43  jz      short loc_418C49
0x418c45  mov     al, 1
0x418c47  jmp     short loc_418C4B
0x418c49  xor     al, al
0x418c4b  pop     edi
0x418c4c  pop     esi
0x418c4d  leave
0x418c4e  retn
```

# write_requires_double_translation_nolock(int)

- ea: `0x414219`
- end: `0x41428a`
- name: `?write_requires_double_translation_nolock@@YA_NH@Z`
- size: `113`
- prototype: `bool __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x414672`

## callees

- `0x40e819`
- `0x414219`
- `0x414937`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x414276`
- `KERNEL32!GetConsoleMode` at `0x414276`

## pseudocode

```c
bool __cdecl write_requires_double_translation_nolock(int FileHandle)
{
  int v1; // edi
  int v2; // esi
  bool result; // al
  DWORD Mode; // [esp+8h] [ebp-4h] BYREF

  result = _isatty(FileHandle)
        && (v1 = FileHandle >> 6, v2 = 56 * (FileHandle & 0x3F), *(char *)(dword_427018[FileHandle >> 6] + v2 + 40) < 0)
        && (*(_DWORD *)(*(_DWORD *)(__acrt_getptd() + 76) + 168) || *(_BYTE *)(dword_427018[v1] + v2 + 41))
        && GetConsoleMode(*(HANDLE *)(dword_427018[v1] + v2 + 24), &Mode);
  return result;
}

```

## disassembly

```asm
0x414219  mov     edi, edi
0x41421b  push    ebp
0x41421c  mov     ebp, esp
0x41421e  push    ecx
0x41421f  push    esi
0x414220  mov     esi, [ebp+FileHandle]
0x414223  push    edi
0x414224  push    esi; FileHandle
0x414225  call    __isatty
0x41422a  pop     ecx
0x41422b  test    eax, eax
0x41422d  jz      short loc_414284
0x41422f  mov     edi, esi
0x414231  and     esi, 3Fh
0x414234  sar     edi, 6
0x414237  imul    esi, 38h ; '8'
0x41423a  mov     eax, dword_427018[edi*4]
0x414241  cmp     byte ptr [eax+esi+28h], 0
0x414246  jge     short loc_414284
0x414248  call    ___acrt_getptd
0x41424d  mov     eax, [eax+4Ch]
0x414250  cmp     dword ptr [eax+0A8h], 0
0x414257  jnz     short loc_414267
0x414259  mov     eax, dword_427018[edi*4]
0x414260  cmp     byte ptr [eax+esi+29h], 0
0x414265  jz      short loc_414284
0x414267  lea     eax, [ebp+Mode]
0x41426a  push    eax; lpMode
0x41426b  mov     eax, dword_427018[edi*4]
0x414272  push    dword ptr [eax+esi+18h]; hConsoleHandle
0x414276  call    ds:GetConsoleMode
0x41427c  test    eax, eax
0x41427e  jz      short loc_414284
0x414280  mov     al, 1
0x414282  jmp     short loc_414286
0x414284  xor     al, al
0x414286  pop     edi
0x414287  pop     esi
0x414288  leave
0x414289  retn
```

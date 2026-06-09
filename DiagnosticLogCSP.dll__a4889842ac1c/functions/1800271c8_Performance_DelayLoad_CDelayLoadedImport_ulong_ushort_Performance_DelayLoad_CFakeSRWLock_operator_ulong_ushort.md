# Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)

- ea: `0x1800271c8`
- end: `0x180027252`
- name: `??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ`
- size: `138`
- prototype: `FARPROC __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800274b4`
- `0x18002a358`
- `0x18002b24c`
- `0x18002bccc`
- `0x18002c210`
- `0x18002c860`
- `0x18002fee0`

## callees

- `0x1800271c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027201`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002721d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027201`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002721d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027234`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
FARPROC __fastcall Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(__int64 *a1)
{
  FARPROC result; // rax
  __int64 v3; // rdi
  const CHAR *v4; // rsi
  HMODULE Library; // rax
  const WCHAR *v6; // rcx

  if ( *((_BYTE *)a1 + 24) )
    return (FARPROC)a1[2];
  v3 = *a1;
  v4 = (const CHAR *)a1[1];
  if ( *(_BYTE *)(*a1 + 24) )
  {
    Library = *(HMODULE *)v3;
  }
  else
  {
    Library = LoadLibraryExW(*(LPCWSTR *)(v3 + 8), 0, 0);
    *(_QWORD *)v3 = Library;
    if ( !Library )
    {
      v6 = *(const WCHAR **)(v3 + 16);
      if ( v6 )
      {
        Library = LoadLibraryExW(v6, 0, 0);
        *(_QWORD *)v3 = Library;
      }
      else
      {
        Library = 0;
      }
    }
    *(_BYTE *)(v3 + 24) = 1;
  }
  result = GetProcAddress(Library, v4);
  a1[2] = (__int64)result;
  *((_BYTE *)a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800271c8  mov     [rsp+arg_0], rbx
0x1800271cd  mov     [rsp+arg_8], rsi
0x1800271d2  push    rdi
0x1800271d3  sub     rsp, 20h
0x1800271d7  cmp     byte ptr [rcx+18h], 0
0x1800271db  mov     rbx, rcx
0x1800271de  jz      short loc_1800271E6
0x1800271e0  mov     rax, [rcx+10h]
0x1800271e4  jmp     short loc_180027242
0x1800271e6  mov     rdi, [rcx]
0x1800271e9  mov     rsi, [rcx+8]
0x1800271ed  cmp     byte ptr [rdi+18h], 0
0x1800271f1  jz      short loc_1800271F8
0x1800271f3  mov     rax, [rdi]
0x1800271f6  jmp     short loc_18002722E
0x1800271f8  mov     rcx, [rdi+8]; lpLibFileName
0x1800271fc  xor     r8d, r8d; dwFlags
0x1800271ff  xor     edx, edx; hFile
0x180027201  call    cs:__imp_LoadLibraryExW
0x180027207  mov     [rdi], rax
0x18002720a  test    rax, rax
0x18002720d  jnz     short loc_18002722A
0x18002720f  mov     rcx, [rdi+10h]; lpLibFileName
0x180027213  test    rcx, rcx
0x180027216  jz      short loc_180027228
0x180027218  xor     r8d, r8d; dwFlags
0x18002721b  xor     edx, edx; hFile
0x18002721d  call    cs:__imp_LoadLibraryExW
0x180027223  mov     [rdi], rax
0x180027226  jmp     short loc_18002722A
0x180027228  xor     eax, eax
0x18002722a  mov     byte ptr [rdi+18h], 1
0x18002722e  mov     rdx, rsi; lpProcName
0x180027231  mov     rcx, rax; hModule
0x180027234  call    cs:__imp_GetProcAddress
0x18002723a  mov     [rbx+10h], rax
0x18002723e  mov     byte ptr [rbx+18h], 1
0x180027242  mov     rbx, [rsp+28h+arg_0]
0x180027247  mov     rsi, [rsp+28h+arg_8]
0x18002724c  add     rsp, 20h
0x180027250  pop     rdi
0x180027251  retn
```

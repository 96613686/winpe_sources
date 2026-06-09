# Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)

- ea: `0x18002834c`
- end: `0x1800283e9`
- name: `??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ`
- size: `157`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180028664`
- `0x18002b5d8`
- `0x18002c520`
- `0x18002cfe4`
- `0x18002d540`
- `0x18002db90`
- `0x180031360`

## callees

- `0x18002834c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028385`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800283a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028385`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800283a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800283c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800283c4`

## pseudocode

```c
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
0x18002834c  mov     [rsp+arg_0], rbx
0x180028351  mov     [rsp+arg_8], rsi
0x180028356  push    rdi
0x180028357  sub     rsp, 20h
0x18002835b  cmp     byte ptr [rcx+18h], 0
0x18002835f  mov     rbx, rcx
0x180028362  jz      short loc_18002836A
0x180028364  mov     rax, [rcx+10h]
0x180028368  jmp     short loc_1800283D8
0x18002836a  mov     rdi, [rcx]
0x18002836d  mov     rsi, [rcx+8]
0x180028371  cmp     byte ptr [rdi+18h], 0
0x180028375  jz      short loc_18002837C
0x180028377  mov     rax, [rdi]
0x18002837a  jmp     short loc_1800283BE
0x18002837c  mov     rcx, [rdi+8]; lpLibFileName
0x180028380  xor     r8d, r8d; dwFlags
0x180028383  xor     edx, edx; hFile
0x180028385  call    cs:__imp_LoadLibraryExW
0x18002838c  nop     dword ptr [rax+rax+00h]
0x180028391  mov     [rdi], rax
0x180028394  test    rax, rax
0x180028397  jnz     short loc_1800283BA
0x180028399  mov     rcx, [rdi+10h]; lpLibFileName
0x18002839d  test    rcx, rcx
0x1800283a0  jz      short loc_1800283B8
0x1800283a2  xor     r8d, r8d; dwFlags
0x1800283a5  xor     edx, edx; hFile
0x1800283a7  call    cs:__imp_LoadLibraryExW
0x1800283ae  nop     dword ptr [rax+rax+00h]
0x1800283b3  mov     [rdi], rax
0x1800283b6  jmp     short loc_1800283BA
0x1800283b8  xor     eax, eax
0x1800283ba  mov     byte ptr [rdi+18h], 1
0x1800283be  mov     rdx, rsi; lpProcName
0x1800283c1  mov     rcx, rax; hModule
0x1800283c4  call    cs:__imp_GetProcAddress
0x1800283cb  nop     dword ptr [rax+rax+00h]
0x1800283d0  mov     [rbx+10h], rax
0x1800283d4  mov     byte ptr [rbx+18h], 1
0x1800283d8  mov     rbx, [rsp+28h+arg_0]
0x1800283dd  mov     rsi, [rsp+28h+arg_8]
0x1800283e2  add     rsp, 20h
0x1800283e6  pop     rdi
0x1800283e7  retn
```

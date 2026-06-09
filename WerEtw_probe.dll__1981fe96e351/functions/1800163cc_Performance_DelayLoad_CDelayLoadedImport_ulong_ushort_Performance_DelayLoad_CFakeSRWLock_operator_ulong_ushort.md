# Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)

- ea: `0x1800163cc`
- end: `0x180016456`
- name: `??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800166b4`
- `0x180019558`
- `0x18001af8c`
- `0x18001c584`
- `0x18001da60`
- `0x18001e0b0`
- `0x180022930`

## callees

- `0x1800163cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016405`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016421`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016405`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016438`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016438`

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
0x1800163cc  mov     [rsp+arg_0], rbx
0x1800163d1  mov     [rsp+arg_8], rsi
0x1800163d6  push    rdi
0x1800163d7  sub     rsp, 20h
0x1800163db  cmp     byte ptr [rcx+18h], 0
0x1800163df  mov     rbx, rcx
0x1800163e2  jz      short loc_1800163EA
0x1800163e4  mov     rax, [rcx+10h]
0x1800163e8  jmp     short loc_180016446
0x1800163ea  mov     rdi, [rcx]
0x1800163ed  mov     rsi, [rcx+8]
0x1800163f1  cmp     byte ptr [rdi+18h], 0
0x1800163f5  jz      short loc_1800163FC
0x1800163f7  mov     rax, [rdi]
0x1800163fa  jmp     short loc_180016432
0x1800163fc  mov     rcx, [rdi+8]; lpLibFileName
0x180016400  xor     r8d, r8d; dwFlags
0x180016403  xor     edx, edx; hFile
0x180016405  call    cs:__imp_LoadLibraryExW
0x18001640b  mov     [rdi], rax
0x18001640e  test    rax, rax
0x180016411  jnz     short loc_18001642E
0x180016413  mov     rcx, [rdi+10h]; lpLibFileName
0x180016417  test    rcx, rcx
0x18001641a  jz      short loc_18001642C
0x18001641c  xor     r8d, r8d; dwFlags
0x18001641f  xor     edx, edx; hFile
0x180016421  call    cs:__imp_LoadLibraryExW
0x180016427  mov     [rdi], rax
0x18001642a  jmp     short loc_18001642E
0x18001642c  xor     eax, eax
0x18001642e  mov     byte ptr [rdi+18h], 1
0x180016432  mov     rdx, rsi; lpProcName
0x180016435  mov     rcx, rax; hModule
0x180016438  call    cs:__imp_GetProcAddress
0x18001643e  mov     [rbx+10h], rax
0x180016442  mov     byte ptr [rbx+18h], 1
0x180016446  mov     rbx, [rsp+28h+arg_0]
0x18001644b  mov     rsi, [rsp+28h+arg_8]
0x180016450  add     rsp, 20h
0x180016454  pop     rdi
0x180016455  retn
```

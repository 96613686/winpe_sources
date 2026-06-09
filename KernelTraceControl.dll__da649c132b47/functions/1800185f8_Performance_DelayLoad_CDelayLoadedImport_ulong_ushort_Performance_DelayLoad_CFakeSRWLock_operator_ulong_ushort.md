# Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)

- ea: `0x1800185f8`
- end: `0x18001866c`
- name: `??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180017354`
- `0x180017710`
- `0x180017b30`
- `0x18001818c`
- `0x18001bc08`

## callees

- `0x1800185f8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180018653`
- `KERNEL32!GetProcAddress` at `0x180018653`
- `KERNEL32!LoadLibraryExW` at `0x180018623`
- `KERNEL32!LoadLibraryExW` at `0x18001863f`
- `KERNEL32!LoadLibraryExW` at `0x180018623`
- `KERNEL32!LoadLibraryExW` at `0x18001863f`

## pseudocode

```c
FARPROC __fastcall Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(__int64 *a1)
{
  FARPROC result; // rax
  __int64 v3; // rdi
  HMODULE Library; // rax
  const WCHAR *v5; // rcx

  if ( *((_BYTE *)a1 + 24) )
    return (FARPROC)a1[2];
  v3 = *a1;
  if ( !*(_BYTE *)(*a1 + 24) )
  {
    Library = LoadLibraryExW(*(LPCWSTR *)(v3 + 8), 0, 0);
    *(_QWORD *)v3 = Library;
    if ( !Library )
    {
      v5 = *(const WCHAR **)(v3 + 16);
      if ( v5 )
        *(_QWORD *)v3 = LoadLibraryExW(v5, 0, 0);
    }
    *(_BYTE *)(v3 + 24) = 1;
  }
  result = GetProcAddress(*(HMODULE *)v3, (LPCSTR)a1[1]);
  a1[2] = (__int64)result;
  *((_BYTE *)a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800185f8  mov     [rsp+arg_0], rbx
0x1800185fd  push    rdi
0x1800185fe  sub     rsp, 20h
0x180018602  cmp     byte ptr [rcx+18h], 0
0x180018606  mov     rbx, rcx
0x180018609  jz      short loc_180018611
0x18001860b  mov     rax, [rcx+10h]
0x18001860f  jmp     short loc_180018661
0x180018611  mov     rdi, [rcx]
0x180018614  cmp     byte ptr [rdi+18h], 0
0x180018618  jnz     short loc_18001864C
0x18001861a  mov     rcx, [rdi+8]; lpLibFileName
0x18001861e  xor     r8d, r8d; dwFlags
0x180018621  xor     edx, edx; hFile
0x180018623  call    cs:__imp_LoadLibraryExW
0x180018629  mov     [rdi], rax
0x18001862c  test    rax, rax
0x18001862f  jnz     short loc_180018648
0x180018631  mov     rcx, [rdi+10h]; lpLibFileName
0x180018635  test    rcx, rcx
0x180018638  jz      short loc_180018648
0x18001863a  xor     r8d, r8d; dwFlags
0x18001863d  xor     edx, edx; hFile
0x18001863f  call    cs:__imp_LoadLibraryExW
0x180018645  mov     [rdi], rax
0x180018648  mov     byte ptr [rdi+18h], 1
0x18001864c  mov     rdx, [rbx+8]; lpProcName
0x180018650  mov     rcx, [rdi]; hModule
0x180018653  call    cs:__imp_GetProcAddress
0x180018659  mov     [rbx+10h], rax
0x18001865d  mov     byte ptr [rbx+18h], 1
0x180018661  mov     rbx, [rsp+28h+arg_0]
0x180018666  add     rsp, 20h
0x18001866a  pop     rdi
0x18001866b  retn
```

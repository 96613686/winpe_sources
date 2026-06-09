# Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(void)

- ea: `0x18004b314`
- end: `0x18004b364`
- name: `??B?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAPEAUHINSTANCE__@@XZ`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009b40`
- `0x180067a68`
- `0x1800723e4`

## callees

- `0x18004b314`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18004b331`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18004b34d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18004b331`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18004b34d`

## pseudocode

```c
HMODULE __fastcall Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(
        __int64 a1)
{
  HMODULE result; // rax
  const WCHAR *v3; // rcx

  if ( *(_BYTE *)(a1 + 24) )
    return *(HMODULE *)a1;
  result = LoadLibraryExW(*(LPCWSTR *)(a1 + 8), 0, 0);
  *(_QWORD *)a1 = result;
  if ( !result )
  {
    v3 = *(const WCHAR **)(a1 + 16);
    if ( v3 )
    {
      result = LoadLibraryExW(v3, 0, 0);
      *(_QWORD *)a1 = result;
    }
    else
    {
      result = 0;
    }
  }
  *(_BYTE *)(a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18004b314  push    rbx
0x18004b316  sub     rsp, 20h
0x18004b31a  cmp     byte ptr [rcx+18h], 0
0x18004b31e  mov     rbx, rcx
0x18004b321  jz      short loc_18004B328
0x18004b323  mov     rax, [rcx]
0x18004b326  jmp     short loc_18004B35E
0x18004b328  mov     rcx, [rcx+8]; lpLibFileName
0x18004b32c  xor     r8d, r8d; dwFlags
0x18004b32f  xor     edx, edx; hFile
0x18004b331  call    cs:__imp_LoadLibraryExW
0x18004b337  mov     [rbx], rax
0x18004b33a  test    rax, rax
0x18004b33d  jnz     short loc_18004B35A
0x18004b33f  mov     rcx, [rbx+10h]; lpLibFileName
0x18004b343  test    rcx, rcx
0x18004b346  jz      short loc_18004B358
0x18004b348  xor     r8d, r8d; dwFlags
0x18004b34b  xor     edx, edx; hFile
0x18004b34d  call    cs:__imp_LoadLibraryExW
0x18004b353  mov     [rbx], rax
0x18004b356  jmp     short loc_18004B35A
0x18004b358  xor     eax, eax
0x18004b35a  mov     byte ptr [rbx+18h], 1
0x18004b35e  add     rsp, 20h
0x18004b362  pop     rbx
0x18004b363  retn
```

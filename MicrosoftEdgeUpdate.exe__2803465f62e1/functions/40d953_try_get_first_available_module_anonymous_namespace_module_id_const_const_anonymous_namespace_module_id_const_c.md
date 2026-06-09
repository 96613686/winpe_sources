# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x40d953`
- end: `0x40d9ee`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z`
- size: `155`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40d9ee`

## callees

- `0x40d953`
- `0x40f5e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40d994`
- `KERNEL32!GetLastError` at `0x40d994`
- `KERNEL32!FreeLibrary` at `0x40d9e4`
- `KERNEL32!FreeLibrary` at `0x40d9e4`
- `KERNEL32!LoadLibraryExW` at `0x40d988`
- `KERNEL32!LoadLibraryExW` at `0x40d9bb`
- `KERNEL32!LoadLibraryExW` at `0x40d988`
- `KERNEL32!LoadLibraryExW` at `0x40d9bb`

## pseudocode

```c
HMODULE __cdecl try_get_first_available_module(_DWORD *a1, _DWORD *a2)
{
  int *v3; // ebx
  HMODULE Library; // esi
  const WCHAR *lpLibFileName; // [esp+Ch] [ebp-4h]

  while ( 1 )
  {
    if ( a1 == a2 )
      return 0;
    v3 = &dword_417D9C[*a1];
    Library = (HMODULE)*v3;
    if ( !*v3 )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_10:
    ++a1;
  }
  lpLibFileName = (&::lpLibFileName)[*a1];
  Library = LoadLibraryExW(lpLibFileName, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(lpLibFileName, L"api-ms-", 7u)
     || (Library = LoadLibraryExW(lpLibFileName, 0, 0)) == 0) )
  {
    _InterlockedExchange(v3, -1);
    goto LABEL_10;
  }
  if ( _InterlockedExchange(v3, (__int32)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x40d953  push    ebp
0x40d954  mov     ebp, esp
0x40d956  push    ecx
0x40d957  push    ebx
0x40d958  push    esi
0x40d959  push    edi
0x40d95a  mov     edi, [ebp+arg_0]
0x40d95d  jmp     short loc_40D9CF
0x40d95f  mov     eax, [edi]
0x40d961  lea     ebx, dword_417D9C[eax*4]
0x40d968  mov     esi, [ebx]
0x40d96a  nop
0x40d96b  test    esi, esi
0x40d96d  jz      short loc_40D976
0x40d96f  cmp     esi, 0FFFFFFFFh
0x40d972  jnz     short loc_40D9EA
0x40d974  jmp     short loc_40D9CC
0x40d976  mov     eax, ds:lpLibFileName[eax*4]
0x40d97d  push    800h; dwFlags
0x40d982  push    0; hFile
0x40d984  push    eax; lpLibFileName
0x40d985  mov     [ebp+lpLibFileName], eax
0x40d988  call    ds:LoadLibraryExW
0x40d98e  mov     esi, eax
0x40d990  test    esi, esi
0x40d992  jnz     short loc_40D9DB
0x40d994  call    ds:GetLastError
0x40d99a  cmp     eax, 57h ; 'W'
0x40d99d  jnz     short loc_40D9C7
0x40d99f  mov     esi, [ebp+lpLibFileName]
0x40d9a2  push    7; MaxCount
0x40d9a4  push    offset aApiMs
0x40d9a9  push    esi; String1
0x40d9aa  call    _wcsncmp
0x40d9af  add     esp, 0Ch
0x40d9b2  test    eax, eax
0x40d9b4  jz      short loc_40D9C7
0x40d9b6  push    0; dwFlags
0x40d9b8  push    0; hFile
0x40d9ba  push    esi; lpLibFileName
0x40d9bb  call    ds:LoadLibraryExW
0x40d9c1  mov     esi, eax
0x40d9c3  test    esi, esi
0x40d9c5  jnz     short loc_40D9DB
0x40d9c7  or      eax, 0FFFFFFFFh
0x40d9ca  xchg    eax, [ebx]
0x40d9cc  add     edi, 4
0x40d9cf  cmp     edi, [ebp+arg_4]
0x40d9d2  jnz     short loc_40D95F
0x40d9d4  xor     eax, eax
0x40d9d6  pop     edi
0x40d9d7  pop     esi
0x40d9d8  pop     ebx
0x40d9d9  leave
0x40d9da  retn
0x40d9db  mov     eax, esi
0x40d9dd  xchg    eax, [ebx]
0x40d9df  test    eax, eax
0x40d9e1  jz      short loc_40D9EA
0x40d9e3  push    esi; hLibModule
0x40d9e4  call    ds:FreeLibrary
0x40d9ea  mov     eax, esi
0x40d9ec  jmp     short loc_40D9D6
```

# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x1001a175`
- end: `0x1001a23e`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1001a23e`

## callees

- `0x10016d37`
- `0x1001a175`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1001a1b3`
- `KERNEL32!LoadLibraryExW` at `0x1001a1f5`
- `KERNEL32!LoadLibraryExW` at `0x1001a1b3`
- `KERNEL32!LoadLibraryExW` at `0x1001a1f5`
- `KERNEL32!GetLastError` at `0x1001a1bf`
- `KERNEL32!GetLastError` at `0x1001a1bf`
- `KERNEL32!FreeLibrary` at `0x1001a21b`
- `KERNEL32!FreeLibrary` at `0x1001a21b`

## pseudocode

```c
HMODULE __cdecl try_get_first_available_module(_DWORD *a1, _DWORD *a2)
{
  HMODULE Library; // esi
  const WCHAR *v4; // ebx
  volatile __int32 *v6; // [esp+Ch] [ebp-4h]

  while ( 1 )
  {
    if ( a1 == a2 )
      return 0;
    Library = (HMODULE)dword_100352B8[*a1];
    v6 = &dword_100352B8[*a1];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_16:
    ++a1;
  }
  v4 = (&off_1002CE60)[*a1];
  Library = LoadLibraryExW(v4, 0, 0x800u);
  if ( !Library )
  {
    Library = GetLastError() != 87 || !wcsncmp(v4, L"api-ms-", 7u) || !wcsncmp(v4, L"ext-ms-", 7u)
            ? 0
            : LoadLibraryExW(v4, 0, 0);
    if ( !Library )
    {
      _InterlockedExchange(v6, -1);
      goto LABEL_16;
    }
  }
  if ( _InterlockedExchange(v6, (__int32)Library) )
    FreeLibrary(Library);
  return Library;
}

```

## disassembly

```asm
0x1001a175  mov     edi, edi
0x1001a177  push    ebp
0x1001a178  mov     ebp, esp
0x1001a17a  push    ecx
0x1001a17b  push    ebx
0x1001a17c  push    esi
0x1001a17d  push    edi
0x1001a17e  mov     edi, [ebp+arg_0]
0x1001a181  jmp     loc_1001A228
0x1001a186  mov     ebx, [edi]
0x1001a188  lea     eax, dword_100352B8[ebx*4]
0x1001a18f  mov     esi, [eax]
0x1001a191  mov     [ebp+var_4], eax
0x1001a194  nop
0x1001a195  test    esi, esi
0x1001a197  jz      short loc_1001A1A4
0x1001a199  cmp     esi, 0FFFFFFFFh
0x1001a19c  jz      loc_1001A225
0x1001a1a2  jmp     short loc_1001A221
0x1001a1a4  mov     ebx, ds:off_1002CE60[ebx*4]
0x1001a1ab  push    800h; dwFlags
0x1001a1b0  push    0; hFile
0x1001a1b2  push    ebx; lpLibFileName
0x1001a1b3  call    ds:LoadLibraryExW
0x1001a1b9  mov     esi, eax
0x1001a1bb  test    esi, esi
0x1001a1bd  jnz     short loc_1001A20F
0x1001a1bf  call    ds:GetLastError
0x1001a1c5  cmp     eax, 57h ; 'W'
0x1001a1c8  jnz     short loc_1001A1FF
0x1001a1ca  push    7; MaxCount
0x1001a1cc  push    offset aApiMs_0
0x1001a1d1  push    ebx; String1
0x1001a1d2  call    _wcsncmp
0x1001a1d7  add     esp, 0Ch
0x1001a1da  test    eax, eax
0x1001a1dc  jz      short loc_1001A1FF
0x1001a1de  push    7; MaxCount
0x1001a1e0  push    offset aExtMs_0
0x1001a1e5  push    ebx; String1
0x1001a1e6  call    _wcsncmp
0x1001a1eb  add     esp, 0Ch
0x1001a1ee  test    eax, eax
0x1001a1f0  jz      short loc_1001A1FF
0x1001a1f2  push    esi; dwFlags
0x1001a1f3  push    esi; hFile
0x1001a1f4  push    ebx; lpLibFileName
0x1001a1f5  call    ds:LoadLibraryExW
0x1001a1fb  mov     esi, eax
0x1001a1fd  jmp     short loc_1001A201
0x1001a1ff  xor     esi, esi
0x1001a201  test    esi, esi
0x1001a203  jnz     short loc_1001A20F
0x1001a205  mov     ecx, [ebp+var_4]
0x1001a208  or      eax, 0FFFFFFFFh
0x1001a20b  xchg    eax, [ecx]
0x1001a20d  jmp     short loc_1001A225
0x1001a20f  mov     ecx, [ebp+var_4]
0x1001a212  mov     eax, esi
0x1001a214  xchg    eax, [ecx]
0x1001a216  test    eax, eax
0x1001a218  jz      short loc_1001A221
0x1001a21a  push    esi; hLibModule
0x1001a21b  call    ds:FreeLibrary
0x1001a221  test    esi, esi
0x1001a223  jnz     short loc_1001A23A
0x1001a225  add     edi, 4
0x1001a228  cmp     edi, [ebp+arg_4]
0x1001a22b  jnz     loc_1001A186
0x1001a231  xor     eax, eax
0x1001a233  pop     edi
0x1001a234  pop     esi
0x1001a235  pop     ebx
0x1001a236  mov     esp, ebp
0x1001a238  pop     ebp
0x1001a239  retn
0x1001a23a  mov     eax, esi
0x1001a23c  jmp     short loc_1001A233
```

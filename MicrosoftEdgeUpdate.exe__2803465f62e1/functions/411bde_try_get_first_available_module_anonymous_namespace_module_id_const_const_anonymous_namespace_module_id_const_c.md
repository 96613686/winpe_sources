# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x411bde`
- end: `0x411ca5`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z`
- size: `199`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x411ca5`

## callees

- `0x40f5e8`
- `0x411bde`

## import_xrefs

- `KERNEL32!GetLastError` at `0x411c28`
- `KERNEL32!GetLastError` at `0x411c28`
- `KERNEL32!FreeLibrary` at `0x411c84`
- `KERNEL32!FreeLibrary` at `0x411c84`
- `KERNEL32!LoadLibraryExW` at `0x411c1c`
- `KERNEL32!LoadLibraryExW` at `0x411c5e`
- `KERNEL32!LoadLibraryExW` at `0x411c1c`
- `KERNEL32!LoadLibraryExW` at `0x411c5e`

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
    Library = (HMODULE)dword_4183B8[*a1];
    v6 = &dword_4183B8[*a1];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_16:
    ++a1;
  }
  v4 = (&String1)[*a1];
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
0x411bde  mov     edi, edi
0x411be0  push    ebp
0x411be1  mov     ebp, esp
0x411be3  push    ecx
0x411be4  push    ebx
0x411be5  push    esi
0x411be6  push    edi
0x411be7  mov     edi, [ebp+arg_0]
0x411bea  jmp     loc_411C91
0x411bef  mov     ebx, [edi]
0x411bf1  lea     eax, dword_4183B8[ebx*4]
0x411bf8  mov     esi, [eax]
0x411bfa  mov     [ebp+var_4], eax
0x411bfd  nop
0x411bfe  test    esi, esi
0x411c00  jz      short loc_411C0D
0x411c02  cmp     esi, 0FFFFFFFFh
0x411c05  jz      loc_411C8E
0x411c0b  jmp     short loc_411C8A
0x411c0d  mov     ebx, ds:String1[ebx*4]
0x411c14  push    800h; dwFlags
0x411c19  push    0; hFile
0x411c1b  push    ebx; lpLibFileName
0x411c1c  call    ds:LoadLibraryExW
0x411c22  mov     esi, eax
0x411c24  test    esi, esi
0x411c26  jnz     short loc_411C78
0x411c28  call    ds:GetLastError
0x411c2e  cmp     eax, 57h ; 'W'
0x411c31  jnz     short loc_411C68
0x411c33  push    7; MaxCount
0x411c35  push    offset aApiMs
0x411c3a  push    ebx; String1
0x411c3b  call    _wcsncmp
0x411c40  add     esp, 0Ch
0x411c43  test    eax, eax
0x411c45  jz      short loc_411C68
0x411c47  push    7; MaxCount
0x411c49  push    offset aExtMs
0x411c4e  push    ebx; String1
0x411c4f  call    _wcsncmp
0x411c54  add     esp, 0Ch
0x411c57  test    eax, eax
0x411c59  jz      short loc_411C68
0x411c5b  push    esi; dwFlags
0x411c5c  push    esi; hFile
0x411c5d  push    ebx; lpLibFileName
0x411c5e  call    ds:LoadLibraryExW
0x411c64  mov     esi, eax
0x411c66  jmp     short loc_411C6A
0x411c68  xor     esi, esi
0x411c6a  test    esi, esi
0x411c6c  jnz     short loc_411C78
0x411c6e  mov     ecx, [ebp+var_4]
0x411c71  or      eax, 0FFFFFFFFh
0x411c74  xchg    eax, [ecx]
0x411c76  jmp     short loc_411C8E
0x411c78  mov     ecx, [ebp+var_4]
0x411c7b  mov     eax, esi
0x411c7d  xchg    eax, [ecx]
0x411c7f  test    eax, eax
0x411c81  jz      short loc_411C8A
0x411c83  push    esi; hLibModule
0x411c84  call    ds:FreeLibrary
0x411c8a  test    esi, esi
0x411c8c  jnz     short loc_411CA1
0x411c8e  add     edi, 4
0x411c91  cmp     edi, [ebp+arg_4]
0x411c94  jnz     loc_411BEF
0x411c9a  xor     eax, eax
0x411c9c  pop     edi
0x411c9d  pop     esi
0x411c9e  pop     ebx
0x411c9f  leave
0x411ca0  retn
0x411ca1  mov     eax, esi
0x411ca3  jmp     short loc_411C9C
```

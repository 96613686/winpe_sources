# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x40ebf7`
- end: `0x40ec92`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z`
- size: `155`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40ec92`

## callees

- `0x40ebf7`
- `0x413678`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x40ec88`
- `KERNEL32!FreeLibrary` at `0x40ec88`
- `KERNEL32!LoadLibraryExW` at `0x40ec2c`
- `KERNEL32!LoadLibraryExW` at `0x40ec5f`
- `KERNEL32!LoadLibraryExW` at `0x40ec2c`
- `KERNEL32!LoadLibraryExW` at `0x40ec5f`
- `KERNEL32!GetLastError` at `0x40ec38`
- `KERNEL32!GetLastError` at `0x40ec38`

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
    v3 = &dword_43E0A4[*a1];
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
0x40ebf7  push    ebp
0x40ebf8  mov     ebp, esp
0x40ebfa  push    ecx
0x40ebfb  push    ebx
0x40ebfc  push    esi
0x40ebfd  push    edi
0x40ebfe  mov     edi, [ebp+arg_0]
0x40ec01  jmp     short loc_40EC73
0x40ec03  mov     eax, [edi]
0x40ec05  lea     ebx, dword_43E0A4[eax*4]
0x40ec0c  mov     esi, [ebx]
0x40ec0e  nop
0x40ec0f  test    esi, esi
0x40ec11  jz      short loc_40EC1A
0x40ec13  cmp     esi, 0FFFFFFFFh
0x40ec16  jnz     short loc_40EC8E
0x40ec18  jmp     short loc_40EC70
0x40ec1a  mov     eax, ds:lpLibFileName[eax*4]
0x40ec21  push    800h; dwFlags
0x40ec26  push    0; hFile
0x40ec28  push    eax; lpLibFileName
0x40ec29  mov     [ebp+lpLibFileName], eax
0x40ec2c  call    ds:LoadLibraryExW
0x40ec32  mov     esi, eax
0x40ec34  test    esi, esi
0x40ec36  jnz     short loc_40EC7F
0x40ec38  call    ds:GetLastError
0x40ec3e  cmp     eax, 57h ; 'W'
0x40ec41  jnz     short loc_40EC6B
0x40ec43  mov     esi, [ebp+lpLibFileName]
0x40ec46  push    7; MaxCount
0x40ec48  push    offset aApiMs
0x40ec4d  push    esi; String1
0x40ec4e  call    _wcsncmp
0x40ec53  add     esp, 0Ch
0x40ec56  test    eax, eax
0x40ec58  jz      short loc_40EC6B
0x40ec5a  push    0; dwFlags
0x40ec5c  push    0; hFile
0x40ec5e  push    esi; lpLibFileName
0x40ec5f  call    ds:LoadLibraryExW
0x40ec65  mov     esi, eax
0x40ec67  test    esi, esi
0x40ec69  jnz     short loc_40EC7F
0x40ec6b  or      eax, 0FFFFFFFFh
0x40ec6e  xchg    eax, [ebx]
0x40ec70  add     edi, 4
0x40ec73  cmp     edi, [ebp+arg_4]
0x40ec76  jnz     short loc_40EC03
0x40ec78  xor     eax, eax
0x40ec7a  pop     edi
0x40ec7b  pop     esi
0x40ec7c  pop     ebx
0x40ec7d  leave
0x40ec7e  retn
0x40ec7f  mov     eax, esi
0x40ec81  xchg    eax, [ebx]
0x40ec83  test    eax, eax
0x40ec85  jz      short loc_40EC8E
0x40ec87  push    esi; hLibModule
0x40ec88  call    ds:FreeLibrary
0x40ec8e  mov     eax, esi
0x40ec90  jmp     short loc_40EC7A
```

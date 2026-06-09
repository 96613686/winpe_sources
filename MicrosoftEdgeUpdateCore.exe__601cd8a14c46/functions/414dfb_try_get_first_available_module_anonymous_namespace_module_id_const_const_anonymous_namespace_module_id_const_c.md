# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x414dfb`
- end: `0x414ec2`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z`
- size: `199`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x414ec2`

## callees

- `0x413678`
- `0x414dfb`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x414ea1`
- `KERNEL32!FreeLibrary` at `0x414ea1`
- `KERNEL32!LoadLibraryExW` at `0x414e39`
- `KERNEL32!LoadLibraryExW` at `0x414e7b`
- `KERNEL32!LoadLibraryExW` at `0x414e39`
- `KERNEL32!LoadLibraryExW` at `0x414e7b`
- `KERNEL32!GetLastError` at `0x414e45`
- `KERNEL32!GetLastError` at `0x414e45`

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
    Library = (HMODULE)dword_43E4A8[*a1];
    v6 = &dword_43E4A8[*a1];
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
0x414dfb  mov     edi, edi
0x414dfd  push    ebp
0x414dfe  mov     ebp, esp
0x414e00  push    ecx
0x414e01  push    ebx
0x414e02  push    esi
0x414e03  push    edi
0x414e04  mov     edi, [ebp+arg_0]
0x414e07  jmp     loc_414EAE
0x414e0c  mov     ebx, [edi]
0x414e0e  lea     eax, dword_43E4A8[ebx*4]
0x414e15  mov     esi, [eax]
0x414e17  mov     [ebp+var_4], eax
0x414e1a  nop
0x414e1b  test    esi, esi
0x414e1d  jz      short loc_414E2A
0x414e1f  cmp     esi, 0FFFFFFFFh
0x414e22  jz      loc_414EAB
0x414e28  jmp     short loc_414EA7
0x414e2a  mov     ebx, ds:String1[ebx*4]
0x414e31  push    800h; dwFlags
0x414e36  push    0; hFile
0x414e38  push    ebx; lpLibFileName
0x414e39  call    ds:LoadLibraryExW
0x414e3f  mov     esi, eax
0x414e41  test    esi, esi
0x414e43  jnz     short loc_414E95
0x414e45  call    ds:GetLastError
0x414e4b  cmp     eax, 57h ; 'W'
0x414e4e  jnz     short loc_414E85
0x414e50  push    7; MaxCount
0x414e52  push    offset aApiMs
0x414e57  push    ebx; String1
0x414e58  call    _wcsncmp
0x414e5d  add     esp, 0Ch
0x414e60  test    eax, eax
0x414e62  jz      short loc_414E85
0x414e64  push    7; MaxCount
0x414e66  push    offset aExtMs
0x414e6b  push    ebx; String1
0x414e6c  call    _wcsncmp
0x414e71  add     esp, 0Ch
0x414e74  test    eax, eax
0x414e76  jz      short loc_414E85
0x414e78  push    esi; dwFlags
0x414e79  push    esi; hFile
0x414e7a  push    ebx; lpLibFileName
0x414e7b  call    ds:LoadLibraryExW
0x414e81  mov     esi, eax
0x414e83  jmp     short loc_414E87
0x414e85  xor     esi, esi
0x414e87  test    esi, esi
0x414e89  jnz     short loc_414E95
0x414e8b  mov     ecx, [ebp+var_4]
0x414e8e  or      eax, 0FFFFFFFFh
0x414e91  xchg    eax, [ecx]
0x414e93  jmp     short loc_414EAB
0x414e95  mov     ecx, [ebp+var_4]
0x414e98  mov     eax, esi
0x414e9a  xchg    eax, [ecx]
0x414e9c  test    eax, eax
0x414e9e  jz      short loc_414EA7
0x414ea0  push    esi; hLibModule
0x414ea1  call    ds:FreeLibrary
0x414ea7  test    esi, esi
0x414ea9  jnz     short loc_414EBE
0x414eab  add     edi, 4
0x414eae  cmp     edi, [ebp+arg_4]
0x414eb1  jnz     loc_414E0C
0x414eb7  xor     eax, eax
0x414eb9  pop     edi
0x414eba  pop     esi
0x414ebb  pop     ebx
0x414ebc  leave
0x414ebd  retn
0x414ebe  mov     eax, esi
0x414ec0  jmp     short loc_414EB9
```

# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x100128ce`
- end: `0x10012992`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x03f7da57@@0@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10012992`

## callees

- `0x100128ce`
- `0x10016d37`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x10012909`
- `KERNEL32!LoadLibraryExW` at `0x1001294b`
- `KERNEL32!LoadLibraryExW` at `0x10012909`
- `KERNEL32!LoadLibraryExW` at `0x1001294b`
- `KERNEL32!GetLastError` at `0x10012915`
- `KERNEL32!GetLastError` at `0x10012915`
- `KERNEL32!FreeLibrary` at `0x10012971`
- `KERNEL32!FreeLibrary` at `0x10012971`

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
    Library = (HMODULE)dword_10034DA0[*a1];
    v6 = &dword_10034DA0[*a1];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1 )
      return Library;
LABEL_16:
    ++a1;
  }
  v4 = (&lpLibFileName)[*a1];
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
0x100128ce  push    ebp
0x100128cf  mov     ebp, esp
0x100128d1  push    ecx
0x100128d2  push    ebx
0x100128d3  push    esi
0x100128d4  push    edi
0x100128d5  mov     edi, [ebp+arg_0]
0x100128d8  jmp     loc_1001297E
0x100128dd  mov     ebx, [edi]
0x100128df  lea     eax, dword_10034DA0[ebx*4]
0x100128e6  mov     esi, [eax]
0x100128e8  mov     [ebp+var_4], eax
0x100128eb  test    esi, esi
0x100128ed  jz      short loc_100128FA
0x100128ef  cmp     esi, 0FFFFFFFFh
0x100128f2  jz      loc_1001297B
0x100128f8  jmp     short loc_10012977
0x100128fa  mov     ebx, ds:lpLibFileName[ebx*4]
0x10012901  push    800h; dwFlags
0x10012906  push    0; hFile
0x10012908  push    ebx; lpLibFileName
0x10012909  call    ds:LoadLibraryExW
0x1001290f  mov     esi, eax
0x10012911  test    esi, esi
0x10012913  jnz     short loc_10012965
0x10012915  call    ds:GetLastError
0x1001291b  cmp     eax, 57h ; 'W'
0x1001291e  jnz     short loc_10012955
0x10012920  push    7; MaxCount
0x10012922  push    offset aApiMs
0x10012927  push    ebx; String1
0x10012928  call    _wcsncmp
0x1001292d  add     esp, 0Ch
0x10012930  test    eax, eax
0x10012932  jz      short loc_10012955
0x10012934  push    7; MaxCount
0x10012936  push    offset aExtMs
0x1001293b  push    ebx; String1
0x1001293c  call    _wcsncmp
0x10012941  add     esp, 0Ch
0x10012944  test    eax, eax
0x10012946  jz      short loc_10012955
0x10012948  push    esi; dwFlags
0x10012949  push    esi; hFile
0x1001294a  push    ebx; lpLibFileName
0x1001294b  call    ds:LoadLibraryExW
0x10012951  mov     esi, eax
0x10012953  jmp     short loc_10012957
0x10012955  xor     esi, esi
0x10012957  test    esi, esi
0x10012959  jnz     short loc_10012965
0x1001295b  mov     ecx, [ebp+var_4]
0x1001295e  or      eax, 0FFFFFFFFh
0x10012961  xchg    eax, [ecx]
0x10012963  jmp     short loc_1001297B
0x10012965  mov     ecx, [ebp+var_4]
0x10012968  mov     eax, esi
0x1001296a  xchg    eax, [ecx]
0x1001296c  test    eax, eax
0x1001296e  jz      short loc_10012977
0x10012970  push    esi; hLibModule
0x10012971  call    ds:FreeLibrary
0x10012977  test    esi, esi
0x10012979  jnz     short loc_1001298E
0x1001297b  add     edi, 4
0x1001297e  cmp     edi, [ebp+arg_4]
0x10012981  jnz     loc_100128DD
0x10012987  xor     eax, eax
0x10012989  pop     edi
0x1001298a  pop     esi
0x1001298b  pop     ebx
0x1001298c  leave
0x1001298d  retn
0x1001298e  mov     eax, esi
0x10012990  jmp     short loc_10012989
```

# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x4095d3`
- end: `0x40966e`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x81907119@@0@Z`
- size: `155`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x40966e`

## callees

- `0x4095d3`
- `0x40e498`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x409608`
- `KERNEL32!LoadLibraryExW` at `0x40963b`
- `KERNEL32!LoadLibraryExW` at `0x409608`
- `KERNEL32!LoadLibraryExW` at `0x40963b`
- `KERNEL32!FreeLibrary` at `0x409664`
- `KERNEL32!FreeLibrary` at `0x409664`
- `KERNEL32!GetLastError` at `0x409614`
- `KERNEL32!GetLastError` at `0x409614`

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
    v3 = &dword_426D10[*a1];
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
0x4095d3  push    ebp
0x4095d4  mov     ebp, esp
0x4095d6  push    ecx
0x4095d7  push    ebx
0x4095d8  push    esi
0x4095d9  push    edi
0x4095da  mov     edi, [ebp+arg_0]
0x4095dd  jmp     short loc_40964F
0x4095df  mov     eax, [edi]
0x4095e1  lea     ebx, dword_426D10[eax*4]
0x4095e8  mov     esi, [ebx]
0x4095ea  nop
0x4095eb  test    esi, esi
0x4095ed  jz      short loc_4095F6
0x4095ef  cmp     esi, 0FFFFFFFFh
0x4095f2  jnz     short loc_40966A
0x4095f4  jmp     short loc_40964C
0x4095f6  mov     eax, ds:lpLibFileName[eax*4]
0x4095fd  push    800h; dwFlags
0x409602  push    0; hFile
0x409604  push    eax; lpLibFileName
0x409605  mov     [ebp+lpLibFileName], eax
0x409608  call    ds:LoadLibraryExW
0x40960e  mov     esi, eax
0x409610  test    esi, esi
0x409612  jnz     short loc_40965B
0x409614  call    ds:GetLastError
0x40961a  cmp     eax, 57h ; 'W'
0x40961d  jnz     short loc_409647
0x40961f  mov     esi, [ebp+lpLibFileName]
0x409622  push    7; MaxCount
0x409624  push    offset aApiMs
0x409629  push    esi; String1
0x40962a  call    _wcsncmp
0x40962f  add     esp, 0Ch
0x409632  test    eax, eax
0x409634  jz      short loc_409647
0x409636  push    0; dwFlags
0x409638  push    0; hFile
0x40963a  push    esi; lpLibFileName
0x40963b  call    ds:LoadLibraryExW
0x409641  mov     esi, eax
0x409643  test    esi, esi
0x409645  jnz     short loc_40965B
0x409647  or      eax, 0FFFFFFFFh
0x40964a  xchg    eax, [ebx]
0x40964c  add     edi, 4
0x40964f  cmp     edi, [ebp+arg_4]
0x409652  jnz     short loc_4095DF
0x409654  xor     eax, eax
0x409656  pop     edi
0x409657  pop     esi
0x409658  pop     ebx
0x409659  leave
0x40965a  retn
0x40965b  mov     eax, esi
0x40965d  xchg    eax, [ebx]
0x40965f  test    eax, eax
0x409661  jz      short loc_40966A
0x409663  push    esi; hLibModule
0x409664  call    ds:FreeLibrary
0x40966a  mov     eax, esi
0x40966c  jmp     short loc_409656
```

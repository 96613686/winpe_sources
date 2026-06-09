# try_get_first_available_module(`anonymous namespace'::module_id const * const,`anonymous namespace'::module_id const * const)

- ea: `0x411224`
- end: `0x4112eb`
- name: `?try_get_first_available_module@@YAPAUHINSTANCE__@@QBW4module_id@?A0x391cf84c@@0@Z`
- size: `199`
- prototype: `HMODULE __cdecl(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x4112eb`

## callees

- `0x40e498`
- `0x411224`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x411262`
- `KERNEL32!LoadLibraryExW` at `0x4112a4`
- `KERNEL32!LoadLibraryExW` at `0x411262`
- `KERNEL32!LoadLibraryExW` at `0x4112a4`
- `KERNEL32!FreeLibrary` at `0x4112ca`
- `KERNEL32!FreeLibrary` at `0x4112ca`
- `KERNEL32!GetLastError` at `0x41126e`
- `KERNEL32!GetLastError` at `0x41126e`

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
    Library = (HMODULE)dword_427220[*a1];
    v6 = &dword_427220[*a1];
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
0x411224  mov     edi, edi
0x411226  push    ebp
0x411227  mov     ebp, esp
0x411229  push    ecx
0x41122a  push    ebx
0x41122b  push    esi
0x41122c  push    edi
0x41122d  mov     edi, [ebp+arg_0]
0x411230  jmp     loc_4112D7
0x411235  mov     ebx, [edi]
0x411237  lea     eax, dword_427220[ebx*4]
0x41123e  mov     esi, [eax]
0x411240  mov     [ebp+var_4], eax
0x411243  nop
0x411244  test    esi, esi
0x411246  jz      short loc_411253
0x411248  cmp     esi, 0FFFFFFFFh
0x41124b  jz      loc_4112D4
0x411251  jmp     short loc_4112D0
0x411253  mov     ebx, ds:String1[ebx*4]
0x41125a  push    800h; dwFlags
0x41125f  push    0; hFile
0x411261  push    ebx; lpLibFileName
0x411262  call    ds:LoadLibraryExW
0x411268  mov     esi, eax
0x41126a  test    esi, esi
0x41126c  jnz     short loc_4112BE
0x41126e  call    ds:GetLastError
0x411274  cmp     eax, 57h ; 'W'
0x411277  jnz     short loc_4112AE
0x411279  push    7; MaxCount
0x41127b  push    offset aApiMs
0x411280  push    ebx; String1
0x411281  call    _wcsncmp
0x411286  add     esp, 0Ch
0x411289  test    eax, eax
0x41128b  jz      short loc_4112AE
0x41128d  push    7; MaxCount
0x41128f  push    offset aExtMs
0x411294  push    ebx; String1
0x411295  call    _wcsncmp
0x41129a  add     esp, 0Ch
0x41129d  test    eax, eax
0x41129f  jz      short loc_4112AE
0x4112a1  push    esi; dwFlags
0x4112a2  push    esi; hFile
0x4112a3  push    ebx; lpLibFileName
0x4112a4  call    ds:LoadLibraryExW
0x4112aa  mov     esi, eax
0x4112ac  jmp     short loc_4112B0
0x4112ae  xor     esi, esi
0x4112b0  test    esi, esi
0x4112b2  jnz     short loc_4112BE
0x4112b4  mov     ecx, [ebp+var_4]
0x4112b7  or      eax, 0FFFFFFFFh
0x4112ba  xchg    eax, [ecx]
0x4112bc  jmp     short loc_4112D4
0x4112be  mov     ecx, [ebp+var_4]
0x4112c1  mov     eax, esi
0x4112c3  xchg    eax, [ecx]
0x4112c5  test    eax, eax
0x4112c7  jz      short loc_4112D0
0x4112c9  push    esi; hLibModule
0x4112ca  call    ds:FreeLibrary
0x4112d0  test    esi, esi
0x4112d2  jnz     short loc_4112E7
0x4112d4  add     edi, 4
0x4112d7  cmp     edi, [ebp+arg_4]
0x4112da  jnz     loc_411235
0x4112e0  xor     eax, eax
0x4112e2  pop     edi
0x4112e3  pop     esi
0x4112e4  pop     ebx
0x4112e5  leave
0x4112e6  retn
0x4112e7  mov     eax, esi
0x4112e9  jmp     short loc_4112E2
```

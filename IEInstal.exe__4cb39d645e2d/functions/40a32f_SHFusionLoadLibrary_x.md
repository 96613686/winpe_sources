# SHFusionLoadLibrary(x)

- ea: `0x40a32f`
- end: `0x40a36c`
- name: `_SHFusionLoadLibrary@4`
- size: `61`
- prototype: `int()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x40a372`

## callees

- `0x40a1f1`
- `0x40a242`
- `0x40a32f`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x40a357`
- `KERNEL32!LoadLibraryExW` at `0x40a357`

## string_xrefs

- `0x40a352`: `comctl32.dll`

## pseudocode

```c
int SHFusionLoadLibrary()
{
  int result; // eax
  HMODULE Library; // esi
  ULONG_PTR ulCookie; // [esp+0h] [ebp-4h] BYREF

  ulCookie = 0;
  result = SHActivateContext(&ulCookie);
  if ( result )
  {
    Library = LoadLibraryExW(L"comctl32.dll", 0, 0x4000u);
    SHDeactivateContext(ulCookie);
    return (int)Library;
  }
  return result;
}

```

## disassembly

```asm
0x40a32f  mov     edi, edi
0x40a331  push    ebp
0x40a332  mov     ebp, esp
0x40a334  push    ecx
0x40a335  lea     ecx, [ebp+ulCookie]; lpCookie
0x40a338  mov     [ebp+ulCookie], 0
0x40a33f  call    _SHActivateContext@4; SHActivateContext(x)
0x40a344  test    eax, eax
0x40a346  jnz     short loc_40A34A
0x40a348  leave
0x40a349  retn
0x40a34a  push    esi
0x40a34b  push    4000h; dwFlags
0x40a350  push    0; hFile
0x40a352  push    offset aComctl32Dll; "comctl32.dll"
0x40a357  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x40a35d  mov     ecx, [ebp+ulCookie]; ulCookie
0x40a360  mov     esi, eax
0x40a362  call    _SHDeactivateContext@4; SHDeactivateContext(x)
0x40a367  mov     eax, esi
0x40a369  pop     esi
0x40a36a  leave
0x40a36b  retn
```

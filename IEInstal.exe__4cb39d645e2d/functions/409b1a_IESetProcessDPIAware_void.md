# IESetProcessDPIAware(void)

- ea: `0x409b1a`
- end: `0x409b62`
- name: `?IESetProcessDPIAware@@YGHXZ`
- size: `72`
- prototype: `int __stdcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x409212`

## callees

- `0x409b1a`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x409b3d`
- `KERNEL32!GetProcAddress` at `0x409b3d`
- `KERNEL32!FreeLibrary` at `0x409b56`
- `KERNEL32!FreeLibrary` at `0x409b56`
- `KERNEL32!LoadLibraryExW` at `0x409b2a`
- `KERNEL32!LoadLibraryExW` at `0x409b2a`

## string_xrefs

- `0x409b24`: `user32.dll`

## pseudocode

```c
int __stdcall IESetProcessDPIAware()
{
  int v0; // ebx
  HMODULE Library; // eax
  HMODULE v2; // esi
  BOOL (__stdcall *SetProcessDPIAware)(); // eax

  v0 = 1;
  Library = LoadLibraryExW(L"user32.dll", 0, 0);
  v2 = Library;
  if ( Library )
  {
    SetProcessDPIAware = GetProcAddress(Library, "SetProcessDPIAware");
    if ( SetProcessDPIAware )
      v0 = ((int (__thiscall *)(BOOL (__stdcall *)()))SetProcessDPIAware)(SetProcessDPIAware);
    FreeLibrary(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x409b1a  mov     edi, edi
0x409b1c  push    ebx
0x409b1d  push    esi
0x409b1e  push    0; dwFlags
0x409b20  push    0; hFile
0x409b22  xor     ebx, ebx
0x409b24  push    offset aUser32Dll_0; "user32.dll"
0x409b29  inc     ebx
0x409b2a  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x409b30  mov     esi, eax
0x409b32  test    esi, esi
0x409b34  jz      short loc_409B5D
0x409b36  push    edi
0x409b37  push    offset aSetprocessdpia; "SetProcessDPIAware"
0x409b3c  push    esi; hModule
0x409b3d  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x409b43  mov     edi, eax
0x409b45  test    edi, edi
0x409b47  jz      short loc_409B55
0x409b49  mov     ecx, edi
0x409b4b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x409b51  call    edi
0x409b53  mov     ebx, eax
0x409b55  push    esi; hLibModule
0x409b56  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x409b5c  pop     edi
0x409b5d  pop     esi
0x409b5e  mov     eax, ebx
0x409b60  pop     ebx
0x409b61  retn
```

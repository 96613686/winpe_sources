# RegisterProxyDll(ushort const *)

- ea: `0x4098bb`
- end: `0x40992d`
- name: `?RegisterProxyDll@@YGJPBG@Z`
- size: `114`
- prototype: `unsigned int __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x409212`

## callees

- `0x4098bb`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x4098dd`
- `KERNEL32!GetProcAddress` at `0x4098dd`
- `KERNEL32!FreeLibrary` at `0x40990c`
- `KERNEL32!FreeLibrary` at `0x40990c`
- `KERNEL32!LoadLibraryExW` at `0x4098cb`
- `KERNEL32!LoadLibraryExW` at `0x4098cb`
- `KERNEL32!GetLastError` at `0x4098f7`
- `KERNEL32!GetLastError` at `0x409914`
- `KERNEL32!GetLastError` at `0x4098f7`
- `KERNEL32!GetLastError` at `0x409914`

## string_xrefs

- `0x4098c6`: `actxprxy.dll`
- `0x4098d7`: `DllRegisterServer`

## pseudocode

```c
unsigned int __cdecl RegisterProxyDll()
{
  HMODULE Library; // eax
  HMODULE v1; // edi
  HRESULT (__stdcall *DllRegisterServer)(); // eax
  unsigned int v3; // esi
  signed int LastError; // eax
  signed int v5; // eax

  Library = LoadLibraryExW(L"actxprxy.dll", 0, 0x1000u);
  v1 = Library;
  if ( Library )
  {
    DllRegisterServer = GetProcAddress(Library, "DllRegisterServer");
    if ( DllRegisterServer )
    {
      v3 = ((int (__thiscall *)(HRESULT (__stdcall *)()))DllRegisterServer)(DllRegisterServer);
    }
    else
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
    FreeLibrary(v1);
  }
  else
  {
    v5 = GetLastError();
    v3 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      return v5;
  }
  return v3;
}

```

## disassembly

```asm
0x4098bb  mov     edi, edi
0x4098bd  push    esi
0x4098be  push    edi
0x4098bf  push    1000h; dwFlags
0x4098c4  push    0; hFile
0x4098c6  push    offset aActxprxyDll; "actxprxy.dll"
0x4098cb  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x4098d1  mov     edi, eax
0x4098d3  test    edi, edi
0x4098d5  jz      short loc_409914
0x4098d7  push    offset aDllregisterser; "DllRegisterServer"
0x4098dc  push    edi; hModule
0x4098dd  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x4098e3  mov     esi, eax
0x4098e5  test    esi, esi
0x4098e7  jz      short loc_4098F7
0x4098e9  mov     ecx, esi
0x4098eb  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x4098f1  call    esi
0x4098f3  mov     esi, eax
0x4098f5  jmp     short loc_40990B
0x4098f7  call    ds:__imp__GetLastError@0; GetLastError()
0x4098fd  movzx   esi, ax
0x409900  or      esi, 80070000h
0x409906  test    eax, eax
0x409908  cmovle  esi, eax
0x40990b  push    edi; hLibModule
0x40990c  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x409912  jmp     short loc_409928
0x409914  call    ds:__imp__GetLastError@0; GetLastError()
0x40991a  movzx   esi, ax
0x40991d  or      esi, 80070000h
0x409923  test    eax, eax
0x409925  cmovle  esi, eax
0x409928  pop     edi
0x409929  mov     eax, esi
0x40992b  pop     esi
0x40992c  retn
```

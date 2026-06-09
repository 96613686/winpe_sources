# WinVerifyTrustThreadProc(_WINVERIFYTRUST_PARAMS *)

- ea: `0x408e90`
- end: `0x408f4b`
- name: `?WinVerifyTrustThreadProc@@YGKPAU_WINVERIFYTRUST_PARAMS@@@Z`
- size: `187`
- prototype: `int __stdcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x408e90`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x408ef0`
- `KERNEL32!GetProcAddress` at `0x408ef0`
- `KERNEL32!FreeLibrary` at `0x408f36`
- `KERNEL32!FreeLibrary` at `0x408f36`
- `KERNEL32!LoadLibraryExW` at `0x408ec8`
- `KERNEL32!LoadLibraryExW` at `0x408ec8`
- `KERNEL32!GetLastError` at `0x408ed4`
- `KERNEL32!GetLastError` at `0x408f15`
- `KERNEL32!GetLastError` at `0x408ed4`
- `KERNEL32!GetLastError` at `0x408f15`
- `ole32!CoInitialize` at `0x408e98`
- `ole32!CoInitialize` at `0x408e98`
- `ole32!CoUninitialize` at `0x408f3c`
- `ole32!CoUninitialize` at `0x408f3c`

## string_xrefs

- `0x408ec3`: `WinTrust.Dll`

## pseudocode

```c
int __stdcall WinVerifyTrustThreadProc(_DWORD *lpThreadParameter)
{
  int v1; // esi
  HMODULE Library; // edi
  signed int v3; // eax
  LONG (__stdcall *WinVerifyTrust)(HWND, GUID *, LPVOID); // eax
  signed int LastError; // eax

  v1 = CoInitialize(0);
  if ( v1 >= 0 )
  {
    Library = (HMODULE)_InterlockedCompareExchange(&dword_40F54C, 0, 0);
    if ( Library || (Library = LoadLibraryExW(L"WinTrust.Dll", 0, 0x800u)) != 0 )
    {
      WinVerifyTrust = (LONG (__stdcall *)(HWND, GUID *, LPVOID))GetProcAddress(Library, "WinVerifyTrust");
      if ( WinVerifyTrust )
      {
        v1 = ((int (__thiscall *)(LONG (__stdcall *)(HWND, GUID *, LPVOID), _DWORD, _DWORD, _DWORD))WinVerifyTrust)(
               WinVerifyTrust,
               *lpThreadParameter,
               lpThreadParameter[1],
               lpThreadParameter[2]);
      }
      else
      {
        LastError = GetLastError();
        v1 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v1 = LastError;
      }
      if ( _InterlockedCompareExchange(&dword_40F54C, (signed __int32)Library, 0) )
        FreeLibrary(Library);
    }
    else
    {
      v3 = GetLastError();
      v1 = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        v1 = v3;
    }
    CoUninitialize();
  }
  return v1;
}

```

## disassembly

```asm
0x408e90  mov     edi, edi
0x408e92  push    ebp
0x408e93  mov     ebp, esp
0x408e95  push    esi
0x408e96  push    0; pvReserved
0x408e98  call    ds:__imp__CoInitialize@4; CoInitialize(x)
0x408e9e  mov     esi, eax
0x408ea0  test    esi, esi
0x408ea2  js      loc_408F44
0x408ea8  push    ebx
0x408ea9  push    edi
0x408eaa  xor     ecx, ecx
0x408eac  mov     ebx, offset dword_40F54C
0x408eb1  xor     eax, eax
0x408eb3  lock cmpxchg [ebx], ecx
0x408eb7  mov     edi, eax
0x408eb9  test    edi, edi
0x408ebb  jnz     short loc_408EEA
0x408ebd  push    800h; dwFlags
0x408ec2  push    eax; hFile
0x408ec3  push    offset aWintrustDll_0; "WinTrust.Dll"
0x408ec8  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x408ece  mov     edi, eax
0x408ed0  test    edi, edi
0x408ed2  jnz     short loc_408EEA
0x408ed4  call    ds:__imp__GetLastError@0; GetLastError()
0x408eda  movzx   esi, ax
0x408edd  or      esi, 80070000h
0x408ee3  test    eax, eax
0x408ee5  cmovle  esi, eax
0x408ee8  jmp     short loc_408F3C
0x408eea  push    offset aWinverifytrust; "WinVerifyTrust"
0x408eef  push    edi; hModule
0x408ef0  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x408ef6  mov     esi, eax
0x408ef8  test    esi, esi
0x408efa  jz      short loc_408F15
0x408efc  mov     ecx, [ebp+lpThreadParameter]
0x408eff  push    dword ptr [ecx+8]
0x408f02  push    dword ptr [ecx+4]
0x408f05  push    dword ptr [ecx]
0x408f07  mov     ecx, esi
0x408f09  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x408f0f  call    esi
0x408f11  mov     esi, eax
0x408f13  jmp     short loc_408F29
0x408f15  call    ds:__imp__GetLastError@0; GetLastError()
0x408f1b  movzx   esi, ax
0x408f1e  or      esi, 80070000h
0x408f24  test    eax, eax
0x408f26  cmovle  esi, eax
0x408f29  mov     ecx, edi
0x408f2b  xor     eax, eax
0x408f2d  lock cmpxchg [ebx], ecx
0x408f31  test    eax, eax
0x408f33  jz      short loc_408F3C
0x408f35  push    edi; hLibModule
0x408f36  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x408f3c  call    ds:__imp__CoUninitialize@0; CoUninitialize()
0x408f42  pop     edi
0x408f43  pop     ebx
0x408f44  mov     eax, esi
0x408f46  pop     esi
0x408f47  pop     ebp
0x408f48  retn    4
```

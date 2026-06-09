# GetResourceDll(void)

- ea: `0x140006d24`
- end: `0x140006de9`
- name: `?GetResourceDll@@YAPEAUHINSTANCE__@@XZ`
- size: `197`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000c178`
- `0x14000c5b0`

## callees

- `0x140006284`
- `0x140006d24`
- `0x140006df0`
- `0x1400075f8`
- `0x140014ad0`

## import_xrefs

- `msvcrt!wcslen` at `0x140006d60`
- `msvcrt!wcslen` at `0x140006d6c`
- `msvcrt!wcslen` at `0x140006d60`
- `msvcrt!wcslen` at `0x140006d6c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006dbb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140006dbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006daf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140006daf`

## string_xrefs

- `0x140006d59`: `WmiApRes.dll`
- `0x140006d91`: `WmiApRes.dll`

## pseudocode

```c
HINSTANCE GetResourceDll(void)
{
  HMODULE Library; // rsi
  wchar_t *WbemDirectory; // rdi
  int v2; // ebx
  unsigned int v3; // ecx
  unsigned int v4; // r11d
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-228h] BYREF

  Library = 0;
  WbemDirectory = GetWbemDirectory(0);
  if ( WbemDirectory )
  {
    v2 = wcslen(L"WmiApRes.dll");
    v3 = wcslen(WbemDirectory) + v2 + 1;
    if ( v3 <= 0x104 )
    {
      StringCchCopyW(LibFileName, v3, WbemDirectory);
      StringCchCatW(LibFileName, v4, L"WmiApRes.dll");
      Library = LoadLibraryExW(LibFileName, 0, 0);
    }
    CWin32DefaultArena::WbemMemFree(WbemDirectory);
  }
  return Library;
}

```

## disassembly

```asm
0x140006d24  mov     [rsp+arg_0], rbx
0x140006d29  mov     [rsp+arg_8], rsi
0x140006d2e  push    rdi
0x140006d2f  sub     rsp, 240h
0x140006d36  mov     rax, cs:__security_cookie
0x140006d3d  xor     rax, rsp
0x140006d40  mov     [rsp+248h+var_18], rax
0x140006d48  xor     ecx, ecx; int
0x140006d4a  xor     esi, esi
0x140006d4c  call    ?GetWbemDirectory@@YAPEAGH@Z; GetWbemDirectory(int)
0x140006d51  mov     rdi, rax
0x140006d54  test    rax, rax
0x140006d57  jz      short loc_140006DC1
0x140006d59  lea     rcx, aWmiapresDll; "WmiApRes.dll"
0x140006d60  call    cs:__imp_wcslen
0x140006d66  mov     rcx, rdi; String
0x140006d69  mov     rbx, rax
0x140006d6c  call    cs:__imp_wcslen
0x140006d72  lea     ecx, [rbx+1]
0x140006d75  add     ecx, eax
0x140006d77  cmp     ecx, 104h
0x140006d7d  ja      short loc_140006DB8
0x140006d7f  mov     r11d, ecx
0x140006d82  mov     r8, rdi; unsigned __int16 *
0x140006d85  mov     edx, ecx; unsigned __int64
0x140006d87  lea     rcx, [rsp+248h+LibFileName]; unsigned __int16 *
0x140006d8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140006d91  lea     r8, aWmiapresDll; "WmiApRes.dll"
0x140006d98  mov     edx, r11d; unsigned __int64
0x140006d9b  lea     rcx, [rsp+248h+LibFileName]; unsigned __int16 *
0x140006da0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006da5  xor     r8d, r8d; dwFlags
0x140006da8  lea     rcx, [rsp+248h+LibFileName]; lpLibFileName
0x140006dad  xor     edx, edx; hFile
0x140006daf  call    cs:__imp_LoadLibraryExW
0x140006db5  mov     rsi, rax
0x140006db8  mov     rcx, rdi
0x140006dbb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140006dc1  mov     rax, rsi
0x140006dc4  mov     rcx, [rsp+248h+var_18]
0x140006dcc  xor     rcx, rsp; StackCookie
0x140006dcf  call    __security_check_cookie
0x140006dd4  lea     r11, [rsp+248h+var_8]
0x140006ddc  mov     rbx, [r11+10h]
0x140006de0  mov     rsi, [r11+18h]
0x140006de4  mov     rsp, r11
0x140006de7  pop     rdi
0x140006de8  retn
```

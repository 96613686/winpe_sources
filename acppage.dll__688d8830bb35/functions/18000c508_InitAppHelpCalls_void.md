# InitAppHelpCalls(void)

- ea: `0x18000c508`
- end: `0x18000c61d`
- name: `?InitAppHelpCalls@@YAHXZ`
- size: `277`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c630`

## callees

- `0x180008878`
- `0x18000c508`
- `0x180016280`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18000c5cb`
- `KERNEL32!EncodePointer` at `0x18000c5db`
- `KERNEL32!EncodePointer` at `0x18000c5e4`
- `KERNEL32!EncodePointer` at `0x18000c5cb`
- `KERNEL32!EncodePointer` at `0x18000c5db`
- `KERNEL32!EncodePointer` at `0x18000c5e4`
- `KERNEL32!GetSystemDirectoryW` at `0x18000c544`
- `KERNEL32!GetSystemDirectoryW` at `0x18000c544`
- `KERNEL32!LoadLibraryW` at `0x18000c577`
- `KERNEL32!LoadLibraryW` at `0x18000c577`
- `KERNEL32!GetProcAddress` at `0x18000c58f`
- `KERNEL32!GetProcAddress` at `0x18000c5a2`
- `KERNEL32!GetProcAddress` at `0x18000c5b5`
- `KERNEL32!GetProcAddress` at `0x18000c58f`
- `KERNEL32!GetProcAddress` at `0x18000c5a2`
- `KERNEL32!GetProcAddress` at `0x18000c5b5`

## string_xrefs

- `0x18000c557`: `\apphelp.dll`

## pseudocode

```c
__int64 InitAppHelpCalls(void)
{
  unsigned int v0; // ebx
  HMODULE LibraryW; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rbp
  FARPROC v4; // rsi
  FARPROC v5; // r14
  WCHAR Buffer[264]; // [rsp+20h] [rbp-248h] BYREF

  if ( g_hAppHelp )
    return 1;
  v0 = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x103 && StringCchCatW(Buffer, 0x104u, L"\\apphelp.dll") >= 0 )
  {
    LibraryW = LoadLibraryW(Buffer);
    v2 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "GetPermLayers");
      v4 = GetProcAddress(v2, "SetPermLayers");
      v5 = GetProcAddress(v2, "SetPermLayerState");
      if ( ProcAddress )
      {
        if ( v4 )
        {
          g_pfnGetPermLayers = EncodePointer(ProcAddress);
          EncodePointer(v4);
          g_pfnSetPermLayerState = EncodePointer(v5);
          g_hAppHelp = v2;
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18000c508  push    rbx
0x18000c50a  push    rbp
0x18000c50b  push    rsi
0x18000c50c  push    rdi
0x18000c50d  push    r14
0x18000c50f  sub     rsp, 240h
0x18000c516  mov     rax, cs:__security_cookie
0x18000c51d  xor     rax, rsp
0x18000c520  mov     [rsp+268h+var_38], rax
0x18000c528  cmp     cs:?g_hAppHelp@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hAppHelp
0x18000c530  jnz     loc_18000C5F8
0x18000c536  mov     edi, 104h
0x18000c53b  lea     rcx, [rsp+268h+Buffer]; lpBuffer
0x18000c540  mov     edx, edi; uSize
0x18000c542  xor     ebx, ebx
0x18000c544  call    cs:__imp_GetSystemDirectoryW
0x18000c54a  dec     eax
0x18000c54c  cmp     eax, 103h
0x18000c551  ja      loc_18000C5FD
0x18000c557  lea     r8, aApphelpDll_0; "\\apphelp.dll"
0x18000c55e  mov     edx, edi; cchDest
0x18000c560  lea     rcx, [rsp+268h+Buffer]; pszDest
0x18000c565  call    StringCchCatW
0x18000c56a  test    eax, eax
0x18000c56c  js      loc_18000C5FD
0x18000c572  lea     rcx, [rsp+268h+Buffer]; lpLibFileName
0x18000c577  call    cs:__imp_LoadLibraryW
0x18000c57d  mov     rdi, rax
0x18000c580  test    rax, rax
0x18000c583  jz      short loc_18000C5FD
0x18000c585  lea     rdx, aGetpermlayers; "GetPermLayers"
0x18000c58c  mov     rcx, rax; hModule
0x18000c58f  call    cs:__imp_GetProcAddress
0x18000c595  lea     rdx, aSetpermlayers; "SetPermLayers"
0x18000c59c  mov     rcx, rdi; hModule
0x18000c59f  mov     rbp, rax
0x18000c5a2  call    cs:__imp_GetProcAddress
0x18000c5a8  lea     rdx, aSetpermlayerst; "SetPermLayerState"
0x18000c5af  mov     rcx, rdi; hModule
0x18000c5b2  mov     rsi, rax
0x18000c5b5  call    cs:__imp_GetProcAddress
0x18000c5bb  mov     r14, rax
0x18000c5be  test    rbp, rbp
0x18000c5c1  jz      short loc_18000C5FD
0x18000c5c3  test    rsi, rsi
0x18000c5c6  jz      short loc_18000C5FD
0x18000c5c8  mov     rcx, rbp; Ptr
0x18000c5cb  call    cs:__imp_EncodePointer
0x18000c5d1  mov     rcx, rsi; Ptr
0x18000c5d4  mov     cs:?g_pfnGetPermLayers@@3P6AHPEBGPEAGPEAKK@ZEA, rax; int (*g_pfnGetPermLayers)(ushort const *,ushort *,ulong *,ulong)
0x18000c5db  call    cs:__imp_EncodePointer
0x18000c5e1  mov     rcx, r14; Ptr
0x18000c5e4  call    cs:__imp_EncodePointer
0x18000c5ea  mov     cs:?g_pfnSetPermLayerState@@3P6AHPEBG0KHH@ZEA, rax; int (*g_pfnSetPermLayerState)(ushort const *,ushort const *,ulong,int,int)
0x18000c5f1  mov     cs:?g_hAppHelp@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hAppHelp
0x18000c5f8  mov     ebx, 1
0x18000c5fd  mov     eax, ebx
0x18000c5ff  mov     rcx, [rsp+268h+var_38]
0x18000c607  xor     rcx, rsp; StackCookie
0x18000c60a  call    __security_check_cookie
0x18000c60f  add     rsp, 240h
0x18000c616  pop     r14
0x18000c618  pop     rdi
0x18000c619  pop     rsi
0x18000c61a  pop     rbp
0x18000c61b  pop     rbx
0x18000c61c  retn
```

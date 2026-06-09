# IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))

- ea: `0x18007e680`
- end: `0x18007e719`
- name: `?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z`
- size: `153`
- prototype: `bool __fastcall(LPCSTR lpProcName, HINSTANCE *, __int64 (**)(void))`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007f330`
- `0x18007f540`
- `0x18007faa0`
- `0x180080a50`

## callees

- `0x18001f660`
- `0x18003e8f8`
- `0x18007e680`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18007e6d3`
- `KERNEL32!GetProcAddress` at `0x18007e6d3`
- `KERNEL32!LoadLibraryExW` at `0x18007e6aa`
- `KERNEL32!LoadLibraryExW` at `0x18007e6aa`

## string_xrefs

- `0x18007e69d`: `UnionFSAPI.dll`

## pseudocode

```c
char __fastcall IsOverlayAPISupported(LPCSTR lpProcName, HINSTANCE *a2, __int64 (**a3)(void))
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  __int64 (*ProcAddress)(void); // rax
  char v9; // bl
  HMODULE hModule; // [rsp+68h] [rbp+20h] BYREF

  hModule = 0;
  Library = LoadLibraryExW(L"UnionFSAPI.dll", 0, 0x800u);
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(&hModule, Library);
  v7 = hModule;
  if ( hModule && (ProcAddress = GetProcAddress(hModule, lpProcName)) != 0 )
  {
    if ( a2 )
    {
      hModule = 0;
      *a2 = v7;
    }
    if ( a3 )
      *a3 = ProcAddress;
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  return v9;
}

```

## disassembly

```asm
0x18007e680  push    rbx
0x18007e682  push    rbp
0x18007e683  push    rsi
0x18007e684  push    rdi
0x18007e685  sub     rsp, 28h
0x18007e689  mov     rbx, r8
0x18007e68c  mov     [rsp+48h+hModule], 0
0x18007e695  mov     rsi, rdx
0x18007e698  mov     rbp, rcx
0x18007e69b  xor     edx, edx; hFile
0x18007e69d  lea     rcx, aUnionfsapiDll; "UnionFSAPI.dll"
0x18007e6a4  mov     r8d, 800h; dwFlags
0x18007e6aa  call    cs:__imp_LoadLibraryExW
0x18007e6b1  nop     dword ptr [rax+rax+00h]
0x18007e6b6  mov     rdx, rax
0x18007e6b9  lea     rcx, [rsp+48h+hModule]
0x18007e6be  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18007e6c3  mov     rdi, [rsp+48h+hModule]
0x18007e6c8  test    rdi, rdi
0x18007e6cb  jz      short loc_18007E701
0x18007e6cd  mov     rdx, rbp; lpProcName
0x18007e6d0  mov     rcx, rdi; hModule
0x18007e6d3  call    cs:__imp_GetProcAddress
0x18007e6da  nop     dword ptr [rax+rax+00h]
0x18007e6df  test    rax, rax
0x18007e6e2  jz      short loc_18007E701
0x18007e6e4  test    rsi, rsi
0x18007e6e7  jz      short loc_18007E6F5
0x18007e6e9  mov     [rsp+48h+hModule], 0
0x18007e6f2  mov     [rsi], rdi
0x18007e6f5  test    rbx, rbx
0x18007e6f8  jz      short loc_18007E6FD
0x18007e6fa  mov     [rbx], rax
0x18007e6fd  mov     bl, 1
0x18007e6ff  jmp     short loc_18007E703
0x18007e701  xor     ebx, ebx
0x18007e703  lea     rcx, [rsp+48h+hModule]
0x18007e708  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007e70d  mov     al, bl
0x18007e70f  add     rsp, 28h
0x18007e713  pop     rdi
0x18007e714  pop     rsi
0x18007e715  pop     rbp
0x18007e716  pop     rbx
0x18007e717  retn
```

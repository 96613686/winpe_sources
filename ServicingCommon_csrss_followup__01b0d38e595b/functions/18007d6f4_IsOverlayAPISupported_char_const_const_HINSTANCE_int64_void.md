# IsOverlayAPISupported(char const * const,HINSTANCE__ * *,__int64 (**)(void))

- ea: `0x18007d6f4`
- end: `0x18007d78d`
- name: `?IsOverlayAPISupported@@YA_NQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z`
- size: `153`
- prototype: `bool __fastcall(LPCSTR lpProcName, HINSTANCE *, __int64 (**)(void))`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007e3b0`
- `0x18007e5c0`
- `0x18007eb20`
- `0x18007fae0`

## callees

- `0x180020dc0`
- `0x180023664`
- `0x18007d6f4`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18007d71e`
- `KERNEL32!LoadLibraryExW` at `0x18007d71e`
- `KERNEL32!GetProcAddress` at `0x18007d747`
- `KERNEL32!GetProcAddress` at `0x18007d747`

## string_xrefs

- `0x18007d711`: `UnionFSAPI.dll`

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
0x18007d6f4  push    rbx
0x18007d6f6  push    rbp
0x18007d6f7  push    rsi
0x18007d6f8  push    rdi
0x18007d6f9  sub     rsp, 28h
0x18007d6fd  mov     rbx, r8
0x18007d700  mov     [rsp+48h+hModule], 0
0x18007d709  mov     rsi, rdx
0x18007d70c  mov     rbp, rcx
0x18007d70f  xor     edx, edx; hFile
0x18007d711  lea     rcx, aUnionfsapiDll; "UnionFSAPI.dll"
0x18007d718  mov     r8d, 800h; dwFlags
0x18007d71e  call    cs:__imp_LoadLibraryExW
0x18007d725  nop     dword ptr [rax+rax+00h]
0x18007d72a  mov     rdx, rax
0x18007d72d  lea     rcx, [rsp+48h+hModule]
0x18007d732  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x18007d737  mov     rdi, [rsp+48h+hModule]
0x18007d73c  test    rdi, rdi
0x18007d73f  jz      short loc_18007D775
0x18007d741  mov     rdx, rbp; lpProcName
0x18007d744  mov     rcx, rdi; hModule
0x18007d747  call    cs:__imp_GetProcAddress
0x18007d74e  nop     dword ptr [rax+rax+00h]
0x18007d753  test    rax, rax
0x18007d756  jz      short loc_18007D775
0x18007d758  test    rsi, rsi
0x18007d75b  jz      short loc_18007D769
0x18007d75d  mov     [rsp+48h+hModule], 0
0x18007d766  mov     [rsi], rdi
0x18007d769  test    rbx, rbx
0x18007d76c  jz      short loc_18007D771
0x18007d76e  mov     [rbx], rax
0x18007d771  mov     bl, 1
0x18007d773  jmp     short loc_18007D777
0x18007d775  xor     ebx, ebx
0x18007d777  lea     rcx, [rsp+48h+hModule]
0x18007d77c  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18007d781  mov     al, bl
0x18007d783  add     rsp, 28h
0x18007d787  pop     rdi
0x18007d788  pop     rsi
0x18007d789  pop     rbp
0x18007d78a  pop     rbx
0x18007d78b  retn
```

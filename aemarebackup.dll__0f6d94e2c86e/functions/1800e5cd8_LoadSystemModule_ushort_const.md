# _LoadSystemModule(ushort const *)

- ea: `0x1800e5cd8`
- end: `0x1800e5d8c`
- name: `?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z`
- size: `180`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800e4d00`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000719c`
- `0x18000d62c`
- `0x1800e5cd8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e5d69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e5d69`

## pseudocode

```c
HINSTANCE __fastcall _LoadSystemModule(const unsigned __int16 *a1)
{
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR LibFileName[264]; // [rsp+240h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  if ( GetSystemDirectoryW_0(Buffer, 0x104u) - 1 > 0x102
    || (int)StringCchPrintfW(LibFileName, 0x104u, L"%s\\%s", Buffer, a1) < 0 )
  {
    return 0;
  }
  else
  {
    return LoadLibraryExW(LibFileName, 0, 0);
  }
}

```

## disassembly

```asm
0x1800e5cd8  push    rbx
0x1800e5cda  sub     rsp, 460h
0x1800e5ce1  mov     rax, cs:__security_cookie
0x1800e5ce8  xor     rax, rsp
0x1800e5ceb  mov     [rsp+468h+var_18], rax
0x1800e5cf3  mov     rbx, rcx
0x1800e5cf6  xor     edx, edx; Val
0x1800e5cf8  lea     rcx, [rsp+468h+Buffer]; void *
0x1800e5cfd  mov     r8d, 208h; Size
0x1800e5d03  call    memset_0
0x1800e5d08  xor     edx, edx; Val
0x1800e5d0a  lea     rcx, [rsp+468h+LibFileName]; void *
0x1800e5d12  mov     r8d, 208h; Size
0x1800e5d18  call    memset_0
0x1800e5d1d  mov     edx, 104h; uSize
0x1800e5d22  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x1800e5d27  call    GetSystemDirectoryW_0
0x1800e5d2c  dec     eax
0x1800e5d2e  cmp     eax, 102h
0x1800e5d33  ja      short loc_1800E5D71
0x1800e5d35  lea     r9, [rsp+468h+Buffer]
0x1800e5d3a  mov     [rsp+468h+var_448], rbx
0x1800e5d3f  lea     r8, aSS_1; "%s\\%s"
0x1800e5d46  mov     edx, 104h; unsigned __int64
0x1800e5d4b  lea     rcx, [rsp+468h+LibFileName]; unsigned __int16 *
0x1800e5d53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e5d58  test    eax, eax
0x1800e5d5a  js      short loc_1800E5D71
0x1800e5d5c  xor     r8d, r8d; dwFlags
0x1800e5d5f  lea     rcx, [rsp+468h+LibFileName]; lpLibFileName
0x1800e5d67  xor     edx, edx; hFile
0x1800e5d69  call    cs:__imp_LoadLibraryExW
0x1800e5d6f  jmp     short loc_1800E5D73
0x1800e5d71  xor     eax, eax
0x1800e5d73  mov     rcx, [rsp+468h+var_18]
0x1800e5d7b  xor     rcx, rsp; StackCookie
0x1800e5d7e  call    __security_check_cookie
0x1800e5d83  add     rsp, 460h
0x1800e5d8a  pop     rbx
0x1800e5d8b  retn
```

# mlib::WinBrand::LoadLibraryW(void)

- ea: `0x140056d9c`
- end: `0x140056e00`
- name: `?LoadLibraryW@WinBrand@mlib@@QEAAKXZ`
- size: `100`
- prototype: `unsigned int __fastcall(mlib::WinBrand *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14002ac4c`

## callees

- `0x140056d9c`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140056dd0`
- `KERNEL32!GetProcAddress` at `0x140056de9`
- `KERNEL32!GetProcAddress` at `0x140056dd0`
- `KERNEL32!GetProcAddress` at `0x140056de9`
- `KERNEL32!LoadLibraryW` at `0x140056dac`
- `KERNEL32!LoadLibraryW` at `0x140056dac`
- `KERNEL32!GetLastError` at `0x140056dbf`

## string_xrefs

- `0x140056da5`: `winbrand.dll`

## pseudocode

```c
DWORD __fastcall mlib::WinBrand::LoadLibraryW(mlib::WinBrand *this)
{
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  LibraryW = LoadLibraryW(L"winbrand.dll");
  *(_QWORD *)this = LibraryW;
  if ( LibraryW
    && (ProcAddress = GetProcAddress(LibraryW, "BrandingLoadString"), (*((_QWORD *)this + 1) = ProcAddress) != 0)
    && (v5 = GetProcAddress(*(HMODULE *)this, "BrandingFormatString"), (*((_QWORD *)this + 2) = v5) != 0) )
  {
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x140056d9c  push    rbx
0x140056d9e  sub     rsp, 20h
0x140056da2  mov     rbx, rcx
0x140056da5  lea     rcx, aWinbrandDll; "winbrand.dll"
0x140056dac  call    cs:__imp_LoadLibraryW
0x140056db2  mov     [rbx], rax
0x140056db5  test    rax, rax
0x140056db8  jnz     short loc_140056DC6
0x140056dba  add     rsp, 20h
0x140056dbe  pop     rbx
0x140056dbf  jmp     cs:__imp_GetLastError
0x140056dc6  lea     rdx, aBrandingloadst; "BrandingLoadString"
0x140056dcd  mov     rcx, rax; hModule
0x140056dd0  call    cs:__imp_GetProcAddress
0x140056dd6  mov     [rbx+8], rax
0x140056dda  test    rax, rax
0x140056ddd  jz      short loc_140056DBA
0x140056ddf  mov     rcx, [rbx]; hModule
0x140056de2  lea     rdx, aBrandingformat; "BrandingFormatString"
0x140056de9  call    cs:__imp_GetProcAddress
0x140056def  mov     [rbx+10h], rax
0x140056df3  test    rax, rax
0x140056df6  jz      short loc_140056DBA
0x140056df8  xor     eax, eax
0x140056dfa  add     rsp, 20h
0x140056dfe  pop     rbx
0x140056dff  retn
```

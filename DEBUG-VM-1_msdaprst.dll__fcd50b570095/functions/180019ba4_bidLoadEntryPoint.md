# _bidLoadEntryPoint

- ea: `0x180019ba4`
- end: `0x180019c42`
- name: `_bidLoadEntryPoint`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019f80`

## callees

- `0x180019ba4`
- `0x180019ee4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180019bc9`
- `msvcrt!_wcsicmp` at `0x180019bc9`
- `KERNEL32!GetProcAddress` at `0x180019c12`
- `KERNEL32!GetProcAddress` at `0x180019c12`
- `KERNEL32!LoadLibraryExW` at `0x180019be2`
- `KERNEL32!LoadLibraryExW` at `0x180019be2`

## string_xrefs

- `0x180019bbf`: `MSDADIAG.dll`
- `0x180019bdb`: `MSDADIAG.dll`
- `0x180019c08`: `DllBidEntryPoint`

## pseudocode

```c
FARPROC bidLoadEntryPoint()
{
  LPCWSTR v0; // rbx
  DWORD v1; // r8d
  const WCHAR *v2; // rcx
  HMODULE Library; // rax
  FARPROC result; // rax

  v0 = lpOutputString;
  if ( lpOutputString
    && (!dword_180045794
      ? (Library = hLibModule)
      : (_wcsicmp(lpOutputString, L"MSDADIAG.dll") ? (v1 = 8, v2 = v0) : (v1 = 2048, v2 = L"MSDADIAG.dll"),
         Library = LoadLibraryExW(v2, 0, v1),
         hLibModule = Library),
        Library) )
  {
    result = GetProcAddress(Library, "DllBidEntryPoint");
    bidpEntryPoint = result;
    if ( !result )
      return (FARPROC)bidUnloadEntryPoint();
  }
  else
  {
    result = (FARPROC)ImplBidEntryPoint;
    bidpEntryPoint = ImplBidEntryPoint;
  }
  return result;
}

```

## disassembly

```asm
0x180019ba4  push    rbx
0x180019ba6  sub     rsp, 20h
0x180019baa  mov     rbx, cs:lpOutputString
0x180019bb1  test    rbx, rbx
0x180019bb4  jz      short loc_180019C2E
0x180019bb6  cmp     cs:dword_180045794, 0
0x180019bbd  jz      short loc_180019BFC
0x180019bbf  lea     rdx, aMsdadiagDll; "MSDADIAG.dll"
0x180019bc6  mov     rcx, rbx; String1
0x180019bc9  call    cs:__imp__wcsicmp
0x180019bcf  xor     edx, edx; hFile
0x180019bd1  test    eax, eax
0x180019bd3  jnz     short loc_180019BF1
0x180019bd5  mov     r8d, 800h; dwFlags
0x180019bdb  lea     rcx, aMsdadiagDll; "MSDADIAG.dll"
0x180019be2  call    cs:__imp_LoadLibraryExW
0x180019be8  mov     cs:hLibModule, rax
0x180019bef  jmp     short loc_180019C03
0x180019bf1  mov     r8d, 8
0x180019bf7  mov     rcx, rbx
0x180019bfa  jmp     short loc_180019BE2
0x180019bfc  mov     rax, cs:hLibModule
0x180019c03  test    rax, rax
0x180019c06  jz      short loc_180019C2E
0x180019c08  lea     rdx, ProcName; "DllBidEntryPoint"
0x180019c0f  mov     rcx, rax; hModule
0x180019c12  call    cs:__imp_GetProcAddress
0x180019c18  mov     cs:_bidpEntryPoint, rax
0x180019c1f  test    rax, rax
0x180019c22  jnz     short loc_180019C3C
0x180019c24  add     rsp, 20h
0x180019c28  pop     rbx
0x180019c29  jmp     _bidUnloadEntryPoint
0x180019c2e  lea     rax, ImplBidEntryPoint
0x180019c35  mov     cs:_bidpEntryPoint, rax
0x180019c3c  add     rsp, 20h
0x180019c40  pop     rbx
0x180019c41  retn
```

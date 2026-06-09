# _LoadSharedIconFromDll(ushort const *,int)

- ea: `0x18000855c`
- end: `0x1800085e0`
- name: `?_LoadSharedIconFromDll@@YAPEAUHICON__@@PEBGH@Z`
- size: `132`
- prototype: `HANDLE __fastcall(const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800085e8`

## callees

- `0x18000855c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800085c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800085c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000857c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000857c`
- `USER32!LoadImageW` at `0x1800085bb`
- `USER32!LoadImageW` at `0x1800085bb`
- `USER32!GetSystemMetrics` at `0x18000858d`
- `USER32!GetSystemMetrics` at `0x18000859a`
- `USER32!GetSystemMetrics` at `0x18000858d`
- `USER32!GetSystemMetrics` at `0x18000859a`

## string_xrefs

- `0x18000856d`: `imageres.dll`

## pseudocode

```c
HANDLE __fastcall _LoadSharedIconFromDll(const unsigned __int16 *a1, unsigned __int16 a2)
{
  HANDLE ImageW; // rbx
  HMODULE Library; // rdi
  int cy; // ebx
  int SystemMetrics; // eax

  ImageW = 0;
  Library = LoadLibraryExW(L"imageres.dll", 0, 2u);
  if ( Library )
  {
    cy = GetSystemMetrics(50);
    SystemMetrics = GetSystemMetrics(49);
    ImageW = LoadImageW(Library, (LPCWSTR)a2, 1u, SystemMetrics, cy, 0x8000u);
    FreeLibrary(Library);
  }
  return ImageW;
}

```

## disassembly

```asm
0x18000855c  mov     [rsp+arg_0], rbx
0x180008561  mov     [rsp+arg_8], rsi
0x180008566  push    rdi
0x180008567  sub     rsp, 30h
0x18000856b  mov     esi, edx
0x18000856d  lea     rcx, LibFileName; "imageres.dll"
0x180008574  xor     ebx, ebx
0x180008576  xor     edx, edx; hFile
0x180008578  lea     r8d, [rbx+2]; dwFlags
0x18000857c  call    cs:__imp_LoadLibraryExW
0x180008582  mov     rdi, rax
0x180008585  test    rax, rax
0x180008588  jz      short loc_1800085CD
0x18000858a  lea     ecx, [rbx+32h]; nIndex
0x18000858d  call    cs:__imp_GetSystemMetrics
0x180008593  mov     ecx, 31h ; '1'; nIndex
0x180008598  mov     ebx, eax
0x18000859a  call    cs:__imp_GetSystemMetrics
0x1800085a0  movzx   edx, si; name
0x1800085a3  mov     r8d, 1; type
0x1800085a9  mov     r9d, eax; cx
0x1800085ac  mov     [rsp+38h+fuLoad], 8000h; fuLoad
0x1800085b4  mov     rcx, rdi; hInst
0x1800085b7  mov     [rsp+38h+cy], ebx; cy
0x1800085bb  call    cs:__imp_LoadImageW
0x1800085c1  mov     rcx, rdi; hLibModule
0x1800085c4  mov     rbx, rax
0x1800085c7  call    cs:__imp_FreeLibrary
0x1800085cd  mov     rsi, [rsp+38h+arg_8]
0x1800085d2  mov     rax, rbx
0x1800085d5  mov     rbx, [rsp+38h+arg_0]
0x1800085da  add     rsp, 30h
0x1800085de  pop     rdi
0x1800085df  retn
```

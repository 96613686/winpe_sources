# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x1800237fc`
- end: `0x1800238a8`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800260a4`
- `0x180026334`

## callees

- `0x1800237fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002384f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002387b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002384f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002387b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023823`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180023823`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002383c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023868`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002383c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023868`

## string_xrefs

- `0x180023816`: `aepic.dll`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  char v2; // di
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  v2 = 1;
  if ( !*(_BYTE *)this )
  {
    *(_BYTE *)this = 1;
    Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
    *((_QWORD *)this + 1) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "PicRetrieveFileInfo");
      *((_QWORD *)this + 2) = ProcAddress;
      if ( !ProcAddress )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
      v5 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
      *((_QWORD *)this + 3) = v5;
      if ( !v5 )
      {
        FreeLibrary(*((HMODULE *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
    }
  }
  if ( !*((_QWORD *)this + 2) || !*((_QWORD *)this + 3) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1800237fc  mov     [rsp+arg_0], rbx
0x180023801  push    rdi
0x180023802  sub     rsp, 20h
0x180023806  cmp     byte ptr [rcx], 0
0x180023809  mov     rbx, rcx
0x18002380c  mov     dil, 1
0x18002380f  jnz     short loc_180023889
0x180023811  mov     [rcx], dil
0x180023814  xor     edx, edx; hFile
0x180023816  lea     rcx, aAepicDll; "aepic.dll"
0x18002381d  mov     r8d, 800h; dwFlags
0x180023823  call    cs:__imp_LoadLibraryExW
0x180023829  mov     [rbx+8], rax
0x18002382d  test    rax, rax
0x180023830  jz      short loc_180023889
0x180023832  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x180023839  mov     rcx, rax; hModule
0x18002383c  call    cs:__imp_GetProcAddress
0x180023842  mov     [rbx+10h], rax
0x180023846  test    rax, rax
0x180023849  jnz     short loc_18002385D
0x18002384b  mov     rcx, [rbx+8]; hLibModule
0x18002384f  call    cs:__imp_FreeLibrary
0x180023855  mov     qword ptr [rbx+8], 0
0x18002385d  mov     rcx, [rbx+8]; hModule
0x180023861  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180023868  call    cs:__imp_GetProcAddress
0x18002386e  mov     [rbx+18h], rax
0x180023872  test    rax, rax
0x180023875  jnz     short loc_180023889
0x180023877  mov     rcx, [rbx+8]; hLibModule
0x18002387b  call    cs:__imp_FreeLibrary
0x180023881  mov     qword ptr [rbx+8], 0
0x180023889  cmp     qword ptr [rbx+10h], 0
0x18002388e  jz      short loc_180023897
0x180023890  cmp     qword ptr [rbx+18h], 0
0x180023895  jnz     short loc_18002389A
0x180023897  xor     dil, dil
0x18002389a  mov     rbx, [rsp+28h+arg_0]
0x18002389f  mov     al, dil
0x1800238a2  add     rsp, 20h
0x1800238a6  pop     rdi
0x1800238a7  retn
```

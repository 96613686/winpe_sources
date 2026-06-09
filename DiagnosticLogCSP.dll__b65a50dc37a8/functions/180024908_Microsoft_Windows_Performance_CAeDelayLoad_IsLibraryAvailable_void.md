# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x180024908`
- end: `0x1800249d7`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `207`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027280`
- `0x180027508`

## callees

- `0x180024908`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002496b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800249a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002496b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800249a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024933`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024933`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002498a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024952`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002498a`

## string_xrefs

- `0x180024926`: `aepic.dll`

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
0x180024908  mov     [rsp+arg_0], rbx
0x18002490d  push    rdi
0x18002490e  sub     rsp, 20h
0x180024912  cmp     byte ptr [rcx], 0
0x180024915  mov     rbx, rcx
0x180024918  mov     dil, 1
0x18002491b  jnz     loc_1800249B7
0x180024921  mov     [rcx], dil
0x180024924  xor     edx, edx; hFile
0x180024926  lea     rcx, aAepicDll; "aepic.dll"
0x18002492d  mov     r8d, 800h; dwFlags
0x180024933  call    cs:__imp_LoadLibraryExW
0x18002493a  nop     dword ptr [rax+rax+00h]
0x18002493f  mov     [rbx+8], rax
0x180024943  test    rax, rax
0x180024946  jz      short loc_1800249B7
0x180024948  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x18002494f  mov     rcx, rax; hModule
0x180024952  call    cs:__imp_GetProcAddress
0x180024959  nop     dword ptr [rax+rax+00h]
0x18002495e  mov     [rbx+10h], rax
0x180024962  test    rax, rax
0x180024965  jnz     short loc_18002497F
0x180024967  mov     rcx, [rbx+8]; hLibModule
0x18002496b  call    cs:__imp_FreeLibrary
0x180024972  nop     dword ptr [rax+rax+00h]
0x180024977  mov     qword ptr [rbx+8], 0
0x18002497f  mov     rcx, [rbx+8]; hModule
0x180024983  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x18002498a  call    cs:__imp_GetProcAddress
0x180024991  nop     dword ptr [rax+rax+00h]
0x180024996  mov     [rbx+18h], rax
0x18002499a  test    rax, rax
0x18002499d  jnz     short loc_1800249B7
0x18002499f  mov     rcx, [rbx+8]; hLibModule
0x1800249a3  call    cs:__imp_FreeLibrary
0x1800249aa  nop     dword ptr [rax+rax+00h]
0x1800249af  mov     qword ptr [rbx+8], 0
0x1800249b7  cmp     qword ptr [rbx+10h], 0
0x1800249bc  jz      short loc_1800249C5
0x1800249be  cmp     qword ptr [rbx+18h], 0
0x1800249c3  jnz     short loc_1800249C8
0x1800249c5  xor     dil, dil
0x1800249c8  mov     rbx, [rsp+28h+arg_0]
0x1800249cd  mov     al, dil
0x1800249d0  add     rsp, 20h
0x1800249d4  pop     rdi
0x1800249d5  retn
```

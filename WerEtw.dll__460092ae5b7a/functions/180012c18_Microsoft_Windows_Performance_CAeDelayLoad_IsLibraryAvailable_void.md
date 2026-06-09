# Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)

- ea: `0x180012c18`
- end: `0x180012cc4`
- name: `?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ`
- size: `172`
- prototype: `bool __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014fd4`
- `0x180015264`

## callees

- `0x180012c18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012c97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012c3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012c3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012c84`

## string_xrefs

- `0x180012c32`: `aepic.dll`

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
0x180012c18  mov     [rsp+arg_0], rbx
0x180012c1d  push    rdi
0x180012c1e  sub     rsp, 20h
0x180012c22  cmp     byte ptr [rcx], 0
0x180012c25  mov     rbx, rcx
0x180012c28  mov     dil, 1
0x180012c2b  jnz     short loc_180012CA5
0x180012c2d  mov     [rcx], dil
0x180012c30  xor     edx, edx; hFile
0x180012c32  lea     rcx, aAepicDll; "aepic.dll"
0x180012c39  mov     r8d, 800h; dwFlags
0x180012c3f  call    cs:__imp_LoadLibraryExW
0x180012c45  mov     [rbx+8], rax
0x180012c49  test    rax, rax
0x180012c4c  jz      short loc_180012CA5
0x180012c4e  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x180012c55  mov     rcx, rax; hModule
0x180012c58  call    cs:__imp_GetProcAddress
0x180012c5e  mov     [rbx+10h], rax
0x180012c62  test    rax, rax
0x180012c65  jnz     short loc_180012C79
0x180012c67  mov     rcx, [rbx+8]; hLibModule
0x180012c6b  call    cs:__imp_FreeLibrary
0x180012c71  mov     qword ptr [rbx+8], 0
0x180012c79  mov     rcx, [rbx+8]; hModule
0x180012c7d  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x180012c84  call    cs:__imp_GetProcAddress
0x180012c8a  mov     [rbx+18h], rax
0x180012c8e  test    rax, rax
0x180012c91  jnz     short loc_180012CA5
0x180012c93  mov     rcx, [rbx+8]; hLibModule
0x180012c97  call    cs:__imp_FreeLibrary
0x180012c9d  mov     qword ptr [rbx+8], 0
0x180012ca5  cmp     qword ptr [rbx+10h], 0
0x180012caa  jz      short loc_180012CB3
0x180012cac  cmp     qword ptr [rbx+18h], 0
0x180012cb1  jnz     short loc_180012CB6
0x180012cb3  xor     dil, dil
0x180012cb6  mov     rbx, [rsp+28h+arg_0]
0x180012cbb  mov     al, dil
0x180012cbe  add     rsp, 20h
0x180012cc2  pop     rdi
0x180012cc3  retn
```

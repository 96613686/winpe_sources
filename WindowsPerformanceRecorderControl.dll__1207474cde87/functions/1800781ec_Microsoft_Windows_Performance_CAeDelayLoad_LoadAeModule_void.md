# Microsoft::Windows::Performance::CAeDelayLoad::LoadAeModule(void)

- ea: `0x1800781ec`
- end: `0x180078277`
- name: `?LoadAeModule@CAeDelayLoad@Performance@Windows@Microsoft@@AEAAPEAUHINSTANCE__@@XZ`
- size: `139`
- prototype: `HINSTANCE __fastcall(Microsoft::Windows::Performance::CAeDelayLoad *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010510`
- `0x180033cec`

## callees

- `0x1800781ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180078233`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007825f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180078233`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18007825f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180078220`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007824c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180078220`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007824c`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180078207`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180078207`

## string_xrefs

- `0x1800781f8`: `aepic.dll`

## pseudocode

```c
HINSTANCE __fastcall Microsoft::Windows::Performance::CAeDelayLoad::LoadAeModule(
        Microsoft::Windows::Performance::CAeDelayLoad *this)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rax

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
    v4 = GetProcAddress(*((HMODULE *)this + 1), "PicFreeFileInfo");
    *((_QWORD *)this + 3) = v4;
    if ( !v4 )
    {
      FreeLibrary(*((HMODULE *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
  }
  return (HINSTANCE)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1800781ec  push    rbx
0x1800781ee  sub     rsp, 20h
0x1800781f2  mov     rbx, rcx
0x1800781f5  mov     byte ptr [rcx], 1
0x1800781f8  lea     rcx, aAepicDll; "aepic.dll"
0x1800781ff  xor     edx, edx; hFile
0x180078201  mov     r8d, 800h; dwFlags
0x180078207  call    cs:__imp_LoadLibraryExW
0x18007820d  mov     [rbx+8], rax
0x180078211  test    rax, rax
0x180078214  jz      short loc_18007826D
0x180078216  lea     rdx, aPicretrievefil; "PicRetrieveFileInfo"
0x18007821d  mov     rcx, rax; hModule
0x180078220  call    cs:__imp_GetProcAddress
0x180078226  mov     [rbx+10h], rax
0x18007822a  test    rax, rax
0x18007822d  jnz     short loc_180078241
0x18007822f  mov     rcx, [rbx+8]; hLibModule
0x180078233  call    cs:__imp_FreeLibrary
0x180078239  mov     qword ptr [rbx+8], 0
0x180078241  mov     rcx, [rbx+8]; hModule
0x180078245  lea     rdx, aPicfreefileinf; "PicFreeFileInfo"
0x18007824c  call    cs:__imp_GetProcAddress
0x180078252  mov     [rbx+18h], rax
0x180078256  test    rax, rax
0x180078259  jnz     short loc_18007826D
0x18007825b  mov     rcx, [rbx+8]; hLibModule
0x18007825f  call    cs:__imp_FreeLibrary
0x180078265  mov     qword ptr [rbx+8], 0
0x18007826d  mov     rax, [rbx+8]
0x180078271  add     rsp, 20h
0x180078275  pop     rbx
0x180078276  retn
```

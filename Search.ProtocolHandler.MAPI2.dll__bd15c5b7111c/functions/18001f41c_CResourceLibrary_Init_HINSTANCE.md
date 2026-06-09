# CResourceLibrary::Init(HINSTANCE__ *)

- ea: `0x18001f41c`
- end: `0x18001f4b5`
- name: `?Init@CResourceLibrary@@QEAAXPEAUHINSTANCE__@@@Z`
- size: `153`
- prototype: `void __fastcall(CResourceLibrary *this, HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001ed24`

## callees

- `0x180002300`
- `0x18000306c`
- `0x18001cb98`
- `0x1800399f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f477`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f477`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f45a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f45a`

## pseudocode

```c
void __fastcall CResourceLibrary::Init(CResourceLibrary *this, HINSTANCE a2)
{
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  GetModuleFileNameW(a2, Filename, 0x104u);
  CResourceLibrary::FreeLibs((CResourceLibrary *)&qword_18005A450);
  qword_18005A450 = LoadLibraryExW(Filename, 0, 2u);
  qword_18005A458 = (__int64)LoadMUILibraryW(Filename, 8u, 0);
}

```

## disassembly

```asm
0x18001f41c  push    rbx
0x18001f41e  sub     rsp, 240h
0x18001f425  mov     rax, cs:__security_cookie
0x18001f42c  xor     rax, rsp
0x18001f42f  mov     [rsp+248h+var_18], rax
0x18001f437  mov     rbx, rdx
0x18001f43a  lea     rcx, [rsp+248h+Filename]; void *
0x18001f43f  xor     edx, edx; Val
0x18001f441  mov     r8d, 208h; Size
0x18001f447  call    memset_0
0x18001f44c  mov     r8d, 104h; nSize
0x18001f452  lea     rdx, [rsp+248h+Filename]; lpFilename
0x18001f457  mov     rcx, rbx; hModule
0x18001f45a  call    cs:__imp_GetModuleFileNameW
0x18001f460  lea     rcx, qword_18005A450; this
0x18001f467  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x18001f46c  xor     edx, edx; hFile
0x18001f46e  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x18001f473  lea     r8d, [rdx+2]; dwFlags
0x18001f477  call    cs:__imp_LoadLibraryExW
0x18001f47d  xor     r8d, r8d; LangID
0x18001f480  lea     rcx, [rsp+248h+Filename]; pszFullModuleName
0x18001f485  mov     cs:qword_18005A450, rax
0x18001f48c  lea     edx, [r8+8]; dwLangConvention
0x18001f490  call    LoadMUILibraryW
0x18001f495  mov     cs:qword_18005A458, rax
0x18001f49c  mov     rcx, [rsp+248h+var_18]
0x18001f4a4  xor     rcx, rsp; StackCookie
0x18001f4a7  call    __security_check_cookie
0x18001f4ac  add     rsp, 240h
0x18001f4b3  pop     rbx
0x18001f4b4  retn
```

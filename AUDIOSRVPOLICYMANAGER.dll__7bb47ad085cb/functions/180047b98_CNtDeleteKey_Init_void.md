# CNtDeleteKey::Init(void)

- ea: `0x180047b98`
- end: `0x180047bf7`
- name: `?Init@CNtDeleteKey@@QEAA_NXZ`
- size: `95`
- prototype: `bool __fastcall(CNtDeleteKey *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010a00`

## callees

- `0x180047b98`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047bdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047bdf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180047bc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180047bc3`

## string_xrefs

- `0x180047bb6`: `ntdll.dll`
- `0x180047bd5`: `NtDeleteKey`

## pseudocode

```c
bool __fastcall CNtDeleteKey::Init(CNtDeleteKey *this)
{
  HMODULE Library; // rax

  if ( hLibModule && qword_180064660 )
  {
    LOBYTE(Library) = 1;
  }
  else
  {
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    hLibModule = Library;
    if ( Library )
    {
      qword_180064660 = (__int64 (__fastcall *)(_QWORD))GetProcAddress(Library, "NtDeleteKey");
      LOBYTE(Library) = qword_180064660 != 0;
    }
  }
  return (char)Library;
}

```

## disassembly

```asm
0x180047b98  sub     rsp, 28h
0x180047b9c  cmp     cs:hLibModule, 0
0x180047ba4  jz      short loc_180047BB4
0x180047ba6  cmp     cs:qword_180064660, 0
0x180047bae  jz      short loc_180047BB4
0x180047bb0  mov     al, 1
0x180047bb2  jmp     short loc_180047BF2
0x180047bb4  xor     edx, edx; hFile
0x180047bb6  lea     rcx, LibFileName; "ntdll.dll"
0x180047bbd  mov     r8d, 800h; dwFlags
0x180047bc3  call    cs:__imp_LoadLibraryExW
0x180047bc9  mov     cs:hLibModule, rax
0x180047bd0  test    rax, rax
0x180047bd3  jz      short loc_180047BF2
0x180047bd5  lea     rdx, aNtdeletekey; "NtDeleteKey"
0x180047bdc  mov     rcx, rax; hModule
0x180047bdf  call    cs:__imp_GetProcAddress
0x180047be5  test    rax, rax
0x180047be8  mov     cs:qword_180064660, rax
0x180047bef  setnz   al
0x180047bf2  add     rsp, 28h
0x180047bf6  retn
```

# CResourceLibrary::Init(wchar_t const *)

- ea: `0x14002849c`
- end: `0x1400284e1`
- name: `?Init@CResourceLibrary@@QEAAXPEB_W@Z`
- size: `69`
- prototype: `void(CResourceLibrary *__hidden this, const wchar_t *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400283a0`
- `0x140049388`
- `0x140049454`
- `0x140049520`

## callees

- `0x1400282dc`
- `0x14002b7e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400284ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400284ba`

## pseudocode

```c
void __fastcall CResourceLibrary::Init(CResourceLibrary *this, const wchar_t *a2)
{
  CResourceLibrary::FreeLibs(this);
  *(_QWORD *)this = LoadLibraryExW(a2, 0, 2u);
  *((_QWORD *)this + 1) = LoadMUILibraryW(a2, 8u, 0);
}

```

## disassembly

```asm
0x14002849c  mov     [rsp+arg_0], rbx
0x1400284a1  push    rdi
0x1400284a2  sub     rsp, 20h
0x1400284a6  mov     rbx, rdx
0x1400284a9  mov     rdi, rcx
0x1400284ac  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x1400284b1  xor     edx, edx; hFile
0x1400284b3  mov     rcx, rbx; lpLibFileName
0x1400284b6  lea     r8d, [rdx+2]; dwFlags
0x1400284ba  call    cs:__imp_LoadLibraryExW
0x1400284c0  xor     r8d, r8d; LangID
0x1400284c3  mov     rcx, rbx; pszFullModuleName
0x1400284c6  mov     [rdi], rax
0x1400284c9  lea     edx, [r8+8]; dwLangConvention
0x1400284cd  call    LoadMUILibraryW
0x1400284d2  mov     rbx, [rsp+28h+arg_0]
0x1400284d7  mov     [rdi+8], rax
0x1400284db  add     rsp, 20h
0x1400284df  pop     rdi
0x1400284e0  retn
```

# CLoadMsi::~CLoadMsi(void)

- ea: `0x180012d38`
- end: `0x180012d4f`
- name: `??1CLoadMsi@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HMODULE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18002b013`

## callees

- `0x180012d38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012d44`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012d44`

## pseudocode

```c
void __fastcall CLoadMsi::~CLoadMsi(HMODULE *this)
{
  HMODULE v1; // rcx

  v1 = *this;
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x180012d38  sub     rsp, 28h
0x180012d3c  mov     rcx, [rcx]; hLibModule
0x180012d3f  test    rcx, rcx
0x180012d42  jz      short loc_180012D4A
0x180012d44  call    cs:__imp_FreeLibrary
0x180012d4a  add     rsp, 28h
0x180012d4e  retn
```

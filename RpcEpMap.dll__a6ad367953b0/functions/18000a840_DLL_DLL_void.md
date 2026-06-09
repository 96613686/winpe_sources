# DLL::~DLL(void)

- ea: `0x18000a840`
- end: `0x18000a857`
- name: `??1DLL@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(DLL *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a750`

## callees

- `0x18000a840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a84c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a84c`

## pseudocode

```c
void __fastcall DLL::~DLL(HMODULE *this)
{
  HMODULE v1; // rcx

  v1 = *this;
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x18000a840  sub     rsp, 28h
0x18000a844  mov     rcx, [rcx]; hLibModule
0x18000a847  test    rcx, rcx
0x18000a84a  jz      short loc_18000A852
0x18000a84c  call    cs:__imp_FreeLibrary
0x18000a852  add     rsp, 28h
0x18000a856  retn
```

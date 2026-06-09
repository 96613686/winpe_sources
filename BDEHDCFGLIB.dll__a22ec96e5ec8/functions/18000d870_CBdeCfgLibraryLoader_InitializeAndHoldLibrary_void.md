# CBdeCfgLibraryLoader::InitializeAndHoldLibrary(void)

- ea: `0x18000d870`
- end: `0x18000d88d`
- name: `?InitializeAndHoldLibrary@CBdeCfgLibraryLoader@@AEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(CBdeCfgLibraryLoader *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d9b0`

## import_xrefs

- `msvcrt!_beginthread` at `0x18000d880`
- `msvcrt!_beginthread` at `0x18000d880`

## pseudocode

```c
__int64 __fastcall CBdeCfgLibraryLoader::InitializeAndHoldLibrary(CBdeCfgLibraryLoader *this)
{
  _beginthread(CBdeCfgLibraryLoader::InitializeAndHoldLibraryEntry, 0, this);
  return 0;
}

```

## disassembly

```asm
0x18000d870  sub     rsp, 28h
0x18000d874  mov     r8, rcx; ArgList
0x18000d877  xor     edx, edx; StackSize
0x18000d879  lea     rcx, ?InitializeAndHoldLibraryEntry@CBdeCfgLibraryLoader@@CAXPEAX@Z; StartAddress
0x18000d880  call    cs:__imp__beginthread
0x18000d886  xor     eax, eax
0x18000d888  add     rsp, 28h
0x18000d88c  retn
```

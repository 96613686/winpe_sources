# MyCoUninitialize(HINSTANCE__ *,bool)

- ea: `0x180001190`
- end: `0x1800011b8`
- name: `?MyCoUninitialize@@YAXPEAUHINSTANCE__@@_N@Z`
- size: `40`
- prototype: `void __fastcall(HINSTANCE, bool)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011c0`
- `0x1800022b0`
- `0x18000ba20`

## callees

- `0x180001190`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000119f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000119f`

## pseudocode

```c
void __fastcall MyCoUninitialize(HINSTANCE a1, char a2)
{
  void (*ProcAddress)(void); // rax

  if ( a2 )
  {
    ProcAddress = (void (*)(void))GetProcAddress(a1, "CoUninitialize");
    if ( ProcAddress )
      ProcAddress();
  }
}

```

## disassembly

```asm
0x180001190  sub     rsp, 28h
0x180001194  test    dl, dl
0x180001196  jz      short loc_1800011B3
0x180001198  lea     rdx, ProcName; "CoUninitialize"
0x18000119f  call    cs:__imp_GetProcAddress
0x1800011a5  test    rax, rax
0x1800011a8  jz      short loc_1800011B3
0x1800011aa  add     rsp, 28h
0x1800011ae  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800011b3  add     rsp, 28h
0x1800011b7  retn
```

# GameInputUninitialize

- ea: `0x140007588`
- end: `0x14000764b`
- name: `GameInputUninitialize`
- size: `195`
- prototype: `void()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140007330`

## callees

- `0x140006b48`
- `0x140007588`
- `0x140008010`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x1400075a8`
- `ntdll!EtwEventUnregister` at `0x1400075a8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400075f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007605`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007617`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007629`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007640`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400075f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007605`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007617`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007629`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140007640`

## pseudocode

```c
void GameInputUninitialize()
{
  __int64 v0; // rcx
  void (**v1)(void); // rcx
  HMODULE v2; // rcx

  v0 = qword_14000E020;
  dword_14000E000 = 0;
  qword_14000E020 = 0;
  EtwEventUnregister(v0);
  v1 = (void (**)(void))P;
  if ( P )
  {
    while ( qword_14000E668 )
    {
      v1[--qword_14000E668]();
      v1 = (void (**)(void))P;
    }
    operator delete[](v1);
  }
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( qword_14000E688 )
    FreeLibrary(qword_14000E688);
  if ( qword_14000E680 )
    FreeLibrary(qword_14000E680);
  v2 = qword_14000E698;
  if ( qword_14000E698 )
  {
    FreeLibrary(qword_14000E698);
    v2 = qword_14000E698;
  }
  if ( qword_14000E678 )
    FreeLibrary(v2);
}

```

## disassembly

```asm
0x140007588  sub     rsp, 28h
0x14000758c  mov     rcx, cs:qword_14000E020
0x140007593  mov     cs:dword_14000E000, 0
0x14000759d  mov     cs:qword_14000E020, 0
0x1400075a8  call    cs:__imp_EtwEventUnregister
0x1400075ae  mov     rcx, cs:P; P
0x1400075b5  test    rcx, rcx
0x1400075b8  jz      short loc_1400075E7
0x1400075ba  mov     rax, cs:qword_14000E668
0x1400075c1  test    rax, rax
0x1400075c4  jz      short loc_1400075E2
0x1400075c6  dec     rax
0x1400075c9  mov     cs:qword_14000E668, rax
0x1400075d0  mov     rax, [rcx+rax*8]
0x1400075d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075d9  mov     rcx, cs:P
0x1400075e0  jmp     short loc_1400075BA
0x1400075e2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400075e7  mov     rcx, cs:hLibModule; hLibModule
0x1400075ee  test    rcx, rcx
0x1400075f1  jz      short loc_1400075F9
0x1400075f3  call    cs:__imp_FreeLibrary
0x1400075f9  mov     rcx, cs:qword_14000E688; hLibModule
0x140007600  test    rcx, rcx
0x140007603  jz      short loc_14000760B
0x140007605  call    cs:__imp_FreeLibrary
0x14000760b  mov     rcx, cs:qword_14000E680; hLibModule
0x140007612  test    rcx, rcx
0x140007615  jz      short loc_14000761D
0x140007617  call    cs:__imp_FreeLibrary
0x14000761d  mov     rcx, cs:qword_14000E698; hLibModule
0x140007624  test    rcx, rcx
0x140007627  jz      short loc_140007636
0x140007629  call    cs:__imp_FreeLibrary
0x14000762f  mov     rcx, cs:qword_14000E698; hLibModule
0x140007636  cmp     cs:qword_14000E678, 0
0x14000763e  jz      short loc_140007646
0x140007640  call    cs:__imp_FreeLibrary
0x140007646  add     rsp, 28h
0x14000764a  retn
```

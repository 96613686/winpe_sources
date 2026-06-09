# la_WaitForInputIdle

- ea: `0x180117268`
- end: `0x1801172f4`
- name: `la_WaitForInputIdle`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180116d0c`

## callees

- `0x180117268`
- `0x18011a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18011729b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18011729b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801172c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801172c0`

## string_xrefs

- `0x18011728e`: `user32.dll`

## pseudocode

```c
__int64 __fastcall la_WaitForInputIdle(__int64 a1)
{
  HMODULE LibraryA; // rax

  if ( dword_1801547EC )
  {
    LibraryA = (HMODULE)qword_180155C98;
  }
  else
  {
    dword_1801547EC = 1;
    if ( dword_180155CA0 )
    {
      LibraryA = (HMODULE)qword_180155CA8;
    }
    else
    {
      dword_180155CA0 = 1;
      LibraryA = LoadLibraryA("user32.dll");
      qword_180155CA8 = (__int64)LibraryA;
    }
    if ( LibraryA )
      LibraryA = (HMODULE)GetProcAddress(LibraryA, "WaitForInputIdle");
    qword_180155C98 = (__int64)LibraryA;
  }
  if ( LibraryA )
    return ((__int64 (__fastcall *)(__int64, __int64))LibraryA)(a1, 0xFFFFFFFFLL);
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180117268  push    rbx
0x18011726a  sub     rsp, 20h
0x18011726e  cmp     cs:dword_1801547EC, 0
0x180117275  mov     rbx, rcx
0x180117278  jnz     short loc_1801172CF
0x18011727a  cmp     cs:dword_180155CA0, 0
0x180117281  mov     eax, 1
0x180117286  mov     cs:dword_1801547EC, eax
0x18011728c  jnz     short loc_1801172AA
0x18011728e  lea     rcx, LibFileName; "user32.dll"
0x180117295  mov     cs:dword_180155CA0, eax
0x18011729b  call    cs:__imp_LoadLibraryA
0x1801172a1  mov     cs:qword_180155CA8, rax
0x1801172a8  jmp     short loc_1801172B1
0x1801172aa  mov     rax, cs:qword_180155CA8
0x1801172b1  test    rax, rax
0x1801172b4  jz      short loc_1801172C6
0x1801172b6  lea     rdx, ProcName; "WaitForInputIdle"
0x1801172bd  mov     rcx, rax; hModule
0x1801172c0  call    cs:__imp_GetProcAddress
0x1801172c6  mov     cs:qword_180155C98, rax
0x1801172cd  jmp     short loc_1801172D6
0x1801172cf  mov     rax, cs:qword_180155C98
0x1801172d6  test    rax, rax
0x1801172d9  jnz     short loc_1801172E4
0x1801172db  or      eax, 0FFFFFFFFh
0x1801172de  add     rsp, 20h
0x1801172e2  pop     rbx
0x1801172e3  retn
0x1801172e4  or      edx, 0FFFFFFFFh
0x1801172e7  mov     rcx, rbx
0x1801172ea  add     rsp, 20h
0x1801172ee  pop     rbx
0x1801172ef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```

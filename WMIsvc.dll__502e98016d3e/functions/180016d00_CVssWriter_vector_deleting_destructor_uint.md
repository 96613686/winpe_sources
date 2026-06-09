# CVssWriter::`vector deleting destructor'(uint)

- ea: `0x180016d00`
- end: `0x180016d30`
- name: `??_ECVssWriter@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180016c44`
- `0x180016d00`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016d1c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016d1c`

## pseudocode

```c
CVssWriter *__fastcall CVssWriter::`vector deleting destructor'(CVssWriter *this, char a2)
{
  CVssWriter::~CVssWriter(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180016d00  mov     [rsp+arg_0], rbx
0x180016d05  push    rdi
0x180016d06  sub     rsp, 20h
0x180016d0a  mov     ebx, edx
0x180016d0c  mov     rdi, rcx
0x180016d0f  call    ??1CVssWriter@@UEAA@XZ; CVssWriter::~CVssWriter(void)
0x180016d14  test    bl, 1
0x180016d17  jz      short loc_180016D22
0x180016d19  mov     rcx, rdi
0x180016d1c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180016d22  mov     rax, rdi
0x180016d25  mov     rbx, [rsp+28h+arg_0]
0x180016d2a  add     rsp, 20h
0x180016d2e  pop     rdi
0x180016d2f  retn
```

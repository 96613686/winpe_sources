# CWbemVssWriter::`scalar deleting destructor'(uint)

- ea: `0x180016d40`
- end: `0x180016d70`
- name: `??_GCWbemVssWriter@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(CWbemVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180016c90`
- `0x180016d40`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016d5c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180016d5c`

## pseudocode

```c
CWbemVssWriter *__fastcall CWbemVssWriter::`scalar deleting destructor'(CWbemVssWriter *this, char a2)
{
  CWbemVssWriter::~CWbemVssWriter(this);
  if ( (a2 & 1) != 0 )
    CWin32DefaultArena::WbemMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180016d40  mov     [rsp+arg_0], rbx
0x180016d45  push    rdi
0x180016d46  sub     rsp, 20h
0x180016d4a  mov     ebx, edx
0x180016d4c  mov     rdi, rcx
0x180016d4f  call    ??1CWbemVssWriter@@UEAA@XZ; CWbemVssWriter::~CWbemVssWriter(void)
0x180016d54  test    bl, 1
0x180016d57  jz      short loc_180016D62
0x180016d59  mov     rcx, rdi
0x180016d5c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180016d62  mov     rax, rdi
0x180016d65  mov     rbx, [rsp+28h+arg_0]
0x180016d6a  add     rsp, 20h
0x180016d6e  pop     rdi
0x180016d6f  retn
```

# ATL::CComObject<AppUtilities>::`vector deleting destructor'(uint)

- ea: `0x180020720`
- end: `0x180020788`
- name: `??_E?$CComObject@VAppUtilities@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001900`
- `0x180020720`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180020761`
- `KERNEL32!DeleteCriticalSection` at `0x180020761`

## pseudocode

```c
char *__fastcall ATL::CComObject<AppUtilities>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<AppUtilities>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180020720  mov     [rsp+arg_0], rbx
0x180020725  push    rdi
0x180020726  sub     rsp, 20h
0x18002072a  mov     dword ptr [rcx+8], 0C0000001h
0x180020731  lea     rax, ??_7?$CComObject@VAppUtilities@@@ATL@@6B@; const ATL::CComObject<AppUtilities>::`vftable'
0x180020738  mov     [rcx], rax
0x18002073b  mov     rbx, rcx
0x18002073e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020745  mov     edi, edx
0x180020747  mov     rax, [rcx]
0x18002074a  mov     rax, [rax+10h]
0x18002074e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020753  lea     rcx, [rbx+10h]; lpCriticalSection
0x180020757  cmp     byte ptr [rcx+28h], 0
0x18002075b  jz      short loc_180020767
0x18002075d  mov     byte ptr [rcx+28h], 0
0x180020761  call    cs:__imp_DeleteCriticalSection
0x180020767  test    dil, 1
0x18002076b  jz      short loc_18002077A
0x18002076d  mov     edx, 40h ; '@'
0x180020772  mov     rcx, rbx; Block
0x180020775  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002077a  mov     rax, rbx
0x18002077d  mov     rbx, [rsp+28h+arg_0]
0x180020782  add     rsp, 20h
0x180020786  pop     rdi
0x180020787  retn
```

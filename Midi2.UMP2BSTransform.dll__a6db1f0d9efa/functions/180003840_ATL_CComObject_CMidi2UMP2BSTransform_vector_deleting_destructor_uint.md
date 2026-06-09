# ATL::CComObject<CMidi2UMP2BSTransform>::`vector deleting destructor'(uint)

- ea: `0x180003840`
- end: `0x1800038a8`
- name: `??_E?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001f14`
- `0x180003840`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003881`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003881`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2UMP2BSTransform>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2UMP2BSTransform>::`vftable';
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
0x180003840  mov     [rsp+arg_0], rbx
0x180003845  push    rdi
0x180003846  sub     rsp, 20h
0x18000384a  mov     dword ptr [rcx+8], 0C0000001h
0x180003851  lea     rax, ??_7?$CComObject@VCMidi2UMP2BSTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2UMP2BSTransform>::`vftable'
0x180003858  mov     [rcx], rax
0x18000385b  mov     rbx, rcx
0x18000385e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003865  mov     edi, edx
0x180003867  mov     rax, [rcx]
0x18000386a  mov     rax, [rax+10h]
0x18000386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003873  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003877  cmp     byte ptr [rcx+28h], 0
0x18000387b  jz      short loc_180003887
0x18000387d  mov     byte ptr [rcx+28h], 0
0x180003881  call    cs:__imp_DeleteCriticalSection
0x180003887  test    dil, 1
0x18000388b  jz      short loc_18000389A
0x18000388d  mov     edx, 40h ; '@'
0x180003892  mov     rcx, rbx; Block
0x180003895  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000389a  mov     rax, rbx
0x18000389d  mov     rbx, [rsp+28h+arg_0]
0x1800038a2  add     rsp, 20h
0x1800038a6  pop     rdi
0x1800038a7  retn
```

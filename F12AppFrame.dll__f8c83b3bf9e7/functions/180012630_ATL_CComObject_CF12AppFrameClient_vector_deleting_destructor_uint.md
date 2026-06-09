# ATL::CComObject<CF12AppFrameClient>::`vector deleting destructor'(uint)

- ea: `0x180012630`
- end: `0x180012698`
- name: `??_E?$CComObject@VCF12AppFrameClient@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001900`
- `0x180012630`
- `0x180035010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012671`
- `KERNEL32!DeleteCriticalSection` at `0x180012671`

## pseudocode

```c
char *__fastcall ATL::CComObject<CF12AppFrameClient>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CF12AppFrameClient>::`vftable';
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
0x180012630  mov     [rsp+arg_0], rbx
0x180012635  push    rdi
0x180012636  sub     rsp, 20h
0x18001263a  mov     dword ptr [rcx+8], 0C0000001h
0x180012641  lea     rax, ??_7?$CComObject@VCF12AppFrameClient@@@ATL@@6B@; const ATL::CComObject<CF12AppFrameClient>::`vftable'
0x180012648  mov     [rcx], rax
0x18001264b  mov     rbx, rcx
0x18001264e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012655  mov     edi, edx
0x180012657  mov     rax, [rcx]
0x18001265a  mov     rax, [rax+10h]
0x18001265e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012663  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012667  cmp     byte ptr [rcx+28h], 0
0x18001266b  jz      short loc_180012677
0x18001266d  mov     byte ptr [rcx+28h], 0
0x180012671  call    cs:__imp_DeleteCriticalSection
0x180012677  test    dil, 1
0x18001267b  jz      short loc_18001268A
0x18001267d  mov     edx, 40h ; '@'
0x180012682  mov     rcx, rbx; Block
0x180012685  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001268a  mov     rax, rbx
0x18001268d  mov     rbx, [rsp+28h+arg_0]
0x180012692  add     rsp, 20h
0x180012696  pop     rdi
0x180012697  retn
```

# ATL::CComObject<CMidi2BS2UMPTransform>::`scalar deleting destructor'(uint)

- ea: `0x1800037b0`
- end: `0x180003818`
- name: `??_G?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e84`
- `0x1800037b0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037f1`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2BS2UMPTransform>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2BS2UMPTransform>::`vftable';
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
0x1800037b0  mov     [rsp+arg_0], rbx
0x1800037b5  push    rdi
0x1800037b6  sub     rsp, 20h
0x1800037ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800037c1  lea     rax, ??_7?$CComObject@VCMidi2BS2UMPTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2BS2UMPTransform>::`vftable'
0x1800037c8  mov     [rcx], rax
0x1800037cb  mov     rbx, rcx
0x1800037ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800037d5  mov     edi, edx
0x1800037d7  mov     rax, [rcx]
0x1800037da  mov     rax, [rax+10h]
0x1800037de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800037e7  cmp     byte ptr [rcx+28h], 0
0x1800037eb  jz      short loc_1800037F7
0x1800037ed  mov     byte ptr [rcx+28h], 0
0x1800037f1  call    cs:__imp_DeleteCriticalSection
0x1800037f7  test    dil, 1
0x1800037fb  jz      short loc_18000380A
0x1800037fd  mov     edx, 40h ; '@'
0x180003802  mov     rcx, rbx; Block
0x180003805  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000380a  mov     rax, rbx
0x18000380d  mov     rbx, [rsp+28h+arg_0]
0x180003812  add     rsp, 20h
0x180003816  pop     rdi
0x180003817  retn
```

# ATL::CComObject<CMidi2SchedulerTransform>::`vector deleting destructor'(uint)

- ea: `0x180003950`
- end: `0x1800039b8`
- name: `??_E?$CComObject@VCMidi2SchedulerTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002024`
- `0x180003950`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003991`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003991`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2SchedulerTransform>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2SchedulerTransform>::`vftable';
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
0x180003950  mov     [rsp+arg_0], rbx
0x180003955  push    rdi
0x180003956  sub     rsp, 20h
0x18000395a  mov     dword ptr [rcx+8], 0C0000001h
0x180003961  lea     rax, ??_7?$CComObject@VCMidi2SchedulerTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2SchedulerTransform>::`vftable'
0x180003968  mov     [rcx], rax
0x18000396b  mov     rbx, rcx
0x18000396e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003975  mov     edi, edx
0x180003977  mov     rax, [rcx]
0x18000397a  mov     rax, [rax+10h]
0x18000397e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003983  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003987  cmp     byte ptr [rcx+28h], 0
0x18000398b  jz      short loc_180003997
0x18000398d  mov     byte ptr [rcx+28h], 0
0x180003991  call    cs:__imp_DeleteCriticalSection
0x180003997  test    dil, 1
0x18000399b  jz      short loc_1800039AA
0x18000399d  mov     edx, 40h ; '@'
0x1800039a2  mov     rcx, rbx; Block
0x1800039a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800039aa  mov     rax, rbx
0x1800039ad  mov     rbx, [rsp+28h+arg_0]
0x1800039b2  add     rsp, 20h
0x1800039b6  pop     rdi
0x1800039b7  retn
```

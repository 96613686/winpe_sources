# ATL::CComAggObject<CMidi2SchedulerTransform>::`vector deleting destructor'(uint)

- ea: `0x1800038e0`
- end: `0x180003948`
- name: `??_E?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002024`
- `0x1800038e0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003921`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003921`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2SchedulerTransform>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2SchedulerTransform>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(Block[2].DebugInfo) )
  {
    LOBYTE(Block[2].DebugInfo) = 0;
    DeleteCriticalSection(Block + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800038e0  mov     [rsp+arg_0], rbx
0x1800038e5  push    rdi
0x1800038e6  sub     rsp, 20h
0x1800038ea  mov     dword ptr [rcx+8], 0C0000001h
0x1800038f1  lea     rax, ??_7?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2SchedulerTransform>::`vftable'
0x1800038f8  mov     [rcx], rax
0x1800038fb  mov     rbx, rcx
0x1800038fe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003905  mov     edi, edx
0x180003907  mov     rax, [rcx]
0x18000390a  mov     rax, [rax+10h]
0x18000390e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003913  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003917  cmp     byte ptr [rcx+28h], 0
0x18000391b  jz      short loc_180003927
0x18000391d  mov     byte ptr [rcx+28h], 0
0x180003921  call    cs:__imp_DeleteCriticalSection
0x180003927  test    dil, 1
0x18000392b  jz      short loc_18000393A
0x18000392d  mov     edx, 58h ; 'X'
0x180003932  mov     rcx, rbx; Block
0x180003935  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000393a  mov     rax, rbx
0x18000393d  mov     rbx, [rsp+28h+arg_0]
0x180003942  add     rsp, 20h
0x180003946  pop     rdi
0x180003947  retn
```

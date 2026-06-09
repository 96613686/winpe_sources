# ATL::CComAggObject<CMidi2UMP2BSTransform>::`scalar deleting destructor'(uint)

- ea: `0x1800037d0`
- end: `0x180003838`
- name: `??_G?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001f14`
- `0x1800037d0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003811`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003811`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2UMP2BSTransform>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2UMP2BSTransform>::`vftable';
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
0x1800037d0  mov     [rsp+arg_0], rbx
0x1800037d5  push    rdi
0x1800037d6  sub     rsp, 20h
0x1800037da  mov     dword ptr [rcx+8], 0C0000001h
0x1800037e1  lea     rax, ??_7?$CComAggObject@VCMidi2UMP2BSTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2UMP2BSTransform>::`vftable'
0x1800037e8  mov     [rcx], rax
0x1800037eb  mov     rbx, rcx
0x1800037ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800037f5  mov     edi, edx
0x1800037f7  mov     rax, [rcx]
0x1800037fa  mov     rax, [rax+10h]
0x1800037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003803  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003807  cmp     byte ptr [rcx+28h], 0
0x18000380b  jz      short loc_180003817
0x18000380d  mov     byte ptr [rcx+28h], 0
0x180003811  call    cs:__imp_DeleteCriticalSection
0x180003817  test    dil, 1
0x18000381b  jz      short loc_18000382A
0x18000381d  mov     edx, 58h ; 'X'
0x180003822  mov     rcx, rbx; Block
0x180003825  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000382a  mov     rax, rbx
0x18000382d  mov     rbx, [rsp+28h+arg_0]
0x180003832  add     rsp, 20h
0x180003836  pop     rdi
0x180003837  retn
```

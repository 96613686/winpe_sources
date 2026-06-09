# ATL::CComAggObject<CMigrationPlugin>::`scalar deleting destructor'(uint)

- ea: `0x18000cdd0`
- end: `0x18000ce38`
- name: `??_G?$CComAggObject@VCMigrationPlugin@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002b9c`
- `0x18000cdd0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ce11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ce11`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMigrationPlugin>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMigrationPlugin>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(Block[3].DebugInfo) )
  {
    LOBYTE(Block[3].DebugInfo) = 0;
    DeleteCriticalSection(Block + 2);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000cdd0  mov     [rsp+arg_0], rbx
0x18000cdd5  push    rdi
0x18000cdd6  sub     rsp, 20h
0x18000cdda  mov     dword ptr [rcx+8], 0C0000001h
0x18000cde1  lea     rax, ??_7?$CComAggObject@VCMigrationPlugin@@@ATL@@6B@; const ATL::CComAggObject<CMigrationPlugin>::`vftable'
0x18000cde8  mov     [rcx], rax
0x18000cdeb  mov     rbx, rcx
0x18000cdee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cdf5  mov     edi, edx
0x18000cdf7  mov     rax, [rcx]
0x18000cdfa  mov     rax, [rax+10h]
0x18000cdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce03  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000ce07  cmp     byte ptr [rcx+28h], 0
0x18000ce0b  jz      short loc_18000CE17
0x18000ce0d  mov     byte ptr [rcx+28h], 0
0x18000ce11  call    cs:__imp_DeleteCriticalSection
0x18000ce17  test    dil, 1
0x18000ce1b  jz      short loc_18000CE2A
0x18000ce1d  mov     edx, 80h
0x18000ce22  mov     rcx, rbx; Block
0x18000ce25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ce2a  mov     rax, rbx
0x18000ce2d  mov     rbx, [rsp+28h+arg_0]
0x18000ce32  add     rsp, 20h
0x18000ce36  pop     rdi
0x18000ce37  retn
```

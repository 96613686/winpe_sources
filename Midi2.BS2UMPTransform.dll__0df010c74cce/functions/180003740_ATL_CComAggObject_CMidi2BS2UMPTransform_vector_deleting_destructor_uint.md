# ATL::CComAggObject<CMidi2BS2UMPTransform>::`vector deleting destructor'(uint)

- ea: `0x180003740`
- end: `0x1800037a8`
- name: `??_E?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001e84`
- `0x180003740`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003781`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003781`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2BS2UMPTransform>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2BS2UMPTransform>::`vftable';
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
0x180003740  mov     [rsp+arg_0], rbx
0x180003745  push    rdi
0x180003746  sub     rsp, 20h
0x18000374a  mov     dword ptr [rcx+8], 0C0000001h
0x180003751  lea     rax, ??_7?$CComAggObject@VCMidi2BS2UMPTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2BS2UMPTransform>::`vftable'
0x180003758  mov     [rcx], rax
0x18000375b  mov     rbx, rcx
0x18000375e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003765  mov     edi, edx
0x180003767  mov     rax, [rcx]
0x18000376a  mov     rax, [rax+10h]
0x18000376e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003773  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003777  cmp     byte ptr [rcx+28h], 0
0x18000377b  jz      short loc_180003787
0x18000377d  mov     byte ptr [rcx+28h], 0
0x180003781  call    cs:__imp_DeleteCriticalSection
0x180003787  test    dil, 1
0x18000378b  jz      short loc_18000379A
0x18000378d  mov     edx, 58h ; 'X'
0x180003792  mov     rcx, rbx; Block
0x180003795  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000379a  mov     rax, rbx
0x18000379d  mov     rbx, [rsp+28h+arg_0]
0x1800037a2  add     rsp, 20h
0x1800037a6  pop     rdi
0x1800037a7  retn
```

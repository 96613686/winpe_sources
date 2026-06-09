# ATL::CComAggObject<MetadataPackageSource>::`vector deleting destructor'(uint)

- ea: `0x180011310`
- end: `0x18001137c`
- name: `??_E?$CComAggObject@VMetadataPackageSource@@@ATL@@UEAAPEAXI@Z`
- size: `108`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001520`
- `0x180011310`
- `0x180011878`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001135a`
- `KERNEL32!DeleteCriticalSection` at `0x18001135a`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<MetadataPackageSource>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<MetadataPackageSource>::`vftable';
  MetadataPackageSource::FinalRelease((MetadataPackageSource *)&Block->LockSemaphore);
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
0x180011310  mov     [rsp+arg_0], rbx
0x180011315  push    rdi
0x180011316  sub     rsp, 20h
0x18001131a  lea     rax, ??_7?$CComAggObject@VMetadataPackageSource@@@ATL@@6B@; const ATL::CComAggObject<MetadataPackageSource>::`vftable'
0x180011321  mov     dword ptr [rcx+8], 0C0000001h
0x180011328  mov     [rcx], rax
0x18001132b  mov     rbx, rcx
0x18001132e  add     rcx, 18h; this
0x180011332  mov     edi, edx
0x180011334  call    ?FinalRelease@MetadataPackageSource@@QEAAXXZ; MetadataPackageSource::FinalRelease(void)
0x180011339  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011340  mov     rax, [rcx]
0x180011343  mov     rax, [rax+10h]
0x180011347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001134c  lea     rcx, [rbx+28h]; lpCriticalSection
0x180011350  cmp     byte ptr [rcx+28h], 0
0x180011354  jz      short loc_180011360
0x180011356  mov     byte ptr [rcx+28h], 0
0x18001135a  call    cs:__imp_DeleteCriticalSection
0x180011360  test    dil, 1
0x180011364  jz      short loc_18001136E
0x180011366  mov     rcx, rbx; Block
0x180011369  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001136e  mov     rax, rbx
0x180011371  mov     rbx, [rsp+28h+arg_0]
0x180011376  add     rsp, 20h
0x18001137a  pop     rdi
0x18001137b  retn
```

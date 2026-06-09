# ATL::CComObject<MetadataPackageSource>::`scalar deleting destructor'(uint)

- ea: `0x180011390`
- end: `0x1800113f8`
- name: `??_G?$CComObject@VMetadataPackageSource@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001520`
- `0x180011390`
- `0x180011878`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800113d6`
- `KERNEL32!DeleteCriticalSection` at `0x1800113d6`

## pseudocode

```c
char *__fastcall ATL::CComObject<MetadataPackageSource>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<MetadataPackageSource>::`vftable';
  MetadataPackageSource::FinalRelease((MetadataPackageSource *)Block);
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
0x180011390  mov     [rsp+arg_0], rbx
0x180011395  push    rdi
0x180011396  sub     rsp, 20h
0x18001139a  lea     rax, ??_7?$CComObject@VMetadataPackageSource@@@ATL@@6B@; const ATL::CComObject<MetadataPackageSource>::`vftable'
0x1800113a1  mov     dword ptr [rcx+8], 0C0000001h
0x1800113a8  mov     [rcx], rax
0x1800113ab  mov     edi, edx
0x1800113ad  mov     rbx, rcx
0x1800113b0  call    ?FinalRelease@MetadataPackageSource@@QEAAXXZ; MetadataPackageSource::FinalRelease(void)
0x1800113b5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800113bc  mov     rax, [rcx]
0x1800113bf  mov     rax, [rax+10h]
0x1800113c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113c8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800113cc  cmp     byte ptr [rcx+28h], 0
0x1800113d0  jz      short loc_1800113DC
0x1800113d2  mov     byte ptr [rcx+28h], 0
0x1800113d6  call    cs:__imp_DeleteCriticalSection
0x1800113dc  test    dil, 1
0x1800113e0  jz      short loc_1800113EA
0x1800113e2  mov     rcx, rbx; Block
0x1800113e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800113ea  mov     rax, rbx
0x1800113ed  mov     rbx, [rsp+28h+arg_0]
0x1800113f2  add     rsp, 20h
0x1800113f6  pop     rdi
0x1800113f7  retn
```

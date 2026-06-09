# ATL::CComObject<CEnhancedStorageFolder>::`vector deleting destructor'(uint)

- ea: `0x180002ea0`
- end: `0x180002f2b`
- name: `??_E?$CComObject@VCEnhancedStorageFolder@@@ATL@@UEAAPEAXI@Z`
- size: `139`
- prototype: `_QWORD *__fastcall(_QWORD *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ea0`
- `0x180002f40`
- `0x180006b74`
- `0x18000c010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComObject<CEnhancedStorageFolder>::`vector deleting destructor'(_QWORD *Block, char a2)
{
  __int64 v4; // rcx

  *Block = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `CItemIDFactory<_ITEMID,1450709556>'};
  Block[2] = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IPersistFolder2'};
  Block[3] = &ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IShellFolder2'};
  *((_DWORD *)Block + 8) = -1073741823;
  CEnhancedStorageFolder::FinalRelease((CEnhancedStorageFolder *)Block);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *Block = &CItemIDFactory<_ITEMID,1450709556>::`vftable';
  v4 = Block[1];
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002ea0  mov     [rsp+arg_0], rbx
0x180002ea5  push    rdi
0x180002ea6  sub     rsp, 20h
0x180002eaa  mov     edi, edx
0x180002eac  mov     rbx, rcx
0x180002eaf  lea     rax, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6B?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `CItemIDFactory<_ITEMID,1450709556>'}
0x180002eb6  mov     [rcx], rax
0x180002eb9  lea     rax, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6BIPersistFolder2@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IPersistFolder2'}
0x180002ec0  mov     [rcx+10h], rax
0x180002ec4  lea     rax, ??_7?$CComObject@VCEnhancedStorageFolder@@@ATL@@6BIShellFolder2@@@; const ATL::CComObject<CEnhancedStorageFolder>::`vftable'{for `IShellFolder2'}
0x180002ecb  mov     [rcx+18h], rax
0x180002ecf  mov     dword ptr [rcx+20h], 0C0000001h
0x180002ed6  call    ?FinalRelease@CEnhancedStorageFolder@@QEAAXXZ; CEnhancedStorageFolder::FinalRelease(void)
0x180002edb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002ee2  mov     rax, [rcx]
0x180002ee5  mov     rax, [rax+10h]
0x180002ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eee  nop
0x180002eef  lea     rax, ??_7?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@6B@; const CItemIDFactory<_ITEMID,1450709556>::`vftable'
0x180002ef6  mov     [rbx], rax
0x180002ef9  mov     rcx, [rbx+8]
0x180002efd  test    rcx, rcx
0x180002f00  jz      short loc_180002F0F
0x180002f02  mov     rax, [rcx]
0x180002f05  mov     rax, [rax+10h]
0x180002f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f0e  nop
0x180002f0f  test    dil, 1
0x180002f13  jz      short loc_180002F1D
0x180002f15  mov     rcx, rbx; Block
0x180002f18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f1d  mov     rax, rbx
0x180002f20  mov     rbx, [rsp+28h+arg_0]
0x180002f25  add     rsp, 20h
0x180002f29  pop     rdi
0x180002f2a  retn
```

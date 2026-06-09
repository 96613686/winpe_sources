# ATL::CComObject<CEnhancedStorageEnumerator>::`scalar deleting destructor'(uint)

- ea: `0x180003450`
- end: `0x1800034a5`
- name: `??_G?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@UEAAPEAXI@Z`
- size: `85`
- prototype: `CEnhancedStorageEnumerator *__fastcall(CEnhancedStorageEnumerator *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003450`
- `0x1800034b0`
- `0x180006b74`
- `0x18000c010`

## pseudocode

```c
CEnhancedStorageEnumerator *__fastcall ATL::CComObject<CEnhancedStorageEnumerator>::`scalar deleting destructor'(
        CEnhancedStorageEnumerator *Block,
        char a2)
{
  *(_QWORD *)Block = &ATL::CComObject<CEnhancedStorageEnumerator>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  CEnhancedStorageEnumerator::FinalRelease(Block);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003450  mov     [rsp+arg_0], rbx
0x180003455  push    rdi
0x180003456  sub     rsp, 20h
0x18000345a  mov     edi, edx
0x18000345c  mov     rbx, rcx
0x18000345f  lea     rax, ??_7?$CComObject@VCEnhancedStorageEnumerator@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageEnumerator>::`vftable'
0x180003466  mov     [rcx], rax
0x180003469  mov     dword ptr [rcx+8], 0C0000001h
0x180003470  call    ?FinalRelease@CEnhancedStorageEnumerator@@QEAAXXZ; CEnhancedStorageEnumerator::FinalRelease(void)
0x180003475  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000347c  mov     rax, [rcx]
0x18000347f  mov     rax, [rax+10h]
0x180003483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003488  nop
0x180003489  test    dil, 1
0x18000348d  jz      short loc_180003497
0x18000348f  mov     rcx, rbx; Block
0x180003492  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003497  mov     rax, rbx
0x18000349a  mov     rbx, [rsp+28h+arg_0]
0x18000349f  add     rsp, 20h
0x1800034a3  pop     rdi
0x1800034a4  retn
```

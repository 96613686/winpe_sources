# ATL::CComAggObject<CVsShellExtHandler>::`vector deleting destructor'(uint)

- ea: `0x180003410`
- end: `0x18000346e`
- name: `??_E?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003410`
- `0x180007a90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall ATL::CComAggObject<CVsShellExtHandler>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)Block = &ATL::CComAggObject<CVsShellExtHandler>::`vftable';
  Block[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 7);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  push    rdi
0x180003416  sub     rsp, 20h
0x18000341a  mov     edi, edx
0x18000341c  mov     rbx, rcx
0x18000341f  lea     rax, ??_7?$CComAggObject@VCVsShellExtHandler@@@ATL@@6B@; const ATL::CComAggObject<CVsShellExtHandler>::`vftable'
0x180003426  mov     [rcx], rax
0x180003429  mov     dword ptr [rcx+8], 0C0000001h
0x180003430  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003437  mov     rax, [rcx]
0x18000343a  call    qword ptr [rax+10h]
0x18000343d  mov     rcx, [rbx+38h]
0x180003441  test    rcx, rcx
0x180003444  jz      short loc_18000344D
0x180003446  mov     rax, [rcx]
0x180003449  call    qword ptr [rax+10h]
0x18000344c  nop
0x18000344d  test    dil, 1
0x180003451  jz      short loc_180003460
0x180003453  mov     edx, 40h ; '@'
0x180003458  mov     rcx, rbx; Block
0x18000345b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003460  mov     rax, rbx
0x180003463  mov     rbx, [rsp+28h+arg_0]
0x180003468  add     rsp, 20h
0x18000346c  pop     rdi
0x18000346d  retn
```

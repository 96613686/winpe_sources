# ATL::CComObject<CVsShellExtHandler>::`vector deleting destructor'(uint)

- ea: `0x180003380`
- end: `0x1800033f4`
- name: `??_E?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAPEAXI@Z`
- size: `116`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003380`
- `0x180007a90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ATL::CComObject<CVsShellExtHandler>::`vector deleting destructor'(_QWORD *Block, char a2)
{
  __int64 v4; // rcx

  *Block = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'};
  Block[1] = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'};
  Block[2] = &ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'};
  *((_DWORD *)Block + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = Block[5];
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003380  mov     [rsp+arg_0], rbx
0x180003385  push    rdi
0x180003386  sub     rsp, 20h
0x18000338a  mov     edi, edx
0x18000338c  mov     rbx, rcx
0x18000338f  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPersistFile'}
0x180003396  mov     [rcx], rax
0x180003399  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIExtractIconW@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IExtractIconW'}
0x1800033a0  mov     [rcx+8], rax
0x1800033a4  lea     rax, ??_7?$CComObject@VCVsShellExtHandler@@@ATL@@6BIPropertySetStorage@@@; const ATL::CComObject<CVsShellExtHandler>::`vftable'{for `IPropertySetStorage'}
0x1800033ab  mov     [rcx+10h], rax
0x1800033af  mov     dword ptr [rcx+18h], 0C0000001h
0x1800033b6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800033bd  mov     rax, [rcx]
0x1800033c0  call    qword ptr [rax+10h]
0x1800033c3  mov     rcx, [rbx+28h]
0x1800033c7  test    rcx, rcx
0x1800033ca  jz      short loc_1800033D3
0x1800033cc  mov     rax, [rcx]
0x1800033cf  call    qword ptr [rax+10h]
0x1800033d2  nop
0x1800033d3  test    dil, 1
0x1800033d7  jz      short loc_1800033E6
0x1800033d9  mov     edx, 30h ; '0'
0x1800033de  mov     rcx, rbx; Block
0x1800033e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800033e6  mov     rax, rbx
0x1800033e9  mov     rbx, [rsp+28h+arg_0]
0x1800033ee  add     rsp, 20h
0x1800033f2  pop     rdi
0x1800033f3  retn
```

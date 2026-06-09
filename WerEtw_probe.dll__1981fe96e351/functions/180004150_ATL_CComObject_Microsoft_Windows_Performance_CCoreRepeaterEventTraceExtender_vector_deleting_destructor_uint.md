# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180004150`
- end: `0x1800041d1`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180004150`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
  Block[6] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)Block + 1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004150  mov     [rsp+arg_0], rbx
0x180004155  push    rdi
0x180004156  sub     rsp, 20h
0x18000415a  mov     edi, edx
0x18000415c  mov     rbx, rcx
0x18000415f  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180004166  mov     [rcx], rax
0x180004169  mov     dword ptr [rcx+18h], 0C0000001h
0x180004170  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004177  mov     rax, [rcx]
0x18000417a  mov     rax, [rax+10h]
0x18000417e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004183  nop
0x180004184  mov     rcx, [rbx+10h]
0x180004188  test    rcx, rcx
0x18000418b  jz      short loc_18000419A
0x18000418d  mov     rax, [rcx]
0x180004190  mov     rax, [rax+10h]
0x180004194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004199  nop
0x18000419a  mov     rcx, [rbx+8]
0x18000419e  test    rcx, rcx
0x1800041a1  jz      short loc_1800041B0
0x1800041a3  mov     rax, [rcx]
0x1800041a6  mov     rax, [rax+10h]
0x1800041aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041af  nop
0x1800041b0  test    dil, 1
0x1800041b4  jz      short loc_1800041C3
0x1800041b6  mov     edx, 28h ; '('
0x1800041bb  mov     rcx, rbx; Block
0x1800041be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800041c3  mov     rax, rbx
0x1800041c6  mov     rbx, [rsp+28h+arg_0]
0x1800041cb  add     rsp, 20h
0x1800041cf  pop     rdi
0x1800041d0  retn
```

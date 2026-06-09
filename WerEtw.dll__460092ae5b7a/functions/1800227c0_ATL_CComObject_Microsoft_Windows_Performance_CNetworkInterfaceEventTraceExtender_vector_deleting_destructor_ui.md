# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800227c0`
- end: `0x180022841`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x1800227c0`
- `0x18002a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
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
0x1800227c0  mov     [rsp+arg_0], rbx
0x1800227c5  push    rdi
0x1800227c6  sub     rsp, 20h
0x1800227ca  mov     edi, edx
0x1800227cc  mov     rbx, rcx
0x1800227cf  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x1800227d6  mov     [rcx], rax
0x1800227d9  mov     dword ptr [rcx+18h], 0C0000001h
0x1800227e0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800227e7  mov     rax, [rcx]
0x1800227ea  mov     rax, [rax+10h]
0x1800227ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227f3  nop
0x1800227f4  mov     rcx, [rbx+10h]
0x1800227f8  test    rcx, rcx
0x1800227fb  jz      short loc_18002280A
0x1800227fd  mov     rax, [rcx]
0x180022800  mov     rax, [rax+10h]
0x180022804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022809  nop
0x18002280a  mov     rcx, [rbx+8]
0x18002280e  test    rcx, rcx
0x180022811  jz      short loc_180022820
0x180022813  mov     rax, [rcx]
0x180022816  mov     rax, [rax+10h]
0x18002281a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002281f  nop
0x180022820  test    dil, 1
0x180022824  jz      short loc_180022833
0x180022826  mov     edx, 20h ; ' '
0x18002282b  mov     rcx, rbx; Block
0x18002282e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022833  mov     rax, rbx
0x180022836  mov     rbx, [rsp+28h+arg_0]
0x18002283b  add     rsp, 20h
0x18002283f  pop     rdi
0x180022840  retn
```

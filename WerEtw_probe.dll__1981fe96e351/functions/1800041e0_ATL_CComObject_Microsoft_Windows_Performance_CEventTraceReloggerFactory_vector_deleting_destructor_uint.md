# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(uint)

- ea: `0x1800041e0`
- end: `0x180004233`
- name: `??_E?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `83`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x1800041e0`
- `0x18002a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800041e0  mov     [rsp+arg_0], rbx
0x1800041e5  push    rdi
0x1800041e6  sub     rsp, 20h
0x1800041ea  mov     dword ptr [rcx+8], 0C0000001h
0x1800041f1  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x1800041f8  mov     [rcx], rax
0x1800041fb  mov     rdi, rcx
0x1800041fe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004205  mov     ebx, edx
0x180004207  mov     rax, [rcx]
0x18000420a  mov     rax, [rax+10h]
0x18000420e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004213  test    bl, 1
0x180004216  jz      short loc_180004225
0x180004218  mov     edx, 10h
0x18000421d  mov     rcx, rdi; Block
0x180004220  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004225  mov     rbx, [rsp+28h+arg_0]
0x18000422a  mov     rax, rdi
0x18000422d  add     rsp, 20h
0x180004231  pop     rdi
0x180004232  retn
```

# ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`scalar deleting destructor'(uint)

- ea: `0x180003cb0`
- end: `0x180003cfe`
- name: `??_G?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180003cb0`
- `0x18000b010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003cb0  mov     [rsp+arg_0], rbx
0x180003cb5  push    rdi
0x180003cb6  sub     rsp, 20h
0x180003cba  mov     dword ptr [rcx+8], 0C0000001h
0x180003cc1  lea     rax, ??_7?$CComAggObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComAggObject<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180003cc8  mov     [rcx], rax
0x180003ccb  mov     rdi, rcx
0x180003cce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003cd5  mov     ebx, edx
0x180003cd7  mov     rax, [rcx]
0x180003cda  mov     rax, [rax+10h]
0x180003cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce3  test    bl, 1
0x180003ce6  jz      short loc_180003CF0
0x180003ce8  mov     rcx, rdi; Block
0x180003ceb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003cf0  mov     rbx, [rsp+28h+arg_0]
0x180003cf5  mov     rax, rdi
0x180003cf8  add     rsp, 20h
0x180003cfc  pop     rdi
0x180003cfd  retn
```

# ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`scalar deleting destructor'(uint)

- ea: `0x180003d10`
- end: `0x180003d5e`
- name: `??_G?$CComObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x180003d10`
- `0x18000b010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003d10  mov     [rsp+arg_0], rbx
0x180003d15  push    rdi
0x180003d16  sub     rsp, 20h
0x180003d1a  mov     dword ptr [rcx+8], 0C0000001h
0x180003d21  lea     rax, ??_7?$CComObject@VHtmlDocForParsingSiteUnmarshaller@@@ATL@@6B@; const ATL::CComObject<HtmlDocForParsingSiteUnmarshaller>::`vftable'
0x180003d28  mov     [rcx], rax
0x180003d2b  mov     rdi, rcx
0x180003d2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d35  mov     ebx, edx
0x180003d37  mov     rax, [rcx]
0x180003d3a  mov     rax, [rax+10h]
0x180003d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d43  test    bl, 1
0x180003d46  jz      short loc_180003D50
0x180003d48  mov     rcx, rdi; Block
0x180003d4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003d50  mov     rbx, [rsp+28h+arg_0]
0x180003d55  mov     rax, rdi
0x180003d58  add     rsp, 20h
0x180003d5c  pop     rdi
0x180003d5d  retn
```

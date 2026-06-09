# ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vector deleting destructor'(uint)

- ea: `0x1400102a0`
- end: `0x1400102ef`
- name: `??_E?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400102a0`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400102db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400102db`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1400102a0  mov     [rsp+arg_0], rbx
0x1400102a5  push    rdi
0x1400102a6  sub     rsp, 20h
0x1400102aa  mov     dword ptr [rcx+8], 0C0000001h
0x1400102b1  lea     rax, ??_7?$CComObject@VCSpellCheckHost@Spelling@Globalization@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::Globalization::Spelling::CSpellCheckHost>::`vftable'
0x1400102b8  mov     [rcx], rax
0x1400102bb  mov     rdi, rcx
0x1400102be  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400102c5  mov     ebx, edx
0x1400102c7  mov     rax, [rcx]
0x1400102ca  mov     rax, [rax+10h]
0x1400102ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102d3  test    bl, 1
0x1400102d6  jz      short loc_1400102E1
0x1400102d8  mov     rcx, rdi
0x1400102db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400102e1  mov     rbx, [rsp+28h+arg_0]
0x1400102e6  mov     rax, rdi
0x1400102e9  add     rsp, 20h
0x1400102ed  pop     rdi
0x1400102ee  retn
```

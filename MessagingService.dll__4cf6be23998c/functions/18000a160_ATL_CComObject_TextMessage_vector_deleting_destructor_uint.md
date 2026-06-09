# ATL::CComObject<TextMessage>::`vector deleting destructor'(uint)

- ea: `0x18000a160`
- end: `0x18000a1b7`
- name: `??_E?$CComObject@VTextMessage@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `TextMessage *__fastcall(TextMessage *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a0f4`
- `0x18000a160`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a1a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a1a3`

## pseudocode

```c
TextMessage *__fastcall ATL::CComObject<TextMessage>::`vector deleting destructor'(TextMessage *this, char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<TextMessage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  TextMessage::~TextMessage(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000a160  mov     [rsp+arg_0], rbx
0x18000a165  push    rdi
0x18000a166  sub     rsp, 20h
0x18000a16a  mov     dword ptr [rcx+8], 0C0000001h
0x18000a171  lea     rax, ??_7?$CComObject@VTextMessage@@@ATL@@6B@; const ATL::CComObject<TextMessage>::`vftable'
0x18000a178  mov     [rcx], rax
0x18000a17b  mov     rdi, rcx
0x18000a17e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a185  mov     ebx, edx
0x18000a187  mov     rax, [rcx]
0x18000a18a  mov     rax, [rax+10h]
0x18000a18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a193  mov     rcx, rdi; this
0x18000a196  call    ??1TextMessage@@IEAA@XZ; TextMessage::~TextMessage(void)
0x18000a19b  test    bl, 1
0x18000a19e  jz      short loc_18000A1A9
0x18000a1a0  mov     rcx, rdi
0x18000a1a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a1a9  mov     rbx, [rsp+28h+arg_0]
0x18000a1ae  mov     rax, rdi
0x18000a1b1  add     rsp, 20h
0x18000a1b5  pop     rdi
0x18000a1b6  retn
```

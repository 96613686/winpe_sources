# ATL::CComObject<TextMessageTransport>::`vector deleting destructor'(uint)

- ea: `0x180006b50`
- end: `0x180006ba7`
- name: `??_E?$CComObject@VTextMessageTransport@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `TextMessageTransport *__fastcall(TextMessageTransport *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006ae8`
- `0x180006b50`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006b93`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006b93`

## pseudocode

```c
TextMessageTransport *__fastcall ATL::CComObject<TextMessageTransport>::`vector deleting destructor'(
        TextMessageTransport *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<TextMessageTransport>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  TextMessageTransport::~TextMessageTransport(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006b50  mov     [rsp+arg_0], rbx
0x180006b55  push    rdi
0x180006b56  sub     rsp, 20h
0x180006b5a  mov     dword ptr [rcx+8], 0C0000001h
0x180006b61  lea     rax, ??_7?$CComObject@VTextMessageTransport@@@ATL@@6B@; const ATL::CComObject<TextMessageTransport>::`vftable'
0x180006b68  mov     [rcx], rax
0x180006b6b  mov     rdi, rcx
0x180006b6e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006b75  mov     ebx, edx
0x180006b77  mov     rax, [rcx]
0x180006b7a  mov     rax, [rax+10h]
0x180006b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b83  mov     rcx, rdi; this
0x180006b86  call    ??1TextMessageTransport@@MEAA@XZ; TextMessageTransport::~TextMessageTransport(void)
0x180006b8b  test    bl, 1
0x180006b8e  jz      short loc_180006B99
0x180006b90  mov     rcx, rdi
0x180006b93  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006b99  mov     rbx, [rsp+28h+arg_0]
0x180006b9e  mov     rax, rdi
0x180006ba1  add     rsp, 20h
0x180006ba5  pop     rdi
0x180006ba6  retn
```

# ATL::CComObject<IncomingTextMessageHandler>::`vector deleting destructor'(uint)

- ea: `0x1800071b0`
- end: `0x180007207`
- name: `??_E?$CComObject@VIncomingTextMessageHandler@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `IncomingTextMessageHandler *__fastcall(IncomingTextMessageHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007150`
- `0x1800071b0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800071f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800071f3`

## pseudocode

```c
IncomingTextMessageHandler *__fastcall ATL::CComObject<IncomingTextMessageHandler>::`vector deleting destructor'(
        IncomingTextMessageHandler *this,
        char a2)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<IncomingTextMessageHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  IncomingTextMessageHandler::~IncomingTextMessageHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800071b0  mov     [rsp+arg_0], rbx
0x1800071b5  push    rdi
0x1800071b6  sub     rsp, 20h
0x1800071ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800071c1  lea     rax, ??_7?$CComObject@VIncomingTextMessageHandler@@@ATL@@6B@; const ATL::CComObject<IncomingTextMessageHandler>::`vftable'
0x1800071c8  mov     [rcx], rax
0x1800071cb  mov     rdi, rcx
0x1800071ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800071d5  mov     ebx, edx
0x1800071d7  mov     rax, [rcx]
0x1800071da  mov     rax, [rax+10h]
0x1800071de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e3  mov     rcx, rdi; this
0x1800071e6  call    ??1IncomingTextMessageHandler@@MEAA@XZ; IncomingTextMessageHandler::~IncomingTextMessageHandler(void)
0x1800071eb  test    bl, 1
0x1800071ee  jz      short loc_1800071F9
0x1800071f0  mov     rcx, rdi
0x1800071f3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800071f9  mov     rbx, [rsp+28h+arg_0]
0x1800071fe  mov     rax, rdi
0x180007201  add     rsp, 20h
0x180007205  pop     rdi
0x180007206  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001bd80`
- end: `0x18001bddb`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x18001b708`
- `0x18001bd80`
- `0x18002a010`

## pseudocode

```c
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001bd80  mov     [rsp+arg_0], rbx
0x18001bd85  push    rdi
0x18001bd86  sub     rsp, 20h
0x18001bd8a  mov     dword ptr [rcx+18h], 0C0000001h
0x18001bd91  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001bd98  mov     [rcx], rax
0x18001bd9b  mov     rdi, rcx
0x18001bd9e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001bda5  mov     ebx, edx
0x18001bda7  mov     rax, [rcx]
0x18001bdaa  mov     rax, [rax+10h]
0x18001bdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdb3  mov     rcx, rdi; this
0x18001bdb6  call    ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
0x18001bdbb  test    bl, 1
0x18001bdbe  jz      short loc_18001BDCD
0x18001bdc0  mov     edx, 180h
0x18001bdc5  mov     rcx, rdi; Block
0x18001bdc8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bdcd  mov     rbx, [rsp+28h+arg_0]
0x18001bdd2  mov     rax, rdi
0x18001bdd5  add     rsp, 20h
0x18001bdd9  pop     rdi
0x18001bdda  retn
```

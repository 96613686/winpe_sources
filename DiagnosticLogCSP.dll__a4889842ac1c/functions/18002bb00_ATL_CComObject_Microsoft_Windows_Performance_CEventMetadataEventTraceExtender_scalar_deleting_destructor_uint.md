# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002bb00`
- end: `0x18002bb5b`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18002b654`
- `0x18002bb00`
- `0x180037010`

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
0x18002bb00  mov     [rsp+arg_0], rbx
0x18002bb05  push    rdi
0x18002bb06  sub     rsp, 20h
0x18002bb0a  mov     dword ptr [rcx+18h], 0C0000001h
0x18002bb11  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18002bb18  mov     [rcx], rax
0x18002bb1b  mov     rdi, rcx
0x18002bb1e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002bb25  mov     ebx, edx
0x18002bb27  mov     rax, [rcx]
0x18002bb2a  mov     rax, [rax+10h]
0x18002bb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb33  mov     rcx, rdi; this
0x18002bb36  call    ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
0x18002bb3b  test    bl, 1
0x18002bb3e  jz      short loc_18002BB4D
0x18002bb40  mov     edx, 180h; unsigned __int64
0x18002bb45  mov     rcx, rdi; void *
0x18002bb48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002bb4d  mov     rbx, [rsp+28h+arg_0]
0x18002bb52  mov     rax, rdi
0x18002bb55  add     rsp, 20h
0x18002bb59  pop     rdi
0x18002bb5a  retn
```

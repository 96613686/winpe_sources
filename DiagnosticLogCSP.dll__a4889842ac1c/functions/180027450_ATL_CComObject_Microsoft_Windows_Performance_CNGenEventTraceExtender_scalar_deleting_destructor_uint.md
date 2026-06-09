# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180027450`
- end: `0x1800274ab`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x180026fcc`
- `0x180027450`
- `0x180037010`

## pseudocode

```c
Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180027450  mov     [rsp+arg_0], rbx
0x180027455  push    rdi
0x180027456  sub     rsp, 20h
0x18002745a  mov     dword ptr [rcx+18h], 0C0000001h
0x180027461  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180027468  mov     [rcx], rax
0x18002746b  mov     rdi, rcx
0x18002746e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180027475  mov     ebx, edx
0x180027477  mov     rax, [rcx]
0x18002747a  mov     rax, [rax+10h]
0x18002747e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027483  mov     rcx, rdi; this
0x180027486  call    ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
0x18002748b  test    bl, 1
0x18002748e  jz      short loc_18002749D
0x180027490  mov     edx, 0B8h; unsigned __int64
0x180027495  mov     rcx, rdi; void *
0x180027498  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002749d  mov     rbx, [rsp+28h+arg_0]
0x1800274a2  mov     rax, rdi
0x1800274a5  add     rsp, 20h
0x1800274a9  pop     rdi
0x1800274aa  retn
```

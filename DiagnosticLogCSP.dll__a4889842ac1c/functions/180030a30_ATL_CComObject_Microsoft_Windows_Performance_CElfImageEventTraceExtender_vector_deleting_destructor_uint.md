# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180030a30`
- end: `0x180030a8b`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x180030878`
- `0x180030a30`
- `0x180037010`

## pseudocode

```c
Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180030a30  mov     [rsp+arg_0], rbx
0x180030a35  push    rdi
0x180030a36  sub     rsp, 20h
0x180030a3a  mov     dword ptr [rcx+18h], 0C0000001h
0x180030a41  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180030a48  mov     [rcx], rax
0x180030a4b  mov     rdi, rcx
0x180030a4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180030a55  mov     ebx, edx
0x180030a57  mov     rax, [rcx]
0x180030a5a  mov     rax, [rax+10h]
0x180030a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a63  mov     rcx, rdi; this
0x180030a66  call    ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
0x180030a6b  test    bl, 1
0x180030a6e  jz      short loc_180030A7D
0x180030a70  mov     edx, 50h ; 'P'; unsigned __int64
0x180030a75  mov     rcx, rdi; void *
0x180030a78  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180030a7d  mov     rbx, [rsp+28h+arg_0]
0x180030a82  mov     rax, rdi
0x180030a85  add     rsp, 20h
0x180030a89  pop     rdi
0x180030a8a  retn
```

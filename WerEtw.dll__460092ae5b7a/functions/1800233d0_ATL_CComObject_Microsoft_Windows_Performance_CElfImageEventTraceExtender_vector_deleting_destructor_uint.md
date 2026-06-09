# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x1800233d0`
- end: `0x18002342b`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180023210`
- `0x1800233d0`
- `0x18002a010`

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
0x1800233d0  mov     [rsp+arg_0], rbx
0x1800233d5  push    rdi
0x1800233d6  sub     rsp, 20h
0x1800233da  mov     dword ptr [rcx+18h], 0C0000001h
0x1800233e1  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x1800233e8  mov     [rcx], rax
0x1800233eb  mov     rdi, rcx
0x1800233ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800233f5  mov     ebx, edx
0x1800233f7  mov     rax, [rcx]
0x1800233fa  mov     rax, [rax+10h]
0x1800233fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023403  mov     rcx, rdi; this
0x180023406  call    ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
0x18002340b  test    bl, 1
0x18002340e  jz      short loc_18002341D
0x180023410  mov     edx, 50h ; 'P'
0x180023415  mov     rcx, rdi; Block
0x180023418  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002341d  mov     rbx, [rsp+28h+arg_0]
0x180023422  mov     rax, rdi
0x180023425  add     rsp, 20h
0x180023429  pop     rdi
0x18002342a  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180020950`
- end: `0x1800209ab`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x1800208c0`
- `0x180020950`
- `0x18002a010`

## pseudocode

```c
Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180020950  mov     [rsp+arg_0], rbx
0x180020955  push    rdi
0x180020956  sub     rsp, 20h
0x18002095a  mov     dword ptr [rcx+18h], 0C0000001h
0x180020961  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x180020968  mov     [rcx], rax
0x18002096b  mov     rdi, rcx
0x18002096e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020975  mov     ebx, edx
0x180020977  mov     rax, [rcx]
0x18002097a  mov     rax, [rax+10h]
0x18002097e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020983  mov     rcx, rdi; this
0x180020986  call    ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
0x18002098b  test    bl, 1
0x18002098e  jz      short loc_18002099D
0x180020990  mov     edx, 90h
0x180020995  mov     rcx, rdi; Block
0x180020998  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002099d  mov     rbx, [rsp+28h+arg_0]
0x1800209a2  mov     rax, rdi
0x1800209a5  add     rsp, 20h
0x1800209a9  pop     rdi
0x1800209aa  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002dee0`
- end: `0x18002df3b`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18002de54`
- `0x18002dee0`
- `0x180037010`

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
0x18002dee0  mov     [rsp+arg_0], rbx
0x18002dee5  push    rdi
0x18002dee6  sub     rsp, 20h
0x18002deea  mov     dword ptr [rcx+18h], 0C0000001h
0x18002def1  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18002def8  mov     [rcx], rax
0x18002defb  mov     rdi, rcx
0x18002defe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002df05  mov     ebx, edx
0x18002df07  mov     rax, [rcx]
0x18002df0a  mov     rax, [rax+10h]
0x18002df0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df13  mov     rcx, rdi; this
0x18002df16  call    ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
0x18002df1b  test    bl, 1
0x18002df1e  jz      short loc_18002DF2D
0x18002df20  mov     edx, 90h; unsigned __int64
0x18002df25  mov     rcx, rdi; void *
0x18002df28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002df2d  mov     rbx, [rsp+28h+arg_0]
0x18002df32  mov     rax, rdi
0x18002df35  add     rsp, 20h
0x18002df39  pop     rdi
0x18002df3a  retn
```

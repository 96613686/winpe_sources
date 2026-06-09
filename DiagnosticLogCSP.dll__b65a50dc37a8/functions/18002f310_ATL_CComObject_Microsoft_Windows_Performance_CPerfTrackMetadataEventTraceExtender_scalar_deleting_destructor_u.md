# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002f310`
- end: `0x18002f36c`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x18002f278`
- `0x18002f310`
- `0x180039010`

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
0x18002f310  mov     [rsp+arg_0], rbx
0x18002f315  push    rdi
0x18002f316  sub     rsp, 20h
0x18002f31a  mov     dword ptr [rcx+18h], 0C0000001h
0x18002f321  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18002f328  mov     [rcx], rax
0x18002f32b  mov     rdi, rcx
0x18002f32e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002f335  mov     ebx, edx
0x18002f337  mov     rax, [rcx]
0x18002f33a  mov     rax, [rax+10h]
0x18002f33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f343  mov     rcx, rdi; this
0x18002f346  call    ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
0x18002f34b  test    bl, 1
0x18002f34e  jz      short loc_18002F35D
0x18002f350  mov     edx, 90h; unsigned __int64
0x18002f355  mov     rcx, rdi; void *
0x18002f358  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002f35d  mov     rbx, [rsp+28h+arg_0]
0x18002f362  mov     rax, rdi
0x18002f365  add     rsp, 20h
0x18002f369  pop     rdi
0x18002f36a  retn
```

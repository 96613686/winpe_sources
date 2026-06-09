# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002ce10`
- end: `0x18002ce6c`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x18002c938`
- `0x18002ce10`
- `0x180039010`

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
0x18002ce10  mov     [rsp+arg_0], rbx
0x18002ce15  push    rdi
0x18002ce16  sub     rsp, 20h
0x18002ce1a  mov     dword ptr [rcx+18h], 0C0000001h
0x18002ce21  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18002ce28  mov     [rcx], rax
0x18002ce2b  mov     rdi, rcx
0x18002ce2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002ce35  mov     ebx, edx
0x18002ce37  mov     rax, [rcx]
0x18002ce3a  mov     rax, [rax+10h]
0x18002ce3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce43  mov     rcx, rdi; this
0x18002ce46  call    ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
0x18002ce4b  test    bl, 1
0x18002ce4e  jz      short loc_18002CE5D
0x18002ce50  mov     edx, 180h; unsigned __int64
0x18002ce55  mov     rcx, rdi; void *
0x18002ce58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ce5d  mov     rbx, [rsp+28h+arg_0]
0x18002ce62  mov     rax, rdi
0x18002ce65  add     rsp, 20h
0x18002ce69  pop     rdi
0x18002ce6a  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001dc00`
- end: `0x18001dc66`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001dc00`
- `0x18001dc68`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
  *((_DWORD *)this + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001dc00  mov     [rsp+arg_0], rcx
0x18001dc05  push    rdi
0x18001dc06  sub     rsp, 30h
0x18001dc0a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001dc13  mov     [rsp+38h+arg_8], rbx
0x18001dc18  mov     ebx, edx
0x18001dc1a  mov     rdi, rcx
0x18001dc1d  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001dc24  mov     [rcx], rax
0x18001dc27  mov     dword ptr [rcx+18h], 0C0000001h
0x18001dc2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001dc35  mov     rax, [rcx]
0x18001dc38  mov     rax, [rax+10h]
0x18001dc3c  call    cs:__guard_dispatch_icall_fptr
0x18001dc42  nop
0x18001dc43  mov     rcx, rdi; this
0x18001dc46  call    ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
0x18001dc4b  test    bl, 1
0x18001dc4e  jz      short loc_18001DC58
0x18001dc50  mov     rcx, rdi; Block
0x18001dc53  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dc58  mov     rax, rdi
0x18001dc5b  mov     rbx, [rsp+38h+arg_8]
0x18001dc60  add     rsp, 30h
0x18001dc64  pop     rdi
0x18001dc65  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001a170`
- end: `0x18001a1d6`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001790c`
- `0x18001a170`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
  *((_DWORD *)this + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001a170  mov     [rsp+arg_0], rcx
0x18001a175  push    rdi
0x18001a176  sub     rsp, 30h
0x18001a17a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001a183  mov     [rsp+38h+arg_8], rbx
0x18001a188  mov     ebx, edx
0x18001a18a  mov     rdi, rcx
0x18001a18d  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001a194  mov     [rcx], rax
0x18001a197  mov     dword ptr [rcx+18h], 0C0000001h
0x18001a19e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001a1a5  mov     rax, [rcx]
0x18001a1a8  mov     rax, [rax+10h]
0x18001a1ac  call    cs:__guard_dispatch_icall_fptr
0x18001a1b2  nop
0x18001a1b3  mov     rcx, rdi; this
0x18001a1b6  call    ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
0x18001a1bb  test    bl, 1
0x18001a1be  jz      short loc_18001A1C8
0x18001a1c0  mov     rcx, rdi; Block
0x18001a1c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a1c8  mov     rax, rdi
0x18001a1cb  mov     rbx, [rsp+38h+arg_8]
0x18001a1d0  add     rsp, 30h
0x18001a1d4  pop     rdi
0x18001a1d5  retn
```

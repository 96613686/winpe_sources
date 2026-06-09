# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18000f5f0`
- end: `0x18000f656`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000f5f0`
- `0x18000f658`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
  *((_DWORD *)this + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000f5f0  mov     [rsp+arg_0], rcx
0x18000f5f5  push    rdi
0x18000f5f6  sub     rsp, 30h
0x18000f5fa  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000f603  mov     [rsp+38h+arg_8], rbx
0x18000f608  mov     ebx, edx
0x18000f60a  mov     rdi, rcx
0x18000f60d  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x18000f614  mov     [rcx], rax
0x18000f617  mov     dword ptr [rcx+18h], 0C0000001h
0x18000f61e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f625  mov     rax, [rcx]
0x18000f628  mov     rax, [rax+10h]
0x18000f62c  call    cs:__guard_dispatch_icall_fptr
0x18000f632  nop
0x18000f633  mov     rcx, rdi; this
0x18000f636  call    ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
0x18000f63b  test    bl, 1
0x18000f63e  jz      short loc_18000F648
0x18000f640  mov     rcx, rdi; Block
0x18000f643  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f648  mov     rax, rdi
0x18000f64b  mov     rbx, [rsp+38h+arg_8]
0x18000f650  add     rsp, 30h
0x18000f654  pop     rdi
0x18000f655  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180015c80`
- end: `0x180015ce6`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `102`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015c80`
- `0x180015ce8`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char a2)
{
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
  *((_DWORD *)this + 6) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015c80  mov     [rsp+arg_0], rcx
0x180015c85  push    rdi
0x180015c86  sub     rsp, 30h
0x180015c8a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180015c93  mov     [rsp+38h+arg_8], rbx
0x180015c98  mov     ebx, edx
0x180015c9a  mov     rdi, rcx
0x180015c9d  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180015ca4  mov     [rcx], rax
0x180015ca7  mov     dword ptr [rcx+18h], 0C0000001h
0x180015cae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015cb5  mov     rax, [rcx]
0x180015cb8  mov     rax, [rax+10h]
0x180015cbc  call    cs:__guard_dispatch_icall_fptr
0x180015cc2  nop
0x180015cc3  mov     rcx, rdi; this
0x180015cc6  call    ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
0x180015ccb  test    bl, 1
0x180015cce  jz      short loc_180015CD8
0x180015cd0  mov     rcx, rdi; Block
0x180015cd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015cd8  mov     rax, rdi
0x180015cdb  mov     rbx, [rsp+38h+arg_8]
0x180015ce0  add     rsp, 30h
0x180015ce4  pop     rdi
0x180015ce5  retn
```

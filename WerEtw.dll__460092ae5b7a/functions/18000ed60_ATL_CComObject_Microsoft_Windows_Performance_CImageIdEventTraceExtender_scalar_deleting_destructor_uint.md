# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18000ed60`
- end: `0x18000edbb`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x18000e6cc`
- `0x18000ed60`
- `0x18002a010`

## pseudocode

```c
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ed60  mov     [rsp+arg_0], rbx
0x18000ed65  push    rdi
0x18000ed66  sub     rsp, 20h
0x18000ed6a  mov     dword ptr [rcx+18h], 0C0000001h
0x18000ed71  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x18000ed78  mov     [rcx], rax
0x18000ed7b  mov     rdi, rcx
0x18000ed7e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ed85  mov     ebx, edx
0x18000ed87  mov     rax, [rcx]
0x18000ed8a  mov     rax, [rax+10h]
0x18000ed8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed93  mov     rcx, rdi; this
0x18000ed96  call    ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
0x18000ed9b  test    bl, 1
0x18000ed9e  jz      short loc_18000EDAD
0x18000eda0  mov     edx, 1A8h
0x18000eda5  mov     rcx, rdi; Block
0x18000eda8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000edad  mov     rbx, [rsp+28h+arg_0]
0x18000edb2  mov     rax, rdi
0x18000edb5  add     rsp, 20h
0x18000edb9  pop     rdi
0x18000edba  retn
```

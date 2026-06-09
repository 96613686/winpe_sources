# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180016650`
- end: `0x1800166ab`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x1800161d0`
- `0x180016650`
- `0x18002a010`

## pseudocode

```c
Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180016650  mov     [rsp+arg_0], rbx
0x180016655  push    rdi
0x180016656  sub     rsp, 20h
0x18001665a  mov     dword ptr [rcx+18h], 0C0000001h
0x180016661  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180016668  mov     [rcx], rax
0x18001666b  mov     rdi, rcx
0x18001666e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180016675  mov     ebx, edx
0x180016677  mov     rax, [rcx]
0x18001667a  mov     rax, [rax+10h]
0x18001667e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016683  mov     rcx, rdi; this
0x180016686  call    ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
0x18001668b  test    bl, 1
0x18001668e  jz      short loc_18001669D
0x180016690  mov     edx, 0B8h
0x180016695  mov     rcx, rdi; Block
0x180016698  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001669d  mov     rbx, [rsp+28h+arg_0]
0x1800166a2  mov     rax, rdi
0x1800166a5  add     rsp, 20h
0x1800166a9  pop     rdi
0x1800166aa  retn
```

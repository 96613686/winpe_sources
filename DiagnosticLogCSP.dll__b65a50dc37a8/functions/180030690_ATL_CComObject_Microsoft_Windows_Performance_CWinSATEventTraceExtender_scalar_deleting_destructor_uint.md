# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180030690`
- end: `0x1800306ec`
- name: `??_G?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x180030604`
- `0x180030690`
- `0x180039010`

## pseudocode

```c
Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180030690  mov     [rsp+arg_0], rbx
0x180030695  push    rdi
0x180030696  sub     rsp, 20h
0x18003069a  mov     dword ptr [rcx+18h], 0C0000001h
0x1800306a1  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x1800306a8  mov     [rcx], rax
0x1800306ab  mov     rdi, rcx
0x1800306ae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800306b5  mov     ebx, edx
0x1800306b7  mov     rax, [rcx]
0x1800306ba  mov     rax, [rax+10h]
0x1800306be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306c3  mov     rcx, rdi; this
0x1800306c6  call    ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
0x1800306cb  test    bl, 1
0x1800306ce  jz      short loc_1800306DD
0x1800306d0  mov     edx, 68h ; 'h'; unsigned __int64
0x1800306d5  mov     rcx, rdi; void *
0x1800306d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800306dd  mov     rbx, [rsp+28h+arg_0]
0x1800306e2  mov     rax, rdi
0x1800306e5  add     rsp, 20h
0x1800306e9  pop     rdi
0x1800306ea  retn
```

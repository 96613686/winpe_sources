# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180021ce0`
- end: `0x180021d3b`
- name: `??_G?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180021c6c`
- `0x180021ce0`
- `0x18002a010`

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
0x180021ce0  mov     [rsp+arg_0], rbx
0x180021ce5  push    rdi
0x180021ce6  sub     rsp, 20h
0x180021cea  mov     dword ptr [rcx+18h], 0C0000001h
0x180021cf1  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x180021cf8  mov     [rcx], rax
0x180021cfb  mov     rdi, rcx
0x180021cfe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021d05  mov     ebx, edx
0x180021d07  mov     rax, [rcx]
0x180021d0a  mov     rax, [rax+10h]
0x180021d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d13  mov     rcx, rdi; this
0x180021d16  call    ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
0x180021d1b  test    bl, 1
0x180021d1e  jz      short loc_180021D2D
0x180021d20  mov     edx, 68h ; 'h'
0x180021d25  mov     rcx, rdi; Block
0x180021d28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021d2d  mov     rbx, [rsp+28h+arg_0]
0x180021d32  mov     rax, rdi
0x180021d35  add     rsp, 20h
0x180021d39  pop     rdi
0x180021d3a  retn
```

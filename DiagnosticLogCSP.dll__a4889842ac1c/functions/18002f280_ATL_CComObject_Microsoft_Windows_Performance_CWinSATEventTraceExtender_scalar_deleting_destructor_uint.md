# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002f280`
- end: `0x18002f2db`
- name: `??_G?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18002f200`
- `0x18002f280`
- `0x180037010`

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
0x18002f280  mov     [rsp+arg_0], rbx
0x18002f285  push    rdi
0x18002f286  sub     rsp, 20h
0x18002f28a  mov     dword ptr [rcx+18h], 0C0000001h
0x18002f291  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002f298  mov     [rcx], rax
0x18002f29b  mov     rdi, rcx
0x18002f29e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002f2a5  mov     ebx, edx
0x18002f2a7  mov     rax, [rcx]
0x18002f2aa  mov     rax, [rax+10h]
0x18002f2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2b3  mov     rcx, rdi; this
0x18002f2b6  call    ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
0x18002f2bb  test    bl, 1
0x18002f2be  jz      short loc_18002F2CD
0x18002f2c0  mov     edx, 68h ; 'h'; unsigned __int64
0x18002f2c5  mov     rcx, rdi; void *
0x18002f2c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002f2cd  mov     rbx, [rsp+28h+arg_0]
0x18002f2d2  mov     rax, rdi
0x18002f2d5  add     rsp, 20h
0x18002f2d9  pop     rdi
0x18002f2da  retn
```

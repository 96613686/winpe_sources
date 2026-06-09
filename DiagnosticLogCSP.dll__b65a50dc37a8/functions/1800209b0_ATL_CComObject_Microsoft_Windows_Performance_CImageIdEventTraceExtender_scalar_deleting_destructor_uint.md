# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x1800209b0`
- end: `0x180020a0c`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x1800202fc`
- `0x1800209b0`
- `0x180039010`

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
0x1800209b0  mov     [rsp+arg_0], rbx
0x1800209b5  push    rdi
0x1800209b6  sub     rsp, 20h
0x1800209ba  mov     dword ptr [rcx+18h], 0C0000001h
0x1800209c1  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x1800209c8  mov     [rcx], rax
0x1800209cb  mov     rdi, rcx
0x1800209ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800209d5  mov     ebx, edx
0x1800209d7  mov     rax, [rcx]
0x1800209da  mov     rax, [rax+10h]
0x1800209de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209e3  mov     rcx, rdi; this
0x1800209e6  call    ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
0x1800209eb  test    bl, 1
0x1800209ee  jz      short loc_1800209FD
0x1800209f0  mov     edx, 1A8h; unsigned __int64
0x1800209f5  mov     rcx, rdi; void *
0x1800209f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800209fd  mov     rbx, [rsp+28h+arg_0]
0x180020a02  mov     rax, rdi
0x180020a05  add     rsp, 20h
0x180020a09  pop     rdi
0x180020a0a  retn
```

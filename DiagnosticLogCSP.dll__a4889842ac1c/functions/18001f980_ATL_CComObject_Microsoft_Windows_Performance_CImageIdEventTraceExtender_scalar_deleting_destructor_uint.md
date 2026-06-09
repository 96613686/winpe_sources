# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001f980`
- end: `0x18001f9db`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18001f2ec`
- `0x18001f980`
- `0x180037010`

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
0x18001f980  mov     [rsp+arg_0], rbx
0x18001f985  push    rdi
0x18001f986  sub     rsp, 20h
0x18001f98a  mov     dword ptr [rcx+18h], 0C0000001h
0x18001f991  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x18001f998  mov     [rcx], rax
0x18001f99b  mov     rdi, rcx
0x18001f99e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001f9a5  mov     ebx, edx
0x18001f9a7  mov     rax, [rcx]
0x18001f9aa  mov     rax, [rax+10h]
0x18001f9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9b3  mov     rcx, rdi; this
0x18001f9b6  call    ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
0x18001f9bb  test    bl, 1
0x18001f9be  jz      short loc_18001F9CD
0x18001f9c0  mov     edx, 1A8h; unsigned __int64
0x18001f9c5  mov     rcx, rdi; void *
0x18001f9c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f9cd  mov     rbx, [rsp+28h+arg_0]
0x18001f9d2  mov     rax, rdi
0x18001f9d5  add     rsp, 20h
0x18001f9d9  pop     rdi
0x18001f9da  retn
```

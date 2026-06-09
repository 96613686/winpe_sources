# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180031f40`
- end: `0x180031f9c`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x180031d20`
- `0x180031f40`
- `0x180039010`

## pseudocode

```c
Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180031f40  mov     [rsp+arg_0], rbx
0x180031f45  push    rdi
0x180031f46  sub     rsp, 20h
0x180031f4a  mov     dword ptr [rcx+18h], 0C0000001h
0x180031f51  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180031f58  mov     [rcx], rax
0x180031f5b  mov     rdi, rcx
0x180031f5e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180031f65  mov     ebx, edx
0x180031f67  mov     rax, [rcx]
0x180031f6a  mov     rax, [rax+10h]
0x180031f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f73  mov     rcx, rdi; this
0x180031f76  call    ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
0x180031f7b  test    bl, 1
0x180031f7e  jz      short loc_180031F8D
0x180031f80  mov     edx, 50h ; 'P'; unsigned __int64
0x180031f85  mov     rcx, rdi; void *
0x180031f88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180031f8d  mov     rbx, [rsp+28h+arg_0]
0x180031f92  mov     rax, rdi
0x180031f95  add     rsp, 20h
0x180031f99  pop     rdi
0x180031f9a  retn
```

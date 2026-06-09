# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180028600`
- end: `0x18002865c`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x180028150`
- `0x180028600`
- `0x180039010`

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
0x180028600  mov     [rsp+arg_0], rbx
0x180028605  push    rdi
0x180028606  sub     rsp, 20h
0x18002860a  mov     dword ptr [rcx+18h], 0C0000001h
0x180028611  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180028618  mov     [rcx], rax
0x18002861b  mov     rdi, rcx
0x18002861e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180028625  mov     ebx, edx
0x180028627  mov     rax, [rcx]
0x18002862a  mov     rax, [rax+10h]
0x18002862e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028633  mov     rcx, rdi; this
0x180028636  call    ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
0x18002863b  test    bl, 1
0x18002863e  jz      short loc_18002864D
0x180028640  mov     edx, 0B8h; unsigned __int64
0x180028645  mov     rcx, rdi; void *
0x180028648  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002864d  mov     rbx, [rsp+28h+arg_0]
0x180028652  mov     rax, rdi
0x180028655  add     rsp, 20h
0x180028659  pop     rdi
0x18002865a  retn
```

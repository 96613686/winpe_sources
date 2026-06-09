# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180029960`
- end: `0x1800299bb`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18002989c`
- `0x180029960`
- `0x180037010`

## pseudocode

```c
Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180029960  mov     [rsp+arg_0], rbx
0x180029965  push    rdi
0x180029966  sub     rsp, 20h
0x18002996a  mov     dword ptr [rcx+18h], 0C0000001h
0x180029971  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180029978  mov     [rcx], rax
0x18002997b  mov     rdi, rcx
0x18002997e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180029985  mov     ebx, edx
0x180029987  mov     rax, [rcx]
0x18002998a  mov     rax, [rax+10h]
0x18002998e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029993  mov     rcx, rdi; this
0x180029996  call    ??1CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(void)
0x18002999b  test    bl, 1
0x18002999e  jz      short loc_1800299AD
0x1800299a0  mov     edx, 0B0h; unsigned __int64
0x1800299a5  mov     rcx, rdi; void *
0x1800299a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800299ad  mov     rbx, [rsp+28h+arg_0]
0x1800299b2  mov     rax, rdi
0x1800299b5  add     rsp, 20h
0x1800299b9  pop     rdi
0x1800299ba  retn
```

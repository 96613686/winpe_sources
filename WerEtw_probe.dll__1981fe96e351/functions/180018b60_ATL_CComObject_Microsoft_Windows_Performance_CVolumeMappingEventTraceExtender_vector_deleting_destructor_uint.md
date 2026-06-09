# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180018b60`
- end: `0x180018bbb`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `91`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180018a9c`
- `0x180018b60`
- `0x18002a010`

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
0x180018b60  mov     [rsp+arg_0], rbx
0x180018b65  push    rdi
0x180018b66  sub     rsp, 20h
0x180018b6a  mov     dword ptr [rcx+18h], 0C0000001h
0x180018b71  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180018b78  mov     [rcx], rax
0x180018b7b  mov     rdi, rcx
0x180018b7e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180018b85  mov     ebx, edx
0x180018b87  mov     rax, [rcx]
0x180018b8a  mov     rax, [rax+10h]
0x180018b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b93  mov     rcx, rdi; this
0x180018b96  call    ??1CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(void)
0x180018b9b  test    bl, 1
0x180018b9e  jz      short loc_180018BAD
0x180018ba0  mov     edx, 0B0h
0x180018ba5  mov     rcx, rdi; Block
0x180018ba8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018bad  mov     rbx, [rsp+28h+arg_0]
0x180018bb2  mov     rax, rdi
0x180018bb5  add     rsp, 20h
0x180018bb9  pop     rdi
0x180018bba  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18002abe0`
- end: `0x18002ac3c`
- name: `??_E?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x18002ab20`
- `0x18002abe0`
- `0x180039010`

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
0x18002abe0  mov     [rsp+arg_0], rbx
0x18002abe5  push    rdi
0x18002abe6  sub     rsp, 20h
0x18002abea  mov     dword ptr [rcx+18h], 0C0000001h
0x18002abf1  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18002abf8  mov     [rcx], rax
0x18002abfb  mov     rdi, rcx
0x18002abfe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002ac05  mov     ebx, edx
0x18002ac07  mov     rax, [rcx]
0x18002ac0a  mov     rax, [rax+10h]
0x18002ac0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac13  mov     rcx, rdi; this
0x18002ac16  call    ??1CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::~CVolumeMappingEventTraceExtender(void)
0x18002ac1b  test    bl, 1
0x18002ac1e  jz      short loc_18002AC2D
0x18002ac20  mov     edx, 0B0h; unsigned __int64
0x18002ac25  mov     rcx, rdi; void *
0x18002ac28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ac2d  mov     rbx, [rsp+28h+arg_0]
0x18002ac32  mov     rax, rdi
0x18002ac35  add     rsp, 20h
0x18002ac39  pop     rdi
0x18002ac3a  retn
```

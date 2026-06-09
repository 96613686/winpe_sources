# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x180015ec0`
- end: `0x180015f1d`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `93`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bf8`
- `0x180015c1c`
- `0x180015ec0`
- `0x180039010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger((Microsoft::Windows::Performance::CEventTraceRelogger *)(a1 + 4));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180015ec0  mov     [rsp+arg_0], rbx
0x180015ec5  push    rdi
0x180015ec6  sub     rsp, 20h
0x180015eca  mov     dword ptr [rcx+8], 0C0000001h
0x180015ed1  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180015ed8  mov     [rcx], rax
0x180015edb  mov     rdi, rcx
0x180015ede  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015ee5  mov     ebx, edx
0x180015ee7  mov     rax, [rcx]
0x180015eea  mov     rax, [rax+10h]
0x180015eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef3  lea     rcx, [rdi+10h]; this
0x180015ef7  call    ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
0x180015efc  test    bl, 1
0x180015eff  jz      short loc_180015F0E
0x180015f01  mov     edx, 0C0h; unsigned __int64
0x180015f06  mov     rcx, rdi; void *
0x180015f09  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015f0e  mov     rbx, [rsp+28h+arg_0]
0x180015f13  mov     rax, rdi
0x180015f16  add     rsp, 20h
0x180015f1a  pop     rdi
0x180015f1b  retn
```

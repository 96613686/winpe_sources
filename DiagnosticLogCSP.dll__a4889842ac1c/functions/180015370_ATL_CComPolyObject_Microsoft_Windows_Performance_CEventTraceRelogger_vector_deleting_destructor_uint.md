# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x180015370`
- end: `0x1800153cc`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001bc8`
- `0x18001505c`
- `0x180015370`
- `0x180037010`

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
0x180015370  mov     [rsp+arg_0], rbx
0x180015375  push    rdi
0x180015376  sub     rsp, 20h
0x18001537a  mov     dword ptr [rcx+8], 0C0000001h
0x180015381  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180015388  mov     [rcx], rax
0x18001538b  mov     rdi, rcx
0x18001538e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015395  mov     ebx, edx
0x180015397  mov     rax, [rcx]
0x18001539a  mov     rax, [rax+10h]
0x18001539e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a3  lea     rcx, [rdi+10h]; this
0x1800153a7  call    ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
0x1800153ac  test    bl, 1
0x1800153af  jz      short loc_1800153BE
0x1800153b1  mov     edx, 0C0h; unsigned __int64
0x1800153b6  mov     rcx, rdi; void *
0x1800153b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800153be  mov     rbx, [rsp+28h+arg_0]
0x1800153c3  mov     rax, rdi
0x1800153c6  add     rsp, 20h
0x1800153ca  pop     rdi
0x1800153cb  retn
```

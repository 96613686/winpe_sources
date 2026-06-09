# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x1800042d0`
- end: `0x18000432c`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180003fb8`
- `0x1800042d0`
- `0x18002a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger((Microsoft::Windows::Performance::CEventTraceRelogger *)(Block + 4));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800042d0  mov     [rsp+arg_0], rbx
0x1800042d5  push    rdi
0x1800042d6  sub     rsp, 20h
0x1800042da  mov     dword ptr [rcx+8], 0C0000001h
0x1800042e1  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x1800042e8  mov     [rcx], rax
0x1800042eb  mov     rdi, rcx
0x1800042ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800042f5  mov     ebx, edx
0x1800042f7  mov     rax, [rcx]
0x1800042fa  mov     rax, [rax+10h]
0x1800042fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004303  lea     rcx, [rdi+10h]; this
0x180004307  call    ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
0x18000430c  test    bl, 1
0x18000430f  jz      short loc_18000431E
0x180004311  mov     edx, 0C0h
0x180004316  mov     rcx, rdi; Block
0x180004319  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000431e  mov     rbx, [rsp+28h+arg_0]
0x180004323  mov     rax, rdi
0x180004326  add     rsp, 20h
0x18000432a  pop     rdi
0x18000432b  retn
```

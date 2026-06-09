# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x180005860`
- end: `0x1800058c7`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800029e4`
- `0x180005860`
- `0x1800268f4`
- `0x180027910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  *(_QWORD *)Block = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  Block[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger((Microsoft::Windows::Performance::CEventTraceRelogger *)(Block + 4));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005860  mov     [rsp+arg_0], rcx
0x180005865  push    rdi
0x180005866  sub     rsp, 30h
0x18000586a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005873  mov     [rsp+38h+arg_8], rbx
0x180005878  mov     ebx, edx
0x18000587a  mov     rdi, rcx
0x18000587d  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x180005884  mov     [rcx], rax
0x180005887  mov     dword ptr [rcx+8], 0C0000001h
0x18000588e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005895  mov     rax, [rcx]
0x180005898  mov     rax, [rax+10h]
0x18000589c  call    cs:__guard_dispatch_icall_fptr
0x1800058a2  nop
0x1800058a3  lea     rcx, [rdi+10h]; this
0x1800058a7  call    ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
0x1800058ac  test    bl, 1
0x1800058af  jz      short loc_1800058B9
0x1800058b1  mov     rcx, rdi; Block
0x1800058b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800058b9  mov     rax, rdi
0x1800058bc  mov     rbx, [rsp+38h+arg_8]
0x1800058c1  add     rsp, 30h
0x1800058c5  pop     rdi
0x1800058c6  retn
```

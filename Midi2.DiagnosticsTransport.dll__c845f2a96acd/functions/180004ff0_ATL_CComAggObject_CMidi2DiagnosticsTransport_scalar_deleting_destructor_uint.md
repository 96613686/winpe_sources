# ATL::CComAggObject<CMidi2DiagnosticsTransport>::`scalar deleting destructor'(uint)

- ea: `0x180004ff0`
- end: `0x180005058`
- name: `??_G?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800033f4`
- `0x180004ff0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005031`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005031`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2DiagnosticsTransport>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2DiagnosticsTransport>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( LOBYTE(Block[2].DebugInfo) )
  {
    LOBYTE(Block[2].DebugInfo) = 0;
    DeleteCriticalSection(Block + 1);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004ff0  mov     [rsp+arg_0], rbx
0x180004ff5  push    rdi
0x180004ff6  sub     rsp, 20h
0x180004ffa  mov     dword ptr [rcx+8], 0C0000001h
0x180005001  lea     rax, ??_7?$CComAggObject@VCMidi2DiagnosticsTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2DiagnosticsTransport>::`vftable'
0x180005008  mov     [rcx], rax
0x18000500b  mov     rbx, rcx
0x18000500e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005015  mov     edi, edx
0x180005017  mov     rax, [rcx]
0x18000501a  mov     rax, [rax+10h]
0x18000501e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005023  lea     rcx, [rbx+28h]; lpCriticalSection
0x180005027  cmp     byte ptr [rcx+28h], 0
0x18000502b  jz      short loc_180005037
0x18000502d  mov     byte ptr [rcx+28h], 0
0x180005031  call    cs:__imp_DeleteCriticalSection
0x180005037  test    dil, 1
0x18000503b  jz      short loc_18000504A
0x18000503d  mov     edx, 58h ; 'X'
0x180005042  mov     rcx, rbx; Block
0x180005045  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000504a  mov     rax, rbx
0x18000504d  mov     rbx, [rsp+28h+arg_0]
0x180005052  add     rsp, 20h
0x180005056  pop     rdi
0x180005057  retn
```

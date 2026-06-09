# ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vector deleting destructor'(uint)

- ea: `0x180005680`
- end: `0x1800056e8`
- name: `??_E?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003914`
- `0x180005680`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056c1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vftable';
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
0x180005680  mov     [rsp+arg_0], rbx
0x180005685  push    rdi
0x180005686  sub     rsp, 20h
0x18000568a  mov     dword ptr [rcx+8], 0C0000001h
0x180005691  lea     rax, ??_7?$CComAggObject@VCMidi2VirtualMidiTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2VirtualMidiTransport>::`vftable'
0x180005698  mov     [rcx], rax
0x18000569b  mov     rbx, rcx
0x18000569e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800056a5  mov     edi, edx
0x1800056a7  mov     rax, [rcx]
0x1800056aa  mov     rax, [rax+10h]
0x1800056ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b3  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800056b7  cmp     byte ptr [rcx+28h], 0
0x1800056bb  jz      short loc_1800056C7
0x1800056bd  mov     byte ptr [rcx+28h], 0
0x1800056c1  call    cs:__imp_DeleteCriticalSection
0x1800056c7  test    dil, 1
0x1800056cb  jz      short loc_1800056DA
0x1800056cd  mov     edx, 58h ; 'X'
0x1800056d2  mov     rcx, rbx; Block
0x1800056d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800056da  mov     rax, rbx
0x1800056dd  mov     rbx, [rsp+28h+arg_0]
0x1800056e2  add     rsp, 20h
0x1800056e6  pop     rdi
0x1800056e7  retn
```

# ATL::CComAggObject<CMidi2MidiSrvTransport>::`scalar deleting destructor'(uint)

- ea: `0x180003e90`
- end: `0x180003ef8`
- name: `??_G?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002494`
- `0x180003e90`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ed1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ed1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2MidiSrvTransport>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2MidiSrvTransport>::`vftable';
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
0x180003e90  mov     [rsp+arg_0], rbx
0x180003e95  push    rdi
0x180003e96  sub     rsp, 20h
0x180003e9a  mov     dword ptr [rcx+8], 0C0000001h
0x180003ea1  lea     rax, ??_7?$CComAggObject@VCMidi2MidiSrvTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2MidiSrvTransport>::`vftable'
0x180003ea8  mov     [rcx], rax
0x180003eab  mov     rbx, rcx
0x180003eae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003eb5  mov     edi, edx
0x180003eb7  mov     rax, [rcx]
0x180003eba  mov     rax, [rax+10h]
0x180003ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec3  lea     rcx, [rbx+28h]; lpCriticalSection
0x180003ec7  cmp     byte ptr [rcx+28h], 0
0x180003ecb  jz      short loc_180003ED7
0x180003ecd  mov     byte ptr [rcx+28h], 0
0x180003ed1  call    cs:__imp_DeleteCriticalSection
0x180003ed7  test    dil, 1
0x180003edb  jz      short loc_180003EEA
0x180003edd  mov     edx, 58h ; 'X'
0x180003ee2  mov     rcx, rbx; Block
0x180003ee5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003eea  mov     rax, rbx
0x180003eed  mov     rbx, [rsp+28h+arg_0]
0x180003ef2  add     rsp, 20h
0x180003ef6  pop     rdi
0x180003ef7  retn
```

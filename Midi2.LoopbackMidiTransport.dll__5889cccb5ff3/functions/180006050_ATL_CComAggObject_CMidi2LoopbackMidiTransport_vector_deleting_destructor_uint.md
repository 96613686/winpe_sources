# ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vector deleting destructor'(uint)

- ea: `0x180006050`
- end: `0x1800060cf`
- name: `??_E?$CComAggObject@VCMidi2LoopbackMidiTransport@@@ATL@@UEAAPEAXI@Z`
- size: `127`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800041a4`
- `0x180006050`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060a8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800060a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  __int64 v4; // rcx

  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vftable';
  Block->LockCount = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *(_QWORD *)&Block[2].LockCount;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
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
0x180006050  mov     [rsp+arg_0], rbx
0x180006055  push    rdi
0x180006056  sub     rsp, 20h
0x18000605a  mov     edi, edx
0x18000605c  mov     rbx, rcx
0x18000605f  lea     rax, ??_7?$CComAggObject@VCMidi2LoopbackMidiTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2LoopbackMidiTransport>::`vftable'
0x180006066  mov     [rcx], rax
0x180006069  mov     dword ptr [rcx+8], 0C0000001h
0x180006070  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006077  mov     rax, [rcx]
0x18000607a  mov     rax, [rax+10h]
0x18000607e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006083  nop
0x180006084  mov     rcx, [rbx+58h]
0x180006088  test    rcx, rcx
0x18000608b  jz      short loc_18000609A
0x18000608d  mov     rax, [rcx]
0x180006090  mov     rax, [rax+10h]
0x180006094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006099  nop
0x18000609a  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000609e  cmp     byte ptr [rcx+28h], 0
0x1800060a2  jz      short loc_1800060AE
0x1800060a4  mov     byte ptr [rcx+28h], 0
0x1800060a8  call    cs:__imp_DeleteCriticalSection
0x1800060ae  test    dil, 1
0x1800060b2  jz      short loc_1800060C1
0x1800060b4  mov     edx, 60h ; '`'
0x1800060b9  mov     rcx, rbx; Block
0x1800060bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800060c1  mov     rax, rbx
0x1800060c4  mov     rbx, [rsp+28h+arg_0]
0x1800060c9  add     rsp, 20h
0x1800060cd  pop     rdi
0x1800060ce  retn
```

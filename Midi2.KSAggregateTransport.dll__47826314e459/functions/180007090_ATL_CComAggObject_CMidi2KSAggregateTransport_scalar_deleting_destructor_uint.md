# ATL::CComAggObject<CMidi2KSAggregateTransport>::`scalar deleting destructor'(uint)

- ea: `0x180007090`
- end: `0x1800070f8`
- name: `??_G?$CComAggObject@VCMidi2KSAggregateTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005044`
- `0x180007090`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800070d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800070d1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2KSAggregateTransport>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2KSAggregateTransport>::`vftable';
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
0x180007090  mov     [rsp+arg_0], rbx
0x180007095  push    rdi
0x180007096  sub     rsp, 20h
0x18000709a  mov     dword ptr [rcx+8], 0C0000001h
0x1800070a1  lea     rax, ??_7?$CComAggObject@VCMidi2KSAggregateTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2KSAggregateTransport>::`vftable'
0x1800070a8  mov     [rcx], rax
0x1800070ab  mov     rbx, rcx
0x1800070ae  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800070b5  mov     edi, edx
0x1800070b7  mov     rax, [rcx]
0x1800070ba  mov     rax, [rax+10h]
0x1800070be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c3  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800070c7  cmp     byte ptr [rcx+28h], 0
0x1800070cb  jz      short loc_1800070D7
0x1800070cd  mov     byte ptr [rcx+28h], 0
0x1800070d1  call    cs:__imp_DeleteCriticalSection
0x1800070d7  test    dil, 1
0x1800070db  jz      short loc_1800070EA
0x1800070dd  mov     edx, 58h ; 'X'
0x1800070e2  mov     rcx, rbx; Block
0x1800070e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800070ea  mov     rax, rbx
0x1800070ed  mov     rbx, [rsp+28h+arg_0]
0x1800070f2  add     rsp, 20h
0x1800070f6  pop     rdi
0x1800070f7  retn
```

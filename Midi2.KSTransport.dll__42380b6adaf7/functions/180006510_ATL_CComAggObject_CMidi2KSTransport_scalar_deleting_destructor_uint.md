# ATL::CComAggObject<CMidi2KSTransport>::`scalar deleting destructor'(uint)

- ea: `0x180006510`
- end: `0x180006578`
- name: `??_G?$CComAggObject@VCMidi2KSTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004434`
- `0x180006510`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006551`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006551`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2KSTransport>::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2KSTransport>::`vftable';
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
0x180006510  mov     [rsp+arg_0], rbx
0x180006515  push    rdi
0x180006516  sub     rsp, 20h
0x18000651a  mov     dword ptr [rcx+8], 0C0000001h
0x180006521  lea     rax, ??_7?$CComAggObject@VCMidi2KSTransport@@@ATL@@6B@; const ATL::CComAggObject<CMidi2KSTransport>::`vftable'
0x180006528  mov     [rcx], rax
0x18000652b  mov     rbx, rcx
0x18000652e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006535  mov     edi, edx
0x180006537  mov     rax, [rcx]
0x18000653a  mov     rax, [rax+10h]
0x18000653e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006543  lea     rcx, [rbx+28h]; lpCriticalSection
0x180006547  cmp     byte ptr [rcx+28h], 0
0x18000654b  jz      short loc_180006557
0x18000654d  mov     byte ptr [rcx+28h], 0
0x180006551  call    cs:__imp_DeleteCriticalSection
0x180006557  test    dil, 1
0x18000655b  jz      short loc_18000656A
0x18000655d  mov     edx, 58h ; 'X'
0x180006562  mov     rcx, rbx; Block
0x180006565  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000656a  mov     rax, rbx
0x18000656d  mov     rbx, [rsp+28h+arg_0]
0x180006572  add     rsp, 20h
0x180006576  pop     rdi
0x180006577  retn
```

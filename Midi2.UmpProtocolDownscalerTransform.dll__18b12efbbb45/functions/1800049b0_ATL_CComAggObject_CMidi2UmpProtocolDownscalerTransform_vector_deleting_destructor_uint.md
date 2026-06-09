# ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vector deleting destructor'(uint)

- ea: `0x1800049b0`
- end: `0x180004a18`
- name: `??_E?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x1800049b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049f1`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  Block->LockCount = -1073741823;
  Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vftable';
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
0x1800049b0  mov     [rsp+arg_0], rbx
0x1800049b5  push    rdi
0x1800049b6  sub     rsp, 20h
0x1800049ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800049c1  lea     rax, ??_7?$CComAggObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2UmpProtocolDownscalerTransform>::`vftable'
0x1800049c8  mov     [rcx], rax
0x1800049cb  mov     rbx, rcx
0x1800049ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800049d5  mov     edi, edx
0x1800049d7  mov     rax, [rcx]
0x1800049da  mov     rax, [rax+10h]
0x1800049de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049e3  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800049e7  cmp     byte ptr [rcx+28h], 0
0x1800049eb  jz      short loc_1800049F7
0x1800049ed  mov     byte ptr [rcx+28h], 0
0x1800049f1  call    cs:__imp_DeleteCriticalSection
0x1800049f7  test    dil, 1
0x1800049fb  jz      short loc_180004A0A
0x1800049fd  mov     edx, 58h ; 'X'
0x180004a02  mov     rcx, rbx; Block
0x180004a05  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004a0a  mov     rax, rbx
0x180004a0d  mov     rbx, [rsp+28h+arg_0]
0x180004a12  add     rsp, 20h
0x180004a16  pop     rdi
0x180004a17  retn
```

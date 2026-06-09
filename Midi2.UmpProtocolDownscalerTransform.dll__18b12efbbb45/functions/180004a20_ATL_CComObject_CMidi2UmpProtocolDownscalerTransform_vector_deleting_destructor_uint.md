# ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::`vector deleting destructor'(uint)

- ea: `0x180004a20`
- end: `0x180004a88`
- name: `??_E?$CComObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002e94`
- `0x180004a20`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004a61`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::`vector deleting destructor'(
        char *Block,
        char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[56] )
  {
    Block[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004a20  mov     [rsp+arg_0], rbx
0x180004a25  push    rdi
0x180004a26  sub     rsp, 20h
0x180004a2a  mov     dword ptr [rcx+8], 0C0000001h
0x180004a31  lea     rax, ??_7?$CComObject@VCMidi2UmpProtocolDownscalerTransform@@@ATL@@6B@; const ATL::CComObject<CMidi2UmpProtocolDownscalerTransform>::`vftable'
0x180004a38  mov     [rcx], rax
0x180004a3b  mov     rbx, rcx
0x180004a3e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a45  mov     edi, edx
0x180004a47  mov     rax, [rcx]
0x180004a4a  mov     rax, [rax+10h]
0x180004a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a53  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004a57  cmp     byte ptr [rcx+28h], 0
0x180004a5b  jz      short loc_180004A67
0x180004a5d  mov     byte ptr [rcx+28h], 0
0x180004a61  call    cs:__imp_DeleteCriticalSection
0x180004a67  test    dil, 1
0x180004a6b  jz      short loc_180004A7A
0x180004a6d  mov     edx, 40h ; '@'
0x180004a72  mov     rcx, rbx; Block
0x180004a75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004a7a  mov     rax, rbx
0x180004a7d  mov     rbx, [rsp+28h+arg_0]
0x180004a82  add     rsp, 20h
0x180004a86  pop     rdi
0x180004a87  retn
```

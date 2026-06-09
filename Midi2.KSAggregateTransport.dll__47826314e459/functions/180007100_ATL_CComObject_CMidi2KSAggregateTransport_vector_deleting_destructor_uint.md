# ATL::CComObject<CMidi2KSAggregateTransport>::`vector deleting destructor'(uint)

- ea: `0x180007100`
- end: `0x180007168`
- name: `??_E?$CComObject@VCMidi2KSAggregateTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005044`
- `0x180007100`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007141`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007141`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2KSAggregateTransport>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2KSAggregateTransport>::`vftable';
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
0x180007100  mov     [rsp+arg_0], rbx
0x180007105  push    rdi
0x180007106  sub     rsp, 20h
0x18000710a  mov     dword ptr [rcx+8], 0C0000001h
0x180007111  lea     rax, ??_7?$CComObject@VCMidi2KSAggregateTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2KSAggregateTransport>::`vftable'
0x180007118  mov     [rcx], rax
0x18000711b  mov     rbx, rcx
0x18000711e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007125  mov     edi, edx
0x180007127  mov     rax, [rcx]
0x18000712a  mov     rax, [rax+10h]
0x18000712e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007133  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007137  cmp     byte ptr [rcx+28h], 0
0x18000713b  jz      short loc_180007147
0x18000713d  mov     byte ptr [rcx+28h], 0
0x180007141  call    cs:__imp_DeleteCriticalSection
0x180007147  test    dil, 1
0x18000714b  jz      short loc_18000715A
0x18000714d  mov     edx, 40h ; '@'
0x180007152  mov     rcx, rbx; Block
0x180007155  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000715a  mov     rax, rbx
0x18000715d  mov     rbx, [rsp+28h+arg_0]
0x180007162  add     rsp, 20h
0x180007166  pop     rdi
0x180007167  retn
```

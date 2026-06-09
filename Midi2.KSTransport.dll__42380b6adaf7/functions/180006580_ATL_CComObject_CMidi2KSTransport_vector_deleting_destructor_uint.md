# ATL::CComObject<CMidi2KSTransport>::`vector deleting destructor'(uint)

- ea: `0x180006580`
- end: `0x1800065e8`
- name: `??_E?$CComObject@VCMidi2KSTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004434`
- `0x180006580`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800065c1`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2KSTransport>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2KSTransport>::`vftable';
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
0x180006580  mov     [rsp+arg_0], rbx
0x180006585  push    rdi
0x180006586  sub     rsp, 20h
0x18000658a  mov     dword ptr [rcx+8], 0C0000001h
0x180006591  lea     rax, ??_7?$CComObject@VCMidi2KSTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2KSTransport>::`vftable'
0x180006598  mov     [rcx], rax
0x18000659b  mov     rbx, rcx
0x18000659e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800065a5  mov     edi, edx
0x1800065a7  mov     rax, [rcx]
0x1800065aa  mov     rax, [rax+10h]
0x1800065ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065b3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800065b7  cmp     byte ptr [rcx+28h], 0
0x1800065bb  jz      short loc_1800065C7
0x1800065bd  mov     byte ptr [rcx+28h], 0
0x1800065c1  call    cs:__imp_DeleteCriticalSection
0x1800065c7  test    dil, 1
0x1800065cb  jz      short loc_1800065DA
0x1800065cd  mov     edx, 40h ; '@'
0x1800065d2  mov     rcx, rbx; Block
0x1800065d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800065da  mov     rax, rbx
0x1800065dd  mov     rbx, [rsp+28h+arg_0]
0x1800065e2  add     rsp, 20h
0x1800065e6  pop     rdi
0x1800065e7  retn
```

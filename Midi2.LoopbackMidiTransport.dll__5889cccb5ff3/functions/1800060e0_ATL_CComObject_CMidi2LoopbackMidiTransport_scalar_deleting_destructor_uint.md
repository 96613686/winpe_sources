# ATL::CComObject<CMidi2LoopbackMidiTransport>::`scalar deleting destructor'(uint)

- ea: `0x1800060e0`
- end: `0x18000615f`
- name: `??_G?$CComObject@VCMidi2LoopbackMidiTransport@@@ATL@@UEAAPEAXI@Z`
- size: `127`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800041a4`
- `0x1800060e0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006138`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006138`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2LoopbackMidiTransport>::`scalar deleting destructor'(char *Block, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)Block = &ATL::CComObject<CMidi2LoopbackMidiTransport>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 8);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
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
0x1800060e0  mov     [rsp+arg_0], rbx
0x1800060e5  push    rdi
0x1800060e6  sub     rsp, 20h
0x1800060ea  mov     edi, edx
0x1800060ec  mov     rbx, rcx
0x1800060ef  lea     rax, ??_7?$CComObject@VCMidi2LoopbackMidiTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2LoopbackMidiTransport>::`vftable'
0x1800060f6  mov     [rcx], rax
0x1800060f9  mov     dword ptr [rcx+8], 0C0000001h
0x180006100  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006107  mov     rax, [rcx]
0x18000610a  mov     rax, [rax+10h]
0x18000610e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006113  nop
0x180006114  mov     rcx, [rbx+40h]
0x180006118  test    rcx, rcx
0x18000611b  jz      short loc_18000612A
0x18000611d  mov     rax, [rcx]
0x180006120  mov     rax, [rax+10h]
0x180006124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006129  nop
0x18000612a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000612e  cmp     byte ptr [rcx+28h], 0
0x180006132  jz      short loc_18000613E
0x180006134  mov     byte ptr [rcx+28h], 0
0x180006138  call    cs:__imp_DeleteCriticalSection
0x18000613e  test    dil, 1
0x180006142  jz      short loc_180006151
0x180006144  mov     edx, 48h ; 'H'
0x180006149  mov     rcx, rbx; Block
0x18000614c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006151  mov     rax, rbx
0x180006154  mov     rbx, [rsp+28h+arg_0]
0x180006159  add     rsp, 20h
0x18000615d  pop     rdi
0x18000615e  retn
```

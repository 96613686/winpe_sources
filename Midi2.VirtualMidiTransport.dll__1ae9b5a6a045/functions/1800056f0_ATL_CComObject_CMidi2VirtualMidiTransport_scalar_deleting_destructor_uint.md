# ATL::CComObject<CMidi2VirtualMidiTransport>::`scalar deleting destructor'(uint)

- ea: `0x1800056f0`
- end: `0x180005758`
- name: `??_G?$CComObject@VCMidi2VirtualMidiTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003914`
- `0x1800056f0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005731`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005731`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2VirtualMidiTransport>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2VirtualMidiTransport>::`vftable';
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
0x1800056f0  mov     [rsp+arg_0], rbx
0x1800056f5  push    rdi
0x1800056f6  sub     rsp, 20h
0x1800056fa  mov     dword ptr [rcx+8], 0C0000001h
0x180005701  lea     rax, ??_7?$CComObject@VCMidi2VirtualMidiTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2VirtualMidiTransport>::`vftable'
0x180005708  mov     [rcx], rax
0x18000570b  mov     rbx, rcx
0x18000570e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005715  mov     edi, edx
0x180005717  mov     rax, [rcx]
0x18000571a  mov     rax, [rax+10h]
0x18000571e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005723  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005727  cmp     byte ptr [rcx+28h], 0
0x18000572b  jz      short loc_180005737
0x18000572d  mov     byte ptr [rcx+28h], 0
0x180005731  call    cs:__imp_DeleteCriticalSection
0x180005737  test    dil, 1
0x18000573b  jz      short loc_18000574A
0x18000573d  mov     edx, 40h ; '@'
0x180005742  mov     rcx, rbx; Block
0x180005745  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000574a  mov     rax, rbx
0x18000574d  mov     rbx, [rsp+28h+arg_0]
0x180005752  add     rsp, 20h
0x180005756  pop     rdi
0x180005757  retn
```

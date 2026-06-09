# ATL::CComObject<CMidi2MidiSrvTransport>::`vector deleting destructor'(uint)

- ea: `0x180003f00`
- end: `0x180003f68`
- name: `??_E?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002494`
- `0x180003f00`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f41`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f41`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2MidiSrvTransport>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2MidiSrvTransport>::`vftable';
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
0x180003f00  mov     [rsp+arg_0], rbx
0x180003f05  push    rdi
0x180003f06  sub     rsp, 20h
0x180003f0a  mov     dword ptr [rcx+8], 0C0000001h
0x180003f11  lea     rax, ??_7?$CComObject@VCMidi2MidiSrvTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2MidiSrvTransport>::`vftable'
0x180003f18  mov     [rcx], rax
0x180003f1b  mov     rbx, rcx
0x180003f1e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003f25  mov     edi, edx
0x180003f27  mov     rax, [rcx]
0x180003f2a  mov     rax, [rax+10h]
0x180003f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f33  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003f37  cmp     byte ptr [rcx+28h], 0
0x180003f3b  jz      short loc_180003F47
0x180003f3d  mov     byte ptr [rcx+28h], 0
0x180003f41  call    cs:__imp_DeleteCriticalSection
0x180003f47  test    dil, 1
0x180003f4b  jz      short loc_180003F5A
0x180003f4d  mov     edx, 40h ; '@'
0x180003f52  mov     rcx, rbx; Block
0x180003f55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003f5a  mov     rax, rbx
0x180003f5d  mov     rbx, [rsp+28h+arg_0]
0x180003f62  add     rsp, 20h
0x180003f66  pop     rdi
0x180003f67  retn
```

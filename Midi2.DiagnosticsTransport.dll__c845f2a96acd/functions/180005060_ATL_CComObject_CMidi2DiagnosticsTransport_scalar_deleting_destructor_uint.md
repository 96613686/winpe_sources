# ATL::CComObject<CMidi2DiagnosticsTransport>::`scalar deleting destructor'(uint)

- ea: `0x180005060`
- end: `0x1800050c8`
- name: `??_G?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800033f4`
- `0x180005060`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800050a1`

## pseudocode

```c
char *__fastcall ATL::CComObject<CMidi2DiagnosticsTransport>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CMidi2DiagnosticsTransport>::`vftable';
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
0x180005060  mov     [rsp+arg_0], rbx
0x180005065  push    rdi
0x180005066  sub     rsp, 20h
0x18000506a  mov     dword ptr [rcx+8], 0C0000001h
0x180005071  lea     rax, ??_7?$CComObject@VCMidi2DiagnosticsTransport@@@ATL@@6B@; const ATL::CComObject<CMidi2DiagnosticsTransport>::`vftable'
0x180005078  mov     [rcx], rax
0x18000507b  mov     rbx, rcx
0x18000507e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005085  mov     edi, edx
0x180005087  mov     rax, [rcx]
0x18000508a  mov     rax, [rax+10h]
0x18000508e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005093  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005097  cmp     byte ptr [rcx+28h], 0
0x18000509b  jz      short loc_1800050A7
0x18000509d  mov     byte ptr [rcx+28h], 0
0x1800050a1  call    cs:__imp_DeleteCriticalSection
0x1800050a7  test    dil, 1
0x1800050ab  jz      short loc_1800050BA
0x1800050ad  mov     edx, 40h ; '@'
0x1800050b2  mov     rcx, rbx; Block
0x1800050b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800050ba  mov     rax, rbx
0x1800050bd  mov     rbx, [rsp+28h+arg_0]
0x1800050c2  add     rsp, 20h
0x1800050c6  pop     rdi
0x1800050c7  retn
```

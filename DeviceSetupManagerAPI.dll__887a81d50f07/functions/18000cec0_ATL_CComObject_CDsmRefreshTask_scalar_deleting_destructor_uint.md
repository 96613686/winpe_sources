# ATL::CComObject<CDsmRefreshTask>::`scalar deleting destructor'(uint)

- ea: `0x18000cec0`
- end: `0x18000cf28`
- name: `??_G?$CComObject@VCDsmRefreshTask@@@ATL@@UEAAPEAXI@Z`
- size: `104`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001c6c`
- `0x18000cec0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf01`

## pseudocode

```c
char *__fastcall ATL::CComObject<CDsmRefreshTask>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 2) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CDsmRefreshTask>::`vftable';
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
0x18000cec0  mov     [rsp+arg_0], rbx
0x18000cec5  push    rdi
0x18000cec6  sub     rsp, 20h
0x18000ceca  mov     dword ptr [rcx+8], 0C0000001h
0x18000ced1  lea     rax, ??_7?$CComObject@VCDsmRefreshTask@@@ATL@@6B@; const ATL::CComObject<CDsmRefreshTask>::`vftable'
0x18000ced8  mov     [rcx], rax
0x18000cedb  mov     rbx, rcx
0x18000cede  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cee5  mov     edi, edx
0x18000cee7  mov     rax, [rcx]
0x18000ceea  mov     rax, [rax+10h]
0x18000ceee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cef3  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000cef7  cmp     byte ptr [rcx+28h], 0
0x18000cefb  jz      short loc_18000CF07
0x18000cefd  mov     byte ptr [rcx+28h], 0
0x18000cf01  call    cs:__imp_DeleteCriticalSection
0x18000cf07  test    dil, 1
0x18000cf0b  jz      short loc_18000CF1A
0x18000cf0d  mov     edx, 40h ; '@'
0x18000cf12  mov     rcx, rbx; Block
0x18000cf15  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf1a  mov     rax, rbx
0x18000cf1d  mov     rbx, [rsp+28h+arg_0]
0x18000cf22  add     rsp, 20h
0x18000cf26  pop     rdi
0x18000cf27  retn
```

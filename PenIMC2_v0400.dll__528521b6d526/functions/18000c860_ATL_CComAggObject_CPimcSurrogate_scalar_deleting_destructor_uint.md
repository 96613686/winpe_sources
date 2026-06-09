# ATL::CComAggObject<CPimcSurrogate>::`scalar deleting destructor'(uint)

- ea: `0x18000c860`
- end: `0x18000c8b4`
- name: `??_G?$CComAggObject@VCPimcSurrogate@@@ATL@@UEAAPEAXI@Z`
- size: `84`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c860`
- `0x18000ce0c`
- `0x18000e4a0`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CPimcSurrogate>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  *(_QWORD *)Block = &ATL::CComAggObject<CPimcSurrogate>::`vftable';
  Block[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000c860  mov     [rsp+arg_0], rbx
0x18000c865  push    rdi
0x18000c866  sub     rsp, 20h
0x18000c86a  mov     ebx, edx
0x18000c86c  mov     rdi, rcx
0x18000c86f  lea     rax, ??_7?$CComAggObject@VCPimcSurrogate@@@ATL@@6B@; const ATL::CComAggObject<CPimcSurrogate>::`vftable'
0x18000c876  mov     [rcx], rax
0x18000c879  mov     dword ptr [rcx+8], 0C0000001h
0x18000c880  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c887  mov     rax, [rcx]
0x18000c88a  mov     rax, [rax+10h]
0x18000c88e  call    cs:__guard_dispatch_icall_fptr
0x18000c894  test    bl, 1
0x18000c897  jz      short loc_18000C8A6
0x18000c899  mov     edx, 20h ; ' '
0x18000c89e  mov     rcx, rdi; Block
0x18000c8a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c8a6  mov     rax, rdi
0x18000c8a9  mov     rbx, [rsp+28h+arg_0]
0x18000c8ae  add     rsp, 20h
0x18000c8b2  pop     rdi
0x18000c8b3  retn
```

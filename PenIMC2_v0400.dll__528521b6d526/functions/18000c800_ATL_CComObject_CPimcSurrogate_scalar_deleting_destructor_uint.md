# ATL::CComObject<CPimcSurrogate>::`scalar deleting destructor'(uint)

- ea: `0x18000c800`
- end: `0x18000c854`
- name: `??_G?$CComObject@VCPimcSurrogate@@@ATL@@UEAAPEAXI@Z`
- size: `84`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c800`
- `0x18000ce0c`
- `0x18000e4a0`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CPimcSurrogate>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  *(_QWORD *)Block = &ATL::CComObject<CPimcSurrogate>::`vftable';
  Block[2] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000c800  mov     [rsp+arg_0], rbx
0x18000c805  push    rdi
0x18000c806  sub     rsp, 20h
0x18000c80a  mov     ebx, edx
0x18000c80c  mov     rdi, rcx
0x18000c80f  lea     rax, ??_7?$CComObject@VCPimcSurrogate@@@ATL@@6B@; const ATL::CComObject<CPimcSurrogate>::`vftable'
0x18000c816  mov     [rcx], rax
0x18000c819  mov     dword ptr [rcx+8], 0C0000001h
0x18000c820  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c827  mov     rax, [rcx]
0x18000c82a  mov     rax, [rax+10h]
0x18000c82e  call    cs:__guard_dispatch_icall_fptr
0x18000c834  test    bl, 1
0x18000c837  jz      short loc_18000C846
0x18000c839  mov     edx, 10h
0x18000c83e  mov     rcx, rdi; Block
0x18000c841  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c846  mov     rax, rdi
0x18000c849  mov     rbx, [rsp+28h+arg_0]
0x18000c84e  add     rsp, 20h
0x18000c852  pop     rdi
0x18000c853  retn
```

# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18000b5f0`
- end: `0x18000b671`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x18000b5f0`
- `0x18002a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
  Block[6] = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)Block + 1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp+arg_0], rbx
0x18000b5f5  push    rdi
0x18000b5f6  sub     rsp, 20h
0x18000b5fa  mov     edi, edx
0x18000b5fc  mov     rbx, rcx
0x18000b5ff  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000b606  mov     [rcx], rax
0x18000b609  mov     dword ptr [rcx+18h], 0C0000001h
0x18000b610  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b617  mov     rax, [rcx]
0x18000b61a  mov     rax, [rax+10h]
0x18000b61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b623  nop
0x18000b624  mov     rcx, [rbx+10h]
0x18000b628  test    rcx, rcx
0x18000b62b  jz      short loc_18000B63A
0x18000b62d  mov     rax, [rcx]
0x18000b630  mov     rax, [rax+10h]
0x18000b634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b639  nop
0x18000b63a  mov     rcx, [rbx+8]
0x18000b63e  test    rcx, rcx
0x18000b641  jz      short loc_18000B650
0x18000b643  mov     rax, [rcx]
0x18000b646  mov     rax, [rax+10h]
0x18000b64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b64f  nop
0x18000b650  test    dil, 1
0x18000b654  jz      short loc_18000B663
0x18000b656  mov     edx, 20h ; ' '
0x18000b65b  mov     rcx, rbx; Block
0x18000b65e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b663  mov     rax, rbx
0x18000b666  mov     rbx, [rsp+28h+arg_0]
0x18000b66b  add     rsp, 20h
0x18000b66f  pop     rdi
0x18000b670  retn
```

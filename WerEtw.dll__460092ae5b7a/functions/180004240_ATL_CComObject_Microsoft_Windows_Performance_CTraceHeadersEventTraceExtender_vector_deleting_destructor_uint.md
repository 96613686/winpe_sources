# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180004240`
- end: `0x1800042c1`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `129`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x180004240`
- `0x18002a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)Block = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x180004240  mov     [rsp+arg_0], rbx
0x180004245  push    rdi
0x180004246  sub     rsp, 20h
0x18000424a  mov     edi, edx
0x18000424c  mov     rbx, rcx
0x18000424f  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180004256  mov     [rcx], rax
0x180004259  mov     dword ptr [rcx+18h], 0C0000001h
0x180004260  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004267  mov     rax, [rcx]
0x18000426a  mov     rax, [rax+10h]
0x18000426e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004273  nop
0x180004274  mov     rcx, [rbx+10h]
0x180004278  test    rcx, rcx
0x18000427b  jz      short loc_18000428A
0x18000427d  mov     rax, [rcx]
0x180004280  mov     rax, [rax+10h]
0x180004284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004289  nop
0x18000428a  mov     rcx, [rbx+8]
0x18000428e  test    rcx, rcx
0x180004291  jz      short loc_1800042A0
0x180004293  mov     rax, [rcx]
0x180004296  mov     rax, [rax+10h]
0x18000429a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000429f  nop
0x1800042a0  test    dil, 1
0x1800042a4  jz      short loc_1800042B3
0x1800042a6  mov     edx, 20h ; ' '
0x1800042ab  mov     rcx, rbx; Block
0x1800042ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800042b3  mov     rax, rbx
0x1800042b6  mov     rbx, [rsp+28h+arg_0]
0x1800042bb  add     rsp, 20h
0x1800042bf  pop     rdi
0x1800042c0  retn
```

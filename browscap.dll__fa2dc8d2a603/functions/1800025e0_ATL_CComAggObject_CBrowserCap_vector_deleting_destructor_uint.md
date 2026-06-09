# ATL::CComAggObject<CBrowserCap>::`vector deleting destructor'(uint)

- ea: `0x1800025e0`
- end: `0x180002657`
- name: `??_E?$CComAggObject@VCBrowserCap@@@ATL@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800025e0`
- `0x180007454`
- `0x18000d010`

## import_xrefs

- `msvcrt!free` at `0x180002643`
- `msvcrt!free` at `0x180002643`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall ATL::CComAggObject<CBrowserCap>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)Block = &ATL::CComAggObject<CBrowserCap>::`vftable';
  Block[2] = -1073741823;
  v4 = *((_QWORD *)Block + 12);
  if ( v4 )
  {
    *((_QWORD *)Block + 12) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CBrowserCap::~CBrowserCap((CBrowserCap *)(Block + 6));
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x1800025e0  mov     [rsp+arg_0], rbx
0x1800025e5  push    rdi
0x1800025e6  sub     rsp, 20h
0x1800025ea  mov     edi, edx
0x1800025ec  mov     rbx, rcx
0x1800025ef  lea     rax, ??_7?$CComAggObject@VCBrowserCap@@@ATL@@6B@; const ATL::CComAggObject<CBrowserCap>::`vftable'
0x1800025f6  mov     [rcx], rax
0x1800025f9  mov     dword ptr [rcx+8], 0C0000001h
0x180002600  mov     rcx, [rcx+60h]
0x180002604  test    rcx, rcx
0x180002607  jz      short loc_18000261E
0x180002609  mov     qword ptr [rbx+60h], 0
0x180002611  mov     rax, [rcx]
0x180002614  mov     rax, [rax+10h]
0x180002618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000261d  nop
0x18000261e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002625  mov     rax, [rcx]
0x180002628  mov     rax, [rax+10h]
0x18000262c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002631  lea     rcx, [rbx+18h]; this
0x180002635  call    ??1CBrowserCap@@QEAA@XZ; CBrowserCap::~CBrowserCap(void)
0x18000263a  test    dil, 1
0x18000263e  jz      short loc_180002649
0x180002640  mov     rcx, rbx; Block
0x180002643  call    cs:__imp_free
0x180002649  mov     rax, rbx
0x18000264c  mov     rbx, [rsp+28h+arg_0]
0x180002651  add     rsp, 20h
0x180002655  pop     rdi
0x180002656  retn
```

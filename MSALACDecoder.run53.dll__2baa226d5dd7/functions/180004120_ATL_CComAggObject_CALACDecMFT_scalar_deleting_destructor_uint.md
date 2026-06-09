# ATL::CComAggObject<CALACDecMFT>::`scalar deleting destructor'(uint)

- ea: `0x180004120`
- end: `0x18000417c`
- name: `??_G?$CComAggObject@VCALACDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001574`
- `0x180001f78`
- `0x180004120`
- `0x18000b010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CALACDecMFT>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CALACDecMFT>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CALACDecMFT::~CALACDecMFT((CALACDecMFT *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004120  mov     [rsp+arg_0], rbx
0x180004125  push    rdi
0x180004126  sub     rsp, 20h
0x18000412a  mov     dword ptr [rcx+8], 0C0000001h
0x180004131  lea     rax, ??_7?$CComAggObject@VCALACDecMFT@@@ATL@@6B@; const ATL::CComAggObject<CALACDecMFT>::`vftable'
0x180004138  mov     [rcx], rax
0x18000413b  mov     rdi, rcx
0x18000413e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004145  mov     ebx, edx
0x180004147  mov     rax, [rcx]
0x18000414a  mov     rax, [rax+10h]
0x18000414e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004153  lea     rcx, [rdi+18h]; this
0x180004157  call    ??1CALACDecMFT@@UEAA@XZ; CALACDecMFT::~CALACDecMFT(void)
0x18000415c  test    bl, 1
0x18000415f  jz      short loc_18000416E
0x180004161  mov     edx, 0F0h
0x180004166  mov     rcx, rdi; Block
0x180004169  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000416e  mov     rbx, [rsp+28h+arg_0]
0x180004173  mov     rax, rdi
0x180004176  add     rsp, 20h
0x18000417a  pop     rdi
0x18000417b  retn
```

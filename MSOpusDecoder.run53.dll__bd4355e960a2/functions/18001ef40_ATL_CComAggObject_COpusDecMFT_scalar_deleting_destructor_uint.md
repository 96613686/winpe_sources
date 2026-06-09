# ATL::CComAggObject<COpusDecMFT>::`scalar deleting destructor'(uint)

- ea: `0x18001ef40`
- end: `0x18001ef9c`
- name: `??_G?$CComAggObject@VCOpusDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `92`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`
- `0x18001b45c`
- `0x18001ef40`
- `0x180024010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<COpusDecMFT>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<COpusDecMFT>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  COpusDecMFT::~COpusDecMFT((COpusDecMFT *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18001ef40  mov     [rsp+arg_0], rbx
0x18001ef45  push    rdi
0x18001ef46  sub     rsp, 20h
0x18001ef4a  mov     dword ptr [rcx+8], 0C0000001h
0x18001ef51  lea     rax, ??_7?$CComAggObject@VCOpusDecMFT@@@ATL@@6B@; const ATL::CComAggObject<COpusDecMFT>::`vftable'
0x18001ef58  mov     [rcx], rax
0x18001ef5b  mov     rdi, rcx
0x18001ef5e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ef65  mov     ebx, edx
0x18001ef67  mov     rax, [rcx]
0x18001ef6a  mov     rax, [rax+10h]
0x18001ef6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef73  lea     rcx, [rdi+18h]; this
0x18001ef77  call    ??1COpusDecMFT@@UEAA@XZ; COpusDecMFT::~COpusDecMFT(void)
0x18001ef7c  test    bl, 1
0x18001ef7f  jz      short loc_18001EF8E
0x18001ef81  mov     edx, 158h
0x18001ef86  mov     rcx, rdi; Block
0x18001ef89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ef8e  mov     rbx, [rsp+28h+arg_0]
0x18001ef93  mov     rax, rdi
0x18001ef96  add     rsp, 20h
0x18001ef9a  pop     rdi
0x18001ef9b  retn
```

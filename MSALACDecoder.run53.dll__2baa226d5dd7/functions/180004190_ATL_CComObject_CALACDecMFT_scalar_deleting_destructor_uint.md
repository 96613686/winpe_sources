# ATL::CComObject<CALACDecMFT>::`scalar deleting destructor'(uint)

- ea: `0x180004190`
- end: `0x1800041ee`
- name: `??_G?$CComObject@VCALACDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(CALACDecMFT *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001574`
- `0x180001f78`
- `0x180004190`
- `0x18000b010`

## pseudocode

```c
CALACDecMFT *__fastcall ATL::CComObject<CALACDecMFT>::`scalar deleting destructor'(CALACDecMFT *this, char a2)
{
  *((_DWORD *)this + 38) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CALACDecMFT>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CALACDecMFT::~CALACDecMFT(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004190  mov     [rsp+arg_0], rbx
0x180004195  push    rdi
0x180004196  sub     rsp, 20h
0x18000419a  mov     dword ptr [rcx+98h], 0C0000001h
0x1800041a4  lea     rax, ??_7?$CComObject@VCALACDecMFT@@@ATL@@6B@; const ATL::CComObject<CALACDecMFT>::`vftable'
0x1800041ab  mov     [rcx], rax
0x1800041ae  mov     rdi, rcx
0x1800041b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800041b8  mov     ebx, edx
0x1800041ba  mov     rax, [rcx]
0x1800041bd  mov     rax, [rax+10h]
0x1800041c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c6  mov     rcx, rdi; this
0x1800041c9  call    ??1CALACDecMFT@@UEAA@XZ; CALACDecMFT::~CALACDecMFT(void)
0x1800041ce  test    bl, 1
0x1800041d1  jz      short loc_1800041E0
0x1800041d3  mov     edx, 0D8h
0x1800041d8  mov     rcx, rdi; Block
0x1800041db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800041e0  mov     rbx, [rsp+28h+arg_0]
0x1800041e5  mov     rax, rdi
0x1800041e8  add     rsp, 20h
0x1800041ec  pop     rdi
0x1800041ed  retn
```

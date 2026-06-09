# ATL::CComObject<COpusDecMFT>::`scalar deleting destructor'(uint)

- ea: `0x18001efb0`
- end: `0x18001f01c`
- name: `??_G?$CComObject@VCOpusDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `108`
- prototype: `__int64 __fastcall(COpusDecMFT *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`
- `0x18001b45c`
- `0x18001efb0`
- `0x180024010`

## pseudocode

```c
COpusDecMFT *__fastcall ATL::CComObject<COpusDecMFT>::`scalar deleting destructor'(COpusDecMFT *this, char a2)
{
  *((_DWORD *)this + 40) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'};
  *((_QWORD *)this + 19) = &ATL::CComObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'};
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  COpusDecMFT::~COpusDecMFT(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001efb0  mov     [rsp+arg_0], rbx
0x18001efb5  push    rdi
0x18001efb6  sub     rsp, 20h
0x18001efba  mov     dword ptr [rcx+0A0h], 0C0000001h
0x18001efc4  lea     rax, ??_7?$CComObject@VCOpusDecMFT@@@ATL@@6BCMFTSimpleBase@@@; const ATL::CComObject<COpusDecMFT>::`vftable'{for `CMFTSimpleBase'}
0x18001efcb  mov     [rcx], rax
0x18001efce  mov     rdi, rcx
0x18001efd1  lea     rax, ??_7?$CComObject@VCOpusDecMFT@@@ATL@@6BIMFTelemetryComponent@@@; const ATL::CComObject<COpusDecMFT>::`vftable'{for `IMFTelemetryComponent'}
0x18001efd8  mov     ebx, edx
0x18001efda  mov     [rcx+98h], rax
0x18001efe1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001efe8  mov     rax, [rcx]
0x18001efeb  mov     rax, [rax+10h]
0x18001efef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eff4  mov     rcx, rdi; this
0x18001eff7  call    ??1COpusDecMFT@@UEAA@XZ; COpusDecMFT::~COpusDecMFT(void)
0x18001effc  test    bl, 1
0x18001efff  jz      short loc_18001F00E
0x18001f001  mov     edx, 140h
0x18001f006  mov     rcx, rdi; Block
0x18001f009  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f00e  mov     rbx, [rsp+28h+arg_0]
0x18001f013  mov     rax, rdi
0x18001f016  add     rsp, 20h
0x18001f01a  pop     rdi
0x18001f01b  retn
```

# ATL::CComObject<CWfHelperClass>::`scalar deleting destructor'(uint)

- ea: `0x180002a80`
- end: `0x180002aed`
- name: `??_G?$CComObject@VCWfHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `CWfHelperClass *__fastcall(CWfHelperClass *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002880`
- `0x180002a80`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002ad9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002ad9`

## pseudocode

```c
CWfHelperClass *__fastcall ATL::CComObject<CWfHelperClass>::`scalar deleting destructor'(CWfHelperClass *this, char a2)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CWfHelperClass>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWfHelperClass::~CWfHelperClass(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002a80  mov     [rsp+arg_0], rbx
0x180002a85  push    rdi
0x180002a86  sub     rsp, 20h
0x180002a8a  mov     dword ptr [rcx+40h], 0C0000001h
0x180002a91  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelper'}
0x180002a98  mov     [rcx], rax
0x180002a9b  mov     rdi, rcx
0x180002a9e  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CWfHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180002aa5  mov     ebx, edx
0x180002aa7  mov     [rcx+8], rax
0x180002aab  lea     rax, ??_7?$CComObject@VCWfHelperClass@@@ATL@@6B@; const ATL::CComObject<CWfHelperClass>::`vftable'
0x180002ab2  mov     [rcx+38h], rax
0x180002ab6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002abd  mov     rax, [rcx]
0x180002ac0  mov     rax, [rax+10h]
0x180002ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac9  mov     rcx, rdi; this
0x180002acc  call    ??1CWfHelperClass@@QEAA@XZ; CWfHelperClass::~CWfHelperClass(void)
0x180002ad1  test    bl, 1
0x180002ad4  jz      short loc_180002ADF
0x180002ad6  mov     rcx, rdi
0x180002ad9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002adf  mov     rbx, [rsp+28h+arg_0]
0x180002ae4  mov     rax, rdi
0x180002ae7  add     rsp, 20h
0x180002aeb  pop     rdi
0x180002aec  retn
```

# ATL::CComObject<CSMBHelperClass>::`scalar deleting destructor'(uint)

- ea: `0x180003af0`
- end: `0x180003b5d`
- name: `??_G?$CComObject@VCSMBHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `109`
- prototype: `__int64 __fastcall(CSMBHelperClass *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800037e8`
- `0x180003af0`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003b49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003b49`

## pseudocode

```c
CSMBHelperClass *__fastcall ATL::CComObject<CSMBHelperClass>::`scalar deleting destructor'(
        CSMBHelperClass *this,
        char a2)
{
  *((_DWORD *)this + 16) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelper'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelperInfo'};
  *((_QWORD *)this + 7) = &ATL::CComObject<CSMBHelperClass>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CSMBHelperClass::~CSMBHelperClass(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003af0  mov     [rsp+arg_0], rbx
0x180003af5  push    rdi
0x180003af6  sub     rsp, 20h
0x180003afa  mov     dword ptr [rcx+40h], 0C0000001h
0x180003b01  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelper'}
0x180003b08  mov     [rcx], rax
0x180003b0b  mov     rdi, rcx
0x180003b0e  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CSMBHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x180003b15  mov     ebx, edx
0x180003b17  mov     [rcx+8], rax
0x180003b1b  lea     rax, ??_7?$CComObject@VCSMBHelperClass@@@ATL@@6B@; const ATL::CComObject<CSMBHelperClass>::`vftable'
0x180003b22  mov     [rcx+38h], rax
0x180003b26  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003b2d  mov     rax, [rcx]
0x180003b30  mov     rax, [rax+10h]
0x180003b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b39  mov     rcx, rdi; this
0x180003b3c  call    ??1CSMBHelperClass@@QEAA@XZ; CSMBHelperClass::~CSMBHelperClass(void)
0x180003b41  test    bl, 1
0x180003b44  jz      short loc_180003B4F
0x180003b46  mov     rcx, rdi
0x180003b49  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003b4f  mov     rbx, [rsp+28h+arg_0]
0x180003b54  mov     rax, rdi
0x180003b57  add     rsp, 20h
0x180003b5b  pop     rdi
0x180003b5c  retn
```

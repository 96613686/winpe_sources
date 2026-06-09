# ATL::CComObject<CCompatContextMenu>::`scalar deleting destructor'(uint)

- ea: `0x180008d70`
- end: `0x180008de7`
- name: `??_G?$CComObject@VCCompatContextMenu@@@ATL@@UEAAPEAXI@Z`
- size: `119`
- prototype: `__int64 __fastcall(CCompatContextMenu *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001790`
- `0x180008d20`
- `0x180008d70`
- `0x180017010`

## pseudocode

```c
CCompatContextMenu *__fastcall ATL::CComObject<CCompatContextMenu>::`scalar deleting destructor'(
        CCompatContextMenu *this,
        char a2)
{
  *((_DWORD *)this + 8) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `ICompatContextMenu'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IContextMenu'};
  *((_QWORD *)this + 3) = &ATL::CComObject<CCompatContextMenu>::`vftable'{for `IObjectWithSite'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CCompatContextMenu::~CCompatContextMenu((struct _RTL_CRITICAL_SECTION *)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008d70  mov     [rsp+arg_0], rbx
0x180008d75  push    rdi
0x180008d76  sub     rsp, 20h
0x180008d7a  mov     dword ptr [rcx+20h], 0C0000001h
0x180008d81  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BICompatContextMenu@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `ICompatContextMenu'}
0x180008d88  mov     [rcx], rax
0x180008d8b  mov     rdi, rcx
0x180008d8e  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IShellExtInit'}
0x180008d95  mov     ebx, edx
0x180008d97  mov     [rcx+8], rax
0x180008d9b  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIContextMenu@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IContextMenu'}
0x180008da2  mov     [rcx+10h], rax
0x180008da6  lea     rax, ??_7?$CComObject@VCCompatContextMenu@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CCompatContextMenu>::`vftable'{for `IObjectWithSite'}
0x180008dad  mov     [rcx+18h], rax
0x180008db1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008db8  mov     rax, [rcx]
0x180008dbb  mov     rax, [rax+10h]
0x180008dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc4  mov     rcx, rdi; this
0x180008dc7  call    ??1CCompatContextMenu@@QEAA@XZ; CCompatContextMenu::~CCompatContextMenu(void)
0x180008dcc  test    bl, 1
0x180008dcf  jz      short loc_180008DD9
0x180008dd1  mov     rcx, rdi; Block
0x180008dd4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008dd9  mov     rbx, [rsp+28h+arg_0]
0x180008dde  mov     rax, rdi
0x180008de1  add     rsp, 20h
0x180008de5  pop     rdi
0x180008de6  retn
```

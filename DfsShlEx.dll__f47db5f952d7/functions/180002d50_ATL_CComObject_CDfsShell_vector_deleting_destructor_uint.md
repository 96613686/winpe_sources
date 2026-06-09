# ATL::CComObject<CDfsShell>::`vector deleting destructor'(uint)

- ea: `0x180002d50`
- end: `0x180002db2`
- name: `??_E?$CComObject@VCDfsShell@@@ATL@@UEAAPEAXI@Z`
- size: `98`
- prototype: `__int64 __fastcall(CDfsShell *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002b10`
- `0x180002d50`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d9e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d9e`

## pseudocode

```c
CDfsShell *__fastcall ATL::CComObject<CDfsShell>::`vector deleting destructor'(CDfsShell *this, char a2)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CDfsShell>::`vftable'{for `IShellExtInit'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CDfsShell::~CDfsShell(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002d50  mov     [rsp+arg_0], rbx
0x180002d55  push    rdi
0x180002d56  sub     rsp, 20h
0x180002d5a  mov     dword ptr [rcx+10h], 0C0000001h
0x180002d61  lea     rax, ??_7?$CComObject@VCDfsShell@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CDfsShell>::`vftable'{for `IShellExtInit'}
0x180002d68  mov     [rcx], rax
0x180002d6b  mov     rdi, rcx
0x180002d6e  lea     rax, ??_7?$CComObject@VCDfsShell@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'}
0x180002d75  mov     ebx, edx
0x180002d77  mov     [rcx+8], rax
0x180002d7b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d82  mov     rax, [rcx]
0x180002d85  mov     rax, [rax+10h]
0x180002d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d8e  mov     rcx, rdi; this
0x180002d91  call    ??1CDfsShell@@QEAA@XZ; CDfsShell::~CDfsShell(void)
0x180002d96  test    bl, 1
0x180002d99  jz      short loc_180002DA4
0x180002d9b  mov     rcx, rdi
0x180002d9e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002da4  mov     rbx, [rsp+28h+arg_0]
0x180002da9  mov     rax, rdi
0x180002dac  add     rsp, 20h
0x180002db0  pop     rdi
0x180002db1  retn
```

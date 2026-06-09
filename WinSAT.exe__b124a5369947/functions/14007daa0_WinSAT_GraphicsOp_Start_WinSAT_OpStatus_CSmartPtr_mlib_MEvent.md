# WinSAT::GraphicsOp::Start(WinSAT::OpStatus &,CSmartPtr<mlib::MEvent>)

- ea: `0x14007daa0`
- end: `0x14007dbc5`
- name: `?Start@GraphicsOp@WinSAT@@UEAA_NAEAVOpStatus@2@V?$CSmartPtr@VMEvent@mlib@@@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(void *ArgList)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400085b4`
- `0x14000f858`
- `0x140011f58`
- `0x140016588`
- `0x14004fe00`
- `0x14007daa0`
- `0x14011a010`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x14007db2e`
- `KERNEL32!DuplicateHandle` at `0x14007db2e`
- `KERNEL32!GetCurrentProcess` at `0x14007daef`
- `KERNEL32!GetCurrentProcess` at `0x14007db03`
- `KERNEL32!GetCurrentProcess` at `0x14007daef`
- `KERNEL32!GetCurrentProcess` at `0x14007db03`
- `msvcrt!_beginthreadex` at `0x14007db5c`
- `msvcrt!_beginthreadex` at `0x14007db5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinSAT::GraphicsOp::Start(HANDLE *ArgList, __int64 a2, __int64 a3)
{
  char v6; // bp
  HANDLE CurrentProcess; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  uintptr_t v10; // rax
  unsigned __int16 v11; // r9
  const unsigned __int16 *v12; // rax

  v6 = 1;
  if ( (*((unsigned int (__fastcall **)(HANDLE *))*ArgList + 1))(ArgList) == 4 )
  {
    *(_DWORD *)a2 = 4;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a2 + 8);
LABEL_8:
    *(_BYTE *)(a2 + 16) = 0;
    goto LABEL_9;
  }
  (*((void (__fastcall **)(HANDLE *))*ArgList + 9))(ArgList);
  CurrentProcess = GetCurrentProcess();
  v8 = *(void **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(a3);
  v9 = GetCurrentProcess();
  if ( DuplicateHandle(v9, v8, CurrentProcess, ArgList + 9, 0, 0, 2u) )
  {
    v10 = _beginthreadex(0, 0, WinSAT::GraphicsOp::AssessmentThreadProc, ArgList, 0, 0);
    ArgList[8] = (HANDLE)v10;
    if ( v10 )
    {
      *(_DWORD *)a2 = 6;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a2 + 8);
      v6 = 0;
      goto LABEL_8;
    }
    v12 = mlib::MUIStr_((mlib *)"base\\winsat\\d3d\\graphicsop.cpp", (const char *)0x265, 127, v11);
    WinSAT::OpStatus::SetResult(a2, 3, v12, 0);
  }
  else
  {
    v6 = 0;
  }
LABEL_9:
  CSmartPtr<mlib::MEvent>::Release(a3);
  return v6;
}

```

## disassembly

```asm
0x14007daa0  mov     [rsp+arg_10], r8
0x14007daa5  push    rbx
0x14007daa6  push    rbp
0x14007daa7  push    rdi
0x14007daa8  push    r12
0x14007daaa  push    r14
0x14007daac  push    r15
0x14007daae  sub     rsp, 48h
0x14007dab2  mov     r12, r8
0x14007dab5  mov     r14, rdx
0x14007dab8  mov     r15, rcx
0x14007dabb  mov     bpl, 1
0x14007dabe  mov     rax, [rcx]
0x14007dac1  mov     rax, [rax+8]
0x14007dac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007daca  cmp     eax, 4
0x14007dacd  jnz     short loc_14007DAE0
0x14007dacf  mov     [r14], eax
0x14007dad2  lea     rcx, [r14+8]
0x14007dad6  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14007dadb  jmp     loc_14007DBA7
0x14007dae0  mov     rax, [r15]
0x14007dae3  mov     rcx, r15
0x14007dae6  mov     rax, [rax+48h]
0x14007daea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007daef  call    cs:__imp_GetCurrentProcess
0x14007daf5  mov     rdi, rax
0x14007daf8  mov     rcx, r12
0x14007dafb  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14007db00  mov     rbx, [rax]
0x14007db03  call    cs:__imp_GetCurrentProcess
0x14007db09  lea     r9, [r15+48h]; lpTargetHandle
0x14007db0d  mov     [rsp+78h+dwOptions], 2; dwOptions
0x14007db15  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x14007db1d  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x14007db25  mov     r8, rdi; hTargetProcessHandle
0x14007db28  mov     rdx, rbx; hSourceHandle
0x14007db2b  mov     rcx, rax; hSourceProcessHandle
0x14007db2e  call    cs:__imp_DuplicateHandle
0x14007db34  test    eax, eax
0x14007db36  jnz     short loc_14007DB3D
0x14007db38  xor     bpl, bpl
0x14007db3b  jmp     short loc_14007DBAC
0x14007db3d  mov     qword ptr [rsp+78h+bInheritHandle], 0; ThrdAddr
0x14007db46  mov     [rsp+78h+dwDesiredAccess], 0; InitFlag
0x14007db4e  mov     r9, r15; ArgList
0x14007db51  lea     r8, ?AssessmentThreadProc@GraphicsOp@WinSAT@@CAIPEAX@Z; StartAddress
0x14007db58  xor     edx, edx; StackSize
0x14007db5a  xor     ecx, ecx; Security
0x14007db5c  call    cs:__imp__beginthreadex
0x14007db62  mov     [r15+40h], rax
0x14007db66  test    rax, rax
0x14007db69  jnz     short loc_14007DB94
0x14007db6b  mov     edx, 265h; char *
0x14007db70  lea     r8d, [rax+7Fh]; int
0x14007db74  lea     rcx, aBaseWinsatD3dG; "base\\winsat\\d3d\\graphicsop.cpp"
0x14007db7b  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14007db80  mov     r8, rax
0x14007db83  xor     r9d, r9d
0x14007db86  lea     edx, [r9+3]
0x14007db8a  mov     rcx, r14
0x14007db8d  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x14007db92  jmp     short loc_14007DBAC
0x14007db94  mov     dword ptr [r14], 6
0x14007db9b  lea     rcx, [r14+8]
0x14007db9f  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14007dba4  xor     bpl, bpl
0x14007dba7  mov     byte ptr [r14+10h], 0
0x14007dbac  mov     rcx, r12
0x14007dbaf  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x14007dbb4  mov     al, bpl
0x14007dbb7  add     rsp, 48h
0x14007dbbb  pop     r15
0x14007dbbd  pop     r14
0x14007dbbf  pop     r12
0x14007dbc1  pop     rdi
0x14007dbc2  pop     rbp
0x14007dbc3  pop     rbx
0x14007dbc4  retn
```

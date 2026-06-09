# WinSAT::MPOperation::Start(WinSAT::OpStatus &,CSmartPtr<mlib::MEvent>)

- ea: `0x1400120e0`
- end: `0x1400123ad`
- name: `?Start@MPOperation@WinSAT@@UEAA_NAEAVOpStatus@2@V?$CSmartPtr@VMEvent@mlib@@@@@Z`
- size: `717`
- prototype: `__int64 __fastcall(WinSAT::MPOperation *this, struct WinSAT::OpStatus *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140004348`
- `0x14000449c`
- `0x1400085b4`
- `0x14000a5a8`
- `0x14000b6c8`
- `0x14000f858`
- `0x140011f58`
- `0x1400120e0`
- `0x1400123b4`
- `0x140016588`
- `0x140017af0`
- `0x14003ec14`
- `0x1400530a8`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x1400122ae`
- `KERNEL32!GetThreadPriority` at `0x1400122ae`
- `KERNEL32!GetCurrentThread` at `0x1400122a5`
- `KERNEL32!GetCurrentThread` at `0x1400122a5`
- `KERNEL32!GetLastError` at `0x140012231`
- `KERNEL32!GetLastError` at `0x140012231`
- `KERNEL32!DuplicateHandle` at `0x140012179`
- `KERNEL32!DuplicateHandle` at `0x140012179`
- `KERNEL32!GetPriorityClass` at `0x1400121fb`
- `KERNEL32!GetPriorityClass` at `0x1400121fb`
- `KERNEL32!GetCurrentProcess` at `0x140012137`
- `KERNEL32!GetCurrentProcess` at `0x14001214b`
- `KERNEL32!GetCurrentProcess` at `0x1400121f2`
- `KERNEL32!GetCurrentProcess` at `0x140012220`
- `KERNEL32!GetCurrentProcess` at `0x140012137`
- `KERNEL32!GetCurrentProcess` at `0x14001214b`
- `KERNEL32!GetCurrentProcess` at `0x1400121f2`
- `KERNEL32!GetCurrentProcess` at `0x140012220`
- `KERNEL32!SetPriorityClass` at `0x14001222b`
- `KERNEL32!SetPriorityClass` at `0x14001222b`

## string_xrefs

- `0x140012183`: `Internal error - Failed to copy completion handle.`
- `0x140012299`: `Internal error - NumThreads zero in MPOperation initialization`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall WinSAT::MPOperation::Start(WinSAT::MPOperation *this, struct WinSAT::OpStatus *a2, __int64 a3)
{
  __int64 v3; // r12
  struct WinSAT::OpStatus *v4; // r15
  WinSAT::MPOperation *v5; // rsi
  int v6; // eax
  HANDLE CurrentProcess; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  WCHAR *v11; // r8
  bool started; // di
  char v13; // al
  HANDLE v14; // rax
  int v15; // edx
  int v16; // r8d
  DWORD v17; // ebx
  HANDLE v18; // rax
  char *v19; // rcx
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  _QWORD Buffer[64]; // [rsp+60h] [rbp-248h] BYREF
  DWORD LastError; // [rsp+260h] [rbp-48h]
  char v33; // [rsp+264h] [rbp-44h]
  __int64 v34; // [rsp+268h] [rbp-40h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  v6 = (*(__int64 (__fastcall **)(WinSAT::MPOperation *))(*(_QWORD *)this + 8LL))(this);
  if ( v6 != 4 && v6 != 6 )
  {
    CurrentProcess = GetCurrentProcess();
    v8 = *(void **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(v3);
    v9 = GetCurrentProcess();
    if ( !DuplicateHandle(v9, v8, CurrentProcess, (LPHANDLE)v5 + 1049, 0, 0, 2u) )
    {
      v11 = L"Internal error - Failed to copy completion handle.";
LABEL_5:
      started = 1;
LABEL_6:
      WinSAT::OpStatus::SetResult(v4, 5, v11, 0);
      goto LABEL_23;
    }
    if ( *((_BYTE *)v5 + 8336) )
    {
      *((_DWORD *)v5 + 2075) = 1;
    }
    else
    {
      v19 = (char *)v5 + 40;
      if ( *((_BYTE *)v5 + 8337) )
      {
        v20 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(v19);
        v21 = *(_DWORD *)(v20 + 456);
      }
      else
      {
        v22 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(v19);
        v21 = *(_DWORD *)(v22 + 452);
      }
      *((_DWORD *)v5 + 2075) = v21;
      if ( !v21 )
      {
        v11 = L"Internal error - NumThreads zero in MPOperation initialization";
        goto LABEL_5;
      }
    }
    try
    {
      v13 = (*(__int64 (__fastcall **)(WinSAT::MPOperation *, struct WinSAT::OpStatus *))(*(_QWORD *)v5 + 120LL))(
              v5,
              v4);
      started = v13;
    }
    catch ( std::bad_alloc )
    {
      WinSAT::OpStatus::SetResult(a2, 5, 0, 8);
      started = 1;
      v5 = this;
      v4 = a2;
      v3 = a3;
      goto LABEL_23;
    }
    if ( v13 )
      goto LABEL_23;
    if ( *((_BYTE *)v5 + 8297) )
      WinSAT::MPOperation::DumpVerboseConfigurationInfo(v5);
    if ( !*((_BYTE *)v5 + 8376) )
    {
      v14 = GetCurrentProcess();
      *((_DWORD *)v5 + 2100) = GetPriorityClass(v14);
      started = WinSAT::MPOperation::AdjustPriority(v5, v15, v16);
      if ( started )
      {
        v17 = *((_DWORD *)v5 + 2100);
        v18 = GetCurrentProcess();
        SetPriorityClass(v18, v17);
        LastError = GetLastError();
        v33 = 1;
        v34 = 0;
        mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
        v11 = (WCHAR *)Buffer;
        goto LABEL_6;
      }
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      Log_Text_F("base\\winsat\\exe\\WinSATOp.h", 1134, "Adjusted the priority to %d", ThreadPriority);
    }
    started = WinSAT::MPOperation::StartWorkloads(v5, v4);
    if ( !started )
    {
      *((_DWORD *)v5 + 14) = 4;
      WinSAT::OpStatus::SetResult(v4, 4, L"Operation started successfully.", 0);
LABEL_26:
      CSmartPtr<mlib::MEvent>::Release(v3);
      return started;
    }
LABEL_23:
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      *((_QWORD *)v5 + 3) + 240LL,
      (char *)v4 + 8);
    std::endl(v25);
    if ( *((_BYTE *)v4 + 16) )
    {
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)v5 + 3) + 240LL, (char *)v4 + 24);
      std::endl(v26);
    }
    (*(void (__fastcall **)(WinSAT::MPOperation *))(*(_QWORD *)v5 + 72LL))(v5);
    *((_DWORD *)v5 + 14) = 5;
    goto LABEL_26;
  }
  *(_DWORD *)v4 = v6;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)v4 + 8);
  *((_BYTE *)v4 + 16) = 0;
  CSmartPtr<mlib::MEvent>::Release(v3);
  return 1;
}

```

## disassembly

```asm
0x1400120e0  push    rbx
0x1400120e2  push    rsi
0x1400120e3  push    rdi
0x1400120e4  push    r12
0x1400120e6  push    r15
0x1400120e8  sub     rsp, 280h
0x1400120ef  mov     rax, cs:__security_cookie
0x1400120f6  xor     rax, rsp
0x1400120f9  mov     [rsp+2A8h+var_38], rax
0x140012101  mov     r12, r8
0x140012104  mov     r15, rdx
0x140012107  mov     rsi, rcx
0x14001210a  mov     [rsp+2A8h+var_258], rcx
0x14001210f  mov     [rsp+2A8h+var_260], rdx
0x140012114  mov     [rsp+2A8h+var_250], r8
0x140012119  mov     rax, [rcx]
0x14001211c  mov     rax, [rax+8]
0x140012120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012125  cmp     eax, 4
0x140012128  jz      loc_140012373
0x14001212e  cmp     eax, 6
0x140012131  jz      loc_140012373
0x140012137  call    cs:__imp_GetCurrentProcess
0x14001213d  mov     rdi, rax
0x140012140  mov     rcx, r12
0x140012143  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140012148  mov     rbx, [rax]
0x14001214b  call    cs:__imp_GetCurrentProcess
0x140012151  lea     r9, [rsi+20C8h]; lpTargetHandle
0x140012158  mov     [rsp+2A8h+dwOptions], 2; dwOptions
0x140012160  mov     [rsp+2A8h+bInheritHandle], 0; bInheritHandle
0x140012168  mov     [rsp+2A8h+dwDesiredAccess], 0; dwDesiredAccess
0x140012170  mov     r8, rdi; hTargetProcessHandle
0x140012173  mov     rdx, rbx; hSourceHandle
0x140012176  mov     rcx, rax; hSourceProcessHandle
0x140012179  call    cs:__imp_DuplicateHandle
0x14001217f  test    eax, eax
0x140012181  jnz     short loc_1400121A1
0x140012183  lea     r8, aInternalErrorF; "Internal error - Failed to copy complet"...
0x14001218a  mov     dil, 1
0x14001218d  xor     r9d, r9d
0x140012190  lea     edx, [r9+5]
0x140012194  mov     rcx, r15
0x140012197  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x14001219c  jmp     loc_140012314
0x1400121a1  cmp     byte ptr [rsi+2090h], 0
0x1400121a8  jz      loc_140012266
0x1400121ae  mov     dword ptr [rsi+206Ch], 1
0x1400121b8  mov     rax, [rsi]
0x1400121bb  mov     rdx, r15
0x1400121be  mov     rcx, rsi
0x1400121c1  mov     rax, [rax+78h]
0x1400121c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121ca  mov     dil, al
0x1400121cd  test    al, al
0x1400121cf  jnz     loc_140012314
0x1400121d5  cmp     [rsi+2069h], al
0x1400121db  jz      short loc_1400121E5
0x1400121dd  mov     rcx, rsi; this
0x1400121e0  call    ?DumpVerboseConfigurationInfo@MPOperation@WinSAT@@AEBAXXZ; WinSAT::MPOperation::DumpVerboseConfigurationInfo(void)
0x1400121e5  cmp     byte ptr [rsi+20B8h], 0
0x1400121ec  jnz     loc_1400122CF
0x1400121f2  call    cs:__imp_GetCurrentProcess
0x1400121f8  mov     rcx, rax; hProcess
0x1400121fb  call    cs:__imp_GetPriorityClass
0x140012201  mov     [rsi+20D0h], eax
0x140012207  mov     rcx, rsi; this
0x14001220a  call    ?AdjustPriority@MPOperation@WinSAT@@AEAA_NHH@Z; WinSAT::MPOperation::AdjustPriority(int,int)
0x14001220f  mov     dil, al
0x140012212  test    al, al
0x140012214  jz      loc_1400122A5
0x14001221a  mov     ebx, [rsi+20D0h]
0x140012220  call    cs:__imp_GetCurrentProcess
0x140012226  mov     edx, ebx; dwPriorityClass
0x140012228  mov     rcx, rax; hProcess
0x14001222b  call    cs:__imp_SetPriorityClass
0x140012231  call    cs:__imp_GetLastError
0x140012237  mov     [rsp+2A8h+var_48], eax
0x14001223e  mov     [rsp+2A8h+var_44], 1
0x140012246  mov     [rsp+2A8h+var_40], 0
0x140012252  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x140012257  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14001225c  lea     r8, [rsp+2A8h+Buffer]
0x140012261  jmp     loc_14001218D
0x140012266  lea     rcx, [rsi+28h]
0x14001226a  cmp     byte ptr [rsi+2091h], 0
0x140012271  jz      short loc_140012280
0x140012273  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140012278  mov     ecx, [rax+1C8h]
0x14001227e  jmp     short loc_14001228B
0x140012280  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140012285  mov     ecx, [rax+1C4h]
0x14001228b  mov     [rsi+206Ch], ecx
0x140012291  test    ecx, ecx
0x140012293  jnz     loc_1400121B8
0x140012299  lea     r8, aInternalErrorN_1; "Internal error - NumThreads zero in MPO"...
0x1400122a0  jmp     loc_14001218A
0x1400122a5  call    cs:__imp_GetCurrentThread
0x1400122ab  mov     rcx, rax; hThread
0x1400122ae  call    cs:__imp_GetThreadPriority
0x1400122b4  mov     r9d, eax
0x1400122b7  lea     r8, aAdjustedThePri_1; "Adjusted the priority to %d"
0x1400122be  mov     edx, 46Eh
0x1400122c3  lea     rcx, aBaseWinsatExeW_0; "base\\winsat\\exe\\WinSATOp.h"
0x1400122ca  call    Log_Text_F
0x1400122cf  mov     rdx, r15; struct WinSAT::OpStatus *
0x1400122d2  mov     rcx, rsi; this
0x1400122d5  call    ?StartWorkloads@MPOperation@WinSAT@@AEAA_NAEAVOpStatus@2@@Z; WinSAT::MPOperation::StartWorkloads(WinSAT::OpStatus &)
0x1400122da  mov     dil, al
0x1400122dd  test    al, al
0x1400122df  jnz     short loc_140012314
0x1400122e1  mov     dword ptr [rsi+38h], 4
0x1400122e8  xor     r9d, r9d
0x1400122eb  lea     r8, aOperationStart; "Operation started successfully."
0x1400122f2  lea     edx, [r9+4]
0x1400122f6  mov     rcx, r15
0x1400122f9  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x1400122fe  jmp     short loc_140012366
0x140012300  mov     dil, [rsp+2A8h+var_268]
0x140012305  mov     rsi, [rsp+2A8h+var_258]
0x14001230a  mov     r15, [rsp+2A8h+var_260]
0x14001230f  mov     r12, [rsp+2A8h+var_250]
0x140012314  lea     rdx, [r15+8]
0x140012318  mov     rcx, [rsi+18h]
0x14001231c  mov     ebx, 0F0h
0x140012321  add     rcx, rbx
0x140012324  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140012329  mov     rcx, rax
0x14001232c  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140012331  cmp     byte ptr [r15+10h], 0
0x140012336  jz      short loc_140012350
0x140012338  lea     rdx, [r15+18h]
0x14001233c  mov     rcx, [rsi+18h]
0x140012340  add     rcx, rbx
0x140012343  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140012348  mov     rcx, rax
0x14001234b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140012350  mov     rax, [rsi]
0x140012353  mov     rcx, rsi
0x140012356  mov     rax, [rax+48h]
0x14001235a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001235f  mov     dword ptr [rsi+38h], 5
0x140012366  mov     rcx, r12
0x140012369  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x14001236e  mov     al, dil
0x140012371  jmp     short loc_14001238E
0x140012373  mov     [r15], eax
0x140012376  lea     rcx, [r15+8]
0x14001237a  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x14001237f  mov     byte ptr [r15+10h], 0
0x140012384  mov     rcx, r12
0x140012387  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x14001238c  mov     al, 1
0x14001238e  mov     rcx, [rsp+2A8h+var_38]
0x140012396  xor     rcx, rsp; StackCookie
0x140012399  call    __security_check_cookie
0x14001239e  add     rsp, 280h
0x1400123a5  pop     r15
0x1400123a7  pop     r12
0x1400123a9  pop     rdi
0x1400123aa  pop     rsi
0x1400123ab  pop     rbx
0x1400123ac  retn
```

# CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)

- ea: `0x14003f55c`
- end: `0x14003f71d`
- name: `?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z`
- size: `449`
- prototype: `__int64 __fastcall(CLiveDumpSettings *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14003546c`
- `0x1400361e8`
- `0x140039c40`
- `0x14003a0c0`

## callees

- `0x140005468`
- `0x14000c8a0`
- `0x14001211c`
- `0x140013ff0`
- `0x140014104`
- `0x140034d9c`
- `0x14003f174`
- `0x14003f55c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f6fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f6ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003f6fe`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003f66d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003f6b3`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003f66d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14003f6b3`

## string_xrefs

- `0x14003f597`: `Failed to read the dumpfile setting for machine crash`
- `0x14003f6c5`: `DeleteLiveMiniDumps`

## pseudocode

```c
__int64 __fastcall CLiveDumpSettings::LoadSettings(CLiveDumpSettings *this, const wchar_t *a2, const wchar_t *a3)
{
  int inited; // ebx
  __int64 v7; // rbx
  __int64 v8; // r8
  HKEY *v9; // rax
  HKEY *v10; // rax
  wil::details *v12; // [rsp+20h] [rbp-48h]
  bool v13; // [rsp+28h] [rbp-40h]
  HKEY v14[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v14[0] = 0;
  hKey = 0;
  inited = CLiveDumpSettings::InitLiveReportsStoreRoot(this);
  if ( inited >= 0 )
  {
    if ( !a2 )
      a2 = &pwzValue;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 72, a2, v8);
    if ( !a3 )
      a3 = &pwzValue;
    do
      ++v7;
    while ( a3[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 104, a3, v7);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      (char *)this + 40,
      *((_QWORD *)this + 1),
      (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      (char *)this + 40,
      *((_QWORD *)this + 9),
      (__int64)(*((_QWORD *)this + 10) - *((_QWORD *)this + 9)) >> 1);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back((char *)this + 40, 92);
    v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v14);
    if ( !RegOpenKeyW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\CrashControl\\FullLiveKernelReports",
            v9) )
      *(_DWORD *)this = UtilRegGetDWORD(v14[0], 0, L"FullLiveReportsMax", 1u, 0, v13);
    v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\CrashControl\\LiveKernelReports", v10) )
      *((_DWORD *)this + 1) = UtilRegGetDWORD(hKey, 0, L"DeleteLiveMiniDumps", 1u, 0, v13);
    inited = 0;
  }
  else
  {
    LODWORD(v12) = inited;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x156,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpsettings.cpp",
      "CLiveDumpSettings::LoadSettings",
      v12,
      (int)"Failed to read the dumpfile setting for machine crash",
      (const char *)v14[0]);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14[0] )
    RegCloseKey(v14[0]);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14003f55c  mov     rax, rsp
0x14003f55f  mov     [rax+8], rbx
0x14003f563  mov     [rax+10h], rbp
0x14003f567  push    rsi
0x14003f568  push    rdi
0x14003f569  push    r12
0x14003f56b  push    r14
0x14003f56d  push    r15
0x14003f56f  sub     rsp, 40h
0x14003f573  xor     r15d, r15d
0x14003f576  mov     rbp, r8
0x14003f579  mov     [rax-38h], r15
0x14003f57d  mov     rdi, rdx
0x14003f580  mov     [rax+20h], r15
0x14003f584  mov     rsi, rcx
0x14003f587  call    ?InitLiveReportsStoreRoot@CLiveDumpSettings@@AEAAJXZ; CLiveDumpSettings::InitLiveReportsStoreRoot(void)
0x14003f58c  mov     ebx, eax
0x14003f58e  test    eax, eax
0x14003f590  jns     short loc_14003F5C4
0x14003f592  mov     rcx, [rsp+68h]; this
0x14003f597  lea     rax, aFailedToReadTh; "Failed to read the dumpfile setting for"...
0x14003f59e  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003f5a3  lea     r9, aClivedumpsetti; "CLiveDumpSettings::LoadSettings"
0x14003f5aa  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\werfa"...
0x14003f5b1  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x14003f5b5  mov     edx, 156h; void *
0x14003f5ba  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003f5bf  jmp     loc_14003F6E1
0x14003f5c4  test    rdi, rdi
0x14003f5c7  lea     r12, pwzValue
0x14003f5ce  cmovz   rdi, r12
0x14003f5d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003f5d6  mov     r8, rbx
0x14003f5d9  inc     r8
0x14003f5dc  cmp     [rdi+r8*2], r15w
0x14003f5e1  jnz     short loc_14003F5D9
0x14003f5e3  lea     r14, [rsi+48h]
0x14003f5e7  mov     rdx, rdi
0x14003f5ea  mov     rcx, r14
0x14003f5ed  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003f5f2  test    rbp, rbp
0x14003f5f5  cmovz   rbp, r12
0x14003f5f9  inc     rbx
0x14003f5fc  cmp     [rbp+rbx*2+0], r15w
0x14003f602  jnz     short loc_14003F5F9
0x14003f604  lea     rcx, [rsi+68h]
0x14003f608  mov     r8, rbx
0x14003f60b  mov     rdx, rbp
0x14003f60e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003f613  mov     rdx, [rsi+8]
0x14003f617  lea     rbx, [rsi+28h]
0x14003f61b  mov     r8, [rsi+10h]
0x14003f61f  mov     rcx, rbx
0x14003f622  sub     r8, rdx
0x14003f625  sar     r8, 1
0x14003f628  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003f62d  mov     r8, [r14+8]
0x14003f631  mov     rcx, rbx
0x14003f634  sub     r8, [r14]
0x14003f637  mov     rdx, [r14]
0x14003f63a  sar     r8, 1
0x14003f63d  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14003f642  mov     edx, 5Ch ; '\'
0x14003f647  mov     rcx, rbx
0x14003f64a  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x14003f64f  lea     rcx, [rsp+68h+var_38]
0x14003f654  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003f659  mov     rdi, 0FFFFFFFF80000002h
0x14003f660  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cra"...
0x14003f667  mov     rcx, rdi; hKey
0x14003f66a  mov     r8, rax; phkResult
0x14003f66d  call    cs:__imp_RegOpenKeyW
0x14003f673  mov     ebx, 1
0x14003f678  test    eax, eax
0x14003f67a  jnz     short loc_14003F699
0x14003f67c  mov     rcx, [rsp+68h+var_38]; hKey
0x14003f681  lea     r8, aFulllivereport; "FullLiveReportsMax"
0x14003f688  mov     r9d, ebx; unsigned int
0x14003f68b  mov     [rsp+68h+var_48], r15; bool *
0x14003f690  xor     edx, edx; lpSubKey
0x14003f692  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14003f697  mov     [rsi], eax
0x14003f699  lea     rcx, [rsp+68h+hKey]
0x14003f6a1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14003f6a6  mov     r8, rax; phkResult
0x14003f6a9  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Cra"...
0x14003f6b0  mov     rcx, rdi; hKey
0x14003f6b3  call    cs:__imp_RegOpenKeyW
0x14003f6b9  test    eax, eax
0x14003f6bb  jnz     short loc_14003F6DE
0x14003f6bd  mov     rcx, [rsp+68h+hKey]; hKey
0x14003f6c5  lea     r8, aDeletelivemini; "DeleteLiveMiniDumps"
0x14003f6cc  mov     r9d, ebx; unsigned int
0x14003f6cf  mov     [rsp+68h+var_48], r15; bool *
0x14003f6d4  xor     edx, edx; lpSubKey
0x14003f6d6  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14003f6db  mov     [rsi+4], eax
0x14003f6de  mov     ebx, r15d
0x14003f6e1  mov     rcx, [rsp+68h+hKey]; hKey
0x14003f6e9  test    rcx, rcx
0x14003f6ec  jz      short loc_14003F6F4
0x14003f6ee  call    cs:__imp_RegCloseKey
0x14003f6f4  mov     rcx, [rsp+68h+var_38]; hKey
0x14003f6f9  test    rcx, rcx
0x14003f6fc  jz      short loc_14003F704
0x14003f6fe  call    cs:__imp_RegCloseKey
0x14003f704  mov     rbp, [rsp+68h+arg_8]
0x14003f709  mov     eax, ebx
0x14003f70b  mov     rbx, [rsp+68h+arg_0]
0x14003f710  add     rsp, 40h
0x14003f714  pop     r15
0x14003f716  pop     r14
0x14003f718  pop     r12
0x14003f71a  pop     rdi
0x14003f71b  pop     rsi
0x14003f71c  retn
```

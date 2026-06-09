# CLiveDumpSettings::LoadSettings(wchar_t const *,wchar_t const *)

- ea: `0x1400420a4`
- end: `0x14004227e`
- name: `?LoadSettings@CLiveDumpSettings@@QEAAJPEB_W0@Z`
- size: `474`
- prototype: `__int64 __fastcall(CLiveDumpSettings *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140037978`
- `0x140038760`
- `0x14003c2bc`
- `0x14003c780`

## callees

- `0x14000551c`
- `0x14000ca20`
- `0x140012994`
- `0x140014a88`
- `0x140014b9c`
- `0x1400372dc`
- `0x140041cb8`
- `0x1400420a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140042242`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140042258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140042242`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140042258`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400421b5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140042201`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1400421b5`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140042201`

## string_xrefs

- `0x1400420df`: `Failed to read the dumpfile setting for machine crash`
- `0x140042219`: `DeleteLiveMiniDumps`

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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 72, a2);
    if ( !a3 )
      a3 = &pwzValue;
    do
      ++v7;
    while ( a3[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 104, a3);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
      (char *)this + 40,
      *((_QWORD *)this + 1));
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
0x1400420a4  mov     rax, rsp
0x1400420a7  mov     [rax+8], rbx
0x1400420ab  mov     [rax+10h], rbp
0x1400420af  push    rsi
0x1400420b0  push    rdi
0x1400420b1  push    r12
0x1400420b3  push    r14
0x1400420b5  push    r15
0x1400420b7  sub     rsp, 40h
0x1400420bb  xor     r15d, r15d
0x1400420be  mov     rbp, r8
0x1400420c1  mov     [rax-38h], r15
0x1400420c5  mov     rdi, rdx
0x1400420c8  mov     [rax+20h], r15
0x1400420cc  mov     rsi, rcx
0x1400420cf  call    ?InitLiveReportsStoreRoot@CLiveDumpSettings@@AEAAJXZ; CLiveDumpSettings::InitLiveReportsStoreRoot(void)
0x1400420d4  mov     ebx, eax
0x1400420d6  test    eax, eax
0x1400420d8  jns     short loc_14004210C
0x1400420da  mov     rcx, [rsp+68h]; this
0x1400420df  lea     rax, aFailedToReadTh; "Failed to read the dumpfile setting for"...
0x1400420e6  mov     qword ptr [rsp+68h+var_40], rax; int
0x1400420eb  lea     r9, aClivedumpsetti; "CLiveDumpSettings::LoadSettings"
0x1400420f2  lea     r8, aOnecoreWindows_6; "onecore\\windows\\feedback\\core\\werfa"...
0x1400420f9  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x1400420fd  mov     edx, 156h; void *
0x140042102  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140042107  jmp     loc_140042235
0x14004210c  test    rdi, rdi
0x14004210f  lea     r12, pwzValue
0x140042116  cmovz   rdi, r12
0x14004211a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14004211e  mov     r8, rbx
0x140042121  inc     r8
0x140042124  cmp     [rdi+r8*2], r15w
0x140042129  jnz     short loc_140042121
0x14004212b  lea     r14, [rsi+48h]
0x14004212f  mov     rdx, rdi
0x140042132  mov     rcx, r14
0x140042135  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004213a  test    rbp, rbp
0x14004213d  cmovz   rbp, r12
0x140042141  inc     rbx
0x140042144  cmp     [rbp+rbx*2+0], r15w
0x14004214a  jnz     short loc_140042141
0x14004214c  lea     rcx, [rsi+68h]
0x140042150  mov     r8, rbx
0x140042153  mov     rdx, rbp
0x140042156  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14004215b  mov     rdx, [rsi+8]
0x14004215f  lea     rbx, [rsi+28h]
0x140042163  mov     r8, [rsi+10h]
0x140042167  mov     rcx, rbx
0x14004216a  sub     r8, rdx
0x14004216d  sar     r8, 1
0x140042170  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140042175  mov     r8, [r14+8]
0x140042179  mov     rcx, rbx
0x14004217c  sub     r8, [r14]
0x14004217f  mov     rdx, [r14]
0x140042182  sar     r8, 1
0x140042185  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x14004218a  mov     edx, 5Ch ; '\'
0x14004218f  mov     rcx, rbx
0x140042192  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140042197  lea     rcx, [rsp+68h+var_38]
0x14004219c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400421a1  mov     rdi, 0FFFFFFFF80000002h
0x1400421a8  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Cra"...
0x1400421af  mov     rcx, rdi; hKey
0x1400421b2  mov     r8, rax; phkResult
0x1400421b5  call    cs:__imp_RegOpenKeyW
0x1400421bc  nop     dword ptr [rax+rax+00h]
0x1400421c1  mov     ebx, 1
0x1400421c6  test    eax, eax
0x1400421c8  jnz     short loc_1400421E7
0x1400421ca  mov     rcx, [rsp+68h+var_38]; hKey
0x1400421cf  lea     r8, aFulllivereport; "FullLiveReportsMax"
0x1400421d6  mov     r9d, ebx; unsigned int
0x1400421d9  mov     [rsp+68h+var_48], r15; bool *
0x1400421de  xor     edx, edx; lpSubKey
0x1400421e0  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1400421e5  mov     [rsi], eax
0x1400421e7  lea     rcx, [rsp+68h+hKey]
0x1400421ef  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400421f4  mov     r8, rax; phkResult
0x1400421f7  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Control\\Cra"...
0x1400421fe  mov     rcx, rdi; hKey
0x140042201  call    cs:__imp_RegOpenKeyW
0x140042208  nop     dword ptr [rax+rax+00h]
0x14004220d  test    eax, eax
0x14004220f  jnz     short loc_140042232
0x140042211  mov     rcx, [rsp+68h+hKey]; hKey
0x140042219  lea     r8, aDeletelivemini; "DeleteLiveMiniDumps"
0x140042220  mov     r9d, ebx; unsigned int
0x140042223  mov     [rsp+68h+var_48], r15; bool *
0x140042228  xor     edx, edx; lpSubKey
0x14004222a  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14004222f  mov     [rsi+4], eax
0x140042232  mov     ebx, r15d
0x140042235  mov     rcx, [rsp+68h+hKey]; hKey
0x14004223d  test    rcx, rcx
0x140042240  jz      short loc_14004224E
0x140042242  call    cs:__imp_RegCloseKey
0x140042249  nop     dword ptr [rax+rax+00h]
0x14004224e  mov     rcx, [rsp+68h+var_38]; hKey
0x140042253  test    rcx, rcx
0x140042256  jz      short loc_140042264
0x140042258  call    cs:__imp_RegCloseKey
0x14004225f  nop     dword ptr [rax+rax+00h]
0x140042264  mov     rbp, [rsp+68h+arg_8]
0x140042269  mov     eax, ebx
0x14004226b  mov     rbx, [rsp+68h+arg_0]
0x140042270  add     rsp, 40h
0x140042274  pop     r15
0x140042276  pop     r14
0x140042278  pop     r12
0x14004227a  pop     rdi
0x14004227b  pop     rsi
0x14004227c  retn
```

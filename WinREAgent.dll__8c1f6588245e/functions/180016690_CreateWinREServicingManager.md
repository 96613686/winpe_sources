# CreateWinREServicingManager

- ea: `0x180016690`
- end: `0x180016861`
- name: `CreateWinREServicingManager`
- size: `465`
- prototype: `__int64 __fastcall(__int64, WinREAgent::WinREServicingManager **)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800028f0`
- `0x180004af8`
- `0x1800089d0`
- `0x18000d92c`
- `0x1800164f0`
- `0x180016690`
- `0x180017174`
- `0x180019904`
- `0x180037344`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016702`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180016702`
- `KERNEL32!GetLastError` at `0x18001670c`
- `KERNEL32!GetLastError` at `0x18001674e`
- `KERNEL32!GetLastError` at `0x18001670c`
- `KERNEL32!GetLastError` at `0x18001674e`

## string_xrefs

- `0x180016720`: `Failed to get system Windows directory`
- `0x180016734`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x1800167d2`: `base\diagnosis\srt\winreagent\dll\winreagent.cpp`
- `0x18001673b`: `WinREAgent::CreateWinREServicingManager`
- `0x1800167d9`: `WinREAgent::CreateWinREServicingManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateWinREServicingManager(__int64 a1, WinREAgent::WinREServicingManager **a2)
{
  WinREAgent::WinREServicingManager *v4; // rax
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  WinREAgent::WinREServicingManager *v9; // rax
  void **v11; // [rsp+30h] [rbp-D0h] BYREF
  WinREAgent::WinREServicingManager *v12; // [rsp+38h] [rbp-C8h]
  _QWORD v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = (WinREAgent::WinREServicingManager *)operator new(0x48u);
  if ( v4 )
    v4 = (WinREAgent::WinREServicingManager *)WinREAgent::WinREServicingManager::WinREServicingManager(v4);
  v12 = v4;
  v11 = &RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable';
  memset_0(Buffer, 0, 0x20Au);
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v13);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      v13,
      L"%c:\\",
      Buffer[0]);
    v8 = ((__int64 (__fastcall *)(void ***))v11[3])(&v11);
    v7 = WinREAgent::WinREServicingManager::Initialize(v8, v13, a1);
    if ( (v7 & 0x80000000) == 0 )
    {
      v9 = v12;
      v12 = 0;
      *a2 = v9;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        v7,
        "WinREAgent::CreateWinREServicingManager",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
        79,
        L"Failed to initialize servicing manager");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v13[0] - 24LL));
    v11 = &RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable';
    RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(&v11);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "WinREAgent::CreateWinREServicingManager",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreagent.cpp",
      72,
      L"Failed to get system Windows directory");
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v11 = &RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable';
    RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(&v11);
  }
  return v7;
}

```

## disassembly

```asm
0x180016690  mov     [rsp-8+arg_10], rbx
0x180016695  push    rbp
0x180016696  push    rsi
0x180016697  push    rdi
0x180016698  lea     rbp, [rsp-170h]
0x1800166a0  sub     rsp, 270h
0x1800166a7  mov     rax, cs:__security_cookie
0x1800166ae  xor     rax, rsp
0x1800166b1  mov     [rbp+180h+var_20], rax
0x1800166b8  mov     rdi, rdx
0x1800166bb  mov     rbx, rcx
0x1800166be  mov     ecx, 48h ; 'H'; Size
0x1800166c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800166c8  test    rax, rax
0x1800166cb  jz      short loc_1800166D5
0x1800166cd  mov     rcx, rax; this
0x1800166d0  call    ??0WinREServicingManager@WinREAgent@@QEAA@XZ; WinREAgent::WinREServicingManager::WinREServicingManager(void)
0x1800166d5  mov     [rsp+280h+var_248], rax
0x1800166da  lea     rsi, ??_7?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@6B@; const RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::`vftable'
0x1800166e1  mov     [rsp+280h+var_250], rsi
0x1800166e6  xor     edx, edx; Val
0x1800166e8  mov     r8d, 20Ah; Size
0x1800166ee  lea     rcx, [rsp+280h+Buffer]; void *
0x1800166f3  call    memset_0
0x1800166f8  mov     edx, 104h; uSize
0x1800166fd  lea     rcx, [rsp+280h+Buffer]; lpBuffer
0x180016702  call    cs:__imp_GetSystemWindowsDirectoryW
0x180016708  test    eax, eax
0x18001670a  jnz     short loc_180016774
0x18001670c  call    cs:__imp_GetLastError
0x180016712  mov     edi, 80070000h
0x180016717  test    eax, eax
0x180016719  jle     short loc_180016720
0x18001671b  movzx   eax, ax
0x18001671e  or      eax, edi
0x180016720  lea     rcx, aFailedToGetSys_0; "Failed to get system Windows directory"
0x180016727  mov     [rsp+280h+var_258], rcx
0x18001672c  mov     [rsp+280h+var_260], 48h ; 'H'
0x180016734  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001673b  lea     r8, aWinreagentCrea_0; "WinREAgent::CreateWinREServicingManager"
0x180016742  mov     edx, eax
0x180016744  mov     ecx, 2
0x180016749  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001674e  call    cs:__imp_GetLastError
0x180016754  mov     ebx, eax
0x180016756  test    eax, eax
0x180016758  jle     short loc_18001675F
0x18001675a  movzx   ebx, ax
0x18001675d  or      ebx, edi
0x18001675f  mov     [rsp+280h+var_250], rsi
0x180016764  lea     rcx, [rsp+280h+var_250]
0x180016769  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x18001676e  nop
0x18001676f  jmp     loc_18001683D
0x180016774  lea     rcx, [rsp+280h+var_240]
0x180016779  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001677e  movzx   r8d, [rsp+280h+Buffer]
0x180016784  lea     rdx, aC; "%c:\\"
0x18001678b  lea     rcx, [rsp+280h+var_240]
0x180016790  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180016795  mov     rax, [rsp+280h+var_250]
0x18001679a  lea     rcx, [rsp+280h+var_250]
0x18001679f  mov     rax, [rax+18h]
0x1800167a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a8  mov     r8, rbx
0x1800167ab  lea     rdx, [rsp+280h+var_240]
0x1800167b0  mov     rcx, rax
0x1800167b3  call    ?Initialize@WinREServicingManager@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBD@Z; WinREAgent::WinREServicingManager::Initialize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,char const *)
0x1800167b8  mov     ebx, eax
0x1800167ba  test    eax, eax
0x1800167bc  jns     short loc_18001680D
0x1800167be  lea     rax, aFailedToInitia_10; "Failed to initialize servicing manager"
0x1800167c5  mov     [rsp+280h+var_258], rax
0x1800167ca  mov     [rsp+280h+var_260], 4Fh ; 'O'
0x1800167d2  lea     r9, aBaseDiagnosisS_24; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800167d9  lea     r8, aWinreagentCrea_0; "WinREAgent::CreateWinREServicingManager"
0x1800167e0  mov     edx, ebx
0x1800167e2  mov     ecx, 2
0x1800167e7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800167ec  mov     rcx, [rsp+280h+var_240]
0x1800167f1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800167f5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800167fa  nop
0x1800167fb  mov     [rsp+280h+var_250], rsi
0x180016800  lea     rcx, [rsp+280h+var_250]
0x180016805  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x18001680a  nop
0x18001680b  jmp     short loc_18001683D
0x18001680d  mov     rax, [rsp+280h+var_248]
0x180016812  mov     [rsp+280h+var_248], 0
0x18001681b  mov     [rdi], rax
0x18001681e  mov     rcx, [rsp+280h+var_240]
0x180016823  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180016827  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001682c  nop
0x18001682d  mov     [rsp+280h+var_250], rsi
0x180016832  lea     rcx, [rsp+280h+var_250]
0x180016837  call    ?Release@?$CAutoRelease@PEAVWinREServicingManager@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoRelease<WinREAgent::WinREServicingManager *>::Release(void)
0x18001683c  nop
0x18001683d  mov     eax, ebx
0x18001683f  mov     rcx, [rbp+180h+var_20]
0x180016846  xor     rcx, rsp; StackCookie
0x180016849  call    __security_check_cookie
0x18001684e  mov     rbx, [rsp+280h+arg_10]
0x180016856  add     rsp, 270h
0x18001685d  pop     rdi
0x18001685e  pop     rsi
0x18001685f  pop     rbp
0x180016860  retn
```

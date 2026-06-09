# WinREAgent::WinREGetOSPartition(PushButtonReset::Partition * *)

- ea: `0x18003308c`
- end: `0x180033232`
- name: `?WinREGetOSPartition@WinREAgent@@YAJPEAPEAVPartition@PushButtonReset@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(WinREAgent *__hidden this, struct PushButtonReset::Partition **)`
- caller_count: `4`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180026ddc`
- `0x180033238`
- `0x180033394`
- `0x180033658`

## callees

- `0x1800049a4`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18003308c`
- `0x180037344`
- `0x18003bbf4`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180033118`
- `KERNEL32!GetLastError` at `0x18003315a`
- `KERNEL32!GetLastError` at `0x180033118`
- `KERNEL32!GetLastError` at `0x18003315a`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003310e`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003310e`

## string_xrefs

- `0x18003312c`: `Failed to get host system Windows directory`
- `0x1800330cd`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180033140`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x1800331d9`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x1800330d4`: `WinREAgent::WinREGetOSPartition`
- `0x180033147`: `WinREAgent::WinREGetOSPartition`
- `0x1800331e0`: `WinREAgent::WinREGetOSPartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall WinREAgent::WinREGetOSPartition(WinREAgent *this, struct PushButtonReset::Partition **a2)
{
  signed int result; // eax
  signed int LastError; // eax
  __int64 v5; // rbx
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // [rsp+30h] [rbp-D0h] BYREF
  void **v9; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-C0h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( this )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      v10 = 0;
      v9 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      v5 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v9);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v8,
        (__int64)Buffer);
      v6 = PushButtonReset::Partition::FindByFilePath(&v8, v5);
      ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
      if ( v6 >= 0 )
      {
        v7 = v10;
        v10 = 0;
        *(_QWORD *)this = v7;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v6,
          "WinREAgent::WinREGetOSPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
          150,
          L"Failed to get partition for OS");
      }
      v9 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v9);
      return v6;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::WinREGetOSPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
        144,
        L"Failed to get host system Windows directory");
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREGetOSPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      136,
      L"res cannot be null");
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18003308c  push    rbp
0x18003308e  push    rbx
0x18003308f  push    rsi
0x180033090  push    rdi
0x180033091  lea     rbp, [rsp-178h]
0x180033099  sub     rsp, 278h
0x1800330a0  mov     rax, cs:__security_cookie
0x1800330a7  xor     rax, rsp
0x1800330aa  mov     [rbp+190h+var_30], rax
0x1800330b1  mov     rdi, rcx
0x1800330b4  test    rcx, rcx
0x1800330b7  jnz     short loc_1800330F2
0x1800330b9  lea     rax, aResCannotBeNul; "res cannot be null"
0x1800330c0  mov     [rsp+290h+var_268], rax
0x1800330c5  mov     [rsp+290h+var_270], 88h
0x1800330cd  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800330d4  lea     r8, aWinreagentWinr_0; "WinREAgent::WinREGetOSPartition"
0x1800330db  mov     edx, 80070057h
0x1800330e0  lea     ecx, [rdi+2]
0x1800330e3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800330e8  mov     eax, 80070057h
0x1800330ed  jmp     loc_180033217
0x1800330f2  xor     edx, edx; Val
0x1800330f4  mov     r8d, 20Ah; Size
0x1800330fa  lea     rcx, [rsp+290h+Buffer]; void *
0x1800330ff  call    memset_0
0x180033104  mov     edx, 104h; uSize
0x180033109  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x18003310e  call    cs:__imp_GetWindowsDirectoryW
0x180033114  test    eax, eax
0x180033116  jnz     short loc_180033172
0x180033118  call    cs:__imp_GetLastError
0x18003311e  mov     ebx, 80070000h
0x180033123  test    eax, eax
0x180033125  jle     short loc_18003312C
0x180033127  movzx   eax, ax
0x18003312a  or      eax, ebx
0x18003312c  lea     rcx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180033133  mov     [rsp+290h+var_268], rcx
0x180033138  mov     [rsp+290h+var_270], 90h
0x180033140  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180033147  lea     r8, aWinreagentWinr_0; "WinREAgent::WinREGetOSPartition"
0x18003314e  mov     edx, eax
0x180033150  mov     ecx, 2
0x180033155  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003315a  call    cs:__imp_GetLastError
0x180033160  test    eax, eax
0x180033162  jle     loc_180033217
0x180033168  movzx   eax, ax
0x18003316b  or      eax, ebx
0x18003316d  jmp     loc_180033217
0x180033172  mov     [rsp+290h+var_250], 0
0x18003317b  lea     rsi, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180033182  mov     [rsp+290h+var_258], rsi
0x180033187  lea     rcx, [rsp+290h+var_258]
0x18003318c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180033191  mov     rbx, rax
0x180033194  lea     rdx, [rsp+290h+Buffer]
0x180033199  lea     rcx, [rsp+290h+var_260]
0x18003319e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800331a3  nop
0x1800331a4  mov     rdx, rbx
0x1800331a7  lea     rcx, [rsp+290h+var_260]
0x1800331ac  call    ?FindByFilePath@Partition@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Partition::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Partition * *)
0x1800331b1  mov     ebx, eax
0x1800331b3  mov     rcx, [rsp+290h+var_260]
0x1800331b8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800331bc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800331c1  test    ebx, ebx
0x1800331c3  jns     short loc_1800331F5
0x1800331c5  lea     rax, aFailedToGetPar_6; "Failed to get partition for OS"
0x1800331cc  mov     [rsp+290h+var_268], rax
0x1800331d1  mov     [rsp+290h+var_270], 96h
0x1800331d9  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800331e0  lea     r8, aWinreagentWinr_0; "WinREAgent::WinREGetOSPartition"
0x1800331e7  mov     edx, ebx
0x1800331e9  mov     ecx, 2
0x1800331ee  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800331f3  jmp     short loc_180033206
0x1800331f5  mov     rax, [rsp+290h+var_250]
0x1800331fa  mov     [rsp+290h+var_250], 0
0x180033203  mov     [rdi], rax
0x180033206  mov     [rsp+290h+var_258], rsi
0x18003320b  lea     rcx, [rsp+290h+var_258]
0x180033210  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180033215  mov     eax, ebx
0x180033217  mov     rcx, [rbp+190h+var_30]
0x18003321e  xor     rcx, rsp; StackCookie
0x180033221  call    __security_check_cookie
0x180033226  add     rsp, 278h
0x18003322d  pop     rdi
0x18003322e  pop     rsi
0x18003322f  pop     rbx
0x180033230  pop     rbp
0x180033231  retn
```

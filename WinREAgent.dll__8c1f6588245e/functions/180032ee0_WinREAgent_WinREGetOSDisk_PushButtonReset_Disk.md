# WinREAgent::WinREGetOSDisk(PushButtonReset::Disk * *)

- ea: `0x180032ee0`
- end: `0x180033086`
- name: `?WinREGetOSDisk@WinREAgent@@YAJPEAPEAVDisk@PushButtonReset@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(WinREAgent *__hidden this, struct PushButtonReset::Disk **)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180026320`
- `0x180027fdc`
- `0x180028220`

## callees

- `0x1800049a4`
- `0x180005cc0`
- `0x18000d92c`
- `0x180026260`
- `0x180032ee0`
- `0x180037344`
- `0x18003ba10`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032f6c`
- `KERNEL32!GetLastError` at `0x180032fae`
- `KERNEL32!GetLastError` at `0x180032f6c`
- `KERNEL32!GetLastError` at `0x180032fae`
- `KERNEL32!GetWindowsDirectoryW` at `0x180032f62`
- `KERNEL32!GetWindowsDirectoryW` at `0x180032f62`

## string_xrefs

- `0x180032f80`: `Failed to get host system Windows directory`
- `0x180032f21`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032f94`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x18003302d`: `base\diagnosis\srt\winreagent\lib\api\src\partition.cpp`
- `0x180032f28`: `WinREAgent::WinREGetOSDisk`
- `0x180032f9b`: `WinREAgent::WinREGetOSDisk`
- `0x180033034`: `WinREAgent::WinREGetOSDisk`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall WinREAgent::WinREGetOSDisk(WinREAgent *this, struct PushButtonReset::Disk **a2)
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
      v9 = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
      v5 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v9);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v8,
        (__int64)Buffer);
      v6 = PushButtonReset::Disk::FindByFilePath(&v8, v5);
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
          "WinREAgent::WinREGetOSDisk",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
          194,
          L"Failed to get Disk for OS");
      }
      v9 = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(&v9);
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
        "WinREAgent::WinREGetOSDisk",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
        188,
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
      "WinREAgent::WinREGetOSDisk",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\partition.cpp",
      180,
      L"res cannot be null");
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180032ee0  push    rbp
0x180032ee2  push    rbx
0x180032ee3  push    rsi
0x180032ee4  push    rdi
0x180032ee5  lea     rbp, [rsp-178h]
0x180032eed  sub     rsp, 278h
0x180032ef4  mov     rax, cs:__security_cookie
0x180032efb  xor     rax, rsp
0x180032efe  mov     [rbp+190h+var_30], rax
0x180032f05  mov     rdi, rcx
0x180032f08  test    rcx, rcx
0x180032f0b  jnz     short loc_180032F46
0x180032f0d  lea     rax, aResCannotBeNul; "res cannot be null"
0x180032f14  mov     [rsp+290h+var_268], rax
0x180032f19  mov     [rsp+290h+var_270], 0B4h
0x180032f21  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032f28  lea     r8, aWinreagentWinr_25; "WinREAgent::WinREGetOSDisk"
0x180032f2f  mov     edx, 80070057h
0x180032f34  lea     ecx, [rdi+2]
0x180032f37  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032f3c  mov     eax, 80070057h
0x180032f41  jmp     loc_18003306B
0x180032f46  xor     edx, edx; Val
0x180032f48  mov     r8d, 20Ah; Size
0x180032f4e  lea     rcx, [rsp+290h+Buffer]; void *
0x180032f53  call    memset_0
0x180032f58  mov     edx, 104h; uSize
0x180032f5d  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x180032f62  call    cs:__imp_GetWindowsDirectoryW
0x180032f68  test    eax, eax
0x180032f6a  jnz     short loc_180032FC6
0x180032f6c  call    cs:__imp_GetLastError
0x180032f72  mov     ebx, 80070000h
0x180032f77  test    eax, eax
0x180032f79  jle     short loc_180032F80
0x180032f7b  movzx   eax, ax
0x180032f7e  or      eax, ebx
0x180032f80  lea     rcx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180032f87  mov     [rsp+290h+var_268], rcx
0x180032f8c  mov     [rsp+290h+var_270], 0BCh
0x180032f94  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032f9b  lea     r8, aWinreagentWinr_25; "WinREAgent::WinREGetOSDisk"
0x180032fa2  mov     edx, eax
0x180032fa4  mov     ecx, 2
0x180032fa9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032fae  call    cs:__imp_GetLastError
0x180032fb4  test    eax, eax
0x180032fb6  jle     loc_18003306B
0x180032fbc  movzx   eax, ax
0x180032fbf  or      eax, ebx
0x180032fc1  jmp     loc_18003306B
0x180032fc6  mov     [rsp+290h+var_250], 0
0x180032fcf  lea     rsi, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x180032fd6  mov     [rsp+290h+var_258], rsi
0x180032fdb  lea     rcx, [rsp+290h+var_258]
0x180032fe0  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180032fe5  mov     rbx, rax
0x180032fe8  lea     rdx, [rsp+290h+Buffer]
0x180032fed  lea     rcx, [rsp+290h+var_260]
0x180032ff2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180032ff7  nop
0x180032ff8  mov     rdx, rbx
0x180032ffb  lea     rcx, [rsp+290h+var_260]
0x180033000  call    ?FindByFilePath@Disk@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::Disk::FindByFilePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::Disk * *)
0x180033005  mov     ebx, eax
0x180033007  mov     rcx, [rsp+290h+var_260]
0x18003300c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180033010  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180033015  test    ebx, ebx
0x180033017  jns     short loc_180033049
0x180033019  lea     rax, aFailedToGetDis_0; "Failed to get Disk for OS"
0x180033020  mov     [rsp+290h+var_268], rax
0x180033025  mov     [rsp+290h+var_270], 0C2h
0x18003302d  lea     r9, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180033034  lea     r8, aWinreagentWinr_25; "WinREAgent::WinREGetOSDisk"
0x18003303b  mov     edx, ebx
0x18003303d  mov     ecx, 2
0x180033042  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180033047  jmp     short loc_18003305A
0x180033049  mov     rax, [rsp+290h+var_250]
0x18003304e  mov     [rsp+290h+var_250], 0
0x180033057  mov     [rdi], rax
0x18003305a  mov     [rsp+290h+var_258], rsi
0x18003305f  lea     rcx, [rsp+290h+var_258]
0x180033064  call    ?Release@?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(void)
0x180033069  mov     eax, ebx
0x18003306b  mov     rcx, [rbp+190h+var_30]
0x180033072  xor     rcx, rsp; StackCookie
0x180033075  call    __security_check_cookie
0x18003307a  add     rsp, 278h
0x180033081  pop     rdi
0x180033082  pop     rsi
0x180033083  pop     rbx
0x180033084  pop     rbp
0x180033085  retn
```

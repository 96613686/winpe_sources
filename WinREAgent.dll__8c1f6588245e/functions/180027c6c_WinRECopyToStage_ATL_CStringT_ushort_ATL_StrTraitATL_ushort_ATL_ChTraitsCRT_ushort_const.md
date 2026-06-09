# WinRECopyToStage(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180027c6c`
- end: `0x180027fd4`
- name: `?WinRECopyToStage@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `872`
- prototype: `signed int __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180026ae0`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x180027c6c`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004b35c`
- `0x18004bb04`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180027d1a`
- `KERNEL32!GetLastError` at `0x180027d5c`
- `KERNEL32!GetLastError` at `0x180027d1a`
- `KERNEL32!GetLastError` at `0x180027d5c`
- `KERNEL32!GetWindowsDirectoryW` at `0x180027d10`
- `KERNEL32!GetWindowsDirectoryW` at `0x180027d10`

## string_xrefs

- `0x180027e6b`: `Failed to create [%s]`
- `0x180027ccd`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027d42`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027dec`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027e7f`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027f36`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027f84`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180027c97`: `Copy backup WinRE [%s] to default stage location`
- `0x180027cd4`: `WinRECopyToStage`
- `0x180027d49`: `WinRECopyToStage`
- `0x180027df3`: `WinRECopyToStage`
- `0x180027e86`: `WinRECopyToStage`
- `0x180027f3d`: `WinRECopyToStage`
- `0x180027f8b`: `WinRECopyToStage`
- `0x180027d2e`: `Failed to get host system Windows directory`
- `0x180027d7f`: `System32\Recovery`
- `0x180027dd8`: `Failed to construct path of default stage location`
- `0x180027ee5`: `Failed to construct path of WinRE.wim in stage location`
- `0x180027f06`: `Copy backup WinRE [%s] to [%s]`
- `0x180027f22`: `Stage location already containing a WinRE.wim file`
- `0x180027f70`: `Failed to copy WinRE to default stage location`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
signed int __fastcall WinRECopyToStage(_QWORD *a1)
{
  signed int result; // eax
  signed int LastError; // eax
  int v4; // ebx
  int v5; // edi
  __int64 v6; // rbx
  int v7; // edi
  __int64 v8; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  PushButtonReset::Logging::Trace(0, L"Copy backup WinRE [%s] to default stage location", *a1);
  if ( (unsigned __int8)PushButtonReset::File::Exists(a1) )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v9,
        L"System32\\Recovery");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v8,
        Buffer);
      v4 = PushButtonReset::Path::Combine(&v8, &v9, v10);
      ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
      if ( v4 >= 0 )
      {
        if ( (unsigned __int8)PushButtonReset::Directory::Exists(v10)
          || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v9,
                &pszFormat),
              v5 = PushButtonReset::Directory::Create(v10, 0, &v9),
              ATL::CStringData::Release((ATL::CStringData *)(v9 - 24)),
              v5 >= 0) )
        {
          v6 = v10[0];
        }
        else
        {
          v6 = v10[0];
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v5,
            "WinRECopyToStage",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            961,
            L"Failed to create [%s]",
            v10[0]);
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v8);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v9,
          L"WinRE.wim");
        v7 = PushButtonReset::Path::Combine(v10, &v9, &v8);
        ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
        if ( v7 >= 0 )
        {
          PushButtonReset::Logging::Trace(0, L"Copy backup WinRE [%s] to [%s]", *a1, v8);
          if ( (unsigned __int8)PushButtonReset::File::Exists(&v8) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942480LL,
              "WinRECopyToStage",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
              976,
              L"Stage location already containing a WinRE.wim file");
            v7 = -2147024816;
          }
          else
          {
            v7 = PushButtonReset::File::Copy(a1, &v8, 0);
            if ( v7 < 0 )
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v7,
                "WinRECopyToStage",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
                980,
                L"Failed to copy WinRE to default stage location");
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v7,
            "WinRECopyToStage",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            969,
            L"Failed to construct path of WinRE.wim in stage location");
        }
        ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
        ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
        return v7;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v4,
          "WinRECopyToStage",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          954,
          L"Failed to construct path of default stage location");
        ATL::CStringData::Release((ATL::CStringData *)(v10[0] - 24LL));
        return v4;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinRECopyToStage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        948,
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
      2147942402LL,
      "WinRECopyToStage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      938,
      L"Backup Wim file [%s] doesn't exist",
      *a1);
    return -2147024894;
  }
  return result;
}

```

## disassembly

```asm
0x180027c6c  push    rbp
0x180027c6e  push    rbx
0x180027c6f  push    rsi
0x180027c70  push    rdi
0x180027c71  lea     rbp, [rsp-188h]
0x180027c79  sub     rsp, 288h
0x180027c80  mov     rax, cs:__security_cookie
0x180027c87  xor     rax, rsp
0x180027c8a  mov     [rbp+1A0h+var_30], rax
0x180027c91  mov     rsi, rcx
0x180027c94  mov     r8, [rcx]
0x180027c97  lea     rdx, aCopyBackupWinr; "Copy backup WinRE [%s] to default stage"...
0x180027c9e  xor     ecx, ecx
0x180027ca0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027ca5  mov     rcx, rsi
0x180027ca8  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027cad  test    al, al
0x180027caf  jnz     short loc_180027CF4
0x180027cb1  mov     rax, [rsi]
0x180027cb4  mov     [rsp+2A0h+var_270], rax
0x180027cb9  lea     rax, aBackupWimFileS; "Backup Wim file [%s] doesn't exist"
0x180027cc0  mov     [rsp+2A0h+var_278], rax
0x180027cc5  mov     [rsp+2A0h+var_280], 3AAh
0x180027ccd  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027cd4  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027cdb  mov     edx, 80070002h
0x180027ce0  mov     ecx, 2
0x180027ce5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027cea  mov     eax, 80070002h
0x180027cef  jmp     loc_180027FB9
0x180027cf4  xor     edx, edx; Val
0x180027cf6  mov     r8d, 20Ah; Size
0x180027cfc  lea     rcx, [rsp+2A0h+Buffer]; void *
0x180027d01  call    memset_0
0x180027d06  mov     edx, 104h; uSize
0x180027d0b  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180027d10  call    cs:__imp_GetWindowsDirectoryW
0x180027d16  test    eax, eax
0x180027d18  jnz     short loc_180027D74
0x180027d1a  call    cs:__imp_GetLastError
0x180027d20  mov     ebx, 80070000h
0x180027d25  test    eax, eax
0x180027d27  jle     short loc_180027D2E
0x180027d29  movzx   eax, ax
0x180027d2c  or      eax, ebx
0x180027d2e  lea     rcx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x180027d35  mov     [rsp+2A0h+var_278], rcx
0x180027d3a  mov     [rsp+2A0h+var_280], 3B4h
0x180027d42  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027d49  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027d50  mov     edx, eax
0x180027d52  mov     ecx, 2
0x180027d57  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027d5c  call    cs:__imp_GetLastError
0x180027d62  test    eax, eax
0x180027d64  jle     loc_180027FB9
0x180027d6a  movzx   eax, ax
0x180027d6d  or      eax, ebx
0x180027d6f  jmp     loc_180027FB9
0x180027d74  lea     rcx, [rsp+2A0h+var_250]
0x180027d79  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180027d7e  nop
0x180027d7f  lea     rdx, aSystem32Recove_0; "System32\\Recovery"
0x180027d86  lea     rcx, [rsp+2A0h+var_258]
0x180027d8b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180027d90  nop
0x180027d91  lea     rdx, [rsp+2A0h+Buffer]
0x180027d96  lea     rcx, [rsp+2A0h+var_260]
0x180027d9b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180027da0  nop
0x180027da1  lea     r8, [rsp+2A0h+var_250]
0x180027da6  lea     rdx, [rsp+2A0h+var_258]
0x180027dab  lea     rcx, [rsp+2A0h+var_260]
0x180027db0  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180027db5  mov     ebx, eax
0x180027db7  mov     rcx, [rsp+2A0h+var_260]
0x180027dbc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027dc0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027dc5  nop
0x180027dc6  mov     rcx, [rsp+2A0h+var_258]
0x180027dcb  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027dcf  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027dd4  test    ebx, ebx
0x180027dd6  jns     short loc_180027E1C
0x180027dd8  lea     rax, aFailedToConstr_4; "Failed to construct path of default sta"...
0x180027ddf  mov     [rsp+2A0h+var_278], rax
0x180027de4  mov     [rsp+2A0h+var_280], 3BAh
0x180027dec  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027df3  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027dfa  mov     edx, ebx
0x180027dfc  mov     ecx, 2
0x180027e01  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027e06  nop
0x180027e07  mov     rcx, [rsp+2A0h+var_250]
0x180027e0c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027e10  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027e15  mov     eax, ebx
0x180027e17  jmp     loc_180027FB9
0x180027e1c  lea     rcx, [rsp+2A0h+var_250]
0x180027e21  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027e26  test    al, al
0x180027e28  jnz     short loc_180027E9B
0x180027e2a  lea     rdx, pszFormat
0x180027e31  lea     rcx, [rsp+2A0h+var_258]
0x180027e36  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180027e3b  nop
0x180027e3c  lea     r8, [rsp+2A0h+var_258]
0x180027e41  xor     edx, edx
0x180027e43  lea     rcx, [rsp+2A0h+var_250]
0x180027e48  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027e4d  mov     edi, eax
0x180027e4f  mov     rcx, [rsp+2A0h+var_258]
0x180027e54  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027e58  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027e5d  test    edi, edi
0x180027e5f  jns     short loc_180027E9B
0x180027e61  mov     rbx, [rsp+2A0h+var_250]
0x180027e66  mov     [rsp+2A0h+var_270], rbx
0x180027e6b  lea     rax, aFailedToCreate_3; "Failed to create [%s]"
0x180027e72  mov     [rsp+2A0h+var_278], rax
0x180027e77  mov     [rsp+2A0h+var_280], 3C1h
0x180027e7f  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027e86  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027e8d  mov     edx, edi
0x180027e8f  mov     ecx, 1
0x180027e94  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027e99  jmp     short loc_180027EA0
0x180027e9b  mov     rbx, [rsp+2A0h+var_250]
0x180027ea0  lea     rcx, [rsp+2A0h+var_260]
0x180027ea5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180027eaa  nop
0x180027eab  lea     rdx, aWinreWim; "WinRE.wim"
0x180027eb2  lea     rcx, [rsp+2A0h+var_258]
0x180027eb7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180027ebc  nop
0x180027ebd  lea     r8, [rsp+2A0h+var_260]
0x180027ec2  lea     rdx, [rsp+2A0h+var_258]
0x180027ec7  lea     rcx, [rsp+2A0h+var_250]
0x180027ecc  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180027ed1  mov     edi, eax
0x180027ed3  mov     rcx, [rsp+2A0h+var_258]
0x180027ed8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027edc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027ee1  test    edi, edi
0x180027ee3  jns     short loc_180027EFE
0x180027ee5  lea     rax, aFailedToConstr_6; "Failed to construct path of WinRE.wim i"...
0x180027eec  mov     [rsp+2A0h+var_278], rax
0x180027ef1  mov     [rsp+2A0h+var_280], 3C9h
0x180027ef9  jmp     loc_180027F84
0x180027efe  mov     r9, [rsp+2A0h+var_260]
0x180027f03  mov     r8, [rsi]
0x180027f06  lea     rdx, aCopyBackupWinr_2; "Copy backup WinRE [%s] to [%s]"
0x180027f0d  xor     ecx, ecx
0x180027f0f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180027f14  lea     rcx, [rsp+2A0h+var_260]
0x180027f19  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180027f1e  test    al, al
0x180027f20  jz      short loc_180027F5A
0x180027f22  lea     rax, aStageLocationA; "Stage location already containing a Win"...
0x180027f29  mov     [rsp+2A0h+var_278], rax
0x180027f2e  mov     [rsp+2A0h+var_280], 3D0h
0x180027f36  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027f3d  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027f44  mov     edx, 80070050h
0x180027f49  mov     ecx, 2
0x180027f4e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027f53  mov     edi, 80070050h
0x180027f58  jmp     short loc_180027F9F
0x180027f5a  xor     r8d, r8d
0x180027f5d  lea     rdx, [rsp+2A0h+var_260]
0x180027f62  mov     rcx, rsi
0x180027f65  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x180027f6a  mov     edi, eax
0x180027f6c  test    eax, eax
0x180027f6e  jns     short loc_180027F9F
0x180027f70  lea     rax, aFailedToCopyWi_0; "Failed to copy WinRE to default stage l"...
0x180027f77  mov     [rsp+2A0h+var_278], rax
0x180027f7c  mov     [rsp+2A0h+var_280], 3D4h
0x180027f84  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180027f8b  lea     r8, aWinrecopytosta; "WinRECopyToStage"
0x180027f92  mov     edx, edi
0x180027f94  mov     ecx, 2
0x180027f99  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180027f9e  nop
0x180027f9f  mov     rcx, [rsp+2A0h+var_260]
0x180027fa4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180027fa8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027fad  nop
0x180027fae  lea     rcx, [rbx-18h]; this
0x180027fb2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180027fb7  mov     eax, edi
0x180027fb9  mov     rcx, [rbp+1A0h+var_30]
0x180027fc0  xor     rcx, rsp; StackCookie
0x180027fc3  call    __security_check_cookie
0x180027fc8  add     rsp, 288h
0x180027fcf  pop     rdi
0x180027fd0  pop     rsi
0x180027fd1  pop     rbx
0x180027fd2  pop     rbp
0x180027fd3  retn
```

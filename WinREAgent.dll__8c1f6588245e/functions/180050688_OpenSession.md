# OpenSession

- ea: `0x180050688`
- end: `0x1800508d9`
- name: `OpenSession`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180050588`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x180037344`
- `0x18004a350`
- `0x18004d7a0`
- `0x180050688`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800506e2`
- `KERNEL32!GetLastError` at `0x180050724`
- `KERNEL32!GetLastError` at `0x1800506e2`
- `KERNEL32!GetLastError` at `0x180050724`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800506d8`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800506d8`
- `DismApi!DismOpenSession` at `0x180050820`
- `DismApi!DismOpenSession` at `0x18005085f`
- `DismApi!DismOpenSession` at `0x180050820`
- `DismApi!DismOpenSession` at `0x18005085f`

## string_xrefs

- `0x1800506f6`: `Failed to get host system Windows directory`
- `0x180050711`: `OpenSession`
- `0x1800507e7`: `OpenSession`
- `0x180050847`: `OpenSession`
- `0x18005088e`: `OpenSession`
- `0x180050784`: `Failed to get parent directory for [%s]`
- `0x1800507cc`: `Failed to check whether input directory [%s] is the host Windows dir [%s]`
- `0x18005082c`: `Failed to open DISM session for running host OS`
- `0x180050873`: `Failed to open DISM session against [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall OpenSession(_QWORD *a1, __int64 a2)
{
  signed int LastError; // eax
  signed int result; // eax
  int Directory; // ebx
  int v7; // esi
  __int64 v8; // rbx
  _BYTE v9[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v11[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v11,
      (__int64)Buffer);
    Directory = PushButtonReset::Path::GetDirectory(v11, &v10);
    ATL::CStringData::Release((ATL::CStringData *)(v11[0] - 24LL));
    if ( Directory >= 0 )
    {
      v9[0] = 0;
      v7 = PushButtonReset::Path::AreEqual(a1, &v10, v9);
      if ( v7 < 0 )
      {
        v8 = v10;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v7,
          "OpenSession",
          "base\\reset\\util\\src\\dism.cpp",
          74,
          L"Failed to check whether input directory [%s] is the host Windows dir [%s]",
          *a1,
          v10);
        ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
        return v7;
      }
      if ( v9[0] )
      {
        Directory = DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, a2);
        if ( Directory < 0 )
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Directory,
            "OpenSession",
            "base\\reset\\util\\src\\dism.cpp",
            79,
            L"Failed to open DISM session for running host OS");
      }
      else
      {
        Directory = DismOpenSession(*a1, 0, 0, a2);
        if ( Directory < 0 )
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Directory,
            "OpenSession",
            "base\\reset\\util\\src\\dism.cpp",
            84,
            L"Failed to open DISM session against [%s]",
            *a1);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Directory,
        "OpenSession",
        "base\\reset\\util\\src\\dism.cpp",
        68,
        L"Failed to get parent directory for [%s]",
        Buffer);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    return Directory;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "OpenSession",
      "base\\reset\\util\\src\\dism.cpp",
      63,
      L"Failed to get host system Windows directory");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180050688  mov     [rsp-8+arg_10], rbx
0x18005068d  mov     [rsp-8+arg_18], rsi
0x180050692  push    rbp
0x180050693  push    rdi
0x180050694  push    r14
0x180050696  lea     rbp, [rsp-180h]
0x18005069e  sub     rsp, 280h
0x1800506a5  mov     rax, cs:__security_cookie
0x1800506ac  xor     rax, rsp
0x1800506af  mov     [rbp+190h+var_20], rax
0x1800506b6  mov     r14, rdx
0x1800506b9  mov     rdi, rcx
0x1800506bc  xor     edx, edx; Val
0x1800506be  mov     r8d, 20Ah; Size
0x1800506c4  lea     rcx, [rsp+290h+Buffer]; void *
0x1800506c9  call    memset_0
0x1800506ce  mov     edx, 104h; uSize
0x1800506d3  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x1800506d8  call    cs:__imp_GetWindowsDirectoryW
0x1800506de  test    eax, eax
0x1800506e0  jnz     short loc_18005073C
0x1800506e2  call    cs:__imp_GetLastError
0x1800506e8  mov     ebx, 80070000h
0x1800506ed  test    eax, eax
0x1800506ef  jle     short loc_1800506F6
0x1800506f1  movzx   eax, ax
0x1800506f4  or      eax, ebx
0x1800506f6  lea     rcx, aFailedToGetHos; "Failed to get host system Windows direc"...
0x1800506fd  mov     [rsp+290h+var_268], rcx
0x180050702  mov     [rsp+290h+var_270], 3Fh ; '?'
0x18005070a  lea     r9, aBaseResetUtilS_6; "base\\reset\\util\\src\\dism.cpp"
0x180050711  lea     r8, aOpensession; "OpenSession"
0x180050718  mov     edx, eax
0x18005071a  mov     ecx, 2
0x18005071f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180050724  call    cs:__imp_GetLastError
0x18005072a  test    eax, eax
0x18005072c  jle     loc_1800508B2
0x180050732  movzx   eax, ax
0x180050735  or      eax, ebx
0x180050737  jmp     loc_1800508B2
0x18005073c  lea     rcx, [rsp+290h+var_248]
0x180050741  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180050746  nop
0x180050747  lea     rdx, [rsp+290h+Buffer]
0x18005074c  lea     rcx, [rsp+290h+var_240]
0x180050751  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180050756  nop
0x180050757  lea     rdx, [rsp+290h+var_248]
0x18005075c  lea     rcx, [rsp+290h+var_240]
0x180050761  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180050766  mov     ebx, eax
0x180050768  mov     rcx, [rsp+290h+var_240]
0x18005076d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180050771  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180050776  test    ebx, ebx
0x180050778  jns     short loc_18005079D
0x18005077a  lea     rax, [rsp+290h+Buffer]
0x18005077f  mov     [rsp+290h+var_260], rax
0x180050784  lea     rax, aFailedToGetPar_2; "Failed to get parent directory for [%s]"
0x18005078b  mov     [rsp+290h+var_268], rax
0x180050790  mov     [rsp+290h+var_270], 44h ; 'D'
0x180050798  jmp     loc_180050887
0x18005079d  mov     [rsp+290h+var_250], 0
0x1800507a2  lea     r8, [rsp+290h+var_250]
0x1800507a7  lea     rdx, [rsp+290h+var_248]
0x1800507ac  mov     rcx, rdi
0x1800507af  call    ?AreEqual@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z; PushButtonReset::Path::AreEqual(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x1800507b4  mov     esi, eax
0x1800507b6  test    eax, eax
0x1800507b8  jns     short loc_18005080B
0x1800507ba  mov     rbx, [rsp+290h+var_248]
0x1800507bf  mov     [rsp+290h+var_258], rbx
0x1800507c4  mov     rcx, [rdi]
0x1800507c7  mov     [rsp+290h+var_260], rcx
0x1800507cc  lea     rax, aFailedToCheckW_2; "Failed to check whether input directory"...
0x1800507d3  mov     [rsp+290h+var_268], rax
0x1800507d8  mov     [rsp+290h+var_270], 4Ah ; 'J'
0x1800507e0  lea     r9, aBaseResetUtilS_6; "base\\reset\\util\\src\\dism.cpp"
0x1800507e7  lea     r8, aOpensession; "OpenSession"
0x1800507ee  mov     edx, esi
0x1800507f0  mov     ecx, 2
0x1800507f5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800507fa  nop
0x1800507fb  lea     rcx, [rbx-18h]; this
0x1800507ff  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180050804  mov     eax, esi
0x180050806  jmp     loc_1800508B2
0x18005080b  mov     r9, r14
0x18005080e  xor     r8d, r8d
0x180050811  xor     edx, edx
0x180050813  cmp     [rsp+290h+var_250], dl
0x180050817  jz      short loc_18005085C
0x180050819  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180050820  call    cs:__imp_DismOpenSession
0x180050826  mov     ebx, eax
0x180050828  test    eax, eax
0x18005082a  jns     short loc_1800508A2
0x18005082c  lea     rax, aFailedToOpenDi; "Failed to open DISM session for running"...
0x180050833  mov     [rsp+290h+var_268], rax
0x180050838  mov     [rsp+290h+var_270], 4Fh ; 'O'
0x180050840  lea     r9, aBaseResetUtilS_6; "base\\reset\\util\\src\\dism.cpp"
0x180050847  lea     r8, aOpensession; "OpenSession"
0x18005084e  mov     edx, ebx
0x180050850  mov     ecx, 2
0x180050855  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005085a  jmp     short loc_1800508A2
0x18005085c  mov     rcx, [rdi]
0x18005085f  call    cs:__imp_DismOpenSession
0x180050865  mov     ebx, eax
0x180050867  test    eax, eax
0x180050869  jns     short loc_1800508A2
0x18005086b  mov     rax, [rdi]
0x18005086e  mov     [rsp+290h+var_260], rax
0x180050873  lea     rax, aFailedToOpenDi_0; "Failed to open DISM session against [%s"...
0x18005087a  mov     [rsp+290h+var_268], rax
0x18005087f  mov     [rsp+290h+var_270], 54h ; 'T'
0x180050887  lea     r9, aBaseResetUtilS_6; "base\\reset\\util\\src\\dism.cpp"
0x18005088e  lea     r8, aOpensession; "OpenSession"
0x180050895  mov     edx, ebx
0x180050897  mov     ecx, 2
0x18005089c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800508a1  nop
0x1800508a2  mov     rcx, [rsp+290h+var_248]
0x1800508a7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800508ab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800508b0  mov     eax, ebx
0x1800508b2  mov     rcx, [rbp+190h+var_20]
0x1800508b9  xor     rcx, rsp; StackCookie
0x1800508bc  call    __security_check_cookie
0x1800508c1  lea     r11, [rsp+290h+var_10]
0x1800508c9  mov     rbx, [r11+30h]
0x1800508cd  mov     rsi, [r11+38h]
0x1800508d1  mov     rsp, r11
0x1800508d4  pop     r14
0x1800508d6  pop     rdi
0x1800508d7  pop     rbp
0x1800508d8  retn
```

# PushButtonReset::WindowsRE::OpenConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WindowsRE::Config * *)

- ea: `0x180053830`
- end: `0x180053af4`
- name: `?OpenConfig@WindowsRE@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAVConfig@12@@Z`
- size: `708`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800173a0`
- `0x18001b268`
- `0x18001e51c`

## callees

- `0x1800049a4`
- `0x180005c00`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180037344`
- `0x18004a350`
- `0x1800535fc`
- `0x180053830`
- `0x180053afc`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18005387e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18005387e`
- `KERNEL32!GetLastError` at `0x180053888`
- `KERNEL32!GetLastError` at `0x1800538ca`
- `KERNEL32!GetLastError` at `0x180053a52`
- `KERNEL32!GetLastError` at `0x180053a99`
- `KERNEL32!GetLastError` at `0x180053888`
- `KERNEL32!GetLastError` at `0x1800538ca`
- `KERNEL32!GetLastError` at `0x180053a52`
- `KERNEL32!GetLastError` at `0x180053a99`
- `ReAgent!WinReGetConfig` at `0x180053a45`
- `ReAgent!WinReGetConfig` at `0x180053a45`

## string_xrefs

- `0x1800538b7`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x18005394a`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x180053996`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x1800539ef`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x180053a86`: `PushButtonReset::WindowsRE::OpenConfig`
- `0x18005397b`: `Failed to open system WinRE config`
- `0x180053a6b`: `Failed to load WinRE config for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall PushButtonReset::WindowsRE::OpenConfig(
        __int64 *a1,
        struct PushButtonReset::WindowsRE::Config **a2)
{
  signed int LastError; // eax
  signed int result; // eax
  int v6; // edi
  signed int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  signed int v11; // eax
  signed int v12; // eax
  struct PushButtonReset::WindowsRE::Config *v13; // rcx
  bool v14; // [rsp+40h] [rbp-C0h] BYREF
  void **v15; // [rsp+48h] [rbp-B8h] BYREF
  struct PushButtonReset::WindowsRE::Config *v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::WindowsRE::OpenConfig",
      "base\\reset\\util\\src\\windowsre.cpp",
      238,
      L"Failed to get system Windows dir");
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v14 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)Buffer);
  v6 = PushButtonReset::Path::AreEqual(a1, &v17, &v14);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  if ( v6 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v6,
      "PushButtonReset::WindowsRE::OpenConfig",
      "base\\reset\\util\\src\\windowsre.cpp",
      245,
      L"Failed to check if input [%s] is the host Windows dir [%s]",
      *a1,
      Buffer);
    return v6;
  }
  if ( !v14 )
  {
    v16 = (struct PushButtonReset::WindowsRE::Config *)PbrNew<PushButtonReset::WindowsRE::Config,>();
    v15 = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v15) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::WindowsRE::OpenConfig",
        "base\\reset\\util\\src\\windowsre.cpp",
        256,
        L"Failed to allocate result");
      v6 = -2147024882;
    }
    else
    {
      *(_QWORD *)((__int64 (__fastcall *)(void ***))v15[3])(&v15) = 3744;
      v8 = *a1;
      v9 = ((__int64 (__fastcall *)(void ***))v15[3])(&v15);
      if ( (unsigned int)WinReGetConfig(v8, v9) )
      {
        v13 = v16;
        v16 = 0;
        *a2 = v13;
      }
      else
      {
        v10 = *a1;
        v11 = GetLastError();
        if ( v11 > 0 )
          v11 = (unsigned __int16)v11 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::WindowsRE::OpenConfig",
          "base\\reset\\util\\src\\windowsre.cpp",
          265,
          L"Failed to load WinRE config for [%s]",
          v10);
        v12 = GetLastError();
        v6 = v12;
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
      }
    }
    v15 = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v15);
    return v6;
  }
  result = PushButtonReset::WindowsRE::OpenConfig(a2);
  v7 = result;
  if ( result < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)result,
      "PushButtonReset::WindowsRE::OpenConfig",
      "base\\reset\\util\\src\\windowsre.cpp",
      250,
      L"Failed to open system WinRE config");
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180053830  mov     [rsp-8+arg_10], rbx
0x180053835  push    rbp
0x180053836  push    rsi
0x180053837  push    rdi
0x180053838  push    r12
0x18005383a  push    r14
0x18005383c  lea     rbp, [rsp-180h]
0x180053844  sub     rsp, 280h
0x18005384b  mov     rax, cs:__security_cookie
0x180053852  xor     rax, rsp
0x180053855  mov     [rbp+1A0h+var_30], rax
0x18005385c  mov     r14, rdx
0x18005385f  mov     rsi, rcx
0x180053862  xor     edx, edx; Val
0x180053864  mov     r8d, 20Ah; Size
0x18005386a  lea     rcx, [rsp+2A0h+Buffer]; void *
0x18005386f  call    memset_0
0x180053874  mov     edx, 104h; uSize
0x180053879  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18005387e  call    cs:__imp_GetSystemWindowsDirectoryW
0x180053884  test    eax, eax
0x180053886  jnz     short loc_1800538E2
0x180053888  call    cs:__imp_GetLastError
0x18005388e  mov     ebx, 80070000h
0x180053893  test    eax, eax
0x180053895  jle     short loc_18005389C
0x180053897  movzx   eax, ax
0x18005389a  or      eax, ebx
0x18005389c  lea     rcx, aFailedToGetSys; "Failed to get system Windows dir"
0x1800538a3  mov     [rsp+2A0h+var_278], rcx
0x1800538a8  mov     [rsp+2A0h+var_280], 0EEh
0x1800538b0  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x1800538b7  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x1800538be  mov     edx, eax
0x1800538c0  mov     ecx, 2
0x1800538c5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800538ca  call    cs:__imp_GetLastError
0x1800538d0  test    eax, eax
0x1800538d2  jle     loc_180053ACE
0x1800538d8  movzx   eax, ax
0x1800538db  or      eax, ebx
0x1800538dd  jmp     loc_180053ACE
0x1800538e2  mov     [rsp+2A0h+var_260], 0
0x1800538e7  lea     rdx, [rsp+2A0h+Buffer]
0x1800538ec  lea     rcx, [rsp+2A0h+var_248]
0x1800538f1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800538f6  nop
0x1800538f7  lea     r8, [rsp+2A0h+var_260]
0x1800538fc  lea     rdx, [rsp+2A0h+var_248]
0x180053901  mov     rcx, rsi
0x180053904  call    ?AreEqual@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z; PushButtonReset::Path::AreEqual(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x180053909  mov     edi, eax
0x18005390b  mov     rcx, [rsp+2A0h+var_248]
0x180053910  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180053914  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180053919  test    edi, edi
0x18005391b  jns     short loc_180053962
0x18005391d  lea     rax, [rsp+2A0h+Buffer]
0x180053922  mov     [rsp+2A0h+var_268], rax
0x180053927  mov     rax, [rsi]
0x18005392a  mov     [rsp+2A0h+var_270], rax
0x18005392f  lea     rax, aFailedToCheckI_1; "Failed to check if input [%s] is the ho"...
0x180053936  mov     [rsp+2A0h+var_278], rax
0x18005393b  mov     [rsp+2A0h+var_280], 0F5h
0x180053943  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x18005394a  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x180053951  mov     edx, edi
0x180053953  mov     ecx, 2
0x180053958  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005395d  jmp     loc_180053ACC
0x180053962  cmp     [rsp+2A0h+var_260], 0
0x180053967  jz      short loc_1800539B0
0x180053969  mov     rcx, r14; struct PushButtonReset::WindowsRE::Config **
0x18005396c  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x180053971  mov     ebx, eax
0x180053973  test    eax, eax
0x180053975  jns     loc_180053ACE
0x18005397b  lea     rax, aFailedToOpenSy; "Failed to open system WinRE config"
0x180053982  mov     [rsp+2A0h+var_278], rax
0x180053987  mov     [rsp+2A0h+var_280], 0FAh
0x18005398f  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x180053996  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x18005399d  mov     edx, ebx
0x18005399f  mov     ecx, 2
0x1800539a4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800539a9  mov     eax, ebx
0x1800539ab  jmp     loc_180053ACE
0x1800539b0  call    ??$PbrNew@VConfig@WindowsRE@PushButtonReset@@$$V@@YAPEAVConfig@WindowsRE@PushButtonReset@@XZ; PbrNew<PushButtonReset::WindowsRE::Config,>(void)
0x1800539b5  mov     [rsp+2A0h+var_250], rax
0x1800539ba  lea     r12, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x1800539c1  mov     [rsp+2A0h+var_258], r12
0x1800539c6  lea     rcx, [rsp+2A0h+var_258]
0x1800539cb  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x1800539d0  test    al, al
0x1800539d2  jz      short loc_180053A0F
0x1800539d4  lea     rax, aFailedToAlloca_43; "Failed to allocate result"
0x1800539db  mov     [rsp+2A0h+var_278], rax
0x1800539e0  mov     [rsp+2A0h+var_280], 100h
0x1800539e8  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x1800539ef  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x1800539f6  mov     edx, 8007000Eh
0x1800539fb  mov     ecx, 2
0x180053a00  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053a05  mov     edi, 8007000Eh
0x180053a0a  jmp     loc_180053ABD
0x180053a0f  mov     rax, [rsp+2A0h+var_258]
0x180053a14  lea     rcx, [rsp+2A0h+var_258]
0x180053a19  mov     rax, [rax+18h]
0x180053a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a22  mov     qword ptr [rax], 0EA0h
0x180053a29  mov     rbx, [rsi]
0x180053a2c  mov     rax, [rsp+2A0h+var_258]
0x180053a31  lea     rcx, [rsp+2A0h+var_258]
0x180053a36  mov     rax, [rax+18h]
0x180053a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a3f  mov     rdx, rax
0x180053a42  mov     rcx, rbx
0x180053a45  call    cs:__imp_WinReGetConfig
0x180053a4b  test    eax, eax
0x180053a4d  jnz     short loc_180053AAC
0x180053a4f  mov     rdi, [rsi]
0x180053a52  call    cs:__imp_GetLastError
0x180053a58  mov     ebx, 80070000h
0x180053a5d  test    eax, eax
0x180053a5f  jle     short loc_180053A66
0x180053a61  movzx   eax, ax
0x180053a64  or      eax, ebx
0x180053a66  mov     [rsp+2A0h+var_270], rdi
0x180053a6b  lea     rcx, aFailedToLoadWi; "Failed to load WinRE config for [%s]"
0x180053a72  mov     [rsp+2A0h+var_278], rcx
0x180053a77  mov     [rsp+2A0h+var_280], 109h
0x180053a7f  lea     r9, aBaseResetUtilS_11; "base\\reset\\util\\src\\windowsre.cpp"
0x180053a86  lea     r8, aPushbuttonrese_0; "PushButtonReset::WindowsRE::OpenConfig"
0x180053a8d  mov     edx, eax
0x180053a8f  mov     ecx, 2
0x180053a94  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053a99  call    cs:__imp_GetLastError
0x180053a9f  mov     edi, eax
0x180053aa1  test    eax, eax
0x180053aa3  jle     short loc_180053ABD
0x180053aa5  movzx   edi, ax
0x180053aa8  or      edi, ebx
0x180053aaa  jmp     short loc_180053ABD
0x180053aac  mov     rcx, [rsp+2A0h+var_250]
0x180053ab1  mov     [rsp+2A0h+var_250], 0
0x180053aba  mov     [r14], rcx
0x180053abd  mov     [rsp+2A0h+var_258], r12
0x180053ac2  lea     rcx, [rsp+2A0h+var_258]
0x180053ac7  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180053acc  mov     eax, edi
0x180053ace  mov     rcx, [rbp+1A0h+var_30]
0x180053ad5  xor     rcx, rsp; StackCookie
0x180053ad8  call    __security_check_cookie
0x180053add  mov     rbx, [rsp+2A0h+arg_10]
0x180053ae5  add     rsp, 280h
0x180053aec  pop     r14
0x180053aee  pop     r12
0x180053af0  pop     rdi
0x180053af1  pop     rsi
0x180053af2  pop     rbp
0x180053af3  retn
```

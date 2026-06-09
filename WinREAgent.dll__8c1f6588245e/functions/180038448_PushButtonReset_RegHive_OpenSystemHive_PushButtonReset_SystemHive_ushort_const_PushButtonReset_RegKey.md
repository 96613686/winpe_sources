# PushButtonReset::RegHive::OpenSystemHive(PushButtonReset::SystemHive,ushort const *,PushButtonReset::RegKey * *)

- ea: `0x180038448`
- end: `0x180038772`
- name: `?OpenSystemHive@RegHive@PushButtonReset@@SAJW4SystemHive@2@PEBGPEAPEAVRegKey@2@@Z`
- size: `810`
- prototype: `static int __high(enum PushButtonReset::SystemHive, const unsigned __int16 *, struct PushButtonReset::RegKey **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b300`
- `0x180038434`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x18003717c`
- `0x180037344`
- `0x180038448`
- `0x18004a350`
- `0x18004a898`
- `0x180056ad8`
- `0x180057cd8`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800384a5`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x1800384a5`
- `KERNEL32!GetLastError` at `0x1800384af`
- `KERNEL32!GetLastError` at `0x1800384af`

## string_xrefs

- `0x1800384c4`: `Failed to get path to host Windows directory`
- `0x1800384d8`: `base\reset\util\src\registry.cpp`
- `0x180038571`: `base\reset\util\src\registry.cpp`
- `0x18003869e`: `base\reset\util\src\registry.cpp`
- `0x1800386f6`: `base\reset\util\src\registry.cpp`
- `0x18003872f`: `base\reset\util\src\registry.cpp`
- `0x1800384df`: `PushButtonReset::RegHive::OpenSystemHive`
- `0x180038578`: `PushButtonReset::RegHive::OpenSystemHive`
- `0x1800386a5`: `PushButtonReset::RegHive::OpenSystemHive`
- `0x1800386fd`: `PushButtonReset::RegHive::OpenSystemHive`
- `0x180038736`: `PushButtonReset::RegHive::OpenSystemHive`
- `0x1800385d6`: `Registry: Loading %s hive from online OS`
- `0x1800385fa`: `Failed to open online hive key`
- `0x180038616`: `Registry: Loading %s hive from offline OS %s`
- `0x18003868a`: `Failed to construct path to [%s] under [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PushButtonReset::RegHive::OpenSystemHive(int a1, __int64 a2, struct PushButtonReset::RegKey **a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 result; // rax
  int v9; // edi
  char v10; // dl
  unsigned __int64 i; // rcx
  __int64 v12; // r8
  HKEY v13; // rdi
  const WCHAR *v14; // r12
  __int64 v15; // r15
  ATL::CStringData *v16; // rcx
  unsigned __int16 *v17; // rbx
  char v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v18[0] = 0;
  if ( a2 )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        v7,
        "PushButtonReset::RegHive::OpenSystemHive",
        "base\\reset\\util\\src\\registry.cpp",
        73,
        L"Failed to get path to host Windows directory");
      return v7;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v20,
      a2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v19,
      (__int64)Buffer);
    v9 = PushButtonReset::Path::AreEqual(&v19, &v20, v18);
    ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
    if ( v9 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "PushButtonReset::RegHive::OpenSystemHive",
        "base\\reset\\util\\src\\registry.cpp",
        79,
        L"Failed to check whether host windir [%s] is target windir [%s]",
        Buffer,
        a2);
      return (unsigned int)v9;
    }
    v10 = v18[0];
  }
  else
  {
    v10 = 1;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942487LL,
        "PushButtonReset::RegHive::OpenSystemHive",
        "base\\reset\\util\\src\\registry.cpp",
        122,
        L"Unrecognized SystemHive type %u",
        a1);
      return 2147942487LL;
    }
    v12 = qword_180073CB0[5 * i + 1];
    v13 = (HKEY)qword_180073CB0[5 * i + 2];
    v14 = (const WCHAR *)qword_180073CB0[5 * i + 3];
    v15 = qword_180073CB0[5 * i + 4];
    if ( LODWORD(qword_180073CB0[5 * i]) == a1 )
      break;
  }
  if ( v10 )
  {
    PushButtonReset::Logging::Trace(0, L"Registry: Loading %s hive from online OS", v12);
    result = PbrOpenOnlineHive(v13, v14, a3);
    v7 = result;
    if ( (int)result >= 0 )
      return result;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)result,
      "PushButtonReset::RegHive::OpenSystemHive",
      "base\\reset\\util\\src\\registry.cpp",
      98,
      L"Failed to open online hive key");
    return v7;
  }
  PushButtonReset::Logging::Trace(0, L"Registry: Loading %s hive from offline OS %s", v12, a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v19);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v21,
    v15);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v20,
    a2);
  v9 = PushButtonReset::Path::Combine(&v20, &v21, &v19);
  ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
  if ( v9 >= 0 )
  {
    v17 = v19;
    v9 = PbrOpenOfflineHive(v19, a3);
    if ( v9 < 0 )
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "PushButtonReset::RegHive::OpenSystemHive",
        "base\\reset\\util\\src\\registry.cpp",
        115,
        L"Failed to load offline hive");
    v16 = (ATL::CStringData *)(v17 - 12);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v9,
      "PushButtonReset::RegHive::OpenSystemHive",
      "base\\reset\\util\\src\\registry.cpp",
      112,
      L"Failed to construct path to [%s] under [%s]",
      v15,
      a2);
    v16 = (ATL::CStringData *)(v19 - 12);
  }
  ATL::CStringData::Release(v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180038448  push    rbp
0x18003844a  push    rbx
0x18003844b  push    rsi
0x18003844c  push    rdi
0x18003844d  push    r12
0x18003844f  push    r14
0x180038451  push    r15
0x180038453  lea     rbp, [rsp-180h]
0x18003845b  sub     rsp, 280h
0x180038462  mov     rax, cs:__security_cookie
0x180038469  xor     rax, rsp
0x18003846c  mov     [rbp+1B0h+var_40], rax
0x180038473  mov     r14, r8
0x180038476  mov     rbx, rdx
0x180038479  mov     esi, ecx
0x18003847b  mov     [rsp+2B0h+var_270], 0
0x180038480  test    rdx, rdx
0x180038483  jz      loc_180038598
0x180038489  xor     edx, edx; Val
0x18003848b  mov     r8d, 20Ah; Size
0x180038491  lea     rcx, [rsp+2B0h+Buffer]; void *
0x180038496  call    memset_0
0x18003849b  mov     edx, 104h; uSize
0x1800384a0  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x1800384a5  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800384ab  test    eax, eax
0x1800384ad  jnz     short loc_1800384F9
0x1800384af  call    cs:__imp_GetLastError
0x1800384b5  mov     ebx, eax
0x1800384b7  test    eax, eax
0x1800384b9  jle     short loc_1800384C4
0x1800384bb  movzx   ebx, ax
0x1800384be  or      ebx, 80070000h
0x1800384c4  lea     rax, aFailedToGetPat; "Failed to get path to host Windows dire"...
0x1800384cb  mov     [rsp+2B0h+var_288], rax
0x1800384d0  mov     [rsp+2B0h+var_290], 49h ; 'I'
0x1800384d8  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800384df  lea     r8, aPushbuttonrese_18; "PushButtonReset::RegHive::OpenSystemHiv"...
0x1800384e6  mov     edx, ebx
0x1800384e8  mov     ecx, 2
0x1800384ed  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800384f2  mov     eax, ebx
0x1800384f4  jmp     loc_180038751
0x1800384f9  mov     rdx, rbx
0x1800384fc  lea     rcx, [rsp+2B0h+var_260]
0x180038501  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180038506  nop
0x180038507  lea     rdx, [rsp+2B0h+Buffer]
0x18003850c  lea     rcx, [rsp+2B0h+var_268]
0x180038511  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180038516  nop
0x180038517  lea     r8, [rsp+2B0h+var_270]
0x18003851c  lea     rdx, [rsp+2B0h+var_260]
0x180038521  lea     rcx, [rsp+2B0h+var_268]
0x180038526  call    ?AreEqual@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z; PushButtonReset::Path::AreEqual(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)
0x18003852b  mov     edi, eax
0x18003852d  mov     rcx, [rsp+2B0h+var_268]
0x180038532  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038536  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003853b  nop
0x18003853c  mov     rcx, [rsp+2B0h+var_260]
0x180038541  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038545  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003854a  test    edi, edi
0x18003854c  jns     short loc_180038592
0x18003854e  mov     [rsp+2B0h+var_278], rbx
0x180038553  lea     rax, [rsp+2B0h+Buffer]
0x180038558  mov     [rsp+2B0h+var_280], rax
0x18003855d  lea     rax, aFailedToCheckW_10; "Failed to check whether host windir [%s"...
0x180038564  mov     [rsp+2B0h+var_288], rax
0x180038569  mov     [rsp+2B0h+var_290], 4Fh ; 'O'
0x180038571  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x180038578  lea     r8, aPushbuttonrese_18; "PushButtonReset::RegHive::OpenSystemHiv"...
0x18003857f  mov     edx, edi
0x180038581  mov     ecx, 2
0x180038586  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003858b  mov     eax, edi
0x18003858d  jmp     loc_180038751
0x180038592  mov     dl, [rsp+2B0h+var_270]
0x180038596  jmp     short loc_18003859A
0x180038598  mov     dl, 1
0x18003859a  xor     ecx, ecx
0x18003859c  cmp     rcx, 3
0x1800385a0  jnb     loc_180038717
0x1800385a6  lea     rax, [rcx+rcx*4]
0x1800385aa  lea     r9, qword_180073CB0
0x1800385b1  mov     r8, [r9+rax*8+8]
0x1800385b6  mov     rdi, [r9+rax*8+10h]
0x1800385bb  mov     r12, [r9+rax*8+18h]
0x1800385c0  mov     r15, [r9+rax*8+20h]
0x1800385c5  cmp     [r9+rax*8], esi
0x1800385c9  jz      short loc_1800385D0
0x1800385cb  inc     rcx
0x1800385ce  jmp     short loc_18003859C
0x1800385d0  xor     ecx, ecx
0x1800385d2  test    dl, dl
0x1800385d4  jz      short loc_180038613
0x1800385d6  lea     rdx, aRegistryLoadin; "Registry: Loading %s hive from online O"...
0x1800385dd  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800385e2  mov     r8, r14; struct PushButtonReset::RegKey **
0x1800385e5  mov     rdx, r12; lpSubKey
0x1800385e8  mov     rcx, rdi; hKey
0x1800385eb  call    ?PbrOpenOnlineHive@@YAJPEAUHKEY__@@PEBGPEAPEAVRegKey@PushButtonReset@@@Z; PbrOpenOnlineHive(HKEY__ *,ushort const *,PushButtonReset::RegKey * *)
0x1800385f0  mov     ebx, eax
0x1800385f2  test    eax, eax
0x1800385f4  jns     loc_180038751
0x1800385fa  lea     rax, aFailedToOpenOn; "Failed to open online hive key"
0x180038601  mov     [rsp+2B0h+var_288], rax
0x180038606  mov     [rsp+2B0h+var_290], 62h ; 'b'
0x18003860e  jmp     loc_1800384D8
0x180038613  mov     r9, rbx
0x180038616  lea     rdx, aRegistryLoadin_0; "Registry: Loading %s hive from offline "...
0x18003861d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180038622  lea     rcx, [rsp+2B0h+var_268]
0x180038627  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003862c  nop
0x18003862d  mov     rdx, r15
0x180038630  lea     rcx, [rsp+2B0h+var_258]
0x180038635  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003863a  nop
0x18003863b  mov     rdx, rbx
0x18003863e  lea     rcx, [rsp+2B0h+var_260]
0x180038643  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180038648  nop
0x180038649  lea     r8, [rsp+2B0h+var_268]
0x18003864e  lea     rdx, [rsp+2B0h+var_258]
0x180038653  lea     rcx, [rsp+2B0h+var_260]
0x180038658  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18003865d  mov     edi, eax
0x18003865f  mov     rcx, [rsp+2B0h+var_260]
0x180038664  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038668  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003866d  nop
0x18003866e  mov     rcx, [rsp+2B0h+var_258]
0x180038673  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180038677  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003867c  test    edi, edi
0x18003867e  jns     short loc_1800386CC
0x180038680  mov     [rsp+2B0h+var_278], rbx
0x180038685  mov     [rsp+2B0h+var_280], r15
0x18003868a  lea     rax, aFailedToConstr_2; "Failed to construct path to [%s] under "...
0x180038691  mov     [rsp+2B0h+var_288], rax
0x180038696  mov     [rsp+2B0h+var_290], 70h ; 'p'
0x18003869e  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800386a5  lea     r8, aPushbuttonrese_18; "PushButtonReset::RegHive::OpenSystemHiv"...
0x1800386ac  mov     edx, edi
0x1800386ae  mov     ecx, 2
0x1800386b3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800386b8  nop
0x1800386b9  mov     rcx, [rsp+2B0h+var_268]
0x1800386be  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800386c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800386c7  jmp     loc_18003858B
0x1800386cc  mov     rdx, r14; struct PushButtonReset::RegKey **
0x1800386cf  mov     rbx, [rsp+2B0h+var_268]
0x1800386d4  mov     rcx, rbx; unsigned __int16 *
0x1800386d7  call    ?PbrOpenOfflineHive@@YAJPEBGPEAPEAVRegKey@PushButtonReset@@@Z; PbrOpenOfflineHive(ushort const *,PushButtonReset::RegKey * *)
0x1800386dc  mov     edi, eax
0x1800386de  test    eax, eax
0x1800386e0  jns     short loc_180038711
0x1800386e2  lea     rax, aFailedToLoadOf; "Failed to load offline hive"
0x1800386e9  mov     [rsp+2B0h+var_288], rax
0x1800386ee  mov     [rsp+2B0h+var_290], 73h ; 's'
0x1800386f6  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x1800386fd  lea     r8, aPushbuttonrese_18; "PushButtonReset::RegHive::OpenSystemHiv"...
0x180038704  mov     edx, edi
0x180038706  mov     ecx, 2
0x18003870b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180038710  nop
0x180038711  lea     rcx, [rbx-18h]
0x180038715  jmp     short loc_1800386C2
0x180038717  mov     dword ptr [rsp+2B0h+var_280], esi
0x18003871b  lea     rax, aUnrecognizedSy; "Unrecognized SystemHive type %u"
0x180038722  mov     [rsp+2B0h+var_288], rax
0x180038727  mov     [rsp+2B0h+var_290], 7Ah ; 'z'
0x18003872f  lea     r9, aBaseResetUtilS_4; "base\\reset\\util\\src\\registry.cpp"
0x180038736  lea     r8, aPushbuttonrese_18; "PushButtonReset::RegHive::OpenSystemHiv"...
0x18003873d  mov     edx, 80070057h
0x180038742  mov     ecx, 2
0x180038747  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003874c  mov     eax, 80070057h
0x180038751  mov     rcx, [rbp+1B0h+var_40]
0x180038758  xor     rcx, rsp; StackCookie
0x18003875b  call    __security_check_cookie
0x180038760  add     rsp, 280h
0x180038767  pop     r15
0x180038769  pop     r14
0x18003876b  pop     r12
0x18003876d  pop     rdi
0x18003876e  pop     rsi
0x18003876f  pop     rbx
0x180038770  pop     rbp
0x180038771  retn
```

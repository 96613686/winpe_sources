# CCompositionDatabase::VelocityCondition::PopulateDeviceInfo(DeviceContext *,CDeviceInfo *)

- ea: `0x1800bf570`
- end: `0x1800bf760`
- name: `?PopulateDeviceInfo@VelocityCondition@CCompositionDatabase@@UEAAJPEAVDeviceContext@@PEAVCDeviceInfo@@@Z`
- size: `496`
- prototype: `__int64 __fastcall(CCompositionDatabase::VelocityCondition *__hidden this, struct DeviceContext *, struct CDeviceInfo *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800031d0`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001b9e4`
- `0x18008265c`
- `0x1800bf570`
- `0x180111138`
- `0x1801832a4`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf654`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800bf603`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800bf603`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800bf644`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800bf644`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800bf5b9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800bf5b9`

## string_xrefs

- `0x1800bf5b2`: `shcore.dll`
- `0x1800bf6fb`: `onecore\base\servicing\arbiter\ccompositiondatabase.cpp`
- `0x1800bf5d3`: `shcore.dll is not available, skipping enumeration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCompositionDatabase::VelocityCondition::PopulateDeviceInfo(
        CCompositionDatabase::VelocityCondition *this,
        struct DeviceContext *a2,
        struct CDeviceInfo *a3)
{
  __int64 v5; // rcx
  HMODULE Library; // rdi
  int v7; // ebx
  FARPROC ProcAddress; // rax
  char v9; // al
  __int64 v10; // rdx
  _OWORD *v12; // rdx
  int v13; // [rsp+20h] [rbp-40h]
  int *v14; // [rsp+20h] [rbp-40h]
  int v15[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h]
  unsigned int v18; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v17 = -2;
  *(_QWORD *)v15 = *((_QWORD *)this + 1);
  Library = LoadLibraryExW(L"shcore.dll", 0, 0x800u);
  v7 = 0;
  *(_QWORD *)&v16 = Library;
  if ( Library )
  {
    v18 = 0;
    if ( (unsigned __int8)Windows::StringUtil::TryParsePositiveInteger<wchar_t const *,unsigned long>(v5, v15, &v18) )
    {
      ProcAddress = GetProcAddress(Library, "GetFeatureEnabledState");
      if ( ProcAddress )
      {
        v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress)(v18, 0);
        v7 = 2;
        if ( (v9 & 2) == 0 )
          v7 = (v9 & 1) != 0 ? 4 : 8;
      }
      else
      {
        GetLastError();
      }
    }
    if ( !FreeLibrary(Library) )
    {
      GetLastError();
      __fastfail(7u);
    }
  }
  else
  {
    LogAdapter::TraceInfo<>("shcore.dll is not available, skipping enumeration");
  }
  HIDWORD(v16) = 0;
  *(_QWORD *)&v16 = DuplicateNullTerminatedString(
                      (struct CDeviceInfo *)((char *)a3 + 208),
                      *((const wchar_t **)this + 1));
  if ( (_QWORD)v16 )
  {
    DWORD2(v16) = v7;
    v12 = (_OWORD *)*((_QWORD *)a3 + 43);
    if ( v12 == *((_OWORD **)a3 + 44) )
    {
      std::vector<CDeviceInfo::Velocity>::_Emplace_reallocate<CDeviceInfo::Velocity>((char *)a3 + 336, v12, &v16);
    }
    else
    {
      *v12 = v16;
      *((_QWORD *)a3 + 43) += 16LL;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\cdeviceinfo.cpp",
      (const char *)0x8007000ELL,
      v13);
    v18 = -2147024882;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to add velocity value to device info.");
      *(_QWORD *)v15 = &v18;
      v14 = v15;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA1,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\ccompositiondatabase.cpp",
      (const char *)0x8007000ELL,
      (int)v14);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800bf570  mov     rax, rsp
0x1800bf573  push    rbp
0x1800bf574  push    rdi
0x1800bf575  push    r14
0x1800bf577  mov     rbp, rsp
0x1800bf57a  sub     rsp, 60h
0x1800bf57e  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x1800bf586  mov     [rax+10h], rbx
0x1800bf58a  mov     [rax+20h], rsi
0x1800bf58e  mov     rax, cs:__security_cookie
0x1800bf595  xor     rax, rsp
0x1800bf598  mov     [rbp+var_8], rax
0x1800bf59c  mov     rsi, r8
0x1800bf59f  mov     r14, rcx
0x1800bf5a2  mov     rax, [rcx+8]
0x1800bf5a6  mov     qword ptr [rbp+var_30], rax
0x1800bf5aa  xor     edx, edx; hFile
0x1800bf5ac  mov     r8d, 800h; dwFlags
0x1800bf5b2  lea     rcx, aShcoreDll; "shcore.dll"
0x1800bf5b9  call    cs:__imp_LoadLibraryExW
0x1800bf5c0  nop     dword ptr [rax+rax+00h]
0x1800bf5c5  mov     rdi, rax
0x1800bf5c8  xor     ebx, ebx
0x1800bf5ca  mov     qword ptr [rbp+var_28], rax
0x1800bf5ce  test    rax, rax
0x1800bf5d1  jnz     short loc_1800BF5E5
0x1800bf5d3  lea     rcx, aShcoreDllIsNot; "shcore.dll is not available, skipping e"...
0x1800bf5da  call    ??$TraceInfo@$$V@LogAdapter@@YAXQEBD@Z; LogAdapter::TraceInfo<>(char const * const)
0x1800bf5df  nop
0x1800bf5e0  jmp     loc_1800BF667
0x1800bf5e5  mov     [rbp+var_10], ebx
0x1800bf5e8  lea     r8, [rbp+var_10]
0x1800bf5ec  lea     rdx, [rbp+var_30]
0x1800bf5f0  call    ??$TryParsePositiveInteger@PEB_WK@StringUtil@Windows@@YA_NKAEBQEB_WPEAK@Z; Windows::StringUtil::TryParsePositiveInteger<wchar_t const *,ulong>(ulong,wchar_t const * const &,ulong *)
0x1800bf5f5  test    al, al
0x1800bf5f7  jz      short loc_1800BF641
0x1800bf5f9  lea     rdx, aGetfeatureenab; "GetFeatureEnabledState"
0x1800bf600  mov     rcx, rdi; hModule
0x1800bf603  call    cs:__imp_GetProcAddress
0x1800bf60a  nop     dword ptr [rax+rax+00h]
0x1800bf60f  test    rax, rax
0x1800bf612  jnz     short loc_1800BF622
0x1800bf614  call    cs:__imp_GetLastError
0x1800bf61b  nop     dword ptr [rax+rax+00h]
0x1800bf620  jmp     short loc_1800BF641
0x1800bf622  xor     edx, edx
0x1800bf624  mov     ecx, [rbp+var_10]
0x1800bf627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf62c  mov     ebx, 2
0x1800bf631  test    bl, al
0x1800bf633  jnz     short loc_1800BF641
0x1800bf635  and     al, 1
0x1800bf637  neg     al
0x1800bf639  sbb     ebx, ebx
0x1800bf63b  and     ebx, 0FFFFFFFCh
0x1800bf63e  add     ebx, 8
0x1800bf641  mov     rcx, rdi; hLibModule
0x1800bf644  call    cs:__imp_FreeLibrary
0x1800bf64b  nop     dword ptr [rax+rax+00h]
0x1800bf650  test    eax, eax
0x1800bf652  jnz     short loc_1800BF667
0x1800bf654  call    cs:__imp_GetLastError
0x1800bf65b  nop     dword ptr [rax+rax+00h]
0x1800bf660  mov     ecx, 7
0x1800bf665  int     29h; Win8: RtlFailFast(ecx)
0x1800bf667  xor     eax, eax
0x1800bf669  mov     dword ptr [rbp+var_28+0Ch], eax
0x1800bf66c  lea     rcx, [rsi+0D0h]; struct Windows::Rtl::IPoolAllocator *
0x1800bf673  mov     rdx, [r14+8]; wchar_t *
0x1800bf677  call    ?DuplicateNullTerminatedString@@YAPEA_WAEAVIPoolAllocator@Rtl@Windows@@PEB_W@Z; DuplicateNullTerminatedString(Windows::Rtl::IPoolAllocator &,wchar_t const *)
0x1800bf67c  mov     qword ptr [rbp+var_28], rax
0x1800bf680  test    rax, rax
0x1800bf683  jnz     loc_1800BF710
0x1800bf689  mov     rcx, [rbp+18h]; this
0x1800bf68d  mov     edi, 8007000Eh
0x1800bf692  mov     r9d, edi; char *
0x1800bf695  lea     r8, aOnecoreBaseSer_8; "onecore\\base\\servicing\\arbiter\\cdev"...
0x1800bf69c  mov     edx, 125h; void *
0x1800bf6a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf6a6  mov     [rbp+var_10], edi
0x1800bf6a9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf6b0  test    rcx, rcx
0x1800bf6b3  jz      short loc_1800BF6F4
0x1800bf6b5  lea     r9, aFailedToAddVel; "Failed to add velocity value to device "...
0x1800bf6bc  mov     ebx, 3
0x1800bf6c1  mov     r8d, ebx
0x1800bf6c4  xor     edx, edx
0x1800bf6c6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800bf6cb  lea     rax, [rbp+var_10]
0x1800bf6cf  mov     qword ptr [rbp+var_30], rax
0x1800bf6d3  lea     rcx, [rbp+var_30]
0x1800bf6d7  mov     qword ptr [rsp+60h+var_40], rcx; int
0x1800bf6dc  lea     r9, asc_1801CAFB4; ": {}"
0x1800bf6e3  mov     r8d, ebx
0x1800bf6e6  mov     dl, 1
0x1800bf6e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800bf6ef  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800bf6f4  mov     rcx, [rbp+18h]; this
0x1800bf6f8  mov     r9d, edi; char *
0x1800bf6fb  lea     r8, aOnecoreBaseSer_26; "onecore\\base\\servicing\\arbiter\\ccom"...
0x1800bf702  mov     edx, 0DA1h; void *
0x1800bf707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf70c  mov     eax, edi
0x1800bf70e  jmp     short loc_1800BF73E
0x1800bf710  mov     dword ptr [rbp+var_28+8], ebx
0x1800bf713  lea     rcx, [rsi+150h]
0x1800bf71a  mov     rdx, [rcx+8]
0x1800bf71e  cmp     rdx, [rcx+10h]
0x1800bf722  jz      short loc_1800BF733
0x1800bf724  movups  xmm0, [rbp+var_28]
0x1800bf728  movdqu  xmmword ptr [rdx], xmm0
0x1800bf72c  add     qword ptr [rcx+8], 10h
0x1800bf731  jmp     short loc_1800BF73C
0x1800bf733  lea     r8, [rbp+var_28]
0x1800bf737  call    ??$_Emplace_reallocate@UVelocity@CDeviceInfo@@@?$vector@UVelocity@CDeviceInfo@@V?$allocator@UVelocity@CDeviceInfo@@@std@@@std@@AEAAPEAUVelocity@CDeviceInfo@@QEAU23@$$QEAU23@@Z; std::vector<CDeviceInfo::Velocity>::_Emplace_reallocate<CDeviceInfo::Velocity>(CDeviceInfo::Velocity * const,CDeviceInfo::Velocity &&)
0x1800bf73c  xor     eax, eax
0x1800bf73e  mov     rcx, [rbp+var_8]
0x1800bf742  xor     rcx, rsp; StackCookie
0x1800bf745  call    __security_check_cookie
0x1800bf74a  lea     r11, [rsp+60h+var_s0]
0x1800bf74f  mov     rbx, [r11+28h]
0x1800bf753  mov     rsi, [r11+38h]
0x1800bf757  mov     rsp, r11
0x1800bf75a  pop     r14
0x1800bf75c  pop     rdi
0x1800bf75d  pop     rbp
0x1800bf75e  retn
```

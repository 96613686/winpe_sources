# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager(IUpdateReserveManager * *)

- ea: `0x180249828`
- end: `0x180249b02`
- name: `?GetReserveManager@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAPEAVIUpdateReserveManager@@@Z`
- size: `730`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *__hidden this, struct IUpdateReserveManager **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180248d70`

## callees

- `0x1800150c0`
- `0x180019bdc`
- `0x18008f280`
- `0x1800aa1d4`
- `0x1800eb920`
- `0x1800ef360`
- `0x1801197fc`
- `0x18011a5dc`
- `0x1802432a4`
- `0x180247bc0`
- `0x180247c2c`
- `0x180249828`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180249959`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180249959`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180249901`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180249901`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024996d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180249984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024996d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180249984`

## string_xrefs

- `0x1802498c6`: `ReserveManager.dll`
- `0x180249935`: `BufferedSil: Unable to find ReserveManager along side WCP`
- `0x180249952`: `GetUpdateReserveManager`
- `0x1802499b6`: `pfnGetUpdateReserveManager`
- `0x180249878`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager`
- `0x1802499ab`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager(
        Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *this,
        struct IUpdateReserveManager **a2)
{
  HMODULE *v5; // rsi
  struct IUpdateReserveManager **v6; // rbx
  struct IUpdateReserveManager *v7; // rax
  int Win32PathOfSiblingFile; // ebx
  __int128 *v9; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // r15
  signed int LastError; // eax
  __int64 v13; // rsi
  __int64 v14; // rcx
  int v15; // eax
  const wchar_t *v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int128 v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+40h] [rbp-40h]
  const char *v23; // [rsp+48h] [rbp-38h]
  int *v24; // [rsp+50h] [rbp-30h] BYREF
  int v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp-10h]

  LODWORD(v24) = 0;
  if ( !a2 )
  {
    v22 = 3741;
    *(_QWORD *)&v21 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    v23 = "Not-null check failed: ppReserveManager";
    *((_QWORD *)&v21 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v24,
             &v21);
  }
  v5 = (HMODULE *)((char *)this + 520);
  if ( *((_QWORD *)this + 65) )
  {
    v6 = (struct IUpdateReserveManager **)((char *)this + 528);
    v7 = (struct IUpdateReserveManager *)*((_QWORD *)this + 66);
    if ( v7 )
    {
      *a2 = v7;
      return 0;
    }
  }
  else
  {
    lpLibFileName = 0;
    v26 = 0;
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(&_ImageBase, L"ReserveManager.dll", &v26);
    if ( Win32PathOfSiblingFile < 0 )
    {
      v9 = &v26;
LABEL_8:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v9);
      return (unsigned int)Win32PathOfSiblingFile;
    }
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(v5, Library);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v26);
    v6 = (struct IUpdateReserveManager **)((char *)this + 528);
  }
  if ( !*v5 )
  {
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      (unsigned int)a2,
      (unsigned int)&Windows::WCP::Rtl::Facility_ComponentStore,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"BufferedSil: Unable to find ReserveManager along side WCP",
      0,
      0,
      (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *const)v21);
LABEL_33:
    *a2 = *v6;
    return 0;
  }
  ProcAddress = GetProcAddress(*v5, "GetUpdateReserveManager");
  if ( ProcAddress )
  {
    v13 = 0;
    v22 = 0;
    v21 = 0;
    if ( *((_BYTE *)this + 32) )
    {
      v14 = *((_QWORD *)this + 25);
      lpLibFileName = 0;
      v26 = 0;
      Win32PathOfSiblingFile = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, __int128 *))(*(_QWORD *)v14 + 176LL))(
                                 v14,
                                 0,
                                 (char *)this + 8,
                                 &v26);
      if ( Win32PathOfSiblingFile < 0 )
      {
LABEL_23:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v26);
        v9 = &v21;
        goto LABEL_8;
      }
      v15 = Windows::StringUtil::Rtl::ConvertNtFilePathToNullTerminatedWin32FilePath<Windows::Auto<_LUNICODE_STRING>>(&v26);
      if ( v15 < 0 )
      {
        Win32PathOfSiblingFile = v15;
        goto LABEL_23;
      }
      v13 = v22;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v26);
    }
    v6 = (struct IUpdateReserveManager **)((char *)this + 528);
    if ( !*((_QWORD *)this + 66) )
    {
      v16 = L"BufferedSilUnittests";
      if ( !Windows::ComponentStore::Rtl::Implementation::g_SequentialLockIdentifiers )
        v16 = L"BufferedSil";
      v17 = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, char *))ProcAddress)(
              v13,
              v16,
              0,
              (char *)this + 528);
      v25 = v17;
      if ( v17 == -2146498192 )
      {
        LODWORD(v24) = 0;
        Windows::WCP::Rtl::RtlAutoTrace<int>(v19, v18, v20, &v24);
      }
      else if ( v17 < 0 )
      {
        v24 = &v25;
        Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatHResultWrapper<long>>(v19, v18, v20, &v24);
      }
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
      goto LABEL_33;
    }
    goto LABEL_35;
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_16;
LABEL_35:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180249B01LL);
  }
  LastError = 14077;
LABEL_16:
  v22 = 3767;
  *(_QWORD *)&v21 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
  *((_QWORD *)&v21 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager";
  v23 = "pfnGetUpdateReserveManager";
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
           &v24,
           &v21,
           (unsigned int)LastError);
}

```

## disassembly

```asm
0x180249828  mov     [rsp-28h+arg_10], rbx
0x18024982d  push    rbp
0x18024982e  push    rsi
0x18024982f  push    rdi
0x180249830  push    r14
0x180249832  push    r15
0x180249834  mov     rbp, rsp
0x180249837  sub     rsp, 80h
0x18024983e  mov     rax, cs:__security_cookie
0x180249845  xor     rax, rsp
0x180249848  mov     [rbp+var_8], rax
0x18024984c  mov     dword ptr [rbp+var_30], 0
0x180249853  mov     r14, rdx
0x180249856  mov     rdi, rcx
0x180249859  test    rdx, rdx
0x18024985c  jnz     short loc_180249899
0x18024985e  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180249865  mov     [rbp+var_40], 0E9Dh
0x18024986d  mov     qword ptr [rbp+var_50], rcx
0x180249871  lea     rax, aNotNullCheckFa_85; "Not-null check failed: ppReserveManager"
0x180249878  lea     rcx, aWindowsRtlSyst_84; "Windows::Rtl::SystemImplementation::CBu"...
0x18024987f  mov     [rbp+var_38], rax
0x180249883  mov     qword ptr [rbp+var_50+8], rcx
0x180249887  lea     rdx, [rbp+var_50]
0x18024988b  lea     rcx, [rbp+var_30]
0x18024988f  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180249894  jmp     loc_180249AD3
0x180249899  lea     rsi, [rcx+208h]
0x1802498a0  cmp     qword ptr [rsi], 0
0x1802498a4  jz      short loc_1802498BD
0x1802498a6  lea     rbx, [rcx+210h]
0x1802498ad  mov     rax, [rbx]
0x1802498b0  test    rax, rax
0x1802498b3  jz      short loc_180249928
0x1802498b5  mov     [rdx], rax
0x1802498b8  jmp     loc_180249AD1
0x1802498bd  xorps   xmm0, xmm0
0x1802498c0  lea     r8, [rbp+var_20]
0x1802498c4  xor     eax, eax
0x1802498c6  lea     rdx, aReservemanager_0; "ReserveManager.dll"
0x1802498cd  lea     rcx, __ImageBase
0x1802498d4  mov     [rbp+lpLibFileName], rax
0x1802498d8  movups  [rbp+var_20], xmm0
0x1802498dc  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x1802498e1  mov     ebx, eax
0x1802498e3  test    eax, eax
0x1802498e5  jns     short loc_1802498F7
0x1802498e7  lea     rcx, [rbp+var_20]
0x1802498eb  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802498f0  mov     eax, ebx
0x1802498f2  jmp     loc_180249AD3
0x1802498f7  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1802498fb  xor     edx, edx; hFile
0x1802498fd  lea     r8d, [rdx+8]; dwFlags
0x180249901  call    cs:__imp_LoadLibraryExW
0x180249908  nop     dword ptr [rax+rax+00h]
0x18024990d  mov     rdx, rax
0x180249910  mov     rcx, rsi
0x180249913  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x180249918  lea     rcx, [rbp+var_20]
0x18024991c  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249921  lea     rbx, [rdi+210h]
0x180249928  mov     rcx, [rsi]; this
0x18024992b  test    rcx, rcx
0x18024992e  jnz     short loc_180249952
0x180249930  mov     [rsp+80h+var_58], rcx; unsigned __int64
0x180249935  lea     r9, aBufferedsilUna; "BufferedSil: Unable to find ReserveMana"...
0x18024993c  lea     r8, ?Facility_ComponentStore@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180249943  mov     [rsp+80h+var_60], rcx; char *
0x180249948  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x18024994d  jmp     loc_180249ACB
0x180249952  lea     rdx, aGetupdatereser_0; "GetUpdateReserveManager"
0x180249959  call    cs:__imp_GetProcAddress
0x180249960  nop     dword ptr [rax+rax+00h]
0x180249965  mov     r15, rax
0x180249968  test    rax, rax
0x18024996b  jnz     short loc_1802499E2
0x18024996d  call    cs:__imp_GetLastError
0x180249974  nop     dword ptr [rax+rax+00h]
0x180249979  test    eax, eax
0x18024997b  jnz     short loc_180249984
0x18024997d  mov     eax, 36FDh
0x180249982  jmp     short loc_180249998
0x180249984  call    cs:__imp_GetLastError
0x18024998b  nop     dword ptr [rax+rax+00h]
0x180249990  test    eax, eax
0x180249992  jz      loc_180249AF7
0x180249998  mov     [rbp+var_40], 0EB7h
0x1802499a0  lea     rcx, aOnecoreBaseWcp_29; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x1802499a7  mov     qword ptr [rbp+var_50], rcx
0x1802499ab  lea     rcx, aWindowsRtlSyst_84; "Windows::Rtl::SystemImplementation::CBu"...
0x1802499b2  mov     qword ptr [rbp+var_50+8], rcx
0x1802499b6  lea     rcx, aPfngetupdatere; "pfnGetUpdateReserveManager"
0x1802499bd  mov     [rbp+var_38], rcx
0x1802499c1  test    eax, eax
0x1802499c3  jle     short loc_1802499CD
0x1802499c5  movzx   eax, ax
0x1802499c8  or      eax, 80070000h
0x1802499cd  mov     r8d, eax
0x1802499d0  lea     rdx, [rbp+var_50]
0x1802499d4  lea     rcx, [rbp+var_30]
0x1802499d8  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802499dd  jmp     loc_180249AD3
0x1802499e2  xor     eax, eax
0x1802499e4  xor     esi, esi
0x1802499e6  xorps   xmm0, xmm0
0x1802499e9  mov     [rbp+var_40], rax
0x1802499ed  movups  [rbp+var_50], xmm0
0x1802499f1  cmp     [rdi+20h], al
0x1802499f4  jz      short loc_180249A56
0x1802499f6  mov     rcx, [rdi+0C8h]
0x1802499fd  lea     r8, [rdi+8]
0x180249a01  mov     [rbp+lpLibFileName], rax
0x180249a05  lea     r9, [rbp+var_20]
0x180249a09  movups  [rbp+var_20], xmm0
0x180249a0d  xor     edx, edx
0x180249a0f  mov     rax, [rcx]
0x180249a12  mov     rax, [rax+0B0h]
0x180249a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180249a1e  mov     ebx, eax
0x180249a20  test    eax, eax
0x180249a22  js      short loc_180249A37
0x180249a24  lea     rdx, [rbp+var_50]
0x180249a28  lea     rcx, [rbp+var_20]
0x180249a2c  call    ??$ConvertNtFilePathToNullTerminatedWin32FilePath@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@StringUtil@Windows@@YAJAEBV?$Auto@U_LUNICODE_STRING@@@2@PEAV32@@Z; Windows::StringUtil::Rtl::ConvertNtFilePathToNullTerminatedWin32FilePath<Windows::Auto<_LUNICODE_STRING>>(Windows::Auto<_LUNICODE_STRING> const &,Windows::Auto<_LUNICODE_STRING> *)
0x180249a31  test    eax, eax
0x180249a33  jns     short loc_180249A49
0x180249a35  mov     ebx, eax
0x180249a37  lea     rcx, [rbp+var_20]
0x180249a3b  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249a40  lea     rcx, [rbp+var_50]
0x180249a44  jmp     loc_1802498EB
0x180249a49  mov     rsi, [rbp+var_40]
0x180249a4d  lea     rcx, [rbp+var_20]
0x180249a51  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249a56  lea     rbx, [rdi+210h]
0x180249a5d  cmp     qword ptr [rbx], 0
0x180249a61  jnz     loc_180249AF7
0x180249a67  cmp     cs:?g_SequentialLockIdentifiers@Implementation@Rtl@ComponentStore@Windows@@3_NA, 0; bool Windows::ComponentStore::Rtl::Implementation::g_SequentialLockIdentifiers
0x180249a6e  lea     rax, aBufferedsil; "BufferedSil"
0x180249a75  lea     rdx, aBufferedsiluni; "BufferedSilUnittests"
0x180249a7c  mov     r9, rbx
0x180249a7f  cmovz   rdx, rax
0x180249a83  mov     rcx, rsi
0x180249a86  xor     r8d, r8d
0x180249a89  mov     rax, r15
0x180249a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180249a91  mov     [rbp+var_28], eax
0x180249a94  cmp     eax, 800F0970h
0x180249a99  jnz     short loc_180249AAD
0x180249a9b  lea     r9, [rbp+var_30]
0x180249a9f  mov     dword ptr [rbp+var_30], 0
0x180249aa6  call    ??$RtlAutoTrace@H@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEBH@Z; Windows::WCP::Rtl::RtlAutoTrace<int>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,int const &)
0x180249aab  jmp     short loc_180249AC2
0x180249aad  test    eax, eax
0x180249aaf  jns     short loc_180249AC2
0x180249ab1  lea     rax, [rbp+var_28]
0x180249ab5  lea     r9, [rbp+var_30]
0x180249ab9  mov     [rbp+var_30], rax
0x180249abd  call    ??$RtlAutoTrace@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@012@QEBDAEBU?$FormatHResultWrapper@J@012@@Z; Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatHResultWrapper<long>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180249ac2  lea     rcx, [rbp+var_50]
0x180249ac6  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180249acb  mov     rax, [rbx]
0x180249ace  mov     [r14], rax
0x180249ad1  xor     eax, eax
0x180249ad3  mov     rcx, [rbp+var_8]
0x180249ad7  xor     rcx, rsp; StackCookie
0x180249ada  call    __security_check_cookie
0x180249adf  mov     rbx, [rsp+80h+arg_10]
0x180249ae7  add     rsp, 80h
0x180249aee  pop     r15
0x180249af0  pop     r14
0x180249af2  pop     rdi
0x180249af3  pop     rsi
0x180249af4  pop     rbp
0x180249af5  retn
0x180249af7  mov     ecx, 0C00000E5h; int
0x180249afc  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

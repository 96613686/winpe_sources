# Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager(IUpdateReserveManager * *)

- ea: `0x1801589c8`
- end: `0x180158d5e`
- name: `?GetReserveManager@CBufferedFileSystemProvider@SystemImplementation@Rtl@Windows@@AEAAJPEAPEAVIUpdateReserveManager@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *__hidden this, struct IUpdateReserveManager **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180157db4`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x18000e098`
- `0x18003104c`
- `0x1800497c0`
- `0x18004a05c`
- `0x180050360`
- `0x180050fd0`
- `0x1801589c8`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158b47`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180158b18`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180158b18`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180158ab1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180158ab1`

## string_xrefs

- `0x180158a0d`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager`
- `0x180158b66`: `Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager`
- `0x180158b79`: `pfnGetUpdateReserveManager`
- `0x180158a7d`: `ReserveManager.dll`
- `0x180158b11`: `GetUpdateReserveManager`
- `0x180158af9`: `BufferedSil: Unable to find ReserveManager along side WCP`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager(
        Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider *this,
        struct IUpdateReserveManager **a2)
{
  struct IUpdateReserveManager **v5; // rdi
  struct IUpdateReserveManager *v6; // rax
  int Win32PathOfSiblingFile; // edi
  HMODULE Library; // rax
  HMODULE v9; // rcx
  FARPROC ProcAddress; // r15
  signed int LastError; // eax
  unsigned int v12; // ebx
  LPCWSTR v13; // r14
  const wchar_t *v14; // rdx
  int v15; // eax
  unsigned int v16; // edx
  char *v17; // r9
  __int128 v18; // [rsp+38h] [rbp-39h] BYREF
  LPCWSTR lpLibFileName; // [rsp+48h] [rbp-29h]
  int *v20; // [rsp+50h] [rbp-21h] BYREF
  __int128 v21; // [rsp+58h] [rbp-19h] BYREF
  __int64 v22; // [rsp+68h] [rbp-9h]
  const char *v23; // [rsp+70h] [rbp-1h]
  __int64 v24; // [rsp+78h] [rbp+7h]
  int v25; // [rsp+80h] [rbp+Fh] BYREF
  unsigned __int64 v26[2]; // [rsp+88h] [rbp+17h] BYREF
  int **v27; // [rsp+98h] [rbp+27h]

  v24 = -2;
  if ( !a2 )
  {
    *(_QWORD *)&v21 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
    *((_QWORD *)&v21 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager";
    v22 = 3741;
    v23 = "Not-null check failed: ppReserveManager";
    RtlReportErrorOrigination(&v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( *((_QWORD *)this + 65) )
  {
    v5 = (struct IUpdateReserveManager **)((char *)this + 528);
    v6 = (struct IUpdateReserveManager *)*((_QWORD *)this + 66);
    if ( v6 )
    {
      *a2 = v6;
      return 0;
    }
  }
  else
  {
    v18 = 0;
    lpLibFileName = 0;
    Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(0x180000000uLL, L"ReserveManager.dll", &v18);
    if ( Win32PathOfSiblingFile < 0 )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v18);
      return (unsigned int)Win32PathOfSiblingFile;
    }
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    if ( *((_QWORD *)this + 65) )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x180158D5DLL);
    }
    *((_QWORD *)this + 65) = Library;
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v18);
    v5 = (struct IUpdateReserveManager **)((char *)this + 528);
  }
  v9 = (HMODULE)*((_QWORD *)this + 65);
  if ( !v9 )
  {
    Windows::WCP::Rtl::RtlTraceFromParameterList(
      0,
      (unsigned int)a2,
      (unsigned int)&Windows::WCP::Rtl::Facility_ComponentStore,
      (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)"BufferedSil: Unable to find ReserveManager along side WCP",
      0,
      0,
      (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *const)v18);
LABEL_34:
    *a2 = *v5;
    return 0;
  }
  ProcAddress = GetProcAddress(v9, "GetUpdateReserveManager");
  if ( ProcAddress )
  {
    v18 = 0;
    lpLibFileName = 0;
    v13 = 0;
    if ( !*((_BYTE *)this + 32) )
      goto LABEL_25;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    Win32PathOfSiblingFile = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, unsigned __int64 *))(**((_QWORD **)this + 25) + 176LL))(
                               *((_QWORD *)this + 25),
                               0,
                               (char *)this + 8,
                               v26);
    if ( Win32PathOfSiblingFile >= 0 )
    {
      v21 = *(_OWORD *)v26;
      v22 = (__int64)v27;
      Win32PathOfSiblingFile = RtlConvertNtFilePathToWin32FilePath(&v21, &v18);
      if ( Win32PathOfSiblingFile >= 0 )
      {
        v13 = lpLibFileName;
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v26);
LABEL_25:
        v5 = (struct IUpdateReserveManager **)((char *)this + 528);
        if ( *((_QWORD *)this + 66) )
          goto LABEL_36;
        v14 = L"BufferedSilUnittests";
        if ( !Windows::ComponentStore::Rtl::Implementation::g_SequentialLockIdentifiers )
          v14 = L"BufferedSil";
        v15 = ((__int64 (__fastcall *)(LPCWSTR, const wchar_t *, _QWORD, char *))ProcAddress)(
                v13,
                v14,
                0,
                (char *)this + 528);
        v25 = v15;
        if ( v15 == -2146498192 )
        {
          LODWORD(v20) = 0;
          v26[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<int>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
          v17 = "Scavenge: Reserve Manager not available; continuing without reserves";
        }
        else
        {
          if ( v15 >= 0 )
          {
LABEL_33:
            Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v18);
            goto LABEL_34;
          }
          v20 = &v25;
          v26[1] = (unsigned __int64)`Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatHResultWrapper<long>>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
          v17 = "BufferedSil: Reserve Manager initialization failed with error {0}";
        }
        v27 = &v20;
        v26[0] = 0;
        Windows::WCP::Rtl::RtlTraceFromParameterList(
          0,
          v16,
          (unsigned int)&Windows::WCP::Rtl::Facility_ComponentStore,
          (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)v17,
          (const char *const)1,
          (unsigned __int64)v26,
          (struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *const)v18);
        goto LABEL_33;
      }
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(v26);
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(&v18);
    return (unsigned int)Win32PathOfSiblingFile;
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_17;
LABEL_36:
    INTERNAL_ERROR_ACTION(-1073741595);
    __debugbreak();
  }
  LastError = 14077;
LABEL_17:
  *(_QWORD *)&v21 = "onecore\\base\\wcp\\sil\\fs_buffered.cpp";
  *((_QWORD *)&v21 + 1) = "Windows::Rtl::SystemImplementation::CBufferedFileSystemProvider::GetReserveManager";
  v22 = 3767;
  v23 = "pfnGetUpdateReserveManager";
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v12 = ConvertHResultToNtStatus((unsigned int)LastError);
  RtlReportErrorOrigination(&v21, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v12);
  return v12;
}

```

## disassembly

```asm
0x1801589c8  mov     rax, rsp
0x1801589cb  push    rbp
0x1801589cc  push    rsi
0x1801589cd  push    rdi
0x1801589ce  push    r14
0x1801589d0  push    r15
0x1801589d2  lea     rbp, [rax-5Fh]
0x1801589d6  sub     rsp, 0A0h
0x1801589dd  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x1801589e5  mov     [rax+18h], rbx
0x1801589e9  mov     rax, cs:__security_cookie
0x1801589f0  xor     rax, rsp
0x1801589f3  mov     [rbp+57h+var_28], rax
0x1801589f7  mov     rsi, rdx
0x1801589fa  mov     rbx, rcx
0x1801589fd  test    rdx, rdx
0x180158a00  jnz     short loc_180158A4B
0x180158a02  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180158a09  mov     qword ptr [rbp+57h+var_70], rcx
0x180158a0d  lea     rcx, aWindowsRtlSyst_83; "Windows::Rtl::SystemImplementation::CBu"...
0x180158a14  mov     qword ptr [rbp+57h+var_70+8], rcx
0x180158a18  mov     [rbp+57h+var_60], 0E9Dh
0x180158a20  lea     rax, aNotNullCheckFa_69; "Not-null check failed: ppReserveManager"
0x180158a27  mov     [rbp+57h+var_58], rax
0x180158a2b  mov     r8d, 0C000000Dh
0x180158a31  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180158a38  lea     rcx, [rbp+57h+var_70]
0x180158a3c  call    RtlReportErrorOrigination
0x180158a41  mov     eax, 0C000000Dh
0x180158a46  jmp     loc_180158D24
0x180158a4b  cmp     qword ptr [rcx+208h], 0
0x180158a53  jz      short loc_180158A6C
0x180158a55  lea     rdi, [rcx+210h]
0x180158a5c  mov     rax, [rdi]
0x180158a5f  test    rax, rax
0x180158a62  jz      short loc_180158AE3
0x180158a64  mov     [rdx], rax
0x180158a67  jmp     loc_180158D22
0x180158a6c  xorps   xmm0, xmm0
0x180158a6f  xor     eax, eax
0x180158a71  movups  [rbp+57h+var_90], xmm0
0x180158a75  mov     [rbp+57h+lpLibFileName], rax
0x180158a79  lea     r8, [rbp+57h+var_90]
0x180158a7d  lea     rdx, aReservemanager_0; "ReserveManager.dll"
0x180158a84  lea     rcx, cs:180000000h
0x180158a8b  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x180158a90  mov     edi, eax
0x180158a92  test    eax, eax
0x180158a94  jns     short loc_180158AA7
0x180158a96  lea     rcx, [rbp+57h+var_90]
0x180158a9a  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158a9f  nop
0x180158aa0  mov     eax, edi
0x180158aa2  jmp     loc_180158D24
0x180158aa7  xor     edx, edx; hFile
0x180158aa9  lea     r8d, [rdx+8]; dwFlags
0x180158aad  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x180158ab1  call    cs:__imp_LoadLibraryExW
0x180158ab8  nop     dword ptr [rax+rax+00h]
0x180158abd  cmp     qword ptr [rbx+208h], 0
0x180158ac5  jnz     loc_180158D53
0x180158acb  mov     [rbx+208h], rax
0x180158ad2  lea     rcx, [rbp+57h+var_90]
0x180158ad6  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158adb  nop
0x180158adc  lea     rdi, [rbx+210h]
0x180158ae3  mov     rcx, [rbx+208h]; this
0x180158aea  test    rcx, rcx
0x180158aed  jnz     short loc_180158B11
0x180158aef  mov     [rsp+28h], rcx; unsigned __int64
0x180158af4  mov     [rsp+0C0h+var_A0], rcx; char *
0x180158af9  lea     r9, aBufferedsilUna; "BufferedSil: Unable to find ReserveMana"...
0x180158b00  lea     r8, ?Facility_ComponentStore@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180158b07  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180158b0c  jmp     loc_180158D1C
0x180158b11  lea     rdx, aGetupdatereser; "GetUpdateReserveManager"
0x180158b18  call    cs:__imp_GetProcAddress
0x180158b1f  nop     dword ptr [rax+rax+00h]
0x180158b24  mov     r15, rax
0x180158b27  test    rax, rax
0x180158b2a  jnz     loc_180158BB3
0x180158b30  call    cs:__imp_GetLastError
0x180158b37  nop     dword ptr [rax+rax+00h]
0x180158b3c  test    eax, eax
0x180158b3e  jnz     short loc_180158B47
0x180158b40  mov     eax, 36FDh
0x180158b45  jmp     short loc_180158B5B
0x180158b47  call    cs:__imp_GetLastError
0x180158b4e  nop     dword ptr [rax+rax+00h]
0x180158b53  test    eax, eax
0x180158b55  jz      loc_180158D48
0x180158b5b  lea     rcx, aOnecoreBaseWcp_26; "onecore\\base\\wcp\\sil\\fs_buffered.cp"...
0x180158b62  mov     qword ptr [rbp+57h+var_70], rcx
0x180158b66  lea     rcx, aWindowsRtlSyst_83; "Windows::Rtl::SystemImplementation::CBu"...
0x180158b6d  mov     qword ptr [rbp+57h+var_70+8], rcx
0x180158b71  mov     [rbp+57h+var_60], 0EB7h
0x180158b79  lea     rcx, aPfngetupdatere; "pfnGetUpdateReserveManager"
0x180158b80  mov     [rbp+57h+var_58], rcx
0x180158b84  test    eax, eax
0x180158b86  jle     short loc_180158B90
0x180158b88  movzx   eax, ax
0x180158b8b  or      eax, 80070000h
0x180158b90  mov     ecx, eax
0x180158b92  call    ConvertHResultToNtStatus
0x180158b97  mov     ebx, eax
0x180158b99  mov     r8d, eax
0x180158b9c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180158ba3  lea     rcx, [rbp+57h+var_70]
0x180158ba7  call    RtlReportErrorOrigination
0x180158bac  mov     eax, ebx
0x180158bae  jmp     loc_180158D24
0x180158bb3  xorps   xmm0, xmm0
0x180158bb6  xor     eax, eax
0x180158bb8  movups  [rbp+57h+var_90], xmm0
0x180158bbc  mov     [rbp+57h+lpLibFileName], rax
0x180158bc0  xor     r14d, r14d
0x180158bc3  cmp     [rbx+20h], al
0x180158bc6  jz      loc_180158C5F
0x180158bcc  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180158bd0  mov     [rbp+57h+var_30], rax
0x180158bd4  mov     rcx, [rbx+0C8h]
0x180158bdb  mov     rax, [rcx]
0x180158bde  lea     r8, [rbx+8]
0x180158be2  lea     r9, [rbp+57h+var_40]
0x180158be6  xor     edx, edx
0x180158be8  mov     rax, [rax+0B0h]
0x180158bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158bf4  mov     edi, eax
0x180158bf6  test    eax, eax
0x180158bf8  jns     short loc_180158C13
0x180158bfa  lea     rcx, [rbp+57h+var_40]
0x180158bfe  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158c03  nop
0x180158c04  lea     rcx, [rbp+57h+var_90]
0x180158c08  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158c0d  nop
0x180158c0e  jmp     loc_180158AA0
0x180158c13  movups  xmm0, xmmword ptr [rbp+57h+var_40]
0x180158c17  movups  [rbp+57h+var_70], xmm0
0x180158c1b  movsd   xmm1, [rbp+57h+var_30]
0x180158c20  movsd   [rbp+57h+var_60], xmm1
0x180158c25  lea     rdx, [rbp+57h+var_90]
0x180158c29  lea     rcx, [rbp+57h+var_70]
0x180158c2d  call    RtlConvertNtFilePathToWin32FilePath
0x180158c32  mov     edi, eax
0x180158c34  test    eax, eax
0x180158c36  jns     short loc_180158C51
0x180158c38  lea     rcx, [rbp+57h+var_40]
0x180158c3c  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158c41  nop
0x180158c42  lea     rcx, [rbp+57h+var_90]
0x180158c46  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158c4b  nop
0x180158c4c  jmp     loc_180158AA0
0x180158c51  mov     r14, [rbp+57h+lpLibFileName]
0x180158c55  lea     rcx, [rbp+57h+var_40]
0x180158c59  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158c5e  nop
0x180158c5f  lea     rdi, [rbx+210h]
0x180158c66  cmp     qword ptr [rdi], 0
0x180158c6a  jnz     loc_180158D48
0x180158c70  lea     rdx, aBufferedsiluni; "BufferedSilUnittests"
0x180158c77  lea     rax, aBufferedsil; "BufferedSil"
0x180158c7e  cmp     cs:?g_SequentialLockIdentifiers@Implementation@Rtl@ComponentStore@Windows@@3_NA, 0; bool Windows::ComponentStore::Rtl::Implementation::g_SequentialLockIdentifiers
0x180158c85  cmovz   rdx, rax
0x180158c89  mov     r9, rdi
0x180158c8c  xor     r8d, r8d
0x180158c8f  mov     rcx, r14
0x180158c92  mov     rax, r15
0x180158c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158c9a  mov     [rbp+57h+var_48], eax
0x180158c9d  cmp     eax, 800F0970h
0x180158ca2  jnz     short loc_180158CC3
0x180158ca4  mov     dword ptr [rbp+57h+var_78], 0
0x180158cab  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@H@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBH@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<int>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,int const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180158cb2  mov     [rbp+57h+var_40+8], rax
0x180158cb6  lea     rax, [rbp+57h+var_78]
0x180158cba  lea     r9, aScavengeReserv; "Scavenge: Reserve Manager not available"...
0x180158cc1  jmp     short loc_180158CE5
0x180158cc3  test    eax, eax
0x180158cc5  jns     short loc_180158D12
0x180158cc7  lea     rax, [rbp+57h+var_48]
0x180158ccb  mov     [rbp+57h+var_78], rax
0x180158ccf  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlAutoTrace@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Rtl@WCP@Windows@@YAXKPEAU_RTL_TRACING_FACILITY@234@QEBDAEBU?$FormatHResultWrapper@J@234@@Z@SA@PEAUIRtlFormattedOutputStream@24@PEBX@Z; `Windows::WCP::Rtl::RtlAutoTrace<Windows::WCP::Rtl::FormatHResultWrapper<long>>(ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x180158cd6  mov     [rbp+57h+var_40+8], rax
0x180158cda  lea     rax, [rbp+57h+var_78]
0x180158cde  lea     r9, aBufferedsilRes; "BufferedSil: Reserve Manager initializa"...
0x180158ce5  mov     [rbp+57h+var_30], rax
0x180158ce9  lea     rax, [rbp+57h+var_40]
0x180158ced  mov     [rsp+28h], rax; unsigned __int64
0x180158cf2  mov     [rsp+0C0h+var_A0], 1; char *
0x180158cfb  mov     [rbp+57h+var_40], 0
0x180158d03  lea     r8, ?Facility_ComponentStore@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; unsigned int
0x180158d0a  xor     ecx, ecx; this
0x180158d0c  call    ?RtlTraceFromParameterList@Rtl@WCP@Windows@@YAXKKPEAU_RTL_TRACING_FACILITY@123@QEBD_KQEAU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlTraceFromParameterList(ulong,ulong,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER * const)
0x180158d11  nop
0x180158d12  lea     rcx, [rbp+57h+var_90]
0x180158d16  call    ??1?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAA@XZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::~AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>(void)
0x180158d1b  nop
0x180158d1c  mov     rax, [rdi]
0x180158d1f  mov     [rsi], rax
0x180158d22  xor     eax, eax
0x180158d24  mov     rcx, [rbp+57h+var_28]
0x180158d28  xor     rcx, rsp; StackCookie
0x180158d2b  call    __security_check_cookie
0x180158d30  mov     rbx, [rsp+0C0h+arg_10]
0x180158d38  add     rsp, 0A0h
0x180158d3f  pop     r15
0x180158d41  pop     r14
0x180158d43  pop     rdi
0x180158d44  pop     rsi
0x180158d45  pop     rbp
0x180158d46  retn
0x180158d48  mov     ecx, 0C00000E5h; int
0x180158d4d  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180158d52  int     3; Trap to Debugger
0x180158d53  mov     ecx, 0C00000E5h; int
0x180158d58  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

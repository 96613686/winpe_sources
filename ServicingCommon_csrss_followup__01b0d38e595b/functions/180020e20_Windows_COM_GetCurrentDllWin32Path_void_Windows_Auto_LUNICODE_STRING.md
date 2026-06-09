# Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x180020e20`
- end: `0x1800211e7`
- name: `?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `967`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180021454`
- `0x18007b7c4`

## callees

- `0x180004a8c`
- `0x180017510`
- `0x180017f34`
- `0x180019ea0`
- `0x180020e20`
- `0x1800211f0`
- `0x180021794`
- `0x1800282d0`
- `0x18002d2b0`
- `0x180067710`
- `0x18006b3e0`
- `0x18008bc50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020eb1`
- `KERNEL32!GetLastError` at `0x180020ec8`
- `KERNEL32!GetLastError` at `0x18002112f`
- `KERNEL32!GetLastError` at `0x180021198`
- `KERNEL32!GetLastError` at `0x180020eb1`
- `KERNEL32!GetLastError` at `0x180020ec8`
- `KERNEL32!GetLastError` at `0x18002112f`
- `KERNEL32!GetLastError` at `0x180021198`
- `KERNEL32!GetModuleHandleExW` at `0x180020ea1`
- `KERNEL32!GetModuleHandleExW` at `0x180020ea1`
- `KERNEL32!GetModuleFileNameW` at `0x180020fbf`
- `KERNEL32!GetModuleFileNameW` at `0x180020fbf`
- `ntdll!RtlRaiseStatus` at `0x1800211ad`
- `ntdll!RtlRaiseStatus` at `0x1800211ad`

## string_xrefs

- `0x180020e6c`: `Windows::COM::GetCurrentDllWin32Path`
- `0x180020eef`: `Windows::COM::GetCurrentDllWin32Path`
- `0x180021157`: `Windows::COM::GetCurrentDllWin32Path`
- `0x180020e52`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x180020ee4`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18002114c`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x180020e65`: `Not-null check failed: DirectoryOut`

## pseudocode

```c
__int64 __fastcall Windows::COM::GetCurrentDllWin32Path(LPCWSTR lpModuleName, __int128 *a2)
{
  signed int LastError; // eax
  int i; // eax
  int v6; // eax
  unsigned __int64 v7; // rdi
  DWORD v8; // ebx
  unsigned __int64 v9; // rax
  DWORD ModuleFileNameW; // eax
  int v11; // ebx
  __int128 v12; // xmm2
  LPWSTR v13; // xmm3_8
  __int128 v14; // xmm2
  WCHAR *v15; // xmm3_8
  LPWSTR v16; // xmm1_8
  __int128 v17; // xmm0
  signed int v18; // eax
  unsigned __int64 v19; // [rsp+40h] [rbp-39h] BYREF
  int v20; // [rsp+4Ch] [rbp-2Dh]
  __int128 v21; // [rsp+50h] [rbp-29h] BYREF
  LPWSTR lpFilename; // [rsp+60h] [rbp-19h]
  __int128 v23; // [rsp+68h] [rbp-11h] BYREF
  __int64 v24; // [rsp+78h] [rbp-1h]
  const char *v25; // [rsp+80h] [rbp+7h]
  __int128 v26; // [rsp+88h] [rbp+Fh] BYREF
  WCHAR *v27; // [rsp+98h] [rbp+1Fh]
  HMODULE phModule; // [rsp+A0h] [rbp+27h] BYREF
  int v29; // [rsp+A8h] [rbp+2Fh] BYREF

  v29 = 0;
  if ( !a2 )
  {
    v24 = 23;
    *(_QWORD *)&v23 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
    v25 = "Not-null check failed: DirectoryOut";
    *((_QWORD *)&v23 + 1) = "Windows::COM::GetCurrentDllWin32Path";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v29,
             &v23);
  }
  phModule = 0;
  if ( !GetModuleHandleExW(6u, lpModuleName, &phModule) )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_7:
      v24 = 29;
      *(_QWORD *)&v23 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
      *((_QWORD *)&v23 + 1) = "Windows::COM::GetCurrentDllWin32Path";
      v25 = "GetLastError";
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
               &v29,
               &v23,
               (unsigned int)LastError);
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_7;
LABEL_40:
    RtlRaiseStatus(-1073741595);
  }
  v21 = 0;
  lpFilename = 0;
  for ( i = RtlAllocateLUnicodeString(260, &v21); ; i = RtlReallocateLUnicodeString(0, v7 + 260, &v21) )
  {
    if ( i < 0 )
      goto LABEL_12;
    v7 = *((_QWORD *)&v21 + 1);
    v20 = 0;
    v8 = 0;
    v9 = (*((_QWORD *)&v21 + 1) >> 1) - 2LL;
    if ( v9 > 0xFFFFFFFF )
    {
      v20 = -2147024362;
      BYTE4(v19) = 22;
    }
    else
    {
      v8 = (*((_QWORD *)&v21 + 1) >> 1) - 2;
      if ( v9 == (unsigned int)v9 )
      {
        v20 = 0;
        BYTE4(v19) = 0;
      }
      else
      {
        v20 = -2147467259;
        BYTE4(v19) = 5;
      }
    }
    *(_WORD *)((char *)&v19 + 5) = *(_WORD *)((char *)&v20 + 1);
    HIBYTE(v19) = HIBYTE(v20);
    if ( (v19 & 0x8000000000000000uLL) != 0LL )
    {
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
      return HIDWORD(v19);
    }
    ModuleFileNameW = GetModuleFileNameW(phModule, lpFilename, v8);
    if ( !ModuleFileNameW )
    {
      if ( GetLastError() )
      {
        v18 = GetLastError();
        if ( !v18 )
          goto LABEL_40;
      }
      else
      {
        v18 = 14077;
      }
      v24 = 44;
      *(_QWORD *)&v23 = "onecore\\base\\wcp\\rtllib\\win32lib\\dllpath_library.cpp";
      *((_QWORD *)&v23 + 1) = "Windows::COM::GetCurrentDllWin32Path";
      v25 = "GetLastError";
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v6 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v29,
             &v23,
             (unsigned int)v18);
      goto LABEL_37;
    }
    if ( ModuleFileNameW < v8 )
      break;
    if ( v7 + 260 < v7 )
    {
      v11 = -2147024362;
      goto LABEL_38;
    }
  }
  v19 = 0;
  i = BUCL::Rtl::Multiply<unsigned __int64>(ModuleFileNameW, 2, &v19);
  if ( i >= 0 )
  {
    *(_QWORD *)&v21 = v19;
    if ( v19 > 0x208 && wcsnicmp(L"\\\\?\\", lpFilename, 4u) )
    {
      v27 = 0;
      v26 = 0;
      v11 = Windows::COM::FilePathCombine(L"\\\\?\\", &v21, &v26);
      if ( v11 < 0 )
      {
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v26);
        goto LABEL_38;
      }
      v12 = v21;
      v13 = lpFilename;
      v21 = v26;
      v26 = v12;
      lpFilename = v27;
      v27 = v13;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v26);
    }
    v27 = 0;
    v24 = 0;
    v26 = 0;
    v23 = 0;
    i = RtlSplitLUnicodeString(2, (unsigned int)&v21, 0, 0, 92, (__int64)&v26, (__int64)&v23);
    if ( i >= 0 )
    {
      v14 = *a2;
      v15 = (WCHAR *)*((_QWORD *)a2 + 2);
      v16 = lpFilename;
      *(_QWORD *)&v21 = v26;
      v17 = v21;
      v21 = v14;
      *a2 = v17;
      *((_QWORD *)a2 + 2) = v16;
      lpFilename = v15;
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
      return 0;
    }
  }
LABEL_12:
  v6 = ConvertNtStatusToHResult((unsigned int)i);
LABEL_37:
  v11 = v6;
LABEL_38:
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v21);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180020e20  mov     [rsp-8+arg_10], rbx
0x180020e25  push    rbp
0x180020e26  push    rdi
0x180020e27  push    r14
0x180020e29  lea     rbp, [rsp-47h]
0x180020e2e  sub     rsp, 0C0h
0x180020e35  mov     rax, cs:__security_cookie
0x180020e3c  xor     rax, rsp
0x180020e3f  mov     [rbp+57h+var_20], rax
0x180020e43  mov     [rbp+57h+var_28], 0
0x180020e4a  mov     r14, rdx
0x180020e4d  test    rdx, rdx
0x180020e50  jnz     short loc_180020E8D
0x180020e52  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x180020e59  mov     [rbp+57h+var_58], 17h
0x180020e61  mov     qword ptr [rbp+57h+var_68], rcx
0x180020e65  lea     rax, aNotNullCheckFa_14; "Not-null check failed: DirectoryOut"
0x180020e6c  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x180020e73  mov     [rbp+57h+var_50], rax
0x180020e77  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180020e7b  lea     rdx, [rbp+57h+var_68]
0x180020e7f  lea     rcx, [rbp+57h+var_28]
0x180020e83  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180020e88  jmp     loc_1800211C6
0x180020e8d  mov     rdx, rcx; lpModuleName
0x180020e90  mov     [rbp+57h+phModule], 0
0x180020e98  mov     ecx, 6; dwFlags
0x180020e9d  lea     r8, [rbp+57h+phModule]; phModule
0x180020ea1  call    cs:__imp_GetModuleHandleExW
0x180020ea8  nop     dword ptr [rax+rax+00h]
0x180020ead  test    eax, eax
0x180020eaf  jnz     short loc_180020F26
0x180020eb1  call    cs:__imp_GetLastError
0x180020eb8  nop     dword ptr [rax+rax+00h]
0x180020ebd  test    eax, eax
0x180020ebf  jnz     short loc_180020EC8
0x180020ec1  mov     eax, 36FDh
0x180020ec6  jmp     short loc_180020EDC
0x180020ec8  call    cs:__imp_GetLastError
0x180020ecf  nop     dword ptr [rax+rax+00h]
0x180020ed4  test    eax, eax
0x180020ed6  jz      loc_1800211A8
0x180020edc  mov     [rbp+57h+var_58], 1Dh
0x180020ee4  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x180020eeb  mov     qword ptr [rbp+57h+var_68], rcx
0x180020eef  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x180020ef6  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180020efa  lea     rcx, aGetlasterror; "GetLastError"
0x180020f01  mov     [rbp+57h+var_50], rcx
0x180020f05  test    eax, eax
0x180020f07  jle     short loc_180020F11
0x180020f09  movzx   eax, ax
0x180020f0c  or      eax, 80070000h
0x180020f11  mov     r8d, eax
0x180020f14  lea     rdx, [rbp+57h+var_68]
0x180020f18  lea     rcx, [rbp+57h+var_28]
0x180020f1c  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180020f21  jmp     loc_1800211C6
0x180020f26  xorps   xmm0, xmm0
0x180020f29  lea     rdx, [rbp+57h+var_80]
0x180020f2d  xor     eax, eax
0x180020f2f  mov     ecx, 104h
0x180020f34  movups  [rbp+57h+var_80], xmm0
0x180020f38  mov     [rbp+57h+lpFilename], rax
0x180020f3c  call    RtlAllocateLUnicodeString
0x180020f41  test    eax, eax
0x180020f43  jns     short loc_180020F51
0x180020f45  mov     ecx, eax
0x180020f47  call    ConvertNtStatusToHResult
0x180020f4c  jmp     loc_180021189
0x180020f51  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x180020f55  xor     ecx, ecx
0x180020f57  mov     rax, rdi
0x180020f5a  mov     [rbp+57h+var_84], ecx
0x180020f5d  shr     rax, 1
0x180020f60  xor     ebx, ebx
0x180020f62  add     rax, 0FFFFFFFFFFFFFFFEh
0x180020f66  mov     ecx, 0FFFFFFFFh
0x180020f6b  cmp     rax, rcx
0x180020f6e  ja      short loc_180020F91
0x180020f70  mov     ebx, eax
0x180020f72  cmp     rax, rbx
0x180020f75  jz      short loc_180020F84
0x180020f77  mov     [rbp+57h+var_84], 80004005h
0x180020f7e  mov     byte ptr [rbp+57h+var_90+4], 5
0x180020f82  jmp     short loc_180020F9C
0x180020f84  mov     [rbp+57h+var_84], 0
0x180020f8b  mov     byte ptr [rbp+57h+var_90+4], 0
0x180020f8f  jmp     short loc_180020F9C
0x180020f91  mov     [rbp+57h+var_84], 80070216h
0x180020f98  mov     byte ptr [rbp+57h+var_90+4], 16h
0x180020f9c  movzx   eax, word ptr [rbp+57h+var_84+1]
0x180020fa0  mov     word ptr [rbp+57h+var_90+5], ax
0x180020fa4  mov     al, byte ptr [rbp+57h+var_84+3]
0x180020fa7  mov     byte ptr [rbp+57h+var_90+7], al
0x180020faa  cmp     dword ptr [rbp+57h+var_90+4], 0
0x180020fae  jl      loc_1800211BA
0x180020fb4  mov     rdx, [rbp+57h+lpFilename]; lpFilename
0x180020fb8  mov     r8d, ebx; nSize
0x180020fbb  mov     rcx, [rbp+57h+phModule]; hModule
0x180020fbf  call    cs:__imp_GetModuleFileNameW
0x180020fc6  nop     dword ptr [rax+rax+00h]
0x180020fcb  test    eax, eax
0x180020fcd  jz      loc_18002112F
0x180020fd3  cmp     eax, ebx
0x180020fd5  jb      short loc_180020FFD
0x180020fd7  lea     rdx, [rdi+104h]
0x180020fde  cmp     rdx, rdi
0x180020fe1  jb      short loc_180020FF3
0x180020fe3  lea     r8, [rbp+57h+var_80]
0x180020fe7  xor     ecx, ecx
0x180020fe9  call    RtlReallocateLUnicodeString
0x180020fee  jmp     loc_180020F41
0x180020ff3  mov     ebx, 80070216h
0x180020ff8  jmp     loc_18002118B
0x180020ffd  mov     edi, 2
0x180021002  mov     ecx, eax
0x180021004  mov     edx, edi
0x180021006  mov     qword ptr [rbp-39h], 0
0x18002100e  lea     r8, [rbp+57h+var_90]
0x180021012  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180021017  test    eax, eax
0x180021019  js      loc_180020F45
0x18002101f  mov     rax, [rbp+57h+var_90]
0x180021023  mov     qword ptr [rbp+57h+var_80], rax
0x180021027  cmp     rax, 208h
0x18002102d  jbe     short loc_1800210A5
0x18002102f  mov     rdx, [rbp+57h+lpFilename]; String2
0x180021033  lea     r8d, [rdi+2]; MaxCount
0x180021037  lea     rcx, String1; "\\\\?\\"
0x18002103e  call    _wcsnicmp
0x180021043  test    eax, eax
0x180021045  jz      short loc_1800210A5
0x180021047  xorps   xmm0, xmm0
0x18002104a  lea     r8, [rbp+57h+var_48]
0x18002104e  xor     eax, eax
0x180021050  lea     rdx, [rbp+57h+var_80]
0x180021054  lea     rcx, String1; "\\\\?\\"
0x18002105b  mov     [rbp+57h+var_38], rax
0x18002105f  movups  [rbp+57h+var_48], xmm0
0x180021063  call    ?FilePathCombine@COM@Windows@@YAJPEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::FilePathCombine(wchar_t const *,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x180021068  lea     rcx, [rbp+57h+var_48]
0x18002106c  mov     ebx, eax
0x18002106e  test    eax, eax
0x180021070  jns     short loc_18002107C
0x180021072  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180021077  jmp     loc_18002118B
0x18002107c  movups  xmm2, [rbp+57h+var_80]
0x180021080  movups  xmm0, [rbp+57h+var_48]
0x180021084  movsd   xmm3, [rbp+57h+lpFilename]
0x180021089  movsd   xmm1, [rbp+57h+var_38]
0x18002108e  movups  [rbp+57h+var_80], xmm0
0x180021092  movups  [rbp+57h+var_48], xmm2
0x180021096  movsd   [rbp+57h+lpFilename], xmm1
0x18002109b  movsd   [rbp+57h+var_38], xmm3
0x1800210a0  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800210a5  xor     eax, eax
0x1800210a7  lea     rdx, [rbp+57h+var_80]
0x1800210ab  mov     [rbp+57h+var_38], rax
0x1800210af  xorps   xmm0, xmm0
0x1800210b2  mov     [rbp+57h+var_58], rax
0x1800210b6  xorps   xmm1, xmm1
0x1800210b9  lea     rax, [rbp+57h+var_68]
0x1800210bd  xor     r9d, r9d
0x1800210c0  mov     [rsp+0D0h+var_A0], rax
0x1800210c5  xor     r8d, r8d
0x1800210c8  lea     rax, [rbp+57h+var_48]
0x1800210cc  mov     ecx, edi
0x1800210ce  mov     [rsp+0D0h+var_A8], rax
0x1800210d3  mov     [rsp+0D0h+var_B0], 5Ch ; '\'
0x1800210dc  movups  [rbp+57h+var_48], xmm0
0x1800210e0  movups  [rbp+57h+var_68], xmm1
0x1800210e4  call    RtlSplitLUnicodeString
0x1800210e9  test    eax, eax
0x1800210eb  js      loc_180020F45
0x1800210f1  movups  xmm2, xmmword ptr [r14]
0x1800210f5  lea     rcx, [rbp+57h+var_80]
0x1800210f9  mov     rax, qword ptr [rbp+57h+var_48]
0x1800210fd  movsd   xmm3, qword ptr [r14+10h]
0x180021103  movsd   xmm1, [rbp+57h+lpFilename]
0x180021108  mov     qword ptr [rbp+57h+var_80], rax
0x18002110c  movups  xmm0, [rbp+57h+var_80]
0x180021110  movups  [rbp+57h+var_80], xmm2
0x180021114  movups  xmmword ptr [r14], xmm0
0x180021118  movsd   qword ptr [r14+10h], xmm1
0x18002111e  movsd   [rbp+57h+lpFilename], xmm3
0x180021123  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180021128  xor     eax, eax
0x18002112a  jmp     loc_1800211C6
0x18002112f  call    cs:__imp_GetLastError
0x180021136  nop     dword ptr [rax+rax+00h]
0x18002113b  test    eax, eax
0x18002113d  jnz     short loc_180021198
0x18002113f  mov     eax, 36FDh
0x180021144  mov     [rbp+57h+var_58], 2Ch ; ','
0x18002114c  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x180021153  mov     qword ptr [rbp+57h+var_68], rcx
0x180021157  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18002115e  mov     qword ptr [rbp+57h+var_68+8], rcx
0x180021162  lea     rcx, aGetlasterror; "GetLastError"
0x180021169  mov     [rbp+57h+var_50], rcx
0x18002116d  test    eax, eax
0x18002116f  jle     short loc_180021179
0x180021171  movzx   eax, ax
0x180021174  or      eax, 80070000h
0x180021179  mov     r8d, eax
0x18002117c  lea     rdx, [rbp+57h+var_68]
0x180021180  lea     rcx, [rbp+57h+var_28]
0x180021184  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180021189  mov     ebx, eax
0x18002118b  lea     rcx, [rbp+57h+var_80]
0x18002118f  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180021194  mov     eax, ebx
0x180021196  jmp     short loc_1800211C6
0x180021198  call    cs:__imp_GetLastError
0x18002119f  nop     dword ptr [rax+rax+00h]
0x1800211a4  test    eax, eax
0x1800211a6  jnz     short loc_180021144
0x1800211a8  mov     ecx, 0C00000E5h; Status
0x1800211ad  call    cs:__imp_RtlRaiseStatus
0x1800211b4  nop     dword ptr [rax+rax+00h]
0x1800211b9  int     3; Trap to Debugger
0x1800211ba  lea     rcx, [rbp+57h+var_80]
0x1800211be  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800211c3  mov     eax, dword ptr [rbp+57h+var_90+4]
0x1800211c6  mov     rcx, [rbp+57h+var_20]
0x1800211ca  xor     rcx, rsp; StackCookie
0x1800211cd  call    __security_check_cookie
0x1800211d2  mov     rbx, [rsp+0D0h+arg_10]
0x1800211da  add     rsp, 0C0h
0x1800211e1  pop     r14
0x1800211e3  pop     rdi
0x1800211e4  pop     rbp
0x1800211e5  retn
```

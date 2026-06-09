# Windows::COM::GetCurrentDllWin32Path(void *,Windows::Auto<_LUNICODE_STRING> *)

- ea: `0x18008ce80`
- end: `0x18008d242`
- name: `?GetCurrentDllWin32Path@COM@Windows@@YAJPEAXPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z`
- size: `962`
- prototype: `__int64 __fastcall(LPCWSTR lpModuleName)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18007bb54`
- `0x18008d248`

## callees

- `0x180002564`
- `0x180002c00`
- `0x180004500`
- `0x18000e1b4`
- `0x18001f51c`
- `0x18001f604`
- `0x18001fd10`
- `0x1800243c0`
- `0x1800293a0`
- `0x180067060`
- `0x18006b1e0`
- `0x18008cd70`
- `0x18008ce80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008cf11`
- `KERNEL32!GetLastError` at `0x18008cf28`
- `KERNEL32!GetLastError` at `0x18008d18f`
- `KERNEL32!GetLastError` at `0x18008d1f8`
- `KERNEL32!GetLastError` at `0x18008cf11`
- `KERNEL32!GetLastError` at `0x18008cf28`
- `KERNEL32!GetLastError` at `0x18008d18f`
- `KERNEL32!GetLastError` at `0x18008d1f8`
- `KERNEL32!GetModuleHandleExW` at `0x18008cf01`
- `KERNEL32!GetModuleHandleExW` at `0x18008cf01`
- `KERNEL32!GetModuleFileNameW` at `0x18008d01f`
- `KERNEL32!GetModuleFileNameW` at `0x18008d01f`

## string_xrefs

- `0x18008ceb2`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18008cf44`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18008d1ac`: `onecore\base\wcp\rtllib\win32lib\dllpath_library.cpp`
- `0x18008cec5`: `Not-null check failed: DirectoryOut`
- `0x18008cecc`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18008cf4f`: `Windows::COM::GetCurrentDllWin32Path`
- `0x18008d1b7`: `Windows::COM::GetCurrentDllWin32Path`

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
LABEL_42:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18008D241LL);
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
          goto LABEL_42;
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
0x18008ce80  mov     [rsp-8+arg_10], rbx
0x18008ce85  push    rbp
0x18008ce86  push    rdi
0x18008ce87  push    r14
0x18008ce89  lea     rbp, [rsp-47h]
0x18008ce8e  sub     rsp, 0C0h
0x18008ce95  mov     rax, cs:__security_cookie
0x18008ce9c  xor     rax, rsp
0x18008ce9f  mov     [rbp+57h+var_20], rax
0x18008cea3  mov     [rbp+57h+var_28], 0
0x18008ceaa  mov     r14, rdx
0x18008cead  test    rdx, rdx
0x18008ceb0  jnz     short loc_18008CEED
0x18008ceb2  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18008ceb9  mov     [rbp+57h+var_58], 17h
0x18008cec1  mov     qword ptr [rbp+57h+var_68], rcx
0x18008cec5  lea     rax, aNotNullCheckFa_14; "Not-null check failed: DirectoryOut"
0x18008cecc  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18008ced3  mov     [rbp+57h+var_50], rax
0x18008ced7  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18008cedb  lea     rdx, [rbp+57h+var_68]
0x18008cedf  lea     rcx, [rbp+57h+var_28]
0x18008cee3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18008cee8  jmp     loc_18008D216
0x18008ceed  mov     rdx, rcx; lpModuleName
0x18008cef0  mov     [rbp+57h+phModule], 0
0x18008cef8  mov     ecx, 6; dwFlags
0x18008cefd  lea     r8, [rbp+57h+phModule]; phModule
0x18008cf01  call    cs:__imp_GetModuleHandleExW
0x18008cf08  nop     dword ptr [rax+rax+00h]
0x18008cf0d  test    eax, eax
0x18008cf0f  jnz     short loc_18008CF86
0x18008cf11  call    cs:__imp_GetLastError
0x18008cf18  nop     dword ptr [rax+rax+00h]
0x18008cf1d  test    eax, eax
0x18008cf1f  jnz     short loc_18008CF28
0x18008cf21  mov     eax, 36FDh
0x18008cf26  jmp     short loc_18008CF3C
0x18008cf28  call    cs:__imp_GetLastError
0x18008cf2f  nop     dword ptr [rax+rax+00h]
0x18008cf34  test    eax, eax
0x18008cf36  jz      loc_18008D237
0x18008cf3c  mov     [rbp+57h+var_58], 1Dh
0x18008cf44  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18008cf4b  mov     qword ptr [rbp+57h+var_68], rcx
0x18008cf4f  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18008cf56  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18008cf5a  lea     rcx, aGetlasterror; "GetLastError"
0x18008cf61  mov     [rbp+57h+var_50], rcx
0x18008cf65  test    eax, eax
0x18008cf67  jle     short loc_18008CF71
0x18008cf69  movzx   eax, ax
0x18008cf6c  or      eax, 80070000h
0x18008cf71  mov     r8d, eax
0x18008cf74  lea     rdx, [rbp+57h+var_68]
0x18008cf78  lea     rcx, [rbp+57h+var_28]
0x18008cf7c  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008cf81  jmp     loc_18008D216
0x18008cf86  xorps   xmm0, xmm0
0x18008cf89  lea     rdx, [rbp+57h+var_80]
0x18008cf8d  xor     eax, eax
0x18008cf8f  mov     ecx, 104h
0x18008cf94  movups  [rbp+57h+var_80], xmm0
0x18008cf98  mov     [rbp+57h+lpFilename], rax
0x18008cf9c  call    RtlAllocateLUnicodeString
0x18008cfa1  test    eax, eax
0x18008cfa3  jns     short loc_18008CFB1
0x18008cfa5  mov     ecx, eax
0x18008cfa7  call    ConvertNtStatusToHResult
0x18008cfac  jmp     loc_18008D1E9
0x18008cfb1  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x18008cfb5  xor     ecx, ecx
0x18008cfb7  mov     rax, rdi
0x18008cfba  mov     [rbp+57h+var_84], ecx
0x18008cfbd  shr     rax, 1
0x18008cfc0  xor     ebx, ebx
0x18008cfc2  add     rax, 0FFFFFFFFFFFFFFFEh
0x18008cfc6  mov     ecx, 0FFFFFFFFh
0x18008cfcb  cmp     rax, rcx
0x18008cfce  ja      short loc_18008CFF1
0x18008cfd0  mov     ebx, eax
0x18008cfd2  cmp     rax, rbx
0x18008cfd5  jz      short loc_18008CFE4
0x18008cfd7  mov     [rbp+57h+var_84], 80004005h
0x18008cfde  mov     byte ptr [rbp+57h+var_90+4], 5
0x18008cfe2  jmp     short loc_18008CFFC
0x18008cfe4  mov     [rbp+57h+var_84], 0
0x18008cfeb  mov     byte ptr [rbp+57h+var_90+4], 0
0x18008cfef  jmp     short loc_18008CFFC
0x18008cff1  mov     [rbp+57h+var_84], 80070216h
0x18008cff8  mov     byte ptr [rbp+57h+var_90+4], 16h
0x18008cffc  movzx   eax, word ptr [rbp+57h+var_84+1]
0x18008d000  mov     word ptr [rbp+57h+var_90+5], ax
0x18008d004  mov     al, byte ptr [rbp+57h+var_84+3]
0x18008d007  mov     byte ptr [rbp+57h+var_90+7], al
0x18008d00a  cmp     dword ptr [rbp+57h+var_90+4], 0
0x18008d00e  jl      loc_18008D20A
0x18008d014  mov     rdx, [rbp+57h+lpFilename]; lpFilename
0x18008d018  mov     r8d, ebx; nSize
0x18008d01b  mov     rcx, [rbp+57h+phModule]; hModule
0x18008d01f  call    cs:__imp_GetModuleFileNameW
0x18008d026  nop     dword ptr [rax+rax+00h]
0x18008d02b  test    eax, eax
0x18008d02d  jz      loc_18008D18F
0x18008d033  cmp     eax, ebx
0x18008d035  jb      short loc_18008D05D
0x18008d037  lea     rdx, [rdi+104h]
0x18008d03e  cmp     rdx, rdi
0x18008d041  jb      short loc_18008D053
0x18008d043  lea     r8, [rbp+57h+var_80]
0x18008d047  xor     ecx, ecx
0x18008d049  call    RtlReallocateLUnicodeString
0x18008d04e  jmp     loc_18008CFA1
0x18008d053  mov     ebx, 80070216h
0x18008d058  jmp     loc_18008D1EB
0x18008d05d  mov     edi, 2
0x18008d062  mov     ecx, eax
0x18008d064  mov     edx, edi
0x18008d066  mov     qword ptr [rbp-39h], 0
0x18008d06e  lea     r8, [rbp+57h+var_90]
0x18008d072  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x18008d077  test    eax, eax
0x18008d079  js      loc_18008CFA5
0x18008d07f  mov     rax, [rbp+57h+var_90]
0x18008d083  mov     qword ptr [rbp+57h+var_80], rax
0x18008d087  cmp     rax, 208h
0x18008d08d  jbe     short loc_18008D105
0x18008d08f  mov     rdx, [rbp+57h+lpFilename]; String2
0x18008d093  lea     r8d, [rdi+2]; MaxCount
0x18008d097  lea     rcx, String1; "\\\\?\\"
0x18008d09e  call    _wcsnicmp
0x18008d0a3  test    eax, eax
0x18008d0a5  jz      short loc_18008D105
0x18008d0a7  xorps   xmm0, xmm0
0x18008d0aa  lea     r8, [rbp+57h+var_48]
0x18008d0ae  xor     eax, eax
0x18008d0b0  lea     rdx, [rbp+57h+var_80]
0x18008d0b4  lea     rcx, String1; "\\\\?\\"
0x18008d0bb  mov     [rbp+57h+var_38], rax
0x18008d0bf  movups  [rbp+57h+var_48], xmm0
0x18008d0c3  call    ?FilePathCombine@COM@Windows@@YAJPEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::FilePathCombine(wchar_t const *,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x18008d0c8  lea     rcx, [rbp+57h+var_48]
0x18008d0cc  mov     ebx, eax
0x18008d0ce  test    eax, eax
0x18008d0d0  jns     short loc_18008D0DC
0x18008d0d2  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18008d0d7  jmp     loc_18008D1EB
0x18008d0dc  movups  xmm2, [rbp+57h+var_80]
0x18008d0e0  movups  xmm0, [rbp+57h+var_48]
0x18008d0e4  movsd   xmm3, [rbp+57h+lpFilename]
0x18008d0e9  movsd   xmm1, [rbp+57h+var_38]
0x18008d0ee  movups  [rbp+57h+var_80], xmm0
0x18008d0f2  movups  [rbp+57h+var_48], xmm2
0x18008d0f6  movsd   [rbp+57h+lpFilename], xmm1
0x18008d0fb  movsd   [rbp+57h+var_38], xmm3
0x18008d100  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18008d105  xor     eax, eax
0x18008d107  lea     rdx, [rbp+57h+var_80]
0x18008d10b  mov     [rbp+57h+var_38], rax
0x18008d10f  xorps   xmm0, xmm0
0x18008d112  mov     [rbp+57h+var_58], rax
0x18008d116  xorps   xmm1, xmm1
0x18008d119  lea     rax, [rbp+57h+var_68]
0x18008d11d  xor     r9d, r9d
0x18008d120  mov     [rsp+0D0h+var_A0], rax
0x18008d125  xor     r8d, r8d
0x18008d128  lea     rax, [rbp+57h+var_48]
0x18008d12c  mov     ecx, edi
0x18008d12e  mov     [rsp+0D0h+var_A8], rax
0x18008d133  mov     [rsp+0D0h+var_B0], 5Ch ; '\'
0x18008d13c  movups  [rbp+57h+var_48], xmm0
0x18008d140  movups  [rbp+57h+var_68], xmm1
0x18008d144  call    RtlSplitLUnicodeString
0x18008d149  test    eax, eax
0x18008d14b  js      loc_18008CFA5
0x18008d151  movups  xmm2, xmmword ptr [r14]
0x18008d155  lea     rcx, [rbp+57h+var_80]
0x18008d159  mov     rax, qword ptr [rbp+57h+var_48]
0x18008d15d  movsd   xmm3, qword ptr [r14+10h]
0x18008d163  movsd   xmm1, [rbp+57h+lpFilename]
0x18008d168  mov     qword ptr [rbp+57h+var_80], rax
0x18008d16c  movups  xmm0, [rbp+57h+var_80]
0x18008d170  movups  [rbp+57h+var_80], xmm2
0x18008d174  movups  xmmword ptr [r14], xmm0
0x18008d178  movsd   qword ptr [r14+10h], xmm1
0x18008d17e  movsd   [rbp+57h+lpFilename], xmm3
0x18008d183  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18008d188  xor     eax, eax
0x18008d18a  jmp     loc_18008D216
0x18008d18f  call    cs:__imp_GetLastError
0x18008d196  nop     dword ptr [rax+rax+00h]
0x18008d19b  test    eax, eax
0x18008d19d  jnz     short loc_18008D1F8
0x18008d19f  mov     eax, 36FDh
0x18008d1a4  mov     [rbp+57h+var_58], 2Ch ; ','
0x18008d1ac  lea     rcx, aOnecoreBaseWcp_4; "onecore\\base\\wcp\\rtllib\\win32lib\\d"...
0x18008d1b3  mov     qword ptr [rbp+57h+var_68], rcx
0x18008d1b7  lea     rcx, aWindowsComGetc; "Windows::COM::GetCurrentDllWin32Path"
0x18008d1be  mov     qword ptr [rbp+57h+var_68+8], rcx
0x18008d1c2  lea     rcx, aGetlasterror; "GetLastError"
0x18008d1c9  mov     [rbp+57h+var_50], rcx
0x18008d1cd  test    eax, eax
0x18008d1cf  jle     short loc_18008D1D9
0x18008d1d1  movzx   eax, ax
0x18008d1d4  or      eax, 80070000h
0x18008d1d9  mov     r8d, eax
0x18008d1dc  lea     rdx, [rbp+57h+var_68]
0x18008d1e0  lea     rcx, [rbp+57h+var_28]
0x18008d1e4  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008d1e9  mov     ebx, eax
0x18008d1eb  lea     rcx, [rbp+57h+var_80]
0x18008d1ef  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18008d1f4  mov     eax, ebx
0x18008d1f6  jmp     short loc_18008D216
0x18008d1f8  call    cs:__imp_GetLastError
0x18008d1ff  nop     dword ptr [rax+rax+00h]
0x18008d204  test    eax, eax
0x18008d206  jz      short loc_18008D237
0x18008d208  jmp     short loc_18008D1A4
0x18008d20a  lea     rcx, [rbp+57h+var_80]
0x18008d20e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18008d213  mov     eax, dword ptr [rbp+57h+var_90+4]
0x18008d216  mov     rcx, [rbp+57h+var_20]
0x18008d21a  xor     rcx, rsp; StackCookie
0x18008d21d  call    __security_check_cookie
0x18008d222  mov     rbx, [rsp+0D0h+arg_10]
0x18008d22a  add     rsp, 0C0h
0x18008d231  pop     r14
0x18008d233  pop     rdi
0x18008d234  pop     rbp
0x18008d235  retn
0x18008d237  mov     ecx, 0C00000E5h; int
0x18008d23c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

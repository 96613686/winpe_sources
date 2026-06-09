# win_dox::StreamOnFileHandle::Read(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x18004e90c`
- end: `0x18004eb44`
- name: `?Read@StreamOnFileHandle@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `568`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e5b0`
- `0x18005aacc`
- `0x1800b5af0`
- `0x1800b5f68`

## callees

- `0x1800155e8`
- `0x1800156a4`
- `0x180015af4`
- `0x18004e90c`
- `0x18004eb4c`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ea9b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004e9ca`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004e9ca`

## string_xrefs

- `0x18004ea0d`: `ReadFileEx failed`
- `0x18004ea57`: `Access mode for StreamOnFileHandle does not permit Read.`
- `0x18004eaa8`: `File must not be opened with overlapped flag.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::StreamOnFileHandle::Read(__int64 *a1, LPVOID *a2)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rax
  DWORD v8; // ecx
  signed int LastError; // eax
  DWORD NumberOfBytesRead[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Overlapped; // [rsp+50h] [rbp-B8h]
  struct _OVERLAPPED Overlapped_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v15; // [rsp+88h] [rbp-80h]
  _BYTE v16[64]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E8h] [rbp-20h] BYREF

  Overlapped = -2;
  if ( *((_DWORD *)a1 + 6) > 1u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4Au,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Read.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  NumberOfBytesRead[0] = 0;
  v4 = *a1;
  v14[0] = 0;
  v14[1] = 0;
  v15 = v4;
  *(_OWORD *)&Overlapped_8.Internal = 0u;
  *(_OWORD *)&Overlapped_8.Offset = v4;
  v5 = win_dox::StreamOnFileHandle::Size((win_dox::StreamOnFileHandle *)a1);
  if ( v5 <= *a1 )
  {
    return NumberOfBytesRead[0];
  }
  else
  {
    v6 = *(unsigned int *)a2;
    v7 = v5 - *a1;
    if ( v6 >= v7 )
      LODWORD(v6) = v7;
    if ( !ReadFile((HANDLE)a1[2], a2[1], v6, NumberOfBytesRead, &Overlapped_8) )
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        win_musl::DebugLogHelper(
          "(no filename)",
          &word_18013A0B6,
          121,
          1024,
          -2147418113,
          L"File must not be opened with overlapped flag.");
        std::string::string(v14, "Program has entered an unexpected state");
        std::logic_error::logic_error(v16, v14);
        throw (std::logic_error *)v16;
      }
      if ( LastError != 234 && LastError != 109 && LastError != 38 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x80u,
          LastError,
          (struct win_musl::TStringEllipseBase *)L"ReadFileEx failed");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    v8 = NumberOfBytesRead[0];
    *a1 += NumberOfBytesRead[0];
  }
  return v8;
}

```

## disassembly

```asm
0x18004e90c  mov     rax, rsp
0x18004e90f  push    rbp
0x18004e910  lea     rbp, [rax-98h]
0x18004e917  sub     rsp, 190h
0x18004e91e  mov     [rsp+190h+Overlapped.Internal], 0FFFFFFFFFFFFFFFEh
0x18004e927  mov     [rax+18h], rbx
0x18004e92b  mov     [rax+20h], rdi
0x18004e92f  mov     rax, cs:__security_cookie
0x18004e936  xor     rax, rsp
0x18004e939  mov     [rbp+90h+var_10], rax
0x18004e940  mov     rdi, rdx
0x18004e943  mov     rbx, rcx
0x18004e946  cmp     dword ptr [rcx+18h], 1
0x18004e94a  jnz     loc_18004EA4D
0x18004e950  mov     [rsp+190h+NumberOfBytesRead], 0
0x18004e958  mov     rcx, [rcx]
0x18004e95b  mov     qword ptr [rsp+190h+var_128+8], 0
0x18004e964  mov     [rsp+190h+var_118], 0
0x18004e96d  mov     qword ptr [rbp+90h+var_110+8], 0
0x18004e975  mov     rax, rcx
0x18004e978  shr     rax, 20h
0x18004e97c  mov     dword ptr [rbp+90h+var_110], ecx
0x18004e97f  mov     dword ptr [rbp+90h+var_110+4], eax
0x18004e982  movups  xmm0, [rsp+190h+var_128+8]
0x18004e987  movups  xmmword ptr [rsp+190h+Overlapped.InternalHigh], xmm0
0x18004e98c  movups  xmm1, [rbp+90h+var_110]
0x18004e990  movups  xmmword ptr [rsp+190h+Overlapped.hEvent], xmm1
0x18004e995  mov     rcx, rbx; this
0x18004e998  call    ?Size@StreamOnFileHandle@win_dox@@IEAA_KXZ; win_dox::StreamOnFileHandle::Size(void)
0x18004e99d  cmp     rax, [rbx]
0x18004e9a0  jbe     loc_18004EB3B
0x18004e9a6  mov     r8d, [rdi]
0x18004e9a9  sub     rax, [rbx]
0x18004e9ac  cmp     r8, rax
0x18004e9af  cmovnb  r8d, eax; nNumberOfBytesToRead
0x18004e9b3  lea     rax, [rsp+190h+Overlapped.InternalHigh]
0x18004e9b8  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x18004e9bd  lea     r9, [rsp+190h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004e9c2  mov     rdx, [rdi+8]; lpBuffer
0x18004e9c6  mov     rcx, [rbx+10h]; hFile
0x18004e9ca  call    cs:__imp_ReadFile
0x18004e9d0  test    eax, eax
0x18004e9d2  jz      loc_18004EA9B
0x18004e9d8  mov     ecx, [rsp+190h+NumberOfBytesRead]
0x18004e9dc  add     [rbx], rcx
0x18004e9df  mov     eax, ecx
0x18004e9e1  mov     rcx, [rbp+90h+var_10]
0x18004e9e8  xor     rcx, rsp; StackCookie
0x18004e9eb  call    __security_check_cookie
0x18004e9f0  lea     r11, [rsp+190h+var_s0]
0x18004e9f8  mov     rbx, [r11+20h]
0x18004e9fc  mov     rdi, [r11+28h]
0x18004ea00  mov     rsp, r11
0x18004ea03  pop     rbp
0x18004ea04  retn
0x18004ea05  test    eax, eax
0x18004ea07  jg      loc_18004EB2E
0x18004ea0d  lea     rcx, aReadfileexFail; "ReadFileEx failed"
0x18004ea14  mov     [rsp+190h+var_160], rcx; struct win_musl::TStringEllipseBase *
0x18004ea19  mov     [rsp+190h+var_168], eax; unsigned int
0x18004ea1d  mov     dword ptr [rsp+190h+lpOverlapped], 80h; unsigned int
0x18004ea25  lea     r9, word_18013A0B6
0x18004ea2c  lea     r8, aNoFilename; "(no filename)"
0x18004ea33  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18004ea37  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004ea3c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004ea43  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18004ea47  call    _CxxThrowException_0
0x18004ea4d  cmp     dword ptr [rcx+18h], 0
0x18004ea51  jz      loc_18004E950
0x18004ea57  lea     rax, aAccessModeForS; "Access mode for StreamOnFileHandle does"...
0x18004ea5e  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x18004ea63  mov     [rsp+190h+var_168], 80004001h; unsigned int
0x18004ea6b  mov     dword ptr [rsp+190h+lpOverlapped], 4Ah ; 'J'; unsigned int
0x18004ea73  lea     r9, word_18013A0B6
0x18004ea7a  lea     r8, aNoFilename; "(no filename)"
0x18004ea81  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18004ea85  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004ea8a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004ea91  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x18004ea95  call    _CxxThrowException_0
0x18004ea9b  call    cs:__imp_GetLastError
0x18004eaa1  cmp     eax, 3E5h
0x18004eaa6  jnz     short loc_18004EB0C
0x18004eaa8  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x18004eaaf  mov     qword ptr [rsp+190h+var_168], rax
0x18004eab4  mov     dword ptr [rsp+190h+lpOverlapped], 8000FFFFh
0x18004eabc  mov     r9d, 400h
0x18004eac2  mov     r8d, 79h ; 'y'
0x18004eac8  lea     rdx, word_18013A0B6
0x18004eacf  lea     rcx, aNoFilename; "(no filename)"
0x18004ead6  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18004eadb  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x18004eae2  lea     rcx, [rsp+190h+var_128+8]
0x18004eae7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18004eaec  nop
0x18004eaed  lea     rdx, [rsp+190h+var_128+8]
0x18004eaf2  lea     rcx, [rbp+90h+var_F0]
0x18004eaf6  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18004eafb  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18004eb02  lea     rcx, [rbp+90h+var_F0]; pExceptionObject
0x18004eb06  call    _CxxThrowException_0
0x18004eb0c  cmp     eax, 0EAh
0x18004eb11  jz      loc_18004E9D8
0x18004eb17  cmp     eax, 6Dh ; 'm'
0x18004eb1a  jz      loc_18004E9D8
0x18004eb20  cmp     eax, 26h ; '&'
0x18004eb23  jz      loc_18004E9D8
0x18004eb29  jmp     loc_18004EA05
0x18004eb2e  movzx   eax, ax
0x18004eb31  or      eax, 80070000h
0x18004eb36  jmp     loc_18004EA0D
0x18004eb3b  mov     ecx, [rsp+190h+NumberOfBytesRead]
0x18004eb3f  jmp     loc_18004E9DF
```

# win_dox::StreamOnFileHandle::Write(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)

- ea: `0x180002080`
- end: `0x18000229e`
- name: `?Write@StreamOnFileHandle@win_dox@@QEAAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `542`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002000`
- `0x1800e0060`
- `0x1800f7db0`

## callees

- `0x180002080`
- `0x1800022a4`
- `0x1800155e8`
- `0x1800156a4`
- `0x180015af4`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021fe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000212f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000212f`

## string_xrefs

- `0x180002170`: `WriteFile failed`
- `0x18000220b`: `File must not be opened with overlapped flag.`
- `0x1800021ba`: `Access mode for StreamOnFileHandle does not permit Write.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::StreamOnFileHandle::Write(__int64 a1, __int64 a2, unsigned __int64 a3, unsigned int a4)
{
  void *v6; // rcx
  __int64 result; // rax
  signed int LastError; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Overlapped; // [rsp+50h] [rbp-B8h]
  struct _OVERLAPPED Overlapped_8; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v12[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v13; // [rsp+88h] [rbp-80h]
  _BYTE v14[64]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E8h] [rbp-20h] BYREF

  Overlapped = -2;
  if ( *(_DWORD *)(a1 + 24) != 1 && *(_DWORD *)(a1 + 24) != 2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x92u,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Write.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  win_dox::SetFilePosition(*(win_dox **)(a1 + 16), *(void **)a1, a3, a4);
  NumberOfBytesWritten[0] = 0;
  v6 = *(void **)a1;
  v12[0] = 0;
  v12[1] = 0;
  v13 = (unsigned __int64)v6;
  *(_OWORD *)&Overlapped_8.Internal = 0u;
  *(_OWORD *)&Overlapped_8.Offset = (unsigned __int64)v6;
  if ( !WriteFile(*(HANDLE *)(a1 + 16), *(LPCVOID *)(a2 + 8), *(_DWORD *)a2, NumberOfBytesWritten, &Overlapped_8) )
  {
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      win_musl::DebugLogHelper(
        "(no filename)",
        &word_18013A0B6,
        173,
        1024,
        -2147418113,
        L"File must not be opened with overlapped flag.");
      std::string::string(v12, "Program has entered an unexpected state");
      std::logic_error::logic_error(v14, v12);
      throw (std::logic_error *)v14;
    }
    if ( LastError != 234 && LastError != 109 && LastError != 38 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xB4u,
        LastError,
        (struct win_musl::TStringEllipseBase *)L"WriteFile failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  result = NumberOfBytesWritten[0];
  *(_QWORD *)a1 += NumberOfBytesWritten[0];
  return result;
}

```

## disassembly

```asm
0x180002080  mov     rax, rsp
0x180002083  push    rbp
0x180002084  lea     rbp, [rax-98h]
0x18000208b  sub     rsp, 190h
0x180002092  mov     [rsp+190h+Overlapped.Internal], 0FFFFFFFFFFFFFFFEh
0x18000209b  mov     [rax+18h], rbx
0x18000209f  mov     [rax+20h], rdi
0x1800020a3  mov     rax, cs:__security_cookie
0x1800020aa  xor     rax, rsp
0x1800020ad  mov     [rbp+90h+var_10], rax
0x1800020b4  mov     rdi, rdx
0x1800020b7  mov     rbx, rcx
0x1800020ba  cmp     dword ptr [rcx+18h], 1
0x1800020be  jnz     loc_1800021B0
0x1800020c4  mov     rdx, [rcx]; void *
0x1800020c7  mov     rcx, [rcx+10h]; this
0x1800020cb  call    ?SetFilePosition@win_dox@@YA_KPEAX_KK@Z; win_dox::SetFilePosition(void *,unsigned __int64,ulong)
0x1800020d0  mov     [rsp+190h+NumberOfBytesWritten], 0
0x1800020d8  mov     rcx, [rbx]
0x1800020db  mov     qword ptr [rsp+190h+var_128+8], 0
0x1800020e4  mov     [rsp+190h+var_118], 0
0x1800020ed  mov     qword ptr [rbp+90h+var_110+8], 0
0x1800020f5  mov     rax, rcx
0x1800020f8  shr     rax, 20h
0x1800020fc  mov     dword ptr [rbp+90h+var_110], ecx
0x1800020ff  mov     dword ptr [rbp+90h+var_110+4], eax
0x180002102  movups  xmm0, [rsp+190h+var_128+8]
0x180002107  movups  xmmword ptr [rsp+190h+Overlapped.InternalHigh], xmm0
0x18000210c  movups  xmm1, [rbp+90h+var_110]
0x180002110  movups  xmmword ptr [rsp+190h+Overlapped.hEvent], xmm1
0x180002115  lea     rax, [rsp+190h+Overlapped.InternalHigh]
0x18000211a  mov     [rsp+190h+lpOverlapped], rax; lpOverlapped
0x18000211f  lea     r9, [rsp+190h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002124  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180002127  mov     rdx, [rdi+8]; lpBuffer
0x18000212b  mov     rcx, [rbx+10h]; hFile
0x18000212f  call    cs:__imp_WriteFile
0x180002135  test    eax, eax
0x180002137  jz      loc_1800021FE
0x18000213d  mov     eax, [rsp+190h+NumberOfBytesWritten]
0x180002141  add     [rbx], rax
0x180002144  mov     rcx, [rbp+90h+var_10]
0x18000214b  xor     rcx, rsp; StackCookie
0x18000214e  call    __security_check_cookie
0x180002153  lea     r11, [rsp+190h+var_s0]
0x18000215b  mov     rbx, [r11+20h]
0x18000215f  mov     rdi, [r11+28h]
0x180002163  mov     rsp, r11
0x180002166  pop     rbp
0x180002167  retn
0x180002168  test    eax, eax
0x18000216a  jg      loc_180002291
0x180002170  lea     rcx, aWritefileFaile_0; "WriteFile failed"
0x180002177  mov     [rsp+190h+var_160], rcx; struct win_musl::TStringEllipseBase *
0x18000217c  mov     [rsp+190h+var_168], eax; unsigned int
0x180002180  mov     dword ptr [rsp+190h+lpOverlapped], 0B4h; unsigned int
0x180002188  lea     r9, word_18013A0B6
0x18000218f  lea     r8, aNoFilename; "(no filename)"
0x180002196  lea     rcx, [rbp+90h+pExceptionObject]; this
0x18000219a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000219f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800021a6  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800021aa  call    _CxxThrowException_0
0x1800021b0  cmp     dword ptr [rcx+18h], 2
0x1800021b4  jz      loc_1800020C4
0x1800021ba  lea     rax, aAccessModeForS_0; "Access mode for StreamOnFileHandle does"...
0x1800021c1  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800021c6  mov     [rsp+190h+var_168], 80004001h; unsigned int
0x1800021ce  mov     dword ptr [rsp+190h+lpOverlapped], 92h; unsigned int
0x1800021d6  lea     r9, word_18013A0B6
0x1800021dd  lea     r8, aNoFilename; "(no filename)"
0x1800021e4  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800021e8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800021ed  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800021f4  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800021f8  call    _CxxThrowException_0
0x1800021fe  call    cs:__imp_GetLastError
0x180002204  cmp     eax, 3E5h
0x180002209  jnz     short loc_18000226F
0x18000220b  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x180002212  mov     qword ptr [rsp+190h+var_168], rax
0x180002217  mov     dword ptr [rsp+190h+lpOverlapped], 8000FFFFh
0x18000221f  mov     r9d, 400h
0x180002225  mov     r8d, 0ADh
0x18000222b  lea     rdx, word_18013A0B6
0x180002232  lea     rcx, aNoFilename; "(no filename)"
0x180002239  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18000223e  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180002245  lea     rcx, [rsp+190h+var_128+8]
0x18000224a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18000224f  nop
0x180002250  lea     rdx, [rsp+190h+var_128+8]
0x180002255  lea     rcx, [rbp+90h+var_F0]
0x180002259  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18000225e  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180002265  lea     rcx, [rbp+90h+var_F0]; pExceptionObject
0x180002269  call    _CxxThrowException_0
0x18000226f  cmp     eax, 0EAh
0x180002274  jz      loc_18000213D
0x18000227a  cmp     eax, 6Dh ; 'm'
0x18000227d  jz      loc_18000213D
0x180002283  cmp     eax, 26h ; '&'
0x180002286  jz      loc_18000213D
0x18000228c  jmp     loc_180002168
0x180002291  movzx   eax, ax
0x180002294  or      eax, 80070000h
0x180002299  jmp     loc_180002170
```

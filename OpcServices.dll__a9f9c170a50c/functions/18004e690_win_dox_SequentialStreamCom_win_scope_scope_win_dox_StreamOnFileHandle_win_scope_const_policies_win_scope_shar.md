# win_dox::SequentialStreamCom<win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>,IStream>::Read_Safe(void *,ulong,ulong *)

- ea: `0x18004e690`
- end: `0x18004e905`
- name: `?Read_Safe@?$SequentialStreamCom@V?$scope@PEAVStreamOnFileHandle@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIStream@@@win_dox@@AEAAXPEAXKPEAK@Z`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e650`

## callees

- `0x1800155e8`
- `0x1800156a4`
- `0x180015af4`
- `0x18004e690`
- `0x18004eb4c`
- `0x1800517a0`
- `0x18005ab90`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e85c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004e74f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004e74f`

## string_xrefs

- `0x18004e790`: `ReadFileEx failed`
- `0x18004e818`: `Access mode for StreamOnFileHandle does not permit Read.`
- `0x18004e869`: `File must not be opened with overlapped flag.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall win_dox::SequentialStreamCom<win_scope::scope<win_dox::StreamOnFileHandle *,win_scope::const_policies<win_scope::shared_policies>>,IStream>::Read_Safe(
        __int64 a1,
        void *a2,
        __int64 a3,
        DWORD *a4)
{
  unsigned __int64 v5; // r14
  __int64 *v7; // rbx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rax
  DWORD v11; // ecx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v16[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+E0h] [rbp-20h] BYREF

  v14 = -2;
  v5 = (unsigned int)a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 78, L"IStream", L"Read", L"pv", 0);
  DWORD1(v16[0]) = 0;
  v7 = *(__int64 **)(a1 + 16);
  if ( *((_DWORD *)v7 + 6) > 1u )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4Au,
      0x80004001,
      (struct win_musl::TStringEllipseBase *)L"Access mode for StreamOnFileHandle does not permit Read.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  NumberOfBytesRead = 0;
  v8 = *v7;
  v16[0] = 0u;
  v16[1] = v8;
  *(_OWORD *)&Overlapped.Internal = 0u;
  *(_OWORD *)&Overlapped.Offset = v8;
  v9 = win_dox::StreamOnFileHandle::Size((win_dox::StreamOnFileHandle *)v7);
  if ( v9 <= *v7 )
  {
    v11 = NumberOfBytesRead;
  }
  else
  {
    v10 = v9 - *v7;
    if ( v5 >= v10 )
      LODWORD(v5) = v10;
    LODWORD(v9) = ReadFile((HANDLE)v7[2], a2, v5, &NumberOfBytesRead, &Overlapped);
    if ( !(_DWORD)v9 )
    {
      LODWORD(v9) = GetLastError();
      if ( (_DWORD)v9 == 997 )
      {
        win_musl::DebugLogHelper(
          "(no filename)",
          &word_18013A0B6,
          121,
          1024,
          -2147418113,
          L"File must not be opened with overlapped flag.");
        std::string::string(v16, "Program has entered an unexpected state");
        std::logic_error::logic_error(v17, v16);
        throw (std::logic_error *)v17;
      }
      if ( (_DWORD)v9 != 234 && (_DWORD)v9 != 109 && (_DWORD)v9 != 38 )
      {
        if ( (int)v9 > 0 )
          LODWORD(v9) = (unsigned __int16)v9 | 0x80070000;
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x80u,
          v9,
          (struct win_musl::TStringEllipseBase *)L"ReadFileEx failed");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    v11 = NumberOfBytesRead;
    *v7 += NumberOfBytesRead;
  }
  if ( a4 )
    *a4 = v11;
  return v9;
}

```

## disassembly

```asm
0x18004e690  push    rbp
0x18004e692  push    rbx
0x18004e693  push    rsi
0x18004e694  push    rdi
0x18004e695  push    r14
0x18004e697  lea     rbp, [rsp-90h]
0x18004e69f  sub     rsp, 190h
0x18004e6a6  mov     [rsp+1B0h+var_168], 0FFFFFFFFFFFFFFFEh
0x18004e6af  mov     rax, cs:__security_cookie
0x18004e6b6  xor     rax, rsp
0x18004e6b9  mov     [rbp+0B0h+var_30], rax
0x18004e6c0  mov     rdi, r9
0x18004e6c3  mov     r14d, r8d
0x18004e6c6  mov     rsi, rdx
0x18004e6c9  test    rdx, rdx
0x18004e6cc  jz      loc_18004E7D0
0x18004e6d2  xor     eax, eax
0x18004e6d4  mov     dword ptr [rsp+1B0h+var_140+4], eax
0x18004e6d8  mov     rbx, [rcx+10h]
0x18004e6dc  cmp     dword ptr [rbx+18h], 1
0x18004e6e0  jnz     loc_18004E80F
0x18004e6e6  mov     [rsp+1B0h+NumberOfBytesRead], eax
0x18004e6ea  mov     rcx, [rbx]
0x18004e6ed  mov     qword ptr [rsp+1B0h+var_140], rax
0x18004e6f2  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x18004e6f7  mov     qword ptr [rbp+0B0h+var_130+8], rax
0x18004e6fb  mov     rax, rcx
0x18004e6fe  shr     rax, 20h
0x18004e702  mov     dword ptr [rbp+0B0h+var_130], ecx
0x18004e705  mov     dword ptr [rbp+0B0h+var_130+4], eax
0x18004e708  movups  xmm0, [rsp+1B0h+var_140]
0x18004e70d  movups  xmmword ptr [rsp+1B0h+Overlapped.Internal], xmm0
0x18004e712  movups  xmm1, [rbp+0B0h+var_130]
0x18004e716  movups  xmmword ptr [rsp+1B0h+Overlapped.10h], xmm1
0x18004e71b  mov     rcx, rbx; this
0x18004e71e  call    ?Size@StreamOnFileHandle@win_dox@@IEAA_KXZ; win_dox::StreamOnFileHandle::Size(void)
0x18004e723  cmp     rax, [rbx]
0x18004e726  jbe     loc_18004E8FC
0x18004e72c  sub     rax, [rbx]
0x18004e72f  cmp     r14, rax
0x18004e732  cmovnb  r14d, eax
0x18004e736  lea     rax, [rsp+1B0h+Overlapped]
0x18004e73b  mov     [rsp+1B0h+lpOverlapped], rax; lpOverlapped
0x18004e740  lea     r9, [rsp+1B0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004e745  mov     r8d, r14d; nNumberOfBytesToRead
0x18004e748  mov     rdx, rsi; lpBuffer
0x18004e74b  mov     rcx, [rbx+10h]; hFile
0x18004e74f  call    cs:__imp_ReadFile
0x18004e755  test    eax, eax
0x18004e757  jz      loc_18004E85C
0x18004e75d  mov     ecx, [rsp+1B0h+NumberOfBytesRead]
0x18004e761  add     [rbx], rcx
0x18004e764  test    rdi, rdi
0x18004e767  jz      short loc_18004E76B
0x18004e769  mov     [rdi], ecx
0x18004e76b  mov     rcx, [rbp+0B0h+var_30]
0x18004e772  xor     rcx, rsp; StackCookie
0x18004e775  call    __security_check_cookie
0x18004e77a  add     rsp, 190h
0x18004e781  pop     r14
0x18004e783  pop     rdi
0x18004e784  pop     rsi
0x18004e785  pop     rbx
0x18004e786  pop     rbp
0x18004e787  retn
0x18004e788  test    eax, eax
0x18004e78a  jg      loc_18004E8EF
0x18004e790  lea     rcx, aReadfileexFail; "ReadFileEx failed"
0x18004e797  mov     [rsp+1B0h+var_180], rcx; struct win_musl::TStringEllipseBase *
0x18004e79c  mov     [rsp+1B0h+var_188], eax; unsigned int
0x18004e7a0  mov     dword ptr [rsp+1B0h+lpOverlapped], 80h; unsigned int
0x18004e7a8  lea     r9, word_18013A0B6
0x18004e7af  lea     r8, aNoFilename; "(no filename)"
0x18004e7b6  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x18004e7ba  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004e7bf  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004e7c6  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x18004e7ca  call    _CxxThrowException_0
0x18004e7d0  mov     [rsp+1B0h+var_178], 0
0x18004e7d8  lea     rax, aPv; "pv"
0x18004e7df  mov     [rsp+1B0h+var_180], rax
0x18004e7e4  lea     rax, aRead; "Read"
0x18004e7eb  mov     qword ptr [rsp+1B0h+var_188], rax
0x18004e7f0  lea     rax, aIstream; "IStream"
0x18004e7f7  mov     [rsp+1B0h+lpOverlapped], rax
0x18004e7fc  mov     r9d, 4Eh ; 'N'
0x18004e802  lea     rdx, aNoFilename; "(no filename)"
0x18004e809  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x18004e80f  cmp     [rbx+18h], eax
0x18004e812  jz      loc_18004E6E6
0x18004e818  lea     rax, aAccessModeForS; "Access mode for StreamOnFileHandle does"...
0x18004e81f  mov     [rsp+1B0h+var_180], rax; struct win_musl::TStringEllipseBase *
0x18004e824  mov     [rsp+1B0h+var_188], 80004001h; unsigned int
0x18004e82c  mov     dword ptr [rsp+1B0h+lpOverlapped], 4Ah ; 'J'; unsigned int
0x18004e834  lea     r9, word_18013A0B6
0x18004e83b  lea     r8, aNoFilename; "(no filename)"
0x18004e842  lea     rcx, [rbp+0B0h+pExceptionObject]; this
0x18004e846  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004e84b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004e852  lea     rcx, [rbp+0B0h+pExceptionObject]; pExceptionObject
0x18004e856  call    _CxxThrowException_0
0x18004e85c  call    cs:__imp_GetLastError
0x18004e862  cmp     eax, 3E5h
0x18004e867  jnz     short loc_18004E8CD
0x18004e869  lea     rax, aFileMustNotBeO; "File must not be opened with overlapped"...
0x18004e870  mov     qword ptr [rsp+1B0h+var_188], rax
0x18004e875  mov     dword ptr [rsp+1B0h+lpOverlapped], 8000FFFFh
0x18004e87d  mov     r9d, 400h
0x18004e883  mov     r8d, 79h ; 'y'
0x18004e889  lea     rdx, word_18013A0B6
0x18004e890  lea     rcx, aNoFilename; "(no filename)"
0x18004e897  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18004e89c  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x18004e8a3  lea     rcx, [rsp+1B0h+var_140]
0x18004e8a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18004e8ad  nop
0x18004e8ae  lea     rdx, [rsp+1B0h+var_140]
0x18004e8b3  lea     rcx, [rbp+0B0h+var_110]
0x18004e8b7  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x18004e8bc  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x18004e8c3  lea     rcx, [rbp+0B0h+var_110]; pExceptionObject
0x18004e8c7  call    _CxxThrowException_0
0x18004e8cd  cmp     eax, 0EAh
0x18004e8d2  jz      loc_18004E75D
0x18004e8d8  cmp     eax, 6Dh ; 'm'
0x18004e8db  jz      loc_18004E75D
0x18004e8e1  cmp     eax, 26h ; '&'
0x18004e8e4  jz      loc_18004E75D
0x18004e8ea  jmp     loc_18004E788
0x18004e8ef  movzx   eax, ax
0x18004e8f2  or      eax, 80070000h
0x18004e8f7  jmp     loc_18004E790
0x18004e8fc  mov     ecx, [rsp+1B0h+NumberOfBytesRead]
0x18004e900  jmp     loc_18004E764
```

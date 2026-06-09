# win_musl::DataBuffer::WriteVectorToFile(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 const &)

- ea: `0x180001c5c`
- end: `0x180001daa`
- name: `?WriteVectorToFile@DataBuffer@win_musl@@AEAAXAEBU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z`
- size: `334`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this, const struct __MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800027a0`
- `0x180002b64`

## callees

- `0x180001c5c`
- `0x1800023dc`
- `0x1800023f0`
- `0x180015a68`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001cac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001cac`

## string_xrefs

- `0x180001d3f`: `WriteFile did not write expected data to temporary file`
- `0x180001cd7`: `Call to ::WriteFile failed with HResult 0x%X.`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::WriteVectorToFile(win_musl::DataBuffer *this, DWORD *a2)
{
  DWORD v4; // r8d
  const void *v5; // rdx
  void *v6; // rcx
  unsigned int v7; // eax
  int v8; // edx
  signed int v9; // esi
  DWORD v10; // ecx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v13[512]; // [rsp+F0h] [rbp-418h] BYREF

  win_musl::DataBuffer::TestCreateFile(this);
  v4 = *a2;
  v5 = (const void *)*((_QWORD *)a2 + 1);
  v6 = (void *)*((_QWORD *)this + 8);
  NumberOfBytesWritten = 0;
  v7 = WriteFile(v6, v5, v4, &NumberOfBytesWritten, 0);
  v9 = win_musl::HResultFromBool((win_musl *)v7, v8);
  if ( v9 < 0 )
  {
    memset_0(v13, 0, sizeof(v13));
    StringCchPrintfW(v13, 0x200u, L"Call to ::WriteFile failed with HResult 0x%X.", (unsigned int)v9);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x114u,
      v9,
      (struct win_musl::TStringEllipseBase *)v13);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = NumberOfBytesWritten;
  *((_QWORD *)this + 9) += NumberOfBytesWritten;
  if ( v10 != *a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x11Au,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"WriteFile did not write expected data to temporary file");
    throw (SplException::THResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180001c5c  mov     [rsp+arg_10], rbx
0x180001c61  mov     [rsp+arg_18], rsi
0x180001c66  push    rdi
0x180001c67  sub     rsp, 500h
0x180001c6e  mov     rax, cs:__security_cookie
0x180001c75  xor     rax, rsp
0x180001c78  mov     [rsp+508h+var_18], rax
0x180001c80  mov     rdi, rdx
0x180001c83  mov     rbx, rcx
0x180001c86  call    ?TestCreateFile@DataBuffer@win_musl@@AEAAXXZ; win_musl::DataBuffer::TestCreateFile(void)
0x180001c8b  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180001c8e  lea     r9, [rsp+508h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001c93  mov     rdx, [rdi+8]; lpBuffer
0x180001c97  mov     rcx, [rbx+40h]; hFile
0x180001c9b  mov     [rsp+508h+NumberOfBytesWritten], 0
0x180001ca3  mov     [rsp+508h+lpOverlapped], 0; lpOverlapped
0x180001cac  call    cs:__imp_WriteFile
0x180001cb2  mov     ecx, eax; this
0x180001cb4  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180001cb9  mov     esi, eax
0x180001cbb  test    eax, eax
0x180001cbd  jns     short loc_180001D33
0x180001cbf  xor     edx, edx; Val
0x180001cc1  lea     rcx, [rsp+508h+var_418]; void *
0x180001cc9  mov     r8d, 400h; Size
0x180001ccf  call    memset_0
0x180001cd4  mov     r9d, esi
0x180001cd7  lea     r8, aCallToWritefil; "Call to ::WriteFile failed with HResult"...
0x180001cde  mov     edx, 200h; unsigned __int64
0x180001ce3  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x180001ceb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180001cf0  lea     rax, [rsp+508h+var_418]
0x180001cf8  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180001cfd  lea     r9, word_18013A0B6
0x180001d04  mov     [rsp+508h+var_4E0], esi; unsigned int
0x180001d08  lea     r8, aNoFilename; "(no filename)"
0x180001d0f  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180001d14  mov     dword ptr [rsp+508h+lpOverlapped], 114h; unsigned int
0x180001d1c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001d21  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001d28  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180001d2d  call    _CxxThrowException_0
0x180001d33  mov     ecx, [rsp+508h+NumberOfBytesWritten]
0x180001d37  add     [rbx+48h], rcx
0x180001d3b  cmp     ecx, [rdi]
0x180001d3d  jz      short loc_180001D85
0x180001d3f  lea     rax, aWritefileDidNo; "WriteFile did not write expected data t"...
0x180001d46  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180001d4b  lea     r9, word_18013A0B6
0x180001d52  mov     [rsp+508h+var_4E0], 8000FFFFh; unsigned int
0x180001d5a  lea     r8, aNoFilename; "(no filename)"
0x180001d61  lea     rcx, [rsp+508h+pExceptionObject]; this
0x180001d66  mov     dword ptr [rsp+508h+lpOverlapped], 11Ah; unsigned int
0x180001d6e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001d73  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001d7a  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180001d7f  call    _CxxThrowException_0
0x180001d85  mov     rcx, [rsp+508h+var_18]
0x180001d8d  xor     rcx, rsp; StackCookie
0x180001d90  call    __security_check_cookie
0x180001d95  lea     r11, [rsp+508h+var_8]
0x180001d9d  mov     rbx, [r11+20h]
0x180001da1  mov     rsi, [r11+28h]
0x180001da5  mov     rsp, r11
0x180001da8  pop     rdi
0x180001da9  retn
```

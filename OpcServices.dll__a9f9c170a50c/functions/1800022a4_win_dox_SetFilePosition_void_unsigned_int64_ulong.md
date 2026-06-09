# win_dox::SetFilePosition(void *,unsigned __int64,ulong)

- ea: `0x1800022a4`
- end: `0x1800023d3`
- name: `?SetFilePosition@win_dox@@YA_KPEAX_KK@Z`
- size: `303`
- prototype: `unsigned __int64 __fastcall(win_dox *__hidden this, void *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180002080`
- `0x1800dff00`

## callees

- `0x1800022a4`
- `0x1800023dc`
- `0x180015a68`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800022d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800022d7`

## string_xrefs

- `0x180002331`: `Call to SetFilePointerEx failed with HResult 0x%X.`
- `0x18000238d`: `SetFilePosition SetFilePointerEx requestedPosition and currentPosition do not match`

## pseudocode

```c
LARGE_INTEGER __fastcall win_dox::SetFilePosition(win_dox *this, void *a2)
{
  unsigned int v3; // eax
  int v4; // edx
  signed int v5; // edi
  LARGE_INTEGER result; // rax
  LARGE_INTEGER NewFilePointer; // [rsp+40h] [rbp-4C8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-4B8h] BYREF
  wchar_t v9[512]; // [rsp+F0h] [rbp-418h] BYREF

  NewFilePointer.QuadPart = 0;
  v3 = SetFilePointerEx(this, (LARGE_INTEGER)a2, &NewFilePointer, 0);
  v5 = win_musl::HResultFromBool((win_musl *)v3, v4);
  if ( v5 < 0 )
  {
    memset_0(v9, 0, sizeof(v9));
    StringCchPrintfW(v9, 0x200u, L"Call to SetFilePointerEx failed with HResult 0x%X.", (unsigned int)v5);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x20u,
      v5,
      (struct win_musl::TStringEllipseBase *)v9);
    throw (SplException::THResultException *)pExceptionObject;
  }
  result = NewFilePointer;
  if ( (void *)NewFilePointer.QuadPart != a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x24u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"SetFilePosition SetFilePointerEx requestedPosition and currentPosition do not match");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800022a4  mov     [rsp+arg_10], rbx
0x1800022a9  push    rdi
0x1800022aa  sub     rsp, 500h
0x1800022b1  mov     rax, cs:__security_cookie
0x1800022b8  xor     rax, rsp
0x1800022bb  mov     [rsp+508h+var_18], rax
0x1800022c3  xor     r9d, r9d; dwMoveMethod
0x1800022c6  mov     qword ptr [rsp+508h+NewFilePointer], 0
0x1800022cf  lea     r8, [rsp+508h+NewFilePointer]; lpNewFilePointer
0x1800022d4  mov     rbx, rdx
0x1800022d7  call    cs:__imp_SetFilePointerEx
0x1800022dd  mov     ecx, eax; this
0x1800022df  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x1800022e4  mov     edi, eax
0x1800022e6  test    eax, eax
0x1800022e8  js      short loc_180002319
0x1800022ea  mov     rax, qword ptr [rsp+508h+NewFilePointer]
0x1800022ef  cmp     rax, rbx
0x1800022f2  jnz     loc_18000238D
0x1800022f8  mov     rcx, [rsp+508h+var_18]
0x180002300  xor     rcx, rsp; StackCookie
0x180002303  call    __security_check_cookie
0x180002308  mov     rbx, [rsp+508h+arg_10]
0x180002310  add     rsp, 500h
0x180002317  pop     rdi
0x180002318  retn
0x180002319  xor     edx, edx; Val
0x18000231b  lea     rcx, [rsp+508h+var_418]; void *
0x180002323  mov     r8d, 400h; Size
0x180002329  call    memset_0
0x18000232e  mov     r9d, edi
0x180002331  lea     r8, aCallToSetfilep_0; "Call to SetFilePointerEx failed with HR"...
0x180002338  mov     edx, 200h; unsigned __int64
0x18000233d  lea     rcx, [rsp+508h+var_418]; wchar_t *
0x180002345  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000234a  lea     rax, [rsp+508h+var_418]
0x180002352  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180002357  lea     r9, word_18013A0B6
0x18000235e  mov     [rsp+508h+var_4E0], edi; unsigned int
0x180002362  lea     r8, aNoFilename; "(no filename)"
0x180002369  lea     rcx, [rsp+508h+pExceptionObject]; this
0x18000236e  mov     [rsp+508h+var_4E8], 20h ; ' '; unsigned int
0x180002376  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000237b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180002382  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x180002387  call    _CxxThrowException_0
0x18000238d  lea     rax, aSetfilepositio; "SetFilePosition SetFilePointerEx reques"...
0x180002394  mov     [rsp+508h+var_4D8], rax; struct win_musl::TStringEllipseBase *
0x180002399  lea     r9, word_18013A0B6
0x1800023a0  mov     [rsp+508h+var_4E0], 8000FFFFh; unsigned int
0x1800023a8  lea     r8, aNoFilename; "(no filename)"
0x1800023af  lea     rcx, [rsp+508h+pExceptionObject]; this
0x1800023b4  mov     [rsp+508h+var_4E8], 24h ; '$'; unsigned int
0x1800023bc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800023c1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800023c8  lea     rcx, [rsp+508h+pExceptionObject]; pExceptionObject
0x1800023cd  call    _CxxThrowException_0
```

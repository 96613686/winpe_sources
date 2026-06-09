# win_musl::DataBuffer::WriteBufferToFile(void)

- ea: `0x180001b04`
- end: `0x180001c53`
- name: `?WriteBufferToFile@DataBuffer@win_musl@@AEAAXXZ`
- size: `335`
- prototype: `void __fastcall(win_musl::DataBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180002b64`

## callees

- `0x180001b04`
- `0x1800023dc`
- `0x1800023f0`
- `0x180015a68`
- `0x180028cc0`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001b5c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180001b5c`

## string_xrefs

- `0x180001b75`: `WriteFile did not write expected data to temporary file`
- `0x180001bd3`: `Call to ::WriteFile failed with HResult 0x%X.`

## pseudocode

```c
void __fastcall win_musl::DataBuffer::WriteBufferToFile(win_musl::DataBuffer *this)
{
  _QWORD *v2; // rbx
  DWORD *v3; // rdx
  void *v4; // rcx
  DWORD v5; // esi
  unsigned int v6; // eax
  int v7; // edx
  signed int v8; // ebp
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-4F8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4D8h] BYREF
  wchar_t v11[512]; // [rsp+100h] [rbp-438h] BYREF

  win_musl::DataBuffer::TestCreateFile(this);
  v2 = (_QWORD *)*((_QWORD *)this + 1);
  while ( 1 )
  {
    v2 = (_QWORD *)*v2;
    if ( v2 == *((_QWORD **)this + 1) )
      break;
    v3 = (DWORD *)v2[3];
    v4 = (void *)*((_QWORD *)this + 8);
    v5 = *v3;
    NumberOfBytesWritten = 0;
    v6 = WriteFile(v4, v3 + 1, v5, &NumberOfBytesWritten, 0);
    v8 = win_musl::HResultFromBool((win_musl *)v6, v7);
    if ( v8 < 0 )
    {
      memset_0(v11, 0, sizeof(v11));
      StringCchPrintfW(v11, 0x200u, L"Call to ::WriteFile failed with HResult 0x%X.", (unsigned int)v8);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x147u,
        v8,
        (struct win_musl::TStringEllipseBase *)v11);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( NumberOfBytesWritten != v5 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x14Bu,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"WriteFile did not write expected data to temporary file");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(this);
}

```

## disassembly

```asm
0x180001b04  push    rbx
0x180001b06  push    rbp
0x180001b07  push    rsi
0x180001b08  push    rdi
0x180001b09  sub     rsp, 518h
0x180001b10  mov     rax, cs:__security_cookie
0x180001b17  xor     rax, rsp
0x180001b1a  mov     [rsp+538h+var_38], rax
0x180001b22  mov     rdi, rcx
0x180001b25  call    ?TestCreateFile@DataBuffer@win_musl@@AEAAXXZ; win_musl::DataBuffer::TestCreateFile(void)
0x180001b2a  mov     rbx, [rdi+8]
0x180001b2e  mov     rbx, [rbx]
0x180001b31  cmp     rbx, [rdi+8]
0x180001b35  jz      loc_180001C2F
0x180001b3b  mov     rdx, [rbx+18h]
0x180001b3f  lea     r9, [rsp+538h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180001b44  mov     rcx, [rdi+40h]; hFile
0x180001b48  xor     eax, eax
0x180001b4a  mov     [rsp+538h+lpOverlapped], rax; lpOverlapped
0x180001b4f  mov     esi, [rdx]
0x180001b51  add     rdx, 4; lpBuffer
0x180001b55  mov     r8d, esi; nNumberOfBytesToWrite
0x180001b58  mov     [rsp+538h+NumberOfBytesWritten], eax
0x180001b5c  call    cs:__imp_WriteFile
0x180001b62  mov     ecx, eax; this
0x180001b64  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180001b69  mov     ebp, eax
0x180001b6b  test    eax, eax
0x180001b6d  js      short loc_180001BBB
0x180001b6f  cmp     [rsp+538h+NumberOfBytesWritten], esi
0x180001b73  jz      short loc_180001B2E
0x180001b75  lea     rax, aWritefileDidNo; "WriteFile did not write expected data t"...
0x180001b7c  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x180001b81  lea     r9, word_18013A0B6
0x180001b88  mov     [rsp+538h+var_510], 8000FFFFh; unsigned int
0x180001b90  lea     r8, aNoFilename; "(no filename)"
0x180001b97  lea     rcx, [rsp+538h+pExceptionObject]; this
0x180001b9c  mov     dword ptr [rsp+538h+lpOverlapped], 14Bh; unsigned int
0x180001ba4  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001ba9  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001bb0  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x180001bb5  call    _CxxThrowException_0
0x180001bbb  xor     edx, edx; Val
0x180001bbd  lea     rcx, [rsp+538h+var_438]; void *
0x180001bc5  mov     r8d, 400h; Size
0x180001bcb  call    memset_0
0x180001bd0  mov     r9d, ebp
0x180001bd3  lea     r8, aCallToWritefil; "Call to ::WriteFile failed with HResult"...
0x180001bda  mov     edx, 200h; unsigned __int64
0x180001bdf  lea     rcx, [rsp+538h+var_438]; wchar_t *
0x180001be7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180001bec  lea     rax, [rsp+538h+var_438]
0x180001bf4  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x180001bf9  lea     r9, word_18013A0B6
0x180001c00  mov     [rsp+538h+var_510], ebp; unsigned int
0x180001c04  lea     r8, aNoFilename; "(no filename)"
0x180001c0b  lea     rcx, [rsp+538h+pExceptionObject]; this
0x180001c10  mov     dword ptr [rsp+538h+lpOverlapped], 147h; unsigned int
0x180001c18  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001c1d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001c24  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x180001c29  call    _CxxThrowException_0
0x180001c2f  mov     rcx, rdi
0x180001c32  call    ?clear@?$list@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXXZ; std::list<win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>>::clear(void)
0x180001c37  mov     rcx, [rsp+538h+var_38]
0x180001c3f  xor     rcx, rsp; StackCookie
0x180001c42  call    __security_check_cookie
0x180001c47  add     rsp, 518h
0x180001c4e  pop     rdi
0x180001c4f  pop     rsi
0x180001c50  pop     rbp
0x180001c51  pop     rbx
0x180001c52  retn
```

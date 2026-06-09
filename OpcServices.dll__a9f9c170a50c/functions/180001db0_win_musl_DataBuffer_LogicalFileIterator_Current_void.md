# win_musl::DataBuffer::LogicalFileIterator::Current(void)

- ea: `0x180001db0`
- end: `0x180001f8b`
- name: `?Current@LogicalFileIterator@DataBuffer@win_musl@@QEAA?AU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@XZ`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002718c`

## callees

- `0x180001db0`
- `0x1800023dc`
- `0x180015a68`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180001e1b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180001e1b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180001ec0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180001ec0`

## string_xrefs

- `0x180001e42`: `Call to ::SetFilePointerEx failed with HResult 0x%X.`
- `0x180001ee7`: `Call to ::ReadFile failed with HResult 0x%X.`

## pseudocode

```c
_QWORD *__fastcall win_musl::DataBuffer::LogicalFileIterator::Current(__int64 a1, _QWORD *a2)
{
  LARGE_INTEGER v4; // rdx
  void *v5; // rcx
  unsigned int v6; // eax
  int v7; // edx
  signed int v8; // esi
  __int64 v9; // r8
  void *v10; // rdx
  DWORD v11; // r8d
  unsigned int File; // eax
  int v13; // edx
  signed int v14; // esi
  LARGE_INTEGER NewFilePointer[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v18[512]; // [rsp+F0h] [rbp-10h] BYREF

  v4 = *(LARGE_INTEGER *)(a1 + 16);
  if ( v4.QuadPart == *(_QWORD *)(a1 + 24) )
  {
    *a2 = 0;
    a2[1] = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 32) != v4.QuadPart )
    {
      v5 = *(void **)(a1 + 8);
      NewFilePointer[0].QuadPart = 0;
      v6 = SetFilePointerEx(v5, v4, NewFilePointer, 0);
      v8 = win_musl::HResultFromBool((win_musl *)v6, v7);
      if ( v8 < 0 )
      {
        memset_0(v18, 0, sizeof(v18));
        StringCchPrintfW(v18, 0x200u, L"Call to ::SetFilePointerEx failed with HResult 0x%X.", (unsigned int)v8);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x31Cu,
          v8,
          (struct win_musl::TStringEllipseBase *)v18);
        throw (SplException::THResultException *)pExceptionObject;
      }
      v9 = *(_QWORD *)(a1 + 48);
      v10 = *(void **)(v9 + 8);
      if ( v10 )
        v11 = *(_QWORD *)(v9 + 16) - (_DWORD)v10;
      else
        v11 = 0;
      File = ReadFile(*(HANDLE *)(a1 + 8), v10, v11, (LPDWORD)(a1 + 56), 0);
      v14 = win_musl::HResultFromBool((win_musl *)File, v13);
      if ( v14 < 0 )
      {
        memset_0(v18, 0, sizeof(v18));
        StringCchPrintfW(v18, 0x200u, L"Call to ::ReadFile failed with HResult 0x%X.", (unsigned int)v14);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x326u,
          v14,
          (struct win_musl::TStringEllipseBase *)v18);
        throw (SplException::THResultException *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
    }
    NewFilePointer[0].QuadPart = *(unsigned int *)(a1 + 56);
    NewFilePointer[1] = *(LARGE_INTEGER *)(*(_QWORD *)(a1 + 48) + 8LL);
    *(_OWORD *)a2 = *(_OWORD *)&NewFilePointer[0].LowPart;
  }
  return a2;
}

```

## disassembly

```asm
0x180001db0  mov     [rsp-8+arg_10], rbx
0x180001db5  push    rbp
0x180001db6  push    rsi
0x180001db7  push    rdi
0x180001db8  lea     rbp, [rsp-400h]
0x180001dc0  sub     rsp, 500h
0x180001dc7  mov     rax, cs:__security_cookie
0x180001dce  xor     rax, rsp
0x180001dd1  mov     [rbp+410h+var_20], rax
0x180001dd8  mov     rdi, rdx
0x180001ddb  mov     rbx, rcx
0x180001dde  mov     rdx, [rcx+10h]; liDistanceToMove
0x180001de2  cmp     rdx, [rcx+18h]
0x180001de6  jnz     short loc_180001DFC
0x180001de8  mov     qword ptr [rdi], 0
0x180001def  mov     qword ptr [rdi+8], 0
0x180001df7  jmp     loc_180001F66
0x180001dfc  cmp     [rcx+20h], rdx
0x180001e00  jz      loc_180001F43
0x180001e06  mov     rcx, [rcx+8]; hFile
0x180001e0a  lea     r8, [rsp+510h+NewFilePointer]; lpNewFilePointer
0x180001e0f  xor     r9d, r9d; dwMoveMethod
0x180001e12  mov     qword ptr [rsp+510h+NewFilePointer], 0
0x180001e1b  call    cs:__imp_SetFilePointerEx
0x180001e21  mov     ecx, eax; this
0x180001e23  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180001e28  mov     esi, eax
0x180001e2a  test    eax, eax
0x180001e2c  jns     short loc_180001E96
0x180001e2e  xor     edx, edx; Val
0x180001e30  lea     rcx, [rbp+410h+var_420]; void *
0x180001e34  mov     r8d, 400h; Size
0x180001e3a  call    memset_0
0x180001e3f  mov     r9d, esi
0x180001e42  lea     r8, aCallToSetfilep; "Call to ::SetFilePointerEx failed with "...
0x180001e49  mov     edx, 200h; unsigned __int64
0x180001e4e  lea     rcx, [rbp+410h+var_420]; wchar_t *
0x180001e52  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180001e57  lea     rax, [rbp+410h+var_420]
0x180001e5b  mov     [rsp+510h+var_4E0], rax; struct win_musl::TStringEllipseBase *
0x180001e60  lea     r9, word_18013A0B6
0x180001e67  mov     [rsp+510h+var_4E8], esi; unsigned int
0x180001e6b  lea     r8, aNoFilename; "(no filename)"
0x180001e72  lea     rcx, [rsp+510h+pExceptionObject]; this
0x180001e77  mov     dword ptr [rsp+510h+lpOverlapped], 31Ch; unsigned int
0x180001e7f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001e84  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001e8b  lea     rcx, [rsp+510h+pExceptionObject]; pExceptionObject
0x180001e90  call    _CxxThrowException_0
0x180001e96  mov     r8, [rbx+30h]
0x180001e9a  mov     rdx, [r8+8]; lpBuffer
0x180001e9e  test    rdx, rdx
0x180001ea1  jnz     short loc_180001EA8
0x180001ea3  xor     r8d, r8d
0x180001ea6  jmp     short loc_180001EAF
0x180001ea8  mov     r8, [r8+10h]
0x180001eac  sub     r8, rdx; nNumberOfBytesToRead
0x180001eaf  mov     rcx, [rbx+8]; hFile
0x180001eb3  lea     r9, [rbx+38h]; lpNumberOfBytesRead
0x180001eb7  mov     [rsp+510h+lpOverlapped], 0; lpOverlapped
0x180001ec0  call    cs:__imp_ReadFile
0x180001ec6  mov     ecx, eax; this
0x180001ec8  call    ?HResultFromBool@win_musl@@YAJH@Z; win_musl::HResultFromBool(int)
0x180001ecd  mov     esi, eax
0x180001ecf  test    eax, eax
0x180001ed1  jns     short loc_180001F3B
0x180001ed3  xor     edx, edx; Val
0x180001ed5  lea     rcx, [rbp+410h+var_420]; void *
0x180001ed9  mov     r8d, 400h; Size
0x180001edf  call    memset_0
0x180001ee4  mov     r9d, esi
0x180001ee7  lea     r8, aCallToReadfile; "Call to ::ReadFile failed with HResult "...
0x180001eee  mov     edx, 200h; unsigned __int64
0x180001ef3  lea     rcx, [rbp+410h+var_420]; wchar_t *
0x180001ef7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180001efc  lea     rax, [rbp+410h+var_420]
0x180001f00  mov     [rsp+510h+var_4E0], rax; struct win_musl::TStringEllipseBase *
0x180001f05  lea     r9, word_18013A0B6
0x180001f0c  mov     [rsp+510h+var_4E8], esi; unsigned int
0x180001f10  lea     r8, aNoFilename; "(no filename)"
0x180001f17  lea     rcx, [rsp+510h+pExceptionObject]; this
0x180001f1c  mov     dword ptr [rsp+510h+lpOverlapped], 326h; unsigned int
0x180001f24  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180001f29  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180001f30  lea     rcx, [rsp+510h+pExceptionObject]; pExceptionObject
0x180001f35  call    _CxxThrowException_0
0x180001f3b  mov     rax, [rbx+10h]
0x180001f3f  mov     [rbx+20h], rax
0x180001f43  mov     eax, [rbx+38h]
0x180001f46  mov     dword ptr [rsp+510h+NewFilePointer], eax
0x180001f4a  xor     eax, eax
0x180001f4c  mov     dword ptr [rsp+510h+NewFilePointer+4], eax
0x180001f50  mov     rax, [rbx+30h]
0x180001f54  mov     rcx, [rax+8]
0x180001f58  mov     qword ptr [rsp+510h+NewFilePointer+8], rcx
0x180001f5d  movups  xmm0, xmmword ptr [rsp+510h+NewFilePointer]
0x180001f62  movdqu  xmmword ptr [rdi], xmm0
0x180001f66  mov     rax, rdi
0x180001f69  mov     rcx, [rbp+410h+var_20]
0x180001f70  xor     rcx, rsp; StackCookie
0x180001f73  call    __security_check_cookie
0x180001f78  mov     rbx, [rsp+510h+arg_10]
0x180001f80  add     rsp, 500h
0x180001f87  pop     rdi
0x180001f88  pop     rsi
0x180001f89  pop     rbp
0x180001f8a  retn
```

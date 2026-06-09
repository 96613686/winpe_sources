# Uev::Common::ReadUtf8File(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x140026c48`
- end: `0x140026eea`
- name: `?ReadUtf8File@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14003c570`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004a6c`
- `0x140004ab4`
- `0x14000c3a4`
- `0x14000d1d8`
- `0x14000d2d8`
- `0x1400131ec`
- `0x140014998`
- `0x140026c48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140026e3b`
- `KERNEL32!GetLastError` at `0x140026e76`
- `KERNEL32!GetLastError` at `0x140026eb0`
- `KERNEL32!GetLastError` at `0x140026e3b`
- `KERNEL32!GetLastError` at `0x140026e76`
- `KERNEL32!GetLastError` at `0x140026eb0`
- `KERNEL32!GetFileSize` at `0x140026cc5`
- `KERNEL32!GetFileSize` at `0x140026cc5`
- `KERNEL32!MultiByteToWideChar` at `0x140026d4a`
- `KERNEL32!MultiByteToWideChar` at `0x140026d98`
- `KERNEL32!MultiByteToWideChar` at `0x140026d4a`
- `KERNEL32!MultiByteToWideChar` at `0x140026d98`
- `KERNEL32!CreateFileW` at `0x140026ca3`
- `KERNEL32!CreateFileW` at `0x140026ca3`
- `KERNEL32!ReadFile` at `0x140026cff`
- `KERNEL32!ReadFile` at `0x140026cff`

## string_xrefs

- `0x140026e7e`: `File open error`
- `0x140026e44`: `File read error`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Uev::Common::ReadUtf8File(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rbx
  DWORD FileSize; // eax
  DWORD v5; // r14d
  CHAR *v6; // rsi
  const CHAR *v7; // r12
  int v8; // eax
  unsigned __int64 v9; // r13
  WCHAR *v10; // r15
  __int64 v11; // r8
  char *v12; // r14
  char *v13; // rcx
  DWORD v15; // ebx
  DWORD LastError; // ebx
  DWORD v17; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-99h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-91h] BYREF
  _QWORD v20[4]; // [rsp+60h] [rbp-79h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-59h] BYREF

  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v19[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    std::wstring::wstring(v20, L"File open error");
    Uev::SystemException::SystemException(pExceptionObject, v20, LastError);
    throw (Uev::SystemException *)pExceptionObject;
  }
  FileSize = GetFileSize(FileW, 0);
  v5 = FileSize;
  if ( FileSize == -1 )
  {
    v17 = GetLastError();
    std::wstring::wstring(v20, L"Unable to get file size");
    Uev::SystemException::SystemException(pExceptionObject, v20, v17);
    throw (Uev::SystemException *)pExceptionObject;
  }
  v6 = (CHAR *)operator new[](FileSize);
  v19[1] = v6;
  NumberOfBytesRead = 0;
  if ( !ReadFile(FileW, v6, v5, &NumberOfBytesRead, 0) )
  {
    v15 = GetLastError();
    std::wstring::wstring(v20, L"File read error");
    Uev::SystemException::SystemException(pExceptionObject, v20, v15);
    throw (Uev::SystemException *)pExceptionObject;
  }
  v7 = v6;
  Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::Close(v19);
  if ( *v6 == -17 && v6[1] == -69 && v6[2] == -65 )
  {
    v7 = v6 + 3;
    v5 -= 3;
  }
  v8 = MultiByteToWideChar(0xFDE9u, 0, v7, v5, 0, 0);
  v9 = v8;
  if ( v8 <= 0 )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v13 = (char *)a2;
    else
      v13 = *(char **)a2;
    *(_QWORD *)(a2 + 16) = 0;
    *(_WORD *)v13 = 0;
  }
  else
  {
    v10 = (WCHAR *)operator new[](saturated_mul(v8, 2u));
    v19[2] = v10;
    MultiByteToWideChar(0xFDE9u, 0, v7, v5, v10, v9);
    if ( v9 > *(_QWORD *)(a2 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)a2,
        v9,
        v11,
        v10);
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v12 = (char *)a2;
      else
        v12 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = v9;
      memmove_0(v12, v10, 2 * v9);
      *(_WORD *)&v12[2 * v9] = 0;
    }
    operator delete(v10);
  }
  operator delete(v6);
  return Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(v19);
}

```

## disassembly

```asm
0x140026c48  mov     [rsp-8+arg_10], rbx
0x140026c4d  push    rbp
0x140026c4e  push    rsi
0x140026c4f  push    rdi
0x140026c50  push    r12
0x140026c52  push    r13
0x140026c54  push    r14
0x140026c56  push    r15
0x140026c58  lea     rbp, [rsp-27h]
0x140026c5d  sub     rsp, 100h
0x140026c64  mov     rax, cs:__security_cookie
0x140026c6b  xor     rax, rsp
0x140026c6e  mov     [rbp+57h+var_40], rax
0x140026c72  mov     rdi, rdx
0x140026c75  cmp     qword ptr [rcx+18h], 7
0x140026c7a  jbe     short loc_140026C7F
0x140026c7c  mov     rcx, [rcx]; lpFileName
0x140026c7f  xor     r15d, r15d
0x140026c82  mov     [rsp+130h+hTemplateFile], r15; hTemplateFile
0x140026c87  mov     [rsp+130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140026c8f  mov     [rsp+130h+dwCreationDisposition], 3; dwCreationDisposition
0x140026c97  xor     r9d, r9d; lpSecurityAttributes
0x140026c9a  mov     edx, 80000000h; dwDesiredAccess
0x140026c9f  lea     r8d, [r15+1]; dwShareMode
0x140026ca3  call    cs:__imp_CreateFileW
0x140026ca9  mov     rbx, rax
0x140026cac  mov     [rsp+130h+var_E8], rax
0x140026cb1  inc     rax
0x140026cb4  test    rax, 0FFFFFFFFFFFFFFFEh
0x140026cba  jz      loc_140026E76
0x140026cc0  xor     edx, edx; lpFileSizeHigh
0x140026cc2  mov     rcx, rbx; hFile
0x140026cc5  call    cs:__imp_GetFileSize
0x140026ccb  mov     r14d, eax
0x140026cce  cmp     eax, 0FFFFFFFFh
0x140026cd1  jz      loc_140026EB0
0x140026cd7  mov     ecx, r14d; unsigned __int64
0x140026cda  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140026cdf  mov     rsi, rax
0x140026ce2  mov     [rsp+130h+var_E0], rax
0x140026ce7  mov     [rsp+130h+NumberOfBytesRead], r15d
0x140026cec  mov     qword ptr [rsp+130h+dwCreationDisposition], r15; lpOverlapped
0x140026cf1  lea     r9, [rsp+130h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140026cf6  mov     r8d, r14d; nNumberOfBytesToRead
0x140026cf9  mov     rdx, rax; lpBuffer
0x140026cfc  mov     rcx, rbx; hFile
0x140026cff  call    cs:__imp_ReadFile
0x140026d05  test    eax, eax
0x140026d07  jz      loc_140026E3B
0x140026d0d  mov     r12, rsi
0x140026d10  lea     rcx, [rsp+130h+var_E8]
0x140026d15  call    ?Close@?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAAXXZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::Close(void)
0x140026d1a  cmp     byte ptr [rsi], 0EFh
0x140026d1d  jnz     short loc_140026D33
0x140026d1f  cmp     byte ptr [rsi+1], 0BBh
0x140026d23  jnz     short loc_140026D33
0x140026d25  cmp     byte ptr [rsi+2], 0BFh
0x140026d29  jnz     short loc_140026D33
0x140026d2b  lea     r12, [rsi+3]
0x140026d2f  add     r14d, 0FFFFFFFDh
0x140026d33  mov     [rsp+130h+dwFlagsAndAttributes], r15d; cchWideChar
0x140026d38  mov     qword ptr [rsp+130h+dwCreationDisposition], r15; lpWideCharStr
0x140026d3d  mov     r9d, r14d; cbMultiByte
0x140026d40  mov     r8, r12; lpMultiByteStr
0x140026d43  xor     edx, edx; dwFlags
0x140026d45  mov     ecx, 0FDE9h; CodePage
0x140026d4a  call    cs:__imp_MultiByteToWideChar
0x140026d50  movsxd  r13, eax
0x140026d53  test    eax, eax
0x140026d55  jle     loc_140026DEA
0x140026d5b  mov     rbx, r13
0x140026d5e  mov     eax, 2
0x140026d63  mul     r13
0x140026d66  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x140026d6d  cmovb   rax, rdx
0x140026d71  mov     rcx, rax; unsigned __int64
0x140026d74  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140026d79  mov     r15, rax
0x140026d7c  mov     [rsp+130h+var_D8], rax
0x140026d81  mov     [rsp+130h+dwFlagsAndAttributes], r13d; cchWideChar
0x140026d86  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; lpWideCharStr
0x140026d8b  mov     r9d, r14d; cbMultiByte
0x140026d8e  mov     r8, r12; lpMultiByteStr
0x140026d91  xor     edx, edx; dwFlags
0x140026d93  mov     ecx, 0FDE9h; CodePage
0x140026d98  call    cs:__imp_MultiByteToWideChar
0x140026d9e  cmp     r13, [rdi+18h]
0x140026da2  ja      short loc_140026DD1
0x140026da4  cmp     qword ptr [rdi+18h], 7
0x140026da9  jbe     short loc_140026DB0
0x140026dab  mov     r14, [rdi]
0x140026dae  jmp     short loc_140026DB3
0x140026db0  mov     r14, rdi
0x140026db3  mov     [rdi+10h], rbx
0x140026db7  add     rbx, rbx
0x140026dba  mov     r8, rbx; Size
0x140026dbd  mov     rdx, r15; Src
0x140026dc0  mov     rcx, r14; void *
0x140026dc3  call    memmove_0
0x140026dc8  xor     eax, eax
0x140026dca  mov     [rbx+r14], ax
0x140026dcf  jmp     short loc_140026DE0
0x140026dd1  mov     r9, r15
0x140026dd4  mov     rdx, rbx
0x140026dd7  mov     rcx, rdi
0x140026dda  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140026ddf  nop
0x140026de0  mov     rcx, r15; Block
0x140026de3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140026de8  jmp     short loc_140026E01
0x140026dea  cmp     qword ptr [rdi+18h], 7
0x140026def  jbe     short loc_140026DF6
0x140026df1  mov     rcx, [rdi]
0x140026df4  jmp     short loc_140026DF9
0x140026df6  mov     rcx, rdi
0x140026df9  mov     [rdi+10h], r15
0x140026dfd  mov     [rcx], r15w
0x140026e01  mov     rcx, rsi; Block
0x140026e04  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140026e09  nop
0x140026e0a  lea     rcx, [rsp+130h+var_E8]
0x140026e0f  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x140026e14  mov     rcx, [rbp+57h+var_40]
0x140026e18  xor     rcx, rsp; StackCookie
0x140026e1b  call    __security_check_cookie
0x140026e20  mov     rbx, [rsp+130h+arg_10]
0x140026e28  add     rsp, 100h
0x140026e2f  pop     r15
0x140026e31  pop     r14
0x140026e33  pop     r13
0x140026e35  pop     r12
0x140026e37  pop     rdi
0x140026e38  pop     rsi
0x140026e39  pop     rbp
0x140026e3a  retn
0x140026e3b  call    cs:__imp_GetLastError
0x140026e41  nop
0x140026e42  mov     ebx, eax
0x140026e44  lea     rdx, aFileReadError; "File read error"
0x140026e4b  lea     rcx, [rbp+57h+var_D0]
0x140026e4f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140026e54  nop
0x140026e55  mov     r8d, ebx
0x140026e58  lea     rdx, [rbp+57h+var_D0]
0x140026e5c  lea     rcx, [rbp+57h+pExceptionObject]
0x140026e60  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140026e65  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140026e6c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140026e70  call    _CxxThrowException_0
0x140026e76  call    cs:__imp_GetLastError
0x140026e7c  mov     ebx, eax
0x140026e7e  lea     rdx, aFileOpenError; "File open error"
0x140026e85  lea     rcx, [rbp+57h+var_D0]
0x140026e89  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140026e8e  nop
0x140026e8f  mov     r8d, ebx
0x140026e92  lea     rdx, [rbp+57h+var_D0]
0x140026e96  lea     rcx, [rbp+57h+pExceptionObject]
0x140026e9a  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140026e9f  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140026ea6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140026eaa  call    _CxxThrowException_0
0x140026eb0  call    cs:__imp_GetLastError
0x140026eb6  mov     ebx, eax
0x140026eb8  lea     rdx, aUnableToGetFil; "Unable to get file size"
0x140026ebf  lea     rcx, [rbp+57h+var_D0]
0x140026ec3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140026ec8  nop
0x140026ec9  mov     r8d, ebx
0x140026ecc  lea     rdx, [rbp+57h+var_D0]
0x140026ed0  lea     rcx, [rbp+57h+pExceptionObject]
0x140026ed4  call    ??0SystemException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::SystemException::SystemException(std::wstring const &,ulong)
0x140026ed9  lea     rdx, _TI3?AVSystemException@Uev@@; pThrowInfo
0x140026ee0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140026ee4  call    _CxxThrowException_0
```

# OFile::TryWrite(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180020a7c`
- end: `0x180020b46`
- name: `?TryWrite@OFile@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021610`

## callees

- `0x180005c70`
- `0x180020a7c`
- `0x180021eec`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020b13`
- `KERNEL32!GetLastError` at `0x180020b13`
- `KERNEL32!WriteFile` at `0x180020ac9`
- `KERNEL32!WriteFile` at `0x180020ac9`

## string_xrefs

- `0x180020af1`: `trying to write to a from a file that's not open`
- `0x180020b1c`: `write to file failed`

## pseudocode

```c
char __fastcall OFile::TryWrite(__int64 a1, const void **a2)
{
  void *v2; // rcx
  const void *v3; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-748h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+40h] [rbp-738h] BYREF
  _BYTE v9[912]; // [rsp+3D0h] [rbp-3A8h] BYREF

  v2 = *(void **)(a1 + 48);
  if ( v2 == (void *)-1LL )
  {
    OException::OException(pExceptionObject, a2, L"trying to write to a from a file that's not open");
    throw (OException *)pExceptionObject;
  }
  NumberOfBytesWritten = 0;
  v3 = a2;
  if ( (unsigned __int64)a2[3] > 0xF )
    v3 = *a2;
  if ( !WriteFile(v2, v3, *((_DWORD *)a2 + 4), &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    OException::OException(v9, v6, LastError, L"write to file failed");
    throw (OException *)v9;
  }
  return 1;
}

```

## disassembly

```asm
0x180020a7c  sub     rsp, 778h
0x180020a83  mov     rax, cs:__security_cookie
0x180020a8a  xor     rax, rsp
0x180020a8d  mov     [rsp+778h+var_18], rax
0x180020a95  mov     rcx, [rcx+30h]; hFile
0x180020a99  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020a9d  jz      short loc_180020AF1
0x180020a9f  mov     [rsp+778h+NumberOfBytesWritten], 0
0x180020aa7  mov     rax, rdx
0x180020aaa  cmp     qword ptr [rdx+18h], 0Fh
0x180020aaf  jbe     short loc_180020AB4
0x180020ab1  mov     rax, [rdx]
0x180020ab4  mov     [rsp+778h+lpOverlapped], 0; lpOverlapped
0x180020abd  lea     r9, [rsp+778h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180020ac2  mov     r8d, [rdx+10h]; nNumberOfBytesToWrite
0x180020ac6  mov     rdx, rax; lpBuffer
0x180020ac9  call    cs:__imp_WriteFile
0x180020acf  test    eax, eax
0x180020ad1  jz      short loc_180020B13
0x180020ad3  mov     al, 1
0x180020ad5  jmp     short loc_180020AD9
0x180020ad7  xor     al, al
0x180020ad9  mov     rcx, [rsp+778h+var_18]
0x180020ae1  xor     rcx, rsp; StackCookie
0x180020ae4  call    __security_check_cookie
0x180020ae9  add     rsp, 778h
0x180020af0  retn
0x180020af1  lea     r8, aTryingToWriteT; "trying to write to a from a file that's"...
0x180020af8  lea     rcx, [rsp+778h+pExceptionObject]
0x180020afd  call    ??$?0$0DB@@OException@@QEAA@W4exceptionType@et@@AEAY0DB@$$CB_W@Z; OException::OException(et::exceptionType,wchar_t const (&)[49])
0x180020b02  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020b09  lea     rcx, [rsp+778h+pExceptionObject]; pExceptionObject
0x180020b0e  call    _CxxThrowException
0x180020b13  call    cs:__imp_GetLastError
0x180020b19  mov     r8d, eax
0x180020b1c  lea     r9, aWriteToFileFai; "write to file failed"
0x180020b23  lea     rcx, [rsp+778h+var_3A8]
0x180020b2b  call    ??$?0$0BF@@OException@@QEAA@W4exceptionType@et@@IAEAY0BF@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[21])
0x180020b30  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020b37  lea     rcx, [rsp+778h+var_3A8]; pExceptionObject
0x180020b3f  call    _CxxThrowException
```

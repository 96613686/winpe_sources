# OFile::TryDelete(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180020b48`
- end: `0x180020c4d`
- name: `?TryDelete@OFile@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180020de4`

## callees

- `0x180020b48`
- `0x180021e20`
- `0x180021f80`
- `0x1800266e0`
- `0x1800282a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020b7a`
- `KERNEL32!GetLastError` at `0x180020bbf`
- `KERNEL32!GetLastError` at `0x180020be8`
- `KERNEL32!GetLastError` at `0x180020b7a`
- `KERNEL32!GetLastError` at `0x180020bbf`
- `KERNEL32!GetLastError` at `0x180020be8`
- `KERNEL32!DeleteFileW` at `0x180020b70`
- `KERNEL32!DeleteFileW` at `0x180020bb5`
- `KERNEL32!DeleteFileW` at `0x180020b70`
- `KERNEL32!DeleteFileW` at `0x180020bb5`
- `KERNEL32!SetFileAttributesW` at `0x180020b9e`
- `KERNEL32!SetFileAttributesW` at `0x180020b9e`

## string_xrefs

- `0x180020c20`: `failed to delete file %s`

## pseudocode

```c
char __fastcall OFile::TryDelete(const WCHAR *a1)
{
  const WCHAR *v1; // rbx
  DWORD LastError; // eax
  __int64 v3; // rdx
  const WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  DWORD v7; // eax
  int v8; // edx
  int v9; // r9d
  int v10[4]; // [rsp+30h] [rbp-748h] BYREF
  _BYTE pExceptionObject[912]; // [rsp+40h] [rbp-738h] BYREF
  _BYTE v12[912]; // [rsp+3D0h] [rbp-3A8h] BYREF

  v1 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  if ( !DeleteFileW(a1) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LastError != 5 )
        goto LABEL_13;
      v10[0] = 128;
      v4 = v1;
      if ( *((_QWORD *)v1 + 3) > 7u )
        v4 = *(const WCHAR **)v1;
      if ( !SetFileAttributesW(v4, 0x80u) )
      {
        v7 = GetLastError();
        OException::OException((unsigned int)pExceptionObject, v8, v7, v9, (__int64)v1, (__int64)v10);
        throw (OException *)pExceptionObject;
      }
      v5 = v1;
      if ( *((_QWORD *)v1 + 3) > 7u )
        v5 = *(const WCHAR **)v1;
      if ( !DeleteFileW(v5) )
      {
        LastError = GetLastError();
LABEL_13:
        if ( LastError )
        {
          OException::OException(v12, v3, LastError, L"failed to delete file %s", v1);
          throw (OException *)v12;
        }
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180020b48  push    rbx
0x180020b4a  sub     rsp, 770h
0x180020b51  mov     rax, cs:__security_cookie
0x180020b58  xor     rax, rsp
0x180020b5b  mov     [rsp+778h+var_18], rax
0x180020b63  mov     rbx, rcx
0x180020b66  cmp     qword ptr [rcx+18h], 7
0x180020b6b  jbe     short loc_180020B70
0x180020b6d  mov     rcx, [rcx]; lpFileName
0x180020b70  call    cs:__imp_DeleteFileW
0x180020b76  test    eax, eax
0x180020b78  jnz     short loc_180020BC9
0x180020b7a  call    cs:__imp_GetLastError
0x180020b80  cmp     eax, 2
0x180020b83  jz      short loc_180020BC9
0x180020b85  cmp     eax, 5
0x180020b88  jnz     short loc_180020BC5
0x180020b8a  lea     edx, [rax+7Bh]; dwFileAttributes
0x180020b8d  mov     [rsp+778h+var_748], edx
0x180020b91  mov     rcx, rbx
0x180020b94  cmp     qword ptr [rbx+18h], 7
0x180020b99  jbe     short loc_180020B9E
0x180020b9b  mov     rcx, [rbx]; lpFileName
0x180020b9e  call    cs:__imp_SetFileAttributesW
0x180020ba4  test    eax, eax
0x180020ba6  jz      short loc_180020BE8
0x180020ba8  mov     rcx, rbx
0x180020bab  cmp     qword ptr [rbx+18h], 7
0x180020bb0  jbe     short loc_180020BB5
0x180020bb2  mov     rcx, [rbx]; lpFileName
0x180020bb5  call    cs:__imp_DeleteFileW
0x180020bbb  test    eax, eax
0x180020bbd  jnz     short loc_180020BC9
0x180020bbf  call    cs:__imp_GetLastError
0x180020bc5  test    eax, eax
0x180020bc7  jnz     short loc_180020C1B
0x180020bc9  mov     al, 1
0x180020bcb  jmp     short loc_180020BCF
0x180020bcd  xor     al, al
0x180020bcf  mov     rcx, [rsp+778h+var_18]
0x180020bd7  xor     rcx, rsp; StackCookie
0x180020bda  call    __security_check_cookie
0x180020bdf  add     rsp, 770h
0x180020be6  pop     rbx
0x180020be7  retn
0x180020be8  call    cs:__imp_GetLastError
0x180020bee  mov     r8d, eax
0x180020bf1  lea     rax, [rsp+778h+var_748]
0x180020bf6  mov     [rsp+778h+var_750], rax
0x180020bfb  mov     [rsp+778h+var_758], rbx
0x180020c00  lea     rcx, [rsp+778h+pExceptionObject]
0x180020c05  call    ??$?0$0CC@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@OException@@QEAA@W4exceptionType@et@@IAEAY0CC@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBK@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[34],std::wstring const &,ulong const &)
0x180020c0a  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020c11  lea     rcx, [rsp+778h+pExceptionObject]; pExceptionObject
0x180020c16  call    _CxxThrowException
0x180020c1b  mov     [rsp+778h+var_758], rbx
0x180020c20  lea     r9, aFailedToDelete; "failed to delete file %s"
0x180020c27  mov     r8d, eax
0x180020c2a  lea     rcx, [rsp+778h+var_3A8]
0x180020c32  call    ??$?0$0BJ@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@OException@@QEAA@W4exceptionType@et@@IAEAY0BJ@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[25],std::wstring const &)
0x180020c37  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180020c3e  lea     rcx, [rsp+778h+var_3A8]; pExceptionObject
0x180020c46  call    _CxxThrowException
```

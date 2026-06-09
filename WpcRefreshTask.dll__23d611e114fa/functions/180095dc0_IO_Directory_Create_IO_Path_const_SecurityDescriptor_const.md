# IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)

- ea: `0x180095dc0`
- end: `0x180095f40`
- name: `?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z`
- size: `384`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c6e8`
- `0x1800670c8`
- `0x180095dc0`
- `0x180096030`
- `0x18009eb84`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180009a80`
- `0x18000e93c`
- `0x180035af4`
- `0x180035e0c`
- `0x180059678`
- `0x180059820`
- `0x180095cf8`
- `0x180095dc0`
- `0x180095f48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180095e29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180095e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e88`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095e7e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095e7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IO::Directory *__fastcall IO::Directory::Create(IO::Directory *a1, const WCHAR *a2, _QWORD *a3)
{
  const WCHAR *v6; // rdx
  WCHAR *v7; // rcx
  struct _SECURITY_ATTRIBUTES *p_pExceptionObject; // rdx
  const WCHAR *v9; // rcx
  signed int LastError; // eax
  signed int v11; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  __int64 pExceptionObject; // [rsp+40h] [rbp-9h] BYREF
  __int128 v17; // [rsp+48h] [rbp-1h]
  WCHAR PathName[4]; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp+37h]

  if ( !IO::Directory::Exists((const struct Path *)a2) )
  {
    IO::Path::GetParent(a2, PathName);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v6 = a2;
    else
      v6 = *(const WCHAR **)a2;
    v7 = PathName;
    if ( v19 > 7 )
      v7 = *(WCHAR **)PathName;
    if ( (unsigned int)_o__wcsicmp(v7, v6) )
    {
      IO::Directory::Create(&pExceptionObject, PathName, 0);
      std::wstring::~wstring(&pExceptionObject);
    }
    if ( a3 )
    {
      pExceptionObject = 24;
      v17 = 0;
      *(_QWORD *)&v17 = *a3;
      p_pExceptionObject = (struct _SECURITY_ATTRIBUTES *)&pExceptionObject;
    }
    else
    {
      p_pExceptionObject = 0;
    }
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v9 = a2;
    else
      v9 = *(const WCHAR **)a2;
    if ( !CreateDirectoryW(v9, p_pExceptionObject) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        if ( v11 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v13 = std::array<unsigned short,16>::data(a2);
            v14 = std::wstring::c_str(v13);
            WPP_SF_Sd(*(_QWORD *)(v15 + 16), 12, (int)WPP_7674bc77c88135f0ee99d8137a75c6ac_Traceguids, v14, v11);
          }
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v11);
          throw (ErrorCodeException *)&pExceptionObject;
        }
      }
    }
    std::wstring::~wstring(PathName);
  }
  IO::Directory::Directory(a1, (const struct Path *)a2);
  return a1;
}

```

## disassembly

```asm
0x180095dc0  mov     [rsp-8+arg_10], rbx
0x180095dc5  push    rbp
0x180095dc6  push    rsi
0x180095dc7  push    rdi
0x180095dc8  lea     rbp, [rsp-47h]
0x180095dcd  sub     rsp, 90h
0x180095dd4  mov     rax, cs:__security_cookie
0x180095ddb  xor     rax, rsp
0x180095dde  mov     [rbp+57h+var_18], rax
0x180095de2  mov     rbx, r8
0x180095de5  mov     rdi, rdx
0x180095de8  mov     rsi, rcx
0x180095deb  mov     [rbp+57h+var_68], rcx
0x180095def  mov     rcx, rdx; struct Path *
0x180095df2  call    ?Exists@Directory@IO@@SA_NAEBVPath@2@@Z; IO::Directory::Exists(IO::Path const &)
0x180095df7  test    al, al
0x180095df9  jnz     loc_180095EB1
0x180095dff  lea     rdx, [rbp+57h+PathName]
0x180095e03  mov     rcx, rdi
0x180095e06  call    ?GetParent@Path@IO@@QEBA?AV12@XZ; IO::Path::GetParent(void)
0x180095e0b  nop
0x180095e0c  cmp     qword ptr [rdi+18h], 7
0x180095e11  jbe     short loc_180095E18
0x180095e13  mov     rdx, [rdi]
0x180095e16  jmp     short loc_180095E1B
0x180095e18  mov     rdx, rdi
0x180095e1b  lea     rcx, [rbp+57h+PathName]
0x180095e1f  cmp     [rbp+57h+var_20], 7
0x180095e24  cmova   rcx, qword ptr [rbp+57h+PathName]
0x180095e29  call    cs:__imp__o__wcsicmp
0x180095e2f  test    eax, eax
0x180095e31  jz      short loc_180095E4C
0x180095e33  xor     r8d, r8d
0x180095e36  lea     rdx, [rbp+57h+PathName]
0x180095e3a  lea     rcx, [rbp+57h+pExceptionObject]
0x180095e3e  call    ?Create@Directory@IO@@SA?AV12@AEBVPath@2@PEBVSecurityDescriptor@@@Z; IO::Directory::Create(IO::Path const &,SecurityDescriptor const *)
0x180095e43  lea     rcx, [rbp+57h+pExceptionObject]
0x180095e47  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095e4c  test    rbx, rbx
0x180095e4f  jz      short loc_180095E6D
0x180095e51  mov     [rbp+57h+pExceptionObject], 18h
0x180095e59  xorps   xmm0, xmm0
0x180095e5c  movups  [rbp+57h+var_58], xmm0
0x180095e60  mov     rax, [rbx]
0x180095e63  mov     qword ptr [rbp+57h+var_58], rax
0x180095e67  lea     rdx, [rbp+57h+pExceptionObject]
0x180095e6b  jmp     short loc_180095E6F
0x180095e6d  xor     edx, edx; lpSecurityAttributes
0x180095e6f  cmp     qword ptr [rdi+18h], 7
0x180095e74  jbe     short loc_180095E7B
0x180095e76  mov     rcx, [rdi]
0x180095e79  jmp     short loc_180095E7E
0x180095e7b  mov     rcx, rdi; lpPathName
0x180095e7e  call    cs:__imp_CreateDirectoryW
0x180095e84  test    eax, eax
0x180095e86  jnz     short loc_180095EA8
0x180095e88  call    cs:__imp_GetLastError
0x180095e8e  mov     ebx, eax
0x180095e90  cmp     eax, 0B7h
0x180095e95  jz      short loc_180095EA8
0x180095e97  test    eax, eax
0x180095e99  jle     short loc_180095EA4
0x180095e9b  movzx   ebx, ax
0x180095e9e  or      ebx, 80070000h
0x180095ea4  test    ebx, ebx
0x180095ea6  js      short loc_180095EDE
0x180095ea8  lea     rcx, [rbp+57h+PathName]
0x180095eac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095eb1  mov     rdx, rdi; struct Path *
0x180095eb4  mov     rcx, rsi; this
0x180095eb7  call    ??0Directory@IO@@QEAA@AEBVPath@1@@Z; IO::Directory::Directory(IO::Path const &)
0x180095ebc  mov     rax, rsi
0x180095ebf  mov     rcx, [rbp+57h+var_18]
0x180095ec3  xor     rcx, rsp; StackCookie
0x180095ec6  call    __security_check_cookie
0x180095ecb  mov     rbx, [rsp+0A0h+arg_10]
0x180095ed3  add     rsp, 90h
0x180095eda  pop     rdi
0x180095edb  pop     rsi
0x180095edc  pop     rbp
0x180095edd  retn
0x180095ede  lea     rax, WPP_GLOBAL_Control
0x180095ee5  mov     r10, cs:WPP_GLOBAL_Control
0x180095eec  cmp     r10, rax
0x180095eef  jz      short loc_180095F24
0x180095ef1  test    byte ptr [r10+1Ch], 1
0x180095ef6  jz      short loc_180095F24
0x180095ef8  mov     rcx, rdi
0x180095efb  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x180095f00  mov     rcx, rax
0x180095f03  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x180095f08  mov     edx, 0Ch
0x180095f0d  mov     [rsp+0A0h+var_80], ebx
0x180095f11  mov     r9, rax
0x180095f14  lea     r8, WPP_7674bc77c88135f0ee99d8137a75c6ac_Traceguids
0x180095f1b  mov     rcx, [r10+10h]
0x180095f1f  call    WPP_SF_Sd
0x180095f24  mov     edx, ebx; int
0x180095f26  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180095f2a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180095f2f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180095f36  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180095f3a  call    _CxxThrowException_0
```

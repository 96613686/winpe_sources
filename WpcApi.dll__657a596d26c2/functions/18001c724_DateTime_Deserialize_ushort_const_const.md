# DateTime::Deserialize(ushort const * const)

- ea: `0x18001c724`
- end: `0x18001c9f3`
- name: `?Deserialize@DateTime@@SA?AV1@QEBG@Z`
- size: `719`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180017ee0`
- `0x180018a70`

## callees

- `0x1800032a0`
- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x180019b38`
- `0x180019bd0`
- `0x18001b19c`
- `0x18001b728`
- `0x18001c724`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c933`
- `KERNEL32!SystemTimeToFileTime` at `0x18001c8df`
- `KERNEL32!SystemTimeToFileTime` at `0x18001c8df`

## pseudocode

```c
__int64 __fastcall DateTime::Deserialize(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rcx
  _QWORD *v4; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // [rsp+20h] [rbp-49h] BYREF
  __int128 v9; // [rsp+28h] [rbp-41h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h]
  struct _FILETIME FileTime; // [rsp+40h] [rbp-29h] BYREF
  __int128 v12; // [rsp+48h] [rbp-21h] BYREF
  __int64 v13; // [rsp+58h] [rbp-11h]
  __int128 v14; // [rsp+60h] [rbp-9h] BYREF
  __int64 v15; // [rsp+70h] [rbp+7h]
  _BYTE pExceptionObject[40]; // [rsp+78h] [rbp+Fh] BYREF
  SYSTEMTIME SystemTime; // [rsp+A0h] [rbp+37h] BYREF

  v8 = a2;
  v14 = 0;
  v15 = 0;
  StringAlgo::Split<unsigned short const *,unsigned short,std::back_insert_iterator<std::vector<std::wstring>>>(
    &v14,
    &v8,
    32);
  v3 = (_QWORD *)v14;
  if ( *((_QWORD *)&v14 + 1) - (_QWORD)v14 != 64 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v12 = 0;
  v13 = 0;
  if ( *(_QWORD *)(v14 + 24) > 7u )
    v3 = *(_QWORD **)v14;
  v8 = v3;
  StringAlgo::Split<unsigned short const *,unsigned short,std::back_insert_iterator<std::vector<std::wstring>>>(
    &v12,
    &v8,
    47);
  if ( *((_QWORD *)&v12 + 1) - (_QWORD)v12 != 96 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v9 = 0;
  v10 = 0;
  v4 = (_QWORD *)(v14 + 32);
  if ( *(_QWORD *)(v14 + 56) > 7u )
    v4 = (_QWORD *)*v4;
  v8 = v4;
  StringAlgo::Split<unsigned short const *,unsigned short,std::back_insert_iterator<std::vector<std::wstring>>>(
    &v9,
    &v8,
    58);
  if ( *((_QWORD *)&v9 + 1) - (_QWORD)v9 != 128 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  SystemTime = 0;
  SystemTime.wMonth = StringAlgo::FromString<unsigned short>();
  SystemTime.wDay = StringAlgo::FromString<unsigned short>();
  SystemTime.wYear = StringAlgo::FromString<unsigned short>();
  SystemTime.wHour = StringAlgo::FromString<unsigned short>();
  SystemTime.wMinute = StringAlgo::FromString<unsigned short>();
  SystemTime.wSecond = StringAlgo::FromString<unsigned short>();
  SystemTime.wMilliseconds = StringAlgo::FromString<unsigned short>();
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_f3a944bc79723267707e4fbb78514ff7_Traceguids, v7);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  DateTime::DateTime(a1, &FileTime);
  std::vector<std::wstring>::~vector<std::wstring>(&v9);
  std::vector<std::wstring>::~vector<std::wstring>(&v12);
  std::vector<std::wstring>::~vector<std::wstring>(&v14);
  return a1;
}

```

## disassembly

```asm
0x18001c724  mov     [rsp-8+arg_10], rbx
0x18001c729  push    rbp
0x18001c72a  lea     rbp, [rsp-57h]
0x18001c72f  sub     rsp, 0C0h
0x18001c736  mov     rax, cs:__security_cookie
0x18001c73d  xor     rax, rsp
0x18001c740  mov     [rbp+57h+var_10], rax
0x18001c744  mov     rbx, rcx
0x18001c747  mov     [rbp+57h+var_A0], rdx
0x18001c74b  xorps   xmm0, xmm0
0x18001c74e  movdqu  [rbp+57h+var_60], xmm0
0x18001c753  mov     [rbp+57h+var_50], 0
0x18001c75b  mov     r8d, 20h ; ' '
0x18001c761  lea     rdx, [rbp+57h+var_A0]
0x18001c765  lea     rcx, [rbp+57h+var_60]
0x18001c769  call    ??$Split@PEBGGV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@StringAlgo@@YA_KV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@AEBQEBGG@Z; StringAlgo::Split<ushort const *,ushort,std::back_insert_iterator<std::vector<std::wstring>>>(std::back_insert_iterator<std::vector<std::wstring>>,ushort const * const &,ushort)
0x18001c76e  mov     rcx, qword ptr [rbp+57h+var_60]
0x18001c772  mov     rax, qword ptr [rbp+57h+var_60+8]
0x18001c776  sub     rax, rcx
0x18001c779  cmp     rax, 40h ; '@'
0x18001c77d  jnz     loc_18001C996
0x18001c783  xorps   xmm0, xmm0
0x18001c786  movdqu  [rbp+57h+var_78], xmm0
0x18001c78b  mov     [rbp+57h+var_68], 0
0x18001c793  cmp     qword ptr [rcx+18h], 7
0x18001c798  jbe     short loc_18001C79D
0x18001c79a  mov     rcx, [rcx]
0x18001c79d  mov     [rbp+57h+var_A0], rcx
0x18001c7a1  mov     r8d, 2Fh ; '/'
0x18001c7a7  lea     rdx, [rbp+57h+var_A0]
0x18001c7ab  lea     rcx, [rbp+57h+var_78]
0x18001c7af  call    ??$Split@PEBGGV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@StringAlgo@@YA_KV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@AEBQEBGG@Z; StringAlgo::Split<ushort const *,ushort,std::back_insert_iterator<std::vector<std::wstring>>>(std::back_insert_iterator<std::vector<std::wstring>>,ushort const * const &,ushort)
0x18001c7b4  mov     rax, qword ptr [rbp+57h+var_78+8]
0x18001c7b8  sub     rax, qword ptr [rbp+57h+var_78]
0x18001c7bc  cmp     rax, 60h ; '`'
0x18001c7c0  jnz     loc_18001C9B5
0x18001c7c6  xorps   xmm0, xmm0
0x18001c7c9  movdqu  [rbp+57h+var_98], xmm0
0x18001c7ce  mov     [rbp+57h+var_88], 0
0x18001c7d6  mov     rax, qword ptr [rbp+57h+var_60]
0x18001c7da  add     rax, 20h ; ' '
0x18001c7de  cmp     qword ptr [rax+18h], 7
0x18001c7e3  jbe     short loc_18001C7E8
0x18001c7e5  mov     rax, [rax]
0x18001c7e8  mov     [rbp+57h+var_A0], rax
0x18001c7ec  mov     r8d, 3Ah ; ':'
0x18001c7f2  lea     rdx, [rbp+57h+var_A0]
0x18001c7f6  lea     rcx, [rbp+57h+var_98]
0x18001c7fa  call    ??$Split@PEBGGV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@StringAlgo@@YA_KV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@AEBQEBGG@Z; StringAlgo::Split<ushort const *,ushort,std::back_insert_iterator<std::vector<std::wstring>>>(std::back_insert_iterator<std::vector<std::wstring>>,ushort const * const &,ushort)
0x18001c7ff  mov     rax, qword ptr [rbp+57h+var_98+8]
0x18001c803  sub     rax, qword ptr [rbp+57h+var_98]
0x18001c807  cmp     rax, 80h
0x18001c80d  jnz     loc_18001C9D4
0x18001c813  xorps   xmm0, xmm0
0x18001c816  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c81a  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001c81e  cmp     qword ptr [rcx+18h], 7
0x18001c823  jbe     short loc_18001C828
0x18001c825  mov     rcx, [rcx]
0x18001c828  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c82d  mov     [rbp+57h+SystemTime.wMonth], ax
0x18001c831  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001c835  add     rcx, 20h ; ' '
0x18001c839  cmp     qword ptr [rcx+18h], 7
0x18001c83e  jbe     short loc_18001C843
0x18001c840  mov     rcx, [rcx]
0x18001c843  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c848  mov     [rbp+57h+SystemTime.wDay], ax
0x18001c84c  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001c850  add     rcx, 40h ; '@'
0x18001c854  cmp     qword ptr [rcx+18h], 7
0x18001c859  jbe     short loc_18001C85E
0x18001c85b  mov     rcx, [rcx]
0x18001c85e  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c863  mov     [rbp+57h+SystemTime.wYear], ax
0x18001c867  mov     rcx, qword ptr [rbp+57h+var_98]
0x18001c86b  cmp     qword ptr [rcx+18h], 7
0x18001c870  jbe     short loc_18001C875
0x18001c872  mov     rcx, [rcx]
0x18001c875  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c87a  mov     [rbp+57h+SystemTime.wHour], ax
0x18001c87e  mov     rcx, qword ptr [rbp+57h+var_98]
0x18001c882  add     rcx, 20h ; ' '
0x18001c886  cmp     qword ptr [rcx+18h], 7
0x18001c88b  jbe     short loc_18001C890
0x18001c88d  mov     rcx, [rcx]
0x18001c890  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c895  mov     [rbp+57h+SystemTime.wMinute], ax
0x18001c899  mov     rcx, qword ptr [rbp+57h+var_98]
0x18001c89d  add     rcx, 40h ; '@'
0x18001c8a1  cmp     qword ptr [rcx+18h], 7
0x18001c8a6  jbe     short loc_18001C8AB
0x18001c8a8  mov     rcx, [rcx]
0x18001c8ab  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c8b0  mov     [rbp+57h+SystemTime.wSecond], ax
0x18001c8b4  mov     rcx, qword ptr [rbp+57h+var_98]
0x18001c8b8  add     rcx, 60h ; '`'
0x18001c8bc  cmp     qword ptr [rcx+18h], 7
0x18001c8c1  jbe     short loc_18001C8C6
0x18001c8c3  mov     rcx, [rcx]
0x18001c8c6  call    ??$FromString@G@StringAlgo@@YAGPEBGPEAPEAX@Z; StringAlgo::FromString<ushort>(ushort const *,void * *)
0x18001c8cb  mov     [rbp+57h+SystemTime.wMilliseconds], ax
0x18001c8cf  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18001c8d7  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001c8db  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c8df  call    cs:__imp_SystemTimeToFileTime
0x18001c8e5  test    eax, eax
0x18001c8e7  jz      short loc_18001C933
0x18001c8e9  lea     rdx, [rbp+57h+FileTime]
0x18001c8ed  mov     rcx, rbx
0x18001c8f0  call    ??0DateTime@@QEAA@AEBU_FILETIME@@W4TimeType@@@Z; DateTime::DateTime(_FILETIME const &,TimeType)
0x18001c8f5  nop
0x18001c8f6  lea     rcx, [rbp+57h+var_98]
0x18001c8fa  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001c8ff  nop
0x18001c900  lea     rcx, [rbp+57h+var_78]
0x18001c904  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001c909  nop
0x18001c90a  lea     rcx, [rbp+57h+var_60]
0x18001c90e  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001c913  mov     rax, rbx
0x18001c916  mov     rcx, [rbp+57h+var_10]
0x18001c91a  xor     rcx, rsp; StackCookie
0x18001c91d  call    __security_check_cookie
0x18001c922  mov     rbx, [rsp+0C0h+arg_10]
0x18001c92a  add     rsp, 0C0h
0x18001c931  pop     rbp
0x18001c932  retn
0x18001c933  call    cs:__imp_GetLastError
0x18001c939  nop
0x18001c93a  mov     ebx, eax
0x18001c93c  test    eax, eax
0x18001c93e  jle     short loc_18001C949
0x18001c940  movzx   ebx, ax
0x18001c943  or      ebx, 80070000h
0x18001c949  lea     rax, WPP_GLOBAL_Control
0x18001c950  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c957  cmp     rcx, rax
0x18001c95a  jz      short loc_18001C97A
0x18001c95c  test    byte ptr [rcx+1Ch], 1
0x18001c960  jz      short loc_18001C97A
0x18001c962  mov     edx, 24h ; '$'
0x18001c967  mov     r9d, ebx
0x18001c96a  lea     r8, WPP_f3a944bc79723267707e4fbb78514ff7_Traceguids
0x18001c971  mov     rcx, [rcx+10h]
0x18001c975  call    WPP_SF_d
0x18001c97a  mov     edx, ebx; int
0x18001c97c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c980  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18001c985  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18001c98c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c990  call    _CxxThrowException_0
0x18001c996  mov     edx, 8000FFFFh; int
0x18001c99b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c99f  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18001c9a4  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18001c9ab  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c9af  call    _CxxThrowException_0
0x18001c9b5  mov     edx, 8000FFFFh; int
0x18001c9ba  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c9be  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18001c9c3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18001c9ca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c9ce  call    _CxxThrowException_0
0x18001c9d4  mov     edx, 8000FFFFh; int
0x18001c9d9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001c9dd  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18001c9e2  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18001c9e9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001c9ed  call    _CxxThrowException_0
```

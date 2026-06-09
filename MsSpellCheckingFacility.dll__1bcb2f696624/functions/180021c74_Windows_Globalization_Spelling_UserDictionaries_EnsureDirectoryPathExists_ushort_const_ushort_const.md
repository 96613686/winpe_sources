# Windows::Globalization::Spelling::UserDictionaries::EnsureDirectoryPathExists(ushort const *,ushort const *)

- ea: `0x180021c74`
- end: `0x180021ec0`
- name: `?EnsureDirectoryPathExists@UserDictionaries@Spelling@Globalization@Windows@@SAXPEBG0@Z`
- size: `588`
- prototype: `void __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001ca80`
- `0x180021234`
- `0x180047278`
- `0x1800554e0`
- `0x18008b420`

## callees

- `0x1800202e4`
- `0x1800206ec`
- `0x180021c74`
- `0x180022408`
- `0x1800366a0`
- `0x1800455bc`
- `0x180046e48`
- `0x18004b6d4`
- `0x180061320`
- `0x180062344`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021e25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021ce5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180021e1b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180021e1b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021d59`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021d59`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021d4c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021dff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021d4c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021dff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x180021dcc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x180021dcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Globalization::Spelling::UserDictionaries::EnsureDirectoryPathExists(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2)
{
  int RoamingAppDataPath; // eax
  int v4; // ebx
  unsigned __int16 *v5; // rbx
  _QWORD *v6; // rdx
  DWORD FileAttributesW; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  const WCHAR *v10; // rsi
  LPWSTR NextComponentW; // rax
  const WCHAR *v12; // rcx
  const WCHAR *v13; // rcx
  __int64 v14; // rcx
  signed int LastError; // ebx
  unsigned __int16 *pExceptionObject; // [rsp+20h] [rbp-89h] BYREF
  LPCWSTR pszPath[3]; // [rsp+28h] [rbp-81h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-69h]
  _QWORD v19[7]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD *v20; // [rsp+88h] [rbp-21h]
  _BYTE v21[56]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+1Fh]
  unsigned __int16 *v23; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pExceptionObject = 0;
  RoamingAppDataPath = Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(&pExceptionObject, a2);
  v4 = RoamingAppDataPath;
  if ( RoamingAppDataPath < 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"OnecoreUAP\\private\\Base\\inc\\SpellerUserDictionaries.h",
      (const char *)(unsigned int)RoamingAppDataPath,
      (int)pExceptionObject);
    LODWORD(pExceptionObject) = v4;
    throw (long *)&pExceptionObject;
  }
  v20 = 0;
  if ( CoTaskMemFree )
  {
    v19[0] = &std::_Func_impl_no_alloc<void (*)(void *),void,void *>::`vftable';
    v19[1] = CoTaskMemFree;
    v20 = v19;
  }
  v22 = 0;
  std::_Func_class<long,enum WORDLIST_TYPE,unsigned short const *>::_Reset_move(v21, v19);
  v5 = pExceptionObject;
  v23 = pExceptionObject;
  if ( v20 )
  {
    v6 = v19;
    LOBYTE(v6) = v20 != v19;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v20 + 32LL))(v20, v6);
    v20 = 0;
  }
  if ( PathFileExistsW(lpFileName) )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(v8, PathIsNotDirectory, lpFileName);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x322,
        (unsigned int)"OnecoreUAP\\private\\Base\\inc\\SpellerUserDictionaries.h",
        (const char *)0x80070057LL,
        (int)pExceptionObject);
      LODWORD(pExceptionObject) = -2147024809;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    v10 = &lpFileName[v9];
    while ( 1 )
    {
      NextComponentW = PathFindNextComponentW(v10);
      v10 = NextComponentW;
      if ( !NextComponentW )
        break;
      std::wstring::wstring(pszPath, lpFileName, NextComponentW);
      v12 = (const WCHAR *)pszPath;
      if ( v18 > 7 )
        v12 = pszPath[0];
      if ( !PathFileExistsW(v12) )
      {
        v13 = (const WCHAR *)pszPath;
        if ( v18 > 7 )
          v13 = pszPath[0];
        if ( !CreateDirectoryW(v13, 0) )
        {
          LastError = GetLastError();
          if ( LastError != 183 )
          {
            if ( (Microsoft_Windows_Spell_CheckingEnableBits & 8) != 0 )
              McTemplateU0z_EventWriteTransfer(v14, UnableToCreateDirectory, lpFileName);
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x33F,
              (unsigned int)"OnecoreUAP\\private\\Base\\inc\\SpellerUserDictionaries.h",
              (const char *)(unsigned int)LastError,
              (int)pExceptionObject);
            LODWORD(pExceptionObject) = LastError;
            throw (long *)&pExceptionObject;
          }
        }
      }
      std::wstring::_Tidy_deallocate(pszPath);
    }
  }
  std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(v21);
}

```

## disassembly

```asm
0x180021c74  mov     [rsp-8+arg_10], rbx
0x180021c79  mov     [rsp-8+arg_18], rsi
0x180021c7e  push    rbp
0x180021c7f  push    rdi
0x180021c80  push    r14
0x180021c82  lea     rbp, [rsp-47h]
0x180021c87  sub     rsp, 0F0h
0x180021c8e  mov     rax, cs:__security_cookie
0x180021c95  xor     rax, rsp
0x180021c98  mov     [rbp+57h+var_20], rax
0x180021c9c  mov     rdi, rcx
0x180021c9f  xor     r14d, r14d
0x180021ca2  mov     [rsp+100h+pExceptionObject], r14; int
0x180021ca7  lea     rcx, [rsp+100h+pExceptionObject]; unsigned __int16 **
0x180021cac  call    ?GetRoamingAppDataPath@SpellerUDFiles@Spelling@Globalization@Windows@@SAJPEAPEAGPEBG@Z; Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(ushort * *,ushort const *)
0x180021cb1  mov     ebx, eax
0x180021cb3  test    eax, eax
0x180021cb5  jns     short loc_180021CE5
0x180021cb7  mov     rcx, [rbp+5Fh]; this
0x180021cbb  mov     r9d, eax; char *
0x180021cbe  lea     r8, aOnecoreuapPriv; "OnecoreUAP\\private\\Base\\inc\\Speller"...
0x180021cc5  mov     edx, 317h; void *
0x180021cca  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180021ccf  mov     dword ptr [rsp+100h+pExceptionObject], ebx
0x180021cd3  lea     rdx, _TI1J; pThrowInfo
0x180021cda  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180021cdf  call    _CxxThrowException_0
0x180021ce5  mov     rax, cs:__imp_CoTaskMemFree
0x180021cec  mov     [rbp+57h+var_78], r14
0x180021cf0  test    rax, rax
0x180021cf3  jz      short loc_180021D0C
0x180021cf5  lea     rcx, ??_7?$_Func_impl_no_alloc@P6AXPEAX@ZXPEAX@std@@6B@; const std::_Func_impl_no_alloc<void (*)(void *),void,void *>::`vftable'
0x180021cfc  mov     [rbp+57h+var_B0], rcx
0x180021d00  mov     [rbp+57h+var_A8], rax
0x180021d04  lea     rax, [rbp+57h+var_B0]
0x180021d08  mov     [rbp+57h+var_78], rax
0x180021d0c  mov     [rbp+57h+var_38], r14
0x180021d10  lea     rdx, [rbp+57h+var_B0]
0x180021d14  lea     rcx, [rbp+57h+var_70]
0x180021d18  call    ?_Reset_move@?$_Func_class@JW4WORDLIST_TYPE@@PEBG@std@@IEAAX$$QEAV12@@Z; std::_Func_class<long,WORDLIST_TYPE,ushort const *>::_Reset_move(std::_Func_class<long,WORDLIST_TYPE,ushort const *> &&)
0x180021d1d  mov     rbx, [rsp+100h+pExceptionObject]
0x180021d22  mov     [rbp+57h+var_30], rbx
0x180021d26  mov     rcx, [rbp+57h+var_78]
0x180021d2a  test    rcx, rcx
0x180021d2d  jz      short loc_180021D49
0x180021d2f  mov     rax, [rcx]
0x180021d32  lea     rdx, [rbp+57h+var_B0]
0x180021d36  cmp     rcx, rdx
0x180021d39  setnz   dl
0x180021d3c  mov     rax, [rax+20h]
0x180021d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d45  mov     [rbp+57h+var_78], r14
0x180021d49  mov     rcx, rdi; pszPath
0x180021d4c  call    cs:__imp_PathFileExistsW
0x180021d52  test    eax, eax
0x180021d54  jz      short loc_180021DB7
0x180021d56  mov     rcx, rdi; lpFileName
0x180021d59  call    cs:__imp_GetFileAttributesW
0x180021d5f  cmp     eax, 0FFFFFFFFh
0x180021d62  jz      short loc_180021D6C
0x180021d64  test    al, 10h
0x180021d66  jnz     loc_180021E93
0x180021d6c  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 4
0x180021d73  jz      short loc_180021D84
0x180021d75  mov     r8, rdi
0x180021d78  lea     rdx, PathIsNotDirectory
0x180021d7f  call    McTemplateU0z_EventWriteTransfer
0x180021d84  mov     rcx, [rbp+5Fh]; this
0x180021d88  mov     ebx, 80070057h
0x180021d8d  mov     r9d, ebx; char *
0x180021d90  lea     r8, aOnecoreuapPriv; "OnecoreUAP\\private\\Base\\inc\\Speller"...
0x180021d97  mov     edx, 322h; void *
0x180021d9c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180021da1  mov     dword ptr [rsp+100h+pExceptionObject], ebx
0x180021da5  lea     rdx, _TI1J; pThrowInfo
0x180021dac  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180021db1  call    _CxxThrowException_0
0x180021db7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021dbb  inc     rax
0x180021dbe  cmp     [rbx+rax*2], r14w
0x180021dc3  jnz     short loc_180021DBB
0x180021dc5  lea     rsi, [rdi+rax*2]
0x180021dc9  mov     rcx, rsi; pszPath
0x180021dcc  call    cs:__imp_PathFindNextComponentW
0x180021dd2  mov     rsi, rax
0x180021dd5  test    rax, rax
0x180021dd8  jz      loc_180021E93
0x180021dde  mov     r8, rax
0x180021de1  mov     rdx, rdi
0x180021de4  lea     rcx, [rsp+100h+pszPath]
0x180021de9  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort> const &)
0x180021dee  nop
0x180021def  lea     rcx, [rsp+100h+pszPath]
0x180021df4  cmp     [rbp+57h+var_C0], 7
0x180021df9  cmova   rcx, [rsp+100h+pszPath]; pszPath
0x180021dff  call    cs:__imp_PathFileExistsW
0x180021e05  test    eax, eax
0x180021e07  jnz     short loc_180021E34
0x180021e09  lea     rcx, [rsp+100h+pszPath]
0x180021e0e  cmp     [rbp+57h+var_C0], 7
0x180021e13  cmova   rcx, [rsp+100h+pszPath]; lpPathName
0x180021e19  xor     edx, edx; lpSecurityAttributes
0x180021e1b  call    cs:__imp_CreateDirectoryW
0x180021e21  test    eax, eax
0x180021e23  jnz     short loc_180021E34
0x180021e25  call    cs:__imp_GetLastError
0x180021e2b  mov     ebx, eax
0x180021e2d  cmp     eax, 0B7h
0x180021e32  jnz     short loc_180021E40
0x180021e34  lea     rcx, [rsp+100h+pszPath]
0x180021e39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021e3e  jmp     short loc_180021DC9
0x180021e40  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 8
0x180021e47  jz      short loc_180021E58
0x180021e49  mov     r8, rdi
0x180021e4c  lea     rdx, UnableToCreateDirectory
0x180021e53  call    McTemplateU0z_EventWriteTransfer
0x180021e58  test    ebx, ebx
0x180021e5a  jle     short loc_180021E65
0x180021e5c  movzx   ebx, bx
0x180021e5f  or      ebx, 80070000h
0x180021e65  mov     rcx, [rbp+5Fh]; this
0x180021e69  mov     r9d, ebx; char *
0x180021e6c  lea     r8, aOnecoreuapPriv; "OnecoreUAP\\private\\Base\\inc\\Speller"...
0x180021e73  mov     edx, 33Fh; void *
0x180021e78  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180021e7d  mov     dword ptr [rsp+100h+pExceptionObject], ebx
0x180021e81  lea     rdx, _TI1J; pThrowInfo
0x180021e88  lea     rcx, [rsp+100h+pExceptionObject]; pExceptionObject
0x180021e8d  call    _CxxThrowException_0
0x180021e93  lea     rcx, [rbp+57h+var_70]
0x180021e97  call    ??1?$unique_ptr@VUserDictionary@@V?$function@$$A6AXPEAVUserDictionary@@@Z@std@@@std@@QEAA@XZ; std::unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>::~unique_ptr<UserDictionary,std::function<void (UserDictionary *)>>(void)
0x180021e9c  mov     rcx, [rbp+57h+var_20]
0x180021ea0  xor     rcx, rsp; StackCookie
0x180021ea3  call    __security_check_cookie
0x180021ea8  lea     r11, [rsp+100h+var_10]
0x180021eb0  mov     rbx, [r11+30h]
0x180021eb4  mov     rsi, [r11+38h]
0x180021eb8  mov     rsp, r11
0x180021ebb  pop     r14
0x180021ebd  pop     rdi
0x180021ebe  pop     rbp
0x180021ebf  retn
```

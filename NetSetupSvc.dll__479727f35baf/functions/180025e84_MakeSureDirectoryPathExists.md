# MakeSureDirectoryPathExists

- ea: `0x180025e84`
- end: `0x18002609b`
- name: `MakeSureDirectoryPathExists`
- size: `535`
- prototype: `BOOL __stdcall(PCSTR DirPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path`

## callers

- `0x1800260a4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x1800182b0`
- `0x18002498c`
- `0x180025e84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180025f44`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180025f44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f8d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025f66`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180025f66`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025f83`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025f83`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180025ec6`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x180025ec6`

## pseudocode

```c
BOOL __stdcall MakeSureDirectoryPathExists(PCSTR DirPath)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  const WCHAR *v3; // rax
  HRESULT v4; // ebx
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // r10
  const wchar_t *i; // rax
  wchar_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  const WCHAR *v12; // rax
  DWORD FileAttributesW; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // rax
  signed int LastError; // ebx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r10
  __int64 v21; // rax
  __int64 v22; // r10
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR ppszRootEnd; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v26[32]; // [rsp+108h] [rbp+8h] BYREF

  std::wstring::wstring(v26, DirPath);
  ppszRootEnd = 0;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v1, v2);
  v4 = PathCchSkipRoot(v3, &ppszRootEnd);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, &WPP_GLOBAL_Control, v5);
      WPP_SF_Sd(*(_QWORD *)(v7 + 16), 11, (unsigned int)WPP_4a7bb80c34923429700e535c78fe3875_Traceguids, v6, v4);
    }
    HResultException::HResultException((HResultException *)pExceptionObject, v4);
    throw (HResultException *)pExceptionObject;
  }
  for ( i = ppszRootEnd; *i; i = ++ppszRootEnd )
  {
    v9 = wcschr(i, 0x5Cu);
    ppszRootEnd = v9;
    if ( !v9 )
      break;
    *v9 = 0;
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v10, v11);
    FileAttributesW = GetFileAttributesW(v12);
    if ( FileAttributesW == -1 )
    {
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, v14, v15);
      if ( !CreateDirectoryW(v16, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, &WPP_GLOBAL_Control, v18);
            WPP_SF_S(*(_QWORD *)(v20 + 16), 12, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids, v19);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          HResultException::HResultException((HResultException *)pExceptionObject, LastError);
          throw (HResultException *)pExceptionObject;
        }
      }
    }
    else if ( (FileAttributesW & 0x10) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26, &WPP_GLOBAL_Control, v15);
        WPP_SF_S(*(_QWORD *)(v22 + 16), 13, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids, v21);
      }
      HResultException::HResultException((HResultException *)pExceptionObject, -2147418113);
      throw (HResultException *)pExceptionObject;
    }
    *ppszRootEnd = 92;
  }
  return std::wstring::_Tidy_deallocate(v26);
}

```

## disassembly

```asm
0x180025e84  push    rbp
0x180025e86  push    rbx
0x180025e87  push    rsi
0x180025e88  push    rdi
0x180025e89  lea     rbp, [rsp-38h]
0x180025e8e  sub     rsp, 138h
0x180025e95  mov     rax, cs:__security_cookie
0x180025e9c  xor     rax, rsp
0x180025e9f  mov     [rbp+50h+var_28], rax
0x180025ea3  mov     rdx, rcx
0x180025ea6  lea     rcx, [rbp+50h+var_48]
0x180025eaa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180025eaf  nop
0x180025eb0  xor     edi, edi
0x180025eb2  mov     [rbp+50h+ppszRootEnd], rdi
0x180025eb6  lea     rcx, [rbp+50h+var_48]
0x180025eba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025ebf  mov     rcx, rax; pszPath
0x180025ec2  lea     rdx, [rbp+50h+ppszRootEnd]; ppszRootEnd
0x180025ec6  call    cs:__imp_PathCchSkipRoot
0x180025ecc  mov     ebx, eax
0x180025ece  test    eax, eax
0x180025ed0  jns     short loc_180025F2D
0x180025ed2  lea     rdx, WPP_GLOBAL_Control
0x180025ed9  mov     r10, cs:WPP_GLOBAL_Control
0x180025ee0  cmp     r10, rdx
0x180025ee3  jz      short loc_180025F0F
0x180025ee5  cmp     byte ptr [r10+19h], 2
0x180025eea  jb      short loc_180025F0F
0x180025eec  lea     rcx, [rbp+50h+var_48]
0x180025ef0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025ef5  mov     r9, rax
0x180025ef8  lea     edx, [rdi+0Bh]
0x180025efb  mov     [rsp+150h+var_130], ebx
0x180025eff  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x180025f06  mov     rcx, [r10+10h]
0x180025f0a  call    WPP_SF_Sd
0x180025f0f  mov     edx, ebx; int
0x180025f11  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180025f16  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180025f1b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180025f22  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180025f27  call    _CxxThrowException_0
0x180025f2d  mov     esi, 5Ch ; '\'
0x180025f32  mov     rax, [rbp+50h+ppszRootEnd]
0x180025f36  cmp     [rax], di
0x180025f39  jz      loc_18002607A
0x180025f3f  mov     edx, esi; Ch
0x180025f41  mov     rcx, rax; Str
0x180025f44  call    cs:__imp_wcschr
0x180025f4a  mov     [rbp+50h+ppszRootEnd], rax
0x180025f4e  test    rax, rax
0x180025f51  jz      loc_18002607A
0x180025f57  mov     [rax], di
0x180025f5a  lea     rcx, [rbp+50h+var_48]
0x180025f5e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025f63  mov     rcx, rax; lpFileName
0x180025f66  call    cs:__imp_GetFileAttributesW
0x180025f6c  cmp     eax, 0FFFFFFFFh
0x180025f6f  jnz     loc_180026002
0x180025f75  lea     rcx, [rbp+50h+var_48]
0x180025f79  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025f7e  mov     rcx, rax; lpPathName
0x180025f81  xor     edx, edx; lpSecurityAttributes
0x180025f83  call    cs:__imp_CreateDirectoryW
0x180025f89  test    eax, eax
0x180025f8b  jnz     short loc_180026006
0x180025f8d  call    cs:__imp_GetLastError
0x180025f93  mov     ebx, eax
0x180025f95  cmp     eax, 0B7h
0x180025f9a  jz      short loc_180026006
0x180025f9c  lea     rdx, WPP_GLOBAL_Control
0x180025fa3  mov     r10, cs:WPP_GLOBAL_Control
0x180025faa  cmp     r10, rdx
0x180025fad  jz      short loc_180025FD7
0x180025faf  cmp     byte ptr [r10+19h], 2
0x180025fb4  jb      short loc_180025FD7
0x180025fb6  lea     rcx, [rbp+50h+var_48]
0x180025fba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025fbf  mov     r9, rax
0x180025fc2  mov     edx, 0Ch
0x180025fc7  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x180025fce  mov     rcx, [r10+10h]
0x180025fd2  call    WPP_SF_S
0x180025fd7  test    ebx, ebx
0x180025fd9  jle     short loc_180025FE4
0x180025fdb  movzx   ebx, bx
0x180025fde  or      ebx, 80070000h
0x180025fe4  mov     edx, ebx; int
0x180025fe6  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180025feb  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180025ff0  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180025ff7  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180025ffc  call    _CxxThrowException_0
0x180026002  test    al, 10h
0x180026004  jz      short loc_18002601E
0x180026006  mov     rax, [rbp+50h+ppszRootEnd]
0x18002600a  mov     [rax], si
0x18002600d  mov     rax, [rbp+50h+ppszRootEnd]
0x180026011  add     rax, 2
0x180026015  mov     [rbp+50h+ppszRootEnd], rax
0x180026019  jmp     loc_180025F36
0x18002601e  lea     rdx, WPP_GLOBAL_Control
0x180026025  mov     r10, cs:WPP_GLOBAL_Control
0x18002602c  cmp     r10, rdx
0x18002602f  jz      short loc_180026059
0x180026031  cmp     byte ptr [r10+19h], 2
0x180026036  jb      short loc_180026059
0x180026038  lea     rcx, [rbp+50h+var_48]
0x18002603c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180026041  mov     r9, rax
0x180026044  mov     edx, 0Dh
0x180026049  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x180026050  mov     rcx, [r10+10h]
0x180026054  call    WPP_SF_S
0x180026059  mov     edx, 8000FFFFh; int
0x18002605e  lea     rcx, [rsp+150h+pExceptionObject]; this
0x180026063  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180026068  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002606f  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x180026074  call    _CxxThrowException_0
0x18002607a  lea     rcx, [rbp+50h+var_48]
0x18002607e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026083  mov     rcx, [rbp+50h+var_28]
0x180026087  xor     rcx, rsp; StackCookie
0x18002608a  call    __security_check_cookie
0x18002608f  add     rsp, 138h
0x180026096  pop     rdi
0x180026097  pop     rsi
0x180026098  pop     rbx
0x180026099  pop     rbp
0x18002609a  retn
```

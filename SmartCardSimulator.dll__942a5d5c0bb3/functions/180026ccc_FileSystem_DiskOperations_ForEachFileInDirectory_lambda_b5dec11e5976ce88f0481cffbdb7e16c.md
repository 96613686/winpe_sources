# FileSystem::DiskOperations::ForEachFileInDirectory__lambda_b5dec11e5976ce88f0481cffbdb7e16c___

- ea: `0x180026ccc`
- end: `0x180026f36`
- name: `FileSystem::DiskOperations::ForEachFileInDirectory__lambda_b5dec11e5976ce88f0481cffbdb7e16c___`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180032eb0`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x18000a960`
- `0x18001e778`
- `0x18001ea9c`
- `0x180024478`
- `0x18002622c`
- `0x180026ccc`
- `0x180029c9c`
- `0x180029d64`
- `0x18002d320`
- `0x180039714`
- `0x18003add0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026e32`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026e32`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026d6b`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026d6b`

## pseudocode

```c
_DWORD *__fastcall FileSystem::DiskOperations::ForEachFileInDirectory__lambda_b5dec11e5976ce88f0481cffbdb7e16c___(
        _DWORD *a1,
        __int64 a2,
        HANDLE *a3,
        __int64 a4)
{
  const WCHAR *v8; // rcx
  char *FirstFileTransactedW; // rbx
  __int64 winerror_if; // rax
  _QWORD *v11; // rax
  bool v12; // di
  __int64 v13; // rdx
  _BYTE *v14; // rdx
  BOOL NextFileW; // eax
  __int64 v16; // rax
  _QWORD *v17; // rax
  bool v18; // di
  __int64 v19; // rdx
  __int64 v20; // rax
  bool v21; // zf
  __int64 v22; // rdx
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-B8h] BYREF
  char *v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[16]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v28[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  _DWORD *v30; // [rsp+88h] [rbp-78h]
  _BYTE v31[8]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName[5]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v33[48]; // [rsp+C0h] [rbp-40h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+F0h] [rbp-10h] BYREF

  v30 = a1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(a1);
  v24 = 1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  std::operator+<unsigned short>(lpFileName, a2);
  v8 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] >= (LPCWSTR)8 )
    v8 = lpFileName[0];
  FirstFileTransactedW = (char *)FindFirstFileTransactedW(
                                   v8,
                                   FindExInfoBasic,
                                   &FindFileData,
                                   FindExSearchNameMatch,
                                   0,
                                   0,
                                   *a3);
  v26 = FirstFileTransactedW;
  winerror_if = make_winerror_if(v25, FirstFileTransactedW + 1 == 0);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, winerror_if);
  a1[1] = 3;
  if ( *a1 )
  {
    if ( *a1 == 18 )
    {
      v24 = 0;
      errorlib::scoped_error<winerror_error::tag>::initiate<long>(a1, &v24);
    }
  }
  else
  {
    FileSystem::DiskOperations::specialDirectories(v28);
    std::wstring::wstring(v33, FindFileData.cFileName);
    v11 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                      v28,
                      v27,
                      v33);
    v12 = *v11 == v29;
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(v33, v13, 0);
    if ( !v12 )
      goto LABEL_8;
    v14 = v25;
LABEL_12:
    v20 = lambda_b5dec11e5976ce88f0481cffbdb7e16c_::operator()(a4, v14, &FindFileData, a3);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, v20);
    v21 = *a1 == 0;
    a1[1] = 3;
    if ( v21 )
    {
LABEL_8:
      while ( 1 )
      {
        a1[1] = 3;
        if ( *a1 )
          break;
        NextFileW = FindNextFileW(FirstFileTransactedW, &FindFileData);
        v16 = make_winerror_if(v25, !NextFileW);
        errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, v16);
        a1[1] = 3;
        if ( *a1 )
        {
          if ( *a1 == 18 )
          {
            v24 = 0;
            errorlib::scoped_error<winerror_error::tag>::initiate<long>(a1, &v24);
          }
          break;
        }
        std::wstring::wstring(v33, FindFileData.cFileName);
        v17 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
                          v28,
                          v31,
                          v33);
        v18 = *v17 == v29;
        LOBYTE(v19) = 1;
        std::wstring::_Tidy(v33, v19, 0);
        if ( v18 )
        {
          v14 = v27;
          goto LABEL_12;
        }
      }
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v28);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v26);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(lpFileName, v22, 0);
  return a1;
}

```

## disassembly

```asm
0x180026ccc  push    rbp
0x180026cce  push    rbx
0x180026ccf  push    rsi
0x180026cd0  push    rdi
0x180026cd1  push    r14
0x180026cd3  push    r15
0x180026cd5  lea     rbp, [rsp-258h]
0x180026cdd  sub     rsp, 358h
0x180026ce4  mov     rax, cs:__security_cookie
0x180026ceb  xor     rax, rsp
0x180026cee  mov     [rbp+280h+var_40], rax
0x180026cf5  mov     r15, r9
0x180026cf8  mov     r14, r8
0x180026cfb  mov     rbx, rdx
0x180026cfe  mov     rsi, rcx
0x180026d01  mov     [rbp+280h+var_2F8], rcx
0x180026d05  mov     [rsp+380h+var_340], 1
0x180026d0d  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180026d12  nop
0x180026d13  mov     [rsp+380h+var_340], 1
0x180026d1b  xor     edx, edx; Val
0x180026d1d  mov     r8d, 250h; Size
0x180026d23  lea     rcx, [rbp+280h+FindFileData]; void *
0x180026d27  call    memset_0
0x180026d2c  mov     rdx, rbx
0x180026d2f  lea     rcx, [rbp+280h+lpFileName]
0x180026d33  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180026d38  nop
0x180026d39  mov     rax, [r14]
0x180026d3c  lea     rcx, [rbp+280h+lpFileName]
0x180026d40  cmp     [rbp+280h+var_2D0], 8
0x180026d45  cmovnb  rcx, [rbp+280h+lpFileName]; lpFileName
0x180026d4a  mov     [rsp+380h+hTransaction], rax; hTransaction
0x180026d4f  mov     [rsp+380h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180026d57  mov     [rsp+380h+lpSearchFilter], 0; lpSearchFilter
0x180026d60  xor     r9d, r9d; fSearchOp
0x180026d63  lea     r8, [rbp+280h+FindFileData]; lpFindFileData
0x180026d67  lea     edx, [r9+1]; fInfoLevelId
0x180026d6b  call    cs:__imp_FindFirstFileTransactedW
0x180026d71  mov     rbx, rax
0x180026d74  mov     [rsp+380h+var_330], rax
0x180026d79  xor     edx, edx
0x180026d7b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026d7f  setz    dl
0x180026d82  lea     rcx, [rsp+380h+var_338]
0x180026d87  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026d8c  mov     rdx, rax
0x180026d8f  mov     rcx, rsi
0x180026d92  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026d97  mov     dword ptr [rsi+4], 3
0x180026d9e  cmp     dword ptr [rsi], 0
0x180026da1  jz      short loc_180026DC6
0x180026da3  cmp     dword ptr [rsi], 12h
0x180026da6  jnz     loc_180026EFA
0x180026dac  mov     [rsp+380h+var_340], 0
0x180026db4  lea     rdx, [rsp+380h+var_340]
0x180026db9  mov     rcx, rsi
0x180026dbc  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180026dc1  jmp     loc_180026EFA
0x180026dc6  lea     rcx, [rsp+380h+var_318]
0x180026dcb  call    ?specialDirectories@DiskOperations@FileSystem@@SA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; FileSystem::DiskOperations::specialDirectories(void)
0x180026dd0  nop
0x180026dd1  lea     rdx, [rbp+280h+var_264]
0x180026dd5  lea     rcx, [rbp+280h+var_2C0]
0x180026dd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180026dde  nop
0x180026ddf  lea     r8, [rbp+280h+var_2C0]
0x180026de3  lea     rdx, [rsp+380h+var_328]
0x180026de8  lea     rcx, [rsp+380h+var_318]
0x180026ded  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180026df2  mov     rcx, [rsp+380h+var_310]
0x180026df7  cmp     [rax], rcx
0x180026dfa  setz    dil
0x180026dfe  xor     r8d, r8d
0x180026e01  mov     dl, 1
0x180026e03  lea     rcx, [rbp+280h+var_2C0]
0x180026e07  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026e0c  test    dil, dil
0x180026e0f  jz      short loc_180026E1B
0x180026e11  lea     rdx, [rsp+380h+var_338]
0x180026e16  jmp     loc_180026EA8
0x180026e1b  mov     dword ptr [rsi+4], 3
0x180026e22  cmp     dword ptr [rsi], 0
0x180026e25  jnz     loc_180026EEF
0x180026e2b  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x180026e2f  mov     rcx, rbx; hFindFile
0x180026e32  call    cs:__imp_FindNextFileW
0x180026e38  xor     edx, edx
0x180026e3a  test    eax, eax
0x180026e3c  setz    dl
0x180026e3f  lea     rcx, [rsp+380h+var_338]
0x180026e44  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026e49  mov     rdx, rax
0x180026e4c  mov     rcx, rsi
0x180026e4f  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026e54  mov     dword ptr [rsi+4], 3
0x180026e5b  cmp     dword ptr [rsi], 0
0x180026e5e  jnz     short loc_180026ED4
0x180026e60  lea     rdx, [rbp+280h+var_264]
0x180026e64  lea     rcx, [rbp+280h+var_2C0]
0x180026e68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180026e6d  nop
0x180026e6e  lea     r8, [rbp+280h+var_2C0]
0x180026e72  lea     rdx, [rbp+280h+var_2F0]
0x180026e76  lea     rcx, [rsp+380h+var_318]
0x180026e7b  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180026e80  mov     rcx, [rsp+380h+var_310]
0x180026e85  cmp     [rax], rcx
0x180026e88  setz    dil
0x180026e8c  xor     r8d, r8d
0x180026e8f  mov     dl, 1
0x180026e91  lea     rcx, [rbp+280h+var_2C0]
0x180026e95  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026e9a  test    dil, dil
0x180026e9d  jz      loc_180026E1B
0x180026ea3  lea     rdx, [rsp+380h+var_328]
0x180026ea8  mov     r9, r14
0x180026eab  lea     r8, [rbp+280h+FindFileData]
0x180026eaf  mov     rcx, r15
0x180026eb2  call    _lambda_b5dec11e5976ce88f0481cffbdb7e16c___operator__
0x180026eb7  mov     rdx, rax
0x180026eba  mov     rcx, rsi
0x180026ebd  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026ec2  cmp     dword ptr [rsi], 0
0x180026ec5  mov     dword ptr [rsi+4], 3
0x180026ecc  jz      loc_180026E1B
0x180026ed2  jmp     short loc_180026EEF
0x180026ed4  cmp     dword ptr [rsi], 12h
0x180026ed7  jnz     short loc_180026EEF
0x180026ed9  mov     [rsp+380h+var_340], 0
0x180026ee1  lea     rdx, [rsp+380h+var_340]
0x180026ee6  mov     rcx, rsi
0x180026ee9  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180026eee  nop
0x180026eef  lea     rcx, [rsp+380h+var_318]
0x180026ef4  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180026ef9  nop
0x180026efa  lea     rcx, [rsp+380h+var_330]
0x180026eff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180026f04  nop
0x180026f05  xor     r8d, r8d
0x180026f08  mov     dl, 1
0x180026f0a  lea     rcx, [rbp+280h+lpFileName]
0x180026f0e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026f13  nop
0x180026f14  mov     rax, rsi
0x180026f17  mov     rcx, [rbp+280h+var_40]
0x180026f1e  xor     rcx, rsp; StackCookie
0x180026f21  call    __security_check_cookie
0x180026f26  add     rsp, 358h
0x180026f2d  pop     r15
0x180026f2f  pop     r14
0x180026f31  pop     rdi
0x180026f32  pop     rsi
0x180026f33  pop     rbx
0x180026f34  pop     rbp
0x180026f35  retn
```

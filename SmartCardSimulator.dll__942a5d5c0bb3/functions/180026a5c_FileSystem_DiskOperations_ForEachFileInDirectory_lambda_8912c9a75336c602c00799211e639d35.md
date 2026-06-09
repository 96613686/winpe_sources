# FileSystem::DiskOperations::ForEachFileInDirectory__lambda_8912c9a75336c602c00799211e639d35___

- ea: `0x180026a5c`
- end: `0x180026cc6`
- name: `FileSystem::DiskOperations::ForEachFileInDirectory__lambda_8912c9a75336c602c00799211e639d35___`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800312c4`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x18000a960`
- `0x18001e778`
- `0x18001ea9c`
- `0x180024478`
- `0x18002622c`
- `0x180026a5c`
- `0x180029c9c`
- `0x180029d64`
- `0x18002cb60`
- `0x180039714`
- `0x18003add0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026bc2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026bc2`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026afb`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026afb`

## pseudocode

```c
_DWORD *__fastcall FileSystem::DiskOperations::ForEachFileInDirectory__lambda_8912c9a75336c602c00799211e639d35___(
        _DWORD *a1,
        __int64 a2,
        HANDLE *a3,
        _QWORD *a4)
{
  const WCHAR *v8; // rcx
  char *FirstFileTransactedW; // rbx
  __int64 winerror_if; // rax
  _QWORD *v11; // rax
  bool v12; // di
  __int64 v13; // rdx
  int *v14; // rdx
  BOOL NextFileW; // eax
  __int64 v16; // rax
  _QWORD *v17; // rax
  bool v18; // di
  __int64 v19; // rdx
  int *v20; // rax
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
    v14 = (int *)v25;
LABEL_12:
    v20 = lambda_8912c9a75336c602c00799211e639d35_::operator()(a4, v14, &FindFileData, a3);
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
          v14 = (int *)v27;
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
0x180026a5c  push    rbp
0x180026a5e  push    rbx
0x180026a5f  push    rsi
0x180026a60  push    rdi
0x180026a61  push    r14
0x180026a63  push    r15
0x180026a65  lea     rbp, [rsp-258h]
0x180026a6d  sub     rsp, 358h
0x180026a74  mov     rax, cs:__security_cookie
0x180026a7b  xor     rax, rsp
0x180026a7e  mov     [rbp+280h+var_40], rax
0x180026a85  mov     r15, r9
0x180026a88  mov     r14, r8
0x180026a8b  mov     rbx, rdx
0x180026a8e  mov     rsi, rcx
0x180026a91  mov     [rbp+280h+var_2F8], rcx
0x180026a95  mov     [rsp+380h+var_340], 1
0x180026a9d  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180026aa2  nop
0x180026aa3  mov     [rsp+380h+var_340], 1
0x180026aab  xor     edx, edx; Val
0x180026aad  mov     r8d, 250h; Size
0x180026ab3  lea     rcx, [rbp+280h+FindFileData]; void *
0x180026ab7  call    memset_0
0x180026abc  mov     rdx, rbx
0x180026abf  lea     rcx, [rbp+280h+lpFileName]
0x180026ac3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180026ac8  nop
0x180026ac9  mov     rax, [r14]
0x180026acc  lea     rcx, [rbp+280h+lpFileName]
0x180026ad0  cmp     [rbp+280h+var_2D0], 8
0x180026ad5  cmovnb  rcx, [rbp+280h+lpFileName]; lpFileName
0x180026ada  mov     [rsp+380h+hTransaction], rax; hTransaction
0x180026adf  mov     [rsp+380h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180026ae7  mov     [rsp+380h+lpSearchFilter], 0; lpSearchFilter
0x180026af0  xor     r9d, r9d; fSearchOp
0x180026af3  lea     r8, [rbp+280h+FindFileData]; lpFindFileData
0x180026af7  lea     edx, [r9+1]; fInfoLevelId
0x180026afb  call    cs:__imp_FindFirstFileTransactedW
0x180026b01  mov     rbx, rax
0x180026b04  mov     [rsp+380h+var_330], rax
0x180026b09  xor     edx, edx
0x180026b0b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026b0f  setz    dl
0x180026b12  lea     rcx, [rsp+380h+var_338]
0x180026b17  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026b1c  mov     rdx, rax
0x180026b1f  mov     rcx, rsi
0x180026b22  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026b27  mov     dword ptr [rsi+4], 3
0x180026b2e  cmp     dword ptr [rsi], 0
0x180026b31  jz      short loc_180026B56
0x180026b33  cmp     dword ptr [rsi], 12h
0x180026b36  jnz     loc_180026C8A
0x180026b3c  mov     [rsp+380h+var_340], 0
0x180026b44  lea     rdx, [rsp+380h+var_340]
0x180026b49  mov     rcx, rsi
0x180026b4c  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180026b51  jmp     loc_180026C8A
0x180026b56  lea     rcx, [rsp+380h+var_318]
0x180026b5b  call    ?specialDirectories@DiskOperations@FileSystem@@SA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; FileSystem::DiskOperations::specialDirectories(void)
0x180026b60  nop
0x180026b61  lea     rdx, [rbp+280h+var_264]
0x180026b65  lea     rcx, [rbp+280h+var_2C0]
0x180026b69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180026b6e  nop
0x180026b6f  lea     r8, [rbp+280h+var_2C0]
0x180026b73  lea     rdx, [rsp+380h+var_328]
0x180026b78  lea     rcx, [rsp+380h+var_318]
0x180026b7d  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180026b82  mov     rcx, [rsp+380h+var_310]
0x180026b87  cmp     [rax], rcx
0x180026b8a  setz    dil
0x180026b8e  xor     r8d, r8d
0x180026b91  mov     dl, 1
0x180026b93  lea     rcx, [rbp+280h+var_2C0]
0x180026b97  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026b9c  test    dil, dil
0x180026b9f  jz      short loc_180026BAB
0x180026ba1  lea     rdx, [rsp+380h+var_338]
0x180026ba6  jmp     loc_180026C38
0x180026bab  mov     dword ptr [rsi+4], 3
0x180026bb2  cmp     dword ptr [rsi], 0
0x180026bb5  jnz     loc_180026C7F
0x180026bbb  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x180026bbf  mov     rcx, rbx; hFindFile
0x180026bc2  call    cs:__imp_FindNextFileW
0x180026bc8  xor     edx, edx
0x180026bca  test    eax, eax
0x180026bcc  setz    dl
0x180026bcf  lea     rcx, [rsp+380h+var_338]
0x180026bd4  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026bd9  mov     rdx, rax
0x180026bdc  mov     rcx, rsi
0x180026bdf  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026be4  mov     dword ptr [rsi+4], 3
0x180026beb  cmp     dword ptr [rsi], 0
0x180026bee  jnz     short loc_180026C64
0x180026bf0  lea     rdx, [rbp+280h+var_264]
0x180026bf4  lea     rcx, [rbp+280h+var_2C0]
0x180026bf8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180026bfd  nop
0x180026bfe  lea     r8, [rbp+280h+var_2C0]
0x180026c02  lea     rdx, [rbp+280h+var_2F0]
0x180026c06  lea     rcx, [rsp+380h+var_318]
0x180026c0b  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180026c10  mov     rcx, [rsp+380h+var_310]
0x180026c15  cmp     [rax], rcx
0x180026c18  setz    dil
0x180026c1c  xor     r8d, r8d
0x180026c1f  mov     dl, 1
0x180026c21  lea     rcx, [rbp+280h+var_2C0]
0x180026c25  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026c2a  test    dil, dil
0x180026c2d  jz      loc_180026BAB
0x180026c33  lea     rdx, [rsp+380h+var_328]
0x180026c38  mov     r9, r14
0x180026c3b  lea     r8, [rbp+280h+FindFileData]
0x180026c3f  mov     rcx, r15
0x180026c42  call    _lambda_8912c9a75336c602c00799211e639d35___operator__
0x180026c47  mov     rdx, rax
0x180026c4a  mov     rcx, rsi
0x180026c4d  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026c52  cmp     dword ptr [rsi], 0
0x180026c55  mov     dword ptr [rsi+4], 3
0x180026c5c  jz      loc_180026BAB
0x180026c62  jmp     short loc_180026C7F
0x180026c64  cmp     dword ptr [rsi], 12h
0x180026c67  jnz     short loc_180026C7F
0x180026c69  mov     [rsp+380h+var_340], 0
0x180026c71  lea     rdx, [rsp+380h+var_340]
0x180026c76  mov     rcx, rsi
0x180026c79  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180026c7e  nop
0x180026c7f  lea     rcx, [rsp+380h+var_318]
0x180026c84  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180026c89  nop
0x180026c8a  lea     rcx, [rsp+380h+var_330]
0x180026c8f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180026c94  nop
0x180026c95  xor     r8d, r8d
0x180026c98  mov     dl, 1
0x180026c9a  lea     rcx, [rbp+280h+lpFileName]
0x180026c9e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026ca3  nop
0x180026ca4  mov     rax, rsi
0x180026ca7  mov     rcx, [rbp+280h+var_40]
0x180026cae  xor     rcx, rsp; StackCookie
0x180026cb1  call    __security_check_cookie
0x180026cb6  add     rsp, 358h
0x180026cbd  pop     r15
0x180026cbf  pop     r14
0x180026cc1  pop     rdi
0x180026cc2  pop     rsi
0x180026cc3  pop     rbx
0x180026cc4  pop     rbp
0x180026cc5  retn
```

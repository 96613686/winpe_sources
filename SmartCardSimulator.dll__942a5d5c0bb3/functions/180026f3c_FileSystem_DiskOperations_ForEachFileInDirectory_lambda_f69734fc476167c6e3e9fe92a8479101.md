# FileSystem::DiskOperations::ForEachFileInDirectory__lambda_f69734fc476167c6e3e9fe92a8479101___

- ea: `0x180026f3c`
- end: `0x1800271a6`
- name: `FileSystem::DiskOperations::ForEachFileInDirectory__lambda_f69734fc476167c6e3e9fe92a8479101___`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180032f7c`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x18000a960`
- `0x18001e778`
- `0x18001ea9c`
- `0x180024478`
- `0x18002622c`
- `0x180026f3c`
- `0x180029c9c`
- `0x180029d64`
- `0x18002e768`
- `0x180039714`
- `0x18003add0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800270a2`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800270a2`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026fdb`
- `KERNEL32!FindFirstFileTransactedW` at `0x180026fdb`

## pseudocode

```c
_DWORD *__fastcall FileSystem::DiskOperations::ForEachFileInDirectory__lambda_f69734fc476167c6e3e9fe92a8479101___(
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
    v20 = lambda_f69734fc476167c6e3e9fe92a8479101_::operator()(a4, v14, &FindFileData, a3);
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
0x180026f3c  push    rbp
0x180026f3e  push    rbx
0x180026f3f  push    rsi
0x180026f40  push    rdi
0x180026f41  push    r14
0x180026f43  push    r15
0x180026f45  lea     rbp, [rsp-258h]
0x180026f4d  sub     rsp, 358h
0x180026f54  mov     rax, cs:__security_cookie
0x180026f5b  xor     rax, rsp
0x180026f5e  mov     [rbp+280h+var_40], rax
0x180026f65  mov     r15, r9
0x180026f68  mov     r14, r8
0x180026f6b  mov     rbx, rdx
0x180026f6e  mov     rsi, rcx
0x180026f71  mov     [rbp+280h+var_2F8], rcx
0x180026f75  mov     [rsp+380h+var_340], 1
0x180026f7d  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180026f82  nop
0x180026f83  mov     [rsp+380h+var_340], 1
0x180026f8b  xor     edx, edx; Val
0x180026f8d  mov     r8d, 250h; Size
0x180026f93  lea     rcx, [rbp+280h+FindFileData]; void *
0x180026f97  call    memset_0
0x180026f9c  mov     rdx, rbx
0x180026f9f  lea     rcx, [rbp+280h+lpFileName]
0x180026fa3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180026fa8  nop
0x180026fa9  mov     rax, [r14]
0x180026fac  lea     rcx, [rbp+280h+lpFileName]
0x180026fb0  cmp     [rbp+280h+var_2D0], 8
0x180026fb5  cmovnb  rcx, [rbp+280h+lpFileName]; lpFileName
0x180026fba  mov     [rsp+380h+hTransaction], rax; hTransaction
0x180026fbf  mov     [rsp+380h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180026fc7  mov     [rsp+380h+lpSearchFilter], 0; lpSearchFilter
0x180026fd0  xor     r9d, r9d; fSearchOp
0x180026fd3  lea     r8, [rbp+280h+FindFileData]; lpFindFileData
0x180026fd7  lea     edx, [r9+1]; fInfoLevelId
0x180026fdb  call    cs:__imp_FindFirstFileTransactedW
0x180026fe1  mov     rbx, rax
0x180026fe4  mov     [rsp+380h+var_330], rax
0x180026fe9  xor     edx, edx
0x180026feb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026fef  setz    dl
0x180026ff2  lea     rcx, [rsp+380h+var_338]
0x180026ff7  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026ffc  mov     rdx, rax
0x180026fff  mov     rcx, rsi
0x180027002  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180027007  mov     dword ptr [rsi+4], 3
0x18002700e  cmp     dword ptr [rsi], 0
0x180027011  jz      short loc_180027036
0x180027013  cmp     dword ptr [rsi], 12h
0x180027016  jnz     loc_18002716A
0x18002701c  mov     [rsp+380h+var_340], 0
0x180027024  lea     rdx, [rsp+380h+var_340]
0x180027029  mov     rcx, rsi
0x18002702c  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180027031  jmp     loc_18002716A
0x180027036  lea     rcx, [rsp+380h+var_318]
0x18002703b  call    ?specialDirectories@DiskOperations@FileSystem@@SA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; FileSystem::DiskOperations::specialDirectories(void)
0x180027040  nop
0x180027041  lea     rdx, [rbp+280h+var_264]
0x180027045  lea     rcx, [rbp+280h+var_2C0]
0x180027049  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002704e  nop
0x18002704f  lea     r8, [rbp+280h+var_2C0]
0x180027053  lea     rdx, [rsp+380h+var_328]
0x180027058  lea     rcx, [rsp+380h+var_318]
0x18002705d  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180027062  mov     rcx, [rsp+380h+var_310]
0x180027067  cmp     [rax], rcx
0x18002706a  setz    dil
0x18002706e  xor     r8d, r8d
0x180027071  mov     dl, 1
0x180027073  lea     rcx, [rbp+280h+var_2C0]
0x180027077  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002707c  test    dil, dil
0x18002707f  jz      short loc_18002708B
0x180027081  lea     rdx, [rsp+380h+var_338]
0x180027086  jmp     loc_180027118
0x18002708b  mov     dword ptr [rsi+4], 3
0x180027092  cmp     dword ptr [rsi], 0
0x180027095  jnz     loc_18002715F
0x18002709b  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x18002709f  mov     rcx, rbx; hFindFile
0x1800270a2  call    cs:__imp_FindNextFileW
0x1800270a8  xor     edx, edx
0x1800270aa  test    eax, eax
0x1800270ac  setz    dl
0x1800270af  lea     rcx, [rsp+380h+var_338]
0x1800270b4  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x1800270b9  mov     rdx, rax
0x1800270bc  mov     rcx, rsi
0x1800270bf  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800270c4  mov     dword ptr [rsi+4], 3
0x1800270cb  cmp     dword ptr [rsi], 0
0x1800270ce  jnz     short loc_180027144
0x1800270d0  lea     rdx, [rbp+280h+var_264]
0x1800270d4  lea     rcx, [rbp+280h+var_2C0]
0x1800270d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800270dd  nop
0x1800270de  lea     r8, [rbp+280h+var_2C0]
0x1800270e2  lea     rdx, [rbp+280h+var_2F0]
0x1800270e6  lea     rcx, [rsp+380h+var_318]
0x1800270eb  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x1800270f0  mov     rcx, [rsp+380h+var_310]
0x1800270f5  cmp     [rax], rcx
0x1800270f8  setz    dil
0x1800270fc  xor     r8d, r8d
0x1800270ff  mov     dl, 1
0x180027101  lea     rcx, [rbp+280h+var_2C0]
0x180027105  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002710a  test    dil, dil
0x18002710d  jz      loc_18002708B
0x180027113  lea     rdx, [rsp+380h+var_328]
0x180027118  mov     r9, r14
0x18002711b  lea     r8, [rbp+280h+FindFileData]
0x18002711f  mov     rcx, r15
0x180027122  call    _lambda_f69734fc476167c6e3e9fe92a8479101___operator__
0x180027127  mov     rdx, rax
0x18002712a  mov     rcx, rsi
0x18002712d  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180027132  cmp     dword ptr [rsi], 0
0x180027135  mov     dword ptr [rsi+4], 3
0x18002713c  jz      loc_18002708B
0x180027142  jmp     short loc_18002715F
0x180027144  cmp     dword ptr [rsi], 12h
0x180027147  jnz     short loc_18002715F
0x180027149  mov     [rsp+380h+var_340], 0
0x180027151  lea     rdx, [rsp+380h+var_340]
0x180027156  mov     rcx, rsi
0x180027159  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x18002715e  nop
0x18002715f  lea     rcx, [rsp+380h+var_318]
0x180027164  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180027169  nop
0x18002716a  lea     rcx, [rsp+380h+var_330]
0x18002716f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180027174  nop
0x180027175  xor     r8d, r8d
0x180027178  mov     dl, 1
0x18002717a  lea     rcx, [rbp+280h+lpFileName]
0x18002717e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027183  nop
0x180027184  mov     rax, rsi
0x180027187  mov     rcx, [rbp+280h+var_40]
0x18002718e  xor     rcx, rsp; StackCookie
0x180027191  call    __security_check_cookie
0x180027196  add     rsp, 358h
0x18002719d  pop     r15
0x18002719f  pop     r14
0x1800271a1  pop     rdi
0x1800271a2  pop     rsi
0x1800271a3  pop     rbx
0x1800271a4  pop     rbp
0x1800271a5  retn
```

# FileSystem::DiskOperations::ForEachFileInDirectory__lambda_02fe1a7375f0e783a68abc3cabcf9f28___

- ea: `0x1800267ec`
- end: `0x180026a56`
- name: `FileSystem::DiskOperations::ForEachFileInDirectory__lambda_02fe1a7375f0e783a68abc3cabcf9f28___`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x180033048`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x18000a960`
- `0x18001e778`
- `0x18001ea9c`
- `0x180024478`
- `0x18002622c`
- `0x1800267ec`
- `0x180029c9c`
- `0x180029d64`
- `0x18002a40c`
- `0x180039714`
- `0x18003add0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026952`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026952`
- `KERNEL32!FindFirstFileTransactedW` at `0x18002688b`
- `KERNEL32!FindFirstFileTransactedW` at `0x18002688b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_DWORD *__fastcall FileSystem::DiskOperations::ForEachFileInDirectory__lambda_02fe1a7375f0e783a68abc3cabcf9f28___(
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
    v20 = lambda_02fe1a7375f0e783a68abc3cabcf9f28_::operator()(a4, v14, &FindFileData, a3);
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
0x1800267ec  push    rbp
0x1800267ee  push    rbx
0x1800267ef  push    rsi
0x1800267f0  push    rdi
0x1800267f1  push    r14
0x1800267f3  push    r15
0x1800267f5  lea     rbp, [rsp-258h]
0x1800267fd  sub     rsp, 358h
0x180026804  mov     rax, cs:__security_cookie
0x18002680b  xor     rax, rsp
0x18002680e  mov     [rbp+280h+var_40], rax
0x180026815  mov     r15, r9
0x180026818  mov     r14, r8
0x18002681b  mov     rbx, rdx
0x18002681e  mov     rsi, rcx
0x180026821  mov     [rbp+280h+var_2F8], rcx
0x180026825  mov     [rsp+380h+var_340], 1
0x18002682d  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180026832  nop
0x180026833  mov     [rsp+380h+var_340], 1
0x18002683b  xor     edx, edx; Val
0x18002683d  mov     r8d, 250h; Size
0x180026843  lea     rcx, [rbp+280h+FindFileData]; void *
0x180026847  call    memset_0
0x18002684c  mov     rdx, rbx
0x18002684f  lea     rcx, [rbp+280h+lpFileName]
0x180026853  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180026858  nop
0x180026859  mov     rax, [r14]
0x18002685c  lea     rcx, [rbp+280h+lpFileName]
0x180026860  cmp     [rbp+280h+var_2D0], 8
0x180026865  cmovnb  rcx, [rbp+280h+lpFileName]; lpFileName
0x18002686a  mov     [rsp+380h+hTransaction], rax; hTransaction
0x18002686f  mov     [rsp+380h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180026877  mov     [rsp+380h+lpSearchFilter], 0; lpSearchFilter
0x180026880  xor     r9d, r9d; fSearchOp
0x180026883  lea     r8, [rbp+280h+FindFileData]; lpFindFileData
0x180026887  lea     edx, [r9+1]; fInfoLevelId
0x18002688b  call    cs:__imp_FindFirstFileTransactedW
0x180026891  mov     rbx, rax
0x180026894  mov     [rsp+380h+var_330], rax
0x180026899  xor     edx, edx
0x18002689b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002689f  setz    dl
0x1800268a2  lea     rcx, [rsp+380h+var_338]
0x1800268a7  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x1800268ac  mov     rdx, rax
0x1800268af  mov     rcx, rsi
0x1800268b2  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800268b7  mov     dword ptr [rsi+4], 3
0x1800268be  cmp     dword ptr [rsi], 0
0x1800268c1  jz      short loc_1800268E6
0x1800268c3  cmp     dword ptr [rsi], 12h
0x1800268c6  jnz     loc_180026A1A
0x1800268cc  mov     [rsp+380h+var_340], 0
0x1800268d4  lea     rdx, [rsp+380h+var_340]
0x1800268d9  mov     rcx, rsi
0x1800268dc  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x1800268e1  jmp     loc_180026A1A
0x1800268e6  lea     rcx, [rsp+380h+var_318]
0x1800268eb  call    ?specialDirectories@DiskOperations@FileSystem@@SA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; FileSystem::DiskOperations::specialDirectories(void)
0x1800268f0  nop
0x1800268f1  lea     rdx, [rbp+280h+var_264]
0x1800268f5  lea     rcx, [rbp+280h+var_2C0]
0x1800268f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800268fe  nop
0x1800268ff  lea     r8, [rbp+280h+var_2C0]
0x180026903  lea     rdx, [rsp+380h+var_328]
0x180026908  lea     rcx, [rsp+380h+var_318]
0x18002690d  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180026912  mov     rcx, [rsp+380h+var_310]
0x180026917  cmp     [rax], rcx
0x18002691a  setz    dil
0x18002691e  xor     r8d, r8d
0x180026921  mov     dl, 1
0x180026923  lea     rcx, [rbp+280h+var_2C0]
0x180026927  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002692c  test    dil, dil
0x18002692f  jz      short loc_18002693B
0x180026931  lea     rdx, [rsp+380h+var_338]
0x180026936  jmp     loc_1800269C8
0x18002693b  mov     dword ptr [rsi+4], 3
0x180026942  cmp     dword ptr [rsi], 0
0x180026945  jnz     loc_180026A0F
0x18002694b  lea     rdx, [rbp+280h+FindFileData]; lpFindFileData
0x18002694f  mov     rcx, rbx; hFindFile
0x180026952  call    cs:__imp_FindNextFileW
0x180026958  xor     edx, edx
0x18002695a  test    eax, eax
0x18002695c  setz    dl
0x18002695f  lea     rcx, [rsp+380h+var_338]
0x180026964  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180026969  mov     rdx, rax
0x18002696c  mov     rcx, rsi
0x18002696f  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180026974  mov     dword ptr [rsi+4], 3
0x18002697b  cmp     dword ptr [rsi], 0
0x18002697e  jnz     short loc_1800269F4
0x180026980  lea     rdx, [rbp+280h+var_264]
0x180026984  lea     rcx, [rbp+280h+var_2C0]
0x180026988  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002698d  nop
0x18002698e  lea     r8, [rbp+280h+var_2C0]
0x180026992  lea     rdx, [rbp+280h+var_2F0]
0x180026996  lea     rcx, [rsp+380h+var_318]
0x18002699b  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x1800269a0  mov     rcx, [rsp+380h+var_310]
0x1800269a5  cmp     [rax], rcx
0x1800269a8  setz    dil
0x1800269ac  xor     r8d, r8d
0x1800269af  mov     dl, 1
0x1800269b1  lea     rcx, [rbp+280h+var_2C0]
0x1800269b5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800269ba  test    dil, dil
0x1800269bd  jz      loc_18002693B
0x1800269c3  lea     rdx, [rsp+380h+var_328]
0x1800269c8  mov     r9, r14
0x1800269cb  lea     r8, [rbp+280h+FindFileData]
0x1800269cf  mov     rcx, r15
0x1800269d2  call    _lambda_02fe1a7375f0e783a68abc3cabcf9f28___operator__
0x1800269d7  mov     rdx, rax
0x1800269da  mov     rcx, rsi
0x1800269dd  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800269e2  cmp     dword ptr [rsi], 0
0x1800269e5  mov     dword ptr [rsi+4], 3
0x1800269ec  jz      loc_18002693B
0x1800269f2  jmp     short loc_180026A0F
0x1800269f4  cmp     dword ptr [rsi], 12h
0x1800269f7  jnz     short loc_180026A0F
0x1800269f9  mov     [rsp+380h+var_340], 0
0x180026a01  lea     rdx, [rsp+380h+var_340]
0x180026a06  mov     rcx, rsi
0x180026a09  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180026a0e  nop
0x180026a0f  lea     rcx, [rsp+380h+var_318]
0x180026a14  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180026a19  nop
0x180026a1a  lea     rcx, [rsp+380h+var_330]
0x180026a1f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180026a24  nop
0x180026a25  xor     r8d, r8d
0x180026a28  mov     dl, 1
0x180026a2a  lea     rcx, [rbp+280h+lpFileName]
0x180026a2e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026a33  nop
0x180026a34  mov     rax, rsi
0x180026a37  mov     rcx, [rbp+280h+var_40]
0x180026a3e  xor     rcx, rsp; StackCookie
0x180026a41  call    __security_check_cookie
0x180026a46  add     rsp, 358h
0x180026a4d  pop     r15
0x180026a4f  pop     r14
0x180026a51  pop     rdi
0x180026a52  pop     rsi
0x180026a53  pop     rbx
0x180026a54  pop     rbp
0x180026a55  retn
```

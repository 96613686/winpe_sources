# FileSystem::DestroyFilesystem(void)

- ea: `0x180031370`
- end: `0x180031630`
- name: `?DestroyFilesystem@FileSystem@@QEAAXXZ`
- size: `704`
- prototype: `void __fastcall(FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001fbb4`

## callees

- `0x180007e44`
- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18000bb10`
- `0x18000f970`
- `0x18001e6fc`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x180029b84`
- `0x18002ade8`
- `0x18002efb8`
- `0x180030254`
- `0x180030c84`
- `0x180031370`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180031508`
- `ktmw32!CommitTransaction` at `0x180031508`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FileSystem::DestroyFilesystem(const WCHAR *this)
{
  __int64 FilesystemTransaction; // rax
  unsigned int v3; // eax
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // ecx
  int v7; // ecx
  _DWORD *v8; // rax
  BOOL v9; // eax
  __int64 winerror_if; // rax
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // ecx
  int v15; // ecx
  char v16[8]; // [rsp+30h] [rbp-79h] BYREF
  int v17; // [rsp+38h] [rbp-71h] BYREF
  int v18; // [rsp+3Ch] [rbp-6Dh]
  HANDLE v19; // [rsp+40h] [rbp-69h] BYREF
  HANDLE TransactionHandle; // [rsp+48h] [rbp-61h] BYREF
  int *v21; // [rsp+50h] [rbp-59h] BYREF
  HANDLE *p_TransactionHandle; // [rsp+58h] [rbp-51h]
  _BYTE *v23; // [rsp+70h] [rbp-39h] BYREF
  __int16 v24; // [rsp+78h] [rbp-31h]
  _BYTE v25[24]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v26[24]; // [rsp+98h] [rbp-11h] BYREF
  _BYTE v27[64]; // [rsp+B0h] [rbp+7h] BYREF
  _QWORD v28[2]; // [rsp+F0h] [rbp+47h] BYREF

  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v17);
  v16[0] = 1;
  lambda_82487310dcc4f633fe54cb15883a1c7d_::_lambda_82487310dcc4f633fe54cb15883a1c7d_(v25, v16, this, &v17);
  lambda_1f2fa7ec6605b0250b290bf8a6443ef1_::operator()(v25);
  v16[0] = 0;
  v23 = v25;
  v24 = 258;
  TransactionHandle = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction((__int64)v26);
  v21 = &v17;
  p_TransactionHandle = &TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v21,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v26);
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v19);
  errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(
    &v19,
    &v17);
  v18 = 3;
  if ( v17 )
  {
    memset_0(v27, 0, sizeof(v27));
    v3 = ReportIndentTracker::Indent();
    v21 = (int *)v27;
    p_TransactionHandle = (HANDLE *)v28;
    LOBYTE(v4) = 95;
    ReportIndentTracker::Format(&v21, v3, v5, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v27,
        v17);
    }
  }
  v6 = v17;
  v17 = (int)v19;
  LODWORD(v19) = v6;
  v7 = v18;
  v18 = HIDWORD(v19);
  HIDWORD(v19) = v7;
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v19);
  HIDWORD(v19) = 4;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v19);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(&v17);
  v19 = TransactionHandle;
  v8 = FileSystem::DiskOperations::DeleteDirectoryOnDisk(&v21, this, &v19);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(v8);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v21);
  v9 = CommitTransaction(TransactionHandle);
  winerror_if = make_winerror_if(&v21, !v9);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v17, winerror_if);
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v19);
  errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(
    &v19,
    &v17);
  v18 = 3;
  if ( v17 )
  {
    memset_0(v27, 0, sizeof(v27));
    v11 = ReportIndentTracker::Indent();
    v21 = (int *)v27;
    p_TransactionHandle = (HANDLE *)v28;
    LOBYTE(v12) = 95;
    ReportIndentTracker::Format(&v21, v11, v13, v12);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v27,
        v17);
    }
  }
  v14 = v17;
  v17 = (int)v19;
  LODWORD(v19) = v14;
  v15 = v18;
  v18 = HIDWORD(v19);
  HIDWORD(v19) = v15;
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v19);
  HIDWORD(v19) = 4;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v19);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(&v17);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TransactionHandle);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_1f2fa7ec6605b0250b290bf8a6443ef1_____::operator()(&v23);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v17);
}

```

## disassembly

```asm
0x180031370  mov     [rsp-8+arg_8], rbx
0x180031375  mov     [rsp-8+arg_10], rsi
0x18003137a  push    rbp
0x18003137b  lea     rbp, [rsp-57h]
0x180031380  sub     rsp, 100h
0x180031387  mov     rax, cs:__security_cookie
0x18003138e  xor     rax, rsp
0x180031391  mov     [rbp+57h+var_10], rax
0x180031395  mov     rbx, rcx
0x180031398  lea     rcx, [rbp+57h+var_C8]
0x18003139c  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x1800313a1  nop
0x1800313a2  mov     [rbp+57h+var_D0], 1
0x1800313a6  lea     r9, [rbp+57h+var_C8]
0x1800313aa  mov     r8, rbx
0x1800313ad  lea     rdx, [rbp+57h+var_D0]
0x1800313b1  lea     rcx, [rbp+57h+var_80]
0x1800313b5  call    _lambda_82487310dcc4f633fe54cb15883a1c7d____lambda_82487310dcc4f633fe54cb15883a1c7d_
0x1800313ba  lea     rcx, [rbp+57h+var_80]
0x1800313be  call    _lambda_1f2fa7ec6605b0250b290bf8a6443ef1___operator__
0x1800313c3  mov     [rbp+57h+var_D0], 0
0x1800313c7  lea     rax, [rbp+57h+var_80]
0x1800313cb  mov     [rbp+57h+var_90], rax
0x1800313cf  mov     [rbp+57h+var_88], 102h
0x1800313d5  mov     [rbp+57h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x1800313dd  lea     rcx, [rbp+57h+var_68]
0x1800313e1  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x1800313e6  lea     rcx, [rbp+57h+var_C8]
0x1800313ea  mov     [rbp+57h+var_B0], rcx
0x1800313ee  lea     rcx, [rbp+57h+TransactionHandle]
0x1800313f2  mov     [rbp+57h+var_A8], rcx
0x1800313f6  mov     rdx, rax
0x1800313f9  lea     rcx, [rbp+57h+var_B0]
0x1800313fd  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180031402  lea     rcx, [rbp+57h+var_68]
0x180031406  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x18003140b  lea     rcx, [rbp+57h+var_C0]
0x18003140f  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180031414  lea     rdx, [rbp+57h+var_C8]
0x180031418  lea     rcx, [rbp+57h+var_C0]
0x18003141c  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x180031421  mov     [rbp+57h+var_C4], 3
0x180031428  lea     rsi, WPP_GLOBAL_Control
0x18003142f  cmp     [rbp+57h+var_C8], 0
0x180031433  jz      short loc_18003149F
0x180031435  xor     edx, edx; Val
0x180031437  lea     r8d, [rdx+40h]; Size
0x18003143b  lea     rcx, [rbp+57h+var_50]; void *
0x18003143f  call    memset_0
0x180031444  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180031449  lea     rcx, [rbp+57h+var_50]
0x18003144d  mov     [rbp+57h+var_B0], rcx
0x180031451  lea     rcx, [rbp+57h+var_10]
0x180031455  mov     [rbp+57h+var_A8], rcx
0x180031459  mov     r9b, 5Fh ; '_'
0x18003145c  mov     edx, eax
0x18003145e  lea     rcx, [rbp+57h+var_B0]
0x180031462  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180031467  mov     rcx, cs:WPP_GLOBAL_Control
0x18003146e  cmp     rcx, rsi
0x180031471  jz      short loc_18003149F
0x180031473  test    byte ptr [rcx+1Ch], 1
0x180031477  jz      short loc_18003149F
0x180031479  cmp     byte ptr [rcx+19h], 2
0x18003147d  jb      short loc_18003149F
0x18003147f  mov     edx, 16h
0x180031484  mov     eax, [rbp+57h+var_C8]
0x180031487  mov     [rsp+100h+var_E0], eax
0x18003148b  lea     r9, [rbp+57h+var_50]
0x18003148f  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180031496  mov     rcx, [rcx+10h]
0x18003149a  call    WPP_SF_sd
0x18003149f  mov     ecx, [rbp+57h+var_C8]
0x1800314a2  mov     eax, dword ptr [rbp+57h+var_C0]
0x1800314a5  mov     [rbp+57h+var_C8], eax
0x1800314a8  mov     dword ptr [rbp+57h+var_C0], ecx
0x1800314ab  mov     ecx, [rbp+57h+var_C4]
0x1800314ae  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x1800314b1  mov     [rbp+57h+var_C4], eax
0x1800314b4  mov     dword ptr [rbp+57h+var_C0+4], ecx
0x1800314b7  lea     rcx, [rbp+57h+var_C0]
0x1800314bb  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800314c0  mov     dword ptr [rbp+57h+var_C0+4], 4
0x1800314c7  lea     rcx, [rbp+57h+var_C0]
0x1800314cb  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800314d0  lea     rcx, [rbp+57h+var_C8]
0x1800314d4  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800314d9  mov     rax, [rbp+57h+TransactionHandle]
0x1800314dd  mov     [rbp+57h+var_C0], rax
0x1800314e1  lea     r8, [rbp+57h+var_C0]
0x1800314e5  mov     rdx, rbx
0x1800314e8  lea     rcx, [rbp+57h+var_B0]
0x1800314ec  call    ?DeleteDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::DeleteDirectoryOnDisk(std::wstring const &,void * const &)
0x1800314f1  nop
0x1800314f2  mov     rcx, rax
0x1800314f5  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800314fa  nop
0x1800314fb  lea     rcx, [rbp+57h+var_B0]
0x1800314ff  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180031504  mov     rcx, [rbp+57h+TransactionHandle]; TransactionHandle
0x180031508  call    cs:__imp_CommitTransaction
0x18003150e  xor     edx, edx
0x180031510  test    eax, eax
0x180031512  setz    dl
0x180031515  lea     rcx, [rbp+57h+var_B0]
0x180031519  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18003151e  mov     rdx, rax
0x180031521  lea     rcx, [rbp+57h+var_C8]
0x180031525  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x18003152a  lea     rcx, [rbp+57h+var_C0]
0x18003152e  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180031533  lea     rdx, [rbp+57h+var_C8]
0x180031537  lea     rcx, [rbp+57h+var_C0]
0x18003153b  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x180031540  mov     [rbp+57h+var_C4], 3
0x180031547  cmp     [rbp+57h+var_C8], 0
0x18003154b  jz      short loc_1800315B7
0x18003154d  xor     edx, edx; Val
0x18003154f  lea     r8d, [rdx+40h]; Size
0x180031553  lea     rcx, [rbp+57h+var_50]; void *
0x180031557  call    memset_0
0x18003155c  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180031561  lea     rcx, [rbp+57h+var_50]
0x180031565  mov     [rbp+57h+var_B0], rcx
0x180031569  lea     rcx, [rbp+57h+var_10]
0x18003156d  mov     [rbp+57h+var_A8], rcx
0x180031571  mov     r9b, 5Fh ; '_'
0x180031574  mov     edx, eax
0x180031576  lea     rcx, [rbp+57h+var_B0]
0x18003157a  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003157f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031586  cmp     rcx, rsi
0x180031589  jz      short loc_1800315B7
0x18003158b  test    byte ptr [rcx+1Ch], 1
0x18003158f  jz      short loc_1800315B7
0x180031591  cmp     byte ptr [rcx+19h], 2
0x180031595  jb      short loc_1800315B7
0x180031597  mov     edx, 17h
0x18003159c  mov     eax, [rbp+57h+var_C8]
0x18003159f  mov     [rsp+100h+var_E0], eax
0x1800315a3  lea     r9, [rbp+57h+var_50]
0x1800315a7  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x1800315ae  mov     rcx, [rcx+10h]
0x1800315b2  call    WPP_SF_sd
0x1800315b7  mov     ecx, [rbp+57h+var_C8]
0x1800315ba  mov     eax, dword ptr [rbp+57h+var_C0]
0x1800315bd  mov     [rbp+57h+var_C8], eax
0x1800315c0  mov     dword ptr [rbp+57h+var_C0], ecx
0x1800315c3  mov     ecx, [rbp+57h+var_C4]
0x1800315c6  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x1800315c9  mov     [rbp+57h+var_C4], eax
0x1800315cc  mov     dword ptr [rbp+57h+var_C0+4], ecx
0x1800315cf  lea     rcx, [rbp+57h+var_C0]
0x1800315d3  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800315d8  mov     dword ptr [rbp+57h+var_C0+4], 4
0x1800315df  lea     rcx, [rbp+57h+var_C0]
0x1800315e3  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800315e8  lea     rcx, [rbp+57h+var_C8]
0x1800315ec  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800315f1  nop
0x1800315f2  lea     rcx, [rbp+57h+TransactionHandle]
0x1800315f6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800315fb  nop
0x1800315fc  lea     rcx, [rbp+57h+var_90]
0x180031600  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_1f2fa7ec6605b0250b290bf8a6443ef1_______operator__
0x180031605  nop
0x180031606  lea     rcx, [rbp+57h+var_C8]
0x18003160a  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18003160f  mov     rcx, [rbp+57h+var_10]
0x180031613  xor     rcx, rsp; StackCookie
0x180031616  call    __security_check_cookie
0x18003161b  lea     r11, [rsp+100h+var_s0]
0x180031623  mov     rbx, [r11+18h]
0x180031627  mov     rsi, [r11+20h]
0x18003162b  mov     rsp, r11
0x18003162e  pop     rbp
0x18003162f  retn
```

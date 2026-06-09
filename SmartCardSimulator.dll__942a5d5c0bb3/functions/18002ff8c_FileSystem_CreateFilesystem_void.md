# FileSystem::CreateFilesystem(void)

- ea: `0x18002ff8c`
- end: `0x18003024c`
- name: `?CreateFilesystem@FileSystem@@QEAAXXZ`
- size: `704`
- prototype: `void __fastcall(FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f6dc`

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
- `0x18002d134`
- `0x18002f430`
- `0x18002fae4`
- `0x18002ff8c`
- `0x180030254`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180030124`
- `ktmw32!CommitTransaction` at `0x180030124`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FileSystem::CreateFilesystem(const WCHAR *this)
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
  lambda_afcdcd47c895ec990a5ac9fd9d92b75e_::operator()(v25);
  v16[0] = 0;
  v23 = v25;
  v24 = 258;
  TransactionHandle = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v26);
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
        19,
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
  v8 = FileSystem::DiskOperations::CreateDirectoryOnDisk(&v21, this, &v19);
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
        20,
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
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_afcdcd47c895ec990a5ac9fd9d92b75e_____::operator()(&v23);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v17);
}

```

## disassembly

```asm
0x18002ff8c  mov     [rsp-8+arg_8], rbx
0x18002ff91  mov     [rsp-8+arg_10], rsi
0x18002ff96  push    rbp
0x18002ff97  lea     rbp, [rsp-57h]
0x18002ff9c  sub     rsp, 100h
0x18002ffa3  mov     rax, cs:__security_cookie
0x18002ffaa  xor     rax, rsp
0x18002ffad  mov     [rbp+57h+var_10], rax
0x18002ffb1  mov     rbx, rcx
0x18002ffb4  lea     rcx, [rbp+57h+var_C8]
0x18002ffb8  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x18002ffbd  nop
0x18002ffbe  mov     [rbp+57h+var_D0], 1
0x18002ffc2  lea     r9, [rbp+57h+var_C8]
0x18002ffc6  mov     r8, rbx
0x18002ffc9  lea     rdx, [rbp+57h+var_D0]
0x18002ffcd  lea     rcx, [rbp+57h+var_80]
0x18002ffd1  call    _lambda_82487310dcc4f633fe54cb15883a1c7d____lambda_82487310dcc4f633fe54cb15883a1c7d_
0x18002ffd6  lea     rcx, [rbp+57h+var_80]
0x18002ffda  call    _lambda_afcdcd47c895ec990a5ac9fd9d92b75e___operator__
0x18002ffdf  mov     [rbp+57h+var_D0], 0
0x18002ffe3  lea     rax, [rbp+57h+var_80]
0x18002ffe7  mov     [rbp+57h+var_90], rax
0x18002ffeb  mov     [rbp+57h+var_88], 102h
0x18002fff1  mov     [rbp+57h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x18002fff9  lea     rcx, [rbp+57h+var_68]
0x18002fffd  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x180030002  lea     rcx, [rbp+57h+var_C8]
0x180030006  mov     [rbp+57h+var_B0], rcx
0x18003000a  lea     rcx, [rbp+57h+TransactionHandle]
0x18003000e  mov     [rbp+57h+var_A8], rcx
0x180030012  mov     rdx, rax
0x180030015  lea     rcx, [rbp+57h+var_B0]
0x180030019  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x18003001e  lea     rcx, [rbp+57h+var_68]
0x180030022  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x180030027  lea     rcx, [rbp+57h+var_C0]
0x18003002b  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030030  lea     rdx, [rbp+57h+var_C8]
0x180030034  lea     rcx, [rbp+57h+var_C0]
0x180030038  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x18003003d  mov     [rbp+57h+var_C4], 3
0x180030044  lea     rsi, WPP_GLOBAL_Control
0x18003004b  cmp     [rbp+57h+var_C8], 0
0x18003004f  jz      short loc_1800300BB
0x180030051  xor     edx, edx; Val
0x180030053  lea     r8d, [rdx+40h]; Size
0x180030057  lea     rcx, [rbp+57h+var_50]; void *
0x18003005b  call    memset_0
0x180030060  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030065  lea     rcx, [rbp+57h+var_50]
0x180030069  mov     [rbp+57h+var_B0], rcx
0x18003006d  lea     rcx, [rbp+57h+var_10]
0x180030071  mov     [rbp+57h+var_A8], rcx
0x180030075  mov     r9b, 5Fh ; '_'
0x180030078  mov     edx, eax
0x18003007a  lea     rcx, [rbp+57h+var_B0]
0x18003007e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030083  mov     rcx, cs:WPP_GLOBAL_Control
0x18003008a  cmp     rcx, rsi
0x18003008d  jz      short loc_1800300BB
0x18003008f  test    byte ptr [rcx+1Ch], 1
0x180030093  jz      short loc_1800300BB
0x180030095  cmp     byte ptr [rcx+19h], 2
0x180030099  jb      short loc_1800300BB
0x18003009b  mov     edx, 13h
0x1800300a0  mov     eax, [rbp+57h+var_C8]
0x1800300a3  mov     [rsp+100h+var_E0], eax
0x1800300a7  lea     r9, [rbp+57h+var_50]
0x1800300ab  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x1800300b2  mov     rcx, [rcx+10h]
0x1800300b6  call    WPP_SF_sd
0x1800300bb  mov     ecx, [rbp+57h+var_C8]
0x1800300be  mov     eax, dword ptr [rbp+57h+var_C0]
0x1800300c1  mov     [rbp+57h+var_C8], eax
0x1800300c4  mov     dword ptr [rbp+57h+var_C0], ecx
0x1800300c7  mov     ecx, [rbp+57h+var_C4]
0x1800300ca  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x1800300cd  mov     [rbp+57h+var_C4], eax
0x1800300d0  mov     dword ptr [rbp+57h+var_C0+4], ecx
0x1800300d3  lea     rcx, [rbp+57h+var_C0]
0x1800300d7  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800300dc  mov     dword ptr [rbp+57h+var_C0+4], 4
0x1800300e3  lea     rcx, [rbp+57h+var_C0]
0x1800300e7  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800300ec  lea     rcx, [rbp+57h+var_C8]
0x1800300f0  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800300f5  mov     rax, [rbp+57h+TransactionHandle]
0x1800300f9  mov     [rbp+57h+var_C0], rax
0x1800300fd  lea     r8, [rbp+57h+var_C0]
0x180030101  mov     rdx, rbx
0x180030104  lea     rcx, [rbp+57h+var_B0]
0x180030108  call    ?CreateDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::CreateDirectoryOnDisk(std::wstring const &,void * const &)
0x18003010d  nop
0x18003010e  mov     rcx, rax
0x180030111  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180030116  nop
0x180030117  lea     rcx, [rbp+57h+var_B0]
0x18003011b  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180030120  mov     rcx, [rbp+57h+TransactionHandle]; TransactionHandle
0x180030124  call    cs:__imp_CommitTransaction
0x18003012a  xor     edx, edx
0x18003012c  test    eax, eax
0x18003012e  setz    dl
0x180030131  lea     rcx, [rbp+57h+var_B0]
0x180030135  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18003013a  mov     rdx, rax
0x18003013d  lea     rcx, [rbp+57h+var_C8]
0x180030141  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180030146  lea     rcx, [rbp+57h+var_C0]
0x18003014a  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x18003014f  lea     rdx, [rbp+57h+var_C8]
0x180030153  lea     rcx, [rbp+57h+var_C0]
0x180030157  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x18003015c  mov     [rbp+57h+var_C4], 3
0x180030163  cmp     [rbp+57h+var_C8], 0
0x180030167  jz      short loc_1800301D3
0x180030169  xor     edx, edx; Val
0x18003016b  lea     r8d, [rdx+40h]; Size
0x18003016f  lea     rcx, [rbp+57h+var_50]; void *
0x180030173  call    memset_0
0x180030178  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003017d  lea     rcx, [rbp+57h+var_50]
0x180030181  mov     [rbp+57h+var_B0], rcx
0x180030185  lea     rcx, [rbp+57h+var_10]
0x180030189  mov     [rbp+57h+var_A8], rcx
0x18003018d  mov     r9b, 5Fh ; '_'
0x180030190  mov     edx, eax
0x180030192  lea     rcx, [rbp+57h+var_B0]
0x180030196  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003019b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800301a2  cmp     rcx, rsi
0x1800301a5  jz      short loc_1800301D3
0x1800301a7  test    byte ptr [rcx+1Ch], 1
0x1800301ab  jz      short loc_1800301D3
0x1800301ad  cmp     byte ptr [rcx+19h], 2
0x1800301b1  jb      short loc_1800301D3
0x1800301b3  mov     edx, 14h
0x1800301b8  mov     eax, [rbp+57h+var_C8]
0x1800301bb  mov     [rsp+100h+var_E0], eax
0x1800301bf  lea     r9, [rbp+57h+var_50]
0x1800301c3  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x1800301ca  mov     rcx, [rcx+10h]
0x1800301ce  call    WPP_SF_sd
0x1800301d3  mov     ecx, [rbp+57h+var_C8]
0x1800301d6  mov     eax, dword ptr [rbp+57h+var_C0]
0x1800301d9  mov     [rbp+57h+var_C8], eax
0x1800301dc  mov     dword ptr [rbp+57h+var_C0], ecx
0x1800301df  mov     ecx, [rbp+57h+var_C4]
0x1800301e2  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x1800301e5  mov     [rbp+57h+var_C4], eax
0x1800301e8  mov     dword ptr [rbp+57h+var_C0+4], ecx
0x1800301eb  lea     rcx, [rbp+57h+var_C0]
0x1800301ef  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800301f4  mov     dword ptr [rbp+57h+var_C0+4], 4
0x1800301fb  lea     rcx, [rbp+57h+var_C0]
0x1800301ff  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180030204  lea     rcx, [rbp+57h+var_C8]
0x180030208  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x18003020d  nop
0x18003020e  lea     rcx, [rbp+57h+TransactionHandle]
0x180030212  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030217  nop
0x180030218  lea     rcx, [rbp+57h+var_90]
0x18003021c  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_afcdcd47c895ec990a5ac9fd9d92b75e_______operator__
0x180030221  nop
0x180030222  lea     rcx, [rbp+57h+var_C8]
0x180030226  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18003022b  mov     rcx, [rbp+57h+var_10]
0x18003022f  xor     rcx, rsp; StackCookie
0x180030232  call    __security_check_cookie
0x180030237  lea     r11, [rsp+100h+var_s0]
0x18003023f  mov     rbx, [r11+18h]
0x180030243  mov     rsi, [r11+20h]
0x180030247  mov     rsp, r11
0x18003024a  pop     rbp
0x18003024b  retn
```

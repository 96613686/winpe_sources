# FileSystem::ReadFromDisk(void)

- ea: `0x180033048`
- end: `0x18003337e`
- name: `?ReadFromDisk@FileSystem@@AEAAXXZ`
- size: `822`
- prototype: `void __fastcall(FileSystem *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002941c`

## callees

- `0x18000386c`
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
- `0x1800267ec`
- `0x180029b84`
- `0x18002baf8`
- `0x18002edd0`
- `0x18002f19c`
- `0x180030254`
- `0x180033048`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180033230`
- `ktmw32!CommitTransaction` at `0x180033230`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FileSystem::ReadFromDisk(FileSystem *this)
{
  __int64 FilesystemTransaction; // rax
  unsigned int v3; // eax
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  BOOL v11; // eax
  __int64 winerror_if; // rax
  unsigned int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  int v16; // ecx
  int v17; // ecx
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh]
  char v20[8]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE TransactionHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  int *v24; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE *v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  __int16 v27; // [rsp+88h] [rbp-78h]
  _BYTE *v28; // [rsp+90h] [rbp-70h] BYREF
  __int16 v29; // [rsp+98h] [rbp-68h]
  _BYTE v30[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[24]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v32[64]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v33[2]; // [rsp+110h] [rbp+10h] BYREF

  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v18);
  v20[0] = 1;
  lambda_82487310dcc4f633fe54cb15883a1c7d_::_lambda_82487310dcc4f633fe54cb15883a1c7d_(v30, v20, this, &v18);
  lambda_5b64b3cb6cc5a42f12706bb5fbaaed9a_::operator()(v30);
  v20[0] = 0;
  v28 = v30;
  v29 = 258;
  v26 = *(_QWORD *)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                     v22,
                     this);
  v27 = 258;
  TransactionHandle[0] = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v31);
  v24 = &v18;
  v25 = TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v24,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v31);
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v21);
  errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(
    &v21,
    &v18);
  v19 = 3;
  if ( v18 )
  {
    memset_0(v32, 0, sizeof(v32));
    v3 = ReportIndentTracker::Indent();
    v24 = (int *)v32;
    v25 = (HANDLE *)v33;
    LOBYTE(v4) = 95;
    ReportIndentTracker::Format(&v24, v3, v5, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v32,
        v18);
    }
  }
  v6 = v18;
  v18 = (int)v21;
  LODWORD(v21) = v6;
  v7 = v19;
  v19 = HIDWORD(v21);
  HIDWORD(v21) = v7;
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v21);
  HIDWORD(v21) = 4;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v21);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(&v18);
  v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v24, this);
  v21 = TransactionHandle[0];
  v10 = FileSystem::DiskOperations::ForEachFileInDirectory__lambda_02fe1a7375f0e783a68abc3cabcf9f28___(
          v22,
          v9,
          &v21,
          v8);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v18, v10);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(&v18);
  v11 = CommitTransaction(TransactionHandle[0]);
  winerror_if = make_winerror_if(v22, !v11);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v18, winerror_if);
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v21);
  errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(
    &v21,
    &v18);
  v19 = 3;
  if ( v18 )
  {
    memset_0(v32, 0, sizeof(v32));
    v13 = ReportIndentTracker::Indent();
    v24 = (int *)v32;
    v25 = (HANDLE *)v33;
    LOBYTE(v14) = 95;
    ReportIndentTracker::Format(&v24, v13, v15, v14);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v32,
        v18);
    }
  }
  v16 = v18;
  v18 = (int)v21;
  LODWORD(v21) = v16;
  v17 = v19;
  v19 = HIDWORD(v21);
  HIDWORD(v21) = v17;
  errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(&v21);
  HIDWORD(v21) = 4;
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v21);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(&v18);
  HIBYTE(v27) = 0;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TransactionHandle);
  wil::details::ScopeExitFnGuard__lambda_f66d84e900b9203739d972fb2fb92faf___::operator()(&v26);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_5b64b3cb6cc5a42f12706bb5fbaaed9a_____::operator()(&v28);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v18);
}

```

## disassembly

```asm
0x180033048  mov     [rsp-8+arg_8], rbx
0x18003304d  mov     [rsp-8+arg_10], r14
0x180033052  push    rbp
0x180033053  lea     rbp, [rsp-20h]
0x180033058  sub     rsp, 120h
0x18003305f  mov     rax, cs:__security_cookie
0x180033066  xor     rax, rsp
0x180033069  mov     [rbp+20h+var_10], rax
0x18003306d  mov     rbx, rcx
0x180033070  lea     rcx, [rsp+120h+var_F0]
0x180033075  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x18003307a  nop
0x18003307b  mov     [rsp+120h+var_E8], 1
0x180033080  lea     r9, [rsp+120h+var_F0]
0x180033085  mov     r8, rbx
0x180033088  lea     rdx, [rsp+120h+var_E8]
0x18003308d  lea     rcx, [rbp+20h+var_80]
0x180033091  call    _lambda_82487310dcc4f633fe54cb15883a1c7d____lambda_82487310dcc4f633fe54cb15883a1c7d_
0x180033096  lea     rcx, [rbp+20h+var_80]
0x18003309a  call    _lambda_5b64b3cb6cc5a42f12706bb5fbaaed9a___operator__
0x18003309f  mov     [rsp+120h+var_E8], 0
0x1800330a4  lea     rax, [rbp+20h+var_80]
0x1800330a8  mov     [rbp+20h+var_90], rax
0x1800330ac  mov     [rbp+20h+var_88], 102h
0x1800330b2  mov     rdx, rbx
0x1800330b5  lea     rcx, [rsp+120h+var_D8]
0x1800330ba  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800330bf  mov     rcx, [rax]
0x1800330c2  mov     [rbp+20h+var_A0], rcx
0x1800330c6  mov     [rbp+20h+var_98], 102h
0x1800330cc  mov     [rsp+120h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x1800330d5  lea     rcx, [rbp+20h+var_68]
0x1800330d9  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x1800330de  lea     rcx, [rsp+120h+var_F0]
0x1800330e3  mov     [rsp+120h+var_C0], rcx
0x1800330e8  lea     rcx, [rsp+120h+TransactionHandle]
0x1800330ed  mov     [rsp+120h+var_B8], rcx
0x1800330f2  mov     rdx, rax
0x1800330f5  lea     rcx, [rsp+120h+var_C0]
0x1800330fa  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x1800330ff  lea     rcx, [rbp+20h+var_68]
0x180033103  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x180033108  lea     rcx, [rsp+120h+var_E0]
0x18003310d  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180033112  lea     rdx, [rsp+120h+var_F0]
0x180033117  lea     rcx, [rsp+120h+var_E0]
0x18003311c  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x180033121  mov     [rsp+120h+var_EC], 3
0x180033129  lea     r14, WPP_GLOBAL_Control
0x180033130  cmp     [rsp+120h+var_F0], 0
0x180033135  jz      short loc_1800331A5
0x180033137  xor     edx, edx; Val
0x180033139  lea     r8d, [rdx+40h]; Size
0x18003313d  lea     rcx, [rbp+20h+var_50]; void *
0x180033141  call    memset_0
0x180033146  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003314b  lea     rcx, [rbp+20h+var_50]
0x18003314f  mov     [rsp+120h+var_C0], rcx
0x180033154  lea     rcx, [rbp+20h+var_10]
0x180033158  mov     [rsp+120h+var_B8], rcx
0x18003315d  mov     r9b, 5Fh ; '_'
0x180033160  mov     edx, eax
0x180033162  lea     rcx, [rsp+120h+var_C0]
0x180033167  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003316c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033173  cmp     rcx, r14
0x180033176  jz      short loc_1800331A5
0x180033178  test    byte ptr [rcx+1Ch], 1
0x18003317c  jz      short loc_1800331A5
0x18003317e  cmp     byte ptr [rcx+19h], 2
0x180033182  jb      short loc_1800331A5
0x180033184  mov     edx, 19h
0x180033189  mov     eax, [rsp+120h+var_F0]
0x18003318d  mov     [rsp+120h+var_100], eax
0x180033191  lea     r9, [rbp+20h+var_50]
0x180033195  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x18003319c  mov     rcx, [rcx+10h]
0x1800331a0  call    WPP_SF_sd
0x1800331a5  mov     ecx, [rsp+120h+var_F0]
0x1800331a9  mov     eax, dword ptr [rsp+120h+var_E0]
0x1800331ad  mov     [rsp+120h+var_F0], eax
0x1800331b1  mov     dword ptr [rsp+120h+var_E0], ecx
0x1800331b5  mov     ecx, [rsp+120h+var_EC]
0x1800331b9  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x1800331bd  mov     [rsp+120h+var_EC], eax
0x1800331c1  mov     dword ptr [rsp+120h+var_E0+4], ecx
0x1800331c5  lea     rcx, [rsp+120h+var_E0]
0x1800331ca  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x1800331cf  mov     dword ptr [rsp+120h+var_E0+4], 4
0x1800331d7  lea     rcx, [rsp+120h+var_E0]
0x1800331dc  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800331e1  lea     rcx, [rsp+120h+var_F0]
0x1800331e6  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800331eb  mov     rdx, rbx
0x1800331ee  lea     rcx, [rsp+120h+var_C0]
0x1800331f3  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800331f8  mov     rcx, [rsp+120h+TransactionHandle]
0x1800331fd  mov     [rsp+120h+var_E0], rcx
0x180033202  mov     r9, rax
0x180033205  lea     r8, [rsp+120h+var_E0]
0x18003320a  lea     rcx, [rsp+120h+var_D8]
0x18003320f  call    FileSystem__DiskOperations__ForEachFileInDirectory__lambda_02fe1a7375f0e783a68abc3cabcf9f28___
0x180033214  mov     rdx, rax
0x180033217  lea     rcx, [rsp+120h+var_F0]
0x18003321c  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180033221  lea     rcx, [rsp+120h+var_F0]
0x180033226  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x18003322b  mov     rcx, [rsp+120h+TransactionHandle]; TransactionHandle
0x180033230  call    cs:__imp_CommitTransaction
0x180033236  xor     edx, edx
0x180033238  test    eax, eax
0x18003323a  setz    dl
0x18003323d  lea     rcx, [rsp+120h+var_D8]
0x180033242  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180033247  mov     rdx, rax
0x18003324a  lea     rcx, [rsp+120h+var_F0]
0x18003324f  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180033254  lea     rcx, [rsp+120h+var_E0]
0x180033259  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x18003325e  lea     rdx, [rsp+120h+var_F0]
0x180033263  lea     rcx, [rsp+120h+var_E0]
0x180033268  call    ??$duplicate@V?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV12@@errorlib@@YAXPEAV?$scoped_error@Utag@winerror_error@@@0@AEAV10@@Z; errorlib::duplicate<errorlib::scoped_error<winerror_error::tag>,errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> *,errorlib::scoped_error<winerror_error::tag> &)
0x18003326d  mov     [rsp+120h+var_EC], 3
0x180033275  cmp     [rsp+120h+var_F0], 0
0x18003327a  jz      short loc_1800332EA
0x18003327c  xor     edx, edx; Val
0x18003327e  lea     r8d, [rdx+40h]; Size
0x180033282  lea     rcx, [rbp+20h+var_50]; void *
0x180033286  call    memset_0
0x18003328b  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180033290  lea     rcx, [rbp+20h+var_50]
0x180033294  mov     [rsp+120h+var_C0], rcx
0x180033299  lea     rcx, [rbp+20h+var_10]
0x18003329d  mov     [rsp+120h+var_B8], rcx
0x1800332a2  mov     r9b, 5Fh ; '_'
0x1800332a5  mov     edx, eax
0x1800332a7  lea     rcx, [rsp+120h+var_C0]
0x1800332ac  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800332b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800332b8  cmp     rcx, r14
0x1800332bb  jz      short loc_1800332EA
0x1800332bd  test    byte ptr [rcx+1Ch], 1
0x1800332c1  jz      short loc_1800332EA
0x1800332c3  cmp     byte ptr [rcx+19h], 2
0x1800332c7  jb      short loc_1800332EA
0x1800332c9  mov     edx, 1Ah
0x1800332ce  mov     eax, [rsp+120h+var_F0]
0x1800332d2  mov     [rsp+120h+var_100], eax
0x1800332d6  lea     r9, [rbp+20h+var_50]
0x1800332da  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x1800332e1  mov     rcx, [rcx+10h]
0x1800332e5  call    WPP_SF_sd
0x1800332ea  mov     ecx, [rsp+120h+var_F0]
0x1800332ee  mov     eax, dword ptr [rsp+120h+var_E0]
0x1800332f2  mov     [rsp+120h+var_F0], eax
0x1800332f6  mov     dword ptr [rsp+120h+var_E0], ecx
0x1800332fa  mov     ecx, [rsp+120h+var_EC]
0x1800332fe  mov     eax, dword ptr [rsp+120h+var_E0+4]
0x180033302  mov     [rsp+120h+var_EC], eax
0x180033306  mov     dword ptr [rsp+120h+var_E0+4], ecx
0x18003330a  lea     rcx, [rsp+120h+var_E0]
0x18003330f  call    ??$optionalFailFastCheck@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@@detail@errorlib@@YA_NAEAV?$scoped_error@Utag@winerror_error@@@1@@Z; errorlib::detail::optionalFailFastCheck<errorlib::scoped_error<winerror_error::tag> &>(errorlib::scoped_error<winerror_error::tag> &)
0x180033314  mov     dword ptr [rsp+120h+var_E0+4], 4
0x18003331c  lea     rcx, [rsp+120h+var_E0]
0x180033321  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180033326  lea     rcx, [rsp+120h+var_F0]
0x18003332b  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180033330  mov     byte ptr [rbp+20h+var_98+1], 0
0x180033334  lea     rcx, [rsp+120h+TransactionHandle]
0x180033339  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003333e  nop
0x18003333f  lea     rcx, [rbp+20h+var_A0]
0x180033343  call    wil__details__ScopeExitFnGuard__lambda_f66d84e900b9203739d972fb2fb92faf_____operator__
0x180033348  nop
0x180033349  lea     rcx, [rbp+20h+var_90]
0x18003334d  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_5b64b3cb6cc5a42f12706bb5fbaaed9a_______operator__
0x180033352  nop
0x180033353  lea     rcx, [rsp+120h+var_F0]
0x180033358  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18003335d  mov     rcx, [rbp+20h+var_10]
0x180033361  xor     rcx, rsp; StackCookie
0x180033364  call    __security_check_cookie
0x180033369  lea     r11, [rsp+120h+var_s0]
0x180033371  mov     rbx, [r11+18h]
0x180033375  mov     r14, [r11+20h]
0x180033379  mov     rsp, r11
0x18003337c  pop     rbp
0x18003337d  retn
```

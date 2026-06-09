# FileSystem::DedicatedFile::DeleteEf(AuthenticatedRoleStatus::type const &,ElementaryFileIdentifier::type)

- ea: `0x180030e8c`
- end: `0x1800312bb`
- name: `?DeleteEf@DedicatedFile@FileSystem@@QEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEBUtype@AuthenticatedRoleStatus@@U5ElementaryFileIdentifier@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(FileSystem::DedicatedFile *this)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180048148`

## callees

- `0x180007a64`
- `0x180008148`
- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18000a960`
- `0x18000aa10`
- `0x18000efc0`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x1800260e8`
- `0x1800261bc`
- `0x180028e08`
- `0x180029b84`
- `0x18002c21c`
- `0x18002f2a4`
- `0x18002f614`
- `0x180030254`
- `0x180030c84`
- `0x180030e8c`
- `0x1800322b4`
- `0x180039248`
- `0x18003a170`
- `0x18003aeb0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x18003106d`
- `ktmw32!CommitTransaction` at `0x18003106d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall FileSystem::DedicatedFile::DeleteEf(
        FileSystem::DedicatedFile *this,
        __int64 a2,
        const struct AuthenticatedRoleStatus::type *a3,
        __int16 a4)
{
  __int64 FilesystemTransaction; // rax
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rax
  BOOL v13; // eax
  __int64 winerror_if; // rax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // r8d
  _QWORD *v23; // rax
  unsigned int v24; // eax
  __int64 v25; // r9
  __int64 v26; // r8
  char v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h]
  HANDLE TransactionHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v32; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v33; // [rsp+68h] [rbp-98h]
  _QWORD v34[4]; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+90h] [rbp-70h]
  HANDLE v36; // [rsp+98h] [rbp-68h] BYREF
  _BYTE *v37; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v38; // [rsp+A8h] [rbp-58h]
  _BYTE v39[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v40[48]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v41[5]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v42[40]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v43[64]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v44[4]; // [rsp+190h] [rbp+90h] BYREF
  __int16 v45; // [rsp+1D8h] [rbp+D8h] BYREF

  v45 = a4;
  v32 = (_BYTE *)a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v35 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v29);
  v28 = 1;
  lambda_0524bf129c7ffff2153a4d981466b1ee_::_lambda_0524bf129c7ffff2153a4d981466b1ee_(
    (unsigned int)v40,
    (unsigned int)&v28,
    (_DWORD)this,
    (unsigned int)&v45,
    (__int64)a3,
    a2,
    (__int64)&v29);
  lambda_78a91e47f7e24fb222e85682750c13f8_::operator()(v40);
  v28 = 0;
  v37 = v40;
  v38 = 258;
  LODWORD(v36) = 3;
  if ( FileSystem::DedicatedFile::AccessCheck(this, a3, (const enum CommandField::type *)&v36) )
  {
    TransactionHandle[0] = (HANDLE)-1LL;
    FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v42);
    v34[0] = &v29;
    v34[1] = TransactionHandle;
    std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      v34,
      FilesystemTransaction);
    std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v42);
    v30 = 3;
    if ( v29 )
    {
      memset_0(v43, 0, sizeof(v43));
      v24 = ReportIndentTracker::Indent();
      v32 = v43;
      v33 = v44;
      LOBYTE(v25) = 95;
      ReportIndentTracker::Format(&v32, v24, v26, v25);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          99,
          (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
          (unsigned int)v43,
          v29);
      }
      errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
      goto LABEL_24;
    }
    ElementaryFileIdentifier::make(v39, &v45);
    rangelib::make_raw_range<std::vector<unsigned char> const &>(v34, v39);
    v8 = FileSystem::HexToString(v43, v34);
    v9 = std::operator+<unsigned short>(v42, (char *)this + 152);
    std::operator+<unsigned short>(v41, v9, v8);
    LOBYTE(v10) = 1;
    std::wstring::_Tidy(v42, v10, 0);
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(v43, v11, 0);
    v36 = TransactionHandle[0];
    v12 = FileSystem::DiskOperations::DeleteDirectoryOnDisk(v34, v41, &v36);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v29, v12);
    v30 = 3;
    if ( v29 )
    {
      memset_0(v43, 0, sizeof(v43));
      v19 = ReportIndentTracker::Indent();
      v32 = v43;
      v33 = v44;
      LOBYTE(v20) = 95;
      ReportIndentTracker::Format(&v32, v19, v21, v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v23 = v41;
        if ( v41[3] >= 8u )
          v23 = (_QWORD *)v41[0];
        WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, v22, (unsigned int)v43, v29, (__int64)v23);
      }
    }
    else
    {
      v13 = CommitTransaction(TransactionHandle[0]);
      winerror_if = make_winerror_if(v34, !v13);
      errorlib::scoped_error<ntstatus_error::tag>::operator=(&v29, winerror_if);
      v30 = 3;
      if ( !v29 )
      {
        std::_Tree<std::_Tmap_traits<ElementaryFileIdentifier::type,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::less<ElementaryFileIdentifier::type>,std::allocator<std::pair<ElementaryFileIdentifier::type const,std::tr1::shared_ptr<FileSystem::ElementaryFile>>>,0>>::erase(
          this,
          &v45);
LABEL_7:
        LOBYTE(v15) = 1;
        std::wstring::_Tidy(v41, v15, 0);
        std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(v39);
LABEL_24:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TransactionHandle);
        goto LABEL_25;
      }
      memset_0(v43, 0, sizeof(v43));
      v16 = ReportIndentTracker::Indent();
      v32 = v43;
      v33 = v44;
      LOBYTE(v17) = 95;
      ReportIndentTracker::Format(&v32, v16, v18, v17);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
          (unsigned int)v43,
          v29);
      }
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
    goto LABEL_7;
  }
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_1800759B0);
LABEL_25:
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_78a91e47f7e24fb222e85682750c13f8_____::operator()(&v37);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v29);
  return a2;
}

```

## disassembly

```asm
0x180030e8c  mov     [rsp-8+arg_10], rbx
0x180030e91  mov     [rsp-8+arg_18], r9w
0x180030e97  push    rbp
0x180030e98  push    rsi
0x180030e99  push    rdi
0x180030e9a  lea     rbp, [rsp-0A0h]
0x180030ea2  sub     rsp, 1A0h
0x180030ea9  mov     rax, cs:__security_cookie
0x180030eb0  xor     rax, rsp
0x180030eb3  mov     [rbp+0B0h+var_20], rax
0x180030eba  mov     rbx, r8
0x180030ebd  mov     rdi, rdx
0x180030ec0  mov     rsi, rcx
0x180030ec3  mov     [rsp+1B0h+var_150], rdx
0x180030ec8  mov     [rbp+0B0h+var_120], 1
0x180030ecf  mov     rcx, rdx
0x180030ed2  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180030ed7  nop
0x180030ed8  mov     [rbp+0B0h+var_120], 1
0x180030edf  lea     rcx, [rsp+1B0h+var_168]
0x180030ee4  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030ee9  nop
0x180030eea  mov     [rsp+1B0h+var_170], 1
0x180030eef  lea     rax, [rsp+1B0h+var_168]
0x180030ef4  mov     [rsp+1B0h+var_180], rax
0x180030ef9  mov     [rsp+1B0h+var_188], rdi
0x180030efe  mov     [rsp+1B0h+var_190], rbx
0x180030f03  lea     r9, [rbp+0B0h+arg_18]
0x180030f0a  mov     r8, rsi
0x180030f0d  lea     rdx, [rsp+1B0h+var_170]
0x180030f12  lea     rcx, [rbp+0B0h+var_E0]
0x180030f16  call    _lambda_0524bf129c7ffff2153a4d981466b1ee____lambda_0524bf129c7ffff2153a4d981466b1ee_
0x180030f1b  lea     rcx, [rbp+0B0h+var_E0]
0x180030f1f  call    _lambda_78a91e47f7e24fb222e85682750c13f8___operator__
0x180030f24  mov     [rsp+1B0h+var_170], 0
0x180030f29  lea     rax, [rbp+0B0h+var_E0]
0x180030f2d  mov     [rbp+0B0h+var_110], rax
0x180030f31  mov     [rbp+0B0h+var_108], 102h
0x180030f37  mov     dword ptr [rbp+0B0h+var_118], 3
0x180030f3e  lea     r8, [rbp+0B0h+var_118]; enum CommandField::type *
0x180030f42  mov     rdx, rbx; struct AuthenticatedRoleStatus::type *
0x180030f45  mov     rcx, rsi; this
0x180030f48  call    ?AccessCheck@DedicatedFile@FileSystem@@QEBA_NAEBUtype@AuthenticatedRoleStatus@@AEBW43CommandField@@@Z; FileSystem::DedicatedFile::AccessCheck(AuthenticatedRoleStatus::type const &,CommandField::type const &)
0x180030f4d  test    al, al
0x180030f4f  jnz     short loc_180030F65
0x180030f51  lea     rdx, byte_1800759B0
0x180030f58  mov     rcx, rdi
0x180030f5b  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180030f60  jmp     loc_180031281
0x180030f65  mov     [rsp+1B0h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x180030f6e  lea     rcx, [rbp+0B0h+var_88]
0x180030f72  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x180030f77  lea     rcx, [rsp+1B0h+var_168]
0x180030f7c  mov     [rsp+1B0h+var_140], rcx
0x180030f81  lea     rcx, [rsp+1B0h+TransactionHandle]
0x180030f86  mov     [rsp+1B0h+var_140+8], rcx
0x180030f8b  mov     rdx, rax
0x180030f8e  lea     rcx, [rsp+1B0h+var_140]
0x180030f93  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180030f98  lea     rcx, [rbp+0B0h+var_88]
0x180030f9c  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x180030fa1  mov     [rsp+1B0h+var_164], 3
0x180030fa9  cmp     [rsp+1B0h+var_168], 0
0x180030fae  jnz     loc_1800311EE
0x180030fb4  lea     rdx, [rbp+0B0h+arg_18]
0x180030fbb  lea     rcx, [rbp+0B0h+var_100]
0x180030fbf  call    ?make@ElementaryFileIdentifier@@SA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUtype@1@@Z; ElementaryFileIdentifier::make(ElementaryFileIdentifier::type const &)
0x180030fc4  nop
0x180030fc5  lea     rdx, [rbp+0B0h+var_100]
0x180030fc9  lea     rcx, [rsp+1B0h+var_140]
0x180030fce  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x180030fd3  movaps  xmm0, xmmword ptr [rsp+1B0h+var_140]
0x180030fd8  movdqa  xmmword ptr [rsp+1B0h+var_140], xmm0
0x180030fde  lea     rdx, [rsp+1B0h+var_140]
0x180030fe3  lea     rcx, [rbp+0B0h+var_60]
0x180030fe7  call    ?HexToString@FileSystem@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@@Z; FileSystem::HexToString(rangelib::range<uchar const *>)
0x180030fec  mov     rbx, rax
0x180030fef  lea     rdx, [rsi+98h]
0x180030ff6  lea     rcx, [rbp+0B0h+var_88]
0x180030ffa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x180030fff  nop
0x180031000  mov     r8, rbx
0x180031003  mov     rdx, rax
0x180031006  lea     rcx, [rbp+0B0h+var_B0]
0x18003100a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18003100f  nop
0x180031010  xor     r8d, r8d
0x180031013  mov     dl, 1
0x180031015  lea     rcx, [rbp+0B0h+var_88]
0x180031019  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003101e  nop
0x18003101f  xor     r8d, r8d
0x180031022  mov     dl, 1
0x180031024  lea     rcx, [rbp+0B0h+var_60]
0x180031028  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003102d  mov     rax, [rsp+1B0h+TransactionHandle]
0x180031032  mov     [rbp+0B0h+var_118], rax
0x180031036  lea     r8, [rbp+0B0h+var_118]
0x18003103a  lea     rdx, [rbp+0B0h+var_B0]
0x18003103e  lea     rcx, [rsp+1B0h+var_140]
0x180031043  call    ?DeleteDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::DeleteDirectoryOnDisk(std::wstring const &,void * const &)
0x180031048  mov     rdx, rax
0x18003104b  lea     rcx, [rsp+1B0h+var_168]
0x180031050  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180031055  mov     [rsp+1B0h+var_164], 3
0x18003105d  cmp     [rsp+1B0h+var_168], 0
0x180031062  jnz     loc_180031156
0x180031068  mov     rcx, [rsp+1B0h+TransactionHandle]; TransactionHandle
0x18003106d  call    cs:__imp_CommitTransaction
0x180031073  xor     edx, edx
0x180031075  test    eax, eax
0x180031077  setz    dl
0x18003107a  lea     rcx, [rsp+1B0h+var_140]
0x18003107f  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180031084  mov     rdx, rax
0x180031087  lea     rcx, [rsp+1B0h+var_168]
0x18003108c  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180031091  mov     [rsp+1B0h+var_164], 3
0x180031099  cmp     [rsp+1B0h+var_168], 0
0x18003109e  jnz     short loc_1800310CD
0x1800310a0  lea     rdx, [rbp+0B0h+arg_18]
0x1800310a7  mov     rcx, rsi
0x1800310aa  call    ?erase@?$_Tree@V?$_Tmap_traits@Utype@ElementaryFileIdentifier@@V?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@U?$less@Utype@ElementaryFileIdentifier@@@5@V?$allocator@U?$pair@$$CBUtype@ElementaryFileIdentifier@@V?$shared_ptr@VElementaryFile@FileSystem@@@tr1@std@@@std@@@5@$0A@@std@@@std@@QEAA_KAEBUtype@ElementaryFileIdentifier@@@Z; std::_Tree<std::_Tmap_traits<ElementaryFileIdentifier::type,std::tr1::shared_ptr<FileSystem::ElementaryFile>,std::less<ElementaryFileIdentifier::type>,std::allocator<std::pair<ElementaryFileIdentifier::type const,std::tr1::shared_ptr<FileSystem::ElementaryFile>>>,0>>::erase(ElementaryFileIdentifier::type const &)
0x1800310af  nop
0x1800310b0  xor     r8d, r8d
0x1800310b3  mov     dl, 1
0x1800310b5  lea     rcx, [rbp+0B0h+var_B0]
0x1800310b9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800310be  nop
0x1800310bf  lea     rcx, [rbp+0B0h+var_100]
0x1800310c3  call    ??1?$vector@U_CRYPTOAPI_BLOB@@V?$allocator@U_CRYPTOAPI_BLOB@@@std@@@std@@QEAA@XZ; std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(void)
0x1800310c8  jmp     loc_180031276
0x1800310cd  xor     edx, edx; Val
0x1800310cf  lea     r8d, [rdx+40h]; Size
0x1800310d3  lea     rcx, [rbp+0B0h+var_60]; void *
0x1800310d7  call    memset_0
0x1800310dc  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x1800310e1  lea     rcx, [rbp+0B0h+var_60]
0x1800310e5  mov     [rsp+1B0h+var_150], rcx
0x1800310ea  lea     rcx, [rbp+0B0h+var_20]
0x1800310f1  mov     [rsp+1B0h+var_148], rcx
0x1800310f6  mov     r9b, 5Fh ; '_'
0x1800310f9  mov     edx, eax
0x1800310fb  lea     rcx, [rsp+1B0h+var_150]
0x180031100  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180031105  lea     rax, WPP_GLOBAL_Control
0x18003110c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031113  cmp     rcx, rax
0x180031116  jz      loc_1800311DA
0x18003111c  test    byte ptr [rcx+1Ch], 1
0x180031120  jz      loc_1800311DA
0x180031126  cmp     byte ptr [rcx+19h], 2
0x18003112a  jb      loc_1800311DA
0x180031130  mov     edx, 65h ; 'e'
0x180031135  mov     eax, [rsp+1B0h+var_168]
0x180031139  mov     dword ptr [rsp+1B0h+var_190], eax
0x18003113d  lea     r9, [rbp+0B0h+var_60]
0x180031141  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180031148  mov     rcx, [rcx+10h]
0x18003114c  call    WPP_SF_sd
0x180031151  jmp     loc_1800311DA
0x180031156  xor     edx, edx; Val
0x180031158  lea     r8d, [rdx+40h]; Size
0x18003115c  lea     rcx, [rbp+0B0h+var_60]; void *
0x180031160  call    memset_0
0x180031165  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003116a  lea     rcx, [rbp+0B0h+var_60]
0x18003116e  mov     [rsp+1B0h+var_150], rcx
0x180031173  lea     rcx, [rbp+0B0h+var_20]
0x18003117a  mov     [rsp+1B0h+var_148], rcx
0x18003117f  mov     r9b, 5Fh ; '_'
0x180031182  mov     edx, eax
0x180031184  lea     rcx, [rsp+1B0h+var_150]
0x180031189  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003118e  lea     rax, WPP_GLOBAL_Control
0x180031195  mov     rcx, cs:WPP_GLOBAL_Control
0x18003119c  cmp     rcx, rax
0x18003119f  jz      short loc_1800311DA
0x1800311a1  test    byte ptr [rcx+1Ch], 1
0x1800311a5  jz      short loc_1800311DA
0x1800311a7  cmp     byte ptr [rcx+19h], 2
0x1800311ab  jb      short loc_1800311DA
0x1800311ad  lea     rax, [rbp+0B0h+var_B0]
0x1800311b1  cmp     [rbp+0B0h+var_98], 8
0x1800311b6  cmovnb  rax, [rbp+0B0h+var_B0]
0x1800311bb  mov     edx, 64h ; 'd'
0x1800311c0  mov     [rsp+1B0h+var_188], rax
0x1800311c5  mov     eax, [rsp+1B0h+var_168]
0x1800311c9  mov     dword ptr [rsp+1B0h+var_190], eax
0x1800311cd  lea     r9, [rbp+0B0h+var_60]
0x1800311d1  mov     rcx, [rcx+10h]
0x1800311d5  call    WPP_SF_sDS
0x1800311da  lea     rdx, byte_180075E00
0x1800311e1  mov     rcx, rdi
0x1800311e4  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x1800311e9  jmp     loc_1800310B0
0x1800311ee  xor     edx, edx; Val
0x1800311f0  lea     r8d, [rdx+40h]; Size
0x1800311f4  lea     rcx, [rbp+0B0h+var_60]; void *
0x1800311f8  call    memset_0
0x1800311fd  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180031202  lea     rcx, [rbp+0B0h+var_60]
0x180031206  mov     [rsp+1B0h+var_150], rcx
0x18003120b  lea     rcx, [rbp+0B0h+var_20]
0x180031212  mov     [rsp+1B0h+var_148], rcx
0x180031217  mov     r9b, 5Fh ; '_'
0x18003121a  mov     edx, eax
0x18003121c  lea     rcx, [rsp+1B0h+var_150]
0x180031221  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180031226  lea     rax, WPP_GLOBAL_Control
0x18003122d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031234  cmp     rcx, rax
0x180031237  jz      short loc_180031266
0x180031239  test    byte ptr [rcx+1Ch], 1
0x18003123d  jz      short loc_180031266
0x18003123f  cmp     byte ptr [rcx+19h], 2
0x180031243  jb      short loc_180031266
0x180031245  mov     edx, 63h ; 'c'
0x18003124a  mov     eax, [rsp+1B0h+var_168]
0x18003124e  mov     dword ptr [rsp+1B0h+var_190], eax
0x180031252  lea     r9, [rbp+0B0h+var_60]
0x180031256  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x18003125d  mov     rcx, [rcx+10h]
0x180031261  call    WPP_SF_sd
0x180031266  lea     rdx, byte_180075E00
0x18003126d  mov     rcx, rdi
0x180031270  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180031275  nop
0x180031276  lea     rcx, [rsp+1B0h+TransactionHandle]
0x18003127b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031280  nop
0x180031281  lea     rcx, [rbp+0B0h+var_110]
0x180031285  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_78a91e47f7e24fb222e85682750c13f8_______operator__
0x18003128a  nop
0x18003128b  lea     rcx, [rsp+1B0h+var_168]
0x180031290  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180031295  nop
0x180031296  mov     rax, rdi
0x180031299  mov     rcx, [rbp+0B0h+var_20]
0x1800312a0  xor     rcx, rsp; StackCookie
0x1800312a3  call    __security_check_cookie
0x1800312a8  mov     rbx, [rsp+1B0h+arg_10]
0x1800312b0  add     rsp, 1A0h
0x1800312b7  pop     rdi
0x1800312b8  pop     rsi
0x1800312b9  pop     rbp
0x1800312ba  retn
```

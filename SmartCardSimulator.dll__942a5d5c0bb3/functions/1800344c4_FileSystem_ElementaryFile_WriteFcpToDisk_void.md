# FileSystem::ElementaryFile::WriteFcpToDisk(void)

- ea: `0x1800344c4`
- end: `0x180034b4d`
- name: `?WriteFcpToDisk@ElementaryFile@FileSystem@@AEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@XZ`
- size: `1673`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180029388`
- `0x1800334ec`

## callees

- `0x180007a64`
- `0x180007fe0`
- `0x180008000`
- `0x180008148`
- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18000a960`
- `0x18000a9c4`
- `0x18000c950`
- `0x18000efc0`
- `0x18000fb88`
- `0x18001098c`
- `0x18001e778`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x180026178`
- `0x1800261bc`
- `0x180029b84`
- `0x18002de50`
- `0x18002f4e0`
- `0x18002fae4`
- `0x180030254`
- `0x1800344c4`
- `0x180034b54`
- `0x1800380d4`
- `0x18003aeb0`
- `0x18003af6c`
- `0x18003b014`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x1800349cb`
- `ktmw32!CommitTransaction` at `0x1800349cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_BYTE *__fastcall FileSystem::ElementaryFile::WriteFcpToDisk(__int64 a1, _BYTE *a2)
{
  __int64 FilesystemTransaction; // rax
  _QWORD *v5; // rbx
  _DWORD *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // r8d
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // r8d
  char *v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // r9
  __int64 v19; // r8
  int v20; // r8d
  __int64 v21; // rax
  __int64 v22; // rdx
  _DWORD *v23; // rax
  unsigned int v24; // eax
  __int64 v25; // r9
  __int64 v26; // r8
  int v27; // r8d
  WCHAR *v28; // rax
  char *v29; // rdx
  __int64 v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // r9
  __int64 v33; // r8
  int v34; // r8d
  WCHAR *v35; // rax
  BOOL v36; // eax
  __int64 winerror_if; // rax
  unsigned int v38; // eax
  __int64 v39; // r9
  __int64 v40; // r8
  unsigned int v41; // eax
  __int64 v42; // r9
  __int64 v43; // r8
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  int v46; // [rsp+34h] [rbp-CCh]
  char v47; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE *v48; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v49; // [rsp+48h] [rbp-B8h]
  HANDLE TransactionHandle; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v51[2]; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v52; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v53; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v54; // [rsp+70h] [rbp-90h] BYREF
  __int16 v55; // [rsp+78h] [rbp-88h]
  int v56; // [rsp+80h] [rbp-80h]
  int *v57; // [rsp+88h] [rbp-78h] BYREF
  HANDLE *p_TransactionHandle; // [rsp+90h] [rbp-70h]
  _BYTE v59[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v60[32]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v61[12]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v62; // [rsp+F8h] [rbp-8h]
  _BYTE v63[64]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v64[2]; // [rsp+150h] [rbp+50h] BYREF

  v48 = a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v56 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v45);
  v47 = 1;
  lambda_cc0d561d0a39378afeb417c3dd28e652_::_lambda_cc0d561d0a39378afeb417c3dd28e652_(
    (unsigned int)v60,
    (unsigned int)&v47,
    a1,
    (_DWORD)a2,
    (__int64)&v45);
  lambda_cc0d561d0a39378afeb417c3dd28e652_::operator()(v60);
  v47 = 0;
  v54 = v60;
  v55 = 258;
  TransactionHandle = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v63);
  v57 = &v45;
  p_TransactionHandle = &TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v57,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v63);
  v46 = 3;
  if ( v45 )
  {
    memset_0(v63, 0, sizeof(v63));
    v41 = ReportIndentTracker::Indent();
    v48 = v63;
    v49 = v64;
    LOBYTE(v42) = 95;
    ReportIndentTracker::Format(&v48, v41, v43, v42);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v63,
        v45);
    }
    goto LABEL_53;
  }
  v53 = TransactionHandle;
  v5 = (_QWORD *)(a1 + 136);
  v6 = FileSystem::DiskOperations::CreateDirectoryOnDisk(&v52, (const WCHAR *)(a1 + 136), &v53);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v45, v6);
  v46 = 3;
  if ( !v45 )
    goto LABEL_5;
  if ( v45 != 183 )
  {
    if ( v45 == 112 )
    {
      memset_0(v63, 0, sizeof(v63));
      v12 = ReportIndentTracker::Indent();
      v48 = v63;
      v49 = v64;
      LOBYTE(v13) = 95;
      ReportIndentTracker::Format(&v48, v12, v14, v13);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *(_QWORD *)(a1 + 160) >= 8u )
          v5 = (_QWORD *)*v5;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, v15, (unsigned int)v63, (__int64)v5);
      }
      v16 = &byte_180075BF0;
      goto LABEL_54;
    }
    memset_0(v63, 0, sizeof(v63));
    v17 = ReportIndentTracker::Indent();
    v48 = v63;
    v49 = v64;
    LOBYTE(v18) = 95;
    ReportIndentTracker::Format(&v48, v17, v19, v18);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *(_QWORD *)(a1 + 160) >= 8u )
        v5 = (_QWORD *)*v5;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, v20, (unsigned int)v63, v45, (__int64)v5);
    }
LABEL_53:
    v16 = &byte_180075E00;
LABEL_54:
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v16);
    goto LABEL_55;
  }
  LODWORD(v53) = 0;
  errorlib::scoped_error<winerror_error::tag>::initiate<long>(&v45, &v53);
LABEL_5:
  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(v51);
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v59);
  v7 = DataObjectImplicit<ScardGidsModule,5>::encode(v63, a1 + 32);
  v57 = v51;
  p_TransactionHandle = (HANDLE *)v59;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<unsigned char,wil::secure_allocator<unsigned char>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v57,
    v7);
  std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v63);
  v51[1] = 3;
  if ( (unsigned int)((v51[0] >> 30) - 1) <= 2 )
  {
    memset_0(v63, 0, sizeof(v63));
    v8 = ReportIndentTracker::Indent();
    v48 = v63;
    v49 = v64;
    LOBYTE(v9) = 95;
    ReportIndentTracker::Format(&v48, v8, v10, v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, v11, (unsigned int)v63, v51[0], *(_WORD *)(a1 + 36));
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
    goto LABEL_11;
  }
  v21 = std::operator+<unsigned short>(v63, a1 + 136);
  std::operator+<unsigned short>(v61, v21, L"fcp");
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(v63, v22, 0);
  v52 = TransactionHandle;
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v48, v59);
  v23 = FileSystem::DiskOperations::WriteFileToDisk(&v53, v61, &v48, &v52);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v45, v23);
  v46 = 3;
  if ( v45 )
  {
    if ( v45 == 112 )
    {
      memset_0(v63, 0, sizeof(v63));
      v24 = ReportIndentTracker::Indent();
      v48 = v63;
      v49 = v64;
      LOBYTE(v25) = 95;
      ReportIndentTracker::Format(&v48, v24, v26, v25);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = v61;
        if ( v62 >= 8 )
          v28 = *(WCHAR **)v61;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v27, (unsigned int)v63, (__int64)v28);
      }
      v29 = &byte_180075BF0;
      goto LABEL_35;
    }
    memset_0(v63, 0, sizeof(v63));
    v31 = ReportIndentTracker::Indent();
    v48 = v63;
    v49 = v64;
    LOBYTE(v32) = 95;
    ReportIndentTracker::Format(&v48, v31, v33, v32);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v35 = v61;
      if ( v62 >= 8 )
        v35 = *(WCHAR **)v61;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, v34, (unsigned int)v63, v45, (__int64)v35);
    }
  }
  else
  {
    v36 = CommitTransaction(TransactionHandle);
    winerror_if = make_winerror_if(&v52, !v36);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v45, winerror_if);
    v46 = 3;
    if ( !v45 )
      goto LABEL_36;
    memset_0(v63, 0, sizeof(v63));
    v38 = ReportIndentTracker::Indent();
    v48 = v63;
    v49 = v64;
    LOBYTE(v39) = 95;
    ReportIndentTracker::Format(&v48, v38, v40, v39);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v63,
        v45);
    }
  }
  v29 = &byte_180075E00;
LABEL_35:
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v29);
LABEL_36:
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v61, v30, 0);
LABEL_11:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v59);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v51);
LABEL_55:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TransactionHandle);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_cc0d561d0a39378afeb417c3dd28e652_____::operator()(&v54);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v45);
  return a2;
}

```

## disassembly

```asm
0x1800344c4  mov     [rsp-8+arg_10], rbx
0x1800344c9  mov     [rsp-8+arg_18], rsi
0x1800344ce  push    rbp
0x1800344cf  push    rdi
0x1800344d0  push    r13
0x1800344d2  lea     rbp, [rsp-60h]
0x1800344d7  sub     rsp, 160h
0x1800344de  mov     rax, cs:__security_cookie
0x1800344e5  xor     rax, rsp
0x1800344e8  mov     [rbp+70h+var_20], rax
0x1800344ec  mov     rdi, rdx
0x1800344ef  mov     rsi, rcx
0x1800344f2  mov     qword ptr [rsp+170h+var_130], rdx
0x1800344f7  mov     [rbp+70h+var_F0], 1
0x1800344fe  mov     rcx, rdx
0x180034501  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180034506  nop
0x180034507  mov     [rbp+70h+var_F0], 1
0x18003450e  lea     rcx, [rsp+170h+var_140]
0x180034513  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180034518  nop
0x180034519  mov     [rsp+170h+var_138], 1
0x18003451e  lea     rax, [rsp+170h+var_140]
0x180034523  mov     [rsp+170h+var_150], rax
0x180034528  mov     r9, rdi
0x18003452b  mov     r8, rsi
0x18003452e  lea     rdx, [rsp+170h+var_138]
0x180034533  lea     rcx, [rbp+70h+var_B0]
0x180034537  call    _lambda_cc0d561d0a39378afeb417c3dd28e652____lambda_cc0d561d0a39378afeb417c3dd28e652_
0x18003453c  lea     rcx, [rbp+70h+var_B0]
0x180034540  call    _lambda_cc0d561d0a39378afeb417c3dd28e652___operator__
0x180034545  mov     [rsp+170h+var_138], 0
0x18003454a  lea     rax, [rbp+70h+var_B0]
0x18003454e  mov     [rsp+170h+var_100], rax
0x180034553  mov     [rsp+170h+var_F8], 102h
0x18003455a  mov     [rsp+170h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x180034563  lea     rcx, [rbp+70h+var_60]
0x180034567  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x18003456c  lea     rcx, [rsp+170h+var_140]
0x180034571  mov     [rbp+70h+var_E8], rcx
0x180034575  lea     rcx, [rsp+170h+TransactionHandle]
0x18003457a  mov     [rbp+70h+var_E0], rcx
0x18003457e  mov     rdx, rax
0x180034581  lea     rcx, [rbp+70h+var_E8]
0x180034585  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x18003458a  lea     rcx, [rbp+70h+var_60]
0x18003458e  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x180034593  mov     r13d, 3
0x180034599  mov     [rsp+170h+var_13C], r13d
0x18003459e  cmp     [rsp+170h+var_140], 0
0x1800345a3  jnz     loc_180034A80
0x1800345a9  mov     rax, [rsp+170h+TransactionHandle]
0x1800345ae  mov     [rsp+170h+var_108], rax
0x1800345b3  lea     rbx, [rsi+88h]
0x1800345ba  lea     r8, [rsp+170h+var_108]
0x1800345bf  mov     rdx, rbx
0x1800345c2  lea     rcx, [rsp+170h+var_110]
0x1800345c7  call    ?CreateDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::CreateDirectoryOnDisk(std::wstring const &,void * const &)
0x1800345cc  mov     rdx, rax
0x1800345cf  lea     rcx, [rsp+170h+var_140]
0x1800345d4  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800345d9  mov     [rsp+170h+var_13C], r13d
0x1800345de  mov     eax, [rsp+170h+var_140]
0x1800345e2  test    eax, eax
0x1800345e4  jz      short loc_180034608
0x1800345e6  cmp     eax, 0B7h
0x1800345eb  jnz     loc_180034708
0x1800345f1  mov     dword ptr [rsp+170h+var_108], 0
0x1800345f9  lea     rdx, [rsp+170h+var_108]
0x1800345fe  lea     rcx, [rsp+170h+var_140]
0x180034603  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180034608  lea     rcx, [rsp+170h+var_118]
0x18003460d  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x180034612  nop
0x180034613  lea     rcx, [rbp+70h+var_D0]
0x180034617  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x18003461c  nop
0x18003461d  lea     rdx, [rsi+20h]
0x180034621  lea     rcx, [rbp+70h+var_60]
0x180034625  call    ?encode@?$DataObjectImplicit@UScardGidsModule@@$04@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z; DataObjectImplicit<ScardGidsModule,5>::encode(DataObjectImplicit<ScardGidsModule,5>::type const &)
0x18003462a  nop
0x18003462b  lea     rcx, [rsp+170h+var_118]
0x180034630  mov     [rbp+70h+var_E8], rcx
0x180034634  lea     rcx, [rbp+70h+var_D0]
0x180034638  mov     [rbp+70h+var_E0], rcx
0x18003463c  mov     rdx, rax
0x18003463f  lea     rcx, [rbp+70h+var_E8]
0x180034643  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@3@U453@U453@U453@U453@U453@U453@U453@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAV?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180034648  nop
0x180034649  lea     rcx, [rbp+70h+var_60]
0x18003464d  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x180034652  mov     [rsp+170h+var_114], r13d
0x180034657  mov     eax, [rsp+170h+var_118]
0x18003465b  shr     eax, 1Eh
0x18003465e  dec     eax
0x180034660  cmp     eax, 2
0x180034663  ja      loc_180034812
0x180034669  xor     edx, edx; Val
0x18003466b  lea     r8d, [rdx+40h]; Size
0x18003466f  lea     rcx, [rbp+70h+var_60]; void *
0x180034673  call    memset_0
0x180034678  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003467d  lea     rcx, [rbp+70h+var_60]
0x180034681  mov     qword ptr [rsp+170h+var_130], rcx
0x180034686  lea     rcx, [rbp+70h+var_20]
0x18003468a  mov     qword ptr [rsp+170h+var_130+8], rcx
0x18003468f  mov     r9b, 5Fh ; '_'
0x180034692  mov     edx, eax
0x180034694  lea     rcx, [rsp+170h+var_130]
0x180034699  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003469e  lea     rax, WPP_GLOBAL_Control
0x1800346a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800346ac  cmp     rcx, rax
0x1800346af  jz      short loc_1800346DF
0x1800346b1  test    byte ptr [rcx+1Ch], 1
0x1800346b5  jz      short loc_1800346DF
0x1800346b7  cmp     byte ptr [rcx+19h], 2
0x1800346bb  jb      short loc_1800346DF
0x1800346bd  movzx   eax, word ptr [rsi+24h]
0x1800346c1  mov     edx, 4Dh ; 'M'
0x1800346c6  mov     dword ptr [rsp+170h+var_148], eax
0x1800346ca  mov     eax, [rsp+170h+var_118]
0x1800346ce  mov     dword ptr [rsp+170h+var_150], eax
0x1800346d2  lea     r9, [rbp+70h+var_60]
0x1800346d6  mov     rcx, [rcx+10h]
0x1800346da  call    WPP_SF_sdD
0x1800346df  lea     rdx, byte_180075E00
0x1800346e6  mov     rcx, rdi
0x1800346e9  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x1800346ee  nop
0x1800346ef  lea     rcx, [rbp+70h+var_D0]
0x1800346f3  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800346f8  nop
0x1800346f9  lea     rcx, [rsp+170h+var_118]
0x1800346fe  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180034703  jmp     loc_180034B05
0x180034708  xor     edx, edx; Val
0x18003470a  lea     r8d, [rdx+40h]; Size
0x18003470e  lea     rcx, [rbp+70h+var_60]; void *
0x180034712  cmp     eax, 70h ; 'p'
0x180034715  jnz     short loc_18003478E
0x180034717  call    memset_0
0x18003471c  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034721  lea     rcx, [rbp+70h+var_60]
0x180034725  mov     qword ptr [rsp+170h+var_130], rcx
0x18003472a  lea     rcx, [rbp+70h+var_20]
0x18003472e  mov     qword ptr [rsp+170h+var_130+8], rcx
0x180034733  mov     r9b, 5Fh ; '_'
0x180034736  mov     edx, eax
0x180034738  lea     rcx, [rsp+170h+var_130]
0x18003473d  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034742  lea     rax, WPP_GLOBAL_Control
0x180034749  mov     rcx, cs:WPP_GLOBAL_Control
0x180034750  cmp     rcx, rax
0x180034753  jz      short loc_180034782
0x180034755  test    byte ptr [rcx+1Ch], 1
0x180034759  jz      short loc_180034782
0x18003475b  cmp     byte ptr [rcx+19h], 2
0x18003475f  jb      short loc_180034782
0x180034761  cmp     qword ptr [rbx+18h], 8
0x180034766  jb      short loc_18003476B
0x180034768  mov     rbx, [rbx]
0x18003476b  mov     edx, 4Bh ; 'K'
0x180034770  mov     [rsp+170h+var_150], rbx
0x180034775  lea     r9, [rbp+70h+var_60]
0x180034779  mov     rcx, [rcx+10h]
0x18003477d  call    WPP_SF_sS
0x180034782  lea     rdx, byte_180075BF0
0x180034789  jmp     loc_180034AFC
0x18003478e  call    memset_0
0x180034793  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034798  lea     rcx, [rbp+70h+var_60]
0x18003479c  mov     qword ptr [rsp+170h+var_130], rcx
0x1800347a1  lea     rcx, [rbp+70h+var_20]
0x1800347a5  mov     qword ptr [rsp+170h+var_130+8], rcx
0x1800347aa  mov     r9b, 5Fh ; '_'
0x1800347ad  mov     edx, eax
0x1800347af  lea     rcx, [rsp+170h+var_130]
0x1800347b4  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800347b9  lea     rax, WPP_GLOBAL_Control
0x1800347c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347c7  cmp     rcx, rax
0x1800347ca  jz      loc_180034AF5
0x1800347d0  test    byte ptr [rcx+1Ch], 1
0x1800347d4  jz      loc_180034AF5
0x1800347da  cmp     byte ptr [rcx+19h], 2
0x1800347de  jb      loc_180034AF5
0x1800347e4  cmp     qword ptr [rbx+18h], 8
0x1800347e9  jb      short loc_1800347EE
0x1800347eb  mov     rbx, [rbx]
0x1800347ee  mov     edx, 4Ch ; 'L'
0x1800347f3  mov     [rsp+170h+var_148], rbx
0x1800347f8  mov     eax, [rsp+170h+var_140]
0x1800347fc  mov     dword ptr [rsp+170h+var_150], eax
0x180034800  lea     r9, [rbp+70h+var_60]
0x180034804  mov     rcx, [rcx+10h]
0x180034808  call    WPP_SF_sDS
0x18003480d  jmp     loc_180034AF5
0x180034812  mov     rdx, rbx
0x180034815  lea     rcx, [rbp+70h+var_60]
0x180034819  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18003481e  nop
0x18003481f  lea     r8, aFcp; "fcp"
0x180034826  mov     rdx, rax
0x180034829  lea     rcx, [rbp+70h+var_90]
0x18003482d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180034832  nop
0x180034833  xor     r8d, r8d
0x180034836  mov     dl, 1
0x180034838  lea     rcx, [rbp+70h+var_60]
0x18003483c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180034841  mov     rax, [rsp+170h+TransactionHandle]
0x180034846  mov     [rsp+170h+var_110], rax
0x18003484b  lea     rdx, [rbp+70h+var_D0]
0x18003484f  lea     rcx, [rsp+170h+var_130]
0x180034854  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x180034859  movaps  xmm0, [rsp+170h+var_130]
0x18003485e  movdqa  [rsp+170h+var_130], xmm0
0x180034864  lea     r9, [rsp+170h+var_110]
0x180034869  lea     r8, [rsp+170h+var_130]
0x18003486e  lea     rdx, [rbp+70h+var_90]
0x180034872  lea     rcx, [rsp+170h+var_108]
0x180034877  call    ?WriteFileToDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@AEBQEAX@Z; FileSystem::DiskOperations::WriteFileToDisk(std::wstring const &,rangelib::range<uchar const *>,void * const &)
0x18003487c  mov     rdx, rax
0x18003487f  lea     rcx, [rsp+170h+var_140]
0x180034884  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180034889  mov     [rsp+170h+var_13C], r13d
0x18003488e  mov     eax, [rsp+170h+var_140]
0x180034892  test    eax, eax
0x180034894  jz      loc_1800349C6
0x18003489a  xor     edx, edx; Val
0x18003489c  lea     r8d, [rdx+40h]; Size
0x1800348a0  lea     rcx, [rbp+70h+var_60]; void *
0x1800348a4  cmp     eax, 70h ; 'p'
0x1800348a7  jnz     loc_18003493E
0x1800348ad  call    memset_0
0x1800348b2  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x1800348b7  lea     rcx, [rbp+70h+var_60]
0x1800348bb  mov     qword ptr [rsp+170h+var_130], rcx
0x1800348c0  lea     rcx, [rbp+70h+var_20]
0x1800348c4  mov     qword ptr [rsp+170h+var_130+8], rcx
0x1800348c9  mov     r9b, 5Fh ; '_'
0x1800348cc  mov     edx, eax
0x1800348ce  lea     rcx, [rsp+170h+var_130]
0x1800348d3  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800348d8  lea     rax, WPP_GLOBAL_Control
0x1800348df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348e6  cmp     rcx, rax
0x1800348e9  jz      short loc_18003491C
0x1800348eb  test    byte ptr [rcx+1Ch], 1
0x1800348ef  jz      short loc_18003491C
0x1800348f1  cmp     byte ptr [rcx+19h], 2
0x1800348f5  jb      short loc_18003491C
0x1800348f7  lea     rax, [rbp+70h+var_90]
0x1800348fb  cmp     [rbp+70h+var_78], 8
0x180034900  cmovnb  rax, qword ptr [rbp+70h+var_90]
0x180034905  mov     edx, 4Eh ; 'N'
0x18003490a  mov     [rsp+170h+var_150], rax
0x18003490f  lea     r9, [rbp+70h+var_60]
0x180034913  mov     rcx, [rcx+10h]
0x180034917  call    WPP_SF_sS
0x18003491c  lea     rdx, byte_180075BF0
0x180034923  mov     rcx, rdi
0x180034926  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x18003492b  xor     r8d, r8d
0x18003492e  mov     dl, 1
0x180034930  lea     rcx, [rbp+70h+var_90]
0x180034934  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180034939  jmp     loc_1800346EF
0x18003493e  call    memset_0
0x180034943  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034948  lea     rcx, [rbp+70h+var_60]
0x18003494c  mov     qword ptr [rsp+170h+var_130], rcx
0x180034951  lea     rcx, [rbp+70h+var_20]
0x180034955  mov     qword ptr [rsp+170h+var_130+8], rcx
0x18003495a  mov     r9b, 5Fh ; '_'
0x18003495d  mov     edx, eax
0x18003495f  lea     rcx, [rsp+170h+var_130]
0x180034964  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034969  lea     rax, WPP_GLOBAL_Control
0x180034970  mov     rcx, cs:WPP_GLOBAL_Control
0x180034977  cmp     rcx, rax
0x18003497a  jz      loc_180034A74
0x180034980  test    byte ptr [rcx+1Ch], 1
0x180034984  jz      loc_180034A74
0x18003498a  cmp     byte ptr [rcx+19h], 2
0x18003498e  jb      loc_180034A74
0x180034994  lea     rax, [rbp+70h+var_90]
0x180034998  cmp     [rbp+70h+var_78], 8
0x18003499d  cmovnb  rax, qword ptr [rbp+70h+var_90]
0x1800349a2  mov     edx, 4Fh ; 'O'
0x1800349a7  mov     [rsp+170h+var_148], rax
0x1800349ac  mov     eax, [rsp+170h+var_140]
0x1800349b0  mov     dword ptr [rsp+170h+var_150], eax
0x1800349b4  lea     r9, [rbp+70h+var_60]
0x1800349b8  mov     rcx, [rcx+10h]
0x1800349bc  call    WPP_SF_sDS
0x1800349c1  jmp     loc_180034A74
0x1800349c6  mov     rcx, [rsp+170h+TransactionHandle]; TransactionHandle
0x1800349cb  call    cs:__imp_CommitTransaction
  ... truncated ...
```

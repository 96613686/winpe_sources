# FileSystem::DedicatedFile::WriteFcpToDisk(void)

- ea: `0x180033e14`
- end: `0x1800344bb`
- name: `?WriteFcpToDisk@DedicatedFile@FileSystem@@AEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@XZ`
- size: `1703`
- prototype: ``
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180025890`
- `0x180033384`

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
- `0x1800287d0`
- `0x180029b84`
- `0x18002cef8`
- `0x18002f3d8`
- `0x18002fae4`
- `0x180030254`
- `0x180033e14`
- `0x180034b54`
- `0x180037e60`
- `0x18003aeb0`
- `0x18003af6c`
- `0x18003b0a0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x18003433a`
- `ktmw32!CommitTransaction` at `0x18003433a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall FileSystem::DedicatedFile::WriteFcpToDisk(__int64 a1, __int64 a2)
{
  __int64 FilesystemTransaction; // rax
  _QWORD *v5; // rbx
  _DWORD *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  int v16; // r8d
  char *v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // r8d
  __int64 v22; // rax
  __int64 v23; // rdx
  _DWORD *v24; // rax
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // r8
  int v28; // r8d
  WCHAR *v29; // rax
  char *v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // r9
  __int64 v34; // r8
  int v35; // r8d
  WCHAR *v36; // rax
  BOOL v37; // eax
  __int64 winerror_if; // rax
  unsigned int v39; // eax
  __int64 v40; // r9
  __int64 v41; // r8
  unsigned int v42; // eax
  __int64 v43; // r9
  __int64 v44; // r8
  int v46; // [rsp+30h] [rbp-D0h] BYREF
  int v47; // [rsp+34h] [rbp-CCh]
  char v48; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v49; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TransactionHandle; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v51[2]; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v52; // [rsp+60h] [rbp-A0h] BYREF
  int *v53; // [rsp+68h] [rbp-98h] BYREF
  HANDLE *p_TransactionHandle; // [rsp+70h] [rbp-90h]
  _BYTE *v55; // [rsp+80h] [rbp-80h] BYREF
  __int16 v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+90h] [rbp-70h]
  _BYTE v58[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v59[32]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR v60[12]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v61; // [rsp+F0h] [rbp-10h]
  _BYTE v62[64]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v63[2]; // [rsp+140h] [rbp+40h] BYREF

  *(_QWORD *)&v49 = a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v57 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v46);
  v48 = 1;
  lambda_cc0d561d0a39378afeb417c3dd28e652_::_lambda_cc0d561d0a39378afeb417c3dd28e652_(
    (unsigned int)v59,
    (unsigned int)&v48,
    a1,
    a2,
    (__int64)&v46);
  lambda_9321ce3b3e978945ba87d9863b360b06_::operator()(v59);
  v48 = 0;
  v55 = v59;
  v56 = 258;
  TransactionHandle = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v62);
  v53 = &v46;
  p_TransactionHandle = &TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v53,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v62);
  v47 = 3;
  if ( v46 )
  {
    memset_0(v62, 0, sizeof(v62));
    v42 = ReportIndentTracker::Indent();
    *(_QWORD *)&v49 = v62;
    *((_QWORD *)&v49 + 1) = v63;
    LOBYTE(v43) = 95;
    ReportIndentTracker::Format(&v49, v42, v44, v43);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        114,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v62,
        v46);
    }
    goto LABEL_53;
  }
  v52 = TransactionHandle;
  v5 = (_QWORD *)(a1 + 152);
  v6 = FileSystem::DiskOperations::CreateDirectoryOnDisk(&v53, (const WCHAR *)(a1 + 152), &v52);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v46, v6);
  v47 = 3;
  if ( !v46 )
    goto LABEL_5;
  if ( v46 != 183 )
  {
    if ( v46 == 112 )
    {
      memset_0(v62, 0, sizeof(v62));
      v13 = ReportIndentTracker::Indent();
      *(_QWORD *)&v49 = v62;
      *((_QWORD *)&v49 + 1) = v63;
      LOBYTE(v14) = 95;
      ReportIndentTracker::Format(&v49, v13, v15, v14);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *(_QWORD *)(a1 + 176) >= 8u )
          v5 = (_QWORD *)*v5;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, v16, (unsigned int)v62, (__int64)v5);
      }
      v17 = &byte_180075BF0;
      goto LABEL_54;
    }
    memset_0(v62, 0, sizeof(v62));
    v18 = ReportIndentTracker::Indent();
    *(_QWORD *)&v49 = v62;
    *((_QWORD *)&v49 + 1) = v63;
    LOBYTE(v19) = 95;
    ReportIndentTracker::Format(&v49, v18, v20, v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *(_QWORD *)(a1 + 176) >= 8u )
        v5 = (_QWORD *)*v5;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v21, (unsigned int)v62, v46, (__int64)v5);
    }
LABEL_53:
    v17 = &byte_180075E00;
LABEL_54:
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v17);
    goto LABEL_55;
  }
  LODWORD(v52) = 0;
  errorlib::scoped_error<winerror_error::tag>::initiate<long>(&v46, &v52);
LABEL_5:
  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(v51);
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v58);
  v7 = DataObjectImplicit<ScardGidsModule,4>::encode(v62, a1 + 32);
  v53 = v51;
  p_TransactionHandle = (HANDLE *)v58;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<unsigned char,wil::secure_allocator<unsigned char>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v53,
    v7);
  std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v62);
  v51[1] = 3;
  if ( (unsigned int)((v51[0] >> 30) - 1) <= 2 )
  {
    memset_0(v62, 0, sizeof(v62));
    v8 = ReportIndentTracker::Indent();
    *(_QWORD *)&v49 = v62;
    *((_QWORD *)&v49 + 1) = v63;
    LOBYTE(v9) = 95;
    ReportIndentTracker::Format(&v49, v8, v10, v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v49 = *(_OWORD *)log_byterange<std::vector<unsigned char> const &>(&v53, a1 + 40);
      WPP_SF_sd_HEX_(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, (unsigned int)v62, v51[0], (__int64)&v49);
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
    goto LABEL_11;
  }
  v22 = std::operator+<unsigned short>(v62, a1 + 152);
  std::operator+<unsigned short>(v60, v22, L"fcp");
  LOBYTE(v23) = 1;
  std::wstring::_Tidy(v62, v23, 0);
  v53 = (int *)TransactionHandle;
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v49, v58);
  v24 = FileSystem::DiskOperations::WriteFileToDisk(&v52, v60, &v49, (void **)&v53);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v46, v24);
  v47 = 3;
  if ( v46 )
  {
    if ( v46 == 112 )
    {
      memset_0(v62, 0, sizeof(v62));
      v25 = ReportIndentTracker::Indent();
      *(_QWORD *)&v49 = v62;
      *((_QWORD *)&v49 + 1) = v63;
      LOBYTE(v26) = 95;
      ReportIndentTracker::Format(&v49, v25, v27, v26);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = v60;
        if ( v61 >= 8 )
          v29 = *(WCHAR **)v60;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v28, (unsigned int)v62, (__int64)v29);
      }
      v30 = &byte_180075BF0;
      goto LABEL_35;
    }
    memset_0(v62, 0, sizeof(v62));
    v32 = ReportIndentTracker::Indent();
    *(_QWORD *)&v49 = v62;
    *((_QWORD *)&v49 + 1) = v63;
    LOBYTE(v33) = 95;
    ReportIndentTracker::Format(&v49, v32, v34, v33);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = v60;
      if ( v61 >= 8 )
        v36 = *(WCHAR **)v60;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v35, (unsigned int)v62, v46, (__int64)v36);
    }
  }
  else
  {
    v37 = CommitTransaction(TransactionHandle);
    winerror_if = make_winerror_if(&v53, !v37);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v46, winerror_if);
    v47 = 3;
    if ( !v46 )
      goto LABEL_36;
    memset_0(v62, 0, sizeof(v62));
    v39 = ReportIndentTracker::Indent();
    *(_QWORD *)&v49 = v62;
    *((_QWORD *)&v49 + 1) = v63;
    LOBYTE(v40) = 95;
    ReportIndentTracker::Format(&v49, v39, v41, v40);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v62,
        v46);
    }
  }
  v30 = &byte_180075E00;
LABEL_35:
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v30);
LABEL_36:
  LOBYTE(v31) = 1;
  std::wstring::_Tidy(v60, v31, 0);
LABEL_11:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v58);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v51);
LABEL_55:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TransactionHandle);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_9321ce3b3e978945ba87d9863b360b06_____::operator()(&v55);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v46);
  return a2;
}

```

## disassembly

```asm
0x180033e14  mov     [rsp-8+arg_10], rbx
0x180033e19  mov     [rsp-8+arg_18], rsi
0x180033e1e  push    rbp
0x180033e1f  push    rdi
0x180033e20  push    r13
0x180033e22  lea     rbp, [rsp-50h]
0x180033e27  sub     rsp, 150h
0x180033e2e  mov     rax, cs:__security_cookie
0x180033e35  xor     rax, rsp
0x180033e38  mov     [rbp+60h+var_20], rax
0x180033e3c  mov     rdi, rdx
0x180033e3f  mov     rsi, rcx
0x180033e42  mov     qword ptr [rsp+160h+var_120], rdx
0x180033e47  mov     [rbp+60h+var_D0], 1
0x180033e4e  mov     rcx, rdx
0x180033e51  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180033e56  nop
0x180033e57  mov     [rbp+60h+var_D0], 1
0x180033e5e  lea     rcx, [rsp+160h+var_130]
0x180033e63  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180033e68  nop
0x180033e69  mov     [rsp+160h+var_128], 1
0x180033e6e  lea     rax, [rsp+160h+var_130]
0x180033e73  mov     [rsp+160h+var_140], rax
0x180033e78  mov     r9, rdi
0x180033e7b  mov     r8, rsi
0x180033e7e  lea     rdx, [rsp+160h+var_128]
0x180033e83  lea     rcx, [rbp+60h+var_A8]
0x180033e87  call    _lambda_cc0d561d0a39378afeb417c3dd28e652____lambda_cc0d561d0a39378afeb417c3dd28e652_
0x180033e8c  lea     rcx, [rbp+60h+var_A8]
0x180033e90  call    _lambda_9321ce3b3e978945ba87d9863b360b06___operator__
0x180033e95  mov     [rsp+160h+var_128], 0
0x180033e9a  lea     rax, [rbp+60h+var_A8]
0x180033e9e  mov     [rbp+60h+var_E0], rax
0x180033ea2  mov     [rbp+60h+var_D8], 102h
0x180033ea8  mov     [rsp+160h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x180033eb1  lea     rcx, [rbp+60h+var_60]
0x180033eb5  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x180033eba  lea     rcx, [rsp+160h+var_130]
0x180033ebf  mov     [rsp+160h+var_F8], rcx
0x180033ec4  lea     rcx, [rsp+160h+TransactionHandle]
0x180033ec9  mov     [rsp+160h+var_F0], rcx
0x180033ece  mov     rdx, rax
0x180033ed1  lea     rcx, [rsp+160h+var_F8]
0x180033ed6  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180033edb  lea     rcx, [rbp+60h+var_60]
0x180033edf  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x180033ee4  mov     r13d, 3
0x180033eea  mov     [rsp+160h+var_12C], r13d
0x180033eef  cmp     [rsp+160h+var_130], 0
0x180033ef4  jnz     loc_1800343EF
0x180033efa  mov     rax, [rsp+160h+TransactionHandle]
0x180033eff  mov     [rsp+160h+var_100], rax
0x180033f04  lea     rbx, [rsi+98h]
0x180033f0b  lea     r8, [rsp+160h+var_100]
0x180033f10  mov     rdx, rbx
0x180033f13  lea     rcx, [rsp+160h+var_F8]
0x180033f18  call    ?CreateDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::CreateDirectoryOnDisk(std::wstring const &,void * const &)
0x180033f1d  mov     rdx, rax
0x180033f20  lea     rcx, [rsp+160h+var_130]
0x180033f25  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180033f2a  mov     [rsp+160h+var_12C], r13d
0x180033f2f  mov     eax, [rsp+160h+var_130]
0x180033f33  test    eax, eax
0x180033f35  jz      short loc_180033F59
0x180033f37  cmp     eax, 0B7h
0x180033f3c  jnz     loc_180034077
0x180033f42  mov     dword ptr [rsp+160h+var_100], 0
0x180033f4a  lea     rdx, [rsp+160h+var_100]
0x180033f4f  lea     rcx, [rsp+160h+var_130]
0x180033f54  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180033f59  lea     rcx, [rsp+160h+var_108]
0x180033f5e  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x180033f63  nop
0x180033f64  lea     rcx, [rbp+60h+var_C8]
0x180033f68  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x180033f6d  nop
0x180033f6e  lea     rdx, [rsi+20h]
0x180033f72  lea     rcx, [rbp+60h+var_60]
0x180033f76  call    ?encode@?$DataObjectImplicit@UScardGidsModule@@$03@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z; DataObjectImplicit<ScardGidsModule,4>::encode(DataObjectImplicit<ScardGidsModule,4>::type const &)
0x180033f7b  nop
0x180033f7c  lea     rcx, [rsp+160h+var_108]
0x180033f81  mov     [rsp+160h+var_F8], rcx
0x180033f86  lea     rcx, [rbp+60h+var_C8]
0x180033f8a  mov     [rsp+160h+var_F0], rcx
0x180033f8f  mov     rdx, rax
0x180033f92  lea     rcx, [rsp+160h+var_F8]
0x180033f97  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@3@U453@U453@U453@U453@U453@U453@U453@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAV?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180033f9c  nop
0x180033f9d  lea     rcx, [rbp+60h+var_60]
0x180033fa1  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x180033fa6  mov     [rsp+160h+var_104], r13d
0x180033fab  mov     eax, [rsp+160h+var_108]
0x180033faf  shr     eax, 1Eh
0x180033fb2  dec     eax
0x180033fb4  cmp     eax, 2
0x180033fb7  ja      loc_180034181
0x180033fbd  xor     edx, edx; Val
0x180033fbf  lea     r8d, [rdx+40h]; Size
0x180033fc3  lea     rcx, [rbp+60h+var_60]; void *
0x180033fc7  call    memset_0
0x180033fcc  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180033fd1  lea     rcx, [rbp+60h+var_60]
0x180033fd5  mov     qword ptr [rsp+160h+var_120], rcx
0x180033fda  lea     rcx, [rbp+60h+var_20]
0x180033fde  mov     qword ptr [rsp+160h+var_120+8], rcx
0x180033fe3  mov     r9b, 5Fh ; '_'
0x180033fe6  mov     edx, eax
0x180033fe8  lea     rcx, [rsp+160h+var_120]
0x180033fed  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180033ff2  lea     rax, WPP_GLOBAL_Control
0x180033ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180034000  cmp     rcx, rax
0x180034003  jz      short loc_18003404E
0x180034005  test    byte ptr [rcx+1Ch], 1
0x180034009  jz      short loc_18003404E
0x18003400b  cmp     byte ptr [rcx+19h], 2
0x18003400f  jb      short loc_18003404E
0x180034011  lea     rdx, [rsi+28h]
0x180034015  lea     rcx, [rsp+160h+var_F8]
0x18003401a  call    ??$log_byterange@AEBV?$vector@EV?$allocator@E@std@@@std@@@@YA?AUxbyterange@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; log_byterange<std::vector<uchar> const &>(std::vector<uchar> const &)
0x18003401f  movups  xmm0, xmmword ptr [rax]
0x180034022  movdqu  [rsp+160h+var_120], xmm0
0x180034028  lea     rax, [rsp+160h+var_120]
0x18003402d  mov     [rsp+160h+var_138], rax
0x180034032  mov     eax, [rsp+160h+var_108]
0x180034036  mov     dword ptr [rsp+160h+var_140], eax
0x18003403a  lea     r9, [rbp+60h+var_60]
0x18003403e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034045  mov     rcx, [rcx+10h]
0x180034049  call    WPP_SF_sd_HEX_
0x18003404e  lea     rdx, byte_180075E00
0x180034055  mov     rcx, rdi
0x180034058  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x18003405d  nop
0x18003405e  lea     rcx, [rbp+60h+var_C8]
0x180034062  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180034067  nop
0x180034068  lea     rcx, [rsp+160h+var_108]
0x18003406d  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180034072  jmp     loc_180034474
0x180034077  xor     edx, edx; Val
0x180034079  lea     r8d, [rdx+40h]; Size
0x18003407d  lea     rcx, [rbp+60h+var_60]; void *
0x180034081  cmp     eax, 70h ; 'p'
0x180034084  jnz     short loc_1800340FD
0x180034086  call    memset_0
0x18003408b  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034090  lea     rcx, [rbp+60h+var_60]
0x180034094  mov     qword ptr [rsp+160h+var_120], rcx
0x180034099  lea     rcx, [rbp+60h+var_20]
0x18003409d  mov     qword ptr [rsp+160h+var_120+8], rcx
0x1800340a2  mov     r9b, 5Fh ; '_'
0x1800340a5  mov     edx, eax
0x1800340a7  lea     rcx, [rsp+160h+var_120]
0x1800340ac  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800340b1  lea     rax, WPP_GLOBAL_Control
0x1800340b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340bf  cmp     rcx, rax
0x1800340c2  jz      short loc_1800340F1
0x1800340c4  test    byte ptr [rcx+1Ch], 1
0x1800340c8  jz      short loc_1800340F1
0x1800340ca  cmp     byte ptr [rcx+19h], 2
0x1800340ce  jb      short loc_1800340F1
0x1800340d0  cmp     qword ptr [rbx+18h], 8
0x1800340d5  jb      short loc_1800340DA
0x1800340d7  mov     rbx, [rbx]
0x1800340da  mov     edx, 73h ; 's'
0x1800340df  mov     [rsp+160h+var_140], rbx
0x1800340e4  lea     r9, [rbp+60h+var_60]
0x1800340e8  mov     rcx, [rcx+10h]
0x1800340ec  call    WPP_SF_sS
0x1800340f1  lea     rdx, byte_180075BF0
0x1800340f8  jmp     loc_18003446B
0x1800340fd  call    memset_0
0x180034102  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034107  lea     rcx, [rbp+60h+var_60]
0x18003410b  mov     qword ptr [rsp+160h+var_120], rcx
0x180034110  lea     rcx, [rbp+60h+var_20]
0x180034114  mov     qword ptr [rsp+160h+var_120+8], rcx
0x180034119  mov     r9b, 5Fh ; '_'
0x18003411c  mov     edx, eax
0x18003411e  lea     rcx, [rsp+160h+var_120]
0x180034123  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034128  lea     rax, WPP_GLOBAL_Control
0x18003412f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034136  cmp     rcx, rax
0x180034139  jz      loc_180034464
0x18003413f  test    byte ptr [rcx+1Ch], 1
0x180034143  jz      loc_180034464
0x180034149  cmp     byte ptr [rcx+19h], 2
0x18003414d  jb      loc_180034464
0x180034153  cmp     qword ptr [rbx+18h], 8
0x180034158  jb      short loc_18003415D
0x18003415a  mov     rbx, [rbx]
0x18003415d  mov     edx, 74h ; 't'
0x180034162  mov     [rsp+160h+var_138], rbx
0x180034167  mov     eax, [rsp+160h+var_130]
0x18003416b  mov     dword ptr [rsp+160h+var_140], eax
0x18003416f  lea     r9, [rbp+60h+var_60]
0x180034173  mov     rcx, [rcx+10h]
0x180034177  call    WPP_SF_sDS
0x18003417c  jmp     loc_180034464
0x180034181  mov     rdx, rbx
0x180034184  lea     rcx, [rbp+60h+var_60]
0x180034188  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18003418d  nop
0x18003418e  lea     r8, aFcp; "fcp"
0x180034195  mov     rdx, rax
0x180034198  lea     rcx, [rbp+60h+var_88]
0x18003419c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x1800341a1  nop
0x1800341a2  xor     r8d, r8d
0x1800341a5  mov     dl, 1
0x1800341a7  lea     rcx, [rbp+60h+var_60]
0x1800341ab  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800341b0  mov     rax, [rsp+160h+TransactionHandle]
0x1800341b5  mov     [rsp+160h+var_F8], rax
0x1800341ba  lea     rdx, [rbp+60h+var_C8]
0x1800341be  lea     rcx, [rsp+160h+var_120]
0x1800341c3  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x1800341c8  movaps  xmm0, [rsp+160h+var_120]
0x1800341cd  movdqa  [rsp+160h+var_120], xmm0
0x1800341d3  lea     r9, [rsp+160h+var_F8]
0x1800341d8  lea     r8, [rsp+160h+var_120]
0x1800341dd  lea     rdx, [rbp+60h+var_88]
0x1800341e1  lea     rcx, [rsp+160h+var_100]
0x1800341e6  call    ?WriteFileToDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@AEBQEAX@Z; FileSystem::DiskOperations::WriteFileToDisk(std::wstring const &,rangelib::range<uchar const *>,void * const &)
0x1800341eb  mov     rdx, rax
0x1800341ee  lea     rcx, [rsp+160h+var_130]
0x1800341f3  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800341f8  mov     [rsp+160h+var_12C], r13d
0x1800341fd  mov     eax, [rsp+160h+var_130]
0x180034201  test    eax, eax
0x180034203  jz      loc_180034335
0x180034209  xor     edx, edx; Val
0x18003420b  lea     r8d, [rdx+40h]; Size
0x18003420f  lea     rcx, [rbp+60h+var_60]; void *
0x180034213  cmp     eax, 70h ; 'p'
0x180034216  jnz     loc_1800342AD
0x18003421c  call    memset_0
0x180034221  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034226  lea     rcx, [rbp+60h+var_60]
0x18003422a  mov     qword ptr [rsp+160h+var_120], rcx
0x18003422f  lea     rcx, [rbp+60h+var_20]
0x180034233  mov     qword ptr [rsp+160h+var_120+8], rcx
0x180034238  mov     r9b, 5Fh ; '_'
0x18003423b  mov     edx, eax
0x18003423d  lea     rcx, [rsp+160h+var_120]
0x180034242  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034247  lea     rax, WPP_GLOBAL_Control
0x18003424e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034255  cmp     rcx, rax
0x180034258  jz      short loc_18003428B
0x18003425a  test    byte ptr [rcx+1Ch], 1
0x18003425e  jz      short loc_18003428B
0x180034260  cmp     byte ptr [rcx+19h], 2
0x180034264  jb      short loc_18003428B
0x180034266  lea     rax, [rbp+60h+var_88]
0x18003426a  cmp     [rbp+60h+var_70], 8
0x18003426f  cmovnb  rax, qword ptr [rbp+60h+var_88]
0x180034274  mov     edx, 76h ; 'v'
0x180034279  mov     [rsp+160h+var_140], rax
0x18003427e  lea     r9, [rbp+60h+var_60]
0x180034282  mov     rcx, [rcx+10h]
0x180034286  call    WPP_SF_sS
0x18003428b  lea     rdx, byte_180075BF0
0x180034292  mov     rcx, rdi
0x180034295  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x18003429a  xor     r8d, r8d
0x18003429d  mov     dl, 1
0x18003429f  lea     rcx, [rbp+60h+var_88]
0x1800342a3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800342a8  jmp     loc_18003405E
0x1800342ad  call    memset_0
0x1800342b2  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x1800342b7  lea     rcx, [rbp+60h+var_60]
0x1800342bb  mov     qword ptr [rsp+160h+var_120], rcx
0x1800342c0  lea     rcx, [rbp+60h+var_20]
0x1800342c4  mov     qword ptr [rsp+160h+var_120+8], rcx
0x1800342c9  mov     r9b, 5Fh ; '_'
0x1800342cc  mov     edx, eax
0x1800342ce  lea     rcx, [rsp+160h+var_120]
0x1800342d3  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800342d8  lea     rax, WPP_GLOBAL_Control
0x1800342df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342e6  cmp     rcx, rax
0x1800342e9  jz      loc_1800343E3
0x1800342ef  test    byte ptr [rcx+1Ch], 1
0x1800342f3  jz      loc_1800343E3
0x1800342f9  cmp     byte ptr [rcx+19h], 2
0x1800342fd  jb      loc_1800343E3
0x180034303  lea     rax, [rbp+60h+var_88]
0x180034307  cmp     [rbp+60h+var_70], 8
0x18003430c  cmovnb  rax, qword ptr [rbp+60h+var_88]
0x180034311  mov     edx, 77h ; 'w'
0x180034316  mov     [rsp+160h+var_138], rax
0x18003431b  mov     eax, [rsp+160h+var_130]
0x18003431f  mov     dword ptr [rsp+160h+var_140], eax
0x180034323  lea     r9, [rbp+60h+var_60]
  ... truncated ...
```

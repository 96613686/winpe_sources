# FileSystem::ElementaryFile::WriteDataObjectToDisk(DataObject::type const &)

- ea: `0x18003365c`
- end: `0x180033e0c`
- name: `?WriteDataObjectToDisk@ElementaryFile@FileSystem@@AEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEBUtype@DataObject@@@Z`
- size: `1968`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180032860`

## callees

- `0x180007a64`
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
- `0x18001a8dc`
- `0x18001e778`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x1800260e8`
- `0x1800261bc`
- `0x180028de0`
- `0x180029b84`
- `0x18002aee8`
- `0x18002efe4`
- `0x18002fae4`
- `0x180030254`
- `0x1800322b4`
- `0x18003365c`
- `0x180034b54`
- `0x18003853c`
- `0x180039eac`
- `0x18003aeb0`
- `0x18003af6c`
- `0x18003b014`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180033c91`
- `ktmw32!CommitTransaction` at `0x180033c91`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FileSystem::ElementaryFile::WriteDataObjectToDisk(__int64 a1, __int64 a2, int *a3)
{
  __int64 FilesystemTransaction; // rax
  __int64 v7; // rsi
  _DWORD *v8; // rax
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  char v13; // al
  int v14; // r8d
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
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
  char *v35; // rdx
  unsigned int v36; // eax
  __int64 v37; // r9
  __int64 v38; // r8
  int v39; // r8d
  unsigned int v40; // eax
  __int64 v41; // r9
  __int64 v42; // r8
  int v43; // r8d
  WCHAR *v44; // rax
  BOOL v45; // eax
  __int64 winerror_if; // rax
  unsigned int v47; // eax
  __int64 v48; // r9
  __int64 v49; // r8
  unsigned int v50; // eax
  __int64 v51; // r9
  __int64 v52; // r8
  char v54; // [rsp+30h] [rbp-D0h] BYREF
  int v55; // [rsp+38h] [rbp-C8h] BYREF
  int v56; // [rsp+3Ch] [rbp-C4h]
  _BYTE *v57; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v58; // [rsp+48h] [rbp-B8h]
  unsigned int v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+54h] [rbp-ACh]
  HANDLE TransactionHandle; // [rsp+58h] [rbp-A8h] BYREF
  int *v62; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE *p_TransactionHandle; // [rsp+68h] [rbp-98h]
  HANDLE v64; // [rsp+80h] [rbp-80h] BYREF
  int v65; // [rsp+88h] [rbp-78h]
  _BYTE *v66; // [rsp+90h] [rbp-70h] BYREF
  __int16 v67; // [rsp+98h] [rbp-68h]
  _BYTE v68[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v69[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v70[40]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v71[12]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v72; // [rsp+120h] [rbp+20h]
  _BYTE v73[48]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v74[64]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v75[8]; // [rsp+1A0h] [rbp+A0h] BYREF

  v57 = (_BYTE *)a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v65 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v55);
  v54 = 1;
  lambda_80756bb9bab88cf6ac7c5521679b074e_::_lambda_80756bb9bab88cf6ac7c5521679b074e_(
    (unsigned int)v70,
    (unsigned int)&v54,
    a1,
    (_DWORD)a3,
    a2,
    (__int64)&v55);
  lambda_27b87a78ee0367e5c5e618af4906b9fe_::operator()(v70);
  v54 = 0;
  v66 = v70;
  v67 = 258;
  TransactionHandle = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v73);
  v62 = &v55;
  p_TransactionHandle = &TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v62,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v73);
  v56 = 3;
  if ( v55 )
  {
    memset_0(v74, 0, sizeof(v74));
    v50 = ReportIndentTracker::Indent();
    v57 = v74;
    v58 = v75;
    LOBYTE(v51) = 95;
    ReportIndentTracker::Format(&v57, v50, v52, v51);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v74,
        v55);
    }
    goto LABEL_58;
  }
  v64 = TransactionHandle;
  v7 = a1 + 136;
  v8 = FileSystem::DiskOperations::CreateDirectoryOnDisk(&v62, (const WCHAR *)v7, &v64);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v55, v8);
  v56 = 3;
  if ( !v55 )
    goto LABEL_5;
  if ( v55 != 183 )
  {
    if ( v55 == 112 )
    {
      memset_0(v74, 0, sizeof(v74));
      v31 = ReportIndentTracker::Indent();
      v57 = v74;
      v58 = v75;
      LOBYTE(v32) = 95;
      ReportIndentTracker::Format(&v57, v31, v33, v32);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *(_QWORD *)(v7 + 24) >= 8u )
          v7 = *(_QWORD *)v7;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, v34, (unsigned int)v74, v7);
      }
      v35 = &byte_180075BF0;
      goto LABEL_59;
    }
    memset_0(v74, 0, sizeof(v74));
    v36 = ReportIndentTracker::Indent();
    v57 = v74;
    v58 = v75;
    LOBYTE(v37) = 95;
    ReportIndentTracker::Format(&v57, v36, v38, v37);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *(_QWORD *)(v7 + 24) >= 8u )
        v7 = *(_QWORD *)v7;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, v39, (unsigned int)v74, v55, v7);
    }
LABEL_58:
    v35 = &byte_180075E00;
LABEL_59:
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v35);
    goto LABEL_60;
  }
  LODWORD(v64) = 0;
  errorlib::scoped_error<winerror_error::tag>::initiate<long>(&v55, &v64);
LABEL_5:
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v69);
  errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(&v59);
  v9 = DataObject::encode((__int64)v74, a3);
  v62 = (int *)&v59;
  p_TransactionHandle = (HANDLE *)v69;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<unsigned char,wil::secure_allocator<unsigned char>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v62,
    v9);
  std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v74);
  v60 = 3;
  if ( (v59 >> 30) - 1 <= 2 )
  {
    memset_0(v74, 0, sizeof(v74));
    v10 = ReportIndentTracker::Indent();
    v62 = (int *)v74;
    p_TransactionHandle = (HANDLE *)v75;
    LOBYTE(v11) = 95;
    ReportIndentTracker::Format(&v62, v10, v12, v11);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = Asn1Tag::make((const struct Asn1Tag::type *)a3);
      WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, v14, (unsigned int)v74, v59, v13);
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
  }
  std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v68);
  v15 = Asn1Tag::encode(v74, a3);
  v62 = (int *)&v59;
  p_TransactionHandle = (HANDLE *)v68;
  std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<unsigned char,wil::secure_allocator<unsigned char>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v62,
    v15);
  std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v74);
  v60 = 3;
  if ( (v59 >> 30) - 1 <= 2 )
  {
    memset_0(v74, 0, sizeof(v74));
    v16 = ReportIndentTracker::Indent();
    v62 = (int *)v74;
    p_TransactionHandle = (HANDLE *)v75;
    LOBYTE(v17) = 95;
    ReportIndentTracker::Format(&v62, v16, v18, v17);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v74,
        v59);
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
  }
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v62, v68);
  v19 = FileSystem::HexToString(v74, &v62);
  v20 = std::operator+<unsigned short>(v73, v7);
  std::operator+<unsigned short>(v71, v20, v19);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(v73, v21, 0);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(v74, v22, 0);
  v62 = (int *)TransactionHandle;
  rangelib::make_raw_range<std::vector<unsigned char> const &>(&v57, v69);
  v23 = FileSystem::DiskOperations::WriteFileToDisk(&v64, v71, &v57, (void **)&v62);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v55, v23);
  v56 = 3;
  if ( v55 )
  {
    if ( v55 == 112 )
    {
      memset_0(v74, 0, sizeof(v74));
      v24 = ReportIndentTracker::Indent();
      v57 = v74;
      v58 = v75;
      LOBYTE(v25) = 95;
      ReportIndentTracker::Format(&v57, v24, v26, v25);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = v71;
        if ( v72 >= 8 )
          v28 = *(WCHAR **)v71;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, v27, (unsigned int)v74, (__int64)v28);
      }
      v29 = &byte_180075BF0;
      goto LABEL_26;
    }
    memset_0(v74, 0, sizeof(v74));
    v40 = ReportIndentTracker::Indent();
    v57 = v74;
    v58 = v75;
    LOBYTE(v41) = 95;
    ReportIndentTracker::Format(&v57, v40, v42, v41);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = v71;
      if ( v72 >= 8 )
        v44 = *(WCHAR **)v71;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v43, (unsigned int)v74, v55, (__int64)v44);
    }
  }
  else
  {
    v45 = CommitTransaction(TransactionHandle);
    winerror_if = make_winerror_if(&v62, !v45);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v55, winerror_if);
    v56 = 3;
    if ( !v55 )
      goto LABEL_27;
    memset_0(v74, 0, sizeof(v74));
    v47 = ReportIndentTracker::Indent();
    v57 = v74;
    v58 = v75;
    LOBYTE(v48) = 95;
    ReportIndentTracker::Format(&v57, v47, v49, v48);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v74,
        v55);
    }
  }
  v29 = &byte_180075E00;
LABEL_26:
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, v29);
LABEL_27:
  LOBYTE(v30) = 1;
  std::wstring::_Tidy(v71, v30, 0);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v68);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v59);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v69);
LABEL_60:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TransactionHandle);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_27b87a78ee0367e5c5e618af4906b9fe_____::operator()(&v66);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v55);
  return a2;
}

```

## disassembly

```asm
0x18003365c  push    rbp
0x18003365e  push    rbx
0x18003365f  push    rsi
0x180033660  push    rdi
0x180033661  push    r12
0x180033663  push    r14
0x180033665  push    r15
0x180033667  lea     rbp, [rsp-0B0h]
0x18003366f  sub     rsp, 1B0h
0x180033676  mov     rax, cs:__security_cookie
0x18003367d  xor     rax, rsp
0x180033680  mov     [rbp+0E0h+var_40], rax
0x180033687  mov     rbx, r8
0x18003368a  mov     rdi, rdx
0x18003368d  mov     rsi, rcx
0x180033690  mov     qword ptr [rsp+1E0h+var_1A0], rdx
0x180033695  mov     r12d, 1
0x18003369b  mov     [rbp+0E0h+var_158], r12d
0x18003369f  mov     rcx, rdx
0x1800336a2  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x1800336a7  nop
0x1800336a8  mov     [rbp+0E0h+var_158], r12d
0x1800336ac  lea     rcx, [rsp+1E0h+var_1A8]
0x1800336b1  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x1800336b6  nop
0x1800336b7  mov     [rsp+1E0h+var_1B0], r12b
0x1800336bc  lea     rax, [rsp+1E0h+var_1A8]
0x1800336c1  mov     [rsp+1E0h+var_1B8], rax
0x1800336c6  mov     [rsp+1E0h+var_1C0], rdi
0x1800336cb  mov     r9, rbx
0x1800336ce  mov     r8, rsi
0x1800336d1  lea     rdx, [rsp+1E0h+var_1B0]
0x1800336d6  lea     rcx, [rbp+0E0h+var_100]
0x1800336da  call    _lambda_80756bb9bab88cf6ac7c5521679b074e____lambda_80756bb9bab88cf6ac7c5521679b074e_
0x1800336df  lea     rcx, [rbp+0E0h+var_100]
0x1800336e3  call    _lambda_27b87a78ee0367e5c5e618af4906b9fe___operator__
0x1800336e8  xor     r14d, r14d
0x1800336eb  mov     [rsp+1E0h+var_1B0], r14b
0x1800336f0  lea     rax, [rbp+0E0h+var_100]
0x1800336f4  mov     [rbp+0E0h+var_150], rax
0x1800336f8  mov     [rbp+0E0h+var_148], 102h
0x1800336fe  mov     [rsp+1E0h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x180033707  lea     rcx, [rbp+0E0h+var_B0]
0x18003370b  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x180033710  lea     rcx, [rsp+1E0h+var_1A8]
0x180033715  mov     qword ptr [rsp+1E0h+var_180], rcx
0x18003371a  lea     rcx, [rsp+1E0h+TransactionHandle]
0x18003371f  mov     qword ptr [rsp+1E0h+var_180+8], rcx
0x180033724  mov     rdx, rax
0x180033727  lea     rcx, [rsp+1E0h+var_180]
0x18003372c  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180033731  lea     rcx, [rbp+0E0h+var_B0]
0x180033735  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x18003373a  lea     r15d, [r12+2]
0x18003373f  mov     [rsp+1E0h+var_1A4], r15d
0x180033744  cmp     [rsp+1E0h+var_1A8], r14d
0x180033749  jnz     loc_180033D40
0x18003374f  mov     rax, [rsp+1E0h+TransactionHandle]
0x180033754  mov     [rbp+0E0h+var_160], rax
0x180033758  add     rsi, 88h
0x18003375f  lea     r8, [rbp+0E0h+var_160]
0x180033763  mov     rdx, rsi
0x180033766  lea     rcx, [rsp+1E0h+var_180]
0x18003376b  call    ?CreateDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::CreateDirectoryOnDisk(std::wstring const &,void * const &)
0x180033770  mov     rdx, rax
0x180033773  lea     rcx, [rsp+1E0h+var_1A8]
0x180033778  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x18003377d  mov     [rsp+1E0h+var_1A4], r15d
0x180033782  mov     eax, [rsp+1E0h+var_1A8]
0x180033786  test    eax, eax
0x180033788  jz      short loc_1800337A7
0x18003378a  cmp     eax, 0B7h
0x18003378f  jnz     loc_180033AF8
0x180033795  mov     dword ptr [rbp+0E0h+var_160], r14d
0x180033799  lea     rdx, [rbp+0E0h+var_160]
0x18003379d  lea     rcx, [rsp+1E0h+var_1A8]
0x1800337a2  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x1800337a7  lea     rcx, [rbp+0E0h+var_120]
0x1800337ab  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x1800337b0  nop
0x1800337b1  lea     rcx, [rsp+1E0h+var_190]
0x1800337b6  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x1800337bb  nop
0x1800337bc  mov     rdx, rbx
0x1800337bf  lea     rcx, [rbp+0E0h+var_80]
0x1800337c3  call    ?encode@DataObject@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z; DataObject::encode(DataObject::type const &)
0x1800337c8  nop
0x1800337c9  lea     rcx, [rsp+1E0h+var_190]
0x1800337ce  mov     qword ptr [rsp+1E0h+var_180], rcx
0x1800337d3  lea     rcx, [rbp+0E0h+var_120]
0x1800337d7  mov     qword ptr [rsp+1E0h+var_180+8], rcx
0x1800337dc  mov     rdx, rax
0x1800337df  lea     rcx, [rsp+1E0h+var_180]
0x1800337e4  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@3@U453@U453@U453@U453@U453@U453@U453@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAV?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x1800337e9  nop
0x1800337ea  lea     rcx, [rbp+0E0h+var_80]
0x1800337ee  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x1800337f3  mov     [rsp+1E0h+var_18C], r15d
0x1800337f8  mov     eax, [rsp+1E0h+var_190]
0x1800337fc  shr     eax, 1Eh
0x1800337ff  sub     eax, r12d
0x180033802  mov     r14d, 40h ; '@'
0x180033808  lea     r15, WPP_GLOBAL_Control
0x18003380f  cmp     eax, 2
0x180033812  ja      loc_1800338A2
0x180033818  mov     r8d, r14d; Size
0x18003381b  xor     edx, edx; Val
0x18003381d  lea     rcx, [rbp+0E0h+var_80]; void *
0x180033821  call    memset_0
0x180033826  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003382b  lea     rcx, [rbp+0E0h+var_80]
0x18003382f  mov     qword ptr [rsp+1E0h+var_180], rcx
0x180033834  lea     rcx, [rbp+0E0h+var_40]
0x18003383b  mov     qword ptr [rsp+1E0h+var_180+8], rcx
0x180033840  mov     r9b, 5Fh ; '_'
0x180033843  mov     edx, eax
0x180033845  lea     rcx, [rsp+1E0h+var_180]
0x18003384a  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003384f  mov     rax, cs:WPP_GLOBAL_Control
0x180033856  cmp     rax, r15
0x180033859  jz      short loc_180033893
0x18003385b  test    [rax+1Ch], r12b
0x18003385f  jz      short loc_180033893
0x180033861  cmp     byte ptr [rax+19h], 2
0x180033865  jb      short loc_180033893
0x180033867  mov     rcx, rbx; struct Asn1Tag::type *
0x18003386a  call    ?make@Asn1Tag@@SAKAEBUtype@1@@Z; Asn1Tag::make(Asn1Tag::type const &)
0x18003386f  lea     edx, [r14+15h]
0x180033873  mov     dword ptr [rsp+1E0h+var_1B8], eax
0x180033877  mov     eax, [rsp+1E0h+var_190]
0x18003387b  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18003387f  lea     r9, [rbp+0E0h+var_80]
0x180033883  mov     rcx, cs:WPP_GLOBAL_Control
0x18003388a  mov     rcx, [rcx+10h]
0x18003388e  call    WPP_SF_sdD
0x180033893  lea     rdx, byte_180075E00
0x18003389a  mov     rcx, rdi
0x18003389d  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x1800338a2  lea     rcx, [rbp+0E0h+var_140]
0x1800338a6  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x1800338ab  nop
0x1800338ac  mov     rdx, rbx
0x1800338af  lea     rcx, [rbp+0E0h+var_80]
0x1800338b3  call    ?encode@Asn1Tag@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z; Asn1Tag::encode(Asn1Tag::type const &)
0x1800338b8  nop
0x1800338b9  lea     rcx, [rsp+1E0h+var_190]
0x1800338be  mov     qword ptr [rsp+1E0h+var_180], rcx
0x1800338c3  lea     rcx, [rbp+0E0h+var_140]
0x1800338c7  mov     qword ptr [rsp+1E0h+var_180+8], rcx
0x1800338cc  mov     rdx, rax
0x1800338cf  lea     rcx, [rsp+1E0h+var_180]
0x1800338d4  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@3@U453@U453@U453@U453@U453@U453@U453@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAV?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x1800338d9  nop
0x1800338da  lea     rcx, [rbp+0E0h+var_80]
0x1800338de  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x1800338e3  mov     [rsp+1E0h+var_18C], 3
0x1800338eb  mov     eax, [rsp+1E0h+var_190]
0x1800338ef  shr     eax, 1Eh
0x1800338f2  sub     eax, r12d
0x1800338f5  cmp     eax, 2
0x1800338f8  ja      short loc_180033979
0x1800338fa  mov     r8, r14; Size
0x1800338fd  xor     edx, edx; Val
0x1800338ff  lea     rcx, [rbp+0E0h+var_80]; void *
0x180033903  call    memset_0
0x180033908  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003390d  lea     rcx, [rbp+0E0h+var_80]
0x180033911  mov     qword ptr [rsp+1E0h+var_180], rcx
0x180033916  lea     rcx, [rbp+0E0h+var_40]
0x18003391d  mov     qword ptr [rsp+1E0h+var_180+8], rcx
0x180033922  mov     r9b, 5Fh ; '_'
0x180033925  mov     edx, eax
0x180033927  lea     rcx, [rsp+1E0h+var_180]
0x18003392c  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180033931  mov     rcx, cs:WPP_GLOBAL_Control
0x180033938  cmp     rcx, r15
0x18003393b  jz      short loc_18003396A
0x18003393d  test    [rcx+1Ch], r12b
0x180033941  jz      short loc_18003396A
0x180033943  cmp     byte ptr [rcx+19h], 2
0x180033947  jb      short loc_18003396A
0x180033949  mov     edx, 56h ; 'V'
0x18003394e  mov     eax, [rsp+1E0h+var_190]
0x180033952  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180033956  lea     r9, [rbp+0E0h+var_80]
0x18003395a  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180033961  mov     rcx, [rcx+10h]
0x180033965  call    WPP_SF_sd
0x18003396a  lea     rdx, byte_180075E00
0x180033971  mov     rcx, rdi
0x180033974  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180033979  lea     rdx, [rbp+0E0h+var_140]
0x18003397d  lea     rcx, [rsp+1E0h+var_180]
0x180033982  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x180033987  movaps  xmm0, [rsp+1E0h+var_180]
0x18003398c  movdqa  [rsp+1E0h+var_180], xmm0
0x180033992  lea     rdx, [rsp+1E0h+var_180]
0x180033997  lea     rcx, [rbp+0E0h+var_80]
0x18003399b  call    ?HexToString@FileSystem@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@@Z; FileSystem::HexToString(rangelib::range<uchar const *>)
0x1800339a0  mov     rbx, rax
0x1800339a3  mov     rdx, rsi
0x1800339a6  lea     rcx, [rbp+0E0h+var_B0]
0x1800339aa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x1800339af  nop
0x1800339b0  mov     r8, rbx
0x1800339b3  mov     rdx, rax
0x1800339b6  lea     rcx, [rbp+0E0h+var_D8]
0x1800339ba  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800339bf  nop
0x1800339c0  xor     r8d, r8d
0x1800339c3  mov     dl, r12b
0x1800339c6  lea     rcx, [rbp+0E0h+var_B0]
0x1800339ca  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800339cf  nop
0x1800339d0  xor     r8d, r8d
0x1800339d3  mov     dl, r12b
0x1800339d6  lea     rcx, [rbp+0E0h+var_80]
0x1800339da  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800339df  mov     rax, [rsp+1E0h+TransactionHandle]
0x1800339e4  mov     qword ptr [rsp+1E0h+var_180], rax
0x1800339e9  lea     rdx, [rbp+0E0h+var_120]
0x1800339ed  lea     rcx, [rsp+1E0h+var_1A0]
0x1800339f2  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x1800339f7  movaps  xmm0, [rsp+1E0h+var_1A0]
0x1800339fc  movdqa  [rsp+1E0h+var_1A0], xmm0
0x180033a02  lea     r9, [rsp+1E0h+var_180]
0x180033a07  lea     r8, [rsp+1E0h+var_1A0]
0x180033a0c  lea     rdx, [rbp+0E0h+var_D8]
0x180033a10  lea     rcx, [rbp+0E0h+var_160]
0x180033a14  call    ?WriteFileToDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@AEBQEAX@Z; FileSystem::DiskOperations::WriteFileToDisk(std::wstring const &,rangelib::range<uchar const *>,void * const &)
0x180033a19  mov     rdx, rax
0x180033a1c  lea     rcx, [rsp+1E0h+var_1A8]
0x180033a21  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180033a26  mov     ebx, 3
0x180033a2b  mov     [rsp+1E0h+var_1A4], ebx
0x180033a2f  mov     eax, [rsp+1E0h+var_1A8]
0x180033a33  test    eax, eax
0x180033a35  jz      loc_180033C8C
0x180033a3b  mov     r8, r14; Size
0x180033a3e  xor     edx, edx; Val
0x180033a40  lea     rcx, [rbp+0E0h+var_80]; void *
0x180033a44  cmp     eax, 70h ; 'p'
0x180033a47  jnz     loc_180033C08
0x180033a4d  call    memset_0
0x180033a52  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180033a57  lea     rcx, [rbp+0E0h+var_80]
0x180033a5b  mov     qword ptr [rsp+1E0h+var_1A0], rcx
0x180033a60  lea     rcx, [rbp+0E0h+var_40]
0x180033a67  mov     qword ptr [rsp+1E0h+var_1A0+8], rcx
0x180033a6c  mov     r9b, 5Fh ; '_'
0x180033a6f  mov     edx, eax
0x180033a71  lea     rcx, [rsp+1E0h+var_1A0]
0x180033a76  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180033a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033a82  cmp     rcx, r15
0x180033a85  jz      short loc_180033AB6
0x180033a87  test    [rcx+1Ch], r12b
0x180033a8b  jz      short loc_180033AB6
0x180033a8d  cmp     byte ptr [rcx+19h], 2
0x180033a91  jb      short loc_180033AB6
0x180033a93  lea     rax, [rbp+0E0h+var_D8]
0x180033a97  cmp     [rbp+0E0h+var_C0], 8
0x180033a9c  cmovnb  rax, qword ptr [rbp+0E0h+var_D8]
0x180033aa1  lea     edx, [rbx+54h]
0x180033aa4  mov     [rsp+1E0h+var_1C0], rax
0x180033aa9  lea     r9, [rbp+0E0h+var_80]
0x180033aad  mov     rcx, [rcx+10h]
0x180033ab1  call    WPP_SF_sS
0x180033ab6  lea     rdx, byte_180075BF0
0x180033abd  mov     rcx, rdi
0x180033ac0  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180033ac5  xor     r8d, r8d
0x180033ac8  mov     dl, r12b
0x180033acb  lea     rcx, [rbp+0E0h+var_D8]
0x180033acf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180033ad4  nop
0x180033ad5  lea     rcx, [rbp+0E0h+var_140]
0x180033ad9  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180033ade  nop
0x180033adf  lea     rcx, [rsp+1E0h+var_190]
0x180033ae4  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180033ae9  nop
0x180033aea  lea     rcx, [rbp+0E0h+var_120]
0x180033aee  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180033af3  jmp     loc_180033DC8
0x180033af8  xor     edx, edx; Val
0x180033afa  lea     r8d, [rdx+40h]; Size
0x180033afe  lea     rcx, [rbp+0E0h+var_80]; void *
0x180033b02  cmp     eax, 70h ; 'p'
0x180033b05  jnz     short loc_180033B81
0x180033b07  call    memset_0
0x180033b0c  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180033b11  lea     rcx, [rbp+0E0h+var_80]
0x180033b15  mov     qword ptr [rsp+1E0h+var_1A0], rcx
0x180033b1a  lea     rcx, [rbp+0E0h+var_40]
0x180033b21  mov     qword ptr [rsp+1E0h+var_1A0+8], rcx
0x180033b26  mov     r9b, 5Fh ; '_'
0x180033b29  mov     edx, eax
0x180033b2b  lea     rcx, [rsp+1E0h+var_1A0]
0x180033b30  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
  ... truncated ...
```

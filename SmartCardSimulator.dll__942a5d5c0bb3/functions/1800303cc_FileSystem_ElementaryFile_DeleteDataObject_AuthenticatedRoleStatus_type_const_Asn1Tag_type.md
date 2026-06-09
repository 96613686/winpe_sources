# FileSystem::ElementaryFile::DeleteDataObject(AuthenticatedRoleStatus::type const &,Asn1Tag::type)

- ea: `0x1800303cc`
- end: `0x1800308c2`
- name: `?DeleteDataObject@ElementaryFile@FileSystem@@QEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEBUtype@AuthenticatedRoleStatus@@U5Asn1Tag@@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(FileSystem::ElementaryFile *this)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c34c`

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
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x1800260e8`
- `0x1800261bc`
- `0x180028de0`
- `0x180029b84`
- `0x18002b2f4`
- `0x18002f068`
- `0x18002f6f4`
- `0x180030254`
- `0x1800303cc`
- `0x1800322b4`
- `0x18003853c`
- `0x180038e20`
- `0x18003aeb0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `KERNEL32!DeleteFileTransactedW` at `0x18003064b`
- `KERNEL32!DeleteFileTransactedW` at `0x18003064b`
- `ktmw32!CommitTransaction` at `0x180030688`
- `ktmw32!CommitTransaction` at `0x180030688`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall FileSystem::ElementaryFile::DeleteDataObject(
        FileSystem::ElementaryFile *this,
        __int64 a2,
        const struct AuthenticatedRoleStatus::type *a3,
        int a4)
{
  __int64 FilesystemTransaction; // rax
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  BOOL v17; // eax
  __int64 winerror_if; // rax
  BOOL v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // r9
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // r8
  int v28; // r8d
  LPCWSTR *v29; // rax
  unsigned int v30; // eax
  __int64 v31; // r9
  __int64 v32; // r8
  char v34; // [rsp+30h] [rbp-D0h] BYREF
  int v35; // [rsp+38h] [rbp-C8h] BYREF
  int v36; // [rsp+3Ch] [rbp-C4h]
  int *v37; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE *p_hTransaction; // [rsp+48h] [rbp-B8h]
  _DWORD v39[2]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hTransaction; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v41; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+80h] [rbp-80h]
  _BYTE *v44; // [rsp+88h] [rbp-78h] BYREF
  __int16 v45; // [rsp+90h] [rbp-70h]
  _BYTE v46[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v47[40]; // [rsp+B8h] [rbp-48h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v49; // [rsp+F8h] [rbp-8h]
  _BYTE v50[40]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v51[64]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v52[6]; // [rsp+170h] [rbp+70h] BYREF
  int v53; // [rsp+1C8h] [rbp+C8h] BYREF

  v53 = a4;
  v41 = (_BYTE *)a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v43 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v35);
  v34 = 1;
  lambda_80756bb9bab88cf6ac7c5521679b074e_::_lambda_80756bb9bab88cf6ac7c5521679b074e_(
    (unsigned int)v47,
    (unsigned int)&v34,
    (_DWORD)this,
    (unsigned int)&v53,
    (__int64)a3,
    a2);
  lambda_3687a1fdef2f830cc28fffff45184d0a_::operator()(v47);
  v34 = 0;
  v44 = v47;
  v45 = 258;
  LODWORD(v37) = 14;
  if ( FileSystem::ElementaryFile::AccessCheck(this, a3, (const enum CommandField::type *)&v37) )
  {
    hTransaction = (HANDLE)-1LL;
    FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v50);
    v37 = &v35;
    p_hTransaction = &hTransaction;
    std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      &v37,
      FilesystemTransaction);
    std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v50);
    v36 = 3;
    if ( v35 )
    {
      memset_0(v51, 0, sizeof(v51));
      v30 = ReportIndentTracker::Indent();
      v41 = v51;
      v42 = v52;
      LOBYTE(v31) = 95;
      ReportIndentTracker::Format(&v41, v30, v32, v31);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
          (unsigned int)v51,
          v35);
      }
      errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
      goto LABEL_32;
    }
    std::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>::_Vector_val<unsigned char,wil::secure_allocator<unsigned char>>(v46);
    errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(v39);
    v8 = Asn1Tag::encode(v51, &v53);
    v37 = v39;
    p_hTransaction = (HANDLE *)v46;
    std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<unsigned char,wil::secure_allocator<unsigned char>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
      &v37,
      v8);
    std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<unsigned char const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(v51);
    v39[1] = 3;
    if ( (unsigned int)((v39[0] >> 30) - 1) <= 2 )
    {
      memset_0(v51, 0, sizeof(v51));
      v9 = ReportIndentTracker::Indent();
      v37 = (int *)v51;
      p_hTransaction = (HANDLE *)v52;
      LOBYTE(v10) = 95;
      ReportIndentTracker::Format(&v37, v9, v11, v10);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
          (unsigned int)v51,
          v39[0]);
      }
      errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
    }
    rangelib::make_raw_range<std::vector<unsigned char> const &>(&v37, v46);
    v12 = FileSystem::HexToString(v51, &v37);
    v13 = std::operator+<unsigned short>(v50, (char *)this + 136);
    std::operator+<unsigned short>(lpFileName, v13, v12);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v50, v14, 0);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v51, v15, 0);
    v16 = (const WCHAR *)lpFileName;
    if ( v49 >= 8 )
      v16 = lpFileName[0];
    v17 = DeleteFileTransactedW(v16, hTransaction);
    winerror_if = make_winerror_if(&v37, !v17);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v35, winerror_if);
    v36 = 3;
    if ( v35 )
    {
      memset_0(v51, 0, sizeof(v51));
      v25 = ReportIndentTracker::Indent();
      v41 = v51;
      v42 = v52;
      LOBYTE(v26) = 95;
      ReportIndentTracker::Format(&v41, v25, v27, v26);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = lpFileName;
        if ( v49 >= 8 )
          v29 = (LPCWSTR *)lpFileName[0];
        WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v28, (unsigned int)v51, v35, (__int64)v29);
      }
    }
    else
    {
      v19 = CommitTransaction(hTransaction);
      v20 = make_winerror_if(&v37, !v19);
      errorlib::scoped_error<ntstatus_error::tag>::operator=(&v35, v20);
      v36 = 3;
      if ( !v35 )
      {
        std::_Tree<std::_Tmap_traits<Asn1Tag::type,DataObject::type,std::less<Asn1Tag::type>,std::allocator<std::pair<Asn1Tag::type const,DataObject::type>>,0>>::erase(
          this,
          &v53);
LABEL_15:
        LOBYTE(v21) = 1;
        std::wstring::_Tidy(lpFileName, v21, 0);
        errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v39);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v46);
LABEL_32:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hTransaction);
        goto LABEL_33;
      }
      memset_0(v51, 0, sizeof(v51));
      v22 = ReportIndentTracker::Indent();
      v41 = v51;
      v42 = v52;
      LOBYTE(v23) = 95;
      ReportIndentTracker::Format(&v41, v22, v24, v23);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
          (unsigned int)v51,
          v35);
      }
    }
    errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
    goto LABEL_15;
  }
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_1800759B0);
LABEL_33:
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_3687a1fdef2f830cc28fffff45184d0a_____::operator()(&v44);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v35);
  return a2;
}

```

## disassembly

```asm
0x1800303cc  mov     [rsp-8+arg_10], rbx
0x1800303d1  mov     [rsp-8+arg_18], r9d
0x1800303d6  push    rbp
0x1800303d7  push    rsi
0x1800303d8  push    rdi
0x1800303d9  push    r14
0x1800303db  push    r15
0x1800303dd  lea     rbp, [rsp-80h]
0x1800303e2  sub     rsp, 180h
0x1800303e9  mov     rax, cs:__security_cookie
0x1800303f0  xor     rax, rsp
0x1800303f3  mov     [rbp+0A0h+var_30], rax
0x1800303f7  mov     rbx, r8
0x1800303fa  mov     rdi, rdx
0x1800303fd  mov     r15, rcx
0x180030400  mov     [rsp+1A0h+var_130], rdx
0x180030405  mov     [rbp+0A0h+var_120], 1
0x18003040c  mov     rcx, rdx
0x18003040f  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180030414  nop
0x180030415  mov     [rbp+0A0h+var_120], 1
0x18003041c  lea     rcx, [rsp+1A0h+var_168]
0x180030421  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030426  nop
0x180030427  mov     [rsp+1A0h+var_170], 1
0x18003042c  mov     [rsp+1A0h+var_178], rdi
0x180030431  mov     [rsp+1A0h+var_180], rbx
0x180030436  lea     r9, [rbp+0A0h+arg_18]
0x18003043d  mov     r8, r15
0x180030440  lea     rdx, [rsp+1A0h+var_170]
0x180030445  lea     rcx, [rbp+0A0h+var_E8]
0x180030449  call    _lambda_80756bb9bab88cf6ac7c5521679b074e____lambda_80756bb9bab88cf6ac7c5521679b074e_
0x18003044e  lea     rcx, [rbp+0A0h+var_E8]
0x180030452  call    _lambda_3687a1fdef2f830cc28fffff45184d0a___operator__
0x180030457  mov     [rsp+1A0h+var_170], 0
0x18003045c  lea     rax, [rbp+0A0h+var_E8]
0x180030460  mov     [rbp+0A0h+var_118], rax
0x180030464  mov     [rbp+0A0h+var_110], 102h
0x18003046a  mov     dword ptr [rsp+1A0h+var_160], 0Eh
0x180030472  lea     r8, [rsp+1A0h+var_160]; enum CommandField::type *
0x180030477  mov     rdx, rbx; struct AuthenticatedRoleStatus::type *
0x18003047a  mov     rcx, r15; this
0x18003047d  call    ?AccessCheck@ElementaryFile@FileSystem@@QEBA_NAEBUtype@AuthenticatedRoleStatus@@AEBW43CommandField@@@Z; FileSystem::ElementaryFile::AccessCheck(AuthenticatedRoleStatus::type const &,CommandField::type const &)
0x180030482  test    al, al
0x180030484  jnz     short loc_18003049A
0x180030486  lea     rdx, byte_1800759B0
0x18003048d  mov     rcx, rdi
0x180030490  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180030495  jmp     loc_180030887
0x18003049a  mov     [rsp+1A0h+hTransaction], 0FFFFFFFFFFFFFFFFh
0x1800304a3  lea     rcx, [rbp+0A0h+var_98]
0x1800304a7  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x1800304ac  lea     rcx, [rsp+1A0h+var_168]
0x1800304b1  mov     qword ptr [rsp+1A0h+var_160], rcx
0x1800304b6  lea     rcx, [rsp+1A0h+hTransaction]
0x1800304bb  mov     qword ptr [rsp+1A0h+var_160+8], rcx
0x1800304c0  mov     rdx, rax
0x1800304c3  lea     rcx, [rsp+1A0h+var_160]
0x1800304c8  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x1800304cd  lea     rcx, [rbp+0A0h+var_98]
0x1800304d1  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x1800304d6  mov     ebx, 3
0x1800304db  mov     [rsp+1A0h+var_164], ebx
0x1800304df  cmp     [rsp+1A0h+var_168], 0
0x1800304e4  jnz     loc_1800307F7
0x1800304ea  lea     rcx, [rbp+0A0h+var_108]
0x1800304ee  call    ??0?$_Vector_val@EU?$secure_allocator@E@wil@@@std@@QEAA@U?$secure_allocator@E@wil@@@Z; std::_Vector_val<uchar,wil::secure_allocator<uchar>>::_Vector_val<uchar,wil::secure_allocator<uchar>>(wil::secure_allocator<uchar>)
0x1800304f3  nop
0x1800304f4  lea     rcx, [rsp+1A0h+var_140]
0x1800304f9  call    ??0?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<ntstatus_error::tag>::scoped_error<ntstatus_error::tag>(void)
0x1800304fe  nop
0x1800304ff  lea     rdx, [rbp+0A0h+arg_18]
0x180030506  lea     rcx, [rbp+0A0h+var_70]
0x18003050a  call    ?encode@Asn1Tag@@SA?AV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBUtype@1@@Z; Asn1Tag::encode(Asn1Tag::type const &)
0x18003050f  nop
0x180030510  lea     rcx, [rsp+1A0h+var_140]
0x180030515  mov     qword ptr [rsp+1A0h+var_160], rcx
0x18003051a  lea     rcx, [rbp+0A0h+var_108]
0x18003051e  mov     qword ptr [rsp+1A0h+var_160+8], rcx
0x180030523  mov     rdx, rax
0x180030526  lea     rcx, [rsp+1A0h+var_160]
0x18003052b  call    ??$?4V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@3@U453@U453@U453@U453@U453@U453@U453@@?$tuple@AEAV?$scoped_error@Utag@ntstatus_error@@@errorlib@@AEAV?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@V?$vector@EU?$secure_allocator@E@wil@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@12@@Z; std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag> &,std::vector<uchar,wil::secure_allocator<uchar>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<ntstatus_error::tag>,std::vector<uchar,wil::secure_allocator<uchar>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180030530  nop
0x180030531  lea     rcx, [rbp+0A0h+var_70]
0x180030535  call    ??1?$_Cons_node@V?$scoped_error@Utag@ntstatus_error@@@errorlib@@U?$_Cons_node@Utype@?$DataObjectByteVector@U?$StaticTag1@$0IH@@detail@Asn1Tag@@@@U?$_Cons_node@V?$range@PEBE@rangelib@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>::~_Cons_node<errorlib::scoped_error<ntstatus_error::tag>,std::tr1::_Cons_node<DataObjectByteVector<Asn1Tag::detail::StaticTag1<135>>::type,std::tr1::_Cons_node<rangelib::range<uchar const *>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>>(void)
0x18003053a  mov     [rsp+1A0h+var_13C], ebx
0x18003053e  mov     eax, [rsp+1A0h+var_140]
0x180030542  shr     eax, 1Eh
0x180030545  dec     eax
0x180030547  lea     esi, [rbx+3Dh]
0x18003054a  lea     r14, WPP_GLOBAL_Control
0x180030551  cmp     eax, 2
0x180030554  ja      short loc_1800305D0
0x180030556  mov     r8d, esi; Size
0x180030559  xor     edx, edx; Val
0x18003055b  lea     rcx, [rbp+0A0h+var_70]; void *
0x18003055f  call    memset_0
0x180030564  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030569  lea     rcx, [rbp+0A0h+var_70]
0x18003056d  mov     qword ptr [rsp+1A0h+var_160], rcx
0x180030572  lea     rcx, [rbp+0A0h+var_30]
0x180030576  mov     qword ptr [rsp+1A0h+var_160+8], rcx
0x18003057b  mov     r9b, 5Fh ; '_'
0x18003057e  mov     edx, eax
0x180030580  lea     rcx, [rsp+1A0h+var_160]
0x180030585  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003058a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030591  cmp     rcx, r14
0x180030594  jz      short loc_1800305C1
0x180030596  test    byte ptr [rcx+1Ch], 1
0x18003059a  jz      short loc_1800305C1
0x18003059c  cmp     byte ptr [rcx+19h], 2
0x1800305a0  jb      short loc_1800305C1
0x1800305a2  lea     edx, [rbx+36h]
0x1800305a5  mov     eax, [rsp+1A0h+var_140]
0x1800305a9  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800305ad  lea     r9, [rbp+0A0h+var_70]
0x1800305b1  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x1800305b8  mov     rcx, [rcx+10h]
0x1800305bc  call    WPP_SF_sd
0x1800305c1  lea     rdx, byte_180075E00
0x1800305c8  mov     rcx, rdi
0x1800305cb  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x1800305d0  lea     rdx, [rbp+0A0h+var_108]
0x1800305d4  lea     rcx, [rsp+1A0h+var_160]
0x1800305d9  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x1800305de  movaps  xmm0, [rsp+1A0h+var_160]
0x1800305e3  movdqa  [rsp+1A0h+var_160], xmm0
0x1800305e9  lea     rdx, [rsp+1A0h+var_160]
0x1800305ee  lea     rcx, [rbp+0A0h+var_70]
0x1800305f2  call    ?HexToString@FileSystem@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@@Z; FileSystem::HexToString(rangelib::range<uchar const *>)
0x1800305f7  mov     rbx, rax
0x1800305fa  lea     rdx, [r15+88h]
0x180030601  lea     rcx, [rbp+0A0h+var_98]
0x180030605  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18003060a  nop
0x18003060b  mov     r8, rbx
0x18003060e  mov     rdx, rax
0x180030611  lea     rcx, [rbp+0A0h+lpFileName]
0x180030615  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18003061a  nop
0x18003061b  xor     r8d, r8d
0x18003061e  mov     dl, 1
0x180030620  lea     rcx, [rbp+0A0h+var_98]
0x180030624  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180030629  nop
0x18003062a  xor     r8d, r8d
0x18003062d  mov     dl, 1
0x18003062f  lea     rcx, [rbp+0A0h+var_70]
0x180030633  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180030638  lea     rcx, [rbp+0A0h+lpFileName]
0x18003063c  cmp     [rbp+0A0h+var_A8], 8
0x180030641  cmovnb  rcx, [rbp+0A0h+lpFileName]; lpFileName
0x180030646  mov     rdx, [rsp+1A0h+hTransaction]; hTransaction
0x18003064b  call    cs:__imp_DeleteFileTransactedW
0x180030651  xor     edx, edx
0x180030653  test    eax, eax
0x180030655  setz    dl
0x180030658  lea     rcx, [rsp+1A0h+var_160]
0x18003065d  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180030662  mov     rdx, rax
0x180030665  lea     rcx, [rsp+1A0h+var_168]
0x18003066a  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x18003066f  mov     ebx, 3
0x180030674  mov     [rsp+1A0h+var_164], ebx
0x180030678  cmp     [rsp+1A0h+var_168], 0
0x18003067d  jnz     loc_18003076A
0x180030683  mov     rcx, [rsp+1A0h+hTransaction]; TransactionHandle
0x180030688  call    cs:__imp_CommitTransaction
0x18003068e  xor     edx, edx
0x180030690  test    eax, eax
0x180030692  setz    dl
0x180030695  lea     rcx, [rsp+1A0h+var_160]
0x18003069a  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18003069f  mov     rdx, rax
0x1800306a2  lea     rcx, [rsp+1A0h+var_168]
0x1800306a7  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800306ac  mov     [rsp+1A0h+var_164], ebx
0x1800306b0  cmp     [rsp+1A0h+var_168], 0
0x1800306b5  jnz     short loc_1800306EF
0x1800306b7  lea     rdx, [rbp+0A0h+arg_18]
0x1800306be  mov     rcx, r15
0x1800306c1  call    ?erase@?$_Tree@V?$_Tmap_traits@Utype@Asn1Tag@@U1DataObject@@U?$less@Utype@Asn1Tag@@@std@@V?$allocator@U?$pair@$$CBUtype@Asn1Tag@@U1DataObject@@@std@@@5@$0A@@std@@@std@@QEAA_KAEBUtype@Asn1Tag@@@Z; std::_Tree<std::_Tmap_traits<Asn1Tag::type,DataObject::type,std::less<Asn1Tag::type>,std::allocator<std::pair<Asn1Tag::type const,DataObject::type>>,0>>::erase(Asn1Tag::type const &)
0x1800306c6  nop
0x1800306c7  xor     r8d, r8d
0x1800306ca  mov     dl, 1
0x1800306cc  lea     rcx, [rbp+0A0h+lpFileName]
0x1800306d0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800306d5  nop
0x1800306d6  lea     rcx, [rsp+1A0h+var_140]
0x1800306db  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800306e0  nop
0x1800306e1  lea     rcx, [rbp+0A0h+var_108]
0x1800306e5  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@IEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1800306ea  jmp     loc_18003087C
0x1800306ef  mov     r8, rsi; Size
0x1800306f2  xor     edx, edx; Val
0x1800306f4  lea     rcx, [rbp+0A0h+var_70]; void *
0x1800306f8  call    memset_0
0x1800306fd  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030702  lea     rcx, [rbp+0A0h+var_70]
0x180030706  mov     [rsp+1A0h+var_130], rcx
0x18003070b  lea     rcx, [rbp+0A0h+var_30]
0x18003070f  mov     [rsp+1A0h+var_128], rcx
0x180030714  mov     r9b, 5Fh ; '_'
0x180030717  mov     edx, eax
0x180030719  lea     rcx, [rsp+1A0h+var_130]
0x18003071e  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030723  mov     rcx, cs:WPP_GLOBAL_Control
0x18003072a  cmp     rcx, r14
0x18003072d  jz      loc_1800307E3
0x180030733  test    byte ptr [rcx+1Ch], 1
0x180030737  jz      loc_1800307E3
0x18003073d  cmp     byte ptr [rcx+19h], 2
0x180030741  jb      loc_1800307E3
0x180030747  mov     edx, 3Bh ; ';'
0x18003074c  mov     eax, [rsp+1A0h+var_168]
0x180030750  mov     dword ptr [rsp+1A0h+var_180], eax
0x180030754  lea     r9, [rbp+0A0h+var_70]
0x180030758  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x18003075f  mov     rcx, [rcx+10h]
0x180030763  call    WPP_SF_sd
0x180030768  jmp     short loc_1800307E3
0x18003076a  mov     r8, rsi; Size
0x18003076d  xor     edx, edx; Val
0x18003076f  lea     rcx, [rbp+0A0h+var_70]; void *
0x180030773  call    memset_0
0x180030778  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003077d  lea     rcx, [rbp+0A0h+var_70]
0x180030781  mov     [rsp+1A0h+var_130], rcx
0x180030786  lea     rcx, [rbp+0A0h+var_30]
0x18003078a  mov     [rsp+1A0h+var_128], rcx
0x18003078f  mov     r9b, 5Fh ; '_'
0x180030792  mov     edx, eax
0x180030794  lea     rcx, [rsp+1A0h+var_130]
0x180030799  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003079e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800307a5  cmp     rcx, r14
0x1800307a8  jz      short loc_1800307E3
0x1800307aa  test    byte ptr [rcx+1Ch], 1
0x1800307ae  jz      short loc_1800307E3
0x1800307b0  cmp     byte ptr [rcx+19h], 2
0x1800307b4  jb      short loc_1800307E3
0x1800307b6  lea     rax, [rbp+0A0h+lpFileName]
0x1800307ba  cmp     [rbp+0A0h+var_A8], 8
0x1800307bf  cmovnb  rax, [rbp+0A0h+lpFileName]
0x1800307c4  mov     edx, 3Ah ; ':'
0x1800307c9  mov     [rsp+1A0h+var_178], rax
0x1800307ce  mov     eax, [rsp+1A0h+var_168]
0x1800307d2  mov     dword ptr [rsp+1A0h+var_180], eax
0x1800307d6  lea     r9, [rbp+0A0h+var_70]
0x1800307da  mov     rcx, [rcx+10h]
0x1800307de  call    WPP_SF_sDS
0x1800307e3  lea     rdx, byte_180075E00
0x1800307ea  mov     rcx, rdi
0x1800307ed  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x1800307f2  jmp     loc_1800306C7
0x1800307f7  xor     edx, edx; Val
0x1800307f9  lea     r8d, [rdx+40h]; Size
0x1800307fd  lea     rcx, [rbp+0A0h+var_70]; void *
0x180030801  call    memset_0
0x180030806  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003080b  lea     rcx, [rbp+0A0h+var_70]
0x18003080f  mov     [rsp+1A0h+var_130], rcx
0x180030814  lea     rcx, [rbp+0A0h+var_30]
0x180030818  mov     [rsp+1A0h+var_128], rcx
0x18003081d  mov     r9b, 5Fh ; '_'
0x180030820  mov     edx, eax
0x180030822  lea     rcx, [rsp+1A0h+var_130]
0x180030827  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003082c  lea     r14, WPP_GLOBAL_Control
0x180030833  mov     rcx, cs:WPP_GLOBAL_Control
0x18003083a  cmp     rcx, r14
0x18003083d  jz      short loc_18003086C
0x18003083f  test    byte ptr [rcx+1Ch], 1
0x180030843  jz      short loc_18003086C
0x180030845  cmp     byte ptr [rcx+19h], 2
0x180030849  jb      short loc_18003086C
0x18003084b  mov     edx, 38h ; '8'
0x180030850  mov     eax, [rsp+1A0h+var_168]
0x180030854  mov     dword ptr [rsp+1A0h+var_180], eax
0x180030858  lea     r9, [rbp+0A0h+var_70]
0x18003085c  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180030863  mov     rcx, [rcx+10h]
0x180030867  call    WPP_SF_sd
0x18003086c  lea     rdx, byte_180075E00
0x180030873  mov     rcx, rdi
0x180030876  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x18003087b  nop
0x18003087c  lea     rcx, [rsp+1A0h+hTransaction]
0x180030881  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030886  nop
0x180030887  lea     rcx, [rbp+0A0h+var_118]
0x18003088b  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_3687a1fdef2f830cc28fffff45184d0a_______operator__
0x180030890  nop
0x180030891  lea     rcx, [rsp+1A0h+var_168]
0x180030896  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18003089b  nop
0x18003089c  mov     rax, rdi
0x18003089f  mov     rcx, [rbp+0A0h+var_30]
  ... truncated ...
```

# FileSystem::DeleteDf(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800308c8`
- end: `0x180030c7d`
- name: `?DeleteDf@FileSystem@@QEAA?AV?$scoped_error@Utag@apdustatus_error@@@errorlib@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `949`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004e35c`

## callees

- `0x180007a64`
- `0x180008148`
- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18000a960`
- `0x18000efc0`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180026054`
- `0x1800260e8`
- `0x1800261bc`
- `0x180029b84`
- `0x18002a124`
- `0x18002d7b8`
- `0x18002f45c`
- `0x180030254`
- `0x1800308c8`
- `0x180030c84`
- `0x1800322b4`
- `0x18003633c`
- `0x180039308`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180030b2f`
- `ktmw32!CommitTransaction` at `0x180030b2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_BYTE *__fastcall FileSystem::DeleteDf(__int64 a1, _BYTE *a2, __int64 a3)
{
  __int64 FilesystemTransaction; // rax
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // r8
  _QWORD *v18; // rcx
  int v19; // edx
  BOOL v20; // eax
  __int64 winerror_if; // rax
  unsigned int v22; // eax
  __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rdx
  HANDLE *v26; // rax
  char v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+3Ch] [rbp-C4h]
  HANDLE TransactionHandle[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE *v32; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE *v33; // [rsp+58h] [rbp-A8h]
  _QWORD v34[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v35; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  _QWORD *v38; // [rsp+98h] [rbp-68h] BYREF
  __int16 v39; // [rsp+A0h] [rbp-60h]
  _QWORD v40[4]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v41[40]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v42[48]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v43[64]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v44[6]; // [rsp+160h] [rbp+60h] BYREF

  v35 = a2;
  errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(a2);
  v37 = 1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v29);
  v28 = 1;
  v40[0] = &v28;
  v40[1] = a3;
  v40[2] = a2;
  v40[3] = &v29;
  lambda_b720cf1164622c2f921dfda3a7ce3a2e_::operator()(v40);
  v28 = 0;
  v38 = v40;
  v39 = 258;
  TransactionHandle[0] = (HANDLE)-1LL;
  FilesystemTransaction = FileSystem::DiskOperations::CreateFilesystemTransaction(v41);
  v32 = (HANDLE *)&v29;
  v33 = TransactionHandle;
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    &v32,
    FilesystemTransaction);
  std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(v41);
  v30 = 3;
  if ( !v29 )
  {
    rangelib::make_raw_range<std::vector<unsigned char> const &>(&v32, a3);
    v10 = FileSystem::HexToString(v43, &v32);
    v11 = std::operator+<unsigned short>(v41, a1);
    std::operator+<unsigned short>(v42, v11, v10);
    LOBYTE(v12) = 1;
    std::wstring::_Tidy(v41, v12, 0);
    LOBYTE(v13) = 1;
    std::wstring::_Tidy(v43, v13, 0);
    v34[0] = TransactionHandle[0];
    v14 = FileSystem::DiskOperations::DeleteDirectoryOnDisk(&v32, v42, v34);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v29, v14);
    v30 = 3;
    if ( v29 )
    {
      memset_0(v43, 0, sizeof(v43));
      v15 = ReportIndentTracker::Indent();
      v35 = v43;
      v36 = v44;
      LOBYTE(v16) = 95;
      ReportIndentTracker::Format(&v35, v15, v17, v16);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      v19 = 13;
    }
    else
    {
      v20 = CommitTransaction(TransactionHandle[0]);
      winerror_if = make_winerror_if(&v32, !v20);
      errorlib::scoped_error<ntstatus_error::tag>::operator=(&v29, winerror_if);
      v30 = 3;
      if ( !v29 )
      {
        std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>::_Eqrange(
          a1 + 40,
          &v32,
          a3);
        v26 = v32;
        v34[0] = v32;
        while ( v26 != v33 )
        {
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tmap_traits<Asn1Tag::type,DataObject::type,std::less<Asn1Tag::type>,std::allocator<std::pair<Asn1Tag::type const,DataObject::type>>,0>>,std::_Iterator_base0>::operator++(v34);
          v26 = (HANDLE *)v34[0];
        }
        std::_Tree<std::_Tmap_traits<std::vector<unsigned char>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<unsigned char>>,std::allocator<std::pair<std::vector<unsigned char> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>::erase(
          a1 + 40,
          &v32,
          v32,
          v33);
        goto LABEL_23;
      }
      memset_0(v43, 0, sizeof(v43));
      v22 = ReportIndentTracker::Indent();
      v35 = v43;
      v36 = v44;
      LOBYTE(v23) = 95;
      ReportIndentTracker::Format(&v35, v22, v24, v23);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
LABEL_23:
        LOBYTE(v25) = 1;
        std::wstring::_Tidy(v42, v25, 0);
        goto LABEL_24;
      }
      v19 = 14;
    }
    WPP_SF_sd(v18[2], v19, (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids, (unsigned int)v43, v29);
    goto LABEL_18;
  }
  memset_0(v43, 0, sizeof(v43));
  v7 = ReportIndentTracker::Indent();
  v35 = v43;
  v36 = v44;
  LOBYTE(v8) = 95;
  ReportIndentTracker::Format(&v35, v7, v9, v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
      (unsigned int)v43,
      v29);
  }
  errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(a2, &byte_180075E00);
LABEL_24:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TransactionHandle);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_b720cf1164622c2f921dfda3a7ce3a2e_____::operator()(&v38);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v29);
  return a2;
}

```

## disassembly

```asm
0x1800308c8  push    rbp
0x1800308ca  push    rbx
0x1800308cb  push    rsi
0x1800308cc  push    rdi
0x1800308cd  push    r14
0x1800308cf  lea     rbp, [rsp-70h]
0x1800308d4  sub     rsp, 170h
0x1800308db  mov     rax, cs:__security_cookie
0x1800308e2  xor     rax, rsp
0x1800308e5  mov     [rbp+90h+var_30], rax
0x1800308e9  mov     rsi, r8
0x1800308ec  mov     rdi, rdx
0x1800308ef  mov     r14, rcx
0x1800308f2  mov     [rbp+90h+var_110], rdx
0x1800308f6  mov     [rbp+90h+var_100], 1
0x1800308fd  mov     rcx, rdx
0x180030900  call    ??0?$scoped_error@Utag@apdustatus_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<apdustatus_error::tag>::scoped_error<apdustatus_error::tag>(void)
0x180030905  nop
0x180030906  mov     [rbp+90h+var_100], 1
0x18003090d  lea     rcx, [rsp+190h+var_158]
0x180030912  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030917  nop
0x180030918  mov     [rsp+190h+var_160], 1
0x18003091d  lea     rax, [rsp+190h+var_160]
0x180030922  mov     [rbp+90h+var_E8], rax
0x180030926  mov     [rbp+90h+var_E0], rsi
0x18003092a  mov     [rbp+90h+var_D8], rdi
0x18003092e  lea     rax, [rsp+190h+var_158]
0x180030933  mov     [rbp+90h+var_D0], rax
0x180030937  lea     rcx, [rbp+90h+var_E8]
0x18003093b  call    _lambda_b720cf1164622c2f921dfda3a7ce3a2e___operator__
0x180030940  mov     [rsp+190h+var_160], 0
0x180030945  lea     rax, [rbp+90h+var_E8]
0x180030949  mov     [rbp+90h+var_F8], rax
0x18003094d  mov     [rbp+90h+var_F0], 102h
0x180030953  mov     [rsp+190h+TransactionHandle], 0FFFFFFFFFFFFFFFFh
0x18003095c  lea     rcx, [rbp+90h+var_C8]
0x180030960  call    ?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ; FileSystem::DiskOperations::CreateFilesystemTransaction(void)
0x180030965  lea     rcx, [rsp+190h+var_158]
0x18003096a  mov     qword ptr [rsp+190h+var_140], rcx
0x18003096f  lea     rcx, [rsp+190h+TransactionHandle]
0x180030974  mov     qword ptr [rsp+190h+var_140+8], rcx
0x180030979  mov     rdx, rax
0x18003097c  lea     rcx, [rsp+190h+var_140]
0x180030981  call    ??$?4V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U456@U456@U456@U456@U456@U456@U456@@?$tuple@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAAAEAV012@$$QEAV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@12@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::operator=<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil> &&)
0x180030986  lea     rcx, [rbp+90h+var_C8]
0x18003098a  call    ??1?$_Cons_node@V?$scoped_error@Utag@winerror_error@@@errorlib@@U?$_Cons_node@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U?$_Cons_node@U_Nil@tr1@std@@U123@@tr1@std@@@tr1@std@@@tr1@std@@QEAA@XZ; std::tr1::_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>::~_Cons_node<errorlib::scoped_error<winerror_error::tag>,std::tr1::_Cons_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Cons_node<std::tr1::_Nil,std::tr1::_Nil>>>(void)
0x18003098f  mov     [rsp+190h+var_154], 3
0x180030997  cmp     [rsp+190h+var_158], 0
0x18003099c  jz      loc_180030A28
0x1800309a2  xor     edx, edx; Val
0x1800309a4  lea     r8d, [rdx+40h]; Size
0x1800309a8  lea     rcx, [rbp+90h+var_70]; void *
0x1800309ac  call    memset_0
0x1800309b1  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x1800309b6  lea     rcx, [rbp+90h+var_70]
0x1800309ba  mov     [rbp+90h+var_110], rcx
0x1800309be  lea     rcx, [rbp+90h+var_30]
0x1800309c2  mov     [rbp+90h+var_108], rcx
0x1800309c6  mov     r9b, 5Fh ; '_'
0x1800309c9  mov     edx, eax
0x1800309cb  lea     rcx, [rbp+90h+var_110]
0x1800309cf  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x1800309d4  lea     rax, WPP_GLOBAL_Control
0x1800309db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309e2  cmp     rcx, rax
0x1800309e5  jz      short loc_180030A14
0x1800309e7  test    byte ptr [rcx+1Ch], 1
0x1800309eb  jz      short loc_180030A14
0x1800309ed  cmp     byte ptr [rcx+19h], 2
0x1800309f1  jb      short loc_180030A14
0x1800309f3  mov     edx, 0Ch
0x1800309f8  mov     eax, [rsp+190h+var_158]
0x1800309fc  mov     [rsp+190h+var_170], eax
0x180030a00  lea     r9, [rbp+90h+var_70]
0x180030a04  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180030a0b  mov     rcx, [rcx+10h]
0x180030a0f  call    WPP_SF_sd
0x180030a14  lea     rdx, byte_180075E00
0x180030a1b  mov     rcx, rdi
0x180030a1e  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180030a23  jmp     loc_180030C40
0x180030a28  mov     rdx, rsi
0x180030a2b  lea     rcx, [rsp+190h+var_140]
0x180030a30  call    ??$make_raw_range@AEBV?$vector@EV?$allocator@E@std@@@std@@@rangelib@@YA?AV?$range@PEBE@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; rangelib::make_raw_range<std::vector<uchar> const &>(std::vector<uchar> const &)
0x180030a35  movaps  xmm0, [rsp+190h+var_140]
0x180030a3a  movdqa  [rsp+190h+var_140], xmm0
0x180030a40  lea     rdx, [rsp+190h+var_140]
0x180030a45  lea     rcx, [rbp+90h+var_70]
0x180030a49  call    ?HexToString@FileSystem@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@@Z; FileSystem::HexToString(rangelib::range<uchar const *>)
0x180030a4e  mov     rbx, rax
0x180030a51  mov     rdx, r14
0x180030a54  lea     rcx, [rbp+90h+var_C8]
0x180030a58  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x180030a5d  nop
0x180030a5e  mov     r8, rbx
0x180030a61  mov     rdx, rax
0x180030a64  lea     rcx, [rbp+90h+var_A0]
0x180030a68  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180030a6d  nop
0x180030a6e  xor     r8d, r8d
0x180030a71  mov     dl, 1
0x180030a73  lea     rcx, [rbp+90h+var_C8]
0x180030a77  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180030a7c  nop
0x180030a7d  xor     r8d, r8d
0x180030a80  mov     dl, 1
0x180030a82  lea     rcx, [rbp+90h+var_70]
0x180030a86  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180030a8b  mov     rax, [rsp+190h+TransactionHandle]
0x180030a90  mov     [rsp+190h+var_120], rax
0x180030a95  lea     r8, [rsp+190h+var_120]
0x180030a9a  lea     rdx, [rbp+90h+var_A0]
0x180030a9e  lea     rcx, [rsp+190h+var_140]
0x180030aa3  call    ?DeleteDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::DeleteDirectoryOnDisk(std::wstring const &,void * const &)
0x180030aa8  mov     rdx, rax
0x180030aab  lea     rcx, [rsp+190h+var_158]
0x180030ab0  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180030ab5  mov     ebx, 3
0x180030aba  mov     [rsp+190h+var_154], ebx
0x180030abe  cmp     [rsp+190h+var_158], 0
0x180030ac3  jz      short loc_180030B2A
0x180030ac5  xor     edx, edx; Val
0x180030ac7  lea     r8d, [rbx+3Dh]; Size
0x180030acb  lea     rcx, [rbp+90h+var_70]; void *
0x180030acf  call    memset_0
0x180030ad4  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030ad9  lea     rcx, [rbp+90h+var_70]
0x180030add  mov     [rbp+90h+var_110], rcx
0x180030ae1  lea     rcx, [rbp+90h+var_30]
0x180030ae5  mov     [rbp+90h+var_108], rcx
0x180030ae9  mov     r9b, 5Fh ; '_'
0x180030aec  mov     edx, eax
0x180030aee  lea     rcx, [rbp+90h+var_110]
0x180030af2  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030af7  lea     rax, WPP_GLOBAL_Control
0x180030afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180030b05  cmp     rcx, rax
0x180030b08  jz      loc_180030BD4
0x180030b0e  test    byte ptr [rcx+1Ch], 1
0x180030b12  jz      loc_180030BD4
0x180030b18  cmp     byte ptr [rcx+19h], 2
0x180030b1c  jb      loc_180030BD4
0x180030b22  lea     edx, [rbx+0Ah]
0x180030b25  jmp     loc_180030BB8
0x180030b2a  mov     rcx, [rsp+190h+TransactionHandle]; TransactionHandle
0x180030b2f  call    cs:__imp_CommitTransaction
0x180030b35  xor     edx, edx
0x180030b37  test    eax, eax
0x180030b39  setz    dl
0x180030b3c  lea     rcx, [rsp+190h+var_140]
0x180030b41  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180030b46  mov     rdx, rax
0x180030b49  lea     rcx, [rsp+190h+var_158]
0x180030b4e  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180030b53  mov     [rsp+190h+var_154], ebx
0x180030b57  cmp     [rsp+190h+var_158], 0
0x180030b5c  jz      loc_180030BE5
0x180030b62  xor     edx, edx; Val
0x180030b64  lea     r8d, [rdx+40h]; Size
0x180030b68  lea     rcx, [rbp+90h+var_70]; void *
0x180030b6c  call    memset_0
0x180030b71  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030b76  lea     rcx, [rbp+90h+var_70]
0x180030b7a  mov     [rbp+90h+var_110], rcx
0x180030b7e  lea     rcx, [rbp+90h+var_30]
0x180030b82  mov     [rbp+90h+var_108], rcx
0x180030b86  mov     r9b, 5Fh ; '_'
0x180030b89  mov     edx, eax
0x180030b8b  lea     rcx, [rbp+90h+var_110]
0x180030b8f  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030b94  lea     rax, WPP_GLOBAL_Control
0x180030b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ba2  cmp     rcx, rax
0x180030ba5  jz      short loc_180030BD4
0x180030ba7  test    byte ptr [rcx+1Ch], 1
0x180030bab  jz      short loc_180030BD4
0x180030bad  cmp     byte ptr [rcx+19h], 2
0x180030bb1  jb      short loc_180030BD4
0x180030bb3  mov     edx, 0Eh
0x180030bb8  mov     eax, [rsp+190h+var_158]
0x180030bbc  mov     [rsp+190h+var_170], eax
0x180030bc0  lea     r9, [rbp+90h+var_70]
0x180030bc4  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x180030bcb  mov     rcx, [rcx+10h]
0x180030bcf  call    WPP_SF_sd
0x180030bd4  lea     rdx, byte_180075E00
0x180030bdb  mov     rcx, rdi
0x180030bde  call    ??$initiate@Utag@apdustatus_error@@AEBUtype@StatusField@@@errorlib@@YAXPEAV?$scoped_error@Utag@apdustatus_error@@@0@AEBUtype@StatusField@@@Z; errorlib::initiate<apdustatus_error::tag,StatusField::type const &>(errorlib::scoped_error<apdustatus_error::tag> *,StatusField::type const &)
0x180030be3  jmp     short loc_180030C31
0x180030be5  mov     r8, rsi
0x180030be8  lea     rdx, [rsp+190h+var_140]
0x180030bed  lea     rcx, [r14+28h]
0x180030bf1  call    ?_Eqrange@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@@std@@@2@$0A@@std@@@std@@@std@@V12@@2@AEBV?$vector@EV?$allocator@E@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>::_Eqrange(std::vector<uchar> const &)
0x180030bf6  mov     rax, qword ptr [rsp+190h+var_140]
0x180030bfb  mov     [rsp+190h+var_120], rax
0x180030c00  cmp     rax, qword ptr [rsp+190h+var_140+8]
0x180030c05  jz      short loc_180030C18
0x180030c07  lea     rcx, [rsp+190h+var_120]
0x180030c0c  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@V?$_Tmap_traits@Utype@Asn1Tag@@U1DataObject@@U?$less@Utype@Asn1Tag@@@std@@V?$allocator@U?$pair@$$CBUtype@Asn1Tag@@U1DataObject@@@std@@@5@$0A@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tmap_traits<Asn1Tag::type,DataObject::type,std::less<Asn1Tag::type>,std::allocator<std::pair<Asn1Tag::type const,DataObject::type>>,0>>,std::_Iterator_base0>::operator++(void)
0x180030c11  mov     rax, [rsp+190h+var_120]
0x180030c16  jmp     short loc_180030C00
0x180030c18  mov     r9, qword ptr [rsp+190h+var_140+8]
0x180030c1d  mov     r8, qword ptr [rsp+190h+var_140]
0x180030c22  lea     rdx, [rsp+190h+var_140]
0x180030c27  lea     rcx, [r14+28h]
0x180030c2b  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@@std@@@2@$0A@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@U?$less@V?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$shared_ptr@VDedicatedFile@FileSystem@@@tr1@2@@std@@@2@$0A@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tmap_traits<std::vector<uchar>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tmap_traits<std::vector<uchar>,std::tr1::shared_ptr<FileSystem::DedicatedFile>,std::less<std::vector<uchar>>,std::allocator<std::pair<std::vector<uchar> const,std::tr1::shared_ptr<FileSystem::DedicatedFile>>>,0>>>)
0x180030c30  nop
0x180030c31  xor     r8d, r8d
0x180030c34  mov     dl, 1
0x180030c36  lea     rcx, [rbp+90h+var_A0]
0x180030c3a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180030c3f  nop
0x180030c40  lea     rcx, [rsp+190h+TransactionHandle]
0x180030c45  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030c4a  nop
0x180030c4b  lea     rcx, [rbp+90h+var_F8]
0x180030c4f  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_b720cf1164622c2f921dfda3a7ce3a2e_______operator__
0x180030c54  nop
0x180030c55  lea     rcx, [rsp+190h+var_158]
0x180030c5a  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180030c5f  nop
0x180030c60  mov     rax, rdi
0x180030c63  mov     rcx, [rbp+90h+var_30]
0x180030c67  xor     rcx, rsp; StackCookie
0x180030c6a  call    __security_check_cookie
0x180030c6f  add     rsp, 170h
0x180030c76  pop     r14
0x180030c78  pop     rdi
0x180030c79  pop     rsi
0x180030c7a  pop     rbx
0x180030c7b  pop     rbp
0x180030c7c  retn
```

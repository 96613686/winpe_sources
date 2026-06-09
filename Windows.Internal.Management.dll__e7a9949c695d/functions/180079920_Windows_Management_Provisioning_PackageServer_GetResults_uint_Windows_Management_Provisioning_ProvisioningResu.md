# Windows::Management::Provisioning::PackageServer::GetResults(uint *,Windows::Management::Provisioning::ProvisioningResult * *)

- ea: `0x180079920`
- end: `0x180079d2b`
- name: `?GetResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvisioningResult@234@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvisioningResult **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004d50`
- `0x18000523c`
- `0x180005904`
- `0x18000a2a4`
- `0x18000ce64`
- `0x180012ae8`
- `0x180015acc`
- `0x180015b48`
- `0x180019ae4`
- `0x18001e414`
- `0x180044d84`
- `0x1800786cc`
- `0x180078704`
- `0x18007893c`
- `0x180078a84`
- `0x180078c80`
- `0x180078db0`
- `0x180078f14`
- `0x180078f9c`
- `0x180079038`
- `0x180079920`
- `0x1800ab318`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180079c2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079c45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079c45`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Management::Provisioning::PackageServer::GetResults(
        Windows::Management::Provisioning::PackageServer *this,
        unsigned int *a2,
        struct Windows::Management::Provisioning::ProvisioningResult **a3)
{
  _QWORD *v5; // rax
  const struct ResultData *v6; // rdi
  ResultData *v7; // rsi
  char *v8; // rax
  unsigned int v9; // ebx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v15; // rsi
  int v16; // r12d
  __int64 *v17; // rbx
  char *v18; // rax
  __int64 **v19; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  HSTRING string; // [rsp+20h] [rbp-158h] BYREF
  void *v23; // [rsp+28h] [rbp-150h] BYREF
  char *v24; // [rsp+30h] [rbp-148h] BYREF
  unsigned __int64 v25[2]; // [rsp+38h] [rbp-140h] BYREF
  ResultData *v26[2]; // [rsp+48h] [rbp-130h] BYREF
  __int64 v27; // [rsp+58h] [rbp-120h]
  char v28[16]; // [rsp+60h] [rbp-118h] BYREF
  unsigned __int64 v29; // [rsp+70h] [rbp-108h]
  char v30[16]; // [rsp+78h] [rbp-100h] BYREF
  __int128 v31; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v32; // [rsp+98h] [rbp-E0h]
  __int64 v33; // [rsp+A0h] [rbp-D8h]
  unsigned __int64 v34; // [rsp+A8h] [rbp-D0h]
  _QWORD v35[6]; // [rsp+B0h] [rbp-C8h] BYREF
  char v36[32]; // [rsp+E0h] [rbp-98h] BYREF
  int v37; // [rsp+100h] [rbp-78h]
  int v38; // [rsp+104h] [rbp-74h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  *a3 = 0;
  *a2 = 0;
  ProvResults::EnumerateByPackageId((__int64)v26);
  *(_OWORD *)v25 = 0;
  v5 = operator new(0x48u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  v25[0] = (unsigned __int64)v5;
  v6 = v26[0];
  v7 = v26[1];
  while ( v6 != v7 )
  {
    ResultData::ResultData((ResultData *)v35, v6);
    v8 = *(char **)v35[0];
    v24 = *(char **)v35[0];
    while ( !v8[25] )
    {
      v9 = *((_DWORD *)v8 + 7);
      LODWORD(string) = v9;
      if ( v9 )
      {
        v31 = 0;
        v32 = 0;
        v33 = 7;
        LOWORD(v31) = 0;
        if ( v38 < 0 )
        {
          if ( v37 == v9 )
            std::wstring::operator=(&v31, v36);
          else
            std::wstring::_Assign<unsigned short>(&v31, L"Related setting failure.");
        }
        std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Find_lower_bound<unsigned int>(
          v25,
          v28,
          &string);
        v10 = v29;
        if ( *(_BYTE *)(v29 + 25) || v9 < *(_DWORD *)(v29 + 32) )
        {
          v11 = v25[0];
          v10 = v25[0];
        }
        else
        {
          v11 = v25[0];
        }
        if ( v10 == v11 )
          ((void (__fastcall *)(unsigned __int64 *, char *, HSTRING *, __int128 *))std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::_Emplace<unsigned int &,std::wstring &>)(
            v25,
            v30,
            &string,
            &v31);
        else
          std::wstring::_Append<unsigned short>((void *)(v10 + 40));
        std::wstring::_Tidy_deallocate(&v31);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<unsigned int>>,std::_Iterator_base0>::operator++(&v24);
      v8 = v24;
    }
    ResultData::~ResultData((ResultData *)v35);
    v6 = (const struct ResultData *)((char *)v6 + 120);
  }
  LODWORD(string) = 0;
  v12 = ULongLongToULong(v25[1], (unsigned int *)&string);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v15 = (unsigned int)string;
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningResult [0]>(&v23);
    memset_0(v23, 0, 24 * v15);
    v16 = 0;
    v17 = *(__int64 **)v25[0];
    while ( !*((_BYTE *)v17 + 25) )
    {
      LODWORD(v31) = *((_DWORD *)v17 + 8);
      std::wstring::wstring((char *)&v31 + 8, v17 + 5);
      *((_DWORD *)v23 + 6 * v16) = v31;
      string = 0;
      v18 = (char *)&v31 + 8;
      if ( v34 > 7 )
        v18 = (char *)*((_QWORD *)&v31 + 1);
      v24 = v18;
      Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &v24);
      WindowsDuplicateString(string, (HSTRING *)v23 + 3 * v16 + 1);
      *((_DWORD *)v23 + 6 * v16++ + 4) = 4;
      WindowsDeleteString(string);
      std::wstring::_Tidy_deallocate((char *)&v31 + 8);
      v19 = (__int64 **)v17[2];
      if ( *((_BYTE *)v19 + 25) )
      {
        for ( i = (__int64 *)v17[1]; !*((_BYTE *)i + 25) && v17 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v17 = i;
        v17 = i;
      }
      else
      {
        v17 = (__int64 *)v17[2];
        for ( j = *v19; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v17 = j;
      }
    }
    *a3 = (struct Windows::Management::Provisioning::ProvisioningResult *)v23;
    *a2 = v15;
    v23 = 0;
    std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>(v25);
    if ( v26[0] )
    {
      std::_Destroy_range<std::allocator<ResultData>>(v26[0]);
      std::_Deallocate<16>((_QWORD *)v26[0], 8 * ((signed __int64)(v27 - (unsigned __int64)v26[0]) >> 3));
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
      (const char *)(unsigned int)v12,
      (int)string);
    std::_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::wstring,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::wstring>>,0>>(v25);
    if ( v26[0] )
    {
      std::_Destroy_range<std::allocator<ResultData>>(v26[0]);
      std::_Deallocate<16>((_QWORD *)v26[0], 8 * ((signed __int64)(v27 - (unsigned __int64)v26[0]) >> 3));
    }
    return v13;
  }
}

```

## disassembly

```asm
0x180079920  push    rbx
0x180079922  push    rsi
0x180079923  push    rdi
0x180079924  push    r12
0x180079926  push    r13
0x180079928  push    r14
0x18007992a  push    r15
0x18007992c  sub     rsp, 140h
0x180079933  mov     rax, cs:__security_cookie
0x18007993a  xor     rax, rsp
0x18007993d  mov     [rsp+178h+var_48], rax
0x180079945  mov     r15, r8
0x180079948  mov     r14, rdx
0x18007994b  xor     r13d, r13d
0x18007994e  mov     [r8], r13
0x180079951  mov     [rdx], r13d
0x180079954  lea     rdx, [rcx+68h]
0x180079958  lea     rcx, [rsp+178h+var_130]
0x18007995d  call    ?EnumerateByPackageId@ProvResults@@SA?AV?$vector@UResultData@@V?$allocator@UResultData@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; ProvResults::EnumerateByPackageId(std::wstring const &)
0x180079962  nop
0x180079963  xorps   xmm0, xmm0
0x180079966  movdqu  xmmword ptr [rsp+178h+var_140], xmm0
0x18007996c  lea     ecx, [r13+48h]; Size
0x180079970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079975  mov     [rax], rax
0x180079978  mov     [rax+8], rax
0x18007997c  mov     [rax+10h], rax
0x180079980  mov     word ptr [rax+18h], 101h
0x180079986  mov     [rsp+178h+var_140], rax
0x18007998b  mov     rdi, [rsp+178h+var_130]
0x180079990  mov     rsi, [rsp+178h+var_128]
0x180079995  cmp     rdi, rsi
0x180079998  jz      loc_180079AF5
0x18007999e  mov     rdx, rdi; struct ResultData *
0x1800799a1  lea     rcx, [rsp+178h+var_C8]; this
0x1800799a9  call    ??0ResultData@@QEAA@AEBU0@@Z; ResultData::ResultData(ResultData const &)
0x1800799ae  nop
0x1800799af  mov     rax, [rsp+178h+var_C8]
0x1800799b7  mov     rax, [rax]
0x1800799ba  mov     [rsp+178h+var_148], rax
0x1800799bf  cmp     [rax+19h], r13b
0x1800799c3  jnz     loc_180079ADF
0x1800799c9  mov     ebx, [rax+1Ch]
0x1800799cc  mov     dword ptr [rsp+178h+string], ebx
0x1800799d0  test    ebx, ebx
0x1800799d2  jz      loc_180079ACB
0x1800799d8  xorps   xmm0, xmm0
0x1800799db  movups  [rsp+178h+var_F0], xmm0
0x1800799e3  mov     [rsp+178h+var_E0], r13
0x1800799eb  mov     [rsp+178h+var_D8], 7
0x1800799f7  mov     word ptr [rsp+178h+var_F0], r13w
0x180079a00  cmp     [rsp+178h+var_74], r13d
0x180079a08  jge     short loc_180079A3C
0x180079a0a  lea     rcx, [rsp+178h+var_F0]
0x180079a12  cmp     [rsp+178h+var_78], ebx
0x180079a19  jnz     short loc_180079A2A
0x180079a1b  lea     rdx, [rsp+178h+var_98]
0x180079a23  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180079a28  jmp     short loc_180079A3C
0x180079a2a  mov     r8d, 18h
0x180079a30  lea     rdx, aRelatedSetting; "Related setting failure."
0x180079a37  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180079a3c  lea     r8, [rsp+178h+string]
0x180079a41  lea     rdx, [rsp+178h+var_118]
0x180079a46  lea     rcx, [rsp+178h+var_140]
0x180079a4b  call    ??$_Find_lower_bound@I@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Find_lower_bound<uint>(uint const &)
0x180079a50  mov     rcx, [rsp+178h+var_108]
0x180079a55  cmp     [rcx+19h], r13b
0x180079a59  jnz     short loc_180079A67
0x180079a5b  cmp     ebx, [rcx+20h]
0x180079a5e  jb      short loc_180079A67
0x180079a60  mov     rax, [rsp+178h+var_140]
0x180079a65  jmp     short loc_180079A6F
0x180079a67  mov     rax, [rsp+178h+var_140]
0x180079a6c  mov     rcx, rax
0x180079a6f  cmp     rcx, rax
0x180079a72  jnz     short loc_180079A92
0x180079a74  lea     r9, [rsp+178h+var_F0]
0x180079a7c  lea     r8, [rsp+178h+string]
0x180079a81  lea     rdx, [rsp+178h+var_100]
0x180079a86  lea     rcx, [rsp+178h+var_140]
0x180079a8b  call    ??$_Emplace@AEAIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEAIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Emplace<uint &,std::wstring &>(uint &,std::wstring &)
0x180079a90  jmp     short loc_180079ABE
0x180079a92  lea     rdx, [rsp+178h+var_F0]
0x180079a9a  cmp     [rsp+178h+var_D8], 7
0x180079aa3  cmova   rdx, qword ptr [rsp+178h+var_F0]
0x180079aac  add     rcx, 28h ; '('; Src
0x180079ab0  mov     r8, [rsp+178h+var_E0]
0x180079ab8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180079abd  nop
0x180079abe  lea     rcx, [rsp+178h+var_F0]
0x180079ac6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180079acb  lea     rcx, [rsp+178h+var_148]
0x180079ad0  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>::operator++(void)
0x180079ad5  mov     rax, [rsp+178h+var_148]
0x180079ada  jmp     loc_1800799BF
0x180079adf  lea     rcx, [rsp+178h+var_C8]; this
0x180079ae7  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x180079aec  add     rdi, 78h ; 'x'
0x180079af0  jmp     loc_180079995
0x180079af5  mov     dword ptr [rsp+178h+string], r13d; int
0x180079afa  lea     rdx, [rsp+178h+string]; unsigned int *
0x180079aff  mov     rcx, [rsp+178h+var_140+8]; unsigned __int64
0x180079b04  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180079b09  mov     ebx, eax
0x180079b0b  test    eax, eax
0x180079b0d  jns     short loc_180079B7A
0x180079b0f  mov     rcx, [rsp+178h]; this
0x180079b17  mov     r9d, eax; char *
0x180079b1a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079b21  mov     edx, 0C7h; void *
0x180079b26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b2b  nop
0x180079b2c  lea     rcx, [rsp+178h+var_140]
0x180079b31  call    ??1?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>(void)
0x180079b36  nop
0x180079b37  mov     rcx, [rsp+178h+var_130]; this
0x180079b3c  test    rcx, rcx
0x180079b3f  jz      short loc_180079B73
0x180079b41  mov     rdx, [rsp+178h+var_128]
0x180079b46  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x180079b4b  mov     rcx, [rsp+178h+var_130]
0x180079b50  mov     rax, [rsp+178h+var_120]
0x180079b55  sub     rax, rcx
0x180079b58  sar     rax, 3
0x180079b5c  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x180079b66  imul    rax, rdx
0x180079b6a  imul    rdx, rax, 78h ; 'x'
0x180079b6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180079b73  mov     eax, ebx
0x180079b75  jmp     loc_180079D07
0x180079b7a  mov     esi, dword ptr [rsp+178h+string]
0x180079b7e  mov     edx, esi
0x180079b80  lea     rcx, [rsp+178h+var_150]
0x180079b85  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningResult@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningResult [0]>(unsigned __int64)
0x180079b8a  nop
0x180079b8b  lea     r8, [rsi+rsi*2]
0x180079b8f  shl     r8, 3; Size
0x180079b93  xor     edx, edx; Val
0x180079b95  mov     rcx, [rsp+178h+var_150]; void *
0x180079b9a  call    memset_0
0x180079b9f  mov     r12d, r13d
0x180079ba2  mov     rbx, [rsp+178h+var_140]
0x180079ba7  mov     rbx, [rbx]
0x180079baa  cmp     [rbx+19h], r13b
0x180079bae  jnz     loc_180079CA7
0x180079bb4  mov     eax, [rbx+20h]
0x180079bb7  mov     dword ptr [rsp+178h+var_F0], eax
0x180079bbe  lea     rdx, [rbx+28h]
0x180079bc2  lea     rcx, [rsp+178h+var_F0+8]
0x180079bca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180079bcf  movsxd  rax, r12d
0x180079bd2  lea     rdi, [rax+rax*2]
0x180079bd6  mov     rcx, [rsp+178h+var_150]
0x180079bdb  mov     eax, dword ptr [rsp+178h+var_F0]
0x180079be2  mov     [rcx+rdi*8], eax
0x180079be5  mov     [rsp+178h+string], r13
0x180079bea  lea     rax, [rsp+178h+var_F0+8]
0x180079bf2  cmp     [rsp+178h+var_D0], 7
0x180079bfb  cmova   rax, qword ptr [rsp+178h+var_F0+8]
0x180079c04  mov     [rsp+178h+var_148], rax
0x180079c09  lea     rdx, [rsp+178h+var_148]
0x180079c0e  lea     rcx, [rsp+178h+string]
0x180079c13  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180079c18  mov     rdx, [rsp+178h+var_150]
0x180079c1d  add     rdx, 8
0x180079c21  lea     rdx, [rdx+rdi*8]; newString
0x180079c25  mov     rcx, [rsp+178h+string]; string
0x180079c2a  call    cs:__imp_WindowsDuplicateString
0x180079c30  mov     rax, [rsp+178h+var_150]
0x180079c35  mov     dword ptr [rax+rdi*8+10h], 4
0x180079c3d  inc     r12d
0x180079c40  mov     rcx, [rsp+178h+string]; string
0x180079c45  call    cs:__imp_WindowsDeleteString
0x180079c4b  lea     rcx, [rsp+178h+var_F0+8]
0x180079c53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180079c58  mov     rcx, [rbx+10h]
0x180079c5c  cmp     [rcx+19h], r13b
0x180079c60  jz      short loc_180079C83
0x180079c62  mov     rax, [rbx+8]
0x180079c66  jmp     short loc_180079C75
0x180079c68  cmp     rbx, [rax+10h]
0x180079c6c  jnz     short loc_180079C7B
0x180079c6e  mov     rbx, rax
0x180079c71  mov     rax, [rax+8]
0x180079c75  cmp     [rax+19h], r13b
0x180079c79  jz      short loc_180079C68
0x180079c7b  mov     rbx, rax
0x180079c7e  jmp     loc_180079BAA
0x180079c83  mov     rbx, rcx
0x180079c86  mov     rcx, [rcx]
0x180079c89  cmp     [rcx+19h], r13b
0x180079c8d  jnz     loc_180079BAA
0x180079c93  mov     rbx, rcx
0x180079c96  mov     rax, [rcx]
0x180079c99  mov     rcx, rax
0x180079c9c  cmp     [rax+19h], r13b
0x180079ca0  jz      short loc_180079C93
0x180079ca2  jmp     loc_180079BAA
0x180079ca7  mov     rax, [rsp+178h+var_150]
0x180079cac  mov     [r15], rax
0x180079caf  mov     [r14], esi
0x180079cb2  mov     [rsp+178h+var_150], r13
0x180079cb7  lea     rcx, [rsp+178h+var_140]
0x180079cbc  call    ??1?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>(void)
0x180079cc1  nop
0x180079cc2  mov     rcx, [rsp+178h+var_130]; this
0x180079cc7  test    rcx, rcx
0x180079cca  jz      short loc_180079CFF
0x180079ccc  mov     rdx, [rsp+178h+var_128]
0x180079cd1  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x180079cd6  mov     rcx, [rsp+178h+var_130]
0x180079cdb  mov     rax, [rsp+178h+var_120]
0x180079ce0  sub     rax, rcx
0x180079ce3  sar     rax, 3
0x180079ce7  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x180079cf1  imul    rax, rdx
0x180079cf5  imul    rdx, rax, 78h ; 'x'
0x180079cf9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180079cfe  nop
0x180079cff  xor     eax, eax
0x180079d01  jmp     short loc_180079D07
0x180079d03  mov     eax, dword ptr [rsp+178h+string]
0x180079d07  mov     rcx, [rsp+178h+var_48]
0x180079d0f  xor     rcx, rsp; StackCookie
0x180079d12  call    __security_check_cookie
0x180079d17  add     rsp, 140h
0x180079d1e  pop     r15
0x180079d20  pop     r14
0x180079d22  pop     r13
0x180079d24  pop     r12
0x180079d26  pop     rdi
0x180079d27  pop     rsi
0x180079d28  pop     rbx
0x180079d29  retn
```

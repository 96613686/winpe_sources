# Windows::Management::Provisioning::PackageServer::GetResults(uint *,Windows::Management::Provisioning::ProvisioningResult * *)

- ea: `0x18007b160`
- end: `0x18007b577`
- name: `?GetResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvisioningResult@234@@Z`
- size: `1047`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvisioningResult **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x18000539c`
- `0x180005a74`
- `0x18000a5c4`
- `0x18000d388`
- `0x1800131a8`
- `0x1800161ec`
- `0x180016268`
- `0x1800184c0`
- `0x18001c920`
- `0x1800449f0`
- `0x180079eb0`
- `0x180079ee8`
- `0x18007a124`
- `0x18007a270`
- `0x18007a484`
- `0x18007a5b4`
- `0x18007a718`
- `0x18007a7a0`
- `0x18007a840`
- `0x18007b160`
- `0x1800ae418`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007b46a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b48b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b48b`

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
  int v36; // [rsp+100h] [rbp-78h]
  int v37; // [rsp+104h] [rbp-74h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  *a3 = 0;
  *a2 = 0;
  ProvResults::EnumerateByPackageId(v26, (char *)this + 104);
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
        if ( v37 < 0 )
        {
          if ( v36 == v9 )
            std::wstring::operator=(&v31);
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
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningResult [0]>(&v23, (unsigned int)string);
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
      std::_Deallocate<16>(v26[0], 8 * ((signed __int64)(v27 - (unsigned __int64)v26[0]) >> 3));
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
      std::_Deallocate<16>(v26[0], 8 * ((signed __int64)(v27 - (unsigned __int64)v26[0]) >> 3));
    }
    return v13;
  }
}

```

## disassembly

```asm
0x18007b160  push    rbx
0x18007b162  push    rsi
0x18007b163  push    rdi
0x18007b164  push    r12
0x18007b166  push    r13
0x18007b168  push    r14
0x18007b16a  push    r15
0x18007b16c  sub     rsp, 140h
0x18007b173  mov     rax, cs:__security_cookie
0x18007b17a  xor     rax, rsp
0x18007b17d  mov     [rsp+178h+var_48], rax
0x18007b185  mov     r15, r8
0x18007b188  mov     r14, rdx
0x18007b18b  xor     r13d, r13d
0x18007b18e  mov     [r8], r13
0x18007b191  mov     [rdx], r13d
0x18007b194  lea     rdx, [rcx+68h]
0x18007b198  lea     rcx, [rsp+178h+var_130]
0x18007b19d  call    ?EnumerateByPackageId@ProvResults@@SA?AV?$vector@UResultData@@V?$allocator@UResultData@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; ProvResults::EnumerateByPackageId(std::wstring const &)
0x18007b1a2  nop
0x18007b1a3  xorps   xmm0, xmm0
0x18007b1a6  movdqu  xmmword ptr [rsp+178h+var_140], xmm0
0x18007b1ac  lea     ecx, [r13+48h]; Size
0x18007b1b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b1b5  mov     [rax], rax
0x18007b1b8  mov     [rax+8], rax
0x18007b1bc  mov     [rax+10h], rax
0x18007b1c0  mov     word ptr [rax+18h], 101h
0x18007b1c6  mov     [rsp+178h+var_140], rax
0x18007b1cb  mov     rdi, [rsp+178h+var_130]
0x18007b1d0  mov     rsi, [rsp+178h+var_128]
0x18007b1d5  cmp     rdi, rsi
0x18007b1d8  jz      loc_18007B335
0x18007b1de  mov     rdx, rdi; struct ResultData *
0x18007b1e1  lea     rcx, [rsp+178h+var_C8]; this
0x18007b1e9  call    ??0ResultData@@QEAA@AEBU0@@Z; ResultData::ResultData(ResultData const &)
0x18007b1ee  nop
0x18007b1ef  mov     rax, [rsp+178h+var_C8]
0x18007b1f7  mov     rax, [rax]
0x18007b1fa  mov     [rsp+178h+var_148], rax
0x18007b1ff  cmp     [rax+19h], r13b
0x18007b203  jnz     loc_18007B31F
0x18007b209  mov     ebx, [rax+1Ch]
0x18007b20c  mov     dword ptr [rsp+178h+string], ebx
0x18007b210  test    ebx, ebx
0x18007b212  jz      loc_18007B30B
0x18007b218  xorps   xmm0, xmm0
0x18007b21b  movups  [rsp+178h+var_F0], xmm0
0x18007b223  mov     [rsp+178h+var_E0], r13
0x18007b22b  mov     [rsp+178h+var_D8], 7
0x18007b237  mov     word ptr [rsp+178h+var_F0], r13w
0x18007b240  cmp     [rsp+178h+var_74], r13d
0x18007b248  jge     short loc_18007B27C
0x18007b24a  lea     rcx, [rsp+178h+var_F0]
0x18007b252  cmp     [rsp+178h+var_78], ebx
0x18007b259  jnz     short loc_18007B26A
0x18007b25b  lea     rdx, [rsp+178h+var_98]
0x18007b263  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007b268  jmp     short loc_18007B27C
0x18007b26a  mov     r8d, 18h
0x18007b270  lea     rdx, aRelatedSetting; "Related setting failure."
0x18007b277  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007b27c  lea     r8, [rsp+178h+string]
0x18007b281  lea     rdx, [rsp+178h+var_118]
0x18007b286  lea     rcx, [rsp+178h+var_140]
0x18007b28b  call    ??$_Find_lower_bound@I@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Find_lower_bound<uint>(uint const &)
0x18007b290  mov     rcx, [rsp+178h+var_108]
0x18007b295  cmp     [rcx+19h], r13b
0x18007b299  jnz     short loc_18007B2A7
0x18007b29b  cmp     ebx, [rcx+20h]
0x18007b29e  jb      short loc_18007B2A7
0x18007b2a0  mov     rax, [rsp+178h+var_140]
0x18007b2a5  jmp     short loc_18007B2AF
0x18007b2a7  mov     rax, [rsp+178h+var_140]
0x18007b2ac  mov     rcx, rax
0x18007b2af  cmp     rcx, rax
0x18007b2b2  jnz     short loc_18007B2D2
0x18007b2b4  lea     r9, [rsp+178h+var_F0]
0x18007b2bc  lea     r8, [rsp+178h+string]
0x18007b2c1  lea     rdx, [rsp+178h+var_100]
0x18007b2c6  lea     rcx, [rsp+178h+var_140]
0x18007b2cb  call    ??$_Emplace@AEAIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@AEAIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::_Emplace<uint &,std::wstring &>(uint &,std::wstring &)
0x18007b2d0  jmp     short loc_18007B2FE
0x18007b2d2  lea     rdx, [rsp+178h+var_F0]
0x18007b2da  cmp     [rsp+178h+var_D8], 7
0x18007b2e3  cmova   rdx, qword ptr [rsp+178h+var_F0]
0x18007b2ec  add     rcx, 28h ; '('; Src
0x18007b2f0  mov     r8, [rsp+178h+var_E0]
0x18007b2f8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18007b2fd  nop
0x18007b2fe  lea     rcx, [rsp+178h+var_F0]
0x18007b306  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b30b  lea     rcx, [rsp+178h+var_148]
0x18007b310  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<uint>>,std::_Iterator_base0>::operator++(void)
0x18007b315  mov     rax, [rsp+178h+var_148]
0x18007b31a  jmp     loc_18007B1FF
0x18007b31f  lea     rcx, [rsp+178h+var_C8]; this
0x18007b327  call    ??1ResultData@@QEAA@XZ; ResultData::~ResultData(void)
0x18007b32c  add     rdi, 78h ; 'x'
0x18007b330  jmp     loc_18007B1D5
0x18007b335  mov     dword ptr [rsp+178h+string], r13d; int
0x18007b33a  lea     rdx, [rsp+178h+string]; unsigned int *
0x18007b33f  mov     rcx, [rsp+178h+var_140+8]; unsigned __int64
0x18007b344  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007b349  mov     ebx, eax
0x18007b34b  test    eax, eax
0x18007b34d  jns     short loc_18007B3BA
0x18007b34f  mov     rcx, [rsp+178h]; this
0x18007b357  mov     r9d, eax; char *
0x18007b35a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007b361  mov     edx, 0C7h; void *
0x18007b366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b36b  nop
0x18007b36c  lea     rcx, [rsp+178h+var_140]
0x18007b371  call    ??1?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>(void)
0x18007b376  nop
0x18007b377  mov     rcx, [rsp+178h+var_130]; this
0x18007b37c  test    rcx, rcx
0x18007b37f  jz      short loc_18007B3B3
0x18007b381  mov     rdx, [rsp+178h+var_128]
0x18007b386  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x18007b38b  mov     rcx, [rsp+178h+var_130]
0x18007b390  mov     rax, [rsp+178h+var_120]
0x18007b395  sub     rax, rcx
0x18007b398  sar     rax, 3
0x18007b39c  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x18007b3a6  imul    rax, rdx
0x18007b3aa  imul    rdx, rax, 78h ; 'x'
0x18007b3ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007b3b3  mov     eax, ebx
0x18007b3b5  jmp     loc_18007B553
0x18007b3ba  mov     esi, dword ptr [rsp+178h+string]
0x18007b3be  mov     edx, esi
0x18007b3c0  lea     rcx, [rsp+178h+var_150]
0x18007b3c5  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningResult@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningResult [0]>(unsigned __int64)
0x18007b3ca  nop
0x18007b3cb  lea     r8, [rsi+rsi*2]
0x18007b3cf  shl     r8, 3; Size
0x18007b3d3  xor     edx, edx; Val
0x18007b3d5  mov     rcx, [rsp+178h+var_150]; void *
0x18007b3da  call    memset_0
0x18007b3df  mov     r12d, r13d
0x18007b3e2  mov     rbx, [rsp+178h+var_140]
0x18007b3e7  mov     rbx, [rbx]
0x18007b3ea  cmp     [rbx+19h], r13b
0x18007b3ee  jnz     loc_18007B4F3
0x18007b3f4  mov     eax, [rbx+20h]
0x18007b3f7  mov     dword ptr [rsp+178h+var_F0], eax
0x18007b3fe  lea     rdx, [rbx+28h]
0x18007b402  lea     rcx, [rsp+178h+var_F0+8]
0x18007b40a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007b40f  movsxd  rax, r12d
0x18007b412  lea     rdi, [rax+rax*2]
0x18007b416  mov     rcx, [rsp+178h+var_150]
0x18007b41b  mov     eax, dword ptr [rsp+178h+var_F0]
0x18007b422  mov     [rcx+rdi*8], eax
0x18007b425  mov     [rsp+178h+string], r13
0x18007b42a  lea     rax, [rsp+178h+var_F0+8]
0x18007b432  cmp     [rsp+178h+var_D0], 7
0x18007b43b  cmova   rax, qword ptr [rsp+178h+var_F0+8]
0x18007b444  mov     [rsp+178h+var_148], rax
0x18007b449  lea     rdx, [rsp+178h+var_148]
0x18007b44e  lea     rcx, [rsp+178h+string]
0x18007b453  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007b458  mov     rdx, [rsp+178h+var_150]
0x18007b45d  add     rdx, 8
0x18007b461  lea     rdx, [rdx+rdi*8]; newString
0x18007b465  mov     rcx, [rsp+178h+string]; string
0x18007b46a  call    cs:__imp_WindowsDuplicateString
0x18007b471  nop     dword ptr [rax+rax+00h]
0x18007b476  mov     rax, [rsp+178h+var_150]
0x18007b47b  mov     dword ptr [rax+rdi*8+10h], 4
0x18007b483  inc     r12d
0x18007b486  mov     rcx, [rsp+178h+string]; string
0x18007b48b  call    cs:__imp_WindowsDeleteString
0x18007b492  nop     dword ptr [rax+rax+00h]
0x18007b497  lea     rcx, [rsp+178h+var_F0+8]
0x18007b49f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007b4a4  mov     rcx, [rbx+10h]
0x18007b4a8  cmp     [rcx+19h], r13b
0x18007b4ac  jz      short loc_18007B4CF
0x18007b4ae  mov     rax, [rbx+8]
0x18007b4b2  jmp     short loc_18007B4C1
0x18007b4b4  cmp     rbx, [rax+10h]
0x18007b4b8  jnz     short loc_18007B4C7
0x18007b4ba  mov     rbx, rax
0x18007b4bd  mov     rax, [rax+8]
0x18007b4c1  cmp     [rax+19h], r13b
0x18007b4c5  jz      short loc_18007B4B4
0x18007b4c7  mov     rbx, rax
0x18007b4ca  jmp     loc_18007B3EA
0x18007b4cf  mov     rbx, rcx
0x18007b4d2  mov     rcx, [rcx]
0x18007b4d5  cmp     [rcx+19h], r13b
0x18007b4d9  jnz     loc_18007B3EA
0x18007b4df  mov     rbx, rcx
0x18007b4e2  mov     rax, [rcx]
0x18007b4e5  mov     rcx, rax
0x18007b4e8  cmp     [rax+19h], r13b
0x18007b4ec  jz      short loc_18007B4DF
0x18007b4ee  jmp     loc_18007B3EA
0x18007b4f3  mov     rax, [rsp+178h+var_150]
0x18007b4f8  mov     [r15], rax
0x18007b4fb  mov     [r14], esi
0x18007b4fe  mov     [rsp+178h+var_150], r13
0x18007b503  lea     rcx, [rsp+178h+var_140]
0x18007b508  call    ??1?$_Tree@V?$_Tmap_traits@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<uint,std::wstring,std::less<uint>,std::allocator<std::pair<uint const,std::wstring>>,0>>(void)
0x18007b50d  nop
0x18007b50e  mov     rcx, [rsp+178h+var_130]; this
0x18007b513  test    rcx, rcx
0x18007b516  jz      short loc_18007B54B
0x18007b518  mov     rdx, [rsp+178h+var_128]
0x18007b51d  call    ??$_Destroy_range@V?$allocator@UResultData@@@std@@@std@@YAXPEAUResultData@@QEAU1@AEAV?$allocator@UResultData@@@0@@Z; std::_Destroy_range<std::allocator<ResultData>>(ResultData *,ResultData * const,std::allocator<ResultData> &)
0x18007b522  mov     rcx, [rsp+178h+var_130]
0x18007b527  mov     rax, [rsp+178h+var_120]
0x18007b52c  sub     rax, rcx
0x18007b52f  sar     rax, 3
0x18007b533  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x18007b53d  imul    rax, rdx
0x18007b541  imul    rdx, rax, 78h ; 'x'
0x18007b545  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007b54a  nop
0x18007b54b  xor     eax, eax
0x18007b54d  jmp     short loc_18007B553
0x18007b54f  mov     eax, dword ptr [rsp+178h+string]
0x18007b553  mov     rcx, [rsp+178h+var_48]
0x18007b55b  xor     rcx, rsp; StackCookie
0x18007b55e  call    __security_check_cookie
0x18007b563  add     rsp, 140h
0x18007b56a  pop     r15
0x18007b56c  pop     r14
0x18007b56e  pop     r13
0x18007b570  pop     r12
0x18007b572  pop     rdi
0x18007b573  pop     rsi
0x18007b574  pop     rbx
0x18007b575  retn
```

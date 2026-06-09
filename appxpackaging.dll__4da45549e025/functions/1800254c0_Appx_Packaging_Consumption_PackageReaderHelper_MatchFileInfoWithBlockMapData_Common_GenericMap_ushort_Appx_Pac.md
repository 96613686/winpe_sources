# Appx::Packaging::Consumption::PackageReaderHelper::MatchFileInfoWithBlockMapData(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> *,Common::Array<Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile,Common::ContainerOperations<Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile,Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile>,Common::ArrayOperations<Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile,Common::NoKey>> *)

- ea: `0x1800254c0`
- end: `0x180025a04`
- name: `?MatchFileInfoWithBlockMapData@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEAV?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@34@PEAV?$Array@UMatchedFile@PackageReaderHelper@Consumption@Packaging@Appx@@V?$ContainerOperations@UMatchedFile@PackageReaderHelper@Consumption@Packaging@Appx@@U12345@@Common@@VNoKey@7@V?$ContainerOperations@VNoKey@Common@@UMatchedFile@PackageReaderHelper@Consumption@Packaging@Appx@@@7@V?$ArrayOperations@UMatchedFile@PackageReaderHelper@Consumption@Packaging@Appx@@VNoKey@Common@@@7@@6@@Z`
- size: `1348`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800459f0`
- `0x18004cd48`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x1800254c0`
- `0x180025f70`
- `0x1800265b8`
- `0x1800269d0`
- `0x180026a0c`
- `0x1800597c0`
- `0x180071f50`
- `0x1800992c4`
- `0x1800992d0`
- `0x18009d3d0`
- `0x1801051e4`
- `0x180106010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002566b`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18002566b`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002577e`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18002577e`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025582`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002564c`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025582`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18002564c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800255de`
- `OLEAUT32!__imp_SysFreeString` at `0x1800256a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002590a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800256a5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800257f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002590a`

## string_xrefs

- `0x1800254e4`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`
- `0x18002553b`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::PackageReaderHelper::MatchFileInfoWithBlockMapData(
        __int64 a1,
        struct _RTL_AVL_TABLE *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rsi
  Appx::Packaging::BlockMap::AppxBlockMapFile *v9; // r13
  const unsigned __int16 *v10; // rsi
  Appx::Packaging::FileNameHelper *v11; // rdi
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  _QWORD *v15; // rax
  __int64 *v16; // rsi
  Appx::Packaging::Consumption::AppxFileInfo *v17; // rax
  Appx::Packaging::Consumption::AppxFileInfo *v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int64 *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rsi
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rax
  struct IOpcPartUri *v29; // rcx
  int v30; // eax
  enum APPX_COMPRESSION_OPTION v31; // r8d
  int v32; // eax
  unsigned int v33; // edx
  Appx::Packaging::Consumption::AppxFileInfo **v34; // rax
  unsigned int v35; // edx
  Appx::Packaging::Consumption::AppxFileInfo **v36; // rbx
  Appx::Packaging::Consumption::AppxFileInfo *v37; // rcx
  __int64 v38; // rcx
  unsigned __int64 v39; // rax
  PVOID v40; // rax
  struct IOpcPartUri *v41; // rcx
  __int64 v43; // r9
  __int64 v44; // rdx
  unsigned __int64 v45; // rdi
  void *v46; // rax
  void *v47; // rsi
  unsigned __int64 v48; // rdx
  struct IOpcPartUri *v49; // rcx
  unsigned int v50; // edi
  BSTR bstrString; // [rsp+20h] [rbp-30h] BYREF
  _QWORD Buffer[2]; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v53[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  struct IOpcPartUri *v57; // [rsp+A0h] [rbp+50h] BYREF

  v6 = a1;
  v7 = 0;
  while ( 1 )
  {
    if ( !*(_BYTE *)(a3 + 24) )
    {
LABEL_67:
      if ( (v7 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D1,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
          (const char *)v7,
          (int)bstrString);
      return v7;
    }
    v8 = *(_QWORD *)(a3 + 16);
    v9 = *(Appx::Packaging::BlockMap::AppxBlockMapFile **)(v8 + 8);
    if ( !*((_BYTE *)v9 + 136) )
      break;
LABEL_36:
    if ( !*(_BYTE *)(a3 + 24) )
      goto LABEL_67;
    v40 = RtlEnumerateGenericTableWithoutSplayingAvl(*(PRTL_AVL_TABLE *)a3, (PVOID *)(a3 + 8));
    *(_QWORD *)(a3 + 16) = v40;
    *(_BYTE *)(a3 + 24) = v40 != 0;
    v6 = a1;
  }
  v10 = *(const unsigned __int16 **)v8;
  v11 = *(Appx::Packaging::FileNameHelper **)(v6 + 8);
  v57 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
  v12 = Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(v11, v10, &v57);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
      (const char *)(unsigned int)v12,
      (int)bstrString);
    v41 = v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(struct IOpcPartUri *))v41->lpVtbl->Release)(v41);
    }
    goto LABEL_43;
  }
  bstrString = 0;
  v14 = ((__int64 (__fastcall *)(struct IOpcPartUri *, BSTR *))v57->lpVtbl->GetAbsoluteUri)(v57, &bstrString);
  v13 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
      (const char *)(unsigned int)v14,
      (int)bstrString);
    goto LABEL_42;
  }
  Buffer[0] = bstrString;
  Buffer[1] = 0;
  v15 = RtlLookupElementGenericTableAvl(a2, Buffer);
  if ( !v15 || (v16 = (__int64 *)v15[1]) == 0 )
  {
    SysFreeString(bstrString);
    v49 = v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(struct IOpcPartUri *))v49->lpVtbl->Release)(v49);
    }
    v13 = -2146958843;
    goto LABEL_43;
  }
  v17 = (Appx::Packaging::Consumption::AppxFileInfo *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( !v17 )
  {
    v13 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
      (const char *)0x8007000ELL,
      (int)bstrString);
    Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(0);
LABEL_42:
    SysFreeString(bstrString);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
LABEL_43:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
      (const char *)v13,
      (int)bstrString);
    return v13;
  }
  *(_QWORD *)v17 = 0;
  *((_QWORD *)v17 + 6) = 0;
  *((_DWORD *)v17 + 2) = *((_DWORD *)v16 + 2);
  v19 = *v16;
  *v16 = 0;
  if ( *(_QWORD *)v17 != v19 )
  {
    CoTaskMemFree(*(LPVOID *)v17);
    *(_QWORD *)v18 = v19;
  }
  v20 = v16[6];
  if ( *((_QWORD *)v18 + 6) != v20 )
  {
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v16[6]);
    v21 = *((_QWORD *)v18 + 6);
    *((_QWORD *)v18 + 6) = v20;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = *((_OWORD *)v16 + 1);
  v23 = *((_OWORD *)v16 + 2);
  v53[1] = 0;
  *((_OWORD *)v18 + 1) = v22;
  *((_OWORD *)v18 + 2) = v23;
  v53[0] = bstrString;
  v24 = (__int64 *)RtlLookupElementGenericTableAvl(a2, v53);
  if ( v24 )
  {
    v25 = *v24;
    v26 = v24[1];
    RtlDeleteElementGenericTableAvl(a2, v24);
    Parent = a2[1].BalancedRoot.Parent;
    if ( Parent )
      ((void (__fastcall *)(__int64))Parent)(v25);
    LeftChild = a2[1].BalancedRoot.LeftChild;
    if ( LeftChild )
      ((void (__fastcall *)(__int64))LeftChild)(v26);
  }
  SysFreeString(bstrString);
  v29 = v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(struct IOpcPartUri *))v29->lpVtbl->Release)(v29);
  }
  v30 = *((_DWORD *)v18 + 2);
  if ( v30 == -1 )
  {
    v31 = APPX_COMPRESSION_OPTION_NONE;
  }
  else if ( v30 )
  {
    switch ( v30 )
    {
      case 1:
        v31 = APPX_COMPRESSION_OPTION_MAXIMUM;
        break;
      case 2:
        v31 = APPX_COMPRESSION_OPTION_FAST;
        break;
      case 3:
        v31 = APPX_COMPRESSION_OPTION_SUPERFAST;
        break;
      default:
        v7 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x264,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\util.cpp",
          (const char *)0x8000FFFFLL,
          (int)bstrString);
        v43 = 2147549183LL;
        v44 = 450;
LABEL_45:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
          (const char *)v43,
          (int)bstrString);
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(v18);
        return v7;
    }
  }
  else
  {
    v31 = APPX_COMPRESSION_OPTION_NORMAL;
  }
  v32 = Appx::Packaging::BlockMap::AppxBlockMapFile::MergeFileData(
          v9,
          (Appx::Packaging::Consumption::AppxFileInfo *)((char *)v18 + 16),
          v31);
  v7 = v32;
  if ( v32 < 0 )
  {
    v43 = (unsigned int)v32;
    v44 = 451;
    goto LABEL_45;
  }
  if ( !a4 )
  {
    Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(v18, v33);
    goto LABEL_36;
  }
  v34 = (Appx::Packaging::Consumption::AppxFileInfo **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v36 = v34;
  if ( v34 )
    *v34 = 0;
  else
    v36 = 0;
  v37 = *v36;
  if ( *v36 != v18 )
  {
    if ( v37 )
      Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(v37, v35);
    *v36 = v18;
  }
  v36[1] = v9;
  v38 = *(_QWORD *)(a4 + 16);
  v39 = *(_QWORD *)(a4 + 8);
  if ( v38 + 1 <= v39 )
  {
LABEL_35:
    *(_QWORD *)(*(_QWORD *)a4 + 8 * v38) = v36;
    ++*(_QWORD *)(a4 + 16);
    v7 = 0;
    goto LABEL_36;
  }
  if ( v39 != 0x3FFFFFFF )
  {
    if ( v39 )
      v45 = ((3 * v39) >> 1) + 1;
    else
      v45 = 16;
    if ( v38 + 1 > v45 )
      v45 = v38 + 1;
    if ( v45 > 0x3FFFFFFF )
      v45 = 0x3FFFFFFF;
    v46 = operator new[](8 * v45, (const struct std::nothrow_t *)&std::nothrow);
    v47 = v46;
    if ( !v46 )
    {
      v50 = -2147024882;
      goto LABEL_76;
    }
    if ( *(_QWORD *)a4 )
    {
      memmove_0(v46, *(const void **)a4, 8LL * *(_QWORD *)(a4 + 16));
      operator delete(*(void **)a4, v48);
    }
    v38 = *(_QWORD *)(a4 + 16);
    *(_QWORD *)a4 = v47;
    *(_QWORD *)(a4 + 8) = v45;
    goto LABEL_35;
  }
  v50 = -2147483637;
LABEL_76:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1CA,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
    (const char *)v50,
    (int)bstrString);
  Common::AutoPtrDeallocate<Appx::Packaging::Consumption::PackageReaderHelper::MatchedFile>(v36);
  Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(0);
  return v50;
}

```

## disassembly

```asm
0x1800254c0  mov     [rsp-38h+arg_18], rbx
0x1800254c5  mov     [rsp-38h+Table], rdx
0x1800254ca  mov     [rsp-38h+arg_0], rcx
0x1800254cf  push    rbp
0x1800254d0  push    rsi
0x1800254d1  push    rdi
0x1800254d2  push    r12
0x1800254d4  push    r13
0x1800254d6  push    r14
0x1800254d8  push    r15
0x1800254da  mov     rbp, rsp
0x1800254dd  sub     rsp, 50h
0x1800254e1  mov     r15, r9
0x1800254e4  lea     r14, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x1800254eb  mov     r12, r8
0x1800254ee  mov     rax, rcx
0x1800254f1  xor     ebx, ebx
0x1800254f3  cmp     byte ptr [r12+18h], 0
0x1800254f9  jz      loc_18002595E
0x1800254ff  mov     rsi, [r12+10h]
0x180025504  mov     r13, [rsi+8]
0x180025508  cmp     byte ptr [r13+88h], 0
0x180025510  jnz     loc_180025769
0x180025516  mov     rsi, [rsi]
0x180025519  lea     rcx, [rbp+arg_10]
0x18002551d  mov     rdi, [rax+8]
0x180025521  xor     ebx, ebx
0x180025523  mov     [rbp+arg_10], rbx
0x180025527  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18002552c  lea     r8, [rbp+arg_10]; struct IOpcPartUri **
0x180025530  mov     rdx, rsi; unsigned __int16 *
0x180025533  mov     rcx, rdi; this
0x180025536  call    ?CreatePartUriWithoutValidation@FileNameHelper@Packaging@Appx@@QEAAJPEBGPEAPEAUIOpcPartUri@@@Z; Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(ushort const *,IOpcPartUri * *)
0x18002553b  lea     r14, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180025542  mov     edi, eax
0x180025544  test    eax, eax
0x180025546  js      loc_1800257AB
0x18002554c  mov     rcx, [rbp+arg_10]
0x180025550  lea     rdx, [rbp+bstrString]
0x180025554  mov     [rbp+bstrString], rbx
0x180025558  mov     rax, [rcx]
0x18002555b  mov     rax, [rax+38h]
0x18002555f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025564  mov     edi, eax
0x180025566  test    eax, eax
0x180025568  js      loc_1800257DA
0x18002556e  mov     rax, [rbp+bstrString]
0x180025572  lea     rdx, [rbp+Buffer]; Buffer
0x180025576  mov     rcx, [rbp+Table]; Table
0x18002557a  mov     [rbp+Buffer], rax
0x18002557e  mov     [rbp+var_20], rbx
0x180025582  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180025589  nop     dword ptr [rax+rax+00h]
0x18002558e  test    rax, rax
0x180025591  jz      loc_180025906
0x180025597  mov     rsi, [rax+8]
0x18002559b  test    rsi, rsi
0x18002559e  jz      loc_180025906
0x1800255a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800255ab  lea     ecx, [rbx+38h]; unsigned __int64
0x1800255ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800255b3  mov     rdi, rax
0x1800255b6  test    rax, rax
0x1800255b9  jz      loc_180025862
0x1800255bf  mov     [rax], rbx
0x1800255c2  mov     [rax+30h], rbx
0x1800255c6  mov     eax, [rsi+8]
0x1800255c9  mov     [rdi+8], eax
0x1800255cc  mov     rbx, [rsi]
0x1800255cf  mov     qword ptr [rsi], 0
0x1800255d6  cmp     [rdi], rbx
0x1800255d9  jz      short loc_1800255ED
0x1800255db  mov     rcx, [rdi]; pv
0x1800255de  call    cs:__imp_CoTaskMemFree
0x1800255e5  nop     dword ptr [rax+rax+00h]
0x1800255ea  mov     [rdi], rbx
0x1800255ed  mov     rbx, [rsi+30h]
0x1800255f1  cmp     [rdi+30h], rbx
0x1800255f5  jz      short loc_180025624
0x1800255f7  test    rbx, rbx
0x1800255fa  jz      short loc_18002560B
0x1800255fc  mov     rax, [rbx]
0x1800255ff  mov     rcx, rbx
0x180025602  mov     rax, [rax+8]
0x180025606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002560b  mov     rcx, [rdi+30h]
0x18002560f  mov     [rdi+30h], rbx
0x180025613  test    rcx, rcx
0x180025616  jz      short loc_180025624
0x180025618  mov     rax, [rcx]
0x18002561b  mov     rax, [rax+10h]
0x18002561f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025624  movups  xmm0, xmmword ptr [rsi+10h]
0x180025628  mov     rcx, [rbp+Table]; Table
0x18002562c  lea     rdx, [rbp+var_18]; Buffer
0x180025630  movups  xmm1, xmmword ptr [rsi+20h]
0x180025634  mov     [rbp+var_10], 0
0x18002563c  movups  xmmword ptr [rdi+10h], xmm0
0x180025640  movups  xmmword ptr [rdi+20h], xmm1
0x180025644  mov     rax, [rbp+bstrString]
0x180025648  mov     [rbp+var_18], rax
0x18002564c  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180025653  nop     dword ptr [rax+rax+00h]
0x180025658  test    rax, rax
0x18002565b  jz      short loc_1800256A1
0x18002565d  mov     rcx, [rbp+Table]; Table
0x180025661  mov     rdx, rax; Buffer
0x180025664  mov     rbx, [rax]
0x180025667  mov     rsi, [rax+8]
0x18002566b  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180025672  nop     dword ptr [rax+rax+00h]
0x180025677  mov     rcx, [rbp+Table]
0x18002567b  mov     rax, [rcx+68h]
0x18002567f  test    rax, rax
0x180025682  jz      short loc_18002568C
0x180025684  mov     rcx, rbx
0x180025687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002568c  mov     rax, [rbp+Table]
0x180025690  mov     rax, [rax+70h]
0x180025694  test    rax, rax
0x180025697  jz      short loc_1800256A1
0x180025699  mov     rcx, rsi
0x18002569c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256a1  mov     rcx, [rbp+bstrString]; bstrString
0x1800256a5  call    cs:__imp_SysFreeString
0x1800256ac  nop     dword ptr [rax+rax+00h]
0x1800256b1  mov     rcx, [rbp+arg_10]
0x1800256b5  test    rcx, rcx
0x1800256b8  jz      short loc_1800256CE
0x1800256ba  mov     [rbp+arg_10], 0
0x1800256c2  mov     rax, [rcx]
0x1800256c5  mov     rax, [rax+10h]
0x1800256c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256ce  mov     eax, [rdi+8]
0x1800256d1  cmp     eax, 0FFFFFFFFh
0x1800256d4  jz      loc_1800257A3
0x1800256da  test    eax, eax
0x1800256dc  jnz     loc_180025946
0x1800256e2  lea     r8d, [rax+1]; enum APPX_COMPRESSION_OPTION
0x1800256e6  lea     rdx, [rdi+10h]; struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *
0x1800256ea  mov     rcx, r13; this
0x1800256ed  call    ?MergeFileData@AppxBlockMapFile@BlockMap@Packaging@Appx@@QEAAJAEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::BlockMap::AppxBlockMapFile::MergeFileData(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const &,APPX_COMPRESSION_OPTION)
0x1800256f2  mov     ebx, eax
0x1800256f4  test    eax, eax
0x1800256f6  js      loc_180025842
0x1800256fc  test    r15, r15
0x1800256ff  jz      loc_180025939
0x180025705  mov     esi, 10h
0x18002570a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025711  mov     ecx, esi; unsigned __int64
0x180025713  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025718  mov     rbx, rax
0x18002571b  test    rax, rax
0x18002571e  jz      loc_18002597F
0x180025724  mov     qword ptr [rax], 0
0x18002572b  mov     rcx, [rbx]; this
0x18002572e  cmp     rcx, rdi
0x180025731  jz      short loc_18002573F
0x180025733  test    rcx, rcx
0x180025736  jnz     loc_180025838
0x18002573c  mov     [rbx], rdi
0x18002573f  mov     [rbx+8], r13
0x180025743  mov     rcx, [r15+10h]
0x180025747  mov     rax, [r15+8]
0x18002574b  lea     rdx, [rcx+1]
0x18002574f  cmp     rdx, rax
0x180025752  ja      loc_180025887
0x180025758  mov     rax, [r15]
0x18002575b  mov     [rax+rcx*8], rbx
0x18002575f  inc     qword ptr [r15+10h]
0x180025763  xor     ebx, ebx
0x180025765  mov     rax, [rbp+arg_0]
0x180025769  cmp     byte ptr [r12+18h], 0
0x18002576f  jz      loc_18002595E
0x180025775  mov     rcx, [r12]; Table
0x180025779  lea     rdx, [r12+8]; RestartKey
0x18002577e  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180025785  nop     dword ptr [rax+rax+00h]
0x18002578a  test    rax, rax
0x18002578d  mov     [r12+10h], rax
0x180025792  setnz   al
0x180025795  mov     [r12+18h], al
0x18002579a  mov     rax, [rbp+arg_0]
0x18002579e  jmp     loc_1800254F3
0x1800257a3  xor     r8d, r8d
0x1800257a6  jmp     loc_1800256E6
0x1800257ab  mov     rcx, [rbp+38h]; this
0x1800257af  mov     r9d, edi; char *
0x1800257b2  mov     r8, r14; unsigned int
0x1800257b5  mov     edx, 100h; void *
0x1800257ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800257bf  mov     rcx, [rbp+arg_10]
0x1800257c3  test    rcx, rcx
0x1800257c6  jz      short loc_180025807
0x1800257c8  mov     [rbp+arg_10], rbx
0x1800257cc  mov     rax, [rcx]
0x1800257cf  mov     rax, [rax+10h]
0x1800257d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257d8  jmp     short loc_180025807
0x1800257da  mov     rcx, [rbp+38h]; this
0x1800257de  mov     r9d, edi; char *
0x1800257e1  mov     r8, r14; unsigned int
0x1800257e4  mov     edx, 102h; void *
0x1800257e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800257ee  mov     rcx, [rbp+bstrString]; bstrString
0x1800257f2  call    cs:__imp_SysFreeString
0x1800257f9  nop     dword ptr [rax+rax+00h]
0x1800257fe  lea     rcx, [rbp+arg_10]
0x180025802  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180025807  mov     rcx, [rbp+38h]; this
0x18002580b  mov     r9d, edi; char *
0x18002580e  mov     r8, r14; unsigned int
0x180025811  mov     edx, 1BEh; void *
0x180025816  mov     esi, edi
0x180025818  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002581d  mov     eax, edi
0x18002581f  mov     rbx, [rsp+50h+arg_18]
0x180025827  add     rsp, 50h
0x18002582b  pop     r15
0x18002582d  pop     r14
0x18002582f  pop     r13
0x180025831  pop     r12
0x180025833  pop     rdi
0x180025834  pop     rsi
0x180025835  pop     rbp
0x180025836  retn
0x180025838  call    ??_GAppxFileInfo@Consumption@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(uint)
0x18002583d  jmp     loc_18002573C
0x180025842  mov     r9d, eax; char *
0x180025845  mov     edx, 1C3h; void *
0x18002584a  mov     rcx, [rbp+38h]; this
0x18002584e  mov     r8, r14; unsigned int
0x180025851  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025856  mov     rcx, rdi
0x180025859  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x18002585e  mov     eax, ebx
0x180025860  jmp     short loc_18002581F
0x180025862  mov     rcx, [rbp+38h]; this
0x180025866  mov     edi, 8007000Eh
0x18002586b  mov     r9d, edi; char *
0x18002586e  mov     r8, r14; unsigned int
0x180025871  mov     edx, 10Fh; void *
0x180025876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002587b  xor     ecx, ecx
0x18002587d  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x180025882  jmp     loc_1800257EE
0x180025887  mov     ecx, 3FFFFFFFh
0x18002588c  cmp     rax, rcx
0x18002588f  jz      loc_1800259D5
0x180025895  test    rax, rax
0x180025898  jz      loc_180025991
0x18002589e  lea     rdi, [rax+rax*2]
0x1800258a2  shr     rdi, 1
0x1800258a5  inc     rdi
0x1800258a8  cmp     rdx, rdi
0x1800258ab  cmova   rdi, rdx
0x1800258af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800258b6  cmp     rdi, rcx
0x1800258b9  cmova   rdi, rcx
0x1800258bd  lea     rcx, ds:0[rdi*8]; unsigned __int64
0x1800258c5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800258ca  mov     rsi, rax
0x1800258cd  test    rax, rax
0x1800258d0  jz      loc_1800259CE
0x1800258d6  mov     rdx, [r15]; Src
0x1800258d9  test    rdx, rdx
0x1800258dc  jz      short loc_1800258F6
0x1800258de  mov     r8, [r15+10h]
0x1800258e2  mov     rcx, rax; void *
0x1800258e5  shl     r8, 3; Size
0x1800258e9  call    memmove_0
0x1800258ee  mov     rcx, [r15]; void *
0x1800258f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800258f6  mov     rcx, [r15+10h]
0x1800258fa  mov     [r15], rsi
0x1800258fd  mov     [r15+8], rdi
0x180025901  jmp     loc_180025758
0x180025906  mov     rcx, [rbp+bstrString]; bstrString
0x18002590a  call    cs:__imp_SysFreeString
0x180025911  nop     dword ptr [rax+rax+00h]
0x180025916  mov     rcx, [rbp+arg_10]
0x18002591a  test    rcx, rcx
0x18002591d  jz      short loc_18002592F
0x18002591f  mov     [rbp+arg_10], rbx
0x180025923  mov     rax, [rcx]
0x180025926  mov     rax, [rax+10h]
0x18002592a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002592f  mov     edi, 80080205h
0x180025934  jmp     loc_180025807
0x180025939  mov     rcx, rdi; this
0x18002593c  call    ??_GAppxFileInfo@Consumption@Packaging@Appx@@QEAAPEAXI@Z; Appx::Packaging::Consumption::AppxFileInfo::`scalar deleting destructor'(uint)
0x180025941  jmp     loc_180025765
0x180025946  cmp     eax, 1
0x180025949  jz      short loc_180025986
0x18002594b  cmp     eax, 2
0x18002594e  jz      short loc_180025999
0x180025950  cmp     eax, 3
0x180025953  jnz     short loc_1800259A4
0x180025955  lea     r8d, [rax+1]
0x180025959  jmp     loc_1800256E6
  ... truncated ...
```

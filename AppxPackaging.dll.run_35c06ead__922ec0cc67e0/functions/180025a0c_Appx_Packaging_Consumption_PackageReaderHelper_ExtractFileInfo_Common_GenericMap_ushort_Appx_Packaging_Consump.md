# Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,ushort const *,bool,long,Appx::Packaging::Consumption::AppxFileInfo * *)

- ea: `0x180025a0c`
- end: `0x180025cf5`
- name: `?ExtractFileInfo@PackageReaderHelper@Consumption@Packaging@Appx@@QEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@PEBG_NJPEAPEAUAppxFileInfo@234@@Z`
- size: `745`
- prototype: `__int64 __fastcall(__int64, struct _RTL_AVL_TABLE *, const unsigned __int16 *, char, unsigned int, struct IOpcPartUri *)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001aa64`
- `0x180024608`
- `0x1800c8800`
- `0x1800cefd4`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180025a0c`
- `0x180025f70`
- `0x1800269d0`
- `0x180071f50`
- `0x1800992d0`
- `0x180106010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025bf0`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180025bf0`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025aa6`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025bce`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025aa6`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180025bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025b5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025cc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180025ad5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c7f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025cc4`

## string_xrefs

- `0x180025c2b`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`
- `0x180025c67`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`
- `0x180025c9d`: `onecore\printscan\appxpackaging\consumption\src\packagereaderhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::Consumption::PackageReaderHelper::ExtractFileInfo(
        __int64 a1,
        struct _RTL_AVL_TABLE *a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned int a5,
        struct IOpcPartUri *a6)
{
  struct IOpcPartUri *v6; // r12
  Appx::Packaging::FileNameHelper *v10; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // r14d
  _QWORD *v15; // rax
  struct IOpcPartUriVtbl *v16; // rdi
  struct IOpcPartUri *v17; // rcx
  HRESULT (__stdcall **v19)(IOpcPartUri *, const IID *const, void **); // rax
  HRESULT (__stdcall **v20)(IOpcPartUri *, const IID *const, void **); // rbx
  HRESULT (__stdcall *QueryInterface)(IOpcPartUri *, const IID *const, void **); // rsi
  HRESULT (__stdcall *HasProperty)(IOpcPartUri *, Uri_PROPERTY, BOOL *); // rsi
  HRESULT (__stdcall *v23)(IOpcPartUri *, const IID *const, void **); // rcx
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int64 *v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rbx
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rax
  struct IOpcPartUri *v31; // rcx
  struct IOpcPartUri *v32; // rcx
  BSTR Buffer; // [rsp+20h] [rbp-10h] BYREF
  __int64 v34; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  BSTR bstrString; // [rsp+60h] [rbp+30h] BYREF

  v6 = a6;
  a6 = 0;
  v6->lpVtbl = 0;
  v10 = *(Appx::Packaging::FileNameHelper **)(a1 + 8);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a6);
  v11 = Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(v10, a3, &a6);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
      (const char *)(unsigned int)v11,
      (int)Buffer);
    v31 = a6;
    if ( a6 )
    {
      a6 = 0;
      ((void (__fastcall *)(struct IOpcPartUri *))v31->lpVtbl->Release)(v31);
    }
    return v12;
  }
  else
  {
    bstrString = 0;
    v13 = ((__int64 (__fastcall *)(struct IOpcPartUri *, BSTR *))a6->lpVtbl->GetAbsoluteUri)(a6, &bstrString);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
        (const char *)(unsigned int)v13,
        (int)Buffer);
      goto LABEL_27;
    }
    Buffer = bstrString;
    v34 = 0;
    v15 = RtlLookupElementGenericTableAvl(a2, &Buffer);
    if ( v15 )
    {
      v16 = (struct IOpcPartUriVtbl *)v15[1];
      if ( v16 )
      {
        if ( !a4 )
        {
          v6->lpVtbl = v16;
LABEL_7:
          SysFreeString(bstrString);
          v17 = a6;
          if ( a6 )
          {
            a6 = 0;
            ((void (__fastcall *)(struct IOpcPartUri *))v17->lpVtbl->Release)(v17);
          }
          return v14;
        }
        v19 = (HRESULT (__stdcall **)(IOpcPartUri *, const IID *const, void **))operator new(
                                                                                  0x38u,
                                                                                  (const struct std::nothrow_t *)&std::nothrow);
        v20 = v19;
        if ( v19 )
        {
          *v19 = 0;
          v19[6] = 0;
          *((_DWORD *)v19 + 2) = v16->AddRef;
          QueryInterface = v16->QueryInterface;
          v16->QueryInterface = 0;
          if ( *v19 != QueryInterface )
          {
            CoTaskMemFree(*v19);
            *v20 = QueryInterface;
          }
          HasProperty = v16->HasProperty;
          if ( (char *)v20[6] != (char *)HasProperty )
          {
            if ( HasProperty )
              (*(void (__fastcall **)(HRESULT (__stdcall *)(IOpcPartUri *, Uri_PROPERTY, BOOL *)))(*(_QWORD *)HasProperty
                                                                                                 + 8LL))(v16->HasProperty);
            v23 = v20[6];
            v20[6] = (HRESULT (__stdcall *)(IOpcPartUri *, const IID *const, void **))HasProperty;
            if ( v23 )
              (*(void (__fastcall **)(HRESULT (__stdcall *)(IOpcPartUri *, const IID *const, void **)))(*(_QWORD *)v23 + 16LL))(v23);
          }
          v24 = *(_OWORD *)&v16->Release;
          v25 = *(_OWORD *)&v16->GetPropertyLength;
          v34 = 0;
          *((_OWORD *)v20 + 1) = v24;
          *((_OWORD *)v20 + 2) = v25;
          Buffer = bstrString;
          v6->lpVtbl = (struct IOpcPartUriVtbl *)v20;
          v26 = (__int64 *)RtlLookupElementGenericTableAvl(a2, &Buffer);
          if ( v26 )
          {
            v27 = *v26;
            v28 = v26[1];
            RtlDeleteElementGenericTableAvl(a2, v26);
            Parent = a2[1].BalancedRoot.Parent;
            if ( Parent )
              ((void (__fastcall *)(__int64))Parent)(v27);
            LeftChild = a2[1].BalancedRoot.LeftChild;
            if ( LeftChild )
              ((void (__fastcall *)(__int64))LeftChild)(v28);
          }
          goto LABEL_7;
        }
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\packagereaderhelper.cpp",
          (const char *)0x8007000ELL,
          (int)Buffer);
        Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(0);
LABEL_27:
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a6);
        return v14;
      }
    }
    SysFreeString(bstrString);
    v32 = a6;
    if ( a6 )
    {
      a6 = 0;
      ((void (__fastcall *)(struct IOpcPartUri *))v32->lpVtbl->Release)(v32);
    }
    return a5;
  }
}

```

## disassembly

```asm
0x180025a0c  mov     [rsp-28h+arg_8], rbx
0x180025a11  mov     [rsp-28h+arg_10], rsi
0x180025a16  push    rbp
0x180025a17  push    rdi
0x180025a18  push    r12
0x180025a1a  push    r14
0x180025a1c  push    r15
0x180025a1e  mov     rbp, rsp
0x180025a21  sub     rsp, 30h
0x180025a25  mov     r12, [rbp+arg_28]
0x180025a29  mov     sil, r9b
0x180025a2c  mov     rdi, r8
0x180025a2f  mov     [rbp+arg_28], 0
0x180025a37  mov     r15, rdx
0x180025a3a  mov     qword ptr [r12], 0
0x180025a42  mov     rbx, [rcx+8]
0x180025a46  lea     rcx, [rbp+arg_28]
0x180025a4a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180025a4f  lea     r8, [rbp+arg_28]; struct IOpcPartUri **
0x180025a53  mov     rdx, rdi; unsigned __int16 *
0x180025a56  mov     rcx, rbx; this
0x180025a59  call    ?CreatePartUriWithoutValidation@FileNameHelper@Packaging@Appx@@QEAAJPEBGPEAPEAUIOpcPartUri@@@Z; Appx::Packaging::FileNameHelper::CreatePartUriWithoutValidation(ushort const *,IOpcPartUri * *)
0x180025a5e  mov     ebx, eax
0x180025a60  test    eax, eax
0x180025a62  js      loc_180025C27
0x180025a68  mov     rcx, [rbp+arg_28]
0x180025a6c  lea     rdx, [rbp+bstrString]
0x180025a70  mov     [rbp+bstrString], 0
0x180025a78  mov     rax, [rcx]
0x180025a7b  mov     rax, [rax+38h]
0x180025a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a84  mov     r14d, eax
0x180025a87  test    eax, eax
0x180025a89  js      loc_180025C63
0x180025a8f  mov     rax, [rbp+bstrString]
0x180025a93  lea     rdx, [rbp+Buffer]; Buffer
0x180025a97  mov     rcx, r15; Table
0x180025a9a  mov     [rbp+Buffer], rax
0x180025a9e  mov     [rbp+var_8], 0
0x180025aa6  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180025aad  nop     dword ptr [rax+rax+00h]
0x180025ab2  test    rax, rax
0x180025ab5  jz      loc_180025CC0
0x180025abb  mov     rdi, [rax+8]
0x180025abf  test    rdi, rdi
0x180025ac2  jz      loc_180025CC0
0x180025ac8  test    sil, sil
0x180025acb  jnz     short loc_180025B19
0x180025acd  mov     [r12], rdi
0x180025ad1  mov     rcx, [rbp+bstrString]; bstrString
0x180025ad5  call    cs:__imp_SysFreeString
0x180025adc  nop     dword ptr [rax+rax+00h]
0x180025ae1  mov     rcx, [rbp+arg_28]
0x180025ae5  test    rcx, rcx
0x180025ae8  jz      short loc_180025AFE
0x180025aea  mov     [rbp+arg_28], 0
0x180025af2  mov     rax, [rcx]
0x180025af5  mov     rax, [rax+10h]
0x180025af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025afe  mov     eax, r14d
0x180025b01  mov     rbx, [rsp+30h+arg_8]
0x180025b06  mov     rsi, [rsp+30h+arg_10]
0x180025b0b  add     rsp, 30h
0x180025b0f  pop     r15
0x180025b11  pop     r14
0x180025b13  pop     r12
0x180025b15  pop     rdi
0x180025b16  pop     rbp
0x180025b17  retn
0x180025b19  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180025b20  mov     ecx, 38h ; '8'; unsigned __int64
0x180025b25  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025b2a  mov     rbx, rax
0x180025b2d  test    rax, rax
0x180025b30  jz      loc_180025C99
0x180025b36  mov     qword ptr [rax], 0
0x180025b3d  mov     qword ptr [rax+30h], 0
0x180025b45  mov     ecx, [rdi+8]
0x180025b48  mov     [rax+8], ecx
0x180025b4b  mov     rsi, [rdi]
0x180025b4e  mov     qword ptr [rdi], 0
0x180025b55  cmp     [rax], rsi
0x180025b58  jz      short loc_180025B6C
0x180025b5a  mov     rcx, [rax]; pv
0x180025b5d  call    cs:__imp_CoTaskMemFree
0x180025b64  nop     dword ptr [rax+rax+00h]
0x180025b69  mov     [rbx], rsi
0x180025b6c  mov     rsi, [rdi+30h]
0x180025b70  cmp     [rbx+30h], rsi
0x180025b74  jz      short loc_180025BA3
0x180025b76  test    rsi, rsi
0x180025b79  jz      short loc_180025B8A
0x180025b7b  mov     rax, [rsi]
0x180025b7e  mov     rcx, rsi
0x180025b81  mov     rax, [rax+8]
0x180025b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b8a  mov     rcx, [rbx+30h]
0x180025b8e  mov     [rbx+30h], rsi
0x180025b92  test    rcx, rcx
0x180025b95  jz      short loc_180025BA3
0x180025b97  mov     rax, [rcx]
0x180025b9a  mov     rax, [rax+10h]
0x180025b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba3  movups  xmm0, xmmword ptr [rdi+10h]
0x180025ba7  lea     rdx, [rbp+Buffer]; Buffer
0x180025bab  mov     rcx, r15; Table
0x180025bae  movups  xmm1, xmmword ptr [rdi+20h]
0x180025bb2  mov     [rbp+var_8], 0
0x180025bba  movups  xmmword ptr [rbx+10h], xmm0
0x180025bbe  movups  xmmword ptr [rbx+20h], xmm1
0x180025bc2  mov     rax, [rbp+bstrString]
0x180025bc6  mov     [rbp+Buffer], rax
0x180025bca  mov     [r12], rbx
0x180025bce  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180025bd5  nop     dword ptr [rax+rax+00h]
0x180025bda  test    rax, rax
0x180025bdd  jz      loc_180025AD1
0x180025be3  mov     rdi, [rax]
0x180025be6  mov     rdx, rax; Buffer
0x180025be9  mov     rbx, [rax+8]
0x180025bed  mov     rcx, r15; Table
0x180025bf0  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180025bf7  nop     dword ptr [rax+rax+00h]
0x180025bfc  mov     rax, [r15+68h]
0x180025c00  test    rax, rax
0x180025c03  jz      short loc_180025C0D
0x180025c05  mov     rcx, rdi
0x180025c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c0d  mov     rax, [r15+70h]
0x180025c11  test    rax, rax
0x180025c14  jz      loc_180025AD1
0x180025c1a  mov     rcx, rbx
0x180025c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c22  jmp     loc_180025AD1
0x180025c27  mov     rcx, [rbp+28h]; this
0x180025c2b  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180025c32  mov     r9d, ebx; char *
0x180025c35  mov     edx, 100h; void *
0x180025c3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025c3f  mov     rcx, [rbp+arg_28]
0x180025c43  test    rcx, rcx
0x180025c46  jz      short loc_180025C5C
0x180025c48  mov     [rbp+arg_28], 0
0x180025c50  mov     rax, [rcx]
0x180025c53  mov     rax, [rax+10h]
0x180025c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c5c  mov     eax, ebx
0x180025c5e  jmp     loc_180025B01
0x180025c63  mov     rcx, [rbp+28h]; this
0x180025c67  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180025c6e  mov     r9d, r14d; char *
0x180025c71  mov     edx, 102h; void *
0x180025c76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025c7b  mov     rcx, [rbp+bstrString]; bstrString
0x180025c7f  call    cs:__imp_SysFreeString
0x180025c86  nop     dword ptr [rax+rax+00h]
0x180025c8b  lea     rcx, [rbp+arg_28]
0x180025c8f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180025c94  jmp     loc_180025AFE
0x180025c99  mov     rcx, [rbp+28h]; this
0x180025c9d  lea     r8, aOnecorePrintsc_43; "onecore\\printscan\\appxpackaging\\cons"...
0x180025ca4  mov     r14d, 8007000Eh
0x180025caa  mov     edx, 10Fh; void *
0x180025caf  mov     r9d, r14d; char *
0x180025cb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025cb7  xor     ecx, ecx
0x180025cb9  call    ??$AutoPtrDeallocate@UAppxFileInfo@Consumption@Packaging@Appx@@@Common@@YAXPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::Consumption::AppxFileInfo>(Appx::Packaging::Consumption::AppxFileInfo *)
0x180025cbe  jmp     short loc_180025C7B
0x180025cc0  mov     rcx, [rbp+bstrString]; bstrString
0x180025cc4  call    cs:__imp_SysFreeString
0x180025ccb  nop     dword ptr [rax+rax+00h]
0x180025cd0  mov     rcx, [rbp+arg_28]
0x180025cd4  test    rcx, rcx
0x180025cd7  jz      short loc_180025CED
0x180025cd9  mov     [rbp+arg_28], 0
0x180025ce1  mov     rax, [rcx]
0x180025ce4  mov     rax, [rax+10h]
0x180025ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ced  mov     eax, [rbp+arg_20]
0x180025cf0  jmp     loc_180025B01
```

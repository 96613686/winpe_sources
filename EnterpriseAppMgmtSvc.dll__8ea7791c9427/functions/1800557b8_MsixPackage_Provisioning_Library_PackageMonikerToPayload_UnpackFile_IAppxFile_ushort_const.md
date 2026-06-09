# MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile(IAppxFile *,ushort const *)

- ea: `0x1800557b8`
- end: `0x180055e6d`
- name: `?UnpackFile@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@AEAAJPEAUIAppxFile@@PEBG@Z`
- size: `1717`
- prototype: `int(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, struct IAppxFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180054cdc`

## callees

- `0x18001bf0c`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003f6d8`
- `0x180040400`
- `0x1800557b8`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180055bcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055cba`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055d8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055df1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055bcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055cba`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055d8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180055df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055d08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055dda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055ac8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055c1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055d08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055dda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055e3f`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18005589c`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18005589c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180055c5e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180055c5e`

## string_xrefs

- `0x180055905`: `MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile`
- `0x1800558bf`: `Skipping unpack of %s, it will be hardlinked later.`
- `0x180055c8c`: `Failed to create output stream for '%ws'.`
- `0x180055b9e`: `Failed to create directory tree for '%ws'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile(
        MsixPackage::Provisioning::Library::PackageMonikerToPayload *this,
        struct IAppxFile *a2,
        char *a3)
{
  int v6; // edi
  _QWORD *v8; // rax
  int v9; // eax
  void *v10; // rbx
  int v11; // eax
  HRESULT (__stdcall *GetStream)(IAppxFile *, IStream **); // rdi
  _QWORD *v13; // rcx
  int v14; // edi
  int v15; // ebx
  __int64 v16; // rbx
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // r8
  WCHAR *v19; // rcx
  int DirectoryTree; // edi
  LPCWSTR *v21; // rdx
  IStream *v22; // rcx
  const WCHAR *v23; // rcx
  HRESULT v24; // edi
  LPCWSTR *v25; // rdx
  int v26; // ebx
  LPCWSTR *v27; // rdx
  char *v28; // [rsp+28h] [rbp-90h]
  LPVOID pv; // [rsp+30h] [rbp-88h] BYREF
  IStream *ppstm; // [rsp+38h] [rbp-80h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-78h] BYREF
  _QWORD Buffer[2]; // [rsp+48h] [rbp-70h] BYREF
  __int64 v33; // [rsp+58h] [rbp-60h] BYREF
  LPCWSTR pszFile[2]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v35; // [rsp+70h] [rbp-48h]
  unsigned __int64 v36; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v31 = 0;
  ppstm = 0;
  v33 = 0;
  pv = 0;
  v6 = ((__int64 (__fastcall *)(struct IAppxFile *, LPVOID *))a2->lpVtbl->GetName)(a2, &pv);
  if ( v6 >= 0 )
  {
    Buffer[0] = pv;
    Buffer[1] = 0;
    v8 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 168), Buffer);
    if ( v8 && v8[1] )
    {
      Buffer[0] = 0;
      v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
             (char *)Buffer,
             L"Skipping unpack of %s, it will be hardlinked later.",
             pv);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15C,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v9);
      v10 = (void *)Buffer[0];
      v11 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              Buffer[0],
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
              L"MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile",
              356);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x164,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v11);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      if ( v31 )
        (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      GetStream = a2->lpVtbl->GetStream;
      v13 = v31;
      v31 = 0;
      if ( v13 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v13 + 16LL))(v13, *v13);
      v14 = ((__int64 (__fastcall *)(struct IAppxFile *, _QWORD **))GetStream)(a2, &v31);
      if ( v14 >= 0 )
      {
        v15 = ((__int64 (__fastcall *)(struct IAppxFile *, __int64 *))a2->lpVtbl->GetSize)(a2, &v33);
        if ( v15 >= 0 )
        {
          v16 = v33;
          v36 = 7;
          v35 = 0;
          LOWORD(pszFile[0]) = 0;
          v17 = -1;
          if ( *(_WORD *)a3 )
          {
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)&a3[2 * v18] );
          }
          else
          {
            v18 = 0;
          }
          std::wstring::assign(pszFile, a3, v18);
          std::wstring::append(pszFile, (char *)L"\\", pszSrc[0] != 0);
          if ( *(_WORD *)pv )
          {
            do
              ++v17;
            while ( *((_WORD *)pv + v17) );
          }
          else
          {
            v17 = 0;
          }
          std::wstring::append(pszFile, (char *)pv, v17);
          v19 = (WCHAR *)pszFile;
          if ( v36 >= 8 )
            v19 = (WCHAR *)pszFile[0];
          DirectoryTree = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(v19);
          if ( DirectoryTree >= 0 )
          {
            v22 = ppstm;
            ppstm = 0;
            if ( v22 )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v22 + 16LL))(v22);
            v23 = (const WCHAR *)pszFile;
            if ( v36 >= 8 )
              v23 = pszFile[0];
            v24 = SHCreateStreamOnFileW(v23, 0x1002u, &ppstm);
            if ( v24 >= 0 )
            {
              v26 = (*(__int64 (__fastcall **)(_QWORD *, IStream *, __int64, _QWORD, _QWORD))(*v31 + 56LL))(
                      v31,
                      ppstm,
                      v16,
                      0,
                      0);
              if ( v26 >= 0 )
              {
                if ( v36 >= 8 )
                  operator delete((void *)pszFile[0]);
                v36 = 7;
                v35 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                if ( v31 )
                  (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
                if ( pv )
                  CoTaskMemFree(pv);
                return 0;
              }
              else
              {
                v27 = pszFile;
                if ( v36 >= 8 )
                  v27 = (LPCWSTR *)pszFile[0];
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x181,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                  (const char *)(unsigned int)v26,
                  (int)"Failed to unpack contents to '%ws'.",
                  (const char *)v27);
                if ( v36 >= 8 )
                  operator delete((void *)pszFile[0]);
                v36 = 7;
                v35 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                if ( v31 )
                  (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
                if ( pv )
                  CoTaskMemFree(pv);
                return (unsigned int)v26;
              }
            }
            else
            {
              v25 = pszFile;
              if ( v36 >= 8 )
                v25 = (LPCWSTR *)pszFile[0];
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x17C,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                (const char *)(unsigned int)v24,
                (int)"Failed to create output stream for '%ws'.",
                (const char *)v25);
              if ( v36 >= 8 )
                operator delete((void *)pszFile[0]);
              v36 = 7;
              v35 = 0;
              LOWORD(pszFile[0]) = 0;
              if ( ppstm )
                (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
              if ( v31 )
                (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
              if ( pv )
                CoTaskMemFree(pv);
              return (unsigned int)v24;
            }
          }
          else
          {
            v21 = pszFile;
            if ( v36 >= 8 )
              v21 = (LPCWSTR *)pszFile[0];
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x177,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
              (const char *)(unsigned int)DirectoryTree,
              (int)"Failed to create directory tree for '%ws'.",
              (const char *)v21);
            if ( v36 >= 8 )
              operator delete((void *)pszFile[0]);
            v36 = 7;
            v35 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            if ( v31 )
              (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
            if ( pv )
              CoTaskMemFree(pv);
            return (unsigned int)DirectoryTree;
          }
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x16B,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
            (const char *)(unsigned int)v15,
            (int)"Failed to get file size for '%ws'",
            (const char *)pv);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          if ( v31 )
            (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
          if ( pv )
            CoTaskMemFree(pv);
          return (unsigned int)v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v14,
          (int)"Failed to get source file stream for '%ws'",
          (const char *)pv);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        if ( v31 )
          (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)v14;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v6,
      (int)"Failed to get source file name.",
      v28);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    if ( v31 )
      (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800557b8  push    rbx
0x1800557ba  push    rsi
0x1800557bb  push    rdi
0x1800557bc  push    r14
0x1800557be  push    r15
0x1800557c0  sub     rsp, 90h
0x1800557c7  mov     rax, cs:__security_cookie
0x1800557ce  xor     rax, rsp
0x1800557d1  mov     [rsp+0B8h+var_38], rax
0x1800557d9  mov     rsi, r8
0x1800557dc  mov     rbx, rdx
0x1800557df  mov     r14, rcx
0x1800557e2  xor     r15d, r15d
0x1800557e5  mov     [rsp+0B8h+var_78], r15
0x1800557ea  mov     [rsp+0B8h+ppstm], r15
0x1800557ef  mov     [rsp+0B8h+var_60], r15
0x1800557f4  mov     [rsp+0B8h+pv], r15
0x1800557f9  mov     rax, [rdx]
0x1800557fc  lea     rdx, [rsp+0B8h+pv]
0x180055801  mov     rcx, rbx
0x180055804  mov     rax, [rax+28h]
0x180055808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005580d  mov     edi, eax
0x18005580f  test    eax, eax
0x180055811  jns     short loc_180055881
0x180055813  mov     rcx, [rsp+0B8h]; this
0x18005581b  lea     rax, aFailedToGetSou_0; "Failed to get source file name."
0x180055822  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180055827  mov     r9d, edi; char *
0x18005582a  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180055831  mov     edx, 152h; void *
0x180055836  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005583b  nop
0x18005583c  mov     rcx, [rsp+0B8h+ppstm]
0x180055841  test    rcx, rcx
0x180055844  jz      short loc_180055853
0x180055846  mov     rax, [rcx]
0x180055849  mov     rax, [rax+10h]
0x18005584d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055852  nop
0x180055853  mov     rcx, [rsp+0B8h+var_78]
0x180055858  test    rcx, rcx
0x18005585b  jz      short loc_18005586A
0x18005585d  mov     rax, [rcx]
0x180055860  mov     rax, [rax+10h]
0x180055864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055869  nop
0x18005586a  mov     rcx, [rsp+0B8h+pv]; pv
0x18005586f  test    rcx, rcx
0x180055872  jz      short loc_18005587A
0x180055874  call    cs:__imp_CoTaskMemFree
0x18005587a  mov     eax, edi
0x18005587c  jmp     loc_180055E4D
0x180055881  mov     rax, [rsp+0B8h+pv]
0x180055886  mov     [rsp+0B8h+Buffer], rax
0x18005588b  mov     [rsp+0B8h+var_68], r15
0x180055890  lea     rcx, [r14+0A8h]; Table
0x180055897  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x18005589c  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800558a2  test    rax, rax
0x1800558a5  jz      loc_180055992
0x1800558ab  cmp     [rax+8], r15
0x1800558af  jz      loc_180055992
0x1800558b5  mov     [rsp+0B8h+Buffer], r15
0x1800558ba  mov     r8, [rsp+0B8h+pv]
0x1800558bf  lea     rdx, aSkippingUnpack; "Skipping unpack of %s, it will be hardl"...
0x1800558c6  lea     rcx, [rsp+0B8h+Buffer]
0x1800558cb  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800558d0  mov     rcx, [rsp+0B8h]; this
0x1800558d8  test    eax, eax
0x1800558da  jns     short loc_1800558F0
0x1800558dc  mov     r9d, eax; char *
0x1800558df  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800558e6  mov     edx, 15Ch; void *
0x1800558eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800558f0  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1800558f5  mov     [rsp+0B8h+var_98], 3; int
0x1800558fd  mov     edi, 164h
0x180055902  mov     r9d, edi
0x180055905  lea     r8, aMsixpackagePro_13; "MsixPackage::Provisioning::Library::Pac"...
0x18005590c  lea     rdx, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180055913  mov     rbx, [rsp+0B8h+Buffer]
0x180055918  mov     rcx, rbx
0x18005591b  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180055920  mov     rcx, [rsp+0B8h]; this
0x180055928  test    eax, eax
0x18005592a  jns     short loc_18005593E
0x18005592c  mov     r9d, eax; char *
0x18005592f  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180055936  mov     edx, edi; void *
0x180055938  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005593d  nop
0x18005593e  test    rbx, rbx
0x180055941  jz      short loc_18005594D
0x180055943  mov     rcx, rbx; pv
0x180055946  call    cs:__imp_CoTaskMemFree
0x18005594c  nop
0x18005594d  mov     rcx, [rsp+0B8h+ppstm]
0x180055952  test    rcx, rcx
0x180055955  jz      short loc_180055964
0x180055957  mov     rax, [rcx]
0x18005595a  mov     rax, [rax+10h]
0x18005595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055963  nop
0x180055964  mov     rcx, [rsp+0B8h+var_78]
0x180055969  test    rcx, rcx
0x18005596c  jz      short loc_18005597B
0x18005596e  mov     rax, [rcx]
0x180055971  mov     rax, [rax+10h]
0x180055975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005597a  nop
0x18005597b  mov     rcx, [rsp+0B8h+pv]; pv
0x180055980  test    rcx, rcx
0x180055983  jz      short loc_18005598B
0x180055985  call    cs:__imp_CoTaskMemFree
0x18005598b  xor     eax, eax
0x18005598d  jmp     loc_180055E4D
0x180055992  mov     rax, [rbx]
0x180055995  mov     rdi, [rax+38h]
0x180055999  mov     rcx, [rsp+0B8h+var_78]
0x18005599e  mov     [rsp+0B8h+var_78], r15
0x1800559a3  test    rcx, rcx
0x1800559a6  jz      short loc_1800559B5
0x1800559a8  mov     rdx, [rcx]
0x1800559ab  mov     rax, [rdx+10h]
0x1800559af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559b4  nop
0x1800559b5  lea     rdx, [rsp+0B8h+var_78]
0x1800559ba  mov     rcx, rbx
0x1800559bd  mov     rax, rdi
0x1800559c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559c5  mov     edi, eax
0x1800559c7  test    eax, eax
0x1800559c9  jns     short loc_180055A43
0x1800559cb  mov     rcx, [rsp+0B8h]; this
0x1800559d3  mov     rdx, [rsp+0B8h+pv]
0x1800559d8  mov     [rsp+0B8h+var_90], rdx; char *
0x1800559dd  lea     rax, aFailedToGetSou; "Failed to get source file stream for '%"...
0x1800559e4  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x1800559e9  mov     r9d, edi; char *
0x1800559ec  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800559f3  mov     edx, 169h; void *
0x1800559f8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800559fd  nop
0x1800559fe  mov     rcx, [rsp+0B8h+ppstm]
0x180055a03  test    rcx, rcx
0x180055a06  jz      short loc_180055A15
0x180055a08  mov     rax, [rcx]
0x180055a0b  mov     rax, [rax+10h]
0x180055a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a14  nop
0x180055a15  mov     rcx, [rsp+0B8h+var_78]
0x180055a1a  test    rcx, rcx
0x180055a1d  jz      short loc_180055A2C
0x180055a1f  mov     rax, [rcx]
0x180055a22  mov     rax, [rax+10h]
0x180055a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a2b  nop
0x180055a2c  mov     rcx, [rsp+0B8h+pv]; pv
0x180055a31  test    rcx, rcx
0x180055a34  jz      short loc_180055A3C
0x180055a36  call    cs:__imp_CoTaskMemFree
0x180055a3c  mov     eax, edi
0x180055a3e  jmp     loc_180055E4D
0x180055a43  mov     rax, [rbx]
0x180055a46  lea     rdx, [rsp+0B8h+var_60]
0x180055a4b  mov     rcx, rbx
0x180055a4e  mov     rax, [rax+30h]
0x180055a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a57  mov     ebx, eax
0x180055a59  test    eax, eax
0x180055a5b  jns     short loc_180055AD5
0x180055a5d  mov     rcx, [rsp+0B8h]; this
0x180055a65  mov     rdx, [rsp+0B8h+pv]
0x180055a6a  mov     [rsp+0B8h+var_90], rdx; char *
0x180055a6f  lea     rax, aFailedToGetFil_0; "Failed to get file size for '%ws'"
0x180055a76  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180055a7b  mov     r9d, ebx; char *
0x180055a7e  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180055a85  mov     edx, 16Bh; void *
0x180055a8a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180055a8f  nop
0x180055a90  mov     rcx, [rsp+0B8h+ppstm]
0x180055a95  test    rcx, rcx
0x180055a98  jz      short loc_180055AA7
0x180055a9a  mov     rax, [rcx]
0x180055a9d  mov     rax, [rax+10h]
0x180055aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aa6  nop
0x180055aa7  mov     rcx, [rsp+0B8h+var_78]
0x180055aac  test    rcx, rcx
0x180055aaf  jz      short loc_180055ABE
0x180055ab1  mov     rax, [rcx]
0x180055ab4  mov     rax, [rax+10h]
0x180055ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055abd  nop
0x180055abe  mov     rcx, [rsp+0B8h+pv]; pv
0x180055ac3  test    rcx, rcx
0x180055ac6  jz      short loc_180055ACE
0x180055ac8  call    cs:__imp_CoTaskMemFree
0x180055ace  mov     eax, ebx
0x180055ad0  jmp     loc_180055E4D
0x180055ad5  mov     rbx, [rsp+0B8h+var_60]
0x180055ada  mov     r14d, 7
0x180055ae0  mov     [rsp+0B8h+var_40], r14
0x180055ae5  mov     [rsp+0B8h+var_48], r15
0x180055aea  mov     word ptr [rsp+0B8h+pszFile], r15w
0x180055af0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055af4  cmp     [rsi], r15w
0x180055af8  jnz     short loc_180055AFF
0x180055afa  mov     r8, r15
0x180055afd  jmp     short loc_180055B0C
0x180055aff  mov     r8, rdi
0x180055b02  inc     r8
0x180055b05  cmp     [rsi+r8*2], r15w
0x180055b0a  jnz     short loc_180055B02
0x180055b0c  mov     rdx, rsi; Src
0x180055b0f  lea     rcx, [rsp+0B8h+pszFile]; void *
0x180055b14  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180055b19  mov     r8, r15
0x180055b1c  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180055b24  setnz   r8b
0x180055b28  lea     rdx, pszSrc; "\\"
0x180055b2f  lea     rcx, [rsp+0B8h+pszFile]; Src
0x180055b34  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180055b39  mov     rdx, [rsp+0B8h+pv]; void *
0x180055b3e  cmp     [rdx], r15w
0x180055b42  jnz     short loc_180055B49
0x180055b44  mov     rdi, r15
0x180055b47  jmp     short loc_180055B53
0x180055b49  inc     rdi
0x180055b4c  cmp     [rdx+rdi*2], r15w
0x180055b51  jnz     short loc_180055B49
0x180055b53  mov     r8, rdi
0x180055b56  lea     rcx, [rsp+0B8h+pszFile]; Src
0x180055b5b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180055b60  lea     rcx, [rsp+0B8h+pszFile]
0x180055b65  cmp     [rsp+0B8h+var_40], 8
0x180055b6b  cmovnb  rcx, [rsp+0B8h+pszFile]; lpPathName
0x180055b71  call    ?CreateDirectoryTree@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(ushort const *)
0x180055b76  mov     edi, eax
0x180055b78  test    eax, eax
0x180055b7a  jns     loc_180055C27
0x180055b80  lea     rdx, [rsp+0B8h+pszFile]
0x180055b85  cmp     [rsp+0B8h+var_40], 8
0x180055b8b  cmovnb  rdx, [rsp+0B8h+pszFile]
0x180055b91  mov     rcx, [rsp+0B8h]; this
0x180055b99  mov     [rsp+0B8h+var_90], rdx; char *
0x180055b9e  lea     rax, aFailedToCreate_32; "Failed to create directory tree for '%w"...
0x180055ba5  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180055baa  mov     r9d, edi; char *
0x180055bad  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180055bb4  mov     edx, 177h; void *
0x180055bb9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180055bbe  nop
0x180055bbf  cmp     [rsp+0B8h+var_40], 8
0x180055bc5  jb      short loc_180055BD2
0x180055bc7  mov     rcx, [rsp+0B8h+pszFile]
0x180055bcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180055bd2  mov     [rsp+0B8h+var_40], r14
0x180055bd7  mov     [rsp+0B8h+var_48], r15
0x180055bdc  mov     word ptr [rsp+0B8h+pszFile], r15w
0x180055be2  mov     rcx, [rsp+0B8h+ppstm]
0x180055be7  test    rcx, rcx
0x180055bea  jz      short loc_180055BF9
0x180055bec  mov     rax, [rcx]
0x180055bef  mov     rax, [rax+10h]
0x180055bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bf8  nop
0x180055bf9  mov     rcx, [rsp+0B8h+var_78]
0x180055bfe  test    rcx, rcx
0x180055c01  jz      short loc_180055C10
0x180055c03  mov     rax, [rcx]
0x180055c06  mov     rax, [rax+10h]
0x180055c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c0f  nop
0x180055c10  mov     rcx, [rsp+0B8h+pv]; pv
0x180055c15  test    rcx, rcx
0x180055c18  jz      short loc_180055C20
0x180055c1a  call    cs:__imp_CoTaskMemFree
0x180055c20  mov     eax, edi
0x180055c22  jmp     loc_180055E4D
0x180055c27  mov     rcx, [rsp+0B8h+ppstm]
0x180055c2c  mov     [rsp+0B8h+ppstm], r15
0x180055c31  test    rcx, rcx
0x180055c34  jz      short loc_180055C43
0x180055c36  mov     rax, [rcx]
0x180055c39  mov     rax, [rax+10h]
0x180055c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c42  nop
0x180055c43  lea     rcx, [rsp+0B8h+pszFile]
0x180055c48  cmp     [rsp+0B8h+var_40], 8
0x180055c4e  cmovnb  rcx, [rsp+0B8h+pszFile]; pszFile
0x180055c54  lea     r8, [rsp+0B8h+ppstm]; ppstm
0x180055c59  mov     edx, 1002h; grfMode
0x180055c5e  call    cs:__imp_SHCreateStreamOnFileW
0x180055c64  mov     edi, eax
0x180055c66  test    eax, eax
0x180055c68  jns     loc_180055D15
0x180055c6e  lea     rdx, [rsp+0B8h+pszFile]
  ... truncated ...
```

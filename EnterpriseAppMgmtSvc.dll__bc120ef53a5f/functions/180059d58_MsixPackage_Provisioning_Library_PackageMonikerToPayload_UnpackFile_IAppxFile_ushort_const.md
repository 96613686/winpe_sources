# MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile(IAppxFile *,ushort const *)

- ea: `0x180059d58`
- end: `0x18005a467`
- name: `?UnpackFile@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@AEAAJPEAUIAppxFile@@PEBG@Z`
- size: `1807`
- prototype: `int(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, struct IAppxFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180059274`

## callees

- `0x18001d160`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x18003e50c`
- `0x180043174`
- `0x180043fb4`
- `0x180059d58`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18005a190`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a290`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a36e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a3df`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a190`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a290`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a36e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005a3df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059f37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a1e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a2e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a3c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059e14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059f37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059fee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a1e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a2e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a3c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a433`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180059e42`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180059e42`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18005a22e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18005a22e`

## string_xrefs

- `0x180059eb1`: `MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile`
- `0x180059e6b`: `Skipping unpack of %s, it will be hardlinked later.`
- `0x18005a262`: `Failed to create output stream for '%ws'.`
- `0x18005a162`: `Failed to create directory tree for '%ws'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::UnpackFile(
        MsixPackage::Provisioning::Library::PackageMonikerToPayload *this,
        struct IAppxFile *a2,
        unsigned __int16 *a3)
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
  __int64 v17; // rdi
  __int64 v18; // r8
  const WCHAR *v19; // rcx
  int DirectoryTree; // edi
  LPCWSTR *v21; // rdx
  IStream *v22; // rcx
  const WCHAR *v23; // rcx
  HRESULT v24; // edi
  LPCWSTR *v25; // rdx
  int v26; // ebx
  LPCWSTR *v27; // rdx
  int v28; // [rsp+20h] [rbp-98h]
  char *v29; // [rsp+28h] [rbp-90h]
  LPVOID pv; // [rsp+30h] [rbp-88h] BYREF
  IStream *ppstm; // [rsp+38h] [rbp-80h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-78h] BYREF
  _QWORD Buffer[2]; // [rsp+48h] [rbp-70h] BYREF
  __int64 v34; // [rsp+58h] [rbp-60h] BYREF
  LPCWSTR pszFile[2]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v36; // [rsp+70h] [rbp-48h]
  unsigned __int64 v37; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v32 = 0;
  ppstm = 0;
  v34 = 0;
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
             Buffer,
             L"Skipping unpack of %s, it will be hardlinked later.",
             pv);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15C,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v9,
          v28);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v11,
          3);
      if ( v10 )
        CoTaskMemFree(v10);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      if ( v32 )
        (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      GetStream = a2->lpVtbl->GetStream;
      v13 = v32;
      v32 = 0;
      if ( v13 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v13 + 16LL))(v13, *v13);
      v14 = ((__int64 (__fastcall *)(struct IAppxFile *, _QWORD **))GetStream)(a2, &v32);
      if ( v14 >= 0 )
      {
        v15 = ((__int64 (__fastcall *)(struct IAppxFile *, __int64 *))a2->lpVtbl->GetSize)(a2, &v34);
        if ( v15 >= 0 )
        {
          v16 = v34;
          v37 = 7;
          v36 = 0;
          LOWORD(pszFile[0]) = 0;
          v17 = -1;
          if ( *a3 )
          {
            v18 = -1;
            do
              ++v18;
            while ( a3[v18] );
          }
          std::wstring::assign(pszFile, a3);
          std::wstring::append(pszFile, (void *)L"\\");
          if ( *(_WORD *)pv )
          {
            do
              ++v17;
            while ( *((_WORD *)pv + v17) );
          }
          std::wstring::append(pszFile, pv);
          v19 = (const WCHAR *)pszFile;
          if ( v37 >= 8 )
            v19 = pszFile[0];
          DirectoryTree = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(v19);
          if ( DirectoryTree >= 0 )
          {
            v22 = ppstm;
            ppstm = 0;
            if ( v22 )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)v22 + 16LL))(v22);
            v23 = (const WCHAR *)pszFile;
            if ( v37 >= 8 )
              v23 = pszFile[0];
            v24 = SHCreateStreamOnFileW(v23, 0x1002u, &ppstm);
            if ( v24 >= 0 )
            {
              v26 = (*(__int64 (__fastcall **)(_QWORD *, IStream *, __int64, _QWORD, _QWORD))(*v32 + 56LL))(
                      v32,
                      ppstm,
                      v16,
                      0,
                      0);
              if ( v26 >= 0 )
              {
                if ( v37 >= 8 )
                  operator delete((void *)pszFile[0]);
                v37 = 7;
                v36 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                if ( v32 )
                  (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
                if ( pv )
                  CoTaskMemFree(pv);
                return 0;
              }
              else
              {
                v27 = pszFile;
                if ( v37 >= 8 )
                  v27 = (LPCWSTR *)pszFile[0];
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  (void *)0x181,
                  (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                  (const char *)(unsigned int)v26,
                  (int)"Failed to unpack contents to '%ws'.",
                  (const char *)v27);
                if ( v37 >= 8 )
                  operator delete((void *)pszFile[0]);
                v37 = 7;
                v36 = 0;
                LOWORD(pszFile[0]) = 0;
                if ( ppstm )
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
                if ( v32 )
                  (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
                if ( pv )
                  CoTaskMemFree(pv);
                return (unsigned int)v26;
              }
            }
            else
            {
              v25 = pszFile;
              if ( v37 >= 8 )
                v25 = (LPCWSTR *)pszFile[0];
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x17C,
                (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                (const char *)(unsigned int)v24,
                (int)"Failed to create output stream for '%ws'.",
                (const char *)v25);
              if ( v37 >= 8 )
                operator delete((void *)pszFile[0]);
              v37 = 7;
              v36 = 0;
              LOWORD(pszFile[0]) = 0;
              if ( ppstm )
                (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
              if ( v32 )
                (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
              if ( pv )
                CoTaskMemFree(pv);
              return (unsigned int)v24;
            }
          }
          else
          {
            v21 = pszFile;
            if ( v37 >= 8 )
              v21 = (LPCWSTR *)pszFile[0];
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x177,
              (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
              (const char *)(unsigned int)DirectoryTree,
              (int)"Failed to create directory tree for '%ws'.",
              (const char *)v21);
            if ( v37 >= 8 )
              operator delete((void *)pszFile[0]);
            v37 = 7;
            v36 = 0;
            LOWORD(pszFile[0]) = 0;
            if ( ppstm )
              (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
            if ( v32 )
              (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
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
          if ( v32 )
            (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
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
        if ( v32 )
          (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
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
      v29);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    if ( v32 )
      (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180059d58  push    rbx
0x180059d5a  push    rsi
0x180059d5b  push    rdi
0x180059d5c  push    r14
0x180059d5e  push    r15
0x180059d60  sub     rsp, 90h
0x180059d67  mov     rax, cs:__security_cookie
0x180059d6e  xor     rax, rsp
0x180059d71  mov     [rsp+0B8h+var_38], rax
0x180059d79  mov     rsi, r8
0x180059d7c  mov     rbx, rdx
0x180059d7f  mov     r14, rcx
0x180059d82  xor     r15d, r15d
0x180059d85  mov     [rsp+0B8h+var_78], r15
0x180059d8a  mov     [rsp+0B8h+ppstm], r15
0x180059d8f  mov     [rsp+0B8h+var_60], r15
0x180059d94  mov     [rsp+0B8h+pv], r15
0x180059d99  mov     rax, [rdx]
0x180059d9c  lea     rdx, [rsp+0B8h+pv]
0x180059da1  mov     rcx, rbx
0x180059da4  mov     rax, [rax+28h]
0x180059da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059dad  mov     edi, eax
0x180059daf  test    eax, eax
0x180059db1  jns     short loc_180059E27
0x180059db3  mov     rcx, [rsp+0B8h]; this
0x180059dbb  lea     rax, aFailedToGetSou_0; "Failed to get source file name."
0x180059dc2  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180059dc7  mov     r9d, edi; char *
0x180059dca  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059dd1  mov     edx, 152h; void *
0x180059dd6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180059ddb  nop
0x180059ddc  mov     rcx, [rsp+0B8h+ppstm]
0x180059de1  test    rcx, rcx
0x180059de4  jz      short loc_180059DF3
0x180059de6  mov     rax, [rcx]
0x180059de9  mov     rax, [rax+10h]
0x180059ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059df2  nop
0x180059df3  mov     rcx, [rsp+0B8h+var_78]
0x180059df8  test    rcx, rcx
0x180059dfb  jz      short loc_180059E0A
0x180059dfd  mov     rax, [rcx]
0x180059e00  mov     rax, [rax+10h]
0x180059e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e09  nop
0x180059e0a  mov     rcx, [rsp+0B8h+pv]; pv
0x180059e0f  test    rcx, rcx
0x180059e12  jz      short loc_180059E20
0x180059e14  call    cs:__imp_CoTaskMemFree
0x180059e1b  nop     dword ptr [rax+rax+00h]
0x180059e20  mov     eax, edi
0x180059e22  jmp     loc_18005A447
0x180059e27  mov     rax, [rsp+0B8h+pv]
0x180059e2c  mov     [rsp+0B8h+Buffer], rax
0x180059e31  mov     [rsp+0B8h+var_68], r15
0x180059e36  lea     rcx, [r14+0A8h]; Table
0x180059e3d  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x180059e42  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180059e49  nop     dword ptr [rax+rax+00h]
0x180059e4e  test    rax, rax
0x180059e51  jz      loc_180059F4A
0x180059e57  cmp     [rax+8], r15
0x180059e5b  jz      loc_180059F4A
0x180059e61  mov     [rsp+0B8h+Buffer], r15
0x180059e66  mov     r8, [rsp+0B8h+pv]
0x180059e6b  lea     rdx, aSkippingUnpack; "Skipping unpack of %s, it will be hardl"...
0x180059e72  lea     rcx, [rsp+0B8h+Buffer]
0x180059e77  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180059e7c  mov     rcx, [rsp+0B8h]; this
0x180059e84  test    eax, eax
0x180059e86  jns     short loc_180059E9C
0x180059e88  mov     r9d, eax; char *
0x180059e8b  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059e92  mov     edx, 15Ch; void *
0x180059e97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059e9c  mov     dword ptr [rsp+0B8h+var_90], r15d
0x180059ea1  mov     [rsp+0B8h+var_98], 3; int
0x180059ea9  mov     edi, 164h
0x180059eae  mov     r9d, edi
0x180059eb1  lea     r8, aMsixpackagePro_13; "MsixPackage::Provisioning::Library::Pac"...
0x180059eb8  lea     rdx, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059ebf  mov     rbx, [rsp+0B8h+Buffer]
0x180059ec4  mov     rcx, rbx
0x180059ec7  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180059ecc  mov     rcx, [rsp+0B8h]; this
0x180059ed4  test    eax, eax
0x180059ed6  jns     short loc_180059EEA
0x180059ed8  mov     r9d, eax; char *
0x180059edb  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059ee2  mov     edx, edi; void *
0x180059ee4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180059ee9  nop
0x180059eea  test    rbx, rbx
0x180059eed  jz      short loc_180059EFF
0x180059eef  mov     rcx, rbx; pv
0x180059ef2  call    cs:__imp_CoTaskMemFree
0x180059ef9  nop     dword ptr [rax+rax+00h]
0x180059efe  nop
0x180059eff  mov     rcx, [rsp+0B8h+ppstm]
0x180059f04  test    rcx, rcx
0x180059f07  jz      short loc_180059F16
0x180059f09  mov     rax, [rcx]
0x180059f0c  mov     rax, [rax+10h]
0x180059f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f15  nop
0x180059f16  mov     rcx, [rsp+0B8h+var_78]
0x180059f1b  test    rcx, rcx
0x180059f1e  jz      short loc_180059F2D
0x180059f20  mov     rax, [rcx]
0x180059f23  mov     rax, [rax+10h]
0x180059f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f2c  nop
0x180059f2d  mov     rcx, [rsp+0B8h+pv]; pv
0x180059f32  test    rcx, rcx
0x180059f35  jz      short loc_180059F43
0x180059f37  call    cs:__imp_CoTaskMemFree
0x180059f3e  nop     dword ptr [rax+rax+00h]
0x180059f43  xor     eax, eax
0x180059f45  jmp     loc_18005A447
0x180059f4a  mov     rax, [rbx]
0x180059f4d  mov     rdi, [rax+38h]
0x180059f51  mov     rcx, [rsp+0B8h+var_78]
0x180059f56  mov     [rsp+0B8h+var_78], r15
0x180059f5b  test    rcx, rcx
0x180059f5e  jz      short loc_180059F6D
0x180059f60  mov     rdx, [rcx]
0x180059f63  mov     rax, [rdx+10h]
0x180059f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f6c  nop
0x180059f6d  lea     rdx, [rsp+0B8h+var_78]
0x180059f72  mov     rcx, rbx
0x180059f75  mov     rax, rdi
0x180059f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f7d  mov     edi, eax
0x180059f7f  test    eax, eax
0x180059f81  jns     short loc_18005A001
0x180059f83  mov     rcx, [rsp+0B8h]; this
0x180059f8b  mov     rdx, [rsp+0B8h+pv]
0x180059f90  mov     [rsp+0B8h+var_90], rdx; char *
0x180059f95  lea     rax, aFailedToGetSou; "Failed to get source file stream for '%"...
0x180059f9c  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x180059fa1  mov     r9d, edi; char *
0x180059fa4  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059fab  mov     edx, 169h; void *
0x180059fb0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180059fb5  nop
0x180059fb6  mov     rcx, [rsp+0B8h+ppstm]
0x180059fbb  test    rcx, rcx
0x180059fbe  jz      short loc_180059FCD
0x180059fc0  mov     rax, [rcx]
0x180059fc3  mov     rax, [rax+10h]
0x180059fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fcc  nop
0x180059fcd  mov     rcx, [rsp+0B8h+var_78]
0x180059fd2  test    rcx, rcx
0x180059fd5  jz      short loc_180059FE4
0x180059fd7  mov     rax, [rcx]
0x180059fda  mov     rax, [rax+10h]
0x180059fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fe3  nop
0x180059fe4  mov     rcx, [rsp+0B8h+pv]; pv
0x180059fe9  test    rcx, rcx
0x180059fec  jz      short loc_180059FFA
0x180059fee  call    cs:__imp_CoTaskMemFree
0x180059ff5  nop     dword ptr [rax+rax+00h]
0x180059ffa  mov     eax, edi
0x180059ffc  jmp     loc_18005A447
0x18005a001  mov     rax, [rbx]
0x18005a004  lea     rdx, [rsp+0B8h+var_60]
0x18005a009  mov     rcx, rbx
0x18005a00c  mov     rax, [rax+30h]
0x18005a010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a015  mov     ebx, eax
0x18005a017  test    eax, eax
0x18005a019  jns     short loc_18005A099
0x18005a01b  mov     rcx, [rsp+0B8h]; this
0x18005a023  mov     rdx, [rsp+0B8h+pv]
0x18005a028  mov     [rsp+0B8h+var_90], rdx; char *
0x18005a02d  lea     rax, aFailedToGetFil_0; "Failed to get file size for '%ws'"
0x18005a034  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x18005a039  mov     r9d, ebx; char *
0x18005a03c  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005a043  mov     edx, 16Bh; void *
0x18005a048  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005a04d  nop
0x18005a04e  mov     rcx, [rsp+0B8h+ppstm]
0x18005a053  test    rcx, rcx
0x18005a056  jz      short loc_18005A065
0x18005a058  mov     rax, [rcx]
0x18005a05b  mov     rax, [rax+10h]
0x18005a05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a064  nop
0x18005a065  mov     rcx, [rsp+0B8h+var_78]
0x18005a06a  test    rcx, rcx
0x18005a06d  jz      short loc_18005A07C
0x18005a06f  mov     rax, [rcx]
0x18005a072  mov     rax, [rax+10h]
0x18005a076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a07b  nop
0x18005a07c  mov     rcx, [rsp+0B8h+pv]; pv
0x18005a081  test    rcx, rcx
0x18005a084  jz      short loc_18005A092
0x18005a086  call    cs:__imp_CoTaskMemFree
0x18005a08d  nop     dword ptr [rax+rax+00h]
0x18005a092  mov     eax, ebx
0x18005a094  jmp     loc_18005A447
0x18005a099  mov     rbx, [rsp+0B8h+var_60]
0x18005a09e  mov     r14d, 7
0x18005a0a4  mov     [rsp+0B8h+var_40], r14
0x18005a0a9  mov     [rsp+0B8h+var_48], r15
0x18005a0ae  mov     word ptr [rsp+0B8h+pszFile], r15w
0x18005a0b4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005a0b8  cmp     [rsi], r15w
0x18005a0bc  jnz     short loc_18005A0C3
0x18005a0be  mov     r8, r15
0x18005a0c1  jmp     short loc_18005A0D0
0x18005a0c3  mov     r8, rdi
0x18005a0c6  inc     r8
0x18005a0c9  cmp     [rsi+r8*2], r15w
0x18005a0ce  jnz     short loc_18005A0C6
0x18005a0d0  mov     rdx, rsi; Src
0x18005a0d3  lea     rcx, [rsp+0B8h+pszFile]; void *
0x18005a0d8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18005a0dd  mov     r8, r15
0x18005a0e0  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18005a0e8  setnz   r8b
0x18005a0ec  lea     rdx, pszSrc; "\\"
0x18005a0f3  lea     rcx, [rsp+0B8h+pszFile]; Src
0x18005a0f8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005a0fd  mov     rdx, [rsp+0B8h+pv]; void *
0x18005a102  cmp     [rdx], r15w
0x18005a106  jnz     short loc_18005A10D
0x18005a108  mov     rdi, r15
0x18005a10b  jmp     short loc_18005A117
0x18005a10d  inc     rdi
0x18005a110  cmp     [rdx+rdi*2], r15w
0x18005a115  jnz     short loc_18005A10D
0x18005a117  mov     r8, rdi
0x18005a11a  lea     rcx, [rsp+0B8h+pszFile]; Src
0x18005a11f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18005a124  lea     rcx, [rsp+0B8h+pszFile]
0x18005a129  cmp     [rsp+0B8h+var_40], 8
0x18005a12f  cmovnb  rcx, [rsp+0B8h+pszFile]; lpPathName
0x18005a135  call    ?CreateDirectoryTree@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(ushort const *)
0x18005a13a  mov     edi, eax
0x18005a13c  test    eax, eax
0x18005a13e  jns     loc_18005A1F7
0x18005a144  lea     rdx, [rsp+0B8h+pszFile]
0x18005a149  cmp     [rsp+0B8h+var_40], 8
0x18005a14f  cmovnb  rdx, [rsp+0B8h+pszFile]
0x18005a155  mov     rcx, [rsp+0B8h]; this
0x18005a15d  mov     [rsp+0B8h+var_90], rdx; char *
0x18005a162  lea     rax, aFailedToCreate_32; "Failed to create directory tree for '%w"...
0x18005a169  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x18005a16e  mov     r9d, edi; char *
0x18005a171  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005a178  mov     edx, 177h; void *
0x18005a17d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005a182  nop
0x18005a183  cmp     [rsp+0B8h+var_40], 8
0x18005a189  jb      short loc_18005A19C
0x18005a18b  mov     rcx, [rsp+0B8h+pszFile]
0x18005a190  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005a197  nop     dword ptr [rax+rax+00h]
0x18005a19c  mov     [rsp+0B8h+var_40], r14
0x18005a1a1  mov     [rsp+0B8h+var_48], r15
0x18005a1a6  mov     word ptr [rsp+0B8h+pszFile], r15w
0x18005a1ac  mov     rcx, [rsp+0B8h+ppstm]
0x18005a1b1  test    rcx, rcx
0x18005a1b4  jz      short loc_18005A1C3
0x18005a1b6  mov     rax, [rcx]
0x18005a1b9  mov     rax, [rax+10h]
0x18005a1bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1c2  nop
0x18005a1c3  mov     rcx, [rsp+0B8h+var_78]
0x18005a1c8  test    rcx, rcx
0x18005a1cb  jz      short loc_18005A1DA
0x18005a1cd  mov     rax, [rcx]
0x18005a1d0  mov     rax, [rax+10h]
0x18005a1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1d9  nop
0x18005a1da  mov     rcx, [rsp+0B8h+pv]; pv
0x18005a1df  test    rcx, rcx
0x18005a1e2  jz      short loc_18005A1F0
0x18005a1e4  call    cs:__imp_CoTaskMemFree
0x18005a1eb  nop     dword ptr [rax+rax+00h]
0x18005a1f0  mov     eax, edi
0x18005a1f2  jmp     loc_18005A447
0x18005a1f7  mov     rcx, [rsp+0B8h+ppstm]
0x18005a1fc  mov     [rsp+0B8h+ppstm], r15
0x18005a201  test    rcx, rcx
0x18005a204  jz      short loc_18005A213
0x18005a206  mov     rax, [rcx]
0x18005a209  mov     rax, [rax+10h]
0x18005a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a212  nop
0x18005a213  lea     rcx, [rsp+0B8h+pszFile]
0x18005a218  cmp     [rsp+0B8h+var_40], 8
  ... truncated ...
```

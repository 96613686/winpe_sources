# DownloadExecutionBroker::ExecuteFile(ushort const *,ushort const *,ulong,int,int,ushort const *)

- ea: `0x180025c60`
- end: `0x180026116`
- name: `?ExecuteFile@DownloadExecutionBroker@@UEAAJPEBG0KHH0@Z`
- size: `1206`
- prototype: `int(DownloadExecutionBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800037ac`
- `0x18000a4d0`
- `0x18000d17c`
- `0x18000dc74`
- `0x18000e428`
- `0x18001078c`
- `0x180010b4c`
- `0x18001e93c`
- `0x180025174`
- `0x1800253c4`
- `0x18002583c`
- `0x180025860`
- `0x180025b00`
- `0x180025c60`
- `0x18002655c`
- `0x180026b10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025cd8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025cd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180025eb1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180025eb1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025cae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025e19`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025cae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180025e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800260a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025e98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025ecb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026022`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025e98`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025ecb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180026022`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180025ded`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180025ded`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocIsDangerous` at `0x180025cba`
- `api-ms-win-shlwapi-ie-l1-1-0!AssocIsDangerous` at `0x180025cba`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180026092`
- `ext-ms-win-appmodel-shellexecute-l1-1-0!ShellExecuteExW` at `0x180026092`

## string_xrefs

- `0x180025dca`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\downloadexecutionbroker.cpp`
- `0x180025f6b`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\downloadexecutionbroker.cpp`
- `0x180025fa5`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\downloadexecutionbroker.cpp`
- `0x180025ec2`: `infopath.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DownloadExecutionBroker::ExecuteFile(
        DownloadExecutionBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        int a5,
        int a6)
{
  char v8; // r14
  int PIC; // ebx
  const WCHAR *ExtensionW; // rsi
  char **v11; // rdi
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rbx
  unsigned __int64 v14; // r15
  signed int v15; // edi
  unsigned __int16 *v16; // rax
  size_t v17; // rdx
  HRESULT v18; // eax
  const WCHAR *lpDirectory; // rcx
  char *v20; // rbx
  char v21; // si
  const WCHAR *v22; // r13
  unsigned int v23; // edi
  const WCHAR *FileNameW; // rax
  __int64 v25; // rdi
  __int64 v26; // rax
  unsigned __int64 v27; // rsi
  void **cotaskmem_string_failfast; // r15
  int v29; // eax
  unsigned __int64 v30; // rsi
  unsigned __int16 *v31; // rcx
  const unsigned __int16 *v32; // rdi
  int v33; // eax
  bool v34; // zf
  char v35; // al
  signed int LastError; // eax
  unsigned __int16 **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v40; // [rsp+28h] [rbp-D8h]
  unsigned int v41; // [rsp+30h] [rbp-D0h]
  unsigned int v42[2]; // [rsp+48h] [rbp-B8h] BYREF
  HINSTANCE v43; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v44; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR pszPath; // [rsp+60h] [rbp-A0h] BYREF
  char *v46; // [rsp+68h] [rbp-98h] BYREF
  void *v47; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR *p_pszPath; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+88h] [rbp-78h]
  HKEY *v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  char v53; // [rsp+A0h] [rbp-60h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v42[0] = 0;
  v8 = 1;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, v42);
  if ( PIC >= 0 )
  {
    if ( a4 >= 0x79 )
      goto LABEL_8;
    ExtensionW = PathFindExtensionW(a2);
    if ( !AssocIsDangerous(ExtensionW) )
      goto LABEL_8;
    v11 = (char **)off_18003F090;
    do
    {
      if ( !(unsigned int)_o__wcsicmp(ExtensionW, *v11) )
        break;
      ++v11;
    }
    while ( v11 != &wil::details::g_processLocalData );
    if ( v11 != &wil::details::g_processLocalData )
    {
LABEL_8:
      memset_0(&pExecInfo, 0, sizeof(pExecInfo));
      pExecInfo.cbSize = 112;
      pExecInfo.nShow = 1;
      pExecInfo.fMask = 67109184;
      pExecInfo.hwnd = (HWND)~a6;
      pExecInfo.lpFile = a2;
      *(_QWORD *)v42 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        v42,
        0);
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = 0;
      *(_QWORD *)v42 = 0;
      v14 = v12 + 1;
      if ( v12 + 1 < v12 )
      {
        v16 = 0;
        v15 = -2147024362;
      }
      else
      {
        *(_QWORD *)v42 = 0;
        v47 = 0;
        if ( is_mul_ok(v14, 2u) )
        {
          v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v14);
          *(_QWORD *)v42 = v13;
          v15 = v13 == 0 ? 0x8007000E : 0;
          if ( v13 )
            StringCchCopyNExW(v13, v12 + 1, a2, v12, bIgnoreCase, v40, v41);
          v16 = v13;
        }
        else
        {
          v16 = 0;
          v15 = -2147024362;
        }
      }
      if ( v15 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x23C,
          (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\downloadexecutionbroker.cpp",
          (const char *)(unsigned int)v15,
          (int)bIgnoreCase);
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      v18 = PathCchRemoveFileSpec(v13, v17);
      lpDirectory = pExecInfo.lpDirectory;
      if ( v18 >= 0 )
        lpDirectory = v13;
      pExecInfo.lpDirectory = lpDirectory;
      v20 = 0;
      v46 = 0;
      pszPath = 0;
      v44 = 0;
      v21 = 0;
      v22 = PathFindExtensionW(a2);
      if ( v22 )
      {
        v51 = &v44;
        v52 = 0;
        v53 = 1;
        p_pszPath = &pszPath;
        v49 = 0;
        v50 = 1;
        v23 = (unsigned int)anonymous_namespace_::GetHandlerForExtension(v22, &v49, &v52) >> 31;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&p_pszPath);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v51);
        if ( (unsigned __int8)v23 != 1 )
        {
          if ( CompareStringOrdinal(v22, -1, L".xsn", -1, 1) == 2 )
          {
            FileNameW = PathFindFileNameW(pszPath);
            if ( CompareStringOrdinal(FileNameW, -1, L"infopath.exe", -1, 1) == 2 )
            {
              v25 = -1;
              do
                ++v25;
              while ( a2[v25] );
              v26 = -1;
              do
                ++v26;
              while ( a3[v26] );
              v27 = v25 + v26 + 2;
              cotaskmem_string_failfast = (void **)wil::make_cotaskmem_string_failfast((wil *)&v47, 0, v27);
              if ( &v46 != (char **)cotaskmem_string_failfast )
              {
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &v46,
                  *cotaskmem_string_failfast);
                *cotaskmem_string_failfast = 0;
                v20 = v46;
              }
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v47);
              memset_0(v20, 0, 2 * v27);
              v29 = StringCchCopyW((unsigned __int16 *)v20, v27, a2);
              if ( v29 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x25E,
                  (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\downloadexecutionbroker.cpp",
                  (const char *)(unsigned int)v29,
                  bIgnoreCasea);
              v30 = v27 - (v25 + 1);
              v31 = (unsigned __int16 *)&v20[2 * v25 + 2];
              v32 = a3;
              v33 = StringCchCopyW(v31, v30, a3);
              if ( v33 < 0 )
                wil::details::in1diag3::_FailFast_Hr(
                  retaddr,
                  (void *)0x262,
                  (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\downloadexecutionbroker.cpp",
                  (const char *)(unsigned int)v33,
                  bIgnoreCasea);
              pExecInfo.lpFile = (LPCWSTR)v20;
              pExecInfo.fMask |= 0x400000u;
              a5 = 0;
              v21 = 1;
LABEL_43:
              v43 = 0;
              if ( v21 || (v34 = CompareStringOrdinal(v22, -1, L".url", -1, 1) == 2, v35 = 1, !v34) )
                v35 = 0;
              if ( !v32 || !*v32 )
                v8 = 0;
              if ( a5 || v35 )
              {
                if ( v8 )
                {
                  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
                  if ( (int)anonymous_namespace_::ExecutionServiceProvider::CreateAndInitialize(v32, &v43) >= 0 )
                  {
                    pExecInfo.fMask |= 0x8000000u;
                    pExecInfo.hInstApp = v43;
                  }
                }
              }
              if ( v44 )
              {
                pExecInfo.hkeyClass = v44;
                pExecInfo.fMask |= 3u;
              }
              if ( ShellExecuteExW(&pExecInfo) )
              {
                PIC = 0;
              }
              else
              {
                LastError = GetLastError();
                PIC = LastError;
                if ( LastError > 0 )
                  PIC = (unsigned __int16)LastError | 0x80070000;
                if ( PIC < 0 )
                  goto LABEL_63;
              }
              if ( pExecInfo.hProcess )
                CloseHandle(pExecInfo.hProcess);
LABEL_63:
              Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v43);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v44);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszPath);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v46);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v42);
              return (unsigned int)PIC;
            }
            v21 = 1;
          }
          else
          {
            v21 = 0;
          }
        }
        else
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pszPath,
            0);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &v44,
            0);
        }
      }
      else
      {
        v22 = &pszSubkey;
      }
      v32 = a3;
      goto LABEL_43;
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180025c60  mov     [rsp-8+arg_10], r8
0x180025c65  push    rbp
0x180025c66  push    rbx
0x180025c67  push    rsi
0x180025c68  push    rdi
0x180025c69  push    r12
0x180025c6b  push    r13
0x180025c6d  push    r14
0x180025c6f  push    r15
0x180025c71  lea     rbp, [rsp-28h]
0x180025c76  sub     rsp, 128h
0x180025c7d  mov     edi, r9d
0x180025c80  mov     r12, rdx
0x180025c83  xor     r13d, r13d
0x180025c86  mov     [rsp+160h+var_118], r13d
0x180025c8b  lea     rdx, [rsp+160h+var_118]; unsigned int *
0x180025c90  lea     r14d, [r13+1]
0x180025c94  mov     ecx, r14d; unsigned int
0x180025c97  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180025c9c  mov     ebx, eax
0x180025c9e  test    eax, eax
0x180025ca0  js      loc_180026100
0x180025ca6  cmp     edi, 79h ; 'y'
0x180025ca9  jnb     short loc_180025CF4
0x180025cab  mov     rcx, r12; pszPath
0x180025cae  call    cs:__imp_PathFindExtensionW
0x180025cb4  mov     rsi, rax
0x180025cb7  mov     rcx, rax; pszAssoc
0x180025cba  call    cs:__imp_AssocIsDangerous
0x180025cc0  test    eax, eax
0x180025cc2  jz      short loc_180025CF4
0x180025cc4  lea     rdi, off_18003F090; ".asp"
0x180025ccb  lea     r15, ?g_processLocalData@details@wil@@3V?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@2@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> wil::details::g_processLocalData
0x180025cd2  mov     rdx, [rdi]
0x180025cd5  mov     rcx, rsi
0x180025cd8  call    cs:__imp__o__wcsicmp
0x180025cde  test    eax, eax
0x180025ce0  jz      short loc_180025CEB
0x180025ce2  add     rdi, 8
0x180025ce6  cmp     rdi, r15
0x180025ce9  jnz     short loc_180025CD2
0x180025ceb  cmp     rdi, r15
0x180025cee  jz      loc_180026100
0x180025cf4  mov     ebx, 70h ; 'p'
0x180025cf9  mov     r8d, ebx; Size
0x180025cfc  xor     edx, edx; Val
0x180025cfe  lea     rcx, [rbp+60h+pExecInfo]; void *
0x180025d02  call    memset_0
0x180025d07  mov     [rbp+60h+pExecInfo.cbSize], ebx
0x180025d0a  mov     [rbp+60h+pExecInfo.nShow], r14d
0x180025d0e  mov     [rbp+60h+pExecInfo.fMask], 4000140h
0x180025d15  mov     eax, [rbp+60h+arg_28]
0x180025d1b  not     eax
0x180025d1d  cdqe
0x180025d1f  mov     [rbp+60h+pExecInfo.hwnd], rax
0x180025d23  mov     [rbp+60h+pExecInfo.lpFile], r12
0x180025d27  mov     qword ptr [rsp+160h+var_118], r13
0x180025d2c  xor     edx, edx
0x180025d2e  lea     rcx, [rsp+160h+var_118]
0x180025d33  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025d38  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025d3c  inc     rsi
0x180025d3f  cmp     [r12+rsi*2], r13w
0x180025d44  jnz     short loc_180025D3C
0x180025d46  mov     rbx, r13
0x180025d49  mov     qword ptr [rsp+160h+var_118], rbx
0x180025d4e  lea     r15, [rsi+1]
0x180025d52  cmp     r15, rsi
0x180025d55  jb      short loc_180025DB4
0x180025d57  mov     qword ptr [rsp+160h+var_118], rbx
0x180025d5c  mov     [rsp+160h+var_F0], r13
0x180025d61  mov     eax, 2
0x180025d66  mul     r15
0x180025d69  test    rdx, rdx
0x180025d6c  jnz     short loc_180025DAA
0x180025d6e  mov     rcx, rax; cb
0x180025d71  call    cs:__imp_CoTaskMemAlloc
0x180025d77  mov     rbx, rax
0x180025d7a  mov     qword ptr [rsp+160h+var_118], rax
0x180025d7f  neg     rax
0x180025d82  sbb     edi, edi
0x180025d84  not     edi
0x180025d86  and     edi, 8007000Eh
0x180025d8c  test    rbx, rbx
0x180025d8f  jz      short loc_180025DA2
0x180025d91  mov     r9, rsi; unsigned __int64
0x180025d94  mov     r8, r12; unsigned __int16 *
0x180025d97  mov     rdx, r15; unsigned __int64
0x180025d9a  mov     rcx, rbx; unsigned __int16 *
0x180025d9d  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180025da2  mov     rax, rbx
0x180025da5  xor     r15d, r15d
0x180025da8  jmp     short loc_180025DBF
0x180025daa  mov     rax, r13
0x180025dad  mov     edi, 80070216h
0x180025db2  jmp     short loc_180025DA5
0x180025db4  xor     r15d, r15d
0x180025db7  mov     eax, r15d
0x180025dba  mov     edi, 80070216h
0x180025dbf  mov     rcx, [rbp+68h]; this
0x180025dc3  test    edi, edi
0x180025dc5  jns     short loc_180025DDC
0x180025dc7  mov     r9d, edi; char *
0x180025dca  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180025dd1  mov     edx, 23Ch; void *
0x180025dd6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025ddc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180025de0  inc     rdx; cchPath
0x180025de3  cmp     [rax+rdx*2], r15w
0x180025de8  jnz     short loc_180025DE0
0x180025dea  mov     rcx, rbx; pszPath
0x180025ded  call    cs:__imp_PathCchRemoveFileSpec
0x180025df3  mov     rcx, [rbp+60h+pExecInfo.lpDirectory]
0x180025df7  test    eax, eax
0x180025df9  cmovns  rcx, rbx
0x180025dfd  mov     [rbp+60h+pExecInfo.lpDirectory], rcx
0x180025e01  mov     rbx, r15
0x180025e04  mov     [rsp+160h+var_F8], rbx
0x180025e09  mov     [rsp+160h+pszPath], r15
0x180025e0e  mov     [rsp+160h+var_108], r15
0x180025e13  mov     sil, r15b
0x180025e16  mov     rcx, r12; pszPath
0x180025e19  call    cs:__imp_PathFindExtensionW
0x180025e1f  mov     r13, rax
0x180025e22  test    rax, rax
0x180025e25  jz      loc_180025FF4
0x180025e2b  lea     rax, [rsp+160h+var_108]
0x180025e30  mov     [rbp+60h+var_D0], rax
0x180025e34  mov     [rbp+60h+var_C8], r15
0x180025e38  mov     [rbp+60h+var_C0], r14b
0x180025e3c  lea     rax, [rsp+160h+pszPath]
0x180025e41  mov     [rsp+160h+var_E8], rax
0x180025e46  mov     [rbp+60h+var_E0], r15
0x180025e4a  mov     [rbp+60h+var_D8], r14b
0x180025e4e  lea     r8, [rbp+60h+var_C8]
0x180025e52  lea     rdx, [rbp+60h+var_E0]
0x180025e56  mov     rcx, r13
0x180025e59  call    _anonymous_namespace___GetHandlerForExtension
0x180025e5e  mov     edi, eax
0x180025e60  shr     edi, 1Fh
0x180025e63  lea     rcx, [rsp+160h+var_E8]
0x180025e68  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180025e6d  nop
0x180025e6e  lea     rcx, [rbp+60h+var_D0]
0x180025e72  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180025e77  xor     dil, r14b
0x180025e7a  jz      loc_180025FDA
0x180025e80  mov     dword ptr [rsp+160h+bIgnoreCase], r14d; bIgnoreCase
0x180025e85  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025e89  mov     r9d, esi; cchCount2
0x180025e8c  lea     r8, String2; ".xsn"
0x180025e93  mov     edx, esi; cchCount1
0x180025e95  mov     rcx, r13; lpString1
0x180025e98  call    cs:__imp_CompareStringOrdinal
0x180025e9e  cmp     eax, 2
0x180025ea1  jnz     loc_180025FD5
0x180025ea7  mov     [rsp+160h+var_120], r14b
0x180025eac  mov     rcx, [rsp+160h+pszPath]; pszPath
0x180025eb1  call    cs:__imp_PathFindFileNameW
0x180025eb7  mov     rcx, rax; lpString1
0x180025eba  mov     dword ptr [rsp+160h+bIgnoreCase], r14d; int
0x180025ebf  mov     r9d, esi; cchCount2
0x180025ec2  lea     r8, aInfopathExe; "infopath.exe"
0x180025ec9  mov     edx, esi; cchCount1
0x180025ecb  call    cs:__imp_CompareStringOrdinal
0x180025ed1  cmp     eax, 2
0x180025ed4  jnz     loc_180025FCE
0x180025eda  mov     rdi, rsi
0x180025edd  inc     rdi
0x180025ee0  cmp     [r12+rdi*2], r15w
0x180025ee5  jnz     short loc_180025EDD
0x180025ee7  mov     rax, rsi
0x180025eea  mov     rcx, [rbp+60h+arg_10]
0x180025ef1  inc     rax
0x180025ef4  cmp     [rcx+rax*2], r15w
0x180025ef9  jnz     short loc_180025EF1
0x180025efb  lea     rsi, [rax+2]
0x180025eff  add     rsi, rdi
0x180025f02  mov     r8, rsi; unsigned __int64
0x180025f05  xor     edx, edx; unsigned __int16 *
0x180025f07  lea     rcx, [rsp+160h+var_F0]; this
0x180025f0c  call    ?make_cotaskmem_string_failfast@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_failfast(ushort const *,unsigned __int64)
0x180025f11  mov     r15, rax
0x180025f14  lea     rax, [rsp+160h+var_F8]
0x180025f19  cmp     rax, r15
0x180025f1c  jz      short loc_180025F37
0x180025f1e  mov     rdx, [r15]
0x180025f21  lea     rcx, [rsp+160h+var_F8]
0x180025f26  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025f2b  mov     qword ptr [r15], 0
0x180025f32  mov     rbx, [rsp+160h+var_F8]
0x180025f37  lea     rcx, [rsp+160h+var_F0]
0x180025f3c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180025f41  lea     r8, [rsi+rsi]; Size
0x180025f45  xor     edx, edx; Val
0x180025f47  mov     rcx, rbx; void *
0x180025f4a  call    memset_0
0x180025f4f  mov     r8, r12; unsigned __int16 *
0x180025f52  mov     rdx, rsi; unsigned __int64
0x180025f55  mov     rcx, rbx; unsigned __int16 *
0x180025f58  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025f5d  mov     rcx, [rbp+68h]; this
0x180025f61  xor     r15d, r15d
0x180025f64  test    eax, eax
0x180025f66  jns     short loc_180025F7D
0x180025f68  mov     r9d, eax; char *
0x180025f6b  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180025f72  mov     edx, 25Eh; void *
0x180025f77  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025f7d  lea     rax, [rdi+1]
0x180025f81  sub     rsi, rax
0x180025f84  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x180025f88  mov     rdi, [rbp+60h+arg_10]
0x180025f8f  mov     r8, rdi; unsigned __int16 *
0x180025f92  mov     rdx, rsi; unsigned __int64
0x180025f95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025f9a  mov     rcx, [rbp+68h]; this
0x180025f9e  test    eax, eax
0x180025fa0  jns     short loc_180025FB7
0x180025fa2  mov     r9d, eax; char *
0x180025fa5  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180025fac  mov     edx, 262h; void *
0x180025fb1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025fb7  mov     [rbp+60h+pExecInfo.lpFile], rbx
0x180025fbb  bts     [rbp+60h+pExecInfo.fMask], 16h
0x180025fc0  mov     [rbp+60h+arg_20], r15d
0x180025fc7  mov     sil, [rsp+160h+var_120]
0x180025fcc  jmp     short loc_180026002
0x180025fce  mov     sil, [rsp+160h+var_120]
0x180025fd3  jmp     short loc_180025FFB
0x180025fd5  mov     sil, r15b
0x180025fd8  jmp     short loc_180025FFB
0x180025fda  xor     edx, edx
0x180025fdc  lea     rcx, [rsp+160h+pszPath]
0x180025fe1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180025fe6  xor     edx, edx
0x180025fe8  lea     rcx, [rsp+160h+var_108]
0x180025fed  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180025ff2  jmp     short loc_180025FFB
0x180025ff4  lea     r13, pszSubkey
0x180025ffb  mov     rdi, [rbp+60h+arg_10]
0x180026002  mov     [rsp+160h+var_110], r15
0x180026007  test    sil, sil
0x18002600a  jnz     short loc_180026030
0x18002600c  mov     dword ptr [rsp+160h+bIgnoreCase], r14d; bIgnoreCase
0x180026011  or      r9d, 0FFFFFFFFh; cchCount2
0x180026015  lea     r8, aUrl; ".url"
0x18002601c  or      edx, r9d; cchCount1
0x18002601f  mov     rcx, r13; lpString1
0x180026022  call    cs:__imp_CompareStringOrdinal
0x180026028  cmp     eax, 2
0x18002602b  mov     al, r14b
0x18002602e  jz      short loc_180026033
0x180026030  mov     al, r15b
0x180026033  test    rdi, rdi
0x180026036  jz      short loc_18002603E
0x180026038  cmp     [rdi], r15w
0x18002603c  jnz     short loc_180026041
0x18002603e  mov     r14b, r15b
0x180026041  cmp     [rbp+60h+arg_20], r15d
0x180026048  jnz     short loc_18002604E
0x18002604a  test    al, al
0x18002604c  jz      short loc_18002607C
0x18002604e  test    r14b, r14b
0x180026051  jz      short loc_18002607C
0x180026053  lea     rcx, [rsp+160h+var_110]
0x180026058  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002605d  lea     rdx, [rsp+160h+var_110]
0x180026062  mov     rcx, rdi
0x180026065  call    _anonymous_namespace___ExecutionServiceProvider__CreateAndInitialize
0x18002606a  test    eax, eax
0x18002606c  js      short loc_18002607C
0x18002606e  bts     [rbp+60h+pExecInfo.fMask], 1Bh
0x180026073  mov     rax, [rsp+160h+var_110]
0x180026078  mov     [rbp+60h+pExecInfo.hInstApp], rax
0x18002607c  mov     rax, [rsp+160h+var_108]
0x180026081  test    rax, rax
0x180026084  jz      short loc_18002608E
0x180026086  mov     [rbp+60h+pExecInfo.hkeyClass], rax
0x18002608a  or      [rbp+60h+pExecInfo.fMask], 3
0x18002608e  lea     rcx, [rbp+60h+pExecInfo]; pExecInfo
0x180026092  call    cs:__imp_ShellExecuteExW
0x180026098  test    eax, eax
0x18002609a  jz      short loc_1800260A1
0x18002609c  mov     ebx, r15d
0x18002609f  jmp     short loc_1800260BA
0x1800260a1  call    cs:__imp_GetLastError
0x1800260a7  mov     ebx, eax
0x1800260a9  test    eax, eax
0x1800260ab  jle     short loc_1800260B6
0x1800260ad  movzx   ebx, ax
0x1800260b0  or      ebx, 80070000h
0x1800260b6  test    ebx, ebx
0x1800260b8  js      short loc_1800260CA
0x1800260ba  mov     rcx, [rbp+60h+pExecInfo.hProcess]; hObject
0x1800260be  test    rcx, rcx
0x1800260c1  jz      short loc_1800260CA
0x1800260c3  call    cs:__imp_CloseHandle
0x1800260c9  nop
0x1800260ca  lea     rcx, [rsp+160h+var_110]
  ... truncated ...
```

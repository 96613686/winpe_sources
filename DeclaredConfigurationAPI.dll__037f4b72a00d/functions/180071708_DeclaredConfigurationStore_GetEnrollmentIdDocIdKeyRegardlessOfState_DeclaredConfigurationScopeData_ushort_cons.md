# DeclaredConfigurationStore_GetEnrollmentIdDocIdKeyRegardlessOfState(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)

- ea: `0x180071708`
- end: `0x180071b8c`
- name: `?DeclaredConfigurationStore_GetEnrollmentIdDocIdKeyRegardlessOfState@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z`
- size: `1156`
- prototype: `__int64 __fastcall(struct DeclaredConfigurationScopeData *, const unsigned __int16 *, HKEY *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180066550`

## callees

- `0x18000be80`
- `0x1800117dc`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x1800600bc`
- `0x180071708`
- `0x18008cec8`
- `0x18008f3bc`
- `0x180100418`
- `0x180100ad8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800717d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007185d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800718d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180071ac6`
- `OLEAUT32!__imp_SysFreeString` at `0x180071b24`
- `OLEAUT32!__imp_SysFreeString` at `0x1800717d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007185d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800718d4`
- `OLEAUT32!__imp_SysFreeString` at `0x180071ac6`
- `OLEAUT32!__imp_SysFreeString` at `0x180071b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800717e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800717e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071871`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b38`

## string_xrefs

- `0x180071794`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x180071825`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007189c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeclaredConfigurationStore_GetEnrollmentIdDocIdKeyRegardlessOfState(
        struct DeclaredConfigurationScopeData *a1,
        const unsigned __int16 *a2,
        HKEY *a3)
{
  int RegKeyPathForEnrollmentId; // eax
  unsigned int v7; // ebx
  BSTR *v8; // rax
  unsigned int i; // edi
  int v10; // edi
  BSTR *v11; // rax
  unsigned int j; // ebx
  int DocIdSubKeys; // eax
  unsigned int k; // ebx
  unsigned int m; // edi
  unsigned int v16; // ecx
  int v17; // ebx
  unsigned int v18; // ebx
  HKEY v19; // rax
  BSTR *v20; // rax
  unsigned int n; // ebx
  BSTR *v23; // rax
  unsigned int v24; // ebx
  int v25; // [rsp+20h] [rbp-99h]
  void *Block; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-71h] BYREF
  LPCWSTR v28; // [rsp+50h] [rbp-69h] BYREF
  HKEY v29; // [rsp+58h] [rbp-61h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-59h] BYREF
  HKEY v31; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  HKEY *v33; // [rsp+78h] [rbp-41h] BYREF
  HKEY v34; // [rsp+80h] [rbp-39h] BYREF
  char v35; // [rsp+88h] [rbp-31h]
  void *p_hKey; // [rsp+90h] [rbp-29h] BYREF
  HKEY v37; // [rsp+98h] [rbp-21h] BYREF
  char v38; // [rsp+A0h] [rbp-19h]
  unsigned __int16 **v39; // [rsp+A8h] [rbp-11h]
  char v40; // [rsp+B0h] [rbp-9h]
  void **p_Block; // [rsp+B8h] [rbp-1h]
  LPVOID *p_pv; // [rsp+C0h] [rbp+7h]
  unsigned int *v43; // [rsp+C8h] [rbp+Fh]
  char v44; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  LPVOID pv; // [rsp+130h] [rbp+77h] BYREF
  unsigned int v47; // [rsp+138h] [rbp+7Fh] BYREF

  hKey = 0;
  v31 = 0;
  Block = 0;
  lpSubKey = 0;
  pv = 0;
  v47 = 0;
  if ( a3 && a1 )
  {
    p_Block = &Block;
    p_pv = &pv;
    v43 = &v47;
    v44 = 1;
    *a3 = 0;
    RegKeyPathForEnrollmentId = GetRegKeyPathForEnrollmentId(a1, &Block);
    v7 = RegKeyPathForEnrollmentId;
    if ( RegKeyPathForEnrollmentId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F1,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)RegKeyPathForEnrollmentId,
        v25);
      if ( Block )
        operator delete(Block);
      v8 = (BSTR *)pv;
      if ( pv )
      {
        for ( i = 0; i < v47; v8 = (BSTR *)pv )
          SysFreeString(v8[i++]);
        CoTaskMemFree(v8);
      }
      goto LABEL_52;
    }
    p_hKey = &hKey;
    v37 = 0;
    v38 = 1;
    v10 = DCCDNUtil_GetHKey((LPCWSTR)Block, &v37, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v10,
        v25);
      if ( Block )
        operator delete(Block);
      v11 = (BSTR *)pv;
      if ( !pv )
        goto LABEL_17;
      for ( j = 0; j < v47; v11 = (BSTR *)pv )
        SysFreeString(v11[j++]);
LABEL_16:
      CoTaskMemFree(v11);
LABEL_17:
      v7 = v10;
LABEL_52:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v7;
    }
    DocIdSubKeys = GetDocIdSubKeys(hKey);
    v10 = DocIdSubKeys;
    if ( DocIdSubKeys < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)DocIdSubKeys,
        v25);
      if ( Block )
        operator delete(Block);
      v11 = (BSTR *)pv;
      if ( !pv )
        goto LABEL_17;
      for ( k = 0; k < v47; v11 = (BSTR *)pv )
        SysFreeString(v11[k++]);
      goto LABEL_16;
    }
    for ( m = 0; ; ++m )
    {
      v16 = v47;
      if ( m >= v47 )
        break;
      if ( (int)DCStringCchPrintfAllStrings(&lpSubKey, qword_18018A420, 3, *(_QWORD *)a1, *((_QWORD *)pv + m), a2) >= 0 )
      {
        p_hKey = &lpSubKey;
        LOBYTE(v37) = 1;
        v33 = &v31;
        v34 = 0;
        v35 = 1;
        v17 = DCCDNUtil_GetHKey(lpSubKey, &v34, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v33);
        if ( v17 >= 0 && v31 )
        {
          v27 = 0;
          v39 = &v27;
          v40 = 1;
          if ( DCCDNUtil_GetRegistryString(v31, 0, L"MostRecentVersion", &v27) >= 0 )
          {
            v28 = 0;
            if ( (int)DCStringCchPrintfAllStrings(&v28, qword_18018A558, 4, *(_QWORD *)a1, *((_QWORD *)pv + m), a2, v27) >= 0 )
            {
              v29 = 0;
              v33 = &v29;
              v34 = 0;
              v35 = 1;
              v18 = (unsigned int)DCCDNUtil_GetHKey(v28, &v34, 0) >> 31;
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v33);
              if ( (unsigned __int8)v18 != 1 )
              {
                v19 = v29;
                if ( v29 )
                {
                  v29 = 0;
                  *a3 = v19;
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
                  if ( v28 )
                  {
                    operator delete((void *)v28);
                    v28 = 0;
                  }
                  operator delete(v27);
                  v27 = 0;
                  if ( lpSubKey )
                    operator delete((void *)lpSubKey);
                  if ( Block )
                    operator delete(Block);
                  v20 = (BSTR *)pv;
                  if ( pv )
                  {
                    for ( n = 0; n < v47; v20 = (BSTR *)pv )
                      SysFreeString(v20[n++]);
                    CoTaskMemFree(v20);
                  }
                  v7 = 0;
                  goto LABEL_52;
                }
              }
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
            }
            if ( v28 )
            {
              operator delete((void *)v28);
              v28 = 0;
            }
          }
          v40 = 0;
          operator delete(v27);
          v27 = 0;
        }
        LOBYTE(v37) = 0;
        if ( lpSubKey )
          operator delete((void *)lpSubKey);
      }
    }
    if ( Block )
    {
      operator delete(Block);
      v16 = v47;
    }
    v23 = (BSTR *)pv;
    if ( pv )
    {
      v24 = 0;
      if ( v16 )
      {
        do
        {
          SysFreeString(v23[v24++]);
          v23 = (BSTR *)pv;
        }
        while ( v24 < v47 );
      }
      CoTaskMemFree(v23);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147500037LL;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180071708  mov     [rsp-8+arg_0], rbx
0x18007170d  mov     [rsp-8+arg_18], r9d
0x180071712  push    rbp
0x180071713  push    rsi
0x180071714  push    rdi
0x180071715  push    r12
0x180071717  push    r13
0x180071719  push    r14
0x18007171b  push    r15
0x18007171d  lea     rbp, [rsp-27h]
0x180071722  sub     rsp, 0E0h
0x180071729  mov     r14, r8
0x18007172c  mov     r12, rdx
0x18007172f  mov     rsi, rcx
0x180071732  xor     r13d, r13d
0x180071735  mov     [rbp+57h+hKey], r13
0x180071739  mov     [rbp+57h+var_A8], r13
0x18007173d  mov     [rbp+57h+Block], r13
0x180071741  mov     [rbp+57h+lpSubKey], r13
0x180071745  mov     [rbp+57h+pv], r13
0x180071749  mov     [rbp+57h+arg_18], r13d
0x18007174d  test    r8, r8
0x180071750  jz      loc_180071B59
0x180071756  test    rcx, rcx
0x180071759  jz      loc_180071B59
0x18007175f  lea     rax, [rbp+57h+Block]
0x180071763  mov     [rbp+57h+var_58], rax
0x180071767  lea     rax, [rbp+57h+pv]
0x18007176b  mov     [rbp+57h+var_50], rax
0x18007176f  lea     rax, [rbp+57h+arg_18]
0x180071773  mov     [rbp+57h+var_48], rax
0x180071777  mov     [rbp+57h+var_40], 1
0x18007177b  mov     [r8], r13
0x18007177e  lea     rdx, [rbp+57h+Block]
0x180071782  call    GetRegKeyPathForEnrollmentId
0x180071787  mov     ebx, eax
0x180071789  test    eax, eax
0x18007178b  jns     short loc_1800717EF
0x18007178d  mov     rcx, [rbp+5Fh]; this
0x180071791  mov     r9d, eax; char *
0x180071794  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007179b  mov     edx, 7F1h; void *
0x1800717a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800717a5  nop
0x1800717a6  mov     rcx, [rbp+57h+Block]; Block
0x1800717aa  test    rcx, rcx
0x1800717ad  jz      short loc_1800717B4
0x1800717af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800717b4  mov     rax, [rbp+57h+pv]
0x1800717b8  test    rax, rax
0x1800717bb  jz      loc_180071AE3
0x1800717c1  mov     edi, r13d
0x1800717c4  cmp     [rbp+57h+arg_18], r13d
0x1800717c8  jbe     short loc_1800717E1
0x1800717ca  mov     ecx, edi
0x1800717cc  mov     rcx, [rax+rcx*8]; bstrString
0x1800717d0  call    cs:__imp_SysFreeString
0x1800717d6  inc     edi
0x1800717d8  mov     rax, [rbp+57h+pv]
0x1800717dc  cmp     edi, [rbp+57h+arg_18]
0x1800717df  jb      short loc_1800717CA
0x1800717e1  mov     rcx, rax; pv
0x1800717e4  call    cs:__imp_CoTaskMemFree
0x1800717ea  jmp     loc_180071AE3
0x1800717ef  lea     rax, [rbp+57h+hKey]
0x1800717f3  mov     [rbp+57h+var_80], rax
0x1800717f7  mov     [rbp+57h+var_78], r13
0x1800717fb  mov     [rbp+57h+var_70], 1
0x1800717ff  xor     r8d, r8d; int
0x180071802  lea     rdx, [rbp+57h+var_78]; HKEY *
0x180071806  mov     rcx, [rbp+57h+Block]; lpSubKey
0x18007180a  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18007180f  mov     edi, eax
0x180071811  lea     rcx, [rbp+57h+var_80]
0x180071815  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007181a  test    edi, edi
0x18007181c  jns     short loc_18007187E
0x18007181e  mov     rcx, [rbp+5Fh]; this
0x180071822  mov     r9d, edi; char *
0x180071825  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007182c  mov     edx, 7F5h; void *
0x180071831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071836  nop
0x180071837  mov     rcx, [rbp+57h+Block]; Block
0x18007183b  test    rcx, rcx
0x18007183e  jz      short loc_180071845
0x180071840  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071845  mov     rax, [rbp+57h+pv]
0x180071849  test    rax, rax
0x18007184c  jz      short loc_180071877
0x18007184e  mov     ebx, r13d
0x180071851  cmp     [rbp+57h+arg_18], r13d
0x180071855  jbe     short loc_18007186E
0x180071857  mov     ecx, ebx
0x180071859  mov     rcx, [rax+rcx*8]; bstrString
0x18007185d  call    cs:__imp_SysFreeString
0x180071863  inc     ebx
0x180071865  mov     rax, [rbp+57h+pv]
0x180071869  cmp     ebx, [rbp+57h+arg_18]
0x18007186c  jb      short loc_180071857
0x18007186e  mov     rcx, rax; pv
0x180071871  call    cs:__imp_CoTaskMemFree
0x180071877  mov     ebx, edi
0x180071879  jmp     loc_180071AE3
0x18007187e  lea     r8, [rbp+57h+pv]
0x180071882  lea     rdx, [rbp+57h+arg_18]
0x180071886  mov     rcx, [rbp+57h+hKey]; hKey
0x18007188a  call    GetDocIdSubKeys
0x18007188f  mov     edi, eax
0x180071891  test    eax, eax
0x180071893  jns     short loc_1800718E7
0x180071895  mov     rcx, [rbp+5Fh]; this
0x180071899  mov     r9d, eax; char *
0x18007189c  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800718a3  mov     edx, 7F7h; void *
0x1800718a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800718ad  nop
0x1800718ae  mov     rcx, [rbp+57h+Block]; Block
0x1800718b2  test    rcx, rcx
0x1800718b5  jz      short loc_1800718BC
0x1800718b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800718bc  mov     rax, [rbp+57h+pv]
0x1800718c0  test    rax, rax
0x1800718c3  jz      short loc_180071877
0x1800718c5  mov     ebx, r13d
0x1800718c8  cmp     [rbp+57h+arg_18], r13d
0x1800718cc  jbe     short loc_18007186E
0x1800718ce  mov     ecx, ebx
0x1800718d0  mov     rcx, [rax+rcx*8]; bstrString
0x1800718d4  call    cs:__imp_SysFreeString
0x1800718da  inc     ebx
0x1800718dc  mov     rax, [rbp+57h+pv]
0x1800718e0  cmp     ebx, [rbp+57h+arg_18]
0x1800718e3  jb      short loc_1800718CE
0x1800718e5  jmp     short loc_18007186E
0x1800718e7  mov     edi, r13d
0x1800718ea  mov     ecx, [rbp+57h+arg_18]
0x1800718ed  cmp     edi, ecx
0x1800718ef  jnb     loc_180071AFA
0x1800718f5  mov     r15d, edi
0x1800718f8  mov     [rsp+110h+var_E8], r12
0x1800718fd  mov     rax, [rbp+57h+pv]
0x180071901  mov     rcx, [rax+r15*8]
0x180071905  mov     [rsp+110h+var_F0], rcx
0x18007190a  mov     r9, [rsi]
0x18007190d  mov     r8d, 3
0x180071913  mov     rdx, cs:qword_18018A420
0x18007191a  lea     rcx, [rbp+57h+lpSubKey]
0x18007191e  call    DCStringCchPrintfAllStrings
0x180071923  test    eax, eax
0x180071925  js      loc_180071A5B
0x18007192b  lea     rax, [rbp+57h+lpSubKey]
0x18007192f  mov     [rbp+57h+var_80], rax
0x180071933  mov     byte ptr [rbp+57h+var_78], 1
0x180071937  lea     rax, [rbp+57h+var_A8]
0x18007193b  mov     [rbp+57h+var_98], rax
0x18007193f  mov     [rbp+57h+var_90], r13
0x180071943  mov     [rbp+57h+var_88], 1
0x180071947  xor     r8d, r8d; int
0x18007194a  lea     rdx, [rbp+57h+var_90]; HKEY *
0x18007194e  mov     rcx, [rbp+57h+lpSubKey]; lpSubKey
0x180071952  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x180071957  mov     ebx, eax
0x180071959  lea     rcx, [rbp+57h+var_98]
0x18007195d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180071962  test    ebx, ebx
0x180071964  js      loc_180071A49
0x18007196a  mov     rcx, [rbp+57h+var_A8]; HKEY
0x18007196e  test    rcx, rcx
0x180071971  jz      loc_180071A49
0x180071977  mov     [rbp+57h+var_C8], r13
0x18007197b  lea     rax, [rbp+57h+var_C8]
0x18007197f  mov     [rbp+57h+var_68], rax
0x180071983  mov     [rbp+57h+var_60], 1
0x180071987  lea     r9, [rbp+57h+var_C8]; unsigned __int16 **
0x18007198b  lea     r8, aMostrecentvers; "MostRecentVersion"
0x180071992  xor     edx, edx; unsigned __int16 *
0x180071994  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180071999  test    eax, eax
0x18007199b  js      loc_180071A38
0x1800719a1  mov     [rbp+57h+var_C0], r13
0x1800719a5  mov     rax, [rbp+57h+var_C8]
0x1800719a9  mov     [rsp+110h+var_E0], rax
0x1800719ae  mov     [rsp+110h+var_E8], r12
0x1800719b3  mov     rax, [rbp+57h+pv]
0x1800719b7  mov     rcx, [rax+r15*8]
0x1800719bb  mov     [rsp+110h+var_F0], rcx
0x1800719c0  mov     r9, [rsi]
0x1800719c3  mov     r8d, 4
0x1800719c9  mov     rdx, cs:qword_18018A558
0x1800719d0  lea     rcx, [rbp+57h+var_C0]
0x1800719d4  call    DCStringCchPrintfAllStrings
0x1800719d9  test    eax, eax
0x1800719db  js      short loc_180071A26
0x1800719dd  mov     [rbp+57h+var_B8], r13
0x1800719e1  lea     rax, [rbp+57h+var_B8]
0x1800719e5  mov     [rbp+57h+var_98], rax
0x1800719e9  mov     [rbp+57h+var_90], r13
0x1800719ed  mov     [rbp+57h+var_88], 1
0x1800719f1  xor     r8d, r8d; int
0x1800719f4  lea     rdx, [rbp+57h+var_90]; HKEY *
0x1800719f8  mov     rcx, [rbp+57h+var_C0]; lpSubKey
0x1800719fc  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x180071a01  mov     ebx, eax
0x180071a03  shr     ebx, 1Fh
0x180071a06  lea     rcx, [rbp+57h+var_98]
0x180071a0a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180071a0f  xor     bl, 1
0x180071a12  jz      short loc_180071A1D
0x180071a14  mov     rax, [rbp+57h+var_B8]
0x180071a18  test    rax, rax
0x180071a1b  jnz     short loc_180071A62
0x180071a1d  lea     rcx, [rbp+57h+var_B8]
0x180071a21  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071a26  mov     rcx, [rbp+57h+var_C0]; Block
0x180071a2a  test    rcx, rcx
0x180071a2d  jz      short loc_180071A38
0x180071a2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a34  mov     [rbp+57h+var_C0], r13
0x180071a38  mov     [rbp+57h+var_60], r13b
0x180071a3c  mov     rcx, [rbp+57h+var_C8]; Block
0x180071a40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a45  mov     [rbp+57h+var_C8], r13
0x180071a49  mov     byte ptr [rbp+57h+var_78], r13b
0x180071a4d  mov     rcx, [rbp+57h+lpSubKey]; Block
0x180071a51  test    rcx, rcx
0x180071a54  jz      short loc_180071A5B
0x180071a56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a5b  inc     edi
0x180071a5d  jmp     loc_1800718EA
0x180071a62  mov     [rbp+57h+var_B8], r13
0x180071a66  mov     [r14], rax
0x180071a69  lea     rcx, [rbp+57h+var_B8]
0x180071a6d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071a72  mov     rcx, [rbp+57h+var_C0]; Block
0x180071a76  test    rcx, rcx
0x180071a79  jz      short loc_180071A84
0x180071a7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a80  mov     [rbp+57h+var_C0], r13
0x180071a84  mov     rcx, [rbp+57h+var_C8]; Block
0x180071a88  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a8d  mov     [rbp+57h+var_C8], r13
0x180071a91  mov     rcx, [rbp+57h+lpSubKey]; Block
0x180071a95  test    rcx, rcx
0x180071a98  jz      short loc_180071AA0
0x180071a9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071a9f  nop
0x180071aa0  mov     rcx, [rbp+57h+Block]; Block
0x180071aa4  test    rcx, rcx
0x180071aa7  jz      short loc_180071AAE
0x180071aa9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071aae  mov     rax, [rbp+57h+pv]
0x180071ab2  test    rax, rax
0x180071ab5  jz      short loc_180071AE0
0x180071ab7  mov     ebx, r13d
0x180071aba  cmp     [rbp+57h+arg_18], r13d
0x180071abe  jbe     short loc_180071AD7
0x180071ac0  mov     ecx, ebx
0x180071ac2  mov     rcx, [rax+rcx*8]; bstrString
0x180071ac6  call    cs:__imp_SysFreeString
0x180071acc  inc     ebx
0x180071ace  mov     rax, [rbp+57h+pv]
0x180071ad2  cmp     ebx, [rbp+57h+arg_18]
0x180071ad5  jb      short loc_180071AC0
0x180071ad7  mov     rcx, rax; pv
0x180071ada  call    cs:__imp_CoTaskMemFree
0x180071ae0  mov     ebx, r13d
0x180071ae3  lea     rcx, [rbp+57h+var_A8]
0x180071ae7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071aec  nop
0x180071aed  lea     rcx, [rbp+57h+hKey]
0x180071af1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071af6  mov     eax, ebx
0x180071af8  jmp     short loc_180071B71
0x180071afa  mov     rax, [rbp+57h+Block]
0x180071afe  test    rax, rax
0x180071b01  jz      short loc_180071B0E
0x180071b03  mov     rcx, rax; Block
0x180071b06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071b0b  mov     ecx, [rbp+57h+arg_18]
0x180071b0e  mov     rax, [rbp+57h+pv]
0x180071b12  test    rax, rax
0x180071b15  jz      short loc_180071B3F
0x180071b17  mov     ebx, r13d
0x180071b1a  test    ecx, ecx
0x180071b1c  jz      short loc_180071B35
0x180071b1e  mov     ecx, ebx
0x180071b20  mov     rcx, [rax+rcx*8]; bstrString
0x180071b24  call    cs:__imp_SysFreeString
0x180071b2a  inc     ebx
0x180071b2c  mov     rax, [rbp+57h+pv]
0x180071b30  cmp     ebx, [rbp+57h+arg_18]
0x180071b33  jb      short loc_180071B1E
0x180071b35  mov     rcx, rax; pv
0x180071b38  call    cs:__imp_CoTaskMemFree
0x180071b3e  nop
0x180071b3f  lea     rcx, [rbp+57h+var_A8]
0x180071b43  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071b48  nop
0x180071b49  lea     rcx, [rbp+57h+hKey]
  ... truncated ...
```

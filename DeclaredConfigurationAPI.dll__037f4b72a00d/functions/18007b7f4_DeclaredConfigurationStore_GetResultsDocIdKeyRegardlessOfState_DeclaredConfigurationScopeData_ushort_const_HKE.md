# DeclaredConfigurationStore_GetResultsDocIdKeyRegardlessOfState(DeclaredConfigurationScopeData *,ushort const *,HKEY__ * *,int)

- ea: `0x18007b7f4`
- end: `0x18007bc78`
- name: `?DeclaredConfigurationStore_GetResultsDocIdKeyRegardlessOfState@@YAJPEAUDeclaredConfigurationScopeData@@PEBGPEAPEAUHKEY__@@H@Z`
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
- `0x18007b7f4`
- `0x18008cec8`
- `0x18008f3bc`
- `0x180100418`
- `0x180100ad8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18007b8bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b949`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bbb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bc10`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b8bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b949`
- `OLEAUT32!__imp_SysFreeString` at `0x18007b9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bbb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18007bc10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bbc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bc24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b95d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bbc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007bc24`

## string_xrefs

- `0x18007b880`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007b911`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18007b988`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeclaredConfigurationStore_GetResultsDocIdKeyRegardlessOfState(
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
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-61h] BYREF
  HKEY v30; // [rsp+60h] [rbp-59h] BYREF
  HKEY v31; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  HKEY *v33; // [rsp+78h] [rbp-41h] BYREF
  HKEY v34; // [rsp+80h] [rbp-39h] BYREF
  char v35; // [rsp+88h] [rbp-31h]
  void *p_hKey; // [rsp+90h] [rbp-29h] BYREF
  HKEY v37; // [rsp+98h] [rbp-21h] BYREF
  char v38; // [rsp+A0h] [rbp-19h]
  LPCWSTR *p_lpSubKey; // [rsp+A8h] [rbp-11h]
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
        (void *)0x868,
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
        (void *)0x86C,
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
        (void *)0x86E,
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
      p_lpSubKey = &lpSubKey;
      v40 = 1;
      if ( (int)DCStringCchPrintfAllStrings(&lpSubKey, qword_18018A420, 3, *(_QWORD *)a1, *((_QWORD *)pv + m), a2) >= 0 )
      {
        v33 = &v31;
        v34 = 0;
        v35 = 1;
        v17 = DCCDNUtil_GetHKey(lpSubKey, &v34, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v33);
        if ( v17 >= 0 )
        {
          if ( v31 )
          {
            v27 = 0;
            p_hKey = &v27;
            LOBYTE(v37) = 1;
            if ( DCCDNUtil_GetRegistryString(v31, 0, L"MostRecentVersion", &v27) >= 0 )
            {
              v28 = 0;
              if ( (int)DCStringCchPrintfAllStrings(
                          &v28,
                          qword_18018A560,
                          4,
                          *(_QWORD *)a1,
                          *((_QWORD *)pv + m),
                          a2,
                          v27) >= 0 )
              {
                v30 = 0;
                v33 = &v30;
                v34 = 0;
                v35 = 1;
                v18 = (unsigned int)DCCDNUtil_GetHKey(v28, &v34, 0) >> 31;
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v33);
                if ( (unsigned __int8)v18 != 1 )
                {
                  v19 = v30;
                  if ( v30 )
                  {
                    v30 = 0;
                    *a3 = v19;
                    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
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
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
              }
              if ( v28 )
              {
                operator delete((void *)v28);
                v28 = 0;
              }
            }
            LOBYTE(v37) = 0;
            operator delete(v27);
            v27 = 0;
          }
        }
      }
      v40 = 0;
      if ( lpSubKey )
        operator delete((void *)lpSubKey);
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
0x18007b7f4  mov     [rsp-8+arg_0], rbx
0x18007b7f9  mov     [rsp-8+arg_18], r9d
0x18007b7fe  push    rbp
0x18007b7ff  push    rsi
0x18007b800  push    rdi
0x18007b801  push    r12
0x18007b803  push    r13
0x18007b805  push    r14
0x18007b807  push    r15
0x18007b809  lea     rbp, [rsp-27h]
0x18007b80e  sub     rsp, 0E0h
0x18007b815  mov     r14, r8
0x18007b818  mov     r12, rdx
0x18007b81b  mov     rsi, rcx
0x18007b81e  xor     r13d, r13d
0x18007b821  mov     [rbp+57h+hKey], r13
0x18007b825  mov     [rbp+57h+var_A8], r13
0x18007b829  mov     [rbp+57h+Block], r13
0x18007b82d  mov     [rbp+57h+lpSubKey], r13
0x18007b831  mov     [rbp+57h+pv], r13
0x18007b835  mov     [rbp+57h+arg_18], r13d
0x18007b839  test    r8, r8
0x18007b83c  jz      loc_18007BC45
0x18007b842  test    rcx, rcx
0x18007b845  jz      loc_18007BC45
0x18007b84b  lea     rax, [rbp+57h+Block]
0x18007b84f  mov     [rbp+57h+var_58], rax
0x18007b853  lea     rax, [rbp+57h+pv]
0x18007b857  mov     [rbp+57h+var_50], rax
0x18007b85b  lea     rax, [rbp+57h+arg_18]
0x18007b85f  mov     [rbp+57h+var_48], rax
0x18007b863  mov     [rbp+57h+var_40], 1
0x18007b867  mov     [r8], r13
0x18007b86a  lea     rdx, [rbp+57h+Block]
0x18007b86e  call    GetRegKeyPathForEnrollmentId
0x18007b873  mov     ebx, eax
0x18007b875  test    eax, eax
0x18007b877  jns     short loc_18007B8DB
0x18007b879  mov     rcx, [rbp+5Fh]; this
0x18007b87d  mov     r9d, eax; char *
0x18007b880  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007b887  mov     edx, 868h; void *
0x18007b88c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b891  nop
0x18007b892  mov     rcx, [rbp+57h+Block]; Block
0x18007b896  test    rcx, rcx
0x18007b899  jz      short loc_18007B8A0
0x18007b89b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b8a0  mov     rax, [rbp+57h+pv]
0x18007b8a4  test    rax, rax
0x18007b8a7  jz      loc_18007BBCF
0x18007b8ad  mov     edi, r13d
0x18007b8b0  cmp     [rbp+57h+arg_18], r13d
0x18007b8b4  jbe     short loc_18007B8CD
0x18007b8b6  mov     ecx, edi
0x18007b8b8  mov     rcx, [rax+rcx*8]; bstrString
0x18007b8bc  call    cs:__imp_SysFreeString
0x18007b8c2  inc     edi
0x18007b8c4  mov     rax, [rbp+57h+pv]
0x18007b8c8  cmp     edi, [rbp+57h+arg_18]
0x18007b8cb  jb      short loc_18007B8B6
0x18007b8cd  mov     rcx, rax; pv
0x18007b8d0  call    cs:__imp_CoTaskMemFree
0x18007b8d6  jmp     loc_18007BBCF
0x18007b8db  lea     rax, [rbp+57h+hKey]
0x18007b8df  mov     [rbp+57h+var_80], rax
0x18007b8e3  mov     [rbp+57h+var_78], r13
0x18007b8e7  mov     [rbp+57h+var_70], 1
0x18007b8eb  xor     r8d, r8d; int
0x18007b8ee  lea     rdx, [rbp+57h+var_78]; HKEY *
0x18007b8f2  mov     rcx, [rbp+57h+Block]; lpSubKey
0x18007b8f6  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18007b8fb  mov     edi, eax
0x18007b8fd  lea     rcx, [rbp+57h+var_80]
0x18007b901  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007b906  test    edi, edi
0x18007b908  jns     short loc_18007B96A
0x18007b90a  mov     rcx, [rbp+5Fh]; this
0x18007b90e  mov     r9d, edi; char *
0x18007b911  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007b918  mov     edx, 86Ch; void *
0x18007b91d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b922  nop
0x18007b923  mov     rcx, [rbp+57h+Block]; Block
0x18007b927  test    rcx, rcx
0x18007b92a  jz      short loc_18007B931
0x18007b92c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b931  mov     rax, [rbp+57h+pv]
0x18007b935  test    rax, rax
0x18007b938  jz      short loc_18007B963
0x18007b93a  mov     ebx, r13d
0x18007b93d  cmp     [rbp+57h+arg_18], r13d
0x18007b941  jbe     short loc_18007B95A
0x18007b943  mov     ecx, ebx
0x18007b945  mov     rcx, [rax+rcx*8]; bstrString
0x18007b949  call    cs:__imp_SysFreeString
0x18007b94f  inc     ebx
0x18007b951  mov     rax, [rbp+57h+pv]
0x18007b955  cmp     ebx, [rbp+57h+arg_18]
0x18007b958  jb      short loc_18007B943
0x18007b95a  mov     rcx, rax; pv
0x18007b95d  call    cs:__imp_CoTaskMemFree
0x18007b963  mov     ebx, edi
0x18007b965  jmp     loc_18007BBCF
0x18007b96a  lea     r8, [rbp+57h+pv]
0x18007b96e  lea     rdx, [rbp+57h+arg_18]
0x18007b972  mov     rcx, [rbp+57h+hKey]; hKey
0x18007b976  call    GetDocIdSubKeys
0x18007b97b  mov     edi, eax
0x18007b97d  test    eax, eax
0x18007b97f  jns     short loc_18007B9D3
0x18007b981  mov     rcx, [rbp+5Fh]; this
0x18007b985  mov     r9d, eax; char *
0x18007b988  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18007b98f  mov     edx, 86Eh; void *
0x18007b994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b999  nop
0x18007b99a  mov     rcx, [rbp+57h+Block]; Block
0x18007b99e  test    rcx, rcx
0x18007b9a1  jz      short loc_18007B9A8
0x18007b9a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b9a8  mov     rax, [rbp+57h+pv]
0x18007b9ac  test    rax, rax
0x18007b9af  jz      short loc_18007B963
0x18007b9b1  mov     ebx, r13d
0x18007b9b4  cmp     [rbp+57h+arg_18], r13d
0x18007b9b8  jbe     short loc_18007B95A
0x18007b9ba  mov     ecx, ebx
0x18007b9bc  mov     rcx, [rax+rcx*8]; bstrString
0x18007b9c0  call    cs:__imp_SysFreeString
0x18007b9c6  inc     ebx
0x18007b9c8  mov     rax, [rbp+57h+pv]
0x18007b9cc  cmp     ebx, [rbp+57h+arg_18]
0x18007b9cf  jb      short loc_18007B9BA
0x18007b9d1  jmp     short loc_18007B95A
0x18007b9d3  mov     edi, r13d
0x18007b9d6  mov     ecx, [rbp+57h+arg_18]
0x18007b9d9  cmp     edi, ecx
0x18007b9db  jnb     loc_18007BBE6
0x18007b9e1  lea     rax, [rbp+57h+lpSubKey]
0x18007b9e5  mov     [rbp+57h+var_68], rax
0x18007b9e9  mov     [rbp+57h+var_60], 1
0x18007b9ed  mov     r15d, edi
0x18007b9f0  mov     [rsp+110h+var_E8], r12
0x18007b9f5  mov     rax, [rbp+57h+pv]
0x18007b9f9  mov     rcx, [rax+r15*8]
0x18007b9fd  mov     [rsp+110h+var_F0], rcx
0x18007ba02  mov     r9, [rsi]
0x18007ba05  mov     r8d, 3
0x18007ba0b  mov     rdx, cs:qword_18018A420
0x18007ba12  lea     rcx, [rbp+57h+lpSubKey]
0x18007ba16  call    DCStringCchPrintfAllStrings
0x18007ba1b  test    eax, eax
0x18007ba1d  js      loc_18007BB35
0x18007ba23  lea     rax, [rbp+57h+var_A8]
0x18007ba27  mov     [rbp+57h+var_98], rax
0x18007ba2b  mov     [rbp+57h+var_90], r13
0x18007ba2f  mov     [rbp+57h+var_88], 1
0x18007ba33  xor     r8d, r8d; int
0x18007ba36  lea     rdx, [rbp+57h+var_90]; HKEY *
0x18007ba3a  mov     rcx, [rbp+57h+lpSubKey]; lpSubKey
0x18007ba3e  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18007ba43  mov     ebx, eax
0x18007ba45  lea     rcx, [rbp+57h+var_98]
0x18007ba49  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007ba4e  test    ebx, ebx
0x18007ba50  js      loc_18007BB35
0x18007ba56  mov     rcx, [rbp+57h+var_A8]; HKEY
0x18007ba5a  test    rcx, rcx
0x18007ba5d  jz      loc_18007BB35
0x18007ba63  mov     [rbp+57h+var_C8], r13
0x18007ba67  lea     rax, [rbp+57h+var_C8]
0x18007ba6b  mov     [rbp+57h+var_80], rax
0x18007ba6f  mov     byte ptr [rbp+57h+var_78], 1
0x18007ba73  lea     r9, [rbp+57h+var_C8]; unsigned __int16 **
0x18007ba77  lea     r8, aMostrecentvers; "MostRecentVersion"
0x18007ba7e  xor     edx, edx; unsigned __int16 *
0x18007ba80  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18007ba85  test    eax, eax
0x18007ba87  js      loc_18007BB24
0x18007ba8d  mov     [rbp+57h+var_C0], r13
0x18007ba91  mov     rax, [rbp+57h+var_C8]
0x18007ba95  mov     [rsp+110h+var_E0], rax
0x18007ba9a  mov     [rsp+110h+var_E8], r12
0x18007ba9f  mov     rax, [rbp+57h+pv]
0x18007baa3  mov     rcx, [rax+r15*8]
0x18007baa7  mov     [rsp+110h+var_F0], rcx
0x18007baac  mov     r9, [rsi]
0x18007baaf  mov     r8d, 4
0x18007bab5  mov     rdx, cs:qword_18018A560
0x18007babc  lea     rcx, [rbp+57h+var_C0]
0x18007bac0  call    DCStringCchPrintfAllStrings
0x18007bac5  test    eax, eax
0x18007bac7  js      short loc_18007BB12
0x18007bac9  mov     [rbp+57h+var_B0], r13
0x18007bacd  lea     rax, [rbp+57h+var_B0]
0x18007bad1  mov     [rbp+57h+var_98], rax
0x18007bad5  mov     [rbp+57h+var_90], r13
0x18007bad9  mov     [rbp+57h+var_88], 1
0x18007badd  xor     r8d, r8d; int
0x18007bae0  lea     rdx, [rbp+57h+var_90]; HKEY *
0x18007bae4  mov     rcx, [rbp+57h+var_C0]; lpSubKey
0x18007bae8  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18007baed  mov     ebx, eax
0x18007baef  shr     ebx, 1Fh
0x18007baf2  lea     rcx, [rbp+57h+var_98]
0x18007baf6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18007bafb  xor     bl, 1
0x18007bafe  jz      short loc_18007BB09
0x18007bb00  mov     rax, [rbp+57h+var_B0]
0x18007bb04  test    rax, rax
0x18007bb07  jnz     short loc_18007BB4E
0x18007bb09  lea     rcx, [rbp+57h+var_B0]
0x18007bb0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bb12  mov     rcx, [rbp+57h+var_C0]; Block
0x18007bb16  test    rcx, rcx
0x18007bb19  jz      short loc_18007BB24
0x18007bb1b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb20  mov     [rbp+57h+var_C0], r13
0x18007bb24  mov     byte ptr [rbp+57h+var_78], r13b
0x18007bb28  mov     rcx, [rbp+57h+var_C8]; Block
0x18007bb2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb31  mov     [rbp+57h+var_C8], r13
0x18007bb35  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18007bb39  test    rcx, rcx
0x18007bb3c  mov     [rbp+57h+var_60], r13b
0x18007bb40  jz      short loc_18007BB47
0x18007bb42  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb47  inc     edi
0x18007bb49  jmp     loc_18007B9D6
0x18007bb4e  mov     [rbp+57h+var_B0], r13
0x18007bb52  mov     [r14], rax
0x18007bb55  lea     rcx, [rbp+57h+var_B0]
0x18007bb59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bb5e  mov     rcx, [rbp+57h+var_C0]; Block
0x18007bb62  test    rcx, rcx
0x18007bb65  jz      short loc_18007BB70
0x18007bb67  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb6c  mov     [rbp+57h+var_C0], r13
0x18007bb70  mov     rcx, [rbp+57h+var_C8]; Block
0x18007bb74  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb79  mov     [rbp+57h+var_C8], r13
0x18007bb7d  mov     rcx, [rbp+57h+lpSubKey]; Block
0x18007bb81  test    rcx, rcx
0x18007bb84  jz      short loc_18007BB8C
0x18007bb86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb8b  nop
0x18007bb8c  mov     rcx, [rbp+57h+Block]; Block
0x18007bb90  test    rcx, rcx
0x18007bb93  jz      short loc_18007BB9A
0x18007bb95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bb9a  mov     rax, [rbp+57h+pv]
0x18007bb9e  test    rax, rax
0x18007bba1  jz      short loc_18007BBCC
0x18007bba3  mov     ebx, r13d
0x18007bba6  cmp     [rbp+57h+arg_18], r13d
0x18007bbaa  jbe     short loc_18007BBC3
0x18007bbac  mov     ecx, ebx
0x18007bbae  mov     rcx, [rax+rcx*8]; bstrString
0x18007bbb2  call    cs:__imp_SysFreeString
0x18007bbb8  inc     ebx
0x18007bbba  mov     rax, [rbp+57h+pv]
0x18007bbbe  cmp     ebx, [rbp+57h+arg_18]
0x18007bbc1  jb      short loc_18007BBAC
0x18007bbc3  mov     rcx, rax; pv
0x18007bbc6  call    cs:__imp_CoTaskMemFree
0x18007bbcc  mov     ebx, r13d
0x18007bbcf  lea     rcx, [rbp+57h+var_A8]
0x18007bbd3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bbd8  nop
0x18007bbd9  lea     rcx, [rbp+57h+hKey]
0x18007bbdd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bbe2  mov     eax, ebx
0x18007bbe4  jmp     short loc_18007BC5D
0x18007bbe6  mov     rax, [rbp+57h+Block]
0x18007bbea  test    rax, rax
0x18007bbed  jz      short loc_18007BBFA
0x18007bbef  mov     rcx, rax; Block
0x18007bbf2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007bbf7  mov     ecx, [rbp+57h+arg_18]
0x18007bbfa  mov     rax, [rbp+57h+pv]
0x18007bbfe  test    rax, rax
0x18007bc01  jz      short loc_18007BC2B
0x18007bc03  mov     ebx, r13d
0x18007bc06  test    ecx, ecx
0x18007bc08  jz      short loc_18007BC21
0x18007bc0a  mov     ecx, ebx
0x18007bc0c  mov     rcx, [rax+rcx*8]; bstrString
0x18007bc10  call    cs:__imp_SysFreeString
0x18007bc16  inc     ebx
0x18007bc18  mov     rax, [rbp+57h+pv]
0x18007bc1c  cmp     ebx, [rbp+57h+arg_18]
0x18007bc1f  jb      short loc_18007BC0A
0x18007bc21  mov     rcx, rax; pv
0x18007bc24  call    cs:__imp_CoTaskMemFree
0x18007bc2a  nop
0x18007bc2b  lea     rcx, [rbp+57h+var_A8]
0x18007bc2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007bc34  nop
0x18007bc35  lea     rcx, [rbp+57h+hKey]
  ... truncated ...
```

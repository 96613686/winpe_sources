# DeleteTreeContainersEnrollmentSid

- ea: `0x18008c028`
- end: `0x18008c266`
- name: `DeleteTreeContainersEnrollmentSid`
- size: `574`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180069de0`

## callees

- `0x18001ce5c`
- `0x18001d0b0`
- `0x18005a400`
- `0x18005f3d8`
- `0x18008c028`
- `0x18008cec8`
- `0x18008f6fc`
- `0x18008fa00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c141`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c203`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c141`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18008c203`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008c1b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008c1b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c0ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c095`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008c0ba`

## pseudocode

```c
__int64 __fastcall DeleteTreeContainersEnrollmentSid(LPCWSTR *a1)
{
  HKEY v3; // rbx
  int DocIdSubKeys; // edi
  HKEY v5; // rcx
  int ResultsContainerIdEnrollmentIdKey; // ebx
  DWORD v7; // r14d
  LSTATUS v8; // eax
  unsigned int v9; // edi
  bool v10; // cc
  __int64 v11; // rdx
  LSTATUS v12; // eax
  __int64 v13; // [rsp+60h] [rbp-29h] BYREF
  HKEY v14; // [rsp+68h] [rbp-21h] BYREF
  HKEY *p_hKey; // [rsp+70h] [rbp-19h] BYREF
  __int64 v16; // [rsp+78h] [rbp-11h] BYREF
  char v17; // [rsp+80h] [rbp-9h]
  _QWORD v18[2]; // [rsp+88h] [rbp-1h] BYREF
  char v19; // [rsp+98h] [rbp+Fh]
  DWORD v20; // [rsp+F0h] [rbp+67h] BYREF
  DWORD cSubKeys; // [rsp+F8h] [rbp+6Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+100h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+108h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !a1 )
    return 2147942487LL;
  v20 = 0;
  v3 = 0;
  v13 = 0;
  hKey = 0;
  DocIdSubKeys = DCGetReadonlyHKey(qword_18018A440);
  if ( DocIdSubKeys < 0 )
  {
    v5 = hKey;
  }
  else
  {
    v3 = hKey;
    v5 = 0;
  }
  if ( v5 )
    RegCloseKey(v5);
  if ( DocIdSubKeys < 0 )
  {
    if ( DocIdSubKeys == -2147024894 )
    {
      v13 = 0;
      DocIdSubKeys = 0;
      v20 = 0;
    }
  }
  else
  {
    DocIdSubKeys = GetDocIdSubKeys(v3, &v20, &v13);
    RegCloseKey(v3);
  }
  v19 = 1;
  ResultsContainerIdEnrollmentIdKey = 0;
  v18[0] = &v13;
  if ( DocIdSubKeys >= 0 )
    ResultsContainerIdEnrollmentIdKey = DocIdSubKeys;
  v7 = 0;
  for ( v18[1] = &v20; v7 < v20; ++v7 )
  {
    hKey = 0;
    p_hKey = &hKey;
    v16 = 0;
    v17 = 1;
    ResultsContainerIdEnrollmentIdKey = GetResultsContainerIdEnrollmentIdKey(a1, *(_QWORD *)(v13 + 8LL * v7), &v16);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( ResultsContainerIdEnrollmentIdKey >= 0 )
    {
      v8 = RegDeleteTreeW(hKey, a1[1]);
      v9 = v8;
      v10 = v8 <= 0;
      if ( v8
        || (cSubKeys = 0,
            cbMaxSubKeyLen = 0,
            v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0),
            v9 = v8,
            v10 = v8 <= 0,
            v8) )
      {
        if ( !v10 )
          v9 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_19;
      }
      if ( !cSubKeys )
      {
        v14 = 0;
        p_hKey = &v14;
        v16 = 0;
        v11 = *(_QWORD *)(v13 + 8LL * v7);
        v17 = 1;
        ResultsContainerIdEnrollmentIdKey = GetResultsContainerIdEnrollmentsKey(a1, v11, &v16);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( ResultsContainerIdEnrollmentIdKey >= 0 )
        {
          v12 = RegDeleteTreeW(v14, *a1);
          v9 = v12;
          if ( v12 )
          {
            if ( v12 > 0 )
              v9 = (unsigned __int16)v12 | 0x80070000;
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
LABEL_19:
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
            ResultsContainerIdEnrollmentIdKey = 0;
            if ( v9 != -2147024894 )
              ResultsContainerIdEnrollmentIdKey = v9;
            continue;
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  wil::details::ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075___::operator()(v18);
  return (unsigned int)ResultsContainerIdEnrollmentIdKey;
}

```

## disassembly

```asm
0x18008c028  push    rbp
0x18008c02a  push    rbx
0x18008c02b  push    rsi
0x18008c02c  push    rdi
0x18008c02d  push    r12
0x18008c02f  push    r13
0x18008c031  push    r14
0x18008c033  push    r15
0x18008c035  lea     rbp, [rsp-1Fh]
0x18008c03a  sub     rsp, 0A8h
0x18008c041  xor     r12d, r12d
0x18008c044  mov     rsi, rcx
0x18008c047  mov     [rbp+57h+cSubKeys], r12d
0x18008c04b  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x18008c04f  test    rcx, rcx
0x18008c052  jnz     short loc_18008C05E
0x18008c054  mov     eax, 80070057h
0x18008c059  jmp     loc_18008C252
0x18008c05e  mov     rcx, cs:qword_18018A440; lpSubKey
0x18008c065  lea     rdx, [rbp+57h+hKey]
0x18008c069  mov     [rbp+57h+arg_0], r12d
0x18008c06d  mov     rbx, r12
0x18008c070  mov     [rbp+57h+var_80], r12
0x18008c074  mov     [rbp+57h+hKey], r12
0x18008c078  call    DCGetReadonlyHKey
0x18008c07d  mov     edi, eax
0x18008c07f  test    eax, eax
0x18008c081  js      short loc_18008C08C
0x18008c083  mov     rbx, [rbp+57h+hKey]
0x18008c087  mov     rcx, r12
0x18008c08a  jmp     short loc_18008C090
0x18008c08c  mov     rcx, [rbp+57h+hKey]; hKey
0x18008c090  test    rcx, rcx
0x18008c093  jz      short loc_18008C09B
0x18008c095  call    cs:__imp_RegCloseKey
0x18008c09b  mov     r13d, 80070002h
0x18008c0a1  test    edi, edi
0x18008c0a3  js      short loc_18008C0C2
0x18008c0a5  lea     r8, [rbp+57h+var_80]
0x18008c0a9  mov     rcx, rbx; hKey
0x18008c0ac  lea     rdx, [rbp+57h+arg_0]
0x18008c0b0  call    GetDocIdSubKeys
0x18008c0b5  mov     rcx, rbx; hKey
0x18008c0b8  mov     edi, eax
0x18008c0ba  call    cs:__imp_RegCloseKey
0x18008c0c0  jmp     short loc_18008C0D2
0x18008c0c2  cmp     edi, r13d
0x18008c0c5  jnz     short loc_18008C0D2
0x18008c0c7  mov     [rbp+57h+var_80], r12
0x18008c0cb  mov     edi, r12d
0x18008c0ce  mov     [rbp+57h+arg_0], r12d
0x18008c0d2  test    edi, edi
0x18008c0d4  mov     [rbp+57h+var_48], 1
0x18008c0d8  lea     rax, [rbp+57h+var_80]
0x18008c0dc  mov     ebx, r12d
0x18008c0df  mov     [rbp+57h+var_58], rax
0x18008c0e3  cmovns  ebx, edi
0x18008c0e6  lea     rax, [rbp+57h+arg_0]
0x18008c0ea  mov     r14d, r12d
0x18008c0ed  mov     [rbp+57h+var_50], rax
0x18008c0f1  cmp     [rbp+57h+arg_0], r12d
0x18008c0f5  jbe     loc_18008C247
0x18008c0fb  mov     rdx, [rbp+57h+var_80]
0x18008c0ff  lea     rax, [rbp+57h+hKey]
0x18008c103  mov     [rbp+57h+hKey], r12
0x18008c107  lea     r8, [rbp+57h+var_68]
0x18008c10b  mov     r15d, r14d
0x18008c10e  mov     rcx, rsi
0x18008c111  mov     [rbp+57h+var_70], rax
0x18008c115  mov     [rbp+57h+var_68], r12
0x18008c119  mov     [rbp+57h+var_60], 1
0x18008c11d  mov     rdx, [rdx+r15*8]
0x18008c121  call    GetResultsContainerIdEnrollmentIdKey
0x18008c126  lea     rcx, [rbp+57h+var_70]
0x18008c12a  mov     ebx, eax
0x18008c12c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008c131  test    ebx, ebx
0x18008c133  js      loc_18008C231
0x18008c139  mov     rdx, [rsi+8]; lpSubKey
0x18008c13d  mov     rcx, [rbp+57h+hKey]; hKey
0x18008c141  call    cs:__imp_RegDeleteTreeW
0x18008c147  mov     edi, eax
0x18008c149  test    eax, eax
0x18008c14b  jz      short loc_18008C16F
0x18008c14d  jle     short loc_18008C158
0x18008c14f  movzx   edi, ax
0x18008c152  or      edi, 80070000h
0x18008c158  lea     rcx, [rbp+57h+hKey]
0x18008c15c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c161  cmp     edi, r13d
0x18008c164  mov     ebx, r12d
0x18008c167  cmovnz  ebx, edi
0x18008c16a  jmp     loc_18008C23A
0x18008c16f  mov     rcx, [rbp+57h+hKey]; hKey
0x18008c173  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18008c177  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18008c17c  xor     r9d, r9d; lpReserved
0x18008c17f  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18008c184  xor     r8d, r8d; lpcchClass
0x18008c187  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18008c18c  xor     edx, edx; lpClass
0x18008c18e  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18008c193  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x18008c198  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18008c19d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18008c1a2  lea     rax, [rbp+57h+cSubKeys]
0x18008c1a6  mov     [rsp+0E0h+lpcSubKeys], rax; lpcSubKeys
0x18008c1ab  mov     [rbp+57h+cSubKeys], r12d
0x18008c1af  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x18008c1b3  call    cs:__imp_RegQueryInfoKeyW
0x18008c1b9  mov     edi, eax
0x18008c1bb  test    eax, eax
0x18008c1bd  jnz     short loc_18008C14D
0x18008c1bf  cmp     [rbp+57h+cSubKeys], r12d
0x18008c1c3  jnz     short loc_18008C231
0x18008c1c5  mov     rdx, [rbp+57h+var_80]
0x18008c1c9  lea     rax, [rbp+57h+var_78]
0x18008c1cd  mov     [rbp+57h+var_78], r12
0x18008c1d1  lea     r8, [rbp+57h+var_68]
0x18008c1d5  mov     rcx, rsi
0x18008c1d8  mov     [rbp+57h+var_70], rax
0x18008c1dc  mov     [rbp+57h+var_68], r12
0x18008c1e0  mov     rdx, [rdx+r15*8]
0x18008c1e4  mov     [rbp+57h+var_60], 1
0x18008c1e8  call    GetResultsContainerIdEnrollmentsKey
0x18008c1ed  lea     rcx, [rbp+57h+var_70]
0x18008c1f1  mov     ebx, eax
0x18008c1f3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008c1f8  test    ebx, ebx
0x18008c1fa  js      short loc_18008C228
0x18008c1fc  mov     rdx, [rsi]; lpSubKey
0x18008c1ff  mov     rcx, [rbp+57h+var_78]; hKey
0x18008c203  call    cs:__imp_RegDeleteTreeW
0x18008c209  mov     edi, eax
0x18008c20b  test    eax, eax
0x18008c20d  jz      short loc_18008C228
0x18008c20f  jle     short loc_18008C21A
0x18008c211  movzx   edi, ax
0x18008c214  or      edi, 80070000h
0x18008c21a  lea     rcx, [rbp+57h+var_78]
0x18008c21e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c223  jmp     loc_18008C158
0x18008c228  lea     rcx, [rbp+57h+var_78]
0x18008c22c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c231  lea     rcx, [rbp+57h+hKey]
0x18008c235  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c23a  inc     r14d
0x18008c23d  cmp     r14d, [rbp+57h+arg_0]
0x18008c241  jb      loc_18008C0FB
0x18008c247  lea     rcx, [rbp+57h+var_58]
0x18008c24b  call    wil__details__ScopeExitFn__lambda_f984c43bf46297e92d14b60ba967b075_____operator__
0x18008c250  mov     eax, ebx
0x18008c252  add     rsp, 0A8h
0x18008c259  pop     r15
0x18008c25b  pop     r14
0x18008c25d  pop     r13
0x18008c25f  pop     r12
0x18008c261  pop     rdi
0x18008c262  pop     rsi
0x18008c263  pop     rbx
0x18008c264  pop     rbp
0x18008c265  retn
```

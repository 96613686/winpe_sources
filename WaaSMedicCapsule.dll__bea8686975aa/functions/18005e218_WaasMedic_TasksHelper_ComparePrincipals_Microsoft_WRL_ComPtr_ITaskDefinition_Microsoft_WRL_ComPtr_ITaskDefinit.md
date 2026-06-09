# WaasMedic::TasksHelper::ComparePrincipals(Microsoft::WRL::ComPtr<ITaskDefinition>,Microsoft::WRL::ComPtr<ITaskDefinition>,int,bool *)

- ea: `0x18005e218`
- end: `0x18005e60c`
- name: `?ComparePrincipals@TasksHelper@WaasMedic@@CAJV?$ComPtr@UITaskDefinition@@@WRL@Microsoft@@0HPEA_N@Z`
- size: `1012`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005fc80`

## callees

- `0x18002543c`
- `0x18005e218`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e426`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e475`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e426`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005e475`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e2ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e2f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e33e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e366`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4df`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e557`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e565`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e573`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e581`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e2ca`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e2f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e33e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e366`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e4df`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e557`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e565`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e573`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e581`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e312`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e387`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e405`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e454`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e312`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e387`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e405`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e454`

## string_xrefs

- `0x18005e3eb`: `Principal TASK_RUNLEVEL_TYPE did not match! Expected: %d; Actual: %d`
- `0x18005e43d`: `Principal task IDs did not match! Expected: %s; Actual: %s`
- `0x18005e49f`: `Error encountered when comparing current task principal settings with expected task principal settings. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall WaasMedic::TasksHelper::ComparePrincipals(_QWORD *a1, _QWORD *a2, int a3, _BYTE *a4)
{
  int v7; // r15d
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, BSTR *); // rbx
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, BSTR *); // rbx
  const WCHAR *v12; // rbx
  __int64 v13; // rdi
  void (__fastcall *v14)(__int64, BSTR *); // rbx
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, BSTR *); // rbx
  const WCHAR *v17; // rbx
  UINT cchCount2; // eax
  UINT v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // [rsp+30h] [rbp-40h] BYREF
  BSTR pbstr; // [rsp+38h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  BSTR v30; // [rsp+48h] [rbp-28h] BYREF
  BSTR v31; // [rsp+50h] [rbp-20h] BYREF
  __int64 v32; // [rsp+58h] [rbp-18h] BYREF
  __int64 v33; // [rsp+60h] [rbp-10h] BYREF
  int v34; // [rsp+C0h] [rbp+50h] BYREF

  v34 = a3;
  v33 = 0;
  v32 = 0;
  bstrString = 0;
  v31 = 0;
  pbstr = 0;
  v30 = 0;
  if ( *a1 && *a2 && a4 )
  {
    *a4 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 120LL))(*a2, &v33);
    if ( v7 < 0 || (v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 120LL))(*a1, &v32), v7 < 0) )
    {
      LogLevelW(
        2u,
        L"Error encountered when comparing current task principal settings with expected task principal settings. hr=0x%08x",
        (unsigned int)v7);
      goto LABEL_20;
    }
    v8 = v33;
    v9 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 56LL);
    SysFreeString(bstrString);
    bstrString = 0;
    v9(v8, &bstrString);
    v10 = v32;
    v11 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 56LL);
    SysFreeString(v31);
    v31 = 0;
    v11(v10, &v31);
    v12 = bstrString;
    if ( SysStringLen(bstrString) )
    {
      cchCount2 = SysStringLen(bstrString);
      if ( CompareStringW(0x400u, 0, v12, -1, bstrString, cchCount2) == 2 )
      {
LABEL_9:
        v13 = v33;
        v14 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v33 + 88LL);
        SysFreeString(pbstr);
        pbstr = 0;
        v14(v13, &pbstr);
        v15 = v32;
        v16 = *(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v32 + 88LL);
        SysFreeString(v30);
        v30 = 0;
        v16(v15, &v30);
        v17 = v30;
        if ( SysStringLen(pbstr) )
        {
          v19 = SysStringLen(pbstr);
          if ( CompareStringW(0x400u, 0, v17, -1, pbstr, v19) == 2 )
          {
LABEL_12:
            v34 = 0;
            v27 = 0;
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 136LL))(v33, &v34);
            (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 136LL))(v32, &v27);
            if ( v34 == v27 )
              *a4 = 1;
            else
              LogLevelW(3u, L"Principal TASK_RUNLEVEL_TYPE did not match! Expected: %d; Actual: %d");
            goto LABEL_20;
          }
        }
        else if ( !v17 || !*v17 )
        {
          goto LABEL_12;
        }
        LogLevelW(3u, L"Principal user IDs did not match! Expected: %s; Actual: %s", v30, pbstr);
LABEL_20:
        SysFreeString(v30);
        v30 = 0;
        SysFreeString(pbstr);
        pbstr = 0;
        SysFreeString(v31);
        v31 = 0;
        SysFreeString(bstrString);
        bstrString = 0;
        v20 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
        v21 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        v22 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = *a2;
        if ( *a2 )
        {
          *a2 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
        return (unsigned int)v7;
      }
    }
    else if ( !v12 || !*v12 )
    {
      goto LABEL_9;
    }
    LogLevelW(3u, L"Principal task IDs did not match! Expected: %s; Actual: %s", v31, bstrString);
    goto LABEL_20;
  }
  SysFreeString(0);
  v30 = 0;
  SysFreeString(pbstr);
  pbstr = 0;
  SysFreeString(v31);
  v31 = 0;
  SysFreeString(bstrString);
  bstrString = 0;
  v25 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18005e218  mov     rax, rsp
0x18005e21b  mov     [rax+20h], rbx
0x18005e21f  mov     [rax+18h], r8d
0x18005e223  mov     [rax+10h], rdx
0x18005e227  mov     [rax+8], rcx
0x18005e22b  push    rbp
0x18005e22c  push    rsi
0x18005e22d  push    rdi
0x18005e22e  push    r12
0x18005e230  push    r13
0x18005e232  push    r14
0x18005e234  push    r15
0x18005e236  mov     rbp, rsp
0x18005e239  sub     rsp, 70h
0x18005e23d  mov     r12, r9
0x18005e240  mov     rsi, rdx
0x18005e243  mov     r14, rcx
0x18005e246  xor     r13d, r13d
0x18005e249  mov     [rbp+var_10], r13
0x18005e24d  mov     [rbp+var_18], r13
0x18005e251  mov     [rbp+bstrString], r13
0x18005e255  mov     [rbp+var_20], r13
0x18005e259  mov     [rbp+pbstr], r13
0x18005e25d  mov     [rbp+var_28], r13
0x18005e261  cmp     [rcx], r13
0x18005e264  jz      loc_18005E555
0x18005e26a  cmp     [rdx], r13
0x18005e26d  jz      loc_18005E555
0x18005e273  test    r9, r9
0x18005e276  jz      loc_18005E555
0x18005e27c  mov     [r9], r13b
0x18005e27f  mov     rcx, [rdx]
0x18005e282  mov     rax, [rcx]
0x18005e285  lea     rdx, [rbp+var_10]
0x18005e289  mov     rax, [rax+78h]
0x18005e28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e292  mov     r15d, eax
0x18005e295  test    eax, eax
0x18005e297  js      loc_18005E49C
0x18005e29d  mov     rcx, [r14]
0x18005e2a0  mov     rax, [rcx]
0x18005e2a3  lea     rdx, [rbp+var_18]
0x18005e2a7  mov     rax, [rax+78h]
0x18005e2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2b0  mov     r15d, eax
0x18005e2b3  test    eax, eax
0x18005e2b5  js      loc_18005E49C
0x18005e2bb  mov     rdi, [rbp+var_10]
0x18005e2bf  mov     rax, [rdi]
0x18005e2c2  mov     rbx, [rax+38h]
0x18005e2c6  mov     rcx, [rbp+bstrString]; bstrString
0x18005e2ca  call    cs:__imp_SysFreeString
0x18005e2d0  mov     [rbp+bstrString], r13
0x18005e2d4  lea     rdx, [rbp+bstrString]
0x18005e2d8  mov     rcx, rdi
0x18005e2db  mov     rax, rbx
0x18005e2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2e3  mov     rdi, [rbp+var_18]
0x18005e2e7  mov     rax, [rdi]
0x18005e2ea  mov     rbx, [rax+38h]
0x18005e2ee  mov     rcx, [rbp+var_20]; bstrString
0x18005e2f2  call    cs:__imp_SysFreeString
0x18005e2f8  mov     [rbp+var_20], r13
0x18005e2fc  lea     rdx, [rbp+var_20]
0x18005e300  mov     rcx, rdi
0x18005e303  mov     rax, rbx
0x18005e306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e30b  mov     rbx, [rbp+bstrString]
0x18005e30f  mov     rcx, rbx; pbstr
0x18005e312  call    cs:__imp_SysStringLen
0x18005e318  test    eax, eax
0x18005e31a  jnz     loc_18005E401
0x18005e320  test    rbx, rbx
0x18005e323  jz      short loc_18005E32F
0x18005e325  cmp     [rbx], r13w
0x18005e329  jnz     loc_18005E435
0x18005e32f  mov     rdi, [rbp+var_10]
0x18005e333  mov     rax, [rdi]
0x18005e336  mov     rbx, [rax+58h]
0x18005e33a  mov     rcx, [rbp+pbstr]; bstrString
0x18005e33e  call    cs:__imp_SysFreeString
0x18005e344  mov     [rbp+pbstr], r13
0x18005e348  lea     rdx, [rbp+pbstr]
0x18005e34c  mov     rcx, rdi
0x18005e34f  mov     rax, rbx
0x18005e352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e357  mov     rdi, [rbp+var_18]
0x18005e35b  mov     rax, [rdi]
0x18005e35e  mov     rbx, [rax+58h]
0x18005e362  mov     rcx, [rbp+var_28]; bstrString
0x18005e366  call    cs:__imp_SysFreeString
0x18005e36c  mov     [rbp+var_28], r13
0x18005e370  lea     rdx, [rbp+var_28]
0x18005e374  mov     rcx, rdi
0x18005e377  mov     rax, rbx
0x18005e37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e37f  mov     rbx, [rbp+var_28]
0x18005e383  mov     rcx, [rbp+pbstr]; pbstr
0x18005e387  call    cs:__imp_SysStringLen
0x18005e38d  test    eax, eax
0x18005e38f  jnz     loc_18005E450
0x18005e395  test    rbx, rbx
0x18005e398  jz      short loc_18005E3A4
0x18005e39a  cmp     [rbx], r13w
0x18005e39e  jnz     loc_18005E484
0x18005e3a4  mov     [rbp+arg_10], r13d
0x18005e3a8  mov     [rbp+var_40], r13d
0x18005e3ac  mov     rcx, [rbp+var_10]
0x18005e3b0  mov     rax, [rcx]
0x18005e3b3  lea     rdx, [rbp+arg_10]
0x18005e3b7  mov     rax, [rax+88h]
0x18005e3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3c3  mov     rcx, [rbp+var_18]
0x18005e3c7  mov     rax, [rcx]
0x18005e3ca  lea     rdx, [rbp+var_40]
0x18005e3ce  mov     rax, [rax+88h]
0x18005e3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3da  mov     r9d, [rbp+arg_10]
0x18005e3de  mov     r8d, [rbp+var_40]
0x18005e3e2  cmp     r9d, r8d
0x18005e3e5  jz      loc_18005E495
0x18005e3eb  lea     rdx, aPrincipalTaskR; "Principal TASK_RUNLEVEL_TYPE did not ma"...
0x18005e3f2  mov     ecx, 3; unsigned __int8
0x18005e3f7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005e3fc  jmp     loc_18005E4B1
0x18005e401  mov     rcx, [rbp+bstrString]; pbstr
0x18005e405  call    cs:__imp_SysStringLen
0x18005e40b  mov     rcx, [rbp+bstrString]
0x18005e40f  mov     [rsp+70h+cchCount2], eax; cchCount2
0x18005e413  mov     [rsp+70h+lpString2], rcx; lpString2
0x18005e418  or      r9d, 0FFFFFFFFh; cchCount1
0x18005e41c  mov     r8, rbx; lpString1
0x18005e41f  xor     edx, edx; dwCmpFlags
0x18005e421  mov     ecx, 400h; Locale
0x18005e426  call    cs:__imp_CompareStringW
0x18005e42c  cmp     eax, 2
0x18005e42f  jz      loc_18005E32F
0x18005e435  mov     r9, [rbp+bstrString]
0x18005e439  mov     r8, [rbp+var_20]
0x18005e43d  lea     rdx, aPrincipalTaskI; "Principal task IDs did not match! Expec"...
0x18005e444  mov     ecx, 3; unsigned __int8
0x18005e449  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005e44e  jmp     short loc_18005E4B1
0x18005e450  mov     rcx, [rbp+pbstr]; pbstr
0x18005e454  call    cs:__imp_SysStringLen
0x18005e45a  mov     rdx, [rbp+pbstr]
0x18005e45e  mov     [rsp+70h+cchCount2], eax; cchCount2
0x18005e462  mov     [rsp+70h+lpString2], rdx; lpString2
0x18005e467  or      r9d, 0FFFFFFFFh; cchCount1
0x18005e46b  mov     r8, rbx; lpString1
0x18005e46e  xor     edx, edx; dwCmpFlags
0x18005e470  mov     ecx, 400h; Locale
0x18005e475  call    cs:__imp_CompareStringW
0x18005e47b  cmp     eax, 2
0x18005e47e  jz      loc_18005E3A4
0x18005e484  mov     r9, [rbp+pbstr]
0x18005e488  mov     r8, [rbp+var_28]
0x18005e48c  lea     rdx, aPrincipalUserI; "Principal user IDs did not match! Expec"...
0x18005e493  jmp     short loc_18005E444
0x18005e495  mov     byte ptr [r12], 1
0x18005e49a  jmp     short loc_18005E4B1
0x18005e49c  mov     r8d, r15d
0x18005e49f  lea     rdx, aErrorEncounter_10; "Error encountered when comparing curren"...
0x18005e4a6  mov     ecx, 2; unsigned __int8
0x18005e4ab  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005e4b0  nop
0x18005e4b1  mov     rcx, [rbp+var_28]; bstrString
0x18005e4b5  call    cs:__imp_SysFreeString
0x18005e4bb  mov     [rbp+var_28], r13
0x18005e4bf  mov     rcx, [rbp+pbstr]; bstrString
0x18005e4c3  call    cs:__imp_SysFreeString
0x18005e4c9  mov     [rbp+pbstr], r13
0x18005e4cd  mov     rcx, [rbp+var_20]; bstrString
0x18005e4d1  call    cs:__imp_SysFreeString
0x18005e4d7  mov     [rbp+var_20], r13
0x18005e4db  mov     rcx, [rbp+bstrString]; bstrString
0x18005e4df  call    cs:__imp_SysFreeString
0x18005e4e5  mov     [rbp+bstrString], r13
0x18005e4e9  mov     rcx, [rbp+var_18]
0x18005e4ed  test    rcx, rcx
0x18005e4f0  jz      short loc_18005E503
0x18005e4f2  mov     [rbp+var_18], r13
0x18005e4f6  mov     rax, [rcx]
0x18005e4f9  mov     rax, [rax+10h]
0x18005e4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e502  nop
0x18005e503  mov     rcx, [rbp+var_10]
0x18005e507  test    rcx, rcx
0x18005e50a  jz      short loc_18005E51D
0x18005e50c  mov     [rbp+var_10], r13
0x18005e510  mov     rax, [rcx]
0x18005e513  mov     rax, [rax+10h]
0x18005e517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e51c  nop
0x18005e51d  mov     rcx, [r14]
0x18005e520  test    rcx, rcx
0x18005e523  jz      short loc_18005E535
0x18005e525  mov     [r14], r13
0x18005e528  mov     rax, [rcx]
0x18005e52b  mov     rax, [rax+10h]
0x18005e52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e534  nop
0x18005e535  mov     rcx, [rsi]
0x18005e538  test    rcx, rcx
0x18005e53b  jz      short loc_18005E54D
0x18005e53d  mov     [rsi], r13
0x18005e540  mov     rax, [rcx]
0x18005e543  mov     rax, [rax+10h]
0x18005e547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e54c  nop
0x18005e54d  mov     eax, r15d
0x18005e550  jmp     loc_18005E5F4
0x18005e555  xor     ecx, ecx; bstrString
0x18005e557  call    cs:__imp_SysFreeString
0x18005e55d  mov     [rbp+var_28], r13
0x18005e561  mov     rcx, [rbp+pbstr]; bstrString
0x18005e565  call    cs:__imp_SysFreeString
0x18005e56b  mov     [rbp+pbstr], r13
0x18005e56f  mov     rcx, [rbp+var_20]; bstrString
0x18005e573  call    cs:__imp_SysFreeString
0x18005e579  mov     [rbp+var_20], r13
0x18005e57d  mov     rcx, [rbp+bstrString]; bstrString
0x18005e581  call    cs:__imp_SysFreeString
0x18005e587  mov     [rbp+bstrString], r13
0x18005e58b  mov     rcx, [rbp+var_18]
0x18005e58f  test    rcx, rcx
0x18005e592  jz      short loc_18005E5A5
0x18005e594  mov     [rbp+var_18], r13
0x18005e598  mov     rax, [rcx]
0x18005e59b  mov     rax, [rax+10h]
0x18005e59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5a4  nop
0x18005e5a5  mov     rcx, [rbp+var_10]
0x18005e5a9  test    rcx, rcx
0x18005e5ac  jz      short loc_18005E5BF
0x18005e5ae  mov     [rbp+var_10], r13
0x18005e5b2  mov     rax, [rcx]
0x18005e5b5  mov     rax, [rax+10h]
0x18005e5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5be  nop
0x18005e5bf  mov     rcx, [r14]
0x18005e5c2  test    rcx, rcx
0x18005e5c5  jz      short loc_18005E5D7
0x18005e5c7  mov     [r14], r13
0x18005e5ca  mov     rax, [rcx]
0x18005e5cd  mov     rax, [rax+10h]
0x18005e5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5d6  nop
0x18005e5d7  mov     rcx, [rsi]
0x18005e5da  test    rcx, rcx
0x18005e5dd  jz      short loc_18005E5EF
0x18005e5df  mov     [rsi], r13
0x18005e5e2  mov     rax, [rcx]
0x18005e5e5  mov     rax, [rax+10h]
0x18005e5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e5ee  nop
0x18005e5ef  mov     eax, 80004003h
0x18005e5f4  mov     rbx, [rsp+70h+arg_18]
0x18005e5fc  add     rsp, 70h
0x18005e600  pop     r15
0x18005e602  pop     r14
0x18005e604  pop     r13
0x18005e606  pop     r12
0x18005e608  pop     rdi
0x18005e609  pop     rsi
0x18005e60a  pop     rbp
0x18005e60b  retn
```

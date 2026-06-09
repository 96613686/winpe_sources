# _IsSingleUserNoPassword

- ea: `0x180039418`
- end: `0x1800398cf`
- name: `_IsSingleUserNoPassword`
- size: `1207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038c34`
- `0x18003dbe0`

## callees

- `0x180017dec`
- `0x180039418`
- `0x1800398d8`
- `0x180039958`
- `0x18006c000`
- `0x1800923f0`
- `0x18009255c`
- `0x18009d010`

## import_xrefs

- `CredProvCommonCore!__imp_?IsLocalNoPasswordUser@@YA_NPEBG0@Z` at `0x1800398ae`
- `CredProvCommonCore!__imp_?IsLocalNoPasswordUser@@YA_NPEBG0@Z` at `0x1800398ae`
- `CredProvCommonCore!__imp_IsUserAllowedLogin` at `0x180039530`
- `CredProvCommonCore!__imp_IsUserAllowedLogin` at `0x180039530`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039730`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800397fd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039730`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800397fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003948d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003948d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800397dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800395d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800397dd`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800397f0`
- `PROPSYS!PropVariantToStringAlloc` at `0x180039872`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800397f0`
- `PROPSYS!PropVariantToStringAlloc` at `0x180039872`

## pseudocode

```c
bool __fastcall IsSingleUserNoPassword(_WORD *a1, __int64 a2, _WORD *a3)
{
  _WORD *v3; // rbx
  _WORD *v4; // r15
  bool v5; // r13
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rsi
  unsigned __int64 v9; // rdi
  __int64 *v10; // r12
  int v11; // r15d
  int v12; // ebx
  unsigned int v13; // r14d
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64 *, _QWORD, LPVOID *); // rbx
  LPVOID v16; // rcx
  __int64 *v17; // rbx
  __int64 v18; // rax
  unsigned __int64 i; // rbx
  LPVOID v20; // rcx
  int v22; // eax
  LPVOID *v23; // rcx
  _WORD *v24; // r10
  __int64 v25; // r9
  _WORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  bool v30; // zf
  _WORD *v31; // rcx
  unsigned __int16 *v32; // r8
  _WORD *v33; // rax
  unsigned __int16 *v34; // rcx
  _WORD *v35; // rcx
  HRESULT v36; // r15d
  __int64 v37; // rax
  HRESULT v38; // r14d
  int v39; // [rsp+30h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-61h] BYREF
  PROPVARIANT propvar[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v42; // [rsp+50h] [rbp-49h]
  _QWORD *v43; // [rsp+58h] [rbp-41h] BYREF
  __int64 v44; // [rsp+60h] [rbp-39h]
  __int64 v45; // [rsp+68h] [rbp-31h]
  __int64 v46; // [rsp+70h] [rbp-29h]
  _WORD *v47; // [rsp+78h] [rbp-21h]
  _WORD *v48; // [rsp+80h] [rbp-19h]
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v50; // [rsp+98h] [rbp-1h]
  LPVOID pv; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v52; // [rsp+A8h] [rbp+Fh]
  __int64 v53; // [rsp+B0h] [rbp+17h]

  v48 = a1;
  v3 = a3;
  v47 = a3;
  v4 = a1;
  v5 = 0;
  if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_AuthUI_Context,
      AuthUITraceId_Logon_AutoLogon_IsSingleUserNoPassword_Start);
  ppv = 0;
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&ppv);
  if ( CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv) >= 0 )
  {
    v8 = 0;
    v43 = 0;
    v9 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v10 = (__int64 *)ppv;
    v39 = 0;
    if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 32LL))(ppv, &v39) < 0 )
    {
LABEL_27:
      CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::RemoveAll(&v43);
      if ( v5 )
        goto LABEL_28;
      goto LABEL_35;
    }
    v11 = v39;
    if ( (unsigned int)v39 > 0x7FFFFFFF )
      goto LABEL_33;
    v12 = 0;
    v13 = 0;
    if ( v39 > 0 )
    {
      while ( v12 >= 0 )
      {
        v14 = *v10;
        pv = 0;
        v15 = *(__int64 (__fastcall **)(__int64 *, _QWORD, LPVOID *))(v14 + 40);
        Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&pv);
        v12 = v15(v10, v13, &pv);
        if ( v12 >= 0 )
        {
          if ( (unsigned int)IsUserAllowedLogin(pv) )
          {
            v12 = 0;
            if ( v9 != v46
              || (v22 = CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::_EnsureCapacity(
                          &v43,
                          v9 + 1),
                  v9 = v44,
                  v12 = v22,
                  v8 = v43,
                  v22 >= 0) )
            {
              v44 = ++v9;
              v23 = (LPVOID *)&v8[v9 - 1];
              if ( v23 )
              {
                *v23 = pv;
                if ( pv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 8LL))(pv);
              }
            }
          }
        }
        v16 = pv;
        if ( pv )
        {
          pv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
        }
        if ( (int)++v13 >= v11 )
        {
          if ( v12 < 0 )
            break;
          goto LABEL_14;
        }
      }
LABEL_33:
      CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::RemoveAll(&v43);
LABEL_26:
      v3 = v47;
      v4 = v48;
      goto LABEL_27;
    }
LABEL_14:
    if ( v9 != 1 )
    {
LABEL_21:
      if ( v8 )
      {
        for ( i = 0; i < v9; ++i )
          Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v8[i]);
        CoTaskMemFree(v8);
        v43 = 0;
      }
      v44 = 0;
      v46 = 0;
      goto LABEL_26;
    }
    v17 = (__int64 *)*v8;
    if ( *v8 )
      (*(void (__fastcall **)(_QWORD))(*v17 + 8))(*v8);
    pv = 0;
    v52 = -1;
    v53 = -1;
    v42 = 0;
    v18 = *v17;
    *(_OWORD *)propvar = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, PROPVARIANT *))(v18 + 40))(v17, PKEY_SAM_Name, propvar) < 0
      || ((v38 = -2147023728, LOWORD(propvar[0]))
        ? (v36 = PropVariantToStringAlloc(propvar, (PWSTR *)&pv))
        : (v36 = -2147023728),
          PropVariantClear(propvar),
          v36 < 0) )
    {
LABEL_18:
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      v52 = 0;
      v53 = 0;
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
      goto LABEL_21;
    }
    propvar[0] = 0;
    propvar[1] = (PROPVARIANT)-1LL;
    v42 = -1;
    v50 = 0;
    v37 = *v17;
    *(_OWORD *)pvar = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64 *, PROPVARIANT *))(v37 + 40))(v17, PKEY_SAM_Domain, pvar) >= 0 )
    {
      if ( LOWORD(pvar[0]) )
        v38 = PropVariantToStringAlloc(pvar, (PWSTR *)propvar);
      PropVariantClear(pvar);
      if ( v38 >= 0 )
      {
        v24 = pv;
        v25 = 2147483646;
        v26 = v47;
        v27 = 256;
        v28 = 2147483646;
        v29 = 256;
        do
        {
          if ( !v28 )
            break;
          if ( !*v24 )
            break;
          *v26++ = *v24++;
          --v28;
          --v29;
        }
        while ( v29 );
        v30 = v29 == 0;
        v31 = v26 - 1;
        v32 = (unsigned __int16 *)propvar[0];
        if ( !v30 )
          v31 = v26;
        *v31 = 0;
        if ( v30 )
          goto LABEL_56;
        v33 = v48;
        v34 = v32;
        do
        {
          if ( !v25 )
            break;
          if ( !*v34 )
            break;
          *v33++ = *v34++;
          --v25;
          --v27;
        }
        while ( v27 );
        v35 = v33 - 1;
        if ( v27 )
          v35 = v33;
        *v35 = 0;
        if ( !v27 )
          goto LABEL_56;
        v5 = IsLocalNoPasswordUser(v32, (const unsigned __int16 *)pv);
      }
    }
    v32 = (unsigned __int16 *)propvar[0];
LABEL_56:
    if ( v32 )
      CoTaskMemFree(v32);
    goto LABEL_18;
  }
LABEL_35:
  *v4 = 0;
  *v3 = 0;
LABEL_28:
  if ( (Microsoft_Windows_Shell_AuthUIEnableBits & 0x10) != 0 )
    McTemplateU0t_EventWriteTransfer(v7, v6, v5);
  v20 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return v5;
}

```

## disassembly

```asm
0x180039418  mov     [rsp-8+arg_8], rbx
0x18003941d  push    rbp
0x18003941e  push    rsi
0x18003941f  push    rdi
0x180039420  push    r12
0x180039422  push    r13
0x180039424  push    r14
0x180039426  push    r15
0x180039428  lea     rbp, [rsp-27h]
0x18003942d  sub     rsp, 0C0h
0x180039434  mov     rax, cs:__security_cookie
0x18003943b  xor     rax, rsp
0x18003943e  mov     [rbp+57h+var_38], rax
0x180039442  xor     r12d, r12d
0x180039445  mov     [rbp+57h+var_70], rcx
0x180039449  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 10h
0x180039450  mov     rbx, r8
0x180039453  mov     [rbp+57h+var_78], rbx
0x180039457  mov     r15, rcx
0x18003945a  mov     r13b, r12b
0x18003945d  jnz     loc_180039880
0x180039463  lea     rcx, [rbp+57h+var_B8]
0x180039467  mov     [rbp+57h+var_B8], r12
0x18003946b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180039470  xor     edx, edx; pUnkOuter
0x180039472  lea     rax, [rbp+57h+var_B8]
0x180039476  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x18003947d  mov     [rsp+0F0h+ppv], rax; ppv
0x180039482  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180039489  lea     r8d, [rdx+1]; dwClsContext
0x18003948d  call    cs:__imp_CoCreateInstance
0x180039493  test    eax, eax
0x180039495  js      loc_1800396BB
0x18003949b  mov     rsi, r12
0x18003949e  mov     [rbp+57h+var_98], r12
0x1800394a2  mov     rdi, r12
0x1800394a5  mov     [rbp+57h+var_90], r12
0x1800394a9  mov     [rbp+57h+var_88], r12
0x1800394ad  lea     rdx, [rbp+57h+var_C0]
0x1800394b1  mov     [rbp+57h+var_80], r12
0x1800394b5  mov     r12, [rbp+57h+var_B8]
0x1800394b9  mov     rcx, r12
0x1800394bc  mov     [rbp+57h+var_C0], esi
0x1800394bf  mov     rax, [r12]
0x1800394c3  mov     rax, [rax+20h]
0x1800394c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394cc  test    eax, eax
0x1800394ce  js      loc_1800398B9
0x1800394d4  mov     r15d, [rbp+57h+var_C0]
0x1800394d8  cmp     r15d, 7FFFFFFFh
0x1800394df  ja      loc_180039691
0x1800394e5  xor     ebx, ebx
0x1800394e7  xor     r14d, r14d
0x1800394ea  test    r15d, r15d
0x1800394ed  jle     loc_1800396B3
0x1800394f3  test    ebx, ebx
0x1800394f5  js      loc_180039696
0x1800394fb  mov     rax, [r12]
0x1800394ff  lea     rcx, [rbp+57h+pv]
0x180039503  mov     [rbp+57h+pv], 0
0x18003950b  mov     rbx, [rax+28h]
0x18003950f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180039514  lea     r8, [rbp+57h+pv]
0x180039518  mov     edx, r14d
0x18003951b  mov     rcx, r12
0x18003951e  mov     rax, rbx
0x180039521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039526  mov     ebx, eax
0x180039528  test    eax, eax
0x18003952a  js      short loc_18003953E
0x18003952c  mov     rcx, [rbp+57h+pv]
0x180039530  call    cs:__imp_IsUserAllowedLogin
0x180039536  test    eax, eax
0x180039538  jnz     loc_1800396C8
0x18003953e  mov     rcx, [rbp+57h+pv]
0x180039542  test    rcx, rcx
0x180039545  jz      short loc_18003955B
0x180039547  mov     [rbp+57h+pv], 0
0x18003954f  mov     rax, [rcx]
0x180039552  mov     rax, [rax+10h]
0x180039556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003955b  inc     r14d
0x18003955e  cmp     r14d, r15d
0x180039561  jl      short loc_1800394F3
0x180039563  xor     r12d, r12d
0x180039566  test    ebx, ebx
0x180039568  js      loc_180039699
0x18003956e  cmp     rdi, 1
0x180039572  jnz     loc_1800395F8
0x180039578  mov     rbx, [rsi]
0x18003957b  test    rbx, rbx
0x18003957e  jz      short loc_18003958F
0x180039580  mov     rax, [rbx]
0x180039583  mov     rcx, rbx
0x180039586  mov     rax, [rax+8]
0x18003958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003958f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039593  mov     [rbp+57h+pv], r12
0x180039597  mov     [rbp+57h+var_48], rax
0x18003959b  lea     r8, [rbp+57h+propvar]
0x18003959f  mov     [rbp+57h+var_40], rax
0x1800395a3  lea     rdx, PKEY_SAM_Name
0x1800395aa  xor     eax, eax
0x1800395ac  xorps   xmm0, xmm0
0x1800395af  mov     [rbp+57h+var_A0], rax
0x1800395b3  mov     rcx, rbx
0x1800395b6  mov     rax, [rbx]
0x1800395b9  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x1800395bd  mov     rax, [rax+28h]
0x1800395c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395c6  test    eax, eax
0x1800395c8  jns     loc_18003984D
0x1800395ce  mov     rcx, [rbp+57h+pv]; pv
0x1800395d2  test    rcx, rcx
0x1800395d5  jz      short loc_1800395E1
0x1800395d7  call    cs:__imp_CoTaskMemFree
0x1800395dd  mov     [rbp+57h+pv], r12
0x1800395e1  mov     [rbp+57h+var_48], r12
0x1800395e5  mov     rcx, rbx
0x1800395e8  mov     [rbp+57h+var_40], r12
0x1800395ec  mov     rax, [rbx]
0x1800395ef  mov     rax, [rax+10h]
0x1800395f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395f8  test    rsi, rsi
0x1800395fb  jz      short loc_180039623
0x1800395fd  mov     rbx, r12
0x180039600  test    rdi, rdi
0x180039603  jz      short loc_180039616
0x180039605  lea     rcx, [rsi+rbx*8]
0x180039609  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18003960e  inc     rbx
0x180039611  cmp     rbx, rdi
0x180039614  jb      short loc_180039605
0x180039616  mov     rcx, rsi; pv
0x180039619  call    cs:__imp_CoTaskMemFree
0x18003961f  mov     [rbp+57h+var_98], r12
0x180039623  mov     [rbp+57h+var_90], r12
0x180039627  mov     [rbp+57h+var_80], r12
0x18003962b  mov     rbx, [rbp+57h+var_78]
0x18003962f  mov     r15, [rbp+57h+var_70]
0x180039633  lea     rcx, [rbp+57h+var_98]
0x180039637  call    ?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@@@QEAAXXZ; CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::RemoveAll(void)
0x18003963c  test    r13b, r13b
0x18003963f  jz      short loc_1800396BB
0x180039641  test    cs:Microsoft_Windows_Shell_AuthUIEnableBits, 10h
0x180039648  jnz     loc_1800398C1
0x18003964e  mov     rcx, [rbp+57h+var_B8]
0x180039652  test    rcx, rcx
0x180039655  jz      short loc_180039667
0x180039657  mov     [rbp+57h+var_B8], r12
0x18003965b  mov     rax, [rcx]
0x18003965e  mov     rax, [rax+10h]
0x180039662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039667  mov     al, r13b
0x18003966a  mov     rcx, [rbp+57h+var_38]
0x18003966e  xor     rcx, rsp; StackCookie
0x180039671  call    __security_check_cookie
0x180039676  mov     rbx, [rsp+0F0h+arg_8]
0x18003967e  add     rsp, 0C0h
0x180039685  pop     r15
0x180039687  pop     r14
0x180039689  pop     r13
0x18003968b  pop     r12
0x18003968d  pop     rdi
0x18003968e  pop     rsi
0x18003968f  pop     rbp
0x180039690  retn
0x180039691  mov     ebx, 80070216h
0x180039696  xor     r12d, r12d
0x180039699  lea     rcx, [rbp+57h+var_98]
0x18003969d  call    ?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@@@QEAAXXZ; CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::RemoveAll(void)
0x1800396a2  test    ebx, ebx
0x1800396a4  js      short loc_18003962B
0x1800396a6  mov     rdi, [rbp+57h+var_90]
0x1800396aa  mov     rsi, [rbp+57h+var_98]
0x1800396ae  jmp     loc_18003956E
0x1800396b3  xor     r12d, r12d
0x1800396b6  jmp     loc_18003956E
0x1800396bb  mov     [r15], r12w
0x1800396bf  mov     [rbx], r12w
0x1800396c3  jmp     loc_180039641
0x1800396c8  xor     ebx, ebx
0x1800396ca  cmp     rdi, [rbp+57h+var_80]
0x1800396ce  jnz     short loc_1800396EF
0x1800396d0  lea     rdx, [rdi+1]
0x1800396d4  lea     rcx, [rbp+57h+var_98]
0x1800396d8  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IPropertyStore>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IPropertyStore>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IPropertyStore>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800396dd  mov     rdi, [rbp+57h+var_90]
0x1800396e1  mov     ebx, eax
0x1800396e3  mov     rsi, [rbp+57h+var_98]
0x1800396e7  test    eax, eax
0x1800396e9  js      loc_18003953E
0x1800396ef  inc     rdi
0x1800396f2  mov     [rbp+57h+var_90], rdi
0x1800396f6  lea     rcx, [rdi-1]
0x1800396fa  lea     rcx, [rsi+rcx*8]
0x1800396fe  test    rcx, rcx
0x180039701  jz      loc_18003953E
0x180039707  mov     rax, [rbp+57h+pv]
0x18003970b  mov     [rcx], rax
0x18003970e  mov     rcx, [rbp+57h+pv]
0x180039712  test    rcx, rcx
0x180039715  jz      loc_18003953E
0x18003971b  mov     rax, [rcx]
0x18003971e  mov     rax, [rax+8]
0x180039722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039727  jmp     loc_18003953E
0x18003972c  lea     rcx, [rbp+57h+pvar]; pvar
0x180039730  call    cs:__imp_PropVariantClear
0x180039736  test    r14d, r14d
0x180039739  js      loc_180039847
0x18003973f  mov     r10, [rbp+57h+pv]
0x180039743  mov     r9d, 7FFFFFFEh
0x180039749  mov     rax, [rbp+57h+var_78]
0x18003974d  mov     edx, 100h
0x180039752  mov     ecx, r9d
0x180039755  mov     r8d, edx
0x180039758  test    rcx, rcx
0x18003975b  jz      short loc_18003977C
0x18003975d  movzx   r11d, word ptr [r10]
0x180039761  test    r11w, r11w
0x180039765  jz      short loc_18003977C
0x180039767  mov     [rax], r11w
0x18003976b  add     r10, 2
0x18003976f  add     rax, 2
0x180039773  dec     rcx
0x180039776  sub     r8, 1
0x18003977a  jnz     short loc_180039758
0x18003977c  test    r8, r8
0x18003977f  lea     rcx, [rax-2]
0x180039783  mov     r8, [rbp+57h+propvar]
0x180039787  cmovnz  rcx, rax
0x18003978b  mov     [rcx], r12w
0x18003978f  jz      short loc_1800397D1
0x180039791  mov     rax, [rbp+57h+var_70]
0x180039795  mov     rcx, r8
0x180039798  test    r9, r9
0x18003979b  jz      short loc_1800397BC
0x18003979d  movzx   r10d, word ptr [rcx]
0x1800397a1  test    r10w, r10w
0x1800397a5  jz      short loc_1800397BC
0x1800397a7  mov     [rax], r10w
0x1800397ab  add     rcx, 2
0x1800397af  add     rax, 2
0x1800397b3  dec     r9
0x1800397b6  sub     rdx, 1
0x1800397ba  jnz     short loc_180039798
0x1800397bc  test    rdx, rdx
0x1800397bf  lea     rcx, [rax-2]
0x1800397c3  cmovnz  rcx, rax
0x1800397c7  mov     [rcx], r12w
0x1800397cb  jnz     loc_1800398A7
0x1800397d1  test    r8, r8
0x1800397d4  jz      loc_1800395CE
0x1800397da  mov     rcx, r8; pv
0x1800397dd  call    cs:__imp_CoTaskMemFree
0x1800397e3  jmp     loc_1800395CE
0x1800397e8  lea     rdx, [rbp+57h+pv]; ppszOut
0x1800397ec  lea     rcx, [rbp+57h+propvar]; propvar
0x1800397f0  call    cs:__imp_PropVariantToStringAlloc
0x1800397f6  mov     r15d, eax
0x1800397f9  lea     rcx, [rbp+57h+propvar]; pvar
0x1800397fd  call    cs:__imp_PropVariantClear
0x180039803  test    r15d, r15d
0x180039806  js      loc_1800395CE
0x18003980c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039810  mov     [rbp+57h+propvar], r12
0x180039814  mov     [rbp+57h+propvar+8], rax
0x180039818  lea     r8, [rbp+57h+pvar]
0x18003981c  mov     [rbp+57h+var_A0], rax
0x180039820  lea     rdx, PKEY_SAM_Domain
0x180039827  xor     eax, eax
0x180039829  xorps   xmm0, xmm0
0x18003982c  mov     [rbp+57h+var_58], rax
0x180039830  mov     rcx, rbx
0x180039833  mov     rax, [rbx]
0x180039836  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18003983a  mov     rax, [rax+28h]
0x18003983e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039843  test    eax, eax
0x180039845  jns     short loc_18003985F
0x180039847  mov     r8, [rbp+57h+propvar]
0x18003984b  jmp     short loc_1800397D1
0x18003984d  mov     r14d, 80070490h
0x180039853  cmp     r12w, word ptr [rbp+57h+propvar]
0x180039858  jnz     short loc_1800397E8
0x18003985a  mov     r15d, r14d
0x18003985d  jmp     short loc_1800397F9
0x18003985f  cmp     r12w, word ptr [rbp+57h+pvar]
0x180039864  jz      loc_18003972C
0x18003986a  lea     rdx, [rbp+57h+propvar]; ppszOut
0x18003986e  lea     rcx, [rbp+57h+pvar]; propvar
0x180039872  call    cs:__imp_PropVariantToStringAlloc
0x180039878  mov     r14d, eax
0x18003987b  jmp     loc_18003972C
0x180039880  lea     rax, [rbp+57h+pv]
0x180039884  mov     r9d, 1
0x18003988a  lea     rdx, AuthUITraceId_Logon_AutoLogon_IsSingleUserNoPassword_Start
0x180039891  mov     [rsp+0F0h+ppv], rax
0x180039896  lea     rcx, Microsoft_Windows_Shell_AuthUI_Context
  ... truncated ...
```

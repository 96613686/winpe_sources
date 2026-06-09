# EnterpriseAppManager::GetIconToken(_GUID,ushort * *)

- ea: `0x180004250`
- end: `0x180004858`
- name: `?GetIconToken@EnterpriseAppManager@@UEAAJU_GUID@@PEAPEAG@Z`
- size: `1544`
- prototype: `int(EnterpriseAppManager *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003608`
- `0x180003728`
- `0x180004250`
- `0x180006780`
- `0x180006858`
- `0x180027afc`
- `0x180029f88`
- `0x180066da6`
- `0x180066db2`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800045c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800045c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000457c`
- `OLEAUT32!__imp_SysFreeString` at `0x180004588`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004678`
- `OLEAUT32!__imp_SysFreeString` at `0x180004684`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180004701`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047e4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000457c`
- `OLEAUT32!__imp_SysFreeString` at `0x180004588`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800045e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004678`
- `OLEAUT32!__imp_SysFreeString` at `0x180004684`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046f5`
- `OLEAUT32!__imp_SysFreeString` at `0x180004701`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047d8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047e4`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180004667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180004768`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180004667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x180004768`

## string_xrefs

- `0x1800042d3`: `EnterpriseAppManager::GetIconToken`
- `0x180004791`: `EnterpriseAppManager::GetIconToken`
- `0x18000450c`: `EnterpriseAppManager::GetIconToken - the EnterpriseId of the caller does not match that of the application being retrieved.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall EnterpriseAppManager::GetIconToken(
        EnterpriseAppManager *this,
        struct _GUID *a2,
        unsigned __int16 **a3)
{
  EnterpriseAppManager *v6; // rcx
  __int64 v7; // r8
  HRESULT CallerIds; // ebx
  int v9; // esi
  EnterpriseAppManager *v10; // rcx
  EnterpriseAppManager *v11; // rcx
  __int64 v12; // rax
  BSTR v14; // [rsp+30h] [rbp-D0h] BYREF
  BSTR v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcchPath; // [rsp+68h] [rbp-98h] BYREF
  DWORD v20; // [rsp+6Ch] [rbp-94h] BYREF
  PCWSTR pszUrl; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v23; // [rsp+80h] [rbp-80h] BYREF
  GUID Buf2; // [rsp+90h] [rbp-70h] BYREF
  GUID Buf1; // [rsp+A0h] [rbp-60h] BYREF
  GUID rguid; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  WCHAR pszPath[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v30[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  Buf1 = GUID_NULL;
  v23 = GUID_NULL;
  Buf2 = GUID_NULL;
  ppv = 0;
  v16 = 0;
  v22 = 0;
  pszUrl = 0;
  v15 = 0;
  memset_0(v30, 0, 0x208u);
  v20 = 260;
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 8) != 0 )
  {
    v27 = L"EnterpriseAppManager::GetIconToken";
    v28 = 70;
    McGenEventWrite_EventWriteTransfer(v6, EnterpriseAppMgmtSvcApiBegin, v7, 2, &rguid);
  }
  if ( !a3 )
  {
    CallerIds = -2147024809;
    goto LABEL_63;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    CallerIds = -2147467259;
    goto LABEL_63;
  }
  v9 = SecurityValidator<1>::CheckPermissionForOperation();
  CallerIds = GetCallerIds(&Buf1, &v23, 0);
  if ( CallerIds >= 0 )
  {
    rguid = v23;
    CallerIds = ConvertGuidToBstr(&rguid, &v15);
    if ( CallerIds >= 0 )
    {
      CallerIds = CoCreateInstance(&CLSID_PMSvc, 0, 0x17u, &IID_IPMEnumerationManager, &ppv);
      if ( CallerIds >= 0 )
      {
        v14 = 0;
        *(_QWORD *)&rguid.Data1 = 0;
        *(struct _GUID *)bstrString = v23;
        CallerIds = (*(__int64 (__fastcall **)(LPVOID, BSTR *, BSTR *))(*(_QWORD *)ppv + 72LL))(ppv, bstrString, &v14);
        if ( CallerIds < 0 )
        {
          if ( *(_QWORD *)&rguid.Data1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
          v6 = (EnterpriseAppManager *)v14;
          if ( v14 )
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
          goto LABEL_63;
        }
        if ( (**(int (__fastcall ***)(BSTR, GUID *, GUID *))v14)(
               v14,
               &GUID_2925390a_d947_4062_9dad_cf6f60e6a707,
               &rguid) >= 0 )
        {
          CallerIds = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)&rguid.Data1 + 24LL))(
                        *(_QWORD *)&rguid.Data1,
                        &v15);
          if ( CallerIds < 0 )
          {
            if ( *(_QWORD *)&rguid.Data1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
            v6 = (EnterpriseAppManager *)v14;
            if ( v14 )
              (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
            goto LABEL_63;
          }
        }
        if ( *(_QWORD *)&rguid.Data1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
        if ( v14 )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 16LL))(v14);
        rguid = *a2;
        CallerIds = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv + 72LL))(ppv, &rguid, &v16);
        if ( CallerIds >= 0 )
        {
          CallerIds = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v16 + 224LL))(v16, &Buf2);
          if ( CallerIds >= 0 )
          {
            if ( v9 < 0 && memcmp_0(&Buf1, &Buf2, 0x10u) )
            {
              if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
                McTemplateU0zq_EventWriteTransfer(
                  v6,
                  EnterpriseAppMgmtSvcError,
                  L"EnterpriseAppManager::GetIconToken - the EnterpriseId of the caller does not match that of the applica"
                   "tion being retrieved.",
                  (unsigned int)CallerIds);
              CallerIds = -2147024809;
              goto LABEL_63;
            }
            if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v16)(
                   v16,
                   &GUID_2925390a_d947_4062_9dad_cf6f60e6a707,
                   &v22) < 0 )
            {
              CallerIds = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v16 + 64LL))(v16, &pszUrl);
              if ( CallerIds >= 0 )
              {
                v6 = (EnterpriseAppManager *)pszUrl;
                if ( !pszUrl )
                  goto LABEL_62;
                v12 = -1;
                do
                  ++v12;
                while ( pszUrl[v12] );
                if ( v12 )
                {
                  CallerIds = PathCreateFromUrlW(pszUrl, v30, &v20, 0);
                  if ( CallerIds >= 0 )
                    CallerIds = EnterpriseAppManager::CreateDSSToken(v6, v30, v15, a3);
                }
                else
                {
LABEL_62:
                  CallerIds = -2147467259;
                }
              }
            }
            else
            {
              *(_QWORD *)&rguid.Data1 = 0;
              v14 = 0;
              bstrString[0] = 0;
              CallerIds = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 40LL))(v22, &v14);
              if ( CallerIds < 0 )
              {
                SysFreeString(bstrString[0]);
                SysFreeString(v14);
                v6 = *(EnterpriseAppManager **)&rguid.Data1;
                if ( *(_QWORD *)&rguid.Data1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
                goto LABEL_63;
              }
              CallerIds = CoCreateInstance(
                            &GUID_b9e511fc_e364_497a_a121_b7b3612cedce,
                            0,
                            0x17u,
                            &GUID_35f785fa_1979_4a8b_bc8f_fd70eb0d1544,
                            (LPVOID *)&rguid);
              if ( CallerIds < 0 )
              {
                SysFreeString(bstrString[0]);
                SysFreeString(v14);
                v6 = *(EnterpriseAppManager **)&rguid.Data1;
                if ( *(_QWORD *)&rguid.Data1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
                goto LABEL_63;
              }
              (*(void (__fastcall **)(_QWORD, BSTR, BSTR *))(**(_QWORD **)&rguid.Data1 + 240LL))(
                *(_QWORD *)&rguid.Data1,
                v14,
                bstrString);
              if ( (int)EnterpriseAppManager::CreateDSSToken(v10, bstrString[0], v15, a3) >= 0 )
                goto LABEL_52;
              memset_0(pszPath, 0, 0x208u);
              pcchPath = 260;
              CallerIds = PathCreateFromUrlW(bstrString[0], pszPath, &pcchPath, 0);
              if ( CallerIds < 0 )
              {
                SysFreeString(bstrString[0]);
                SysFreeString(v14);
                v6 = *(EnterpriseAppManager **)&rguid.Data1;
                if ( *(_QWORD *)&rguid.Data1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
                goto LABEL_63;
              }
              CallerIds = EnterpriseAppManager::CreateDSSToken(v11, pszPath, v15, a3);
              if ( CallerIds >= 0 )
              {
LABEL_52:
                SysFreeString(bstrString[0]);
                SysFreeString(v14);
                v6 = *(EnterpriseAppManager **)&rguid.Data1;
                if ( *(_QWORD *)&rguid.Data1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
              }
              else
              {
                SysFreeString(bstrString[0]);
                SysFreeString(v14);
                v6 = *(EnterpriseAppManager **)&rguid.Data1;
                if ( *(_QWORD *)&rguid.Data1 )
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&rguid.Data1 + 16LL))(*(_QWORD *)&rguid.Data1);
              }
            }
          }
        }
      }
    }
  }
LABEL_63:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 8) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v6,
      EnterpriseAppMgmtSvcApiEnd,
      L"EnterpriseAppManager::GetIconToken",
      (unsigned int)CallerIds);
  if ( CallerIds < 0 && (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      v6,
      EnterpriseAppMgmtSvcError,
      L"EnterpriseAppManager::GetIconToken",
      (unsigned int)CallerIds);
  SysFreeString(v15);
  SysFreeString((BSTR)pszUrl);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)CallerIds;
}

```

## disassembly

```asm
0x180004250  mov     [rsp-8+arg_18], rbx
0x180004255  push    rbp
0x180004256  push    rsi
0x180004257  push    rdi
0x180004258  push    r14
0x18000425a  push    r15
0x18000425c  lea     rbp, [rsp-400h]
0x180004264  sub     rsp, 500h
0x18000426b  mov     rax, cs:__security_cookie
0x180004272  xor     rax, rsp
0x180004275  mov     [rbp+420h+var_30], rax
0x18000427c  mov     rdi, r8
0x18000427f  mov     r14, rdx
0x180004282  mov     rbx, rcx
0x180004285  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000428c  movdqu  [rbp+420h+Buf1], xmm0
0x180004291  movdqu  xmmword ptr [rbp+420h+var_4A0.Data1], xmm0
0x180004296  movdqu  [rbp+420h+Buf2], xmm0
0x18000429b  xor     r15d, r15d
0x18000429e  mov     [rsp+520h+var_4C0], r15
0x1800042a3  mov     [rsp+520h+var_4E0], r15
0x1800042a8  mov     [rsp+520h+var_4A8], r15
0x1800042ad  mov     [rsp+520h+pszUrl], r15
0x1800042b2  mov     [rsp+520h+var_4E8], r15
0x1800042b7  xor     edx, edx; Val
0x1800042b9  mov     r8d, 208h; Size
0x1800042bf  lea     rcx, [rbp+420h+var_240]; void *
0x1800042c6  call    memset_0
0x1800042cb  mov     [rsp+520h+var_4B4], 104h
0x1800042d3  lea     rsi, aEnterpriseappm_1; "EnterpriseAppManager::GetIconToken"
0x1800042da  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x1800042e1  jz      short loc_180004308
0x1800042e3  mov     [rbp+420h+var_460], rsi
0x1800042e7  mov     [rbp+420h+var_458], 46h ; 'F'
0x1800042ef  lea     rax, [rbp+420h+rguid]
0x1800042f3  mov     [rsp+520h+ppv], rax
0x1800042f8  lea     r9d, [r15+2]
0x1800042fc  lea     rdx, EnterpriseAppMgmtSvcApiBegin
0x180004303  call    McGenEventWrite_EventWriteTransfer
0x180004308  test    rdi, rdi
0x18000430b  jnz     short loc_180004317
0x18000430d  mov     ebx, 80070057h
0x180004312  jmp     loc_180004798
0x180004317  cmp     [rbx+10h], r15
0x18000431b  jnz     short loc_180004327
0x18000431d  mov     ebx, 80004005h
0x180004322  jmp     loc_180004798
0x180004327  call    ?CheckPermissionForOperation@?$SecurityValidator@$00@@CAJPEBG@Z; SecurityValidator<1>::CheckPermissionForOperation(ushort const *)
0x18000432c  mov     esi, eax
0x18000432e  xor     r8d, r8d; unsigned int *
0x180004331  lea     rdx, [rbp+420h+var_4A0]; struct _GUID *
0x180004335  lea     rcx, [rbp+420h+Buf1]; struct _GUID *
0x180004339  call    ?GetCallerIds@@YAJPEAU_GUID@@0PEAK@Z; GetCallerIds(_GUID *,_GUID *,ulong *)
0x18000433e  mov     ebx, eax
0x180004340  test    eax, eax
0x180004342  js      loc_180004791
0x180004348  movaps  xmm0, xmmword ptr [rbp+420h+var_4A0.Data1]
0x18000434c  movdqa  xmmword ptr [rbp+420h+rguid.Data1], xmm0
0x180004351  lea     rdx, [rsp+520h+var_4E8]; unsigned __int16 **
0x180004356  lea     rcx, [rbp+420h+rguid]; rguid
0x18000435a  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x18000435f  mov     ebx, eax
0x180004361  test    eax, eax
0x180004363  js      loc_180004791
0x180004369  lea     rax, [rsp+520h+var_4C0]
0x18000436e  mov     [rsp+520h+ppv], rax; ppv
0x180004373  lea     r9, IID_IPMEnumerationManager; riid
0x18000437a  xor     edx, edx; pUnkOuter
0x18000437c  lea     r8d, [rdx+17h]; dwClsContext
0x180004380  lea     rcx, CLSID_PMSvc; rclsid
0x180004387  call    cs:__imp_CoCreateInstance
0x18000438d  mov     ebx, eax
0x18000438f  test    eax, eax
0x180004391  js      loc_180004791
0x180004397  mov     [rsp+520h+var_4F0], r15
0x18000439c  mov     qword ptr [rbp+420h+rguid.Data1], r15
0x1800043a0  mov     rcx, [rsp+520h+var_4C0]
0x1800043a5  movaps  xmm0, xmmword ptr [rbp+420h+var_4A0.Data1]
0x1800043a9  movdqa  xmmword ptr [rsp+520h+bstrString], xmm0
0x1800043af  mov     rax, [rcx]
0x1800043b2  lea     r8, [rsp+520h+var_4F0]
0x1800043b7  lea     rdx, [rsp+520h+bstrString]
0x1800043bc  mov     rax, [rax+48h]
0x1800043c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c5  mov     ebx, eax
0x1800043c7  test    eax, eax
0x1800043c9  jns     short loc_1800043FD
0x1800043cb  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800043cf  test    rcx, rcx
0x1800043d2  jz      short loc_1800043E1
0x1800043d4  mov     rax, [rcx]
0x1800043d7  mov     rax, [rax+10h]
0x1800043db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e0  nop
0x1800043e1  mov     rcx, [rsp+520h+var_4F0]
0x1800043e6  test    rcx, rcx
0x1800043e9  jz      short loc_1800043F8
0x1800043eb  mov     rax, [rcx]
0x1800043ee  mov     rax, [rax+10h]
0x1800043f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f7  nop
0x1800043f8  jmp     loc_180004791
0x1800043fd  mov     rcx, [rsp+520h+var_4F0]
0x180004402  mov     rax, [rcx]
0x180004405  lea     r8, [rbp+420h+rguid]
0x180004409  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180004410  mov     rax, [rax]
0x180004413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004418  test    eax, eax
0x18000441a  js      short loc_180004469
0x18000441c  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004420  mov     rax, [rcx]
0x180004423  lea     rdx, [rsp+520h+var_4E8]
0x180004428  mov     rax, [rax+18h]
0x18000442c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004431  mov     ebx, eax
0x180004433  test    eax, eax
0x180004435  jns     short loc_180004469
0x180004437  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x18000443b  test    rcx, rcx
0x18000443e  jz      short loc_18000444D
0x180004440  mov     rax, [rcx]
0x180004443  mov     rax, [rax+10h]
0x180004447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444c  nop
0x18000444d  mov     rcx, [rsp+520h+var_4F0]
0x180004452  test    rcx, rcx
0x180004455  jz      short loc_180004464
0x180004457  mov     rax, [rcx]
0x18000445a  mov     rax, [rax+10h]
0x18000445e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004463  nop
0x180004464  jmp     loc_180004791
0x180004469  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x18000446d  test    rcx, rcx
0x180004470  jz      short loc_18000447F
0x180004472  mov     rax, [rcx]
0x180004475  mov     rax, [rax+10h]
0x180004479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000447e  nop
0x18000447f  mov     rcx, [rsp+520h+var_4F0]
0x180004484  test    rcx, rcx
0x180004487  jz      short loc_180004496
0x180004489  mov     rax, [rcx]
0x18000448c  mov     rax, [rax+10h]
0x180004490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004495  nop
0x180004496  mov     rcx, [rsp+520h+var_4C0]
0x18000449b  movups  xmm0, xmmword ptr [r14]
0x18000449f  movdqu  xmmword ptr [rbp+420h+rguid.Data1], xmm0
0x1800044a4  mov     rax, [rcx]
0x1800044a7  lea     r8, [rsp+520h+var_4E0]
0x1800044ac  lea     rdx, [rbp+420h+rguid]
0x1800044b0  mov     rax, [rax+48h]
0x1800044b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b9  mov     ebx, eax
0x1800044bb  test    eax, eax
0x1800044bd  js      loc_180004791
0x1800044c3  mov     rcx, [rsp+520h+var_4E0]
0x1800044c8  mov     rax, [rcx]
0x1800044cb  lea     rdx, [rbp+420h+Buf2]
0x1800044cf  mov     rax, [rax+0E0h]
0x1800044d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044db  mov     ebx, eax
0x1800044dd  test    eax, eax
0x1800044df  js      loc_180004791
0x1800044e5  test    esi, esi
0x1800044e7  jns     short loc_180004529
0x1800044e9  mov     r8d, 10h; Size
0x1800044ef  lea     rdx, [rbp+420h+Buf2]; Buf2
0x1800044f3  lea     rcx, [rbp+420h+Buf1]; Buf1
0x1800044f7  call    memcmp_0
0x1800044fc  test    eax, eax
0x1800044fe  jz      short loc_180004529
0x180004500  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180004507  jz      short loc_18000451F
0x180004509  mov     r9d, ebx
0x18000450c  lea     r8, aEnterpriseappm_14; "EnterpriseAppManager::GetIconToken - th"...
0x180004513  lea     rdx, EnterpriseAppMgmtSvcError
0x18000451a  call    McTemplateU0zq_EventWriteTransfer
0x18000451f  mov     ebx, 80070057h
0x180004524  jmp     loc_180004791
0x180004529  mov     rcx, [rsp+520h+var_4E0]
0x18000452e  mov     rax, [rcx]
0x180004531  lea     r8, [rsp+520h+var_4A8]
0x180004536  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x18000453d  mov     rax, [rax]
0x180004540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004545  test    eax, eax
0x180004547  js      loc_180004720
0x18000454d  mov     qword ptr [rbp+420h+rguid.Data1], r15
0x180004551  mov     [rsp+520h+var_4F0], r15
0x180004556  mov     [rsp+520h+bstrString], r15
0x18000455b  mov     rcx, [rsp+520h+var_4A8]
0x180004560  mov     rax, [rcx]
0x180004563  lea     rdx, [rsp+520h+var_4F0]
0x180004568  mov     rax, [rax+28h]
0x18000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004571  mov     ebx, eax
0x180004573  test    eax, eax
0x180004575  jns     short loc_1800045AA
0x180004577  mov     rcx, [rsp+520h+bstrString]; bstrString
0x18000457c  call    cs:__imp_SysFreeString
0x180004582  nop
0x180004583  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x180004588  call    cs:__imp_SysFreeString
0x18000458e  nop
0x18000458f  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004593  test    rcx, rcx
0x180004596  jz      short loc_1800045A5
0x180004598  mov     rax, [rcx]
0x18000459b  mov     rax, [rax+10h]
0x18000459f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a4  nop
0x1800045a5  jmp     loc_180004791
0x1800045aa  lea     rax, [rbp+420h+rguid]
0x1800045ae  mov     [rsp+520h+ppv], rax; ppv
0x1800045b3  lea     r9, _GUID_35f785fa_1979_4a8b_bc8f_fd70eb0d1544; riid
0x1800045ba  xor     edx, edx; pUnkOuter
0x1800045bc  lea     r8d, [rdx+17h]; dwClsContext
0x1800045c0  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x1800045c7  call    cs:__imp_CoCreateInstance
0x1800045cd  mov     ebx, eax
0x1800045cf  test    eax, eax
0x1800045d1  jns     short loc_180004606
0x1800045d3  mov     rcx, [rsp+520h+bstrString]; bstrString
0x1800045d8  call    cs:__imp_SysFreeString
0x1800045de  nop
0x1800045df  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x1800045e4  call    cs:__imp_SysFreeString
0x1800045ea  nop
0x1800045eb  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800045ef  test    rcx, rcx
0x1800045f2  jz      short loc_180004601
0x1800045f4  mov     rax, [rcx]
0x1800045f7  mov     rax, [rax+10h]
0x1800045fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004600  nop
0x180004601  jmp     loc_180004791
0x180004606  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x18000460a  mov     rax, [rcx]
0x18000460d  lea     r8, [rsp+520h+bstrString]
0x180004612  mov     rdx, [rsp+520h+var_4F0]
0x180004617  mov     rax, [rax+0F0h]
0x18000461e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004623  mov     r9, rdi; unsigned __int16 **
0x180004626  mov     r8, [rsp+520h+var_4E8]; unsigned __int16 *
0x18000462b  mov     rdx, [rsp+520h+bstrString]; unsigned __int16 *
0x180004630  call    ?CreateDSSToken@EnterpriseAppManager@@AEAAJPEBG0PEAPEAG@Z; EnterpriseAppManager::CreateDSSToken(ushort const *,ushort const *,ushort * *)
0x180004635  test    eax, eax
0x180004637  jns     loc_1800046F0
0x18000463d  xor     edx, edx; Val
0x18000463f  mov     r8d, 208h; Size
0x180004645  lea     rcx, [rbp+420h+pszPath]; void *
0x180004649  call    memset_0
0x18000464e  mov     [rsp+520h+pcchPath], 104h
0x180004656  xor     r9d, r9d; dwFlags
0x180004659  lea     r8, [rsp+520h+pcchPath]; pcchPath
0x18000465e  lea     rdx, [rbp+420h+pszPath]; pszPath
0x180004662  mov     rcx, [rsp+520h+bstrString]; pszUrl
0x180004667  call    cs:__imp_PathCreateFromUrlW
0x18000466d  mov     ebx, eax
0x18000466f  test    eax, eax
0x180004671  jns     short loc_1800046A6
0x180004673  mov     rcx, [rsp+520h+bstrString]; bstrString
0x180004678  call    cs:__imp_SysFreeString
0x18000467e  nop
0x18000467f  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x180004684  call    cs:__imp_SysFreeString
0x18000468a  nop
0x18000468b  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x18000468f  test    rcx, rcx
0x180004692  jz      short loc_1800046A1
0x180004694  mov     rax, [rcx]
0x180004697  mov     rax, [rax+10h]
0x18000469b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a0  nop
0x1800046a1  jmp     loc_180004791
0x1800046a6  mov     r9, rdi; unsigned __int16 **
0x1800046a9  mov     r8, [rsp+520h+var_4E8]; unsigned __int16 *
0x1800046ae  lea     rdx, [rbp+420h+pszPath]; unsigned __int16 *
0x1800046b2  call    ?CreateDSSToken@EnterpriseAppManager@@AEAAJPEBG0PEAPEAG@Z; EnterpriseAppManager::CreateDSSToken(ushort const *,ushort const *,ushort * *)
0x1800046b7  mov     ebx, eax
0x1800046b9  test    eax, eax
0x1800046bb  jns     short loc_1800046F0
0x1800046bd  mov     rcx, [rsp+520h+bstrString]; bstrString
0x1800046c2  call    cs:__imp_SysFreeString
0x1800046c8  nop
0x1800046c9  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x1800046ce  call    cs:__imp_SysFreeString
0x1800046d4  nop
0x1800046d5  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800046d9  test    rcx, rcx
0x1800046dc  jz      short loc_1800046EB
0x1800046de  mov     rax, [rcx]
0x1800046e1  mov     rax, [rax+10h]
0x1800046e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ea  nop
0x1800046eb  jmp     loc_180004791
0x1800046f0  mov     rcx, [rsp+520h+bstrString]; bstrString
  ... truncated ...
```

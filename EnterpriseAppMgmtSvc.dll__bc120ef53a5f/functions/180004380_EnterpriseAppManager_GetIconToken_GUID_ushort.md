# EnterpriseAppManager::GetIconToken(_GUID,ushort * *)

- ea: `0x180004380`
- end: `0x1800049e9`
- name: `?GetIconToken@EnterpriseAppManager@@UEAAJU_GUID@@PEAPEAG@Z`
- size: `1641`
- prototype: `int(EnterpriseAppManager *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800036b8`
- `0x180003814`
- `0x180004380`
- `0x1800069dc`
- `0x180006ac0`
- `0x180029c84`
- `0x18002c194`
- `0x18006c8c6`
- `0x18006c8d2`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800044b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004709`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800044b7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004709`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004720`
- `OLEAUT32!__imp_SysFreeString` at `0x180004732`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004828`
- `OLEAUT32!__imp_SysFreeString` at `0x18000483a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004867`
- `OLEAUT32!__imp_SysFreeString` at `0x180004879`
- `OLEAUT32!__imp_SysFreeString` at `0x18000495c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000496e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800046c4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004720`
- `OLEAUT32!__imp_SysFreeString` at `0x180004732`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047d2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004828`
- `OLEAUT32!__imp_SysFreeString` at `0x18000483a`
- `OLEAUT32!__imp_SysFreeString` at `0x180004867`
- `OLEAUT32!__imp_SysFreeString` at `0x180004879`
- `OLEAUT32!__imp_SysFreeString` at `0x18000495c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000496e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800047bb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800048e6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800047bb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathCreateFromUrlW` at `0x1800048e6`

## string_xrefs

- `0x180004403`: `EnterpriseAppManager::GetIconToken`
- `0x180004915`: `EnterpriseAppManager::GetIconToken`
- `0x180004642`: `EnterpriseAppManager::GetIconToken - the EnterpriseId of the caller does not match that of the application being retrieved.`

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
    McGenEventWrite_EventWriteTransfer(v6, EnterpriseAppMgmtSvcApiBegin, v7, 2);
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
  v9 = SecurityValidator<1>::CheckPermissionForOperation(v6);
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
0x180004380  mov     [rsp-8+arg_18], rbx
0x180004385  push    rbp
0x180004386  push    rsi
0x180004387  push    rdi
0x180004388  push    r14
0x18000438a  push    r15
0x18000438c  lea     rbp, [rsp-400h]
0x180004394  sub     rsp, 500h
0x18000439b  mov     rax, cs:__security_cookie
0x1800043a2  xor     rax, rsp
0x1800043a5  mov     [rbp+420h+var_30], rax
0x1800043ac  mov     rdi, r8
0x1800043af  mov     r14, rdx
0x1800043b2  mov     rbx, rcx
0x1800043b5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800043bc  movdqu  [rbp+420h+Buf1], xmm0
0x1800043c1  movdqu  xmmword ptr [rbp+420h+var_4A0.Data1], xmm0
0x1800043c6  movdqu  [rbp+420h+Buf2], xmm0
0x1800043cb  xor     r15d, r15d
0x1800043ce  mov     [rsp+520h+var_4C0], r15
0x1800043d3  mov     [rsp+520h+var_4E0], r15
0x1800043d8  mov     [rsp+520h+var_4A8], r15
0x1800043dd  mov     [rsp+520h+pszUrl], r15
0x1800043e2  mov     [rsp+520h+var_4E8], r15
0x1800043e7  xor     edx, edx; Val
0x1800043e9  mov     r8d, 208h; Size
0x1800043ef  lea     rcx, [rbp+420h+var_240]; void *
0x1800043f6  call    memset_0
0x1800043fb  mov     [rsp+520h+var_4B4], 104h
0x180004403  lea     rsi, aEnterpriseappm_1; "EnterpriseAppManager::GetIconToken"
0x18000440a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 8
0x180004411  jz      short loc_180004438
0x180004413  mov     [rbp+420h+var_460], rsi
0x180004417  mov     [rbp+420h+var_458], 46h ; 'F'
0x18000441f  lea     rax, [rbp+420h+rguid]
0x180004423  mov     [rsp+520h+ppv], rax
0x180004428  lea     r9d, [r15+2]
0x18000442c  lea     rdx, EnterpriseAppMgmtSvcApiBegin
0x180004433  call    McGenEventWrite_EventWriteTransfer
0x180004438  test    rdi, rdi
0x18000443b  jnz     short loc_180004447
0x18000443d  mov     ebx, 80070057h
0x180004442  jmp     loc_18000491C
0x180004447  cmp     [rbx+10h], r15
0x18000444b  jnz     short loc_180004457
0x18000444d  mov     ebx, 80004005h
0x180004452  jmp     loc_18000491C
0x180004457  call    ?CheckPermissionForOperation@?$SecurityValidator@$00@@CAJPEBG@Z; SecurityValidator<1>::CheckPermissionForOperation(ushort const *)
0x18000445c  mov     esi, eax
0x18000445e  xor     r8d, r8d; unsigned int *
0x180004461  lea     rdx, [rbp+420h+var_4A0]; struct _GUID *
0x180004465  lea     rcx, [rbp+420h+Buf1]; struct _GUID *
0x180004469  call    ?GetCallerIds@@YAJPEAU_GUID@@0PEAK@Z; GetCallerIds(_GUID *,_GUID *,ulong *)
0x18000446e  mov     ebx, eax
0x180004470  test    eax, eax
0x180004472  js      loc_180004915
0x180004478  movaps  xmm0, xmmword ptr [rbp+420h+var_4A0.Data1]
0x18000447c  movdqa  xmmword ptr [rbp+420h+rguid.Data1], xmm0
0x180004481  lea     rdx, [rsp+520h+var_4E8]; unsigned __int16 **
0x180004486  lea     rcx, [rbp+420h+rguid]; rguid
0x18000448a  call    ?ConvertGuidToBstr@@YAJU_GUID@@PEAPEAG@Z; ConvertGuidToBstr(_GUID,ushort * *)
0x18000448f  mov     ebx, eax
0x180004491  test    eax, eax
0x180004493  js      loc_180004915
0x180004499  lea     rax, [rsp+520h+var_4C0]
0x18000449e  mov     [rsp+520h+ppv], rax; ppv
0x1800044a3  lea     r9, IID_IPMEnumerationManager; riid
0x1800044aa  xor     edx, edx; pUnkOuter
0x1800044ac  lea     r8d, [rdx+17h]; dwClsContext
0x1800044b0  lea     rcx, CLSID_PMSvc; rclsid
0x1800044b7  call    cs:__imp_CoCreateInstance
0x1800044be  nop     dword ptr [rax+rax+00h]
0x1800044c3  mov     ebx, eax
0x1800044c5  test    eax, eax
0x1800044c7  js      loc_180004915
0x1800044cd  mov     [rsp+520h+var_4F0], r15
0x1800044d2  mov     qword ptr [rbp+420h+rguid.Data1], r15
0x1800044d6  mov     rcx, [rsp+520h+var_4C0]
0x1800044db  movaps  xmm0, xmmword ptr [rbp+420h+var_4A0.Data1]
0x1800044df  movdqa  xmmword ptr [rsp+520h+bstrString], xmm0
0x1800044e5  mov     rax, [rcx]
0x1800044e8  lea     r8, [rsp+520h+var_4F0]
0x1800044ed  lea     rdx, [rsp+520h+bstrString]
0x1800044f2  mov     rax, [rax+48h]
0x1800044f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fb  mov     ebx, eax
0x1800044fd  test    eax, eax
0x1800044ff  jns     short loc_180004533
0x180004501  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004505  test    rcx, rcx
0x180004508  jz      short loc_180004517
0x18000450a  mov     rax, [rcx]
0x18000450d  mov     rax, [rax+10h]
0x180004511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004516  nop
0x180004517  mov     rcx, [rsp+520h+var_4F0]
0x18000451c  test    rcx, rcx
0x18000451f  jz      short loc_18000452E
0x180004521  mov     rax, [rcx]
0x180004524  mov     rax, [rax+10h]
0x180004528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452d  nop
0x18000452e  jmp     loc_180004915
0x180004533  mov     rcx, [rsp+520h+var_4F0]
0x180004538  mov     rax, [rcx]
0x18000453b  lea     r8, [rbp+420h+rguid]
0x18000453f  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180004546  mov     rax, [rax]
0x180004549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454e  test    eax, eax
0x180004550  js      short loc_18000459F
0x180004552  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004556  mov     rax, [rcx]
0x180004559  lea     rdx, [rsp+520h+var_4E8]
0x18000455e  mov     rax, [rax+18h]
0x180004562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004567  mov     ebx, eax
0x180004569  test    eax, eax
0x18000456b  jns     short loc_18000459F
0x18000456d  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004571  test    rcx, rcx
0x180004574  jz      short loc_180004583
0x180004576  mov     rax, [rcx]
0x180004579  mov     rax, [rax+10h]
0x18000457d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004582  nop
0x180004583  mov     rcx, [rsp+520h+var_4F0]
0x180004588  test    rcx, rcx
0x18000458b  jz      short loc_18000459A
0x18000458d  mov     rax, [rcx]
0x180004590  mov     rax, [rax+10h]
0x180004594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004599  nop
0x18000459a  jmp     loc_180004915
0x18000459f  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800045a3  test    rcx, rcx
0x1800045a6  jz      short loc_1800045B5
0x1800045a8  mov     rax, [rcx]
0x1800045ab  mov     rax, [rax+10h]
0x1800045af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b4  nop
0x1800045b5  mov     rcx, [rsp+520h+var_4F0]
0x1800045ba  test    rcx, rcx
0x1800045bd  jz      short loc_1800045CC
0x1800045bf  mov     rax, [rcx]
0x1800045c2  mov     rax, [rax+10h]
0x1800045c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045cb  nop
0x1800045cc  mov     rcx, [rsp+520h+var_4C0]
0x1800045d1  movups  xmm0, xmmword ptr [r14]
0x1800045d5  movdqu  xmmword ptr [rbp+420h+rguid.Data1], xmm0
0x1800045da  mov     rax, [rcx]
0x1800045dd  lea     r8, [rsp+520h+var_4E0]
0x1800045e2  lea     rdx, [rbp+420h+rguid]
0x1800045e6  mov     rax, [rax+48h]
0x1800045ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ef  mov     ebx, eax
0x1800045f1  test    eax, eax
0x1800045f3  js      loc_180004915
0x1800045f9  mov     rcx, [rsp+520h+var_4E0]
0x1800045fe  mov     rax, [rcx]
0x180004601  lea     rdx, [rbp+420h+Buf2]
0x180004605  mov     rax, [rax+0E0h]
0x18000460c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004611  mov     ebx, eax
0x180004613  test    eax, eax
0x180004615  js      loc_180004915
0x18000461b  test    esi, esi
0x18000461d  jns     short loc_18000465F
0x18000461f  mov     r8d, 10h; Size
0x180004625  lea     rdx, [rbp+420h+Buf2]; Buf2
0x180004629  lea     rcx, [rbp+420h+Buf1]; Buf1
0x18000462d  call    memcmp_0
0x180004632  test    eax, eax
0x180004634  jz      short loc_18000465F
0x180004636  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18000463d  jz      short loc_180004655
0x18000463f  mov     r9d, ebx
0x180004642  lea     r8, aEnterpriseappm_14; "EnterpriseAppManager::GetIconToken - th"...
0x180004649  lea     rdx, EnterpriseAppMgmtSvcError
0x180004650  call    McTemplateU0zq_EventWriteTransfer
0x180004655  mov     ebx, 80070057h
0x18000465a  jmp     loc_180004915
0x18000465f  mov     rcx, [rsp+520h+var_4E0]
0x180004664  mov     rax, [rcx]
0x180004667  lea     r8, [rsp+520h+var_4A8]
0x18000466c  lea     rdx, _GUID_2925390a_d947_4062_9dad_cf6f60e6a707
0x180004673  mov     rax, [rax]
0x180004676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467b  test    eax, eax
0x18000467d  js      loc_18000489E
0x180004683  mov     qword ptr [rbp+420h+rguid.Data1], r15
0x180004687  mov     [rsp+520h+var_4F0], r15
0x18000468c  mov     [rsp+520h+bstrString], r15
0x180004691  mov     rcx, [rsp+520h+var_4A8]
0x180004696  mov     rax, [rcx]
0x180004699  lea     rdx, [rsp+520h+var_4F0]
0x18000469e  mov     rax, [rax+28h]
0x1800046a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a7  mov     ebx, eax
0x1800046a9  test    eax, eax
0x1800046ab  jns     short loc_1800046EC
0x1800046ad  mov     rcx, [rsp+520h+bstrString]; bstrString
0x1800046b2  call    cs:__imp_SysFreeString
0x1800046b9  nop     dword ptr [rax+rax+00h]
0x1800046be  nop
0x1800046bf  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x1800046c4  call    cs:__imp_SysFreeString
0x1800046cb  nop     dword ptr [rax+rax+00h]
0x1800046d0  nop
0x1800046d1  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800046d5  test    rcx, rcx
0x1800046d8  jz      short loc_1800046E7
0x1800046da  mov     rax, [rcx]
0x1800046dd  mov     rax, [rax+10h]
0x1800046e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e6  nop
0x1800046e7  jmp     loc_180004915
0x1800046ec  lea     rax, [rbp+420h+rguid]
0x1800046f0  mov     [rsp+520h+ppv], rax; ppv
0x1800046f5  lea     r9, _GUID_35f785fa_1979_4a8b_bc8f_fd70eb0d1544; riid
0x1800046fc  xor     edx, edx; pUnkOuter
0x1800046fe  lea     r8d, [rdx+17h]; dwClsContext
0x180004702  lea     rcx, _GUID_b9e511fc_e364_497a_a121_b7b3612cedce; rclsid
0x180004709  call    cs:__imp_CoCreateInstance
0x180004710  nop     dword ptr [rax+rax+00h]
0x180004715  mov     ebx, eax
0x180004717  test    eax, eax
0x180004719  jns     short loc_18000475A
0x18000471b  mov     rcx, [rsp+520h+bstrString]; bstrString
0x180004720  call    cs:__imp_SysFreeString
0x180004727  nop     dword ptr [rax+rax+00h]
0x18000472c  nop
0x18000472d  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x180004732  call    cs:__imp_SysFreeString
0x180004739  nop     dword ptr [rax+rax+00h]
0x18000473e  nop
0x18000473f  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x180004743  test    rcx, rcx
0x180004746  jz      short loc_180004755
0x180004748  mov     rax, [rcx]
0x18000474b  mov     rax, [rax+10h]
0x18000474f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004754  nop
0x180004755  jmp     loc_180004915
0x18000475a  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x18000475e  mov     rax, [rcx]
0x180004761  lea     r8, [rsp+520h+bstrString]
0x180004766  mov     rdx, [rsp+520h+var_4F0]
0x18000476b  mov     rax, [rax+0F0h]
0x180004772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004777  mov     r9, rdi; unsigned __int16 **
0x18000477a  mov     r8, [rsp+520h+var_4E8]; unsigned __int16 *
0x18000477f  mov     rdx, [rsp+520h+bstrString]; unsigned __int16 *
0x180004784  call    ?CreateDSSToken@EnterpriseAppManager@@AEAAJPEBG0PEAPEAG@Z; EnterpriseAppManager::CreateDSSToken(ushort const *,ushort const *,ushort * *)
0x180004789  test    eax, eax
0x18000478b  jns     loc_180004862
0x180004791  xor     edx, edx; Val
0x180004793  mov     r8d, 208h; Size
0x180004799  lea     rcx, [rbp+420h+pszPath]; void *
0x18000479d  call    memset_0
0x1800047a2  mov     [rsp+520h+pcchPath], 104h
0x1800047aa  xor     r9d, r9d; dwFlags
0x1800047ad  lea     r8, [rsp+520h+pcchPath]; pcchPath
0x1800047b2  lea     rdx, [rbp+420h+pszPath]; pszPath
0x1800047b6  mov     rcx, [rsp+520h+bstrString]; pszUrl
0x1800047bb  call    cs:__imp_PathCreateFromUrlW
0x1800047c2  nop     dword ptr [rax+rax+00h]
0x1800047c7  mov     ebx, eax
0x1800047c9  test    eax, eax
0x1800047cb  jns     short loc_18000480C
0x1800047cd  mov     rcx, [rsp+520h+bstrString]; bstrString
0x1800047d2  call    cs:__imp_SysFreeString
0x1800047d9  nop     dword ptr [rax+rax+00h]
0x1800047de  nop
0x1800047df  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x1800047e4  call    cs:__imp_SysFreeString
0x1800047eb  nop     dword ptr [rax+rax+00h]
0x1800047f0  nop
0x1800047f1  mov     rcx, qword ptr [rbp+420h+rguid.Data1]
0x1800047f5  test    rcx, rcx
0x1800047f8  jz      short loc_180004807
0x1800047fa  mov     rax, [rcx]
0x1800047fd  mov     rax, [rax+10h]
0x180004801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004806  nop
0x180004807  jmp     loc_180004915
0x18000480c  mov     r9, rdi; unsigned __int16 **
0x18000480f  mov     r8, [rsp+520h+var_4E8]; unsigned __int16 *
0x180004814  lea     rdx, [rbp+420h+pszPath]; unsigned __int16 *
0x180004818  call    ?CreateDSSToken@EnterpriseAppManager@@AEAAJPEBG0PEAPEAG@Z; EnterpriseAppManager::CreateDSSToken(ushort const *,ushort const *,ushort * *)
0x18000481d  mov     ebx, eax
0x18000481f  test    eax, eax
0x180004821  jns     short loc_180004862
0x180004823  mov     rcx, [rsp+520h+bstrString]; bstrString
0x180004828  call    cs:__imp_SysFreeString
0x18000482f  nop     dword ptr [rax+rax+00h]
0x180004834  nop
0x180004835  mov     rcx, [rsp+520h+var_4F0]; bstrString
0x18000483a  call    cs:__imp_SysFreeString
  ... truncated ...
```

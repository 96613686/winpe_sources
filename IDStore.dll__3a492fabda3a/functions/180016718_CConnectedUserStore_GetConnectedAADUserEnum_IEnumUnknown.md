# CConnectedUserStore::GetConnectedAADUserEnum(IEnumUnknown * *)

- ea: `0x180016718`
- end: `0x180016bb1`
- name: `?GetConnectedAADUserEnum@CConnectedUserStore@@AEAAJPEAPEAUIEnumUnknown@@@Z`
- size: `1177`
- prototype: `__int64 __fastcall(CConnectedUserStore *__hidden this, struct IEnumUnknown **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004490`

## callees

- `0x180003560`
- `0x180003a70`
- `0x180005ea0`
- `0x18000acb0`
- `0x18000c040`
- `0x18000e39c`
- `0x18000e530`
- `0x18000edb4`
- `0x1800144b4`
- `0x180015948`
- `0x18001596c`
- `0x1800159c4`
- `0x1800159e4`
- `0x180016718`
- `0x180018ac4`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800168a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800168a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800168d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016939`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001699b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001699b`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800169d7`
- `api-ms-win-security-base-l1-1-0!EqualDomainSid` at `0x1800169d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001696b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001696b`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800169ff`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800169ff`

## pseudocode

```c
__int64 __fastcall CConnectedUserStore::GetConnectedAADUserEnum(CConnectedUserStore *this, struct IEnumUnknown **a2)
{
  CIdentityProfileHandler *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  int v6; // eax
  char *v7; // rsi
  CIdentityProfileHandler *v8; // rcx
  __int64 v9; // rdx
  HKEY v10; // rbx
  LSTATUS v11; // r15d
  DWORD i; // r14d
  BOOL v13; // ebx
  DWORD LastError; // eax
  int v15; // eax
  CConnectedUser *v16; // rbx
  __int64 v17; // r9
  CIdentityProfileHandler *v18; // rcx
  __int64 v19; // rdx
  unsigned int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // r8
  int MachineSid; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSid1; // [rsp+48h] [rbp-B8h] BYREF
  BOOL pfEqual; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  PSID pSid2; // [rsp+68h] [rbp-98h] BYREF
  PSID *p_pSid2; // [rsp+70h] [rbp-90h] BYREF
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  char v33; // [rsp+80h] [rbp-80h]
  struct IUnknown *v34; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[16]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[144]; // [rsp+A0h] [rbp-60h] BYREF

  MachineSid = 0;
  pSid1 = 0;
  v34 = 0;
  pSid2 = 0;
  hKey = 0;
  CLogBlock::CLogBlock((CLogBlock *)v35, "CConnectedUserStore::GetConnectedAADUserEnum", &MachineSid);
  if ( !a2 )
  {
    MachineSid = -2147467261;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = 23;
      v5 = 2147500035LL;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v5);
      goto LABEL_51;
    }
    goto LABEL_51;
  }
  *a2 = 0;
  p_pSid2 = &pSid2;
  Sid = 0;
  v33 = 1;
  MachineSid = GetMachineSid(&Sid);
  wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSid2);
  if ( MachineSid >= 0 )
  {
    v6 = ATL::CComObject<CGenericEnum>::CreateInstance(&pSid1);
    MachineSid = v6;
    v7 = (char *)pSid1;
    if ( v6 >= 0 )
    {
      (*(void (__fastcall **)(PSID))(*(_QWORD *)pSid1 + 8LL))(pSid1);
      *(GUID *)(v7 + 92) = GUID_9d5f2149_de8c_45f2_b313_6587a04f771d;
      MachineSid = 0;
      v10 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&pSid1);
        RegCloseKey(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&pSid1);
      }
      hKey = 0;
      v11 = RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
              0,
              0x20019u,
              &hKey);
      if ( !v11 )
      {
        for ( i = 0; !v11; ++i )
        {
          memset_0(Name, 0, 0x112u);
          cchName = 137;
          v11 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
          if ( !v11 )
          {
            pSid1 = 0;
            p_pSid2 = &pSid1;
            Sid = 0;
            v33 = 1;
            v13 = ConvertStringSidToSidW(Name, &Sid);
            wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSid2);
            if ( v13 )
            {
              pfEqual = 0;
              if ( EqualDomainSid(pSid1, pSid2, &pfEqual) )
              {
                if ( pfEqual )
                {
                  v27 = 0;
                  if ( (int)LsaLookupUserAccountType(pSid1, &v27) >= 0 && v27 == 5 )
                  {
                    v15 = ATL::CComObject<CConnectedUser>::CreateInstance(&v34);
                    MachineSid = v15;
                    if ( v15 < 0 )
                    {
                      v18 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      {
                        goto LABEL_43;
                      }
                      v19 = 28;
                      v17 = (unsigned int)v15;
LABEL_42:
                      WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, v17);
                      goto LABEL_43;
                    }
                    v16 = (CConnectedUser *)v34;
                    ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->AddRef)(v34);
                    MachineSid = CConnectedUser::InitializeConnectedAADUser(v16, pSid1);
                    if ( MachineSid < 0 )
                    {
                      (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v16 + 16LL))(v16);
                      v18 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
                      {
                        goto LABEL_43;
                      }
                      v19 = 29;
                      v17 = (unsigned int)MachineSid;
                      goto LABEL_42;
                    }
                    MachineSid = CGenericEnum::Add((CGenericEnum *)v7, (struct IUnknown *)v16);
                    (*(void (__fastcall **)(CConnectedUser *))(*(_QWORD *)v16 + 16LL))(v16);
                    v17 = (unsigned int)MachineSid;
                    if ( MachineSid < 0 )
                    {
                      v18 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                      {
                        v19 = 30;
                        goto LABEL_42;
                      }
LABEL_43:
                      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid1);
                      goto LABEL_49;
                    }
                  }
                }
              }
            }
            else if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids,
                LastError);
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid1);
          }
        }
      }
      v6 = (**(__int64 (__fastcall ***)(PSID, GUID *, struct IEnumUnknown **))v7)(
             v7,
             &GUID_00000100_0000_0000_c000_000000000046,
             a2);
      MachineSid = v6;
      if ( v6 >= 0 )
        goto LABEL_49;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_49;
      }
      v9 = 31;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_49:
        if ( v7 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))(v7);
        goto LABEL_51;
      }
      v9 = 25;
    }
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids, (unsigned int)v6);
    goto LABEL_49;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = 24;
    v5 = (unsigned int)MachineSid;
    goto LABEL_5;
  }
LABEL_51:
  v20 = MapErrorCodes(MachineSid);
  CLogBlock::~CLogBlock((CLogBlock *)v35, v21, v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSid2);
  return v20;
}

```

## disassembly

```asm
0x180016718  push    rbp
0x18001671a  push    rbx
0x18001671b  push    rsi
0x18001671c  push    rdi
0x18001671d  push    r12
0x18001671f  push    r13
0x180016721  push    r14
0x180016723  push    r15
0x180016725  lea     rbp, [rsp-0D8h]
0x18001672d  sub     rsp, 1D8h
0x180016734  mov     rax, cs:__security_cookie
0x18001673b  xor     rax, rsp
0x18001673e  mov     [rbp+110h+var_50], rax
0x180016745  mov     r12, rdx
0x180016748  xor     r13d, r13d
0x18001674b  mov     [rsp+210h+var_1D0], r13d
0x180016750  mov     [rsp+210h+pSid1], r13
0x180016755  mov     [rbp+110h+var_188], r13
0x180016759  mov     [rsp+210h+pSid2], r13
0x18001675e  mov     [rsp+210h+hKey], r13
0x180016763  lea     r8, [rsp+210h+var_1D0]; int *
0x180016768  lea     rdx, aCconnecteduser_12; "CConnectedUserStore::GetConnectedAADUse"...
0x18001676f  lea     rcx, [rbp+110h+var_180]; this
0x180016773  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x180016778  nop
0x180016779  test    r12, r12
0x18001677c  jnz     short loc_1800167C6
0x18001677e  mov     [rsp+210h+var_1D0], 80004003h
0x180016786  lea     rdi, WPP_GLOBAL_Control
0x18001678d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016794  cmp     rcx, rdi
0x180016797  jz      loc_180016B62
0x18001679d  test    byte ptr [rcx+1Ch], 4
0x1800167a1  jz      loc_180016B62
0x1800167a7  lea     edx, [r13+17h]
0x1800167ab  mov     r9d, 80004003h
0x1800167b1  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800167b8  mov     rcx, [rcx+10h]
0x1800167bc  call    WPP_SF_d
0x1800167c1  jmp     loc_180016B62
0x1800167c6  mov     [r12], r13
0x1800167ca  lea     rax, [rsp+210h+pSid2]
0x1800167cf  mov     [rsp+210h+var_1A0], rax
0x1800167d4  mov     [rsp+210h+Sid], r13
0x1800167d9  mov     [rbp+110h+var_190], 1
0x1800167dd  lea     rcx, [rsp+210h+Sid]; void **
0x1800167e2  call    ?GetMachineSid@@YAJPEAPEAX@Z; GetMachineSid(void * *)
0x1800167e7  mov     [rsp+210h+var_1D0], eax
0x1800167eb  lea     rcx, [rsp+210h+var_1A0]
0x1800167f0  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800167f5  mov     eax, [rsp+210h+var_1D0]
0x1800167f9  test    eax, eax
0x1800167fb  jns     short loc_180016828
0x1800167fd  lea     rdi, WPP_GLOBAL_Control
0x180016804  mov     rcx, cs:WPP_GLOBAL_Control
0x18001680b  cmp     rcx, rdi
0x18001680e  jz      loc_180016B62
0x180016814  test    byte ptr [rcx+1Ch], 4
0x180016818  jz      loc_180016B62
0x18001681e  mov     edx, 18h
0x180016823  mov     r9d, eax
0x180016826  jmp     short loc_1800167B1
0x180016828  lea     rcx, [rsp+210h+pSid1]
0x18001682d  call    ?CreateInstance@?$CComObject@VCGenericEnum@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGenericEnum>::CreateInstance(ATL::CComObject<CGenericEnum> * *)
0x180016832  mov     [rsp+210h+var_1D0], eax
0x180016836  mov     rsi, [rsp+210h+pSid1]
0x18001683b  test    eax, eax
0x18001683d  jns     short loc_18001686A
0x18001683f  lea     rdi, WPP_GLOBAL_Control
0x180016846  mov     rcx, cs:WPP_GLOBAL_Control
0x18001684d  cmp     rcx, rdi
0x180016850  jz      loc_180016B4E
0x180016856  test    byte ptr [rcx+1Ch], 4
0x18001685a  jz      loc_180016B4E
0x180016860  mov     edx, 19h
0x180016865  jmp     loc_180016B3B
0x18001686a  mov     rax, [rsi]
0x18001686d  mov     rcx, rsi
0x180016870  mov     rax, [rax+8]
0x180016874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016879  movups  xmm0, xmmword ptr cs:_GUID_9d5f2149_de8c_45f2_b313_6587a04f771d.Data1
0x180016880  movdqu  xmmword ptr [rsi+5Ch], xmm0
0x180016885  mov     [rsp+210h+var_1D0], r13d
0x18001688a  mov     rbx, [rsp+210h+hKey]
0x18001688f  test    rbx, rbx
0x180016892  jz      short loc_1800168B1
0x180016894  lea     rcx, [rsp+210h+pSid1]; this
0x180016899  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001689e  mov     rcx, rbx; hKey
0x1800168a1  call    cs:__imp_RegCloseKey
0x1800168a7  lea     rcx, [rsp+210h+pSid1]; this
0x1800168ac  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800168b1  mov     [rsp+210h+hKey], r13
0x1800168b6  lea     rax, [rsp+210h+hKey]
0x1800168bb  mov     [rsp+210h+phkResult], rax; phkResult
0x1800168c0  mov     r9d, 20019h; samDesired
0x1800168c6  xor     r8d, r8d; ulOptions
0x1800168c9  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800168d0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800168d7  call    cs:__imp_RegOpenKeyExW
0x1800168dd  mov     r15d, eax
0x1800168e0  lea     rdi, WPP_GLOBAL_Control
0x1800168e7  test    eax, eax
0x1800168e9  jnz     loc_180016B04
0x1800168ef  mov     r14d, r13d
0x1800168f2  test    r15d, r15d
0x1800168f5  jnz     loc_180016B04
0x1800168fb  xor     edx, edx; Val
0x1800168fd  mov     r8d, 112h; Size
0x180016903  lea     rcx, [rbp+110h+Name]; void *
0x180016907  call    memset_0
0x18001690c  mov     [rsp+210h+cchName], 89h
0x180016914  mov     [rsp+210h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180016919  mov     [rsp+210h+lpcchClass], r13; lpcchClass
0x18001691e  mov     [rsp+210h+lpClass], r13; lpClass
0x180016923  mov     [rsp+210h+phkResult], r13; lpReserved
0x180016928  lea     r9, [rsp+210h+cchName]; lpcchName
0x18001692d  lea     r8, [rbp+110h+Name]; lpName
0x180016931  mov     edx, r14d; dwIndex
0x180016934  mov     rcx, [rsp+210h+hKey]; hKey
0x180016939  call    cs:__imp_RegEnumKeyExW
0x18001693f  mov     r15d, eax
0x180016942  test    eax, eax
0x180016944  jnz     loc_180016A7F
0x18001694a  mov     [rsp+210h+pSid1], r13
0x18001694f  lea     rax, [rsp+210h+pSid1]
0x180016954  mov     [rsp+210h+var_1A0], rax
0x180016959  mov     [rsp+210h+Sid], r13
0x18001695e  mov     [rbp+110h+var_190], 1
0x180016962  lea     rdx, [rsp+210h+Sid]; Sid
0x180016967  lea     rcx, [rbp+110h+Name]; StringSid
0x18001696b  call    cs:__imp_ConvertStringSidToSidW
0x180016971  mov     ebx, eax
0x180016973  lea     rcx, [rsp+210h+var_1A0]
0x180016978  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18001697d  test    ebx, ebx
0x18001697f  jnz     short loc_1800169C3
0x180016981  mov     rax, cs:WPP_GLOBAL_Control
0x180016988  cmp     rax, rdi
0x18001698b  jz      loc_180016A75
0x180016991  test    byte ptr [rax+1Ch], 4
0x180016995  jz      loc_180016A75
0x18001699b  call    cs:__imp_GetLastError
0x1800169a1  lea     edx, [rbx+1Bh]
0x1800169a4  mov     r9d, eax
0x1800169a7  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x1800169ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169b5  mov     rcx, [rcx+10h]
0x1800169b9  call    WPP_SF_d
0x1800169be  jmp     loc_180016A75
0x1800169c3  mov     [rsp+210h+pfEqual], r13d
0x1800169c8  lea     r8, [rsp+210h+pfEqual]; pfEqual
0x1800169cd  mov     rdx, [rsp+210h+pSid2]; pSid2
0x1800169d2  mov     rcx, [rsp+210h+pSid1]; pSid1
0x1800169d7  call    cs:__imp_EqualDomainSid
0x1800169dd  test    eax, eax
0x1800169df  jz      loc_180016A75
0x1800169e5  cmp     [rsp+210h+pfEqual], r13d
0x1800169ea  jz      loc_180016A75
0x1800169f0  mov     [rsp+210h+var_1BC], r13d
0x1800169f5  lea     rdx, [rsp+210h+var_1BC]
0x1800169fa  mov     rcx, [rsp+210h+pSid1]
0x1800169ff  call    cs:__imp_LsaLookupUserAccountType
0x180016a05  test    eax, eax
0x180016a07  js      short loc_180016A75
0x180016a09  cmp     [rsp+210h+var_1BC], 5
0x180016a0e  jnz     short loc_180016A75
0x180016a10  lea     rcx, [rbp+110h+var_188]
0x180016a14  call    ?CreateInstance@?$CComObject@VCConnectedUser@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CConnectedUser>::CreateInstance(ATL::CComObject<CConnectedUser> * *)
0x180016a19  mov     [rsp+210h+var_1D0], eax
0x180016a1d  test    eax, eax
0x180016a1f  js      loc_180016ACD
0x180016a25  mov     rbx, [rbp+110h+var_188]
0x180016a29  mov     rax, [rbx]
0x180016a2c  mov     rcx, rbx
0x180016a2f  mov     rax, [rax+8]
0x180016a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a38  mov     rdx, [rsp+210h+pSid1]; void *
0x180016a3d  mov     rcx, rbx; this
0x180016a40  call    ?InitializeConnectedAADUser@CConnectedUser@@QEAAJPEAX@Z; CConnectedUser::InitializeConnectedAADUser(void *)
0x180016a45  mov     [rsp+210h+var_1D0], eax
0x180016a49  test    eax, eax
0x180016a4b  js      short loc_180016AA0
0x180016a4d  mov     rdx, rbx; struct IUnknown *
0x180016a50  mov     rcx, rsi; this
0x180016a53  call    ?Add@CGenericEnum@@QEAAJPEAUIUnknown@@@Z; CGenericEnum::Add(IUnknown *)
0x180016a58  mov     [rsp+210h+var_1D0], eax
0x180016a5c  mov     rax, [rbx]
0x180016a5f  mov     rcx, rbx
0x180016a62  mov     rax, [rax+10h]
0x180016a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a6b  mov     r9d, [rsp+210h+var_1D0]
0x180016a70  test    r9d, r9d
0x180016a73  js      short loc_180016A87
0x180016a75  lea     rcx, [rsp+210h+pSid1]
0x180016a7a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180016a7f  inc     r14d
0x180016a82  jmp     loc_1800168F2
0x180016a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a8e  cmp     rcx, rdi
0x180016a91  jz      short loc_180016AF8
0x180016a93  test    byte ptr [rcx+1Ch], 4
0x180016a97  jz      short loc_180016AF8
0x180016a99  mov     edx, 1Eh
0x180016a9e  jmp     short loc_180016AE7
0x180016aa0  mov     rax, [rbx]
0x180016aa3  mov     rcx, rbx
0x180016aa6  mov     rax, [rax+10h]
0x180016aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ab6  cmp     rcx, rdi
0x180016ab9  jz      short loc_180016AF8
0x180016abb  test    byte ptr [rcx+1Ch], 4
0x180016abf  jz      short loc_180016AF8
0x180016ac1  mov     edx, 1Dh
0x180016ac6  mov     r9d, [rsp+210h+var_1D0]
0x180016acb  jmp     short loc_180016AE7
0x180016acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ad4  cmp     rcx, rdi
0x180016ad7  jz      short loc_180016AF8
0x180016ad9  test    byte ptr [rcx+1Ch], 4
0x180016add  jz      short loc_180016AF8
0x180016adf  mov     edx, 1Ch
0x180016ae4  mov     r9d, eax
0x180016ae7  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180016aee  mov     rcx, [rcx+10h]
0x180016af2  call    WPP_SF_d
0x180016af7  nop
0x180016af8  lea     rcx, [rsp+210h+pSid1]
0x180016afd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180016b02  jmp     short loc_180016B4E
0x180016b04  mov     rax, [rsi]
0x180016b07  mov     r8, r12
0x180016b0a  lea     rdx, _GUID_00000100_0000_0000_c000_000000000046
0x180016b11  mov     rcx, rsi
0x180016b14  mov     rax, [rax]
0x180016b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b1c  mov     [rsp+210h+var_1D0], eax
0x180016b20  test    eax, eax
0x180016b22  jns     short loc_180016B4E
0x180016b24  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b2b  cmp     rcx, rdi
0x180016b2e  jz      short loc_180016B4E
0x180016b30  test    byte ptr [rcx+1Ch], 4
0x180016b34  jz      short loc_180016B4E
0x180016b36  mov     edx, 1Fh
0x180016b3b  mov     r9d, eax
0x180016b3e  lea     r8, WPP_b72d4e051fd83533ab7d0ff6c3008341_Traceguids
0x180016b45  mov     rcx, [rcx+10h]
0x180016b49  call    WPP_SF_d
0x180016b4e  test    rsi, rsi
0x180016b51  jz      short loc_180016B62
0x180016b53  mov     rax, [rsi]
0x180016b56  mov     rcx, rsi
0x180016b59  mov     rax, [rax+10h]
0x180016b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b62  mov     ecx, [rsp+210h+var_1D0]; int
0x180016b66  call    ?MapErrorCodes@@YAJJ@Z; MapErrorCodes(long)
0x180016b6b  mov     ebx, eax
0x180016b6d  lea     rcx, [rbp+110h+var_180]; this
0x180016b71  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180016b76  nop
0x180016b77  lea     rcx, [rsp+210h+hKey]
0x180016b7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180016b81  nop
0x180016b82  lea     rcx, [rsp+210h+pSid2]
0x180016b87  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180016b8c  mov     eax, ebx
0x180016b8e  mov     rcx, [rbp+110h+var_50]
0x180016b95  xor     rcx, rsp; StackCookie
0x180016b98  call    __security_check_cookie
0x180016b9d  add     rsp, 1D8h
0x180016ba4  pop     r15
0x180016ba6  pop     r14
0x180016ba8  pop     r13
0x180016baa  pop     r12
0x180016bac  pop     rdi
0x180016bad  pop     rsi
0x180016bae  pop     rbx
0x180016baf  pop     rbp
0x180016bb0  retn
```

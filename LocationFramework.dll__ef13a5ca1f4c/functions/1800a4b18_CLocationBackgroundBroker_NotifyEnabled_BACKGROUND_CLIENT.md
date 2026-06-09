# CLocationBackgroundBroker::NotifyEnabled(BACKGROUND_CLIENT &)

- ea: `0x1800a4b18`
- end: `0x1800a4e59`
- name: `?NotifyEnabled@CLocationBackgroundBroker@@AEAAJAEAUBACKGROUND_CLIENT@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(CLocationBackgroundBroker *__hidden this, struct BACKGROUND_CLIENT *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801193c4`
- `0x180119640`

## callees

- `0x180012398`
- `0x18001859c`
- `0x18001ecbc`
- `0x18001efe0`
- `0x1800234ec`
- `0x180028fdc`
- `0x18008f530`
- `0x18009c310`
- `0x18009e038`
- `0x1800a4b18`
- `0x1800a4e60`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x18015e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800a4c89`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a4cfb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a4d22`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a4c89`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a4cfb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a4d22`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800a4be6`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800a4be6`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a4bc7`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800a4bc7`

## string_xrefs

- `0x1800a4c10`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbackgroundbroker.cpp`
- `0x1800a4c72`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbackgroundbroker.cpp`
- `0x1800a4ce6`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbackgroundbroker.cpp`
- `0x1800a4d87`: `onecoreuap\drivers\mobilepc\location\product\core\systemintegration\locationbackgroundbroker.cpp`
- `0x1800a4bfd`: `AppContainerDeriveSidFromMoniker(familyName, &packageSid)`
- `0x1800a4c5f`: `LocationSystemHelper::GenerateApplicationContext(sidUser.Sid(), packageSid.get(), applicationContext.m_str)`
- `0x1800a4c09`: `CLocationBackgroundBroker::NotifyEnabled`
- `0x1800a4c6b`: `CLocationBackgroundBroker::NotifyEnabled`
- `0x1800a4cdf`: `CLocationBackgroundBroker::NotifyEnabled`
- `0x1800a4d80`: `CLocationBackgroundBroker::NotifyEnabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLocationBackgroundBroker::NotifyEnabled(
        CLocationBackgroundBroker *this,
        struct BACKGROUND_CLIENT *a2)
{
  char *v4; // rsi
  const unsigned __int16 *v5; // r8
  LONG v6; // eax
  bool v7; // sf
  int v8; // eax
  unsigned int v9; // ebx
  PSID v10; // rbx
  const unsigned __int16 *v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  OLECHAR *v14; // rbx
  int v15; // eax
  unsigned int v16; // esi
  OLECHAR *v18; // rbx
  __int128 v19; // xmm6
  __int64 v20; // xmm7_8
  wil::details *v21; // [rsp+30h] [rbp-D8h]
  BSTR bstrString; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h]
  PSID Sid; // [rsp+68h] [rbp-A0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v27[56]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+B0h] [rbp-58h]
  WCHAR packageFamilyName[72]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1D0h] [rbp+C8h]

  if ( !*((_QWORD *)this + 17) || !*((_QWORD *)this + 16) )
    return 1;
  v4 = (char *)a2 + 8;
  if ( *((_DWORD *)a2 + 2) == -1 )
  {
    memset_0(v27, 0, 0x78u);
    ATL::CSid::CSid((ATL::CSid *)v27, *(const struct _SID **)(*(_QWORD *)a2 + 32LL), v5);
    Sid = 0;
    packageFamilyNameLength = 65;
    v6 = PackageFamilyNameFromFullName(*(PCWSTR *)(*(_QWORD *)a2 + 24LL), &packageFamilyNameLength, packageFamilyName);
    v7 = v6 < 0;
    if ( v6 > 0 )
      v7 = 1;
    if ( !v7 )
    {
      v8 = AppContainerDeriveSidFromMoniker(packageFamilyName, &Sid);
      v9 = v8;
      if ( v8 < 0 )
      {
        LODWORD(v21) = v8;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbackgroundbroker.cpp",
          "CLocationBackgroundBroker::NotifyEnabled",
          "AppContainerDeriveSidFromMoniker(familyName, &packageSid)",
          v21,
          (int)bstrString);
LABEL_13:
        CAutoSidPtr::Close((CAutoSidPtr *)&Sid);
        ATL::CSid::~CSid((ATL::CSid *)v27);
        return v9;
      }
    }
    bstrString = 0;
    v10 = Sid;
    v11 = ATL::CSid::Sid((ATL::CSid *)v27);
    v12 = LocationSystemHelper::GenerateApplicationContext(v11, v10, &bstrString);
    v9 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v21) = v12;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbackgroundbroker.cpp",
        "CLocationBackgroundBroker::NotifyEnabled",
        "LocationSystemHelper::GenerateApplicationContext(sidUser.Sid(), packageSid.get(), applicationContext.m_str)",
        v21,
        (int)bstrString);
      SysFreeString(bstrString);
      goto LABEL_13;
    }
    v13 = *((_QWORD *)this + 16);
    *(GUID *)v23 = GUID_NULL;
    v14 = bstrString;
    v15 = (*(__int64 (__fastcall **)(__int64, BSTR, _BYTE *, __int64, char *))(*(_QWORD *)v13 + 24LL))(
            v13,
            bstrString,
            v23,
            1,
            v4);
    v16 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v21) = v15;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbackgroundbroker.cpp",
        "CLocationBackgroundBroker::NotifyEnabled",
        "m_geofenceStore->GetApplicationId(applicationContext, ProductId, TRUE , &(client.ApplicationId))",
        v21,
        (int)bstrString);
      SysFreeString(v14);
      v9 = v16;
      goto LABEL_13;
    }
    SysFreeString(v14);
    CAutoSidPtr::Close((CAutoSidPtr *)&Sid);
    ATL::CSid::~CSid((ATL::CSid *)v27);
  }
  v18 = (OLECHAR *)*((_QWORD *)this + 17);
  bstrString = v18;
  if ( !v18 )
  {
    v9 = -2147418113;
    LODWORD(v21) = -2147418113;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\systemintegration\\locationbackgroundbroker.cpp",
      "CLocationBackgroundBroker::NotifyEnabled",
      "pGeofenceEventSubscriptions",
      v21,
      0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&bstrString);
    return v9;
  }
  (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v18 + 8LL))(v18);
  v19 = *(_OWORD *)a2;
  v20 = *((_QWORD *)a2 + 2);
  *(_QWORD *)v23 = v18;
  (*(void (__fastcall **)(OLECHAR *))(*(_QWORD *)v18 + 8LL))(v18);
  *(_OWORD *)&v23[8] = v19;
  v24 = v20;
  v28 = 0;
  v28 = std::_Func_impl_no_alloc__CLocationBackgroundBroker::NotifyEnabled_::_2_::_lambda_1__long_::_Func_impl_no_alloc__CLocationBackgroundBroker::NotifyEnabled_::_2_::_lambda_1__long___CLocationBackgroundBroker::NotifyEnabled_::_2_::_lambda_1__0_(
          v27,
          v23);
  CLocationWorkQueue_Impl<0>::QueueWorkItem((char *)this + 152, v27);
  std::_Func_class<void,enum CLocationActivityDetector::ActivityType,bool>::_Tidy(v27);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&bstrString);
  return 0;
}

```

## disassembly

```asm
0x1800a4b18  mov     rax, rsp
0x1800a4b1b  mov     [rax+18h], rbx
0x1800a4b1f  mov     [rax+20h], rsi
0x1800a4b23  push    rbp
0x1800a4b24  push    rdi
0x1800a4b25  push    r14
0x1800a4b27  lea     rbp, [rax-0C8h]
0x1800a4b2e  sub     rsp, 1B0h
0x1800a4b35  movaps  xmmword ptr [rax-28h], xmm6
0x1800a4b39  movaps  xmmword ptr [rax-38h], xmm7
0x1800a4b3d  mov     rax, cs:__security_cookie
0x1800a4b44  xor     rax, rsp
0x1800a4b47  mov     [rbp+0C0h+var_40], rax
0x1800a4b4e  mov     r14, rdx
0x1800a4b51  mov     rdi, rcx
0x1800a4b54  cmp     qword ptr [rcx+88h], 0
0x1800a4b5c  jz      loc_1800A4E23
0x1800a4b62  cmp     qword ptr [rcx+80h], 0
0x1800a4b6a  jz      loc_1800A4E23
0x1800a4b70  lea     rsi, [rdx+8]
0x1800a4b74  cmp     dword ptr [rsi], 0FFFFFFFFh
0x1800a4b77  jnz     loc_1800A4D3E
0x1800a4b7d  xor     edx, edx; Val
0x1800a4b7f  lea     r8d, [rdx+78h]; Size
0x1800a4b83  lea     rcx, [rsp+1C0h+var_150]; void *
0x1800a4b88  call    memset_0
0x1800a4b8d  mov     rdx, [r14]
0x1800a4b90  mov     rdx, [rdx+20h]; struct _SID *
0x1800a4b94  lea     rcx, [rsp+1C0h+var_150]; this
0x1800a4b99  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x1800a4b9e  nop
0x1800a4b9f  mov     [rsp+1C0h+Sid], 0
0x1800a4ba8  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800a4baf  mov     [rsp+1C0h+packageFamilyNameLength], 41h ; 'A'
0x1800a4bb7  mov     rcx, [r14]
0x1800a4bba  lea     r8, [rbp+0C0h+packageFamilyName]; packageFamilyName
0x1800a4bbe  lea     rdx, [rsp+1C0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800a4bc3  mov     rcx, [rcx+18h]; packageFullName
0x1800a4bc7  call    cs:__imp_PackageFamilyNameFromFullName
0x1800a4bcd  test    eax, eax
0x1800a4bcf  jle     short loc_1800A4BDB
0x1800a4bd1  movzx   eax, ax
0x1800a4bd4  or      eax, 80070000h
0x1800a4bd9  test    eax, eax
0x1800a4bdb  js      short loc_1800A4C26
0x1800a4bdd  lea     rdx, [rsp+1C0h+Sid]
0x1800a4be2  lea     rcx, [rbp+0C0h+packageFamilyName]
0x1800a4be6  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x1800a4bec  mov     ebx, eax
0x1800a4bee  test    eax, eax
0x1800a4bf0  jns     short loc_1800A4C26
0x1800a4bf2  mov     rcx, [rbp+0C8h]; this
0x1800a4bf9  mov     dword ptr [rsp+1C0h+var_198], eax; wil::details *
0x1800a4bfd  lea     rax, aAppcontainerde_0; "AppContainerDeriveSidFromMoniker(family"...
0x1800a4c04  mov     [rsp+1C0h+var_1A0], rax; char *
0x1800a4c09  lea     r9, aClocationbackg_4; "CLocationBackgroundBroker::NotifyEnable"...
0x1800a4c10  lea     r8, aOnecoreuapDriv_28; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a4c17  mov     edx, 1AAh; void *
0x1800a4c1c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a4c21  jmp     loc_1800A4D03
0x1800a4c26  mov     [rsp+1C0h+bstrString], 0; int
0x1800a4c2f  mov     rbx, [rsp+1C0h+Sid]
0x1800a4c34  lea     rcx, [rsp+1C0h+var_150]; this
0x1800a4c39  call    ?Sid@CSid@ATL@@QEBAPEBGXZ; ATL::CSid::Sid(void)
0x1800a4c3e  lea     r8, [rsp+1C0h+bstrString]; unsigned __int16 **
0x1800a4c43  mov     rdx, rbx; Sid
0x1800a4c46  mov     rcx, rax; unsigned __int16 *
0x1800a4c49  call    ?GenerateApplicationContext@LocationSystemHelper@@SAJPEBGQEAXAEAPEAG@Z; LocationSystemHelper::GenerateApplicationContext(ushort const *,void * const,ushort * &)
0x1800a4c4e  mov     ebx, eax
0x1800a4c50  test    eax, eax
0x1800a4c52  jns     short loc_1800A4C91
0x1800a4c54  mov     rcx, [rbp+0C8h]; this
0x1800a4c5b  mov     dword ptr [rsp+1C0h+var_198], eax; wil::details *
0x1800a4c5f  lea     rax, aLocationsystem; "LocationSystemHelper::GenerateApplicati"...
0x1800a4c66  mov     [rsp+1C0h+var_1A0], rax; char *
0x1800a4c6b  lea     r9, aClocationbackg_4; "CLocationBackgroundBroker::NotifyEnable"...
0x1800a4c72  lea     r8, aOnecoreuapDriv_28; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a4c79  mov     edx, 1B0h; void *
0x1800a4c7e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a4c83  nop
0x1800a4c84  mov     rcx, [rsp+1C0h+bstrString]; bstrString
0x1800a4c89  call    cs:__imp_SysFreeString
0x1800a4c8f  jmp     short loc_1800A4D03
0x1800a4c91  mov     rcx, [rdi+80h]
0x1800a4c98  movdqa  [rsp+1C0h+var_188+8], xmm6
0x1800a4c9e  mov     rax, [rcx]
0x1800a4ca1  mov     [rsp+1C0h+var_1A0], rsi
0x1800a4ca6  mov     r9d, 1
0x1800a4cac  lea     r8, [rsp+1C0h+var_188+8]
0x1800a4cb1  mov     rbx, [rsp+1C0h+bstrString]
0x1800a4cb6  mov     rdx, rbx
0x1800a4cb9  mov     rax, [rax+18h]
0x1800a4cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4cc2  mov     esi, eax
0x1800a4cc4  test    eax, eax
0x1800a4cc6  jns     short loc_1800A4D1F
0x1800a4cc8  mov     rcx, [rbp+0C8h]; this
0x1800a4ccf  mov     dword ptr [rsp+1C0h+var_198], eax; wil::details *
0x1800a4cd3  lea     rax, aMGeofencestore; "m_geofenceStore->GetApplicationId(appli"...
0x1800a4cda  mov     [rsp+1C0h+var_1A0], rax; char *
0x1800a4cdf  lea     r9, aClocationbackg_4; "CLocationBackgroundBroker::NotifyEnable"...
0x1800a4ce6  lea     r8, aOnecoreuapDriv_28; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a4ced  mov     edx, 1B5h; void *
0x1800a4cf2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a4cf7  nop
0x1800a4cf8  mov     rcx, rbx; bstrString
0x1800a4cfb  call    cs:__imp_SysFreeString
0x1800a4d01  mov     ebx, esi
0x1800a4d03  lea     rcx, [rsp+1C0h+Sid]; this
0x1800a4d08  call    ?Close@CAutoSidPtr@@QEAAXXZ; CAutoSidPtr::Close(void)
0x1800a4d0d  nop
0x1800a4d0e  lea     rcx, [rsp+1C0h+var_150]; this
0x1800a4d13  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800a4d18  mov     eax, ebx
0x1800a4d1a  jmp     loc_1800A4E28
0x1800a4d1f  mov     rcx, rbx; bstrString
0x1800a4d22  call    cs:__imp_SysFreeString
0x1800a4d28  nop
0x1800a4d29  lea     rcx, [rsp+1C0h+Sid]; this
0x1800a4d2e  call    ?Close@CAutoSidPtr@@QEAAXXZ; CAutoSidPtr::Close(void)
0x1800a4d33  nop
0x1800a4d34  lea     rcx, [rsp+1C0h+var_150]; this
0x1800a4d39  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800a4d3e  mov     rbx, [rdi+88h]
0x1800a4d45  mov     [rsp+1C0h+bstrString], rbx; int
0x1800a4d4a  test    rbx, rbx
0x1800a4d4d  jz      short loc_1800A4D5F
0x1800a4d4f  mov     rax, [rbx]
0x1800a4d52  mov     rcx, rbx
0x1800a4d55  mov     rax, [rax+8]
0x1800a4d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4d5e  nop
0x1800a4d5f  test    rbx, rbx
0x1800a4d62  jnz     short loc_1800A4DA8
0x1800a4d64  mov     rcx, [rbp+0C8h]; this
0x1800a4d6b  mov     ebx, 8000FFFFh
0x1800a4d70  mov     dword ptr [rsp+1C0h+var_198], ebx; wil::details *
0x1800a4d74  lea     rdx, aPgeofenceevent; "pGeofenceEventSubscriptions"
0x1800a4d7b  mov     [rsp+1C0h+var_1A0], rdx; char *
0x1800a4d80  lea     r9, aClocationbackg_4; "CLocationBackgroundBroker::NotifyEnable"...
0x1800a4d87  lea     r8, aOnecoreuapDriv_28; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800a4d8e  mov     edx, 1BAh; void *
0x1800a4d93  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800a4d98  nop
0x1800a4d99  lea     rcx, [rsp+1C0h+bstrString]
0x1800a4d9e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a4da3  jmp     loc_1800A4D18
0x1800a4da8  movups  xmm6, xmmword ptr [r14]
0x1800a4dac  movsd   xmm7, qword ptr [r14+10h]
0x1800a4db2  mov     qword ptr [rsp+1C0h+var_188+8], rbx
0x1800a4db7  mov     rax, [rbx]
0x1800a4dba  mov     rcx, rbx
0x1800a4dbd  mov     rax, [rax+8]
0x1800a4dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4dc6  nop
0x1800a4dc7  movups  [rsp+1C0h+var_178], xmm6
0x1800a4dcc  movsd   [rsp+1C0h+var_168], xmm7
0x1800a4dd2  mov     [rbp+0C0h+var_118], 0
0x1800a4dda  lea     rdx, [rsp+1C0h+var_188+8]
0x1800a4ddf  lea     rcx, [rsp+1C0h+var_150]
0x1800a4de4  call    std___Func_impl_no_alloc__CLocationBackgroundBroker__NotifyEnabled____2____lambda_1__long____Func_impl_no_alloc__CLocationBackgroundBroker__NotifyEnabled____2____lambda_1__long___CLocationBackgroundBroker__NotifyEnabled____2____lambda_1__0_
0x1800a4de9  mov     [rbp+0C0h+var_118], rax
0x1800a4ded  lea     rcx, [rdi+98h]
0x1800a4df4  lea     rdx, [rsp+1C0h+var_150]
0x1800a4df9  call    ?QueueWorkItem@?$CLocationWorkQueue_Impl@$0A@@@QEAAJAEBV?$function@$$A6AJXZ@std@@@Z; CLocationWorkQueue_Impl<0>::QueueWorkItem(std::function<long (void)> const &)
0x1800a4dfe  nop
0x1800a4dff  lea     rcx, [rsp+1C0h+var_150]
0x1800a4e04  call    ?_Tidy@?$_Func_class@XW4ActivityType@CLocationActivityDetector@@_N@std@@IEAAXXZ; std::_Func_class<void,CLocationActivityDetector::ActivityType,bool>::_Tidy(void)
0x1800a4e09  nop
0x1800a4e0a  lea     rcx, [rsp+1C0h+var_188+8]
0x1800a4e0f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a4e14  nop
0x1800a4e15  lea     rcx, [rsp+1C0h+bstrString]
0x1800a4e1a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a4e1f  xor     eax, eax
0x1800a4e21  jmp     short loc_1800A4E28
0x1800a4e23  mov     eax, 1
0x1800a4e28  mov     rcx, [rbp+0C0h+var_40]
0x1800a4e2f  xor     rcx, rsp; StackCookie
0x1800a4e32  call    __security_check_cookie
0x1800a4e37  lea     r11, [rsp+1C0h+var_10]
0x1800a4e3f  mov     rbx, [r11+30h]
0x1800a4e43  mov     rsi, [r11+38h]
0x1800a4e47  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a4e4c  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a4e51  mov     rsp, r11
0x1800a4e54  pop     r14
0x1800a4e56  pop     rdi
0x1800a4e57  pop     rbp
0x1800a4e58  retn
```

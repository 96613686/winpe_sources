# SystemSettings::WorkAccess::CEnrollmentHelper::GetStringByNodePath(void *)

- ea: `0x180047ef0`
- end: `0x18004852d`
- name: `?GetStringByNodePath@CEnrollmentHelper@WorkAccess@SystemSettings@@SAKPEAX@Z`
- size: `1597`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x180009eac`
- `0x180027a58`
- `0x1800290b8`
- `0x18004592c`
- `0x180047ef0`
- `0x18004cef8`
- `0x18004d2c0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800480dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800480dd`
- `OLEAUT32!__imp_SysAllocString` at `0x180048064`
- `OLEAUT32!__imp_SysAllocString` at `0x180048083`
- `OLEAUT32!__imp_SysAllocString` at `0x1800480ec`
- `OLEAUT32!__imp_SysAllocString` at `0x180048064`
- `OLEAUT32!__imp_SysAllocString` at `0x180048083`
- `OLEAUT32!__imp_SysAllocString` at `0x1800480ec`
- `OLEAUT32!__imp_VariantInit` at `0x180048385`
- `OLEAUT32!__imp_VariantInit` at `0x180048385`
- `OLEAUT32!__imp_VariantClear` at `0x1800481a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800481b9`
- `OLEAUT32!__imp_VariantClear` at `0x180048229`
- `OLEAUT32!__imp_VariantClear` at `0x18004823a`
- `OLEAUT32!__imp_VariantClear` at `0x180048442`
- `OLEAUT32!__imp_VariantClear` at `0x180048453`
- `OLEAUT32!__imp_VariantClear` at `0x180048480`
- `OLEAUT32!__imp_VariantClear` at `0x180048491`
- `OLEAUT32!__imp_VariantClear` at `0x1800481a8`
- `OLEAUT32!__imp_VariantClear` at `0x1800481b9`
- `OLEAUT32!__imp_VariantClear` at `0x180048229`
- `OLEAUT32!__imp_VariantClear` at `0x18004823a`
- `OLEAUT32!__imp_VariantClear` at `0x180048442`
- `OLEAUT32!__imp_VariantClear` at `0x180048453`
- `OLEAUT32!__imp_VariantClear` at `0x180048480`
- `OLEAUT32!__imp_VariantClear` at `0x180048491`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047fed`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180047fed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180047f19`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180047f19`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048503`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180048503`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004802b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004802b`

## string_xrefs

- `0x18004807c`: `OMADM::TargetedUserSID`
- `0x180047f37`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048042`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048191`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`
- `0x180048217`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentHelper::GetStringByNodePath(PVOID Parameter)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  HRESULT v3; // eax
  __int64 v4; // rdx
  BSTR v5; // rax
  BSTR v6; // rax
  __int64 *v7; // rdi
  __int64 *v8; // rbx
  const OLECHAR *StringRawBuffer; // rax
  unsigned __int16 *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, const wchar_t *, __int64 *); // rbx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, __int64 *, int *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  LPVOID v27; // rdi
  __int64 (__fastcall *v28)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v31; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  char v40; // [rsp+99h] [rbp-67h]
  int v41; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 *v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  PCWSTR pszUrl; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v46; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v47; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG *p_pvarg; // [rsp+F8h] [rbp-8h]
  VARIANTARG *v49; // [rsp+100h] [rbp+0h]
  char v50; // [rsp+108h] [rbp+8h]
  GUID pclsid; // [rsp+110h] [rbp+10h] BYREF
  OLECHAR sz[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v53; // [rsp+130h] [rbp+30h]
  __int128 v54; // [rsp+140h] [rbp+40h]
  _OWORD v55[2]; // [rsp+150h] [rbp+50h]
  unsigned __int16 v56[264]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+2B8h]

  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v40 = 1;
    memset(&v47, 0, sizeof(v47));
    v31 = 0;
    v39 = 0;
    v38 = 0;
    v37 = 0;
    v36 = 0;
    v35 = 0;
    pszUrl = 0;
    v44 = 0;
    v43 = 0;
    v42 = 0;
    memset(&pvarg, 0, sizeof(pvarg));
    memset(&v33, 0, sizeof(v33));
    v34 = 0;
    v41 = 0;
    *(_OWORD *)sz = *(_OWORD *)L"{66D0DB14-5638-475f-A386-629522D8C461}";
    v53 = *(_OWORD *)L"4-5638-475f-A386-629522D8C461}";
    v54 = *(_OWORD *)L"75f-A386-629522D8C461}";
    v55[0] = *(_OWORD *)L"-629522D8C461}";
    *(_OWORD *)((char *)v55 + 14) = *(_OWORD *)L"D8C461}";
    pclsid = 0;
    v3 = CLSIDFromString(sz, &pclsid);
    v2 = v3;
    if ( v3 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v3 = CoCreateInstance(&pclsid, 0, 1u, &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0, &v31);
      v2 = v3;
      if ( v3 >= 0 )
      {
        v5 = SysAllocString(L"OMADM::AccountID");
        _bstr_t::operator=(&v43, v5);
        v6 = SysAllocString(L"OMADM::TargetedUserSID");
        _bstr_t::operator=(&v42, v6);
        v7 = v43;
        if ( !v43
          || !*v43
          || (v8 = v42) == 0
          || !*v42
          || !SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
          || (StringRawBuffer = WindowsGetStringRawBuffer(
                                  *(HSTRING *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                             + 8),
                                  0),
              pvarg.llVal = (LONGLONG)SysAllocString(StringRawBuffer),
              v10 = _bstr_t::copy((_bstr_t *)(SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
                                            + 40)),
              v33.llVal = (LONGLONG)v10,
              !pvarg.llVal)
          || !v10 )
        {
          v2 = 1;
          goto LABEL_53;
        }
        p_pvarg = &pvarg;
        v49 = &v33;
        v50 = 1;
        pvarg.vt = 8;
        v33.vt = 8;
        v11 = *(_QWORD *)v31;
        if ( v7 )
          v12 = *v7;
        else
          v12 = 0;
        v46 = pvarg;
        v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(v11 + 104))(v31, v12, &v46);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v15 = *(_QWORD *)v31;
          if ( v8 )
            v16 = *v8;
          else
            v16 = 0;
          v46 = v33;
          v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(v15 + 104))(v31, v16, &v46);
          v2 = v17;
          if ( v17 >= 0 )
          {
            v19 = v31;
            v20 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v31 + 80LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            v17 = v20(v19, L"./Vendor/MSFT/DMClient/Provider", &v38);
            v2 = v17;
            if ( v17 >= 0 )
            {
              v21 = v38;
              v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 192LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
              v17 = v22(v21, &v36);
              v2 = v17;
              if ( v17 >= 0 )
              {
                v23 = v36;
                v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v36 + 24LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
                v17 = v24(v23, 1, &v37, &v41);
                v2 = v17;
                if ( v17 >= 0 )
                {
                  v25 = v37;
                  v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 120LL);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
                  v17 = v26(v25, &v35);
                  v2 = v17;
                  if ( v17 >= 0 )
                  {
                    v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 136LL))(v35, &v34);
                    v2 = v17;
                    if ( v17 >= 0 )
                    {
                      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR *))(*(_QWORD *)v35 + 88LL))(
                              v35,
                              (unsigned int)(v34 - 1),
                              &pszUrl);
                      v2 = v17;
                      if ( v17 >= 0 )
                      {
                        VariantInit(&v47);
                        v17 = SystemSettings::WorkAccess::UrlEscapeWrapper(pszUrl);
                        v2 = v17;
                        if ( v17 >= 0 )
                        {
                          if ( SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty )
                            v17 = StringCchPrintfW(
                                    v56,
                                    0x104u,
                                    (const unsigned __int16 *)*SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty,
                                    v44);
                          else
                            v17 = StringCchPrintfW(v56, 0x104u, 0, v44);
                          v2 = v17;
                          if ( v17 >= 0 )
                          {
                            v27 = v31;
                            v28 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)v31 + 80LL);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                            v17 = v28(v27, v56, &v39);
                            v2 = v17;
                            if ( v17 >= 0 )
                            {
                              v17 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v39 + 104LL))(
                                      v39,
                                      &v47);
                              v2 = v17;
                              if ( v17 >= 0 )
                              {
                                SystemSettings::WorkAccess::CEnrollmentHelper::_value = v47.bstrVal;
                                VariantClear(&pvarg);
                                VariantClear(&v33);
                                v2 = 0;
                                goto LABEL_53;
                              }
                              if ( v17 == -2046820350 )
                              {
                                VariantClear(&pvarg);
                                VariantClear(&v33);
                                v2 = -2046820350;
                                goto LABEL_53;
                              }
                              v18 = 430;
                            }
                            else
                            {
                              v18 = 428;
                            }
                          }
                          else
                          {
                            v18 = 426;
                          }
                        }
                        else
                        {
                          v18 = 424;
                        }
                      }
                      else
                      {
                        v18 = 420;
                      }
                    }
                    else
                    {
                      v18 = 418;
                    }
                  }
                  else
                  {
                    v18 = 416;
                  }
                }
                else
                {
                  v18 = 414;
                }
              }
              else
              {
                v18 = 412;
              }
            }
            else
            {
              v18 = 410;
            }
          }
          else
          {
            v18 = 408;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v17,
            ppv);
          VariantClear(&pvarg);
          VariantClear(&v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x196,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
            (const char *)(unsigned int)v13,
            ppv);
          VariantClear(&pvarg);
          VariantClear(&v33);
          v2 = v14;
        }
LABEL_53:
        _bstr_t::_Free((_bstr_t *)&v42);
        _bstr_t::_Free((_bstr_t *)&v43);
        CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v44);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        CoUninitialize();
        return v2;
      }
      v4 = 364;
    }
    else
    {
      v4 = 362;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    goto LABEL_53;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14D,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmenthelper.cpp",
    (const char *)(unsigned int)v1,
    ppv);
  return v2;
}

```

## disassembly

```asm
0x180047ef0  push    rbp
0x180047ef2  push    rbx
0x180047ef3  push    rsi
0x180047ef4  push    rdi
0x180047ef5  lea     rbp, [rsp-298h]
0x180047efd  sub     rsp, 398h
0x180047f04  mov     rax, cs:__security_cookie
0x180047f0b  xor     rax, rsp
0x180047f0e  mov     [rbp+2B0h+var_30], rax
0x180047f15  xor     edx, edx; dwCoInit
0x180047f17  xor     ecx, ecx; pvReserved
0x180047f19  call    cs:__imp_CoInitializeEx
0x180047f20  nop     dword ptr [rax+rax+00h]
0x180047f25  mov     ebx, eax
0x180047f27  xor     esi, esi
0x180047f29  test    eax, eax
0x180047f2b  jns     short loc_180047F4D
0x180047f2d  mov     rcx, [rbp+2B8h]; this
0x180047f34  mov     r9d, eax; char *
0x180047f37  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180047f3e  mov     edx, 14Dh; void *
0x180047f43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047f48  jmp     loc_18004850F
0x180047f4d  mov     [rbp+2B0h+var_317], 1
0x180047f51  xorps   xmm0, xmm0
0x180047f54  xor     eax, eax
0x180047f56  movups  xmmword ptr [rbp+2B0h+var_2D0], xmm0
0x180047f5a  mov     qword ptr [rbp+2B0h+var_2D0+10h], rax
0x180047f5e  mov     [rsp+3B0h+var_380], rsi
0x180047f63  mov     [rbp+2B0h+var_320], rsi
0x180047f67  mov     [rbp+2B0h+var_328], rsi
0x180047f6b  mov     [rbp+2B0h+var_330], rsi
0x180047f6f  mov     [rsp+3B0h+var_338], rsi
0x180047f74  mov     [rsp+3B0h+var_340], rsi
0x180047f79  mov     [rbp+2B0h+pszUrl], rsi
0x180047f7d  mov     [rbp+2B0h+var_300], rsi
0x180047f81  mov     [rbp+2B0h+var_308], rsi
0x180047f85  mov     [rbp+2B0h+var_310], rsi
0x180047f89  movups  xmmword ptr [rsp+3B0h+pvarg], xmm0
0x180047f8e  mov     qword ptr [rsp+3B0h+pvarg+10h], rax
0x180047f93  xorps   xmm1, xmm1
0x180047f96  movups  xmmword ptr [rsp+3B0h+var_360], xmm1
0x180047f9b  mov     qword ptr [rsp+3B0h+var_360+10h], rax
0x180047fa0  mov     [rsp+3B0h+var_348], esi
0x180047fa4  mov     [rbp+2B0h+var_314], esi
0x180047fa7  movaps  xmm0, xmmword ptr cs:a66d0db14563847; "{66D0DB14-5638-475f-A386-629522D8C461}"
0x180047fae  movaps  xmmword ptr [rbp+2B0h+sz], xmm0
0x180047fb2  movaps  xmm1, xmmword ptr cs:a66d0db14563847+10h; "4-5638-475f-A386-629522D8C461}"
0x180047fb9  movaps  [rbp+2B0h+var_280], xmm1
0x180047fbd  movaps  xmm0, xmmword ptr cs:a66d0db14563847+20h; "75f-A386-629522D8C461}"
0x180047fc4  movaps  [rbp+2B0h+var_270], xmm0
0x180047fc8  movaps  xmm1, xmmword ptr cs:a66d0db14563847+30h; "-629522D8C461}"
0x180047fcf  movaps  xmmword ptr [rbp+2B0h+var_260], xmm1
0x180047fd3  movups  xmm0, xmmword ptr cs:a66d0db14563847+3Eh; "D8C461}"
0x180047fda  movups  xmmword ptr [rbp+2B0h+var_260+0Eh], xmm0
0x180047fde  xorps   xmm0, xmm0
0x180047fe1  movups  xmmword ptr [rbp+2B0h+pclsid.Data1], xmm0
0x180047fe5  lea     rdx, [rbp+2B0h+pclsid]; pclsid
0x180047fe9  lea     rcx, [rbp+2B0h+sz]; lpsz
0x180047fed  call    cs:__imp_CLSIDFromString
0x180047ff4  nop     dword ptr [rax+rax+00h]
0x180047ff9  mov     ebx, eax
0x180047ffb  test    eax, eax
0x180047ffd  jns     short loc_180048006
0x180047fff  mov     edx, 16Ah
0x180048004  jmp     short loc_180048042
0x180048006  lea     rcx, [rsp+3B0h+var_380]
0x18004800b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048010  lea     rax, [rsp+3B0h+var_380]
0x180048015  mov     qword ptr [rsp+3B0h+ppv], rax; int
0x18004801a  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180048021  xor     edx, edx; pUnkOuter
0x180048023  lea     r8d, [rdx+1]; dwClsContext
0x180048027  lea     rcx, [rbp+2B0h+pclsid]; rclsid
0x18004802b  call    cs:__imp_CoCreateInstance
0x180048032  nop     dword ptr [rax+rax+00h]
0x180048037  mov     ebx, eax
0x180048039  test    eax, eax
0x18004803b  jns     short loc_18004805D
0x18004803d  mov     edx, 16Ch; void *
0x180048042  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048049  mov     r9d, eax; char *
0x18004804c  mov     rcx, [rbp+2B8h]; this
0x180048053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048058  jmp     loc_1800484A6
0x18004805d  lea     rcx, aOmadmAccountid; "OMADM::AccountID"
0x180048064  call    cs:__imp_SysAllocString
0x18004806b  nop     dword ptr [rax+rax+00h]
0x180048070  mov     rdx, rax
0x180048073  lea     rcx, [rbp+2B0h+var_308]
0x180048077  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18004807c  lea     rcx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180048083  call    cs:__imp_SysAllocString
0x18004808a  nop     dword ptr [rax+rax+00h]
0x18004808f  mov     rdx, rax
0x180048092  lea     rcx, [rbp+2B0h+var_310]
0x180048096  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18004809b  mov     rdi, [rbp+2B0h+var_308]
0x18004809f  test    rdi, rdi
0x1800480a2  jz      loc_1800484A1
0x1800480a8  cmp     [rdi], rsi
0x1800480ab  jz      loc_1800484A1
0x1800480b1  mov     rbx, [rbp+2B0h+var_310]
0x1800480b5  test    rbx, rbx
0x1800480b8  jz      loc_1800484A1
0x1800480be  cmp     [rbx], rsi
0x1800480c1  jz      loc_1800484A1
0x1800480c7  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x1800480ce  test    rcx, rcx
0x1800480d1  jz      loc_1800484A1
0x1800480d7  xor     edx, edx; length
0x1800480d9  mov     rcx, [rcx+8]; string
0x1800480dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800480e4  nop     dword ptr [rax+rax+00h]
0x1800480e9  mov     rcx, rax; psz
0x1800480ec  call    cs:__imp_SysAllocString
0x1800480f3  nop     dword ptr [rax+rax+00h]
0x1800480f8  mov     qword ptr [rsp+3B0h+pvarg+8], rax
0x1800480fd  mov     rcx, cs:?spAccountEnthusiastSingleton@CEnrollmentHelper@WorkAccess@SystemSettings@@2V?$shared_ptr@VCAccountEnthusiastData@WorkAccess@SystemSettings@@@std@@A; std::shared_ptr<SystemSettings::WorkAccess::CAccountEnthusiastData> SystemSettings::WorkAccess::CEnrollmentHelper::spAccountEnthusiastSingleton
0x180048104  add     rcx, 28h ; '('; this
0x180048108  call    ?copy@_bstr_t@@QEBAPEAGXZ; _bstr_t::copy(void)
0x18004810d  mov     qword ptr [rsp+3B0h+var_360+8], rax
0x180048112  cmp     qword ptr [rsp+3B0h+pvarg+8], rsi
0x180048117  jz      loc_1800484A1
0x18004811d  test    rax, rax
0x180048120  jz      loc_1800484A1
0x180048126  lea     rax, [rsp+3B0h+pvarg]
0x18004812b  mov     [rbp+2B0h+var_2B8], rax
0x18004812f  lea     rax, [rsp+3B0h+var_360]
0x180048134  mov     [rbp+2B0h+var_2B0], rax
0x180048138  mov     [rbp+2B0h+var_2A8], 1
0x18004813c  mov     eax, 8
0x180048141  mov     word ptr [rsp+3B0h+pvarg], ax
0x180048146  mov     word ptr [rsp+3B0h+var_360], ax
0x18004814b  mov     rcx, [rsp+3B0h+var_380]
0x180048150  mov     rax, [rcx]
0x180048153  test    rdi, rdi
0x180048156  jz      short loc_18004815D
0x180048158  mov     rdx, [rdi]
0x18004815b  jmp     short loc_180048160
0x18004815d  mov     rdx, rsi
0x180048160  movups  xmm0, xmmword ptr [rsp+3B0h+pvarg]
0x180048165  movaps  [rbp+2B0h+var_2F0], xmm0
0x180048169  movsd   xmm1, qword ptr [rsp+3B0h+pvarg+10h]
0x18004816f  movsd   [rbp+2B0h+var_2E0], xmm1
0x180048174  lea     r8, [rbp+2B0h+var_2F0]
0x180048178  mov     rax, [rax+68h]
0x18004817c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048181  mov     edi, eax
0x180048183  test    eax, eax
0x180048185  jns     short loc_1800481CC
0x180048187  mov     rcx, [rbp+2B8h]; this
0x18004818e  mov     r9d, eax; char *
0x180048191  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x180048198  mov     edx, 196h; void *
0x18004819d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800481a2  nop
0x1800481a3  lea     rcx, [rsp+3B0h+pvarg]; pvarg
0x1800481a8  call    cs:__imp_VariantClear
0x1800481af  nop     dword ptr [rax+rax+00h]
0x1800481b4  lea     rcx, [rsp+3B0h+var_360]; pvarg
0x1800481b9  call    cs:__imp_VariantClear
0x1800481c0  nop     dword ptr [rax+rax+00h]
0x1800481c5  mov     ebx, edi
0x1800481c7  jmp     loc_1800484A6
0x1800481cc  mov     rcx, [rsp+3B0h+var_380]
0x1800481d1  mov     rax, [rcx]
0x1800481d4  test    rbx, rbx
0x1800481d7  jz      short loc_1800481DE
0x1800481d9  mov     rdx, [rbx]
0x1800481dc  jmp     short loc_1800481E1
0x1800481de  mov     rdx, rsi
0x1800481e1  movups  xmm0, xmmword ptr [rsp+3B0h+var_360]
0x1800481e6  movaps  [rbp+2B0h+var_2F0], xmm0
0x1800481ea  movsd   xmm1, qword ptr [rsp+3B0h+var_360+10h]
0x1800481f0  movsd   [rbp+2B0h+var_2E0], xmm1
0x1800481f5  lea     r8, [rbp+2B0h+var_2F0]
0x1800481f9  mov     rax, [rax+68h]
0x1800481fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048202  mov     ebx, eax
0x180048204  test    eax, eax
0x180048206  jns     short loc_18004824B
0x180048208  mov     edx, 198h; void *
0x18004820d  mov     rcx, [rbp+2B8h]; this
0x180048214  mov     r9d, eax; char *
0x180048217  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\w"...
0x18004821e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048223  nop
0x180048224  lea     rcx, [rsp+3B0h+pvarg]; pvarg
0x180048229  call    cs:__imp_VariantClear
0x180048230  nop     dword ptr [rax+rax+00h]
0x180048235  lea     rcx, [rsp+3B0h+var_360]; pvarg
0x18004823a  call    cs:__imp_VariantClear
0x180048241  nop     dword ptr [rax+rax+00h]
0x180048246  jmp     loc_1800484A6
0x18004824b  mov     rdi, [rsp+3B0h+var_380]
0x180048250  mov     rax, [rdi]
0x180048253  mov     rbx, [rax+50h]
0x180048257  lea     rcx, [rbp+2B0h+var_328]
0x18004825b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180048260  lea     r8, [rbp+2B0h+var_328]
0x180048264  lea     rdx, aVendorMsftDmcl_2; "./Vendor/MSFT/DMClient/Provider"
0x18004826b  mov     rcx, rdi
0x18004826e  mov     rax, rbx
0x180048271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048276  mov     ebx, eax
0x180048278  test    eax, eax
0x18004827a  jns     short loc_180048283
0x18004827c  mov     edx, 19Ah
0x180048281  jmp     short loc_18004820D
0x180048283  mov     rdi, [rbp+2B0h+var_328]
0x180048287  mov     rax, [rdi]
0x18004828a  mov     rbx, [rax+0C0h]
0x180048291  lea     rcx, [rsp+3B0h+var_338]
0x180048296  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004829b  lea     rdx, [rsp+3B0h+var_338]
0x1800482a0  mov     rcx, rdi
0x1800482a3  mov     rax, rbx
0x1800482a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482ab  mov     ebx, eax
0x1800482ad  test    eax, eax
0x1800482af  jns     short loc_1800482BB
0x1800482b1  mov     edx, 19Ch
0x1800482b6  jmp     loc_18004820D
0x1800482bb  mov     rdi, [rsp+3B0h+var_338]
0x1800482c0  mov     rax, [rdi]
0x1800482c3  mov     rbx, [rax+18h]
0x1800482c7  lea     rcx, [rbp+2B0h+var_330]
0x1800482cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800482d0  lea     r9, [rbp+2B0h+var_314]
0x1800482d4  lea     r8, [rbp+2B0h+var_330]
0x1800482d8  mov     edx, 1
0x1800482dd  mov     rcx, rdi
0x1800482e0  mov     rax, rbx
0x1800482e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482e8  mov     ebx, eax
0x1800482ea  test    eax, eax
0x1800482ec  jns     short loc_1800482F8
0x1800482ee  mov     edx, 19Eh
0x1800482f3  jmp     loc_18004820D
0x1800482f8  mov     rdi, [rbp+2B0h+var_330]
0x1800482fc  mov     rax, [rdi]
0x1800482ff  mov     rbx, [rax+78h]
0x180048303  lea     rcx, [rsp+3B0h+var_340]
0x180048308  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004830d  lea     rdx, [rsp+3B0h+var_340]
0x180048312  mov     rcx, rdi
0x180048315  mov     rax, rbx
0x180048318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004831d  mov     ebx, eax
0x18004831f  test    eax, eax
0x180048321  jns     short loc_18004832D
0x180048323  mov     edx, 1A0h
0x180048328  jmp     loc_18004820D
0x18004832d  mov     rcx, [rsp+3B0h+var_340]
0x180048332  mov     rax, [rcx]
0x180048335  lea     rdx, [rsp+3B0h+var_348]
0x18004833a  mov     rax, [rax+88h]
0x180048341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048346  mov     ebx, eax
0x180048348  test    eax, eax
0x18004834a  jns     short loc_180048356
0x18004834c  mov     edx, 1A2h
0x180048351  jmp     loc_18004820D
0x180048356  mov     rcx, [rsp+3B0h+var_340]
0x18004835b  mov     rax, [rcx]
0x18004835e  mov     edx, [rsp+3B0h+var_348]
0x180048362  dec     edx
0x180048364  lea     r8, [rbp+2B0h+pszUrl]
0x180048368  mov     rax, [rax+58h]
0x18004836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048371  mov     ebx, eax
0x180048373  test    eax, eax
0x180048375  jns     short loc_180048381
0x180048377  mov     edx, 1A4h
0x18004837c  jmp     loc_18004820D
0x180048381  lea     rcx, [rbp+2B0h+var_2D0]; pvarg
0x180048385  call    cs:__imp_VariantInit
0x18004838c  nop     dword ptr [rax+rax+00h]
0x180048391  lea     rdx, [rbp+2B0h+var_300]
0x180048395  mov     rcx, [rbp+2B0h+pszUrl]; pszUrl
0x180048399  call    SystemSettings__WorkAccess__UrlEscapeWrapper
0x18004839e  mov     ebx, eax
0x1800483a0  test    eax, eax
0x1800483a2  jns     short loc_1800483AE
0x1800483a4  mov     edx, 1A8h
0x1800483a9  jmp     loc_18004820D
0x1800483ae  mov     rax, cs:?_stringProperty@CEnrollmentHelper@WorkAccess@SystemSettings@@2V_bstr_t@@A; _bstr_t SystemSettings::WorkAccess::CEnrollmentHelper::_stringProperty
0x1800483b5  test    rax, rax
0x1800483b8  jz      short loc_1800483BF
0x1800483ba  mov     r8, [rax]
0x1800483bd  jmp     short loc_1800483C2
0x1800483bf  mov     r8, rsi; unsigned __int16 *
0x1800483c2  mov     r9, [rbp+2B0h+var_300]
0x1800483c6  mov     edx, 104h; unsigned __int64
0x1800483cb  lea     rcx, [rbp+2B0h+var_240]; unsigned __int16 *
0x1800483cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800483d4  mov     ebx, eax
0x1800483d6  test    eax, eax
0x1800483d8  jns     short loc_1800483E4
  ... truncated ...
```

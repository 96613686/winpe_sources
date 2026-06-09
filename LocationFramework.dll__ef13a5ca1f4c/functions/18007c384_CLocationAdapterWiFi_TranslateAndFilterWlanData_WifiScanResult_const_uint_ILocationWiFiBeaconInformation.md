# CLocationAdapterWiFi::TranslateAndFilterWlanData(WifiScanResult const &,uint,ILocationWiFiBeaconInformation * *)

- ea: `0x18007c384`
- end: `0x18007ca1c`
- name: `?TranslateAndFilterWlanData@CLocationAdapterWiFi@@AEAAJAEBUWifiScanResult@@IPEAPEAUILocationWiFiBeaconInformation@@@Z`
- size: `1688`
- prototype: `__int64 __fastcall(CLocationAdapterWiFi *__hidden this, const struct WifiScanResult *, unsigned int, struct ILocationWiFiBeaconInformation **)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062150`
- `0x18007b7f8`

## callees

- `0x180007e70`
- `0x1800081d4`
- `0x180012398`
- `0x18001e1e0`
- `0x18001e3a0`
- `0x18001e3e0`
- `0x18003e5ec`
- `0x18004c784`
- `0x180052594`
- `0x18006807c`
- `0x18007c384`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800f2970`
- `0x180127fac`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007c4ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007c4ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c449`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c9ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c9ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007c42f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007c42f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CLocationAdapterWiFi::TranslateAndFilterWlanData(
        CLocationAdapterWiFi *this,
        const struct WifiScanResult *a2,
        unsigned int a3,
        struct ILocationWiFiBeaconInformation **a4)
{
  __int64 v5; // rsi
  int v7; // edi
  HRESULT v8; // ebx
  char *v9; // rax
  char *v10; // r15
  __int64 v11; // rcx
  unsigned int v12; // r13d
  int v13; // r12d
  _DWORD *v14; // r9
  _DWORD *v15; // rbx
  int v16; // edi
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  double v21; // xmm0_8
  double v22; // xmm0_8
  unsigned __int64 v23; // rcx
  char *v24; // r14
  DWORD v25; // edi
  double v26; // xmm1_8
  double v27; // xmm1_8
  unsigned __int64 v28; // rax
  unsigned int v29; // ebx
  unsigned int v30; // r14d
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // r8
  _BYTE *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  struct ILocationWiFiBeaconInformation *v49; // rax
  bool v50; // [rsp+58h] [rbp-B0h]
  unsigned int v51; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v52; // [rsp+60h] [rbp-A8h] BYREF
  struct _FILETIME v53; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v54; // [rsp+70h] [rbp-98h]
  unsigned __int64 v55; // [rsp+78h] [rbp-90h] BYREF
  _DWORD *v56; // [rsp+80h] [rbp-88h] BYREF
  __int64 v57; // [rsp+88h] [rbp-80h] BYREF
  __int64 v58; // [rsp+90h] [rbp-78h] BYREF
  __int64 v59; // [rsp+98h] [rbp-70h] BYREF
  __int64 v60; // [rsp+A0h] [rbp-68h] BYREF
  struct ILocationWiFiBeaconInformation **v61; // [rsp+A8h] [rbp-60h]
  char *v62; // [rsp+B0h] [rbp-58h]
  _BYTE v63[32]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v64[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v65[32]; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+118h] [rbp+10h] BYREF
  int v67; // [rsp+120h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+128h] [rbp+20h] BYREF

  v61 = a4;
  v51 = a3;
  v5 = 0;
  if ( !a4 )
    return 2147942487LL;
  ppv = 0;
  v55 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)a2 + 1) - *(_QWORD *)a2) >> 4);
  v7 = v55;
  v67 = 256;
  v57 = 0;
  SystemTimeAsFileTime = 0;
  *a4 = 0;
  if ( !v7 )
  {
    v8 = -2147024883;
LABEL_52:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return (unsigned int)v8;
  }
  v8 = CoCreateInstance(
         &GUID_b0dc057d_fa13_4cb3_b54d_4cc05e125781,
         0,
         1u,
         &GUID_ddfa49a5_bf2d_49ea_b7cd_f1a73a923efa,
         &ppv);
  if ( v8 < 0 )
    goto LABEL_52;
  v9 = (char *)CoTaskMemAlloc((unsigned int)(80 * v7));
  v10 = v9;
  v62 = v9;
  if ( !v9 )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
    return 2147942414LL;
  }
  memset_0(v9, 0, (unsigned int)(80 * v7));
  if ( (int)LocationHelper::CreateLocationComponent<ILocationPalMisc>(v11, &v57) >= 0 )
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v57 + 64LL))(v57, &v67);
  LODWORD(v54) = 0;
  v12 = 0;
  v13 = 0;
  v50 = ((v67 - 2) & 0xFFFFFFFD) == 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v14 = (_DWORD *)*((_QWORD *)a2 + 1);
  v56 = v14;
  v15 = *(_DWORD **)a2;
  if ( *(_DWORD **)a2 != v14 )
  {
    v16 = 0;
    do
    {
      if ( *v15 || *((_WORD *)v15 + 2) )
      {
        v17 = *((_QWORD *)v15 + 6);
        v53 = SystemTimeAsFileTime;
        v52 = v17;
        v18 = *(_QWORD *)&SystemTimeAsFileTime - v17;
        v19 = v52 - *(_QWORD *)&SystemTimeAsFileTime;
        if ( v52 - *(_QWORD *)&SystemTimeAsFileTime < 0 )
          v19 = v18;
        v20 = v19 / 10000;
        if ( v19 / 10000 <= (unsigned __int64)v51 )
          goto LABEL_24;
        ++v13;
        if ( v20 < 0 )
          v21 = (double)(int)((v19 / 10000) & 1 | ((unsigned __int64)v20 >> 1))
              + (double)(int)((v19 / 10000) & 1 | ((unsigned __int64)v20 >> 1));
        else
          v21 = (double)(int)v20;
        v22 = v21 / 1000.0;
        v23 = 0;
        if ( v22 >= 9.223372036854776e18 )
        {
          v22 = v22 - 9.223372036854776e18;
          if ( v22 < 9.223372036854776e18 )
            v23 = 0x8000000000000000uLL;
        }
        v5 += v23 + (unsigned int)(int)v22;
        if ( !v50 )
        {
LABEL_24:
          v24 = &v10[80 * v16];
          memcpy_s_0(v24, 6u, v15, 6u);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::GetImpl'::`2'::impl) )
            memcpy_s_0(v24 + 40, 0x24u, v15 + 2, 0x24u);
          *((_DWORD *)v24 + 2) = v15[15];
          *((_DWORD *)v24 + 3) = v15[14] / 0x3E8u;
          *((_DWORD *)v24 + 4) = v15[16];
          *((_DWORD *)v24 + 5) = v15[17];
          *((_DWORD *)v24 + 6) = v15[18];
          *((_DWORD *)v24 + 7) = v15[19];
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::GetImpl'::`2'::impl) )
            *((_QWORD *)v24 + 4) = *((_QWORD *)v15 + 6);
          ++v16;
          v14 = v56;
        }
      }
      else
      {
        ++v12;
      }
      v15 += 20;
    }
    while ( v15 != v14 );
    LODWORD(v54) = v16;
    v25 = v55;
    if ( v12 || v13 )
    {
      if ( v13 )
      {
        if ( v5 < 0 )
          v26 = (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1))
              + (double)(int)(v5 & 1 | ((unsigned __int64)v5 >> 1));
        else
          v26 = (double)(int)v5;
        v27 = v26 / (double)v13;
        v28 = 0;
        if ( v27 >= 9.223372036854776e18 )
        {
          v27 = v27 - 9.223372036854776e18;
          if ( v27 < 9.223372036854776e18 )
            v28 = 0x8000000000000000uLL;
        }
        v5 = v28 + (unsigned int)(int)v27;
      }
      v29 = 100 * v12 / (unsigned int)v55;
      v30 = 100 * v13 / (unsigned int)v55;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent>::GetImpl'::`2'::impl,
                              100 * v13 % (unsigned int)v55) )
      {
        v31 = dword_1801DDF30;
        if ( (unsigned int)dword_1801DDF30 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x200000000000LL) )
          goto LABEL_48;
        v53 = (struct _FILETIME)0x1000000LL;
        LODWORD(v55) = v51;
        LODWORD(v56) = v50;
        v34 = Bucketizer::ToStringBucketRange(&qword_1801E47B0, v64, v30);
        v52 = std::_String_val<std::_Simple_types<char>>::_Myptr(v34, v35);
        v36 = Bucketizer::ToStringBucketRange(&qword_1801E47A0, v63, v29);
        v59 = std::_String_val<std::_Simple_types<char>>::_Myptr(v36, v37);
        v38 = Bucketizer::ToStringBucketRange(&qword_1801E4790, v65, v25);
        v60 = std::_String_val<std::_Simple_types<char>>::_Myptr(v38, v39);
        v58 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v40,
          &word_1801B5196,
          v41,
          &v58,
          &v60,
          &v59,
          &v52,
          &v56,
          &v55,
          &v53);
        std::string::_Tidy_deallocate(v65);
        std::string::_Tidy_deallocate(v63);
        v42 = v64;
      }
      else
      {
        if ( (unsigned int)dword_1801DDF30 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x200000000000LL) )
          goto LABEL_48;
        v58 = 0x1000000;
        LODWORD(v56) = v51;
        LODWORD(v55) = v50;
        v43 = Bucketizer::ToStringBucketRange(&qword_1801E47B0, v63, v30);
        v60 = std::_String_val<std::_Simple_types<char>>::_Myptr(v43, v44);
        v45 = Bucketizer::ToStringBucketRange(&qword_1801E47A0, v64, v29);
        v59 = std::_String_val<std::_Simple_types<char>>::_Myptr(v45, v46);
        LODWORD(v52) = v25;
        v53 = (struct _FILETIME)1LL;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v47,
          &word_1801B4F4E,
          v48,
          &v53,
          &v52,
          &v59,
          &v60,
          &v55,
          &v56,
          &v58);
        std::string::_Tidy_deallocate(v64);
        v42 = v63;
      }
      std::string::_Tidy_deallocate(v42);
LABEL_48:
      if ( (unsigned int)dword_1801DDF30 > 5 )
      {
        LODWORD(v52) = v51;
        LODWORD(v56) = v50;
        v58 = v5;
        LODWORD(v55) = v13;
        v51 = v12;
        v53.dwLowDateTime = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v31,
          (unsigned int)&unk_1801B50B8,
          v32,
          v33,
          (__int64)&v53,
          (__int64)&v51,
          (__int64)&v55,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v52);
      }
    }
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, char *, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, v10, (unsigned int)v54);
  if ( v8 < 0 )
  {
    CoTaskMemFree(v10);
    goto LABEL_52;
  }
  v49 = (struct ILocationWiFiBeaconInformation *)ppv;
  ppv = 0;
  *v61 = v49;
  CoTaskMemFree(v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return 0;
}

```

## disassembly

```asm
0x18007c384  mov     rax, rsp
0x18007c387  mov     [rax+8], rbx
0x18007c38b  push    rbp
0x18007c38c  push    rsi
0x18007c38d  push    rdi
0x18007c38e  push    r12
0x18007c390  push    r13
0x18007c392  push    r14
0x18007c394  push    r15
0x18007c396  lea     rbp, [rax-78h]
0x18007c39a  sub     rsp, 140h
0x18007c3a1  movaps  xmmword ptr [rax-48h], xmm6
0x18007c3a5  mov     rax, cs:__security_cookie
0x18007c3ac  xor     rax, rsp
0x18007c3af  mov     [rbp+70h+var_48], rax
0x18007c3b3  mov     [rbp+70h+var_D0], r9
0x18007c3b7  mov     dword ptr [rsp+170h+var_120+4], r8d
0x18007c3bc  mov     r14, rdx
0x18007c3bf  xor     esi, esi
0x18007c3c1  test    r9, r9
0x18007c3c4  jnz     short loc_18007C3D0
0x18007c3c6  mov     eax, 80070057h
0x18007c3cb  jmp     loc_18007C9F0
0x18007c3d0  mov     [rbp+70h+var_60], rsi
0x18007c3d4  mov     rdi, [rdx+8]
0x18007c3d8  sub     rdi, [rdx]
0x18007c3db  sar     rdi, 4
0x18007c3df  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18007c3e9  imul    rdi, rcx
0x18007c3ed  mov     [rsp+170h+var_100], rdi
0x18007c3f2  mov     [rbp+70h+var_58], 100h
0x18007c3f9  mov     [rbp+70h+var_F0], rsi
0x18007c3fd  mov     qword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18007c401  mov     [r9], rsi
0x18007c404  test    edi, edi
0x18007c406  jnz     short loc_18007C412
0x18007c408  mov     ebx, 8007000Dh
0x18007c40d  jmp     loc_18007C98D
0x18007c412  lea     rax, [rbp+70h+var_60]
0x18007c416  mov     [rsp+170h+ppv], rax; ppv
0x18007c41b  lea     r9, _GUID_ddfa49a5_bf2d_49ea_b7cd_f1a73a923efa; riid
0x18007c422  xor     edx, edx; pUnkOuter
0x18007c424  lea     r8d, [rdx+1]; dwClsContext
0x18007c428  lea     rcx, _GUID_b0dc057d_fa13_4cb3_b54d_4cc05e125781; rclsid
0x18007c42f  call    cs:__imp_CoCreateInstance
0x18007c435  mov     ebx, eax
0x18007c437  test    eax, eax
0x18007c439  js      loc_18007C98D
0x18007c43f  lea     eax, [rdi+rdi*4]
0x18007c442  shl     eax, 4
0x18007c445  mov     ebx, eax
0x18007c447  mov     ecx, eax; cb
0x18007c449  call    cs:__imp_CoTaskMemAlloc
0x18007c44f  mov     r15, rax
0x18007c452  mov     [rbp+70h+var_C8], rax
0x18007c456  test    rax, rax
0x18007c459  jz      loc_18007C9D8
0x18007c45f  mov     r8d, ebx; Size
0x18007c462  xor     edx, edx; Val
0x18007c464  mov     rcx, rax; void *
0x18007c467  call    memset_0
0x18007c46c  lea     rdx, [rbp+70h+var_F0]
0x18007c470  call    ??$CreateLocationComponent@UILocationPalMisc@@@LocationHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAPEAUILocationPalMisc@@@Z; LocationHelper::CreateLocationComponent<ILocationPalMisc>(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ILocationPalMisc * *)
0x18007c475  test    eax, eax
0x18007c477  js      short loc_18007C48D
0x18007c479  mov     rcx, [rbp+70h+var_F0]
0x18007c47d  mov     rax, [rcx]
0x18007c480  lea     rdx, [rbp+70h+var_58]
0x18007c484  mov     rax, [rax+40h]
0x18007c488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c48d  mov     dword ptr [rsp+170h+var_108], esi
0x18007c491  mov     r13d, esi
0x18007c494  mov     r12d, esi
0x18007c497  mov     eax, [rbp+70h+var_58]
0x18007c49a  add     eax, 0FFFFFFFEh
0x18007c49d  test    eax, 0FFFFFFFDh
0x18007c4a2  setz    byte ptr [rsp+170h+var_120]
0x18007c4a7  lea     rcx, [rbp+70h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007c4ab  call    cs:__imp_GetSystemTimeAsFileTime
0x18007c4b1  mov     r9, [r14+8]
0x18007c4b5  mov     [rsp+170h+var_F8], r9
0x18007c4ba  mov     rbx, [r14]
0x18007c4bd  cmp     rbx, r9
0x18007c4c0  jz      loc_18007C965
0x18007c4c6  mov     r10, 8000000000000000h
0x18007c4d0  movsd   xmm6, cs:__real@43e0000000000000
0x18007c4d8  mov     edi, esi
0x18007c4da  xor     eax, eax
0x18007c4dc  cmp     eax, [rbx]
0x18007c4de  jnz     short loc_18007C4EE
0x18007c4e0  cmp     ax, [rbx+4]
0x18007c4e4  jnz     short loc_18007C4EE
0x18007c4e6  inc     r13d
0x18007c4e9  jmp     loc_18007C645
0x18007c4ee  mov     rax, [rbx+30h]
0x18007c4f2  mov     r8, rax
0x18007c4f5  shr     r8, 20h
0x18007c4f9  mov     edx, [rbp+70h+SystemTimeAsFileTime.dwLowDateTime]
0x18007c4fc  mov     ecx, [rbp+70h+SystemTimeAsFileTime.dwHighDateTime]
0x18007c4ff  mov     dword ptr [rsp+170h+var_110+4], ecx
0x18007c503  mov     dword ptr [rsp+170h+var_110], edx
0x18007c507  mov     dword ptr [rsp+170h+var_118+4], r8d
0x18007c50c  mov     dword ptr [rsp+170h+var_118], eax
0x18007c510  mov     rax, [rsp+170h+var_110]
0x18007c515  sub     rax, [rsp+170h+var_118]
0x18007c51a  mov     rcx, rax
0x18007c51d  neg     rcx
0x18007c520  cmovs   rcx, rax
0x18007c524  mov     rax, 346DC5D63886594Bh
0x18007c52e  imul    rcx
0x18007c531  sar     rdx, 0Bh
0x18007c535  mov     rax, rdx
0x18007c538  shr     rax, 3Fh
0x18007c53c  add     rdx, rax
0x18007c53f  mov     eax, dword ptr [rsp+170h+var_120+4]
0x18007c543  cmp     rdx, rax
0x18007c546  jbe     short loc_18007C5A2
0x18007c548  inc     r12d
0x18007c54b  xorps   xmm0, xmm0
0x18007c54e  test    rdx, rdx
0x18007c551  js      short loc_18007C55A
0x18007c553  cvtsi2sd xmm0, rdx
0x18007c558  jmp     short loc_18007C56F
0x18007c55a  mov     rax, rdx
0x18007c55d  shr     rax, 1
0x18007c560  and     edx, 1
0x18007c563  or      rax, rdx
0x18007c566  cvtsi2sd xmm0, rax
0x18007c56b  addsd   xmm0, xmm0
0x18007c56f  divsd   xmm0, cs:__real@408f400000000000
0x18007c577  xor     ecx, ecx
0x18007c579  comisd  xmm0, xmm6
0x18007c57d  jb      short loc_18007C58C
0x18007c57f  subsd   xmm0, xmm6
0x18007c583  comisd  xmm0, xmm6
0x18007c587  jnb     short loc_18007C58C
0x18007c589  mov     rcx, r10
0x18007c58c  cvttsd2si rax, xmm0
0x18007c591  add     rax, rcx
0x18007c594  add     rsi, rax
0x18007c597  cmp     byte ptr [rsp+170h+var_120], 0
0x18007c59c  jnz     loc_18007C645
0x18007c5a2  mov     eax, edi
0x18007c5a4  lea     r14, [rax+rax*4]
0x18007c5a8  shl     r14, 4
0x18007c5ac  add     r14, r15
0x18007c5af  mov     r9d, 6; SourceSize
0x18007c5b5  mov     r8, rbx; Source
0x18007c5b8  mov     edx, r9d; DestinationSize
0x18007c5bb  mov     rcx, r14; Destination
0x18007c5be  call    memcpy_s_0
0x18007c5c3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData> `wil::Feature<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::GetImpl(void)'::`2'::impl
0x18007c5ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::__private_IsEnabled(void)
0x18007c5cf  test    al, al
0x18007c5d1  jz      short loc_18007C5EA
0x18007c5d3  lea     r8, [rbx+8]; Source
0x18007c5d7  lea     rcx, [r14+28h]; Destination
0x18007c5db  mov     eax, 24h ; '$'
0x18007c5e0  mov     r9d, eax; SourceSize
0x18007c5e3  mov     edx, eax; DestinationSize
0x18007c5e5  call    memcpy_s_0
0x18007c5ea  mov     eax, [rbx+3Ch]
0x18007c5ed  mov     [r14+8], eax
0x18007c5f1  mov     eax, 10624DD3h
0x18007c5f6  mul     dword ptr [rbx+38h]
0x18007c5f9  shr     edx, 6
0x18007c5fc  mov     [r14+0Ch], edx
0x18007c600  mov     eax, [rbx+40h]
0x18007c603  mov     [r14+10h], eax
0x18007c607  mov     eax, [rbx+44h]
0x18007c60a  mov     [r14+14h], eax
0x18007c60e  mov     eax, [rbx+48h]
0x18007c611  mov     [r14+18h], eax
0x18007c615  mov     eax, [rbx+4Ch]
0x18007c618  mov     [r14+1Ch], eax
0x18007c61c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData> `wil::Feature<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::GetImpl(void)'::`2'::impl
0x18007c623  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_OptimizedWiFiScanData>::__private_IsEnabled(void)
0x18007c628  test    al, al
0x18007c62a  jz      short loc_18007C634
0x18007c62c  mov     rax, [rbx+30h]
0x18007c630  mov     [r14+20h], rax
0x18007c634  inc     edi
0x18007c636  mov     r9, [rsp+170h+var_F8]
0x18007c63b  mov     r10, 8000000000000000h
0x18007c645  add     rbx, 50h ; 'P'
0x18007c649  cmp     rbx, r9
0x18007c64c  jnz     loc_18007C4DA
0x18007c652  mov     dword ptr [rsp+170h+var_108], edi
0x18007c656  test    r13d, r13d
0x18007c659  mov     rdi, [rsp+170h+var_100]
0x18007c65e  jnz     short loc_18007C669
0x18007c660  test    r12d, r12d
0x18007c663  jz      loc_18007C965
0x18007c669  test    r12d, r12d
0x18007c66c  jz      short loc_18007C6BE
0x18007c66e  xorps   xmm1, xmm1
0x18007c671  test    rsi, rsi
0x18007c674  js      short loc_18007C67D
0x18007c676  cvtsi2sd xmm1, rsi
0x18007c67b  jmp     short loc_18007C692
0x18007c67d  mov     rax, rsi
0x18007c680  shr     rax, 1
0x18007c683  and     esi, 1
0x18007c686  or      rax, rsi
0x18007c689  cvtsi2sd xmm1, rax
0x18007c68e  addsd   xmm1, xmm1
0x18007c692  mov     eax, r12d
0x18007c695  xorps   xmm0, xmm0
0x18007c698  cvtsi2sd xmm0, rax
0x18007c69d  divsd   xmm1, xmm0
0x18007c6a1  xor     eax, eax
0x18007c6a3  comisd  xmm1, xmm6
0x18007c6a7  jb      short loc_18007C6B6
0x18007c6a9  subsd   xmm1, xmm6
0x18007c6ad  comisd  xmm1, xmm6
0x18007c6b1  jnb     short loc_18007C6B6
0x18007c6b3  mov     rax, r10
0x18007c6b6  cvttsd2si rsi, xmm1
0x18007c6bb  add     rsi, rax
0x18007c6be  imul    eax, r13d, 64h ; 'd'
0x18007c6c2  xor     edx, edx
0x18007c6c4  div     edi
0x18007c6c6  mov     ebx, eax
0x18007c6c8  imul    eax, r12d, 64h ; 'd'
0x18007c6cc  xor     edx, edx
0x18007c6ce  div     edi
0x18007c6d0  mov     r14d, eax
0x18007c6d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent> `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent>::GetImpl(void)'::`2'::impl
0x18007c6da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_WiFiGarrulousEvent>::__private_IsEnabled(void)
0x18007c6df  test    al, al
0x18007c6e1  jz      loc_18007C7FF
0x18007c6e7  mov     ecx, cs:dword_1801DDF30
0x18007c6ed  cmp     ecx, 5
0x18007c6f0  jbe     loc_18007C8F0
0x18007c6f6  mov     rdx, 200000000000h
0x18007c700  lea     rcx, dword_1801DDF30
0x18007c707  call    _tlgKeywordOn
0x18007c70c  test    al, al
0x18007c70e  jz      loc_18007C8F0
0x18007c714  mov     [rsp+170h+var_110], 1000000h
0x18007c71d  mov     eax, dword ptr [rsp+170h+var_120+4]
0x18007c721  mov     dword ptr [rsp+170h+var_100], eax
0x18007c725  movzx   eax, byte ptr [rsp+170h+var_120]
0x18007c72a  mov     dword ptr [rsp+170h+var_F8], eax
0x18007c72e  mov     r8d, r14d
0x18007c731  lea     rdx, [rbp+70h+var_A0]
0x18007c735  lea     rcx, qword_1801E47B0
0x18007c73c  call    ?ToStringBucketRange@Bucketizer@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; Bucketizer::ToStringBucketRange(ulong)
0x18007c741  nop
0x18007c742  mov     rcx, rax
0x18007c745  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007c74a  mov     [rsp+170h+var_118], rax
0x18007c74f  mov     r8d, ebx
0x18007c752  lea     rdx, [rbp+70h+var_C0]
0x18007c756  lea     rcx, qword_1801E47A0
0x18007c75d  call    ?ToStringBucketRange@Bucketizer@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; Bucketizer::ToStringBucketRange(ulong)
0x18007c762  nop
0x18007c763  mov     rcx, rax
0x18007c766  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007c76b  mov     [rbp+70h+var_E0], rax
0x18007c76f  mov     r8d, edi
0x18007c772  lea     rdx, [rbp+70h+var_80]
0x18007c776  lea     rcx, qword_1801E4790
0x18007c77d  call    ?ToStringBucketRange@Bucketizer@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z; Bucketizer::ToStringBucketRange(ulong)
0x18007c782  nop
0x18007c783  mov     rcx, rax
0x18007c786  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18007c78b  mov     [rbp+70h+var_D8], rax
0x18007c78f  mov     [rbp+70h+var_E8], 1
0x18007c797  lea     rax, [rsp+170h+var_110]
0x18007c79c  mov     qword ptr [rsp+170h+var_128], rax
0x18007c7a1  lea     rax, [rsp+170h+var_100]
0x18007c7a6  mov     [rsp+170h+var_130], rax
0x18007c7ab  lea     rax, [rsp+170h+var_F8]
0x18007c7b0  mov     [rsp+170h+var_138], rax
0x18007c7b5  lea     rax, [rsp+170h+var_118]
0x18007c7ba  mov     [rsp+170h+var_140], rax
0x18007c7bf  lea     rax, [rbp+70h+var_E0]
0x18007c7c3  mov     [rsp+170h+var_148], rax
0x18007c7c8  lea     rax, [rbp+70h+var_D8]
0x18007c7cc  mov     [rsp+170h+ppv], rax
0x18007c7d1  lea     r9, [rbp+70h+var_E8]
0x18007c7d5  lea     rdx, word_1801B5196
0x18007c7dc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@42@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18007c7e1  nop
0x18007c7e2  lea     rcx, [rbp+70h+var_80]
0x18007c7e6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007c7eb  nop
0x18007c7ec  lea     rcx, [rbp+70h+var_C0]
0x18007c7f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18007c7f5  nop
0x18007c7f6  lea     rcx, [rbp+70h+var_A0]
0x18007c7fa  jmp     loc_18007C8EB
0x18007c7ff  mov     eax, cs:dword_1801DDF30
0x18007c805  cmp     eax, 5
0x18007c808  jbe     loc_18007C8F0
0x18007c80e  mov     rdx, 200000000000h
0x18007c818  lea     rcx, dword_1801DDF30
0x18007c81f  call    _tlgKeywordOn
0x18007c824  test    al, al
  ... truncated ...
```

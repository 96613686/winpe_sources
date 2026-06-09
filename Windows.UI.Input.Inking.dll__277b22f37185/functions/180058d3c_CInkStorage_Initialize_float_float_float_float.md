# CInkStorage::Initialize(float,float,float,float)

- ea: `0x180058d3c`
- end: `0x180059090`
- name: `?Initialize@CInkStorage@@QEAAJMMMM@Z`
- size: `852`
- prototype: `__int64 __usercall@<rax>(LPVOID *ppv@<rcx>, float@<xmm1>, float@<xmm2>, float@<xmm3>, float)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800248d8`
- `0x180034120`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x180058544`
- `0x180058594`
- `0x180058d3c`
- `0x1800fb010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x180058e4d`
- `d3d11!D3D11CreateDevice` at `0x180058e4d`
- `d2d1!__imp_D2D1CreateFactory` at `0x180058eab`
- `d2d1!__imp_D2D1CreateFactory` at `0x180058eab`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058dc4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180058dc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInkStorage::Initialize(LPVOID *ppv, float a2, float a3, float a4, float a5)
{
  HRESULT Instance; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, LPVOID, LPVOID *); // rbx
  LPVOID *v11; // r15
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, _QWORD, __int64 *); // rbx
  int v14; // eax
  int v15; // ecx
  LPVOID *v16; // r14
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, __int64, _QWORD, _QWORD); // rbx
  LPVOID *v19; // rsi
  LPVOID v20; // rcx
  LPVOID *ppva; // [rsp+28h] [rbp-B1h]
  __int64 v23; // [rsp+58h] [rbp-81h] BYREF
  ID3D11Device *ppDevice; // [rsp+60h] [rbp-79h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+68h] [rbp-71h] BYREF
  __int64 v26; // [rsp+70h] [rbp-69h]
  __int64 v27; // [rsp+78h] [rbp-61h] BYREF
  float v28; // [rsp+80h] [rbp-59h]
  float v29; // [rsp+84h] [rbp-55h]
  __int64 v30; // [rsp+88h] [rbp-51h]
  __int64 v31; // [rsp+90h] [rbp-49h]
  __m128i si128; // [rsp+98h] [rbp-41h] BYREF
  float v33; // [rsp+A8h] [rbp-31h]
  float v34; // [rsp+ACh] [rbp-2Dh]
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+B8h] [rbp-21h] BYREF
  int v36; // [rsp+C8h] [rbp-11h]
  int v37; // [rsp+CCh] [rbp-Dh]
  int v38; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+57h]

  ppDevice = 0;
  ppImmediateContext = 0;
  v23 = 0;
  *((float *)ppv + 12) = a5;
  *((float *)ppv + 13) = a4;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv);
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_7b816b45_1996_4476_b132_de9e247c8af0, ppv);
  v7 = Instance;
  if ( Instance >= 0 )
  {
    *(__m128i *)pFeatureLevels = _mm_load_si128((const __m128i *)&_xmm);
    v36 = 37632;
    v37 = 37376;
    v38 = 37120;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppImmediateContext);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppDevice);
    Instance = D3D11CreateDevice(
                 0,
                 D3D_DRIVER_TYPE_WARP,
                 0,
                 0x20u,
                 pFeatureLevels,
                 7u,
                 7u,
                 &ppDevice,
                 0,
                 &ppImmediateContext);
    v7 = Instance;
    if ( Instance >= 0 )
    {
      Instance = Microsoft::WRL::ComPtr<ID3D11Device2>::As<IDXGIDevice>(&ppDevice, ppv + 5);
      v7 = Instance;
      if ( Instance >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv + 1);
        Instance = D2D1CreateFactory(
                     D2D1_FACTORY_TYPE_SINGLE_THREADED,
                     &GUID_94f81a73_9212_4376_9c58_b16a3a0d3992,
                     0,
                     ppv + 1);
        v7 = Instance;
        if ( Instance >= 0 )
        {
          v9 = ppv[1];
          v10 = *(__int64 (__fastcall **)(LPVOID, LPVOID, LPVOID *))(*(_QWORD *)v9 + 136LL);
          v11 = ppv + 4;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(ppv + 4);
          Instance = v10(v9, ppv[5], ppv + 4);
          v7 = Instance;
          if ( Instance >= 0 )
          {
            v12 = *v11;
            v13 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)*v11 + 32LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
            Instance = v13(v12, 0, &v23);
            v7 = Instance;
            if ( Instance >= 0 )
            {
              v14 = (int)*((float *)ppv + 13);
              v15 = (int)*((float *)ppv + 12);
              if ( !v14 )
                v14 = 1;
              LODWORD(v26) = v14;
              if ( !v15 )
                v15 = 1;
              HIDWORD(v26) = v15;
              si128.m128i_i64[0] = 0x100000057LL;
              v27 = 0x100000057LL;
              v28 = FLOAT_96_0;
              v29 = FLOAT_96_0;
              v30 = 1;
              v31 = 0;
              v16 = ppv + 3;
              Instance = Microsoft::WRL::ComPtr<ID2D1DeviceContext>::As<ID2D1DeviceContext2>(&v23, ppv + 3);
              v7 = Instance;
              if ( Instance >= 0 )
              {
                v17 = *v16;
                v18 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)*v16 + 456LL);
                v19 = ppv + 2;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v19);
                ppva = (LPVOID *)&v27;
                Instance = v18(v17, v26, 0, 0);
                v7 = Instance;
                if ( Instance >= 0 )
                {
                  v20 = *v16;
                  si128 = _mm_load_si128((const __m128i *)&_xmm);
                  v33 = a2 * -1.0;
                  v34 = a3 * -1.0;
                  (*(void (__fastcall **)(LPVOID, __m128i *))(*(_QWORD *)v20 + 240LL))(v20, &si128);
                  (*(void (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)*v16 + 592LL))(*v16, *v19);
                  v7 = 0;
                  goto LABEL_23;
                }
                v8 = 179;
              }
              else
              {
                v8 = 173;
              }
            }
            else
            {
              v8 = 158;
            }
          }
          else
          {
            v8 = 157;
          }
        }
        else
        {
          v8 = 155;
        }
      }
      else
      {
        v8 = 149;
      }
    }
    else
    {
      v8 = 147;
    }
  }
  else
  {
    v8 = 125;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\inkstorage.cpp",
    (const char *)(unsigned int)Instance,
    (int)ppva);
LABEL_23:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppImmediateContext);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppDevice);
  return v7;
}

```

## disassembly

```asm
0x180058d3c  mov     rax, rsp
0x180058d3f  mov     [rax+10h], rbx
0x180058d43  mov     [rax+18h], rsi
0x180058d47  push    rbp
0x180058d48  push    rdi
0x180058d49  push    r13
0x180058d4b  push    r14
0x180058d4d  push    r15
0x180058d4f  lea     rbp, [rax-57h]
0x180058d53  sub     rsp, 100h
0x180058d5a  movaps  xmmword ptr [rax-38h], xmm6
0x180058d5e  movaps  xmmword ptr [rax-48h], xmm7
0x180058d62  mov     rax, cs:__security_cookie
0x180058d69  xor     rax, rsp
0x180058d6c  mov     [rbp+4Fh+var_50], rax
0x180058d70  movaps  xmm6, xmm2
0x180058d73  movaps  xmm7, xmm1
0x180058d76  mov     rsi, rcx
0x180058d79  mov     [rbp+4Fh+var_C8], 0
0x180058d81  mov     [rbp+4Fh+var_C0], 0
0x180058d89  mov     [rsp+120h+var_D0], 0
0x180058d92  movss   xmm0, [rbp+4Fh+arg_20]
0x180058d97  movss   dword ptr [rcx+30h], xmm0
0x180058d9c  movss   dword ptr [rcx+34h], xmm3
0x180058da1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058da6  mov     [rsp+120h+ppv], rsi; ppv
0x180058dab  lea     r9, _GUID_7b816b45_1996_4476_b132_de9e247c8af0; riid
0x180058db2  mov     r13d, 1
0x180058db8  mov     r8d, r13d; dwClsContext
0x180058dbb  xor     edx, edx; pUnkOuter
0x180058dbd  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180058dc4  call    cs:__imp_CoCreateInstance
0x180058dca  mov     ebx, eax
0x180058dcc  test    eax, eax
0x180058dce  jns     short loc_180058DD9
0x180058dd0  lea     edx, [r13+7Ch]
0x180058dd4  jmp     loc_180058E5E
0x180058dd9  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x180058de1  movdqu  xmmword ptr [rbp+4Fh+pFeatureLevels], xmm0
0x180058de6  mov     [rbp+4Fh+var_60], 9300h
0x180058ded  mov     [rbp+4Fh+var_5C], 9200h
0x180058df4  mov     [rbp+4Fh+var_58], 9100h
0x180058dfb  lea     rcx, [rbp+4Fh+var_C0]
0x180058dff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058e04  lea     rcx, [rbp+4Fh+var_C8]
0x180058e08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058e0d  lea     rax, [rbp+4Fh+var_C0]
0x180058e11  mov     [rsp+120h+ppImmediateContext], rax; ppImmediateContext
0x180058e16  mov     [rsp+120h+pFeatureLevel], 0; pFeatureLevel
0x180058e1f  lea     rax, [rbp+4Fh+var_C8]
0x180058e23  mov     [rsp+120h+ppDevice], rax; ppDevice
0x180058e28  mov     eax, 7
0x180058e2d  mov     [rsp+120h+SDKVersion], eax; SDKVersion
0x180058e31  mov     [rsp+120h+FeatureLevels], eax; FeatureLevels
0x180058e35  lea     rax, [rbp+4Fh+pFeatureLevels]
0x180058e39  mov     [rsp+120h+ppv], rax; int
0x180058e3e  mov     r9d, 20h ; ' '; Flags
0x180058e44  xor     r8d, r8d; Software
0x180058e47  lea     edx, [r9-1Bh]; DriverType
0x180058e4b  xor     ecx, ecx; pAdapter
0x180058e4d  call    cs:__imp_D3D11CreateDevice
0x180058e53  mov     ebx, eax
0x180058e55  test    eax, eax
0x180058e57  jns     short loc_180058E76
0x180058e59  mov     edx, 93h; void *
0x180058e5e  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180058e65  mov     r9d, eax; char *
0x180058e68  mov     rcx, [rbp+57h]; this
0x180058e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e71  jmp     loc_18005903E
0x180058e76  lea     rdx, [rsi+28h]
0x180058e7a  lea     rcx, [rbp+4Fh+var_C8]
0x180058e7e  call    ??$As@UIDXGIDevice@@@?$ComPtr@UID3D11Device2@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDXGIDevice@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID3D11Device2>::As<IDXGIDevice>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDXGIDevice>>)
0x180058e83  mov     ebx, eax
0x180058e85  test    eax, eax
0x180058e87  jns     short loc_180058E90
0x180058e89  mov     edx, 95h
0x180058e8e  jmp     short loc_180058E5E
0x180058e90  lea     rdi, [rsi+8]
0x180058e94  mov     rcx, rdi
0x180058e97  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058e9c  mov     r9, rdi; ppIFactory
0x180058e9f  xor     r8d, r8d; pFactoryOptions
0x180058ea2  lea     rdx, _GUID_94f81a73_9212_4376_9c58_b16a3a0d3992; riid
0x180058ea9  xor     ecx, ecx; factoryType
0x180058eab  call    cs:__imp_D2D1CreateFactory
0x180058eb1  mov     ebx, eax
0x180058eb3  test    eax, eax
0x180058eb5  jns     short loc_180058EBE
0x180058eb7  mov     edx, 9Bh
0x180058ebc  jmp     short loc_180058E5E
0x180058ebe  mov     rdi, [rdi]
0x180058ec1  mov     rax, [rdi]
0x180058ec4  mov     rbx, [rax+88h]
0x180058ecb  lea     r15, [rsi+20h]
0x180058ecf  mov     rcx, r15
0x180058ed2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058ed7  mov     r8, r15
0x180058eda  mov     rdx, [rsi+28h]
0x180058ede  mov     rcx, rdi
0x180058ee1  mov     rax, rbx
0x180058ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ee9  mov     ebx, eax
0x180058eeb  test    eax, eax
0x180058eed  jns     short loc_180058EF9
0x180058eef  mov     edx, 9Dh
0x180058ef4  jmp     loc_180058E5E
0x180058ef9  mov     rdi, [r15]
0x180058efc  mov     rax, [rdi]
0x180058eff  mov     rbx, [rax+20h]
0x180058f03  lea     rcx, [rsp+120h+var_D0]
0x180058f08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058f0d  lea     r8, [rsp+120h+var_D0]
0x180058f12  xor     edx, edx
0x180058f14  mov     rcx, rdi
0x180058f17  mov     rax, rbx
0x180058f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f1f  mov     ebx, eax
0x180058f21  test    eax, eax
0x180058f23  jns     short loc_180058F2F
0x180058f25  mov     edx, 9Eh
0x180058f2a  jmp     loc_180058E5E
0x180058f2f  cvttss2si rax, dword ptr [rsi+34h]
0x180058f35  cvttss2si rcx, dword ptr [rsi+30h]
0x180058f3b  test    eax, eax
0x180058f3d  cmovz   eax, r13d
0x180058f41  mov     dword ptr [rbp+4Fh+var_B8], eax
0x180058f44  test    ecx, ecx
0x180058f46  cmovz   ecx, r13d
0x180058f4a  mov     dword ptr [rbp+4Fh+var_B8+4], ecx
0x180058f4d  mov     dword ptr [rbp+4Fh+var_90], 57h ; 'W'
0x180058f54  mov     dword ptr [rbp+4Fh+var_90+4], r13d
0x180058f58  movss   xmm0, cs:__real@42c00000
0x180058f60  mov     rax, qword ptr [rbp+4Fh+var_90]
0x180058f64  mov     [rbp+4Fh+var_B0], rax
0x180058f68  movss   [rbp+4Fh+var_A8], xmm0
0x180058f6d  movss   [rbp+4Fh+var_A4], xmm0
0x180058f72  mov     [rbp+4Fh+var_A0], r13
0x180058f76  mov     [rbp+4Fh+var_98], 0
0x180058f7e  lea     r14, [rsi+18h]
0x180058f82  mov     rdx, r14
0x180058f85  lea     rcx, [rsp+120h+var_D0]
0x180058f8a  call    ??$As@UID2D1DeviceContext2@@@?$ComPtr@UID2D1DeviceContext@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UID2D1DeviceContext2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ID2D1DeviceContext>::As<ID2D1DeviceContext2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ID2D1DeviceContext2>>)
0x180058f8f  mov     ebx, eax
0x180058f91  test    eax, eax
0x180058f93  jns     short loc_180058F9F
0x180058f95  mov     edx, 0ADh
0x180058f9a  jmp     loc_180058E5E
0x180058f9f  mov     rdi, [r14]
0x180058fa2  mov     rax, [rdi]
0x180058fa5  mov     rbx, [rax+1C8h]
0x180058fac  add     rsi, 10h
0x180058fb0  mov     rcx, rsi
0x180058fb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058fb8  mov     qword ptr [rsp+120h+FeatureLevels], rsi
0x180058fbd  lea     rax, [rbp+4Fh+var_B0]
0x180058fc1  mov     [rsp+120h+ppv], rax
0x180058fc6  xor     r9d, r9d
0x180058fc9  xor     r8d, r8d
0x180058fcc  mov     rdx, [rbp+4Fh+var_B8]
0x180058fd0  mov     rcx, rdi
0x180058fd3  mov     rax, rbx
0x180058fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058fdb  mov     ebx, eax
0x180058fdd  test    eax, eax
0x180058fdf  jns     short loc_180058FEB
0x180058fe1  mov     edx, 0B3h
0x180058fe6  jmp     loc_180058E5E
0x180058feb  mov     rcx, [r14]
0x180058fee  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180058ff6  movups  [rbp+4Fh+var_90], xmm0
0x180058ffa  mulss   xmm7, cs:__real@bf800000
0x180059002  movss   [rbp+4Fh+var_80], xmm7
0x180059007  mulss   xmm6, cs:__real@bf800000
0x18005900f  movss   [rbp+4Fh+var_7C], xmm6
0x180059014  mov     rax, [rcx]
0x180059017  lea     rdx, [rbp+4Fh+var_90]
0x18005901b  mov     rax, [rax+0F0h]
0x180059022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059027  mov     rcx, [r14]
0x18005902a  mov     rax, [rcx]
0x18005902d  mov     rdx, [rsi]
0x180059030  mov     rax, [rax+250h]
0x180059037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005903c  xor     ebx, ebx
0x18005903e  lea     rcx, [rsp+120h+var_D0]
0x180059043  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059048  nop
0x180059049  lea     rcx, [rbp+4Fh+var_C0]
0x18005904d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059052  nop
0x180059053  lea     rcx, [rbp+4Fh+var_C8]
0x180059057  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005905c  mov     eax, ebx
0x18005905e  mov     rcx, [rbp+4Fh+var_50]
0x180059062  xor     rcx, rsp; StackCookie
0x180059065  call    __security_check_cookie
0x18005906a  lea     r11, [rsp+120h+var_20]
0x180059072  mov     rbx, [r11+38h]
0x180059076  mov     rsi, [r11+40h]
0x18005907a  movaps  xmm6, xmmword ptr [r11-10h]
0x18005907f  movaps  xmm7, xmmword ptr [r11-20h]
0x180059084  mov     rsp, r11
0x180059087  pop     r15
0x180059089  pop     r14
0x18005908b  pop     r13
0x18005908d  pop     rdi
0x18005908e  pop     rbp
0x18005908f  retn
```

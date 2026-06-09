# VideoFrameImpl::GetDXGIDeviceManager(IMFDXGIDeviceManager * *)

- ea: `0x1800376f4`
- end: `0x1800378c7`
- name: `?GetDXGIDeviceManager@VideoFrameImpl@@AEAAXPEAPEAUIMFDXGIDeviceManager@@@Z`
- size: `467`
- prototype: `void __fastcall(VideoFrameImpl *__hidden this, struct IMFDXGIDeviceManager **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800371c0`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x180026920`
- `0x180036074`
- `0x1800376f4`
- `0x180052010`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x180037801`
- `d3d11!D3D11CreateDevice` at `0x180037801`
- `MFPlat!MFLockDXGIDeviceManager` at `0x18003774f`
- `MFPlat!MFLockDXGIDeviceManager` at `0x18003774f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall VideoFrameImpl::GetDXGIDeviceManager(VideoFrameImpl *this, struct IMFDXGIDeviceManager **a2)
{
  unsigned int v4; // eax
  int v5; // edx
  unsigned int v6; // eax
  int v7; // edx
  ID3D11Device *v8; // rdi
  HRESULT (__stdcall *QueryInterface)(ID3D11Device *, const IID *const, void **); // rbx
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v12; // eax
  int v13; // edx
  struct IMFDXGIDeviceManager *v14; // rax
  IMFDXGIDeviceManager *ppManager; // [rsp+50h] [rbp-29h] BYREF
  UINT pResetToken; // [rsp+58h] [rbp-21h] BYREF
  ID3D11Device *ppDevice; // [rsp+60h] [rbp-19h] BYREF
  __int64 v18; // [rsp+68h] [rbp-11h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+70h] [rbp-9h] BYREF
  __int64 v20; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v21[8]; // [rsp+80h] [rbp+7h] BYREF
  __int64 *v22; // [rsp+88h] [rbp+Fh]
  IMFDXGIDeviceManager **p_ppManager; // [rsp+90h] [rbp+17h]
  D3D_FEATURE_LEVEL pFeatureLevels[4]; // [rsp+98h] [rbp+1Fh] BYREF
  int v25; // [rsp+A8h] [rbp+2Fh]
  int v26; // [rsp+ACh] [rbp+33h]
  int v27; // [rsp+B0h] [rbp+37h]

  ppManager = 0;
  pResetToken = 0;
  v20 = 0;
  v21[0] = 0;
  v22 = &v20;
  p_ppManager = &ppManager;
  v4 = MFLockDXGIDeviceManager(&pResetToken, &ppManager);
  MF::ThrowIfFailed((MF *)v4, v5);
  *((_BYTE *)this + 216) = 1;
  if ( ((int (__fastcall *)(IMFDXGIDeviceManager *, __int64 *))ppManager->lpVtbl->OpenDeviceHandle)(ppManager, &v20) < 0 )
  {
    ppDevice = 0;
    v18 = 0;
    pFeatureLevel = 0;
    *(__m128i *)pFeatureLevels = _mm_load_si128((const __m128i *)&_xmm);
    v25 = 37632;
    v26 = 37376;
    v27 = 37120;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppDevice);
    v6 = D3D11CreateDevice(0, D3D_DRIVER_TYPE_HARDWARE, 0, 0x828u, pFeatureLevels, 7u, 7u, &ppDevice, &pFeatureLevel, 0);
    MF::ThrowIfFailed((MF *)v6, v7);
    v8 = ppDevice;
    QueryInterface = ppDevice->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v18);
    v10 = ((__int64 (__fastcall *)(ID3D11Device *, GUID *, __int64 *))QueryInterface)(
            v8,
            &GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0,
            &v18);
    MF::ThrowIfFailed((MF *)v10, v11);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 40LL))(v18, 1);
    v12 = ((__int64 (__fastcall *)(IMFDXGIDeviceManager *, ID3D11Device *, _QWORD))ppManager->lpVtbl->ResetDevice)(
            ppManager,
            ppDevice,
            pResetToken);
    MF::ThrowIfFailed((MF *)v12, v13);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppDevice);
  }
  v14 = ppManager;
  ppManager = 0;
  *a2 = v14;
  ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___::_ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___(v21);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppManager);
}

```

## disassembly

```asm
0x1800376f4  mov     [rsp-8+arg_10], rbx
0x1800376f9  push    rbp
0x1800376fa  push    rsi
0x1800376fb  push    rdi
0x1800376fc  lea     rbp, [rsp-47h]
0x180037701  sub     rsp, 0C0h
0x180037708  mov     rax, cs:__security_cookie
0x18003770f  xor     rax, rsp
0x180037712  mov     [rbp+57h+var_18], rax
0x180037716  mov     rsi, rdx
0x180037719  mov     rbx, rcx
0x18003771c  mov     [rbp+57h+ppManager], 0
0x180037724  mov     [rbp+57h+pResetToken], 0
0x18003772b  mov     [rbp+57h+var_58], 0
0x180037733  mov     [rbp+57h+var_50], 0
0x180037737  lea     rax, [rbp+57h+var_58]
0x18003773b  mov     [rbp+57h+var_48], rax
0x18003773f  lea     rax, [rbp+57h+ppManager]
0x180037743  mov     [rbp+57h+var_40], rax
0x180037747  lea     rdx, [rbp+57h+ppManager]; ppManager
0x18003774b  lea     rcx, [rbp+57h+pResetToken]; pResetToken
0x18003774f  call    cs:__imp_MFLockDXGIDeviceManager
0x180037755  mov     ecx, eax; this
0x180037757  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18003775c  mov     byte ptr [rbx+0D8h], 1
0x180037763  mov     rcx, [rbp+57h+ppManager]
0x180037767  mov     rax, [rcx]
0x18003776a  lea     rdx, [rbp+57h+var_58]
0x18003776e  mov     rax, [rax+30h]
0x180037772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037777  test    eax, eax
0x180037779  jns     loc_180037886
0x18003777f  mov     [rbp+57h+var_70], 0
0x180037787  mov     [rbp+57h+var_68], 0
0x18003778f  mov     [rbp+57h+var_60], 0
0x180037796  movdqa  xmm0, cs:__xmm@0000a0000000a1000000b0000000b100
0x18003779e  movdqu  xmmword ptr [rbp+57h+var_38], xmm0
0x1800377a3  mov     [rbp+57h+var_28], 9300h
0x1800377aa  mov     [rbp+57h+var_24], 9200h
0x1800377b1  mov     [rbp+57h+var_20], 9100h
0x1800377b8  lea     rcx, [rbp+57h+var_70]
0x1800377bc  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800377c1  mov     [rsp+0D0h+ppImmediateContext], 0; ppImmediateContext
0x1800377ca  lea     rax, [rbp+57h+var_60]
0x1800377ce  mov     [rsp+0D0h+pFeatureLevel], rax; pFeatureLevel
0x1800377d3  lea     rax, [rbp+57h+var_70]
0x1800377d7  mov     [rsp+0D0h+ppDevice], rax; ppDevice
0x1800377dc  mov     eax, 7
0x1800377e1  mov     [rsp+0D0h+SDKVersion], eax; SDKVersion
0x1800377e5  mov     [rsp+0D0h+FeatureLevels], eax; FeatureLevels
0x1800377e9  lea     rax, [rbp+57h+var_38]
0x1800377ed  mov     [rsp+0D0h+pFeatureLevels], rax; pFeatureLevels
0x1800377f2  mov     r9d, 828h; Flags
0x1800377f8  xor     r8d, r8d; Software
0x1800377fb  lea     edx, [r8+1]; DriverType
0x1800377ff  xor     ecx, ecx; pAdapter
0x180037801  call    cs:__imp_D3D11CreateDevice
0x180037807  mov     ecx, eax; this
0x180037809  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18003780e  mov     rdi, [rbp+57h+var_70]
0x180037812  mov     rax, [rdi]
0x180037815  mov     rbx, [rax]
0x180037818  lea     rcx, [rbp+57h+var_68]
0x18003781c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037821  lea     r8, [rbp+57h+var_68]
0x180037825  lea     rdx, _GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0
0x18003782c  mov     rcx, rdi
0x18003782f  mov     rax, rbx
0x180037832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037837  mov     ecx, eax; this
0x180037839  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18003783e  mov     rcx, [rbp+57h+var_68]
0x180037842  mov     rax, [rcx]
0x180037845  mov     edx, 1
0x18003784a  mov     rax, [rax+28h]
0x18003784e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037853  mov     rcx, [rbp+57h+ppManager]
0x180037857  mov     rax, [rcx]
0x18003785a  mov     r8d, [rbp+57h+pResetToken]
0x18003785e  mov     rdx, [rbp+57h+var_70]
0x180037862  mov     rax, [rax+38h]
0x180037866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003786b  mov     ecx, eax; this
0x18003786d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180037872  nop
0x180037873  lea     rcx, [rbp+57h+var_68]
0x180037877  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18003787c  nop
0x18003787d  lea     rcx, [rbp+57h+var_70]
0x180037881  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180037886  mov     rax, [rbp+57h+ppManager]
0x18003788a  mov     [rbp+57h+ppManager], 0
0x180037892  mov     [rsi], rax
0x180037895  lea     rcx, [rbp+57h+var_50]
0x180037899  call    ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14______ScopeGuardImpl0__lambda_ef03f6bfae4f7ce35853f9d2e913be14___
0x18003789e  nop
0x18003789f  lea     rcx, [rbp+57h+ppManager]
0x1800378a3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800378a8  mov     rcx, [rbp+57h+var_18]
0x1800378ac  xor     rcx, rsp; StackCookie
0x1800378af  call    __security_check_cookie
0x1800378b4  mov     rbx, [rsp+0D0h+arg_10]
0x1800378bc  add     rsp, 0C0h
0x1800378c3  pop     rdi
0x1800378c4  pop     rsi
0x1800378c5  pop     rbp
0x1800378c6  retn
```

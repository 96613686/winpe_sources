# DeviceFactoryD3D11CreateDeviceWrapper(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)

- ea: `0x1800ca058`
- end: `0x1800ca1f1`
- name: `?DeviceFactoryD3D11CreateDeviceWrapper@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z`
- size: `409`
- prototype: `__int64 __usercall@<rax>(IDXGIAdapter *pAdapter@<rcx>, D3D_DRIVER_TYPE DriverType@<edx>, HINSTANCE@<r8>, unsigned int@<r9d>, D3D_FEATURE_LEVEL *, UINT, unsigned int, ID3D11Device **, enum D3D_FEATURE_LEVEL *, struct ID3D11DeviceContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800c9854`

## callees

- `0x18000fe40`
- `0x1800404ec`
- `0x1800ca058`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x1800ca10b`
- `d3d11!D3D11CreateDevice` at `0x1800ca1d3`
- `d3d11!D3D11CreateDevice` at `0x1800ca10b`
- `d3d11!D3D11CreateDevice` at `0x1800ca1d3`

## pseudocode

```c
HRESULT __fastcall DeviceFactoryD3D11CreateDeviceWrapper(
        IDXGIAdapter *pAdapter,
        D3D_DRIVER_TYPE DriverType,
        ID3D11DeviceContext *a3,
        UINT a4,
        D3D_FEATURE_LEVEL *a5,
        UINT a6,
        unsigned int a7,
        ID3D11Device **a8,
        enum D3D_FEATURE_LEVEL *a9,
        struct ID3D11DeviceContext **a10)
{
  UINT v10; // ebx
  UINT FeatureLevels; // r12d
  const D3D_FEATURE_LEVEL *pFeatureLevels; // r13
  char v15; // al
  unsigned int v16; // ecx
  char v17; // r15
  HRESULT v18; // r14d
  ID3D11Device *ppDevice[2]; // [rsp+50h] [rbp-10h] BYREF
  ID3D11DeviceContext *ppImmediateContext; // [rsp+B0h] [rbp+50h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+B8h] [rbp+58h] BYREF

  ppImmediateContext = a3;
  v10 = a4;
  if ( (a4 & 2) == 0 )
    return D3D11CreateDevice(pAdapter, DriverType, 0, a4, a5, a6, 7u, a8, a9, a10);
  FeatureLevels = a6;
  pFeatureLevels = a5;
  while ( 1 )
  {
    v15 = std::_Atomic_storage<bool,1>::load(&`DeviceFactoryD3D11CreateDeviceWrapper'::`5'::tryDebugDevice);
    ppDevice[0] = 0;
    v16 = v10 & 0xFFFFFFFD;
    pFeatureLevel = 0;
    v10 |= 2u;
    ppImmediateContext = 0;
    v17 = v15;
    if ( !v15 )
      v10 = v16;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppImmediateContext);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppDevice);
    v18 = D3D11CreateDevice(
            pAdapter,
            DriverType,
            0,
            v10,
            pFeatureLevels,
            FeatureLevels,
            7u,
            ppDevice,
            &pFeatureLevel,
            &ppImmediateContext);
    if ( v18 >= 0 )
      break;
    if ( !v17 )
      goto LABEL_14;
    `DeviceFactoryD3D11CreateDeviceWrapper'::`5'::tryDebugDevice = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppImmediateContext);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppDevice);
  }
  if ( a8 )
  {
    *a8 = ppDevice[0];
    ppDevice[0] = 0;
  }
  if ( a9 )
    *a9 = pFeatureLevel;
  if ( a10 )
  {
    *a10 = ppImmediateContext;
    ppImmediateContext = 0;
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppImmediateContext);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppDevice);
  return v18;
}

```

## disassembly

```asm
0x1800ca058  mov     [rsp-38h+arg_0], rbx
0x1800ca05d  mov     [rsp-38h+arg_10], r8
0x1800ca062  push    rbp
0x1800ca063  push    rsi
0x1800ca064  push    rdi
0x1800ca065  push    r12
0x1800ca067  push    r13
0x1800ca069  push    r14
0x1800ca06b  push    r15
0x1800ca06d  mov     rbp, rsp
0x1800ca070  sub     rsp, 60h
0x1800ca074  mov     ebx, r9d
0x1800ca077  mov     edi, edx
0x1800ca079  mov     rsi, rcx
0x1800ca07c  test    r9b, 2
0x1800ca080  jz      loc_1800CA197
0x1800ca086  mov     r12d, [rbp+arg_28]
0x1800ca08a  mov     r13, [rbp+arg_20]
0x1800ca08e  lea     rcx, ?tryDebugDevice@?4??DeviceFactoryD3D11CreateDeviceWrapper@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW45@PEAPEAUID3D11DeviceContext@@@Z@4U?$atomic@_N@std@@A; std::atomic<bool> `DeviceFactoryD3D11CreateDeviceWrapper(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)'::`5'::tryDebugDevice
0x1800ca095  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x1800ca09a  mov     ecx, ebx
0x1800ca09c  mov     [rbp+var_10], 0
0x1800ca0a4  and     ecx, 0FFFFFFFDh
0x1800ca0a7  mov     [rbp+arg_18], 0
0x1800ca0ae  or      ebx, 2
0x1800ca0b1  mov     [rbp+arg_10], 0
0x1800ca0b9  test    al, al
0x1800ca0bb  mov     r15b, al
0x1800ca0be  cmovz   ebx, ecx
0x1800ca0c1  lea     rcx, [rbp+arg_10]
0x1800ca0c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca0ca  lea     rcx, [rbp+var_10]
0x1800ca0ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca0d3  lea     rax, [rbp+arg_10]
0x1800ca0d7  mov     r9d, ebx; Flags
0x1800ca0da  mov     [rsp+60h+ppImmediateContext], rax; ppImmediateContext
0x1800ca0df  xor     r8d, r8d; Software
0x1800ca0e2  lea     rax, [rbp+arg_18]
0x1800ca0e6  mov     edx, edi; DriverType
0x1800ca0e8  mov     [rsp+60h+pFeatureLevel], rax; pFeatureLevel
0x1800ca0ed  mov     rcx, rsi; pAdapter
0x1800ca0f0  lea     rax, [rbp+var_10]
0x1800ca0f4  mov     [rsp+60h+ppDevice], rax; ppDevice
0x1800ca0f9  mov     [rsp+60h+SDKVersion], 7; SDKVersion
0x1800ca101  mov     [rsp+60h+FeatureLevels], r12d; FeatureLevels
0x1800ca106  mov     [rsp+60h+pFeatureLevels], r13; pFeatureLevels
0x1800ca10b  call    cs:__imp_D3D11CreateDevice
0x1800ca111  mov     r14d, eax
0x1800ca114  test    eax, eax
0x1800ca116  jns     short loc_1800CA13C
0x1800ca118  test    r15b, r15b
0x1800ca11b  jz      short loc_1800CA180
0x1800ca11d  xor     eax, eax
0x1800ca11f  lea     rcx, [rbp+arg_10]
0x1800ca123  xchg    al, cs:?tryDebugDevice@?4??DeviceFactoryD3D11CreateDeviceWrapper@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW45@PEAPEAUID3D11DeviceContext@@@Z@4U?$atomic@_N@std@@A; std::atomic<bool> `DeviceFactoryD3D11CreateDeviceWrapper(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)'::`5'::tryDebugDevice
0x1800ca129  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca12e  lea     rcx, [rbp+var_10]
0x1800ca132  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca137  jmp     loc_1800CA08E
0x1800ca13c  mov     rcx, [rbp+arg_38]
0x1800ca140  test    rcx, rcx
0x1800ca143  jz      short loc_1800CA154
0x1800ca145  mov     rax, [rbp+var_10]
0x1800ca149  mov     [rcx], rax
0x1800ca14c  mov     [rbp+var_10], 0
0x1800ca154  mov     rcx, [rbp+arg_40]
0x1800ca15b  test    rcx, rcx
0x1800ca15e  jz      short loc_1800CA165
0x1800ca160  mov     eax, [rbp+arg_18]
0x1800ca163  mov     [rcx], eax
0x1800ca165  mov     rcx, [rbp+arg_48]
0x1800ca16c  test    rcx, rcx
0x1800ca16f  jz      short loc_1800CA180
0x1800ca171  mov     rax, [rbp+arg_10]
0x1800ca175  mov     [rcx], rax
0x1800ca178  mov     [rbp+arg_10], 0
0x1800ca180  lea     rcx, [rbp+arg_10]
0x1800ca184  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca189  lea     rcx, [rbp+var_10]
0x1800ca18d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ca192  mov     eax, r14d
0x1800ca195  jmp     short loc_1800CA1D9
0x1800ca197  mov     rax, [rbp+arg_48]
0x1800ca19e  xor     r8d, r8d; Software
0x1800ca1a1  mov     [rsp+60h+ppImmediateContext], rax; ppImmediateContext
0x1800ca1a6  mov     rax, [rbp+arg_40]
0x1800ca1ad  mov     [rsp+60h+pFeatureLevel], rax; pFeatureLevel
0x1800ca1b2  mov     rax, [rbp+arg_38]
0x1800ca1b6  mov     [rsp+60h+ppDevice], rax; ppDevice
0x1800ca1bb  mov     eax, [rbp+arg_28]
0x1800ca1be  mov     [rsp+60h+SDKVersion], 7; SDKVersion
0x1800ca1c6  mov     [rsp+60h+FeatureLevels], eax; FeatureLevels
0x1800ca1ca  mov     rax, [rbp+arg_20]
0x1800ca1ce  mov     [rsp+60h+pFeatureLevels], rax; pFeatureLevels
0x1800ca1d3  call    cs:__imp_D3D11CreateDevice
0x1800ca1d9  mov     rbx, [rsp+60h+arg_0]
0x1800ca1e1  add     rsp, 60h
0x1800ca1e5  pop     r15
0x1800ca1e7  pop     r14
0x1800ca1e9  pop     r13
0x1800ca1eb  pop     r12
0x1800ca1ed  pop     rdi
0x1800ca1ee  pop     rsi
0x1800ca1ef  pop     rbp
0x1800ca1f0  retn
```

# CDXDeviceFactory::CreateDeviceResources(Microsoft::WRL::ComPtr<IDXGIAdapter1> &,Microsoft::WRL::ComPtr<ID3D11Device1> &,Microsoft::WRL::ComPtr<ID3D11DeviceContext1> &,GraphicsDeviceType,AdditionalDeviceFlags,AdditionalDevicePerformanceFlags,D3D_FEATURE_LEVEL,D3D_FEATURE_LEVEL,DeviceFeatureFlags)

- ea: `0x1800c9854`
- end: `0x1800ca04f`
- name: `?CreateDeviceResources@CDXDeviceFactory@@AEAAJAEAV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@AEAV?$ComPtr@UID3D11Device1@@@34@AEAV?$ComPtr@UID3D11DeviceContext1@@@34@W4GraphicsDeviceType@@W4AdditionalDeviceFlags@@W4AdditionalDevicePerformanceFlags@@W4D3D_FEATURE_LEVEL@@6W4DeviceFeatureFlags@@@Z`
- size: `2043`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b6640`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000e87c`
- `0x18000e8d0`
- `0x18000fe40`
- `0x18005c034`
- `0x180094034`
- `0x1800b3954`
- `0x1800b39a4`
- `0x1800c4c20`
- `0x1800c9330`
- `0x1800c9380`
- `0x1800c93d0`
- `0x1800c949c`
- `0x1800c9564`
- `0x1800c969c`
- `0x1800c9854`
- `0x1800ca058`
- `0x1800ca1f8`
- `0x1800e7010`

## import_xrefs

- `dxgi!CreateDXGIFactory1` at `0x1800c9a11`
- `dxgi!CreateDXGIFactory1` at `0x1800c9a11`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDXDeviceFactory::CreateDeviceResources(
        void **a1,
        IDXGIAdapter **a2,
        _QWORD *a3,
        _QWORD *a4,
        int a5,
        char a6,
        int a7,
        enum D3D_FEATURE_LEVEL a8,
        D3D_FEATURE_LEVEL a9,
        char a10)
{
  int v13; // ecx
  HRESULT DXGIFactory1; // esi
  char v15; // si
  char *v16; // rdi
  D3D_FEATURE_LEVEL v17; // eax
  int v18; // edx
  int v19; // eax
  void **v20; // rdi
  unsigned int i; // r13d
  void *v23; // rdi
  unsigned int (__fastcall *v24)(void *, _QWORD, IDXGIAdapter **); // rbx
  _OWORD *v25; // rcx
  _OWORD *v26; // rax
  __int64 v27; // rdx
  int v28; // r9d
  float v29; // xmm0_4
  __int64 *v30; // rbx
  UINT v31; // edi
  ID3D11DeviceContext *v32; // r8
  D3D_FEATURE_LEVEL *v33; // rdx
  __int64 **v34; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  void *v37; // rcx
  ID3D11DeviceContext *v38; // r8
  void **v39; // rdi
  __int64 (__fastcall *v40)(void **, struct ID3D11DeviceContext **); // rbx
  unsigned int v41; // [rsp+30h] [rbp-D0h]
  ID3D11Device *v42; // [rsp+50h] [rbp-B0h] BYREF
  enum D3D_FEATURE_LEVEL v43[2]; // [rsp+58h] [rbp-A8h] BYREF
  enum D3D_FEATURE_LEVEL v44[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v45; // [rsp+68h] [rbp-98h]
  void **v46; // [rsp+70h] [rbp-90h] BYREF
  struct ID3D11DeviceContext *v47[2]; // [rsp+78h] [rbp-88h] BYREF
  D3D_FEATURE_LEVEL *v48[2]; // [rsp+88h] [rbp-78h] BYREF
  D3D_FEATURE_LEVEL *v49; // [rsp+98h] [rbp-68h]
  __int128 v50; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[320]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v52[272]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v53; // [rsp+300h] [rbp+200h]
  int v54; // [rsp+320h] [rbp+220h]
  _OWORD v55[2]; // [rsp+330h] [rbp+230h] BYREF
  int v56; // [rsp+350h] [rbp+250h]
  char v57; // [rsp+354h] [rbp+254h] BYREF
  int v58; // [rsp+3D8h] [rbp+2D8h]

  v46 = a1;
  v50 = 0;
  std::_Tree<std::_Tset_traits<std::weak_ptr<Spectre::Engine::Material>,std::owner_less<std::weak_ptr<Spectre::Engine::Material>>,std::allocator<std::weak_ptr<Spectre::Engine::Material>>,0>>::_Alloc_sentinel_and_proxy(&v50);
  memset_0(v52, 0, 0x138u);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(v48);
  v45 = a10 & 1;
  if ( (a10 & 1) != 0 || (a10 & 2) != 0 )
  {
    v13 = a8;
    if ( a8 < D3D_FEATURE_LEVEL_10_0 )
    {
LABEL_4:
      DXGIFactory1 = -2147024809;
LABEL_27:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
      goto LABEL_28;
    }
  }
  else
  {
    v13 = a8;
  }
  if ( (a6 & 4) != 0 )
  {
    v15 = 1;
    if ( v13 < 45312 )
      goto LABEL_4;
  }
  else
  {
    v15 = 0;
  }
  v55[0] = _mm_load_si128((const __m128i *)&_xmm);
  v55[1] = _mm_load_si128((const __m128i *)&_xmm);
  v56 = 37120;
  v16 = (char *)v55;
  do
  {
    v17 = *(_DWORD *)v16;
    LODWORD(v42) = v17;
    if ( v17 >= v13 && v17 <= a9 )
    {
      if ( v48[1] == v49 )
      {
        std::vector<float>::_Emplace_reallocate<float const &>(v48, v48[1], &v42);
        v13 = a8;
      }
      else
      {
        *v48[1]++ = v17;
      }
    }
    v16 += 4;
  }
  while ( v16 != &v57 );
  v18 = (2 * (a6 & 1) + 32) | 0x40;
  if ( (a6 & 2) == 0 )
    v18 = 2 * (a6 & 1) + 32;
  v19 = v18 | 0x100;
  if ( !v15 )
    v19 = v18;
  v44[0] = a6 & 8;
  if ( (a6 & 0x10) != 0 )
    v19 |= 0x800u;
  LODWORD(v42) = v19;
  v58 = a6 & 0x20;
  v20 = v46 + 1;
  v46 = v20;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
  DXGIFactory1 = CreateDXGIFactory1(&GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0, v20);
  if ( DXGIFactory1 < 0 )
    goto LABEL_27;
  if ( a5 )
  {
    if ( a5 != 1 )
    {
LABEL_26:
      DXGIFactory1 = -2147467259;
      goto LABEL_27;
    }
    v31 = (unsigned int)v42;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v23 = *v20;
      v24 = *(unsigned int (__fastcall **)(void *, _QWORD, IDXGIAdapter **))(*(_QWORD *)v23 + 96LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
      if ( v24(v23, i, a2) == -2005270526 )
        break;
      DXGIFactory1 = ((__int64 (__fastcall *)(IDXGIAdapter *, _BYTE *))(*a2)->lpVtbl[1].QueryInterface)(*a2, v52);
      if ( DXGIFactory1 < 0 )
        goto LABEL_27;
      if ( !v58 || (v54 & 2) == 0 )
      {
        v25 = v51;
        v26 = v52;
        v27 = 2;
        do
        {
          *v25 = *v26;
          v25[1] = v26[1];
          v25[2] = v26[2];
          v25[3] = v26[3];
          v25[4] = v26[4];
          v25[5] = v26[5];
          v25[6] = v26[6];
          v25[7] = v26[7];
          v25 += 8;
          v26 += 8;
          --v27;
        }
        while ( v27 );
        *v25 = *v26;
        v25[1] = v26[1];
        v25[2] = v26[2];
        *((_QWORD *)v25 + 6) = *((_QWORD *)v26 + 6);
        if ( !Othello::IsDeviceBadConfig((Othello *)v51, 0) )
        {
          if ( v53 < 0 )
            v29 = (float)(v53 & 1 | (unsigned int)((unsigned __int64)v53 >> 1))
                + (float)(v53 & 1 | (unsigned int)((unsigned __int64)v53 >> 1));
          else
            v29 = (float)(int)v53;
          v43[0] = SLODWORD(v29);
          if ( v44[0] )
            *(float *)v43 = v29 * -1.0;
          if ( v28 )
            v43[0] = -8388609;
          std::_Tree<std::_Tmap_traits<float,Microsoft::WRL::ComPtr<IDXGIAdapter1>,std::greater<float>,std::allocator<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>>,1>>::_Emplace<float &,Microsoft::WRL::ComPtr<IDXGIAdapter1> &>(
            &v50,
            v47,
            v43,
            a2);
        }
      }
      v20 = v46;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    v30 = *(__int64 **)v50;
    v31 = (unsigned int)v42;
    while ( v30 != (__int64 *)v50 )
    {
      Microsoft::WRL::ComPtr<ID3D11DepthStencilView>::operator=(a2, v30 + 5);
      DXGIFactory1 = ((__int64 (__fastcall *)(IDXGIAdapter *, _BYTE *))(*a2)->lpVtbl[1].QueryInterface)(*a2, v52);
      if ( DXGIFactory1 < 0 )
        goto LABEL_27;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
      *(_QWORD *)v44 = 0;
      v43[0] = 0;
      v47[0] = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v44);
      DXGIFactory1 = DeviceFactoryD3D11CreateDeviceWrapper(
                       *a2,
                       D3D_DRIVER_TYPE_UNKNOWN,
                       v32,
                       v31,
                       v48[0],
                       v48[1] - v48[0],
                       v41,
                       (ID3D11Device **)v44,
                       v43,
                       v47);
      if ( DXGIFactory1 < 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
      }
      else if ( v43[0] >= a8 )
      {
        if ( !v45
          || v43[0] >= D3D_FEATURE_LEVEL_11_0
          || (LODWORD(v42) = 0,
              (*(int (__fastcall **)(_QWORD, __int64, ID3D11Device **))(**(_QWORD **)v44 + 264LL))(
                *(_QWORD *)v44,
                4,
                &v42) >= 0)
          && (_DWORD)v42 )
        {
          DXGIFactory1 = Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device1>(v44, a3);
          if ( DXGIFactory1 < 0
            || (DXGIFactory1 = Microsoft::WRL::ComPtr<ID3D11DeviceContext>::As<ID3D11DeviceContext1>(v47, a4),
                DXGIFactory1 < 0) )
          {
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
            v37 = v44;
            goto LABEL_80;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v44);
          break;
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v44);
      v34 = (__int64 **)v30[2];
      if ( *((_BYTE *)v34 + 25) )
      {
        for ( j = (__int64 *)v30[1]; !*((_BYTE *)j + 25) && v30 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v30 = j;
        v30 = j;
      }
      else
      {
        v30 = (__int64 *)v30[2];
        for ( k = *v34; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v30 = k;
      }
    }
    if ( v58 || *a2 && *a3 && *a4 )
      goto LABEL_95;
    v33 = v48[0];
    if ( v48[0] == v48[1] )
      v33 = v48[1];
    else
      v48[1] = v48[0];
    v44[0] = D3D_FEATURE_LEVEL_10_0;
    if ( v33 == v49 )
    {
      std::vector<float>::_Emplace_reallocate<float const &>(v48, v33, v44);
    }
    else
    {
      *v33 = D3D_FEATURE_LEVEL_10_0;
      ++v48[1];
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a3);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
  }
  v42 = 0;
  v44[0] = 0;
  *(_QWORD *)v43 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  DXGIFactory1 = DeviceFactoryD3D11CreateDeviceWrapper(
                   0,
                   D3D_DRIVER_TYPE_WARP,
                   v38,
                   v31,
                   v48[0],
                   v48[1] - v48[0],
                   v41,
                   &v42,
                   v44,
                   (struct ID3D11DeviceContext **)v43);
  if ( DXGIFactory1 < 0 )
    goto LABEL_85;
  v46 = 0;
  DXGIFactory1 = Microsoft::WRL::ComPtr<ID3D11Device>::As<IDXGIDevice>(&v42, &v46);
  if ( DXGIFactory1 < 0 )
  {
LABEL_87:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
LABEL_85:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v43);
    v37 = &v42;
LABEL_80:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
    goto LABEL_27;
  }
  v47[0] = 0;
  v39 = v46;
  v40 = (__int64 (__fastcall *)(void **, struct ID3D11DeviceContext **))*((_QWORD *)*v46 + 7);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
  DXGIFactory1 = v40(v39, v47);
  if ( DXGIFactory1 < 0
    || (DXGIFactory1 = Microsoft::WRL::ComPtr<IDXGIAdapter>::As<IDXGIAdapter1>(v47, a2), DXGIFactory1 < 0)
    || (DXGIFactory1 = Microsoft::WRL::ComPtr<ID3D11Device>::As<ID3D11Device1>(&v42, a3), DXGIFactory1 < 0)
    || (DXGIFactory1 = Microsoft::WRL::ComPtr<ID3D11DeviceContext>::As<ID3D11DeviceContext1>(v43, a4), DXGIFactory1 < 0)
    || (DXGIFactory1 = ((__int64 (__fastcall *)(IDXGIAdapter *, _BYTE *))(*a2)->lpVtbl[1].QueryInterface)(*a2, v52),
        DXGIFactory1 < 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
    goto LABEL_87;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
LABEL_95:
  if ( !*a2 || !*a3 || !*a4 )
    goto LABEL_26;
  CDXPixDebug::SetDebugName<IDXGIAdapter1>();
  CDXPixDebug::SetDebugName<ID3D11Device1>(*a3);
  if ( DXGIFactory1 < 0 )
    goto LABEL_27;
LABEL_28:
  if ( v48[0] )
  {
    std::_Deallocate<16>(v48[0], ((char *)v49 - (char *)v48[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    *(_OWORD *)v48 = 0;
    v49 = 0;
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>,void *>>>(
    &v50,
    &v50);
  return (unsigned int)DXGIFactory1;
}

```

## disassembly

```asm
0x1800c9854  push    rbp
0x1800c9856  push    rbx
0x1800c9857  push    rsi
0x1800c9858  push    rdi
0x1800c9859  push    r12
0x1800c985b  push    r13
0x1800c985d  push    r14
0x1800c985f  push    r15
0x1800c9861  lea     rbp, [rsp-268h]
0x1800c9869  sub     rsp, 368h
0x1800c9870  mov     rax, cs:__security_cookie
0x1800c9877  xor     rax, rsp
0x1800c987a  mov     [rbp+2A0h+var_48], rax
0x1800c9881  mov     r12, r9
0x1800c9884  mov     r15, r8
0x1800c9887  mov     r14, rdx
0x1800c988a  mov     [rsp+3A0h+var_330], rcx
0x1800c988f  xorps   xmm0, xmm0
0x1800c9892  movdqu  [rbp+2A0h+var_300], xmm0
0x1800c9897  lea     rcx, [rbp+2A0h+var_300]
0x1800c989b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@U?$owner_less@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@@2@V?$allocator@V?$weak_ptr@VMaterial@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<std::weak_ptr<Spectre::Engine::Material>,std::owner_less<std::weak_ptr<Spectre::Engine::Material>>,std::allocator<std::weak_ptr<Spectre::Engine::Material>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1800c98a0  nop
0x1800c98a1  xor     edx, edx; Val
0x1800c98a3  mov     r8d, 138h; Size
0x1800c98a9  lea     rcx, [rbp+2A0h+var_1B0]; void *
0x1800c98b0  call    memset_0
0x1800c98b5  mov     rcx, r14
0x1800c98b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c98bd  mov     rcx, r15
0x1800c98c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c98c5  mov     rcx, r12
0x1800c98c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c98cd  lea     rcx, [rbp+2A0h+var_318]; void *
0x1800c98d1  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x1800c98d6  nop
0x1800c98d7  mov     al, [rbp+2A0h+arg_48]
0x1800c98dd  and     al, 1
0x1800c98df  mov     [rsp+3A0h+var_338], al
0x1800c98e3  jnz     short loc_1800C98EE
0x1800c98e5  test    [rbp+2A0h+arg_48], 2
0x1800c98ec  jz      short loc_1800C9906
0x1800c98ee  mov     ecx, [rbp+2A0h+arg_38]
0x1800c98f4  cmp     ecx, 0A000h
0x1800c98fa  jge     short loc_1800C990C
0x1800c98fc  mov     esi, 80070057h
0x1800c9901  jmp     loc_1800C9A33
0x1800c9906  mov     ecx, [rbp+2A0h+arg_38]
0x1800c990c  mov     r13d, [rbp+2A0h+arg_28]
0x1800c9913  test    r13b, 4
0x1800c9917  jz      short loc_1800C9926
0x1800c9919  mov     sil, 1
0x1800c991c  cmp     ecx, 0B100h
0x1800c9922  jge     short loc_1800C9929
0x1800c9924  jmp     short loc_1800C98FC
0x1800c9926  xor     sil, sil
0x1800c9929  mov     ebx, [rbp+2A0h+arg_20]
0x1800c992f  movdqa  xmm0, cs:__xmm@0000b0000000b1000000c0000000c100
0x1800c9937  movdqu  [rbp+2A0h+var_70], xmm0
0x1800c993f  movdqa  xmm1, cs:__xmm@00009200000093000000a0000000a100
0x1800c9947  movdqu  [rbp+2A0h+var_60], xmm1
0x1800c994f  mov     [rbp+2A0h+var_50], 9100h
0x1800c9959  lea     rdi, [rbp+2A0h+var_70]
0x1800c9960  mov     eax, [rdi]
0x1800c9962  mov     dword ptr [rsp+3A0h+var_350], eax
0x1800c9966  cmp     eax, ecx
0x1800c9968  jl      short loc_1800C9999
0x1800c996a  cmp     eax, [rbp+2A0h+arg_40]
0x1800c9970  jg      short loc_1800C9999
0x1800c9972  mov     rdx, [rbp+2A0h+var_318+8]
0x1800c9976  cmp     rdx, [rbp+2A0h+var_308]
0x1800c997a  jz      short loc_1800C9985
0x1800c997c  mov     [rdx], eax
0x1800c997e  add     [rbp+2A0h+var_318+8], 4
0x1800c9983  jmp     short loc_1800C9999
0x1800c9985  lea     r8, [rsp+3A0h+var_350]
0x1800c998a  lea     rcx, [rbp+2A0h+var_318]
0x1800c998e  call    ??$_Emplace_reallocate@AEBM@?$vector@MV?$allocator@M@std@@@std@@AEAAPEAMQEAMAEBM@Z; std::vector<float>::_Emplace_reallocate<float const &>(float * const,float const &)
0x1800c9993  mov     ecx, [rbp+2A0h+arg_38]
0x1800c9999  add     rdi, 4
0x1800c999d  lea     rax, [rbp+2A0h+var_4C]
0x1800c99a4  cmp     rdi, rax
0x1800c99a7  jnz     short loc_1800C9960
0x1800c99a9  mov     eax, r13d
0x1800c99ac  and     eax, 1
0x1800c99af  lea     ecx, ds:20h[rax*2]
0x1800c99b6  mov     edx, ecx
0x1800c99b8  or      edx, 40h
0x1800c99bb  test    r13b, 2
0x1800c99bf  cmovz   edx, ecx
0x1800c99c2  mov     eax, edx
0x1800c99c4  bts     eax, 8
0x1800c99c8  test    sil, sil
0x1800c99cb  cmovz   eax, edx
0x1800c99ce  mov     ecx, r13d
0x1800c99d1  and     ecx, 8
0x1800c99d4  mov     [rsp+3A0h+var_340], ecx
0x1800c99d8  test    r13b, 10h
0x1800c99dc  jz      short loc_1800C99E2
0x1800c99de  bts     eax, 0Bh
0x1800c99e2  mov     dword ptr [rsp+3A0h+var_350], eax
0x1800c99e6  and     r13d, 20h
0x1800c99ea  mov     [rbp+2A0h+arg_28], r13d
0x1800c99f1  mov     rdi, [rsp+3A0h+var_330]
0x1800c99f6  add     rdi, 8
0x1800c99fa  mov     [rsp+3A0h+var_330], rdi
0x1800c99ff  mov     rcx, rdi
0x1800c9a02  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9a07  mov     rdx, rdi; ppFactory
0x1800c9a0a  lea     rcx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0; riid
0x1800c9a11  call    cs:__imp_CreateDXGIFactory1
0x1800c9a17  mov     esi, eax
0x1800c9a19  test    eax, eax
0x1800c9a1b  js      short loc_1800C9A33
0x1800c9a1d  test    ebx, ebx
0x1800c9a1f  jz      loc_1800C9AA7
0x1800c9a25  cmp     ebx, 1
0x1800c9a28  jz      loc_1800C9E96
0x1800c9a2e  mov     esi, 80004005h
0x1800c9a33  mov     rcx, r14
0x1800c9a36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9a3b  mov     rcx, r15
0x1800c9a3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9a43  mov     rcx, r12
0x1800c9a46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9a4b  nop
0x1800c9a4c  mov     rcx, [rbp+2A0h+var_318]
0x1800c9a50  test    rcx, rcx
0x1800c9a53  jz      short loc_1800C9A75
0x1800c9a55  mov     rdx, [rbp+2A0h+var_308]
0x1800c9a59  sub     rdx, rcx
0x1800c9a5c  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1800c9a60  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c9a65  xorps   xmm0, xmm0
0x1800c9a68  movdqu  xmmword ptr [rbp+2A0h+var_318], xmm0
0x1800c9a6d  mov     [rbp+2A0h+var_308], 0
0x1800c9a75  lea     rdx, [rbp+2A0h+var_300]
0x1800c9a79  lea     rcx, [rbp+2A0h+var_300]
0x1800c9a7d  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBMV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBMV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBMV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>,void *>>>(std::allocator<std::_Tree_node<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>,void *>> &)
0x1800c9a82  mov     eax, esi
0x1800c9a84  mov     rcx, [rbp+2A0h+var_48]
0x1800c9a8b  xor     rcx, rsp; StackCookie
0x1800c9a8e  call    __security_check_cookie
0x1800c9a93  add     rsp, 368h
0x1800c9a9a  pop     r15
0x1800c9a9c  pop     r14
0x1800c9a9e  pop     r13
0x1800c9aa0  pop     r12
0x1800c9aa2  pop     rdi
0x1800c9aa3  pop     rsi
0x1800c9aa4  pop     rbx
0x1800c9aa5  pop     rbp
0x1800c9aa6  retn
0x1800c9aa7  xor     r13d, r13d
0x1800c9aaa  mov     rdi, [rdi]
0x1800c9aad  mov     rax, [rdi]
0x1800c9ab0  mov     rbx, [rax+60h]
0x1800c9ab4  mov     rcx, r14
0x1800c9ab7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9abc  mov     r8, r14
0x1800c9abf  mov     edx, r13d
0x1800c9ac2  mov     rcx, rdi
0x1800c9ac5  mov     rax, rbx
0x1800c9ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9acd  cmp     eax, 887A0002h
0x1800c9ad2  jz      loc_1800C9C14
0x1800c9ad8  mov     rcx, [r14]
0x1800c9adb  mov     rax, [rcx]
0x1800c9ade  lea     rdx, [rbp+2A0h+var_1B0]
0x1800c9ae5  mov     rax, [rax+50h]
0x1800c9ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9aee  mov     esi, eax
0x1800c9af0  test    eax, eax
0x1800c9af2  js      loc_1800C9A33
0x1800c9af8  mov     r9d, [rbp+2A0h+var_80]
0x1800c9aff  and     r9d, 2
0x1800c9b03  cmp     [rbp+2A0h+arg_28], 0
0x1800c9b0a  jz      short loc_1800C9B15
0x1800c9b0c  test    r9d, r9d
0x1800c9b0f  jnz     loc_1800C9C07
0x1800c9b15  lea     rcx, [rbp+2A0h+var_2F0]
0x1800c9b19  lea     rax, [rbp+2A0h+var_1B0]
0x1800c9b20  mov     edx, 2
0x1800c9b25  lea     r8d, [rdx+7Eh]
0x1800c9b29  movups  xmm0, xmmword ptr [rax]
0x1800c9b2c  movups  xmmword ptr [rcx], xmm0
0x1800c9b2f  movups  xmm1, xmmword ptr [rax+10h]
0x1800c9b33  movups  xmmword ptr [rcx+10h], xmm1
0x1800c9b37  movups  xmm0, xmmword ptr [rax+20h]
0x1800c9b3b  movups  xmmword ptr [rcx+20h], xmm0
0x1800c9b3f  movups  xmm1, xmmword ptr [rax+30h]
0x1800c9b43  movups  xmmword ptr [rcx+30h], xmm1
0x1800c9b47  movups  xmm0, xmmword ptr [rax+40h]
0x1800c9b4b  movups  xmmword ptr [rcx+40h], xmm0
0x1800c9b4f  movups  xmm1, xmmword ptr [rax+50h]
0x1800c9b53  movups  xmmword ptr [rcx+50h], xmm1
0x1800c9b57  movups  xmm0, xmmword ptr [rax+60h]
0x1800c9b5b  movups  xmmword ptr [rcx+60h], xmm0
0x1800c9b5f  movups  xmm1, xmmword ptr [rax+70h]
0x1800c9b63  movups  xmmword ptr [rcx+70h], xmm1
0x1800c9b67  add     rcx, r8
0x1800c9b6a  add     rax, r8
0x1800c9b6d  sub     rdx, 1; struct DXGI_ADAPTER_DESC1
0x1800c9b71  jnz     short loc_1800C9B29
0x1800c9b73  movups  xmm0, xmmword ptr [rax]
0x1800c9b76  movups  xmmword ptr [rcx], xmm0
0x1800c9b79  movups  xmm1, xmmword ptr [rax+10h]
0x1800c9b7d  movups  xmmword ptr [rcx+10h], xmm1
0x1800c9b81  movups  xmm0, xmmword ptr [rax+20h]
0x1800c9b85  movups  xmmword ptr [rcx+20h], xmm0
0x1800c9b89  mov     rax, [rax+30h]
0x1800c9b8d  mov     [rcx+30h], rax
0x1800c9b91  lea     rcx, [rbp+2A0h+var_2F0]; this
0x1800c9b95  call    ?IsDeviceBadConfig@Othello@@YA_NUDXGI_ADAPTER_DESC1@@@Z; Othello::IsDeviceBadConfig(DXGI_ADAPTER_DESC1)
0x1800c9b9a  test    al, al
0x1800c9b9c  jnz     short loc_1800C9C07
0x1800c9b9e  mov     rcx, [rbp+2A0h+var_A0]
0x1800c9ba5  xorps   xmm0, xmm0
0x1800c9ba8  test    rcx, rcx
0x1800c9bab  js      short loc_1800C9BB4
0x1800c9bad  cvtsi2ss xmm0, rcx
0x1800c9bb2  jmp     short loc_1800C9BC9
0x1800c9bb4  mov     rax, rcx
0x1800c9bb7  shr     rax, 1
0x1800c9bba  and     ecx, 1
0x1800c9bbd  or      rax, rcx
0x1800c9bc0  cvtsi2ss xmm0, rax
0x1800c9bc5  addss   xmm0, xmm0
0x1800c9bc9  movss   [rsp+3A0h+var_348], xmm0
0x1800c9bcf  cmp     [rsp+3A0h+var_340], 0
0x1800c9bd4  jz      short loc_1800C9BE4
0x1800c9bd6  mulss   xmm0, cs:__real@bf800000
0x1800c9bde  movss   [rsp+3A0h+var_348], xmm0
0x1800c9be4  test    r9d, r9d
0x1800c9be7  jz      short loc_1800C9BF1
0x1800c9be9  mov     [rsp+3A0h+var_348], 0FF7FFFFFh
0x1800c9bf1  mov     r9, r14
0x1800c9bf4  lea     r8, [rsp+3A0h+var_348]
0x1800c9bf9  lea     rdx, [rsp+3A0h+var_328]
0x1800c9bfe  lea     rcx, [rbp+2A0h+var_300]
0x1800c9c02  call    ??$_Emplace@AEAMAEAV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@MV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@U?$greater@M@std@@V?$allocator@U?$pair@$$CBMV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@std@@@5@$00@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBMV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEAMAEAV?$ComPtr@UIDXGIAdapter1@@@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<float,Microsoft::WRL::ComPtr<IDXGIAdapter1>,std::greater<float>,std::allocator<std::pair<float const,Microsoft::WRL::ComPtr<IDXGIAdapter1>>>,1>>::_Emplace<float &,Microsoft::WRL::ComPtr<IDXGIAdapter1> &>(float &,Microsoft::WRL::ComPtr<IDXGIAdapter1> &)
0x1800c9c07  inc     r13d
0x1800c9c0a  mov     rdi, [rsp+3A0h+var_330]
0x1800c9c0f  jmp     loc_1800C9AAA
0x1800c9c14  mov     rcx, r14
0x1800c9c17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9c1c  mov     rbx, qword ptr [rbp+2A0h+var_300]
0x1800c9c20  mov     rbx, [rbx]
0x1800c9c23  mov     edi, dword ptr [rsp+3A0h+var_350]
0x1800c9c27  mov     r13d, [rbp+2A0h+arg_38]
0x1800c9c2e  cmp     rbx, qword ptr [rbp+2A0h+var_300]
0x1800c9c32  jz      loc_1800C9D81
0x1800c9c38  lea     rdx, [rbx+28h]
0x1800c9c3c  mov     rcx, r14
0x1800c9c3f  call    ??4?$ComPtr@UID3D11DepthStencilView@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ID3D11DepthStencilView>::operator=(Microsoft::WRL::ComPtr<ID3D11DepthStencilView> const &)
0x1800c9c44  mov     rcx, [r14]
0x1800c9c47  mov     rax, [rcx]
0x1800c9c4a  lea     rdx, [rbp+2A0h+var_1B0]
0x1800c9c51  mov     rax, [rax+50h]
0x1800c9c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9c5a  mov     esi, eax
0x1800c9c5c  test    eax, eax
0x1800c9c5e  js      loc_1800C9A33
0x1800c9c64  mov     rcx, r15
0x1800c9c67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9c6c  mov     rcx, r12
0x1800c9c6f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9c74  xor     eax, eax
0x1800c9c76  mov     qword ptr [rsp+3A0h+var_340], rax
0x1800c9c7b  mov     [rsp+3A0h+var_348], eax
0x1800c9c7f  mov     [rsp+3A0h+var_328], rax
0x1800c9c84  lea     rcx, [rsp+3A0h+var_328]
0x1800c9c89  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9c8e  lea     rcx, [rsp+3A0h+var_340]
0x1800c9c93  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9c98  mov     rcx, [rbp+2A0h+var_318]
0x1800c9c9c  mov     rax, [rbp+2A0h+var_318+8]
0x1800c9ca0  sub     rax, rcx
0x1800c9ca3  sar     rax, 2
0x1800c9ca7  lea     rdx, [rsp+3A0h+var_328]
0x1800c9cac  mov     [rsp+3A0h+var_358], rdx; struct ID3D11DeviceContext **
0x1800c9cb1  lea     rdx, [rsp+3A0h+var_348]
0x1800c9cb6  mov     [rsp+3A0h+var_360], rdx; enum D3D_FEATURE_LEVEL *
0x1800c9cbb  lea     rdx, [rsp+3A0h+var_340]
0x1800c9cc0  mov     [rsp+3A0h+var_368], rdx; ID3D11Device **
0x1800c9cc5  mov     [rsp+3A0h+var_378], eax; UINT
0x1800c9cc9  mov     [rsp+3A0h+var_380], rcx; D3D_FEATURE_LEVEL *
0x1800c9cce  mov     r9d, edi; unsigned int
0x1800c9cd1  xor     edx, edx; DriverType
0x1800c9cd3  mov     rcx, [r14]; pAdapter
0x1800c9cd6  call    ?DeviceFactoryD3D11CreateDeviceWrapper@@YAJPEAUIDXGIAdapter@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@IPEBW4D3D_FEATURE_LEVEL@@IIPEAPEAUID3D11Device@@PEAW44@PEAPEAUID3D11DeviceContext@@@Z; DeviceFactoryD3D11CreateDeviceWrapper(IDXGIAdapter *,D3D_DRIVER_TYPE,HINSTANCE__ *,uint,D3D_FEATURE_LEVEL const *,uint,uint,ID3D11Device * *,D3D_FEATURE_LEVEL *,ID3D11DeviceContext * *)
0x1800c9cdb  mov     esi, eax
0x1800c9cdd  test    eax, eax
0x1800c9cdf  js      loc_1800C9DD9
0x1800c9ce5  cmp     [rsp+3A0h+var_348], r13d
0x1800c9cea  jl      loc_1800C9DF2
0x1800c9cf0  cmp     [rsp+3A0h+var_338], 0
0x1800c9cf5  jz      short loc_1800C9D3E
0x1800c9cf7  cmp     [rsp+3A0h+var_348], 0B000h
0x1800c9cff  jge     short loc_1800C9D3E
0x1800c9d01  mov     dword ptr [rsp+3A0h+var_350], 0
  ... truncated ...
```

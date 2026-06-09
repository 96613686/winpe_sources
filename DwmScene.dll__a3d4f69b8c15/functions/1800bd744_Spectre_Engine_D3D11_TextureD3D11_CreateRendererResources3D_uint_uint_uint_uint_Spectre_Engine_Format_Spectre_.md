# Spectre::Engine::D3D11::TextureD3D11::CreateRendererResources3D(uint,uint,uint,uint,Spectre::Engine::Format,Spectre::Engine::Usage,uint,void const *,unsigned __int64)

- ea: `0x1800bd744`
- end: `0x1800bdb79`
- name: `?CreateRendererResources3D@TextureD3D11@D3D11@Engine@Spectre@@IEAAXIIIIW4Format@34@W4Usage@34@IPEBX_K@Z`
- size: `1077`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800bd080`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000dfa2`
- `0x18000fe40`
- `0x18001128c`
- `0x180011f64`
- `0x180012c58`
- `0x18001c290`
- `0x180028604`
- `0x180050dcc`
- `0x1800512e4`
- `0x180051300`
- `0x1800681a8`
- `0x1800b62f0`
- `0x1800b7e3c`
- `0x1800bbaac`
- `0x1800bc4b4`
- `0x1800bd744`
- `0x1800bddc4`
- `0x1800be04c`
- `0x1800be9e4`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800bda42`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800bda42`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Spectre::Engine::D3D11::TextureD3D11::CreateRendererResources3D(
        __int64 a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        __int64 a9)
{
  unsigned int v12; // r13d
  int v13; // eax
  int v14; // r8d
  __int64 v15; // rbx
  int v16; // ebx
  unsigned int v17; // eax
  int v18; // ecx
  int FormatSlicePitch_0; // edi
  __int128 *v20; // rax
  int v21; // ecx
  __int64 v22; // rdx
  __m128i v23; // xmm6
  unsigned __int64 v24; // r13
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int128 *, unsigned __int64, __int64 *); // rbx
  bool v27; // cf
  int v28; // eax
  ULONG_PTR v29; // rbx
  _DWORD *v30; // rax
  int v31; // edx
  __int64 v32; // rcx
  __int64 v34; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD *v38; // [rsp+68h] [rbp-A0h] BYREF
  int v39; // [rsp+70h] [rbp-98h] BYREF
  _DWORD v40[4]; // [rsp+78h] [rbp-90h] BYREF
  __m128i si128; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v42[16]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v43; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v44; // [rsp+C8h] [rbp-40h]
  int v45; // [rsp+D8h] [rbp-30h]
  EXCEPTION_RECORD pExceptionRecord; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v47; // [rsp+188h] [rbp+80h] BYREF
  __int128 v48; // [rsp+198h] [rbp+90h]
  _BYTE pExceptionObject[56]; // [rsp+1B0h] [rbp+A8h] BYREF
  void *retaddr; // [rsp+240h] [rbp+138h]

  LODWORD(v36) = a2;
  v12 = a6;
  v39 = a2;
  LODWORD(v38) = a3;
  LODWORD(v37) = a4;
  v40[0] = a6;
  v34 = a9;
  if ( (a8 & 1) != 0 && a6 == 17 )
  {
    std::string::string(&v47, "Unsupported texture options: Format::UInt8_RGBA cannot be used with BindToShader");
    v13 = std::string::string(
            &si128,
            "onecoreuap\\windows\\dwm\\spectre\\engine\\shared\\nativerendererd3d11\\cpp\\source\\textured3d11.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v13, v14, (unsigned int)&v47, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  v15 = a7;
  *((_QWORD *)&v48 + 1) = 0;
  LODWORD(v47) = a3;
  *(_QWORD *)((char *)&v47 + 4) = a4;
  HIDWORD(v47) = 1;
  LODWORD(v48) = anonymous_namespace_::GetD3DTextureFormat(a6, a8);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  DWORD1(v48) = si128.m128i_i32[v15];
  if ( (_DWORD)v15 == 2 || (_DWORD)v15 == 3 )
  {
    HIDWORD(v48) = 0x10000;
    if ( (_DWORD)v15 == 3 )
      HIDWORD(v48) = 196608;
  }
  if ( (a8 & 1) != 0 )
    DWORD2(v48) = 8;
  v43 = v47;
  v44 = v48;
  v45 = 0;
  DWORD2(v43) = a5;
  v16 = a8 & 0x20;
  if ( (a8 & 0x20) != 0 )
  {
    v17 = a4;
    if ( a3 >= a4 )
      v17 = a3;
    v18 = 0;
    while ( v17 > 1 )
    {
      v17 >>= 1;
      ++v18;
    }
    HIDWORD(v43) = v18 != -1;
    v45 = 1;
    DWORD2(v44) |= 0x20u;
    *(_BYTE *)(a1 + 208) = 1;
  }
  FormatSlicePitch_0 = Spectre::Engine::GetFormatSlicePitch_0(v12, a3, a4, &v39);
  if ( v16 )
    *(_QWORD *)(a1 + 200) = 4LL * *(_QWORD *)(a1 + 200) / 3uLL;
  Spectre::Engine::RendererResource::SetMemoryTrackingData(a1, *(_QWORD *)(a1 + 200), (a8 & 6) != 0 ? 3 : 11);
  v20 = (__int128 *)v42;
  v21 = v36;
  v22 = v34;
  do
  {
    *(_QWORD *)v20 = v22;
    *((_DWORD *)v20 + 2) = v21;
    *((_DWORD *)v20++ + 3) = FormatSlicePitch_0;
  }
  while ( v20 != &v43 );
  v35 = 0;
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(a1 + 72, &si128);
  v23 = si128;
  v24 = _mm_srli_si128(si128, 8).m128i_u64[0];
  Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(si128.m128i_i64[0], &v36);
  v25 = v36;
  v26 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int64, __int64 *))(*(_QWORD *)v36 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v27 = v34 != 0;
  v34 = -v34;
  v28 = v26(v25, &v43, (unsigned __int64)v42 & -(__int64)v27, &v35);
  v29 = v28;
  Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(
    (Spectre::Engine::D3D11::RenderDeviceD3D11 *)v23.m128i_i64[0],
    v28);
  if ( (v29 & 0x80000000) != 0LL )
  {
    memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
    pExceptionRecord.ExceptionCode = -532265403;
    pExceptionRecord.ExceptionAddress = retaddr;
    pExceptionRecord.NumberParameters = 1;
    pExceptionRecord.ExceptionInformation[0] = v29;
    RaiseFailFastException(&pExceptionRecord, 0, 0);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  if ( v24 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)_mm_srli_si128(v23, 8).m128i_i64[0]);
  std::make_unique<Spectre::Engine::TextureDesc,unsigned int &,unsigned int &,unsigned int &,enum Spectre::Engine::Format &,unsigned int &,enum Spectre::Engine::Usage &,0>(
    (unsigned int)&v34,
    (unsigned int)&v38,
    (unsigned int)&v37,
    (unsigned int)&a5,
    (__int64)v40,
    (__int64)&a8,
    (__int64)&a7);
  Spectre::Engine::D3D11::TextureD3D11::CreateResourceView3D(a1, (unsigned int)&v37, v35, a8, HIDWORD(v43));
  Microsoft::WRL::ComPtr<ID3D11RenderTargetView>::operator=(a1 + 176, &v35);
  Microsoft::WRL::ComPtr<ID3D11RenderTargetView>::operator=(a1 + 160, &v37);
  v30 = operator new(0x10u);
  if ( v30 )
  {
    v31 = HIDWORD(v43);
    v32 = v34;
    v34 = 0;
    *(_QWORD *)v30 = v32;
    v30[2] = v31;
    v30[3] = 1;
  }
  v38 = v30;
  std::unique_ptr<Spectre::Engine::DeviceTextureDesc>::operator=<std::default_delete<Spectre::Engine::DeviceTextureDesc>,0>(
    a1 + 112,
    &v38);
  std::unique_ptr<Spectre::Engine::DeviceTextureDesc>::~unique_ptr<Spectre::Engine::DeviceTextureDesc>(&v38);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(&v34);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
}

```

## disassembly

```asm
0x1800bd744  mov     rax, rsp
0x1800bd747  push    rbp
0x1800bd748  push    rbx
0x1800bd749  push    rsi
0x1800bd74a  push    rdi
0x1800bd74b  push    r13
0x1800bd74d  push    r15
0x1800bd74f  lea     rbp, [rax-138h]
0x1800bd756  sub     rsp, 208h
0x1800bd75d  movaps  xmmword ptr [rax-48h], xmm6
0x1800bd761  mov     rax, cs:__security_cookie
0x1800bd768  xor     rax, rsp
0x1800bd76b  mov     [rbp+130h+var_50], rax
0x1800bd772  mov     esi, r9d
0x1800bd775  mov     edi, r8d
0x1800bd778  mov     dword ptr [rsp+230h+var_1E0], edx
0x1800bd77c  mov     r15, rcx
0x1800bd77f  mov     r13d, [rbp+130h+arg_28]
0x1800bd786  mov     [rsp+230h+var_1C8], edx
0x1800bd78a  mov     dword ptr [rsp+230h+var_1D0], r8d
0x1800bd78f  mov     dword ptr [rsp+230h+var_1D8], r9d
0x1800bd794  mov     [rsp+230h+var_1C0], r13d
0x1800bd799  mov     rax, [rbp+130h+arg_40]
0x1800bd7a0  mov     [rsp+230h+var_1F0], rax
0x1800bd7a5  mov     eax, 1
0x1800bd7aa  test    byte ptr [rbp+130h+arg_38], al
0x1800bd7b0  jz      short loc_1800BD80B
0x1800bd7b2  cmp     r13d, 11h
0x1800bd7b6  jnz     short loc_1800BD80B
0x1800bd7b8  lea     rdx, aUnsupportedTex; "Unsupported texture options: Format::UI"...
0x1800bd7bf  lea     rcx, [rbp+130h+var_B0]
0x1800bd7c6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bd7cb  nop
0x1800bd7cc  lea     rdx, aOnecoreuapWind_37; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800bd7d3  lea     rcx, [rbp+130h+var_1B0]
0x1800bd7d7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800bd7dc  mov     byte ptr [rsp+230h+var_210], 0
0x1800bd7e1  lea     r9, [rbp+130h+var_B0]
0x1800bd7e8  mov     rdx, rax
0x1800bd7eb  lea     rcx, [rbp+130h+pExceptionObject]
0x1800bd7f2  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x1800bd7f7  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x1800bd7fe  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800bd805  call    _CxxThrowException_0
0x1800bd80b  mov     ebx, [rbp+130h+arg_30]
0x1800bd811  mov     dword ptr [rbp+130h+var_B0+8], 0
0x1800bd81b  mov     qword ptr [rbp+130h+var_A0+8], 0
0x1800bd826  mov     dword ptr [rbp+130h+var_B0], edi
0x1800bd82c  mov     dword ptr [rbp+130h+var_B0+4], esi
0x1800bd832  mov     dword ptr [rbp+130h+var_B0+0Ch], eax
0x1800bd838  mov     edx, [rbp+130h+arg_38]
0x1800bd83e  mov     ecx, r13d
0x1800bd841  call    _anonymous_namespace___GetD3DTextureFormat
0x1800bd846  mov     dword ptr [rbp+130h+var_A0], eax
0x1800bd84c  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x1800bd854  movdqu  [rbp+130h+var_1B0], xmm0
0x1800bd859  mov     ecx, dword ptr [rbp+rbx*4+130h+var_1B0]
0x1800bd85d  mov     dword ptr [rbp+130h+var_A0+4], ecx
0x1800bd863  cmp     ebx, 2
0x1800bd866  jz      short loc_1800BD86F
0x1800bd868  xor     eax, eax
0x1800bd86a  cmp     ebx, 3
0x1800bd86d  jnz     short loc_1800BD88A
0x1800bd86f  mov     dword ptr [rbp+130h+var_A0+0Ch], 10000h
0x1800bd879  xor     eax, eax
0x1800bd87b  cmp     ebx, 3
0x1800bd87e  jnz     short loc_1800BD88A
0x1800bd880  mov     dword ptr [rbp+130h+var_A0+0Ch], 30000h
0x1800bd88a  mov     edx, 1
0x1800bd88f  test    byte ptr [rbp+130h+arg_38], dl
0x1800bd895  jz      short loc_1800BD8A0
0x1800bd897  or      eax, 8
0x1800bd89a  mov     dword ptr [rbp+130h+var_A0+8], eax
0x1800bd8a0  movups  xmm0, [rbp+130h+var_B0]
0x1800bd8a7  movups  [rbp+130h+var_180], xmm0
0x1800bd8ab  movups  xmm1, [rbp+130h+var_A0]
0x1800bd8b2  movups  [rbp+130h+var_170], xmm1
0x1800bd8b6  xor     r9d, r9d
0x1800bd8b9  mov     [rbp+130h+var_160], r9d
0x1800bd8bd  mov     eax, [rbp+130h+arg_20]
0x1800bd8c3  mov     dword ptr [rbp+130h+var_180+8], eax
0x1800bd8c6  mov     ebx, [rbp+130h+arg_38]
0x1800bd8cc  and     ebx, 20h
0x1800bd8cf  jz      short loc_1800BD901
0x1800bd8d1  mov     eax, esi
0x1800bd8d3  cmp     edi, esi
0x1800bd8d5  cmovnb  eax, edi
0x1800bd8d8  xor     ecx, ecx
0x1800bd8da  jmp     short loc_1800BD8E0
0x1800bd8dc  shr     eax, 1
0x1800bd8de  add     ecx, edx
0x1800bd8e0  cmp     eax, edx
0x1800bd8e2  ja      short loc_1800BD8DC
0x1800bd8e4  lea     eax, [rcx+1]
0x1800bd8e7  cmp     eax, edx
0x1800bd8e9  cmovnb  eax, edx
0x1800bd8ec  mov     dword ptr [rbp+130h+var_180+0Ch], eax
0x1800bd8ef  or      r9d, edx
0x1800bd8f2  mov     [rbp+130h+var_160], r9d
0x1800bd8f6  or      dword ptr [rbp+130h+var_170+8], 20h
0x1800bd8fa  mov     [r15+0D0h], dl
0x1800bd901  lea     r9, [rsp+230h+var_1C8]
0x1800bd906  mov     r8d, esi
0x1800bd909  mov     edx, edi
0x1800bd90b  mov     ecx, r13d
0x1800bd90e  call    Spectre__Engine__GetFormatSlicePitch_0
0x1800bd913  mov     edi, eax
0x1800bd915  test    ebx, ebx
0x1800bd917  jz      short loc_1800BD93B
0x1800bd919  mov     rcx, [r15+0C8h]
0x1800bd920  shl     rcx, 2
0x1800bd924  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800bd92e  mul     rcx
0x1800bd931  shr     rdx, 1
0x1800bd934  mov     [r15+0C8h], rdx
0x1800bd93b  mov     ecx, [rbp+130h+arg_38]
0x1800bd941  and     cl, 6
0x1800bd944  neg     cl
0x1800bd946  sbb     r8d, r8d
0x1800bd949  and     r8d, 0FFFFFFF8h
0x1800bd94d  add     r8d, 0Bh
0x1800bd951  mov     rdx, [r15+0C8h]
0x1800bd958  mov     rcx, r15
0x1800bd95b  call    ?SetMemoryTrackingData@RendererResource@Engine@Spectre@@IEAAX_KW4Category@PerformanceManager@23@@Z; Spectre::Engine::RendererResource::SetMemoryTrackingData(unsigned __int64,Spectre::Engine::PerformanceManager::Category)
0x1800bd960  lea     rax, [rbp+130h+var_190]
0x1800bd964  mov     ecx, dword ptr [rsp+230h+var_1E0]
0x1800bd968  mov     rdx, [rsp+230h+var_1F0]
0x1800bd96d  mov     [rax], rdx
0x1800bd970  mov     [rax+8], ecx
0x1800bd973  mov     [rax+0Ch], edi
0x1800bd976  add     rax, 10h
0x1800bd97a  lea     r8, [rbp+130h+var_180]
0x1800bd97e  cmp     rax, r8
0x1800bd981  jnz     short loc_1800BD96D
0x1800bd983  mov     [rsp+230h+var_1E8], 0
0x1800bd98c  lea     rcx, [r15+48h]
0x1800bd990  lea     rdx, [rbp+130h+var_1B0]
0x1800bd994  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800bd999  movaps  xmm6, [rbp+130h+var_1B0]
0x1800bd99d  movaps  [rbp+130h+var_1B0], xmm6
0x1800bd9a1  movdqa  xmm0, xmm6
0x1800bd9a5  psrldq  xmm0, 8
0x1800bd9aa  movq    r13, xmm0
0x1800bd9af  lea     rdx, [rsp+230h+var_1E0]
0x1800bd9b4  movq    rcx, xmm6
0x1800bd9b9  call    ?GetDevice@RenderDeviceD3D11@D3D11@Engine@Spectre@@QEBA?AV?$ComPtr@UID3D11Device1@@@WRL@Microsoft@@XZ; Spectre::Engine::D3D11::RenderDeviceD3D11::GetDevice(void)
0x1800bd9be  nop
0x1800bd9bf  mov     rdi, [rsp+230h+var_1E0]
0x1800bd9c4  mov     rax, [rdi]
0x1800bd9c7  mov     rbx, [rax+30h]
0x1800bd9cb  lea     rcx, [rsp+230h+var_1E8]
0x1800bd9d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bd9d5  neg     [rsp+230h+var_1F0]
0x1800bd9da  sbb     r8, r8
0x1800bd9dd  lea     rax, [rbp+130h+var_190]
0x1800bd9e1  and     r8, rax
0x1800bd9e4  lea     r9, [rsp+230h+var_1E8]
0x1800bd9e9  lea     rdx, [rbp+130h+var_180]
0x1800bd9ed  mov     rcx, rdi
0x1800bd9f0  mov     rax, rbx
0x1800bd9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9f8  movsxd  rbx, eax
0x1800bd9fb  mov     edx, ebx; int
0x1800bd9fd  movq    rcx, xmm6; this
0x1800bda02  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800bda07  test    ebx, ebx
0x1800bda09  jns     short loc_1800BDA49
0x1800bda0b  xor     edx, edx; Val
0x1800bda0d  mov     r8d, 98h; Size
0x1800bda13  lea     rcx, [rbp+130h+pExceptionRecord]; void *
0x1800bda17  call    memset_0
0x1800bda1c  mov     [rbp+130h+pExceptionRecord.ExceptionCode], 0E0464645h
0x1800bda23  mov     rcx, [rbp+138h]
0x1800bda2a  mov     [rbp+130h+pExceptionRecord.ExceptionAddress], rcx
0x1800bda2e  mov     [rbp+130h+pExceptionRecord.NumberParameters], 1
0x1800bda35  mov     [rbp+130h+pExceptionRecord.ExceptionInformation], rbx
0x1800bda39  xor     r8d, r8d; dwFlags
0x1800bda3c  xor     edx, edx; pContextRecord
0x1800bda3e  lea     rcx, [rbp+130h+pExceptionRecord]; pExceptionRecord
0x1800bda42  call    cs:__imp_RaiseFailFastException
0x1800bda48  nop
0x1800bda49  lea     rcx, [rsp+230h+var_1E0]
0x1800bda4e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bda53  nop
0x1800bda54  test    r13, r13
0x1800bda57  jz      short loc_1800BDA68
0x1800bda59  psrldq  xmm6, 8
0x1800bda5e  movq    rcx, xmm6; this
0x1800bda63  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bda68  lea     rax, [rbp+130h+arg_30]
0x1800bda6f  mov     [rsp+30h], rax
0x1800bda74  lea     rax, [rbp+130h+arg_38]
0x1800bda7b  mov     [rsp+230h+var_208], rax
0x1800bda80  lea     rax, [rsp+230h+var_1C0]
0x1800bda85  mov     [rsp+230h+var_210], rax
0x1800bda8a  lea     r9, [rbp+130h+arg_20]
0x1800bda91  lea     r8, [rsp+230h+var_1D8]
0x1800bda96  lea     rdx, [rsp+230h+var_1D0]
0x1800bda9b  lea     rcx, [rsp+230h+var_1F0]
0x1800bdaa0  call    ??$make_unique@UTextureDesc@Engine@Spectre@@AEAIAEAIAEAIAEAW4Format@23@AEAIAEAW4Usage@23@$0A@@std@@YA?AV?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@0@AEAI00AEAW4Format@Engine@Spectre@@0AEAW4Usage@34@@Z; std::make_unique<Spectre::Engine::TextureDesc,uint &,uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &,0>(uint &,uint &,uint &,Spectre::Engine::Format &,uint &,Spectre::Engine::Usage &)
0x1800bdaa5  nop
0x1800bdaa6  mov     eax, dword ptr [rbp+130h+var_180+0Ch]
0x1800bdaa9  mov     dword ptr [rsp+230h+var_210], eax
0x1800bdaad  mov     r9d, [rbp+130h+arg_38]
0x1800bdab4  mov     r8, [rsp+230h+var_1E8]
0x1800bdab9  lea     rdx, [rsp+230h+var_1D8]
0x1800bdabe  mov     rcx, r15
0x1800bdac1  call    ?CreateResourceView3D@TextureD3D11@D3D11@Engine@Spectre@@IEBA?AV?$ComPtr@UID3D11ShaderResourceView@@@WRL@Microsoft@@AEAUID3D11Texture3D@@II@Z; Spectre::Engine::D3D11::TextureD3D11::CreateResourceView3D(ID3D11Texture3D &,uint,uint)
0x1800bdac6  lea     rcx, [r15+0B0h]
0x1800bdacd  lea     rdx, [rsp+230h+var_1E8]
0x1800bdad2  call    ??4?$ComPtr@UID3D11RenderTargetView@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ID3D11RenderTargetView>::operator=(Microsoft::WRL::ComPtr<ID3D11RenderTargetView> &&)
0x1800bdad7  lea     rcx, [r15+0A0h]
0x1800bdade  lea     rdx, [rsp+230h+var_1D8]
0x1800bdae3  call    ??4?$ComPtr@UID3D11RenderTargetView@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ID3D11RenderTargetView>::operator=(Microsoft::WRL::ComPtr<ID3D11RenderTargetView> &&)
0x1800bdae8  mov     ecx, 10h; unsigned __int64
0x1800bdaed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bdaf2  test    rax, rax
0x1800bdaf5  jz      short loc_1800BDB15
0x1800bdaf7  mov     edx, dword ptr [rbp+130h+var_180+0Ch]
0x1800bdafa  mov     rcx, [rsp+230h+var_1F0]
0x1800bdaff  mov     [rsp+230h+var_1F0], 0
0x1800bdb08  mov     [rax], rcx
0x1800bdb0b  mov     [rax+8], edx
0x1800bdb0e  mov     dword ptr [rax+0Ch], 1
0x1800bdb15  mov     [rsp+230h+var_1D0], rax
0x1800bdb1a  lea     rcx, [r15+70h]
0x1800bdb1e  lea     rdx, [rsp+230h+var_1D0]
0x1800bdb23  call    ??$?4U?$default_delete@UDeviceTextureDesc@Engine@Spectre@@@std@@$0A@@?$unique_ptr@UDeviceTextureDesc@Engine@Spectre@@U?$default_delete@UDeviceTextureDesc@Engine@Spectre@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Spectre::Engine::DeviceTextureDesc>::operator=<std::default_delete<Spectre::Engine::DeviceTextureDesc>,0>(std::unique_ptr<Spectre::Engine::DeviceTextureDesc> &&)
0x1800bdb28  lea     rcx, [rsp+230h+var_1D0]
0x1800bdb2d  call    ??1?$unique_ptr@UDeviceTextureDesc@Engine@Spectre@@U?$default_delete@UDeviceTextureDesc@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::DeviceTextureDesc>::~unique_ptr<Spectre::Engine::DeviceTextureDesc>(void)
0x1800bdb32  lea     rcx, [rsp+230h+var_1D8]
0x1800bdb37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bdb3c  nop
0x1800bdb3d  lea     rcx, [rsp+230h+var_1F0]
0x1800bdb42  call    ??1?$unique_ptr@UTextureDesc@Engine@Spectre@@U?$default_delete@UTextureDesc@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::unique_ptr<Spectre::Engine::TextureDesc>::~unique_ptr<Spectre::Engine::TextureDesc>(void)
0x1800bdb47  nop
0x1800bdb48  lea     rcx, [rsp+230h+var_1E8]
0x1800bdb4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bdb52  mov     rcx, [rbp+130h+var_50]
0x1800bdb59  xor     rcx, rsp; StackCookie
0x1800bdb5c  call    __security_check_cookie
0x1800bdb61  movaps  xmm6, [rsp+230h+var_48+8]
0x1800bdb69  add     rsp, 208h
0x1800bdb70  pop     r15
0x1800bdb72  pop     r13
0x1800bdb74  pop     rdi
0x1800bdb75  pop     rsi
0x1800bdb76  pop     rbx
0x1800bdb77  pop     rbp
0x1800bdb78  retn
```

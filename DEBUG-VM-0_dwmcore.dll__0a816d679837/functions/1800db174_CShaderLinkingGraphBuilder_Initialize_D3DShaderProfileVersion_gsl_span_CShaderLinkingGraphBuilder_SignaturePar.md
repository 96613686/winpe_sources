# CShaderLinkingGraphBuilder::Initialize(D3DShaderProfileVersion,gsl::span<CShaderLinkingGraphBuilder::SignatureParameter const,-1>)

- ea: `0x1800db174`
- end: `0x1800db507`
- name: `?Initialize@CShaderLinkingGraphBuilder@@QEAAJW4D3DShaderProfileVersion@@V?$span@$$CBUSignatureParameter@CShaderLinkingGraphBuilder@@$0?0@gsl@@@Z`
- size: `915`
- prototype: `__int64 __fastcall(struct ID3D11Linker **ppLinker)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800db79c`
- `0x180255680`

## callees

- `0x18002de54`
- `0x180042de0`
- `0x1800d57f0`
- `0x1800d5b30`
- `0x1800db174`
- `0x1800db510`
- `0x1800dc560`
- `0x1800dc734`
- `0x180228490`
- `0x180229430`
- `0x18025674c`
- `0x1802b6010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800db4c2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800db4c2`
- `D3DCOMPILER_47!D3DCreateLinker` at `0x1800db2d1`
- `D3DCOMPILER_47!D3DCreateLinker` at `0x1800db2d1`
- `D3DCOMPILER_47!D3DCreateFunctionLinkingGraph` at `0x1800db2fc`
- `D3DCOMPILER_47!D3DCreateFunctionLinkingGraph` at `0x1800db2fc`

## pseudocode

```c
__int64 __fastcall CShaderLinkingGraphBuilder::Initialize(struct ID3D11Linker **ppLinker, char a2, _QWORD *a3)
{
  __int64 v3; // rsi
  SIZE_T size_of; // rax
  void *v7; // rbx
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // rbx
  int v11; // ecx
  _OWORD *v12; // rdx
  __int128 v13; // xmm2
  __int128 v14; // xmm3
  __int64 v15; // xmm0_8
  HRESULT v16; // eax
  unsigned int v17; // edi
  struct ID3D11Linker **v18; // rbx
  HRESULT v19; // eax
  struct ID3D11Linker *v20; // rdi
  HRESULT (__stdcall *UseLibrary)(ID3D11Linker *, struct ID3D11ModuleInstance *); // rbx
  int v22; // eax
  unsigned int i; // r14d
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+59h] [rbp-A7h]
  char v33; // [rsp+5Dh] [rbp-A3h]
  __int16 v34; // [rsp+5Eh] [rbp-A2h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int128 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+78h] [rbp-88h]
  _BYTE v38[24]; // [rsp+88h] [rbp-78h]
  _OWORD v39[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h]
  _BYTE v41[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v42; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v43; // [rsp+F0h] [rbp-10h] BYREF
  char v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+F9h] [rbp-7h]
  char v46; // [rsp+FDh] [rbp-3h]

  v3 = 0;
  *((_BYTE *)ppLinker + 84) = a2;
  v29 = 0;
  *(_OWORD *)Src = 0;
  v27 = 0;
  if ( *a3 )
  {
    if ( *a3 > 0x492492492492492uLL )
      std::_Xlength_error("vector too long");
    size_of = std::_Get_size_of_n<56>(*a3);
    v7 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    memmove_0(v7, Src[0], (char *)Src[1] - (char *)Src[0]);
    std::vector<CShapeRenderTask>::_Change_array(Src, v7, 0, *a3);
  }
  v8 = a3[1];
  v9 = v8;
  v10 = v8 + 32LL * *a3;
  if ( v8 != v10 )
  {
    do
    {
      v11 = *(_DWORD *)(v9 + 28);
      v12 = Src[1];
      v36 = *(_OWORD *)(v9 + 8);
      LODWORD(v37) = *(_DWORD *)(v9 + 24);
      *(_OWORD *)&v38[8] = 0;
      *(_QWORD *)((char *)&v37 + 4) = (v11 != 1) | 0x100000000LL;
      HIDWORD(v37) = v11;
      v13 = v37;
      *(_QWORD *)v38 = 0x100000000LL;
      v14 = *(_OWORD *)v38;
      v15 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v38[8], *(__m128d *)&v38[8]);
      v39[1] = v37;
      v39[0] = v36;
      v39[2] = *(_OWORD *)v38;
      v40 = v15;
      if ( Src[1] == v29 )
      {
        std::vector<_D3D11_PARAMETER_DESC>::_Emplace_reallocate<_D3D11_PARAMETER_DESC const &>(Src, Src[1], v39);
      }
      else
      {
        *(_OWORD *)Src[1] = v36;
        v12[1] = v13;
        v12[2] = v14;
        *((_QWORD *)v12 + 6) = v15;
        Src[1] = (char *)Src[1] + 56;
      }
      v9 += 32;
    }
    while ( v9 != v10 );
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppLinker);
  v16 = D3DCreateLinker(ppLinker);
  v17 = v16;
  if ( v16 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v16, 0x45u, 0);
  }
  else
  {
    v18 = ppLinker + 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppLinker + 1);
    v19 = D3DCreateFunctionLinkingGraph(0, (struct ID3D11FunctionLinkingGraph **)ppLinker + 1);
    v17 = v19;
    if ( v19 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v19, 0x46u, 0);
    }
    else
    {
      v20 = *v18;
      UseLibrary = (*v18)->lpVtbl->UseLibrary;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      v22 = ((__int64 (__fastcall *)(struct ID3D11Linker *, void *, __int64, __int64 *))UseLibrary)(
              v20,
              Src[0],
              0x6DB6DB6DB6DB6DB7LL * (((char *)Src[1] - (char *)Src[0]) >> 3),
              &v27);
      v17 = v22;
      if ( v22 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v22, 0x4Au, 0);
      }
      else
      {
        for ( i = 0; i < *(_DWORD *)a3; v3 = 0 )
        {
          v24 = v27;
          v30 = 0;
          v35 = 0;
          v32 = 0;
          v33 = 0;
          v34 = 0;
          if ( v27 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
            v30 = v24;
            v3 = v24;
          }
          v31 = i;
          if ( (unsigned __int64)i >= *a3 )
          {
            ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
            __debugbreak();
          }
          v43 = v3;
          v42 = *(_WORD *)(32LL * i + v8);
          if ( v3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
          v45 = v35;
          v46 = v35;
          v44 = i;
          std::_Hash<std::_Umap_traits<enum ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node,std::_Uhash_compare<enum ShaderLinkingArgument,std::hash<enum ShaderLinkingArgument>,std::equal_to<enum ShaderLinkingArgument>>,std::allocator<std::pair<enum ShaderLinkingArgument const,CShaderLinkingGraphBuilder::Node>>,0>>::emplace<std::pair<enum ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node>>(
            ppLinker + 2,
            v41,
            &v42);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          ++i;
        }
      }
    }
  }
  v25 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( Src[0] )
    std::_Deallocate<16>(Src[0], 8 * ((signed __int64)((__int64)v29 - (unsigned __int64)Src[0]) >> 3));
  return v17;
}

```

## disassembly

```asm
0x1800db174  mov     [rsp-8+arg_8], rbx
0x1800db179  push    rbp
0x1800db17a  push    rsi
0x1800db17b  push    rdi
0x1800db17c  push    r12
0x1800db17e  push    r13
0x1800db180  push    r14
0x1800db182  push    r15
0x1800db184  lea     rbp, [rsp-10h]
0x1800db189  sub     rsp, 110h
0x1800db190  mov     rax, cs:__security_cookie
0x1800db197  xor     rax, rsp
0x1800db19a  mov     [rbp+40h+var_40], rax
0x1800db19e  xor     esi, esi
0x1800db1a0  mov     [rcx+54h], dl
0x1800db1a3  xorps   xmm0, xmm0
0x1800db1a6  mov     r12, r8
0x1800db1a9  mov     r15, rcx
0x1800db1ac  mov     [rsp+140h+var_F8], rsi
0x1800db1b1  movdqu  xmmword ptr [rsp+140h+Src], xmm0
0x1800db1b7  mov     [rsp+140h+var_110], rsi
0x1800db1bc  cmp     [r8], rsi
0x1800db1bf  jbe     short loc_1800DB210
0x1800db1c1  mov     rax, 492492492492492h
0x1800db1cb  cmp     [r8], rax
0x1800db1ce  ja      loc_1800DB4BB
0x1800db1d4  mov     rcx, [r8]
0x1800db1d7  call    ??$_Get_size_of_n@$0DI@@std@@YA_K_K@Z; std::_Get_size_of_n<56>(unsigned __int64)
0x1800db1dc  mov     rcx, rax; dwBytes
0x1800db1df  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800db1e4  mov     rdx, [rsp+140h+Src]; Src
0x1800db1e9  mov     rcx, rax; void *
0x1800db1ec  mov     r8, [rsp+140h+Src+8]
0x1800db1f1  mov     rbx, rax
0x1800db1f4  sub     r8, rdx; Size
0x1800db1f7  call    memmove_0
0x1800db1fc  mov     r9, [r12]
0x1800db200  lea     rcx, [rsp+140h+Src]
0x1800db205  xor     r8d, r8d
0x1800db208  mov     rdx, rbx
0x1800db20b  call    ?_Change_array@?$vector@VCShapeRenderTask@@V?$allocator@VCShapeRenderTask@@@std@@@std@@AEAAXQEAVCShapeRenderTask@@_K1@Z; std::vector<CShapeRenderTask>::_Change_array(CShapeRenderTask * const,unsigned __int64,unsigned __int64)
0x1800db210  mov     r13, [r12+8]
0x1800db215  mov     rbx, [r12]
0x1800db219  mov     rdi, r13
0x1800db21c  shl     rbx, 5
0x1800db220  add     rbx, r13
0x1800db223  cmp     r13, rbx
0x1800db226  jz      loc_1800DB2C6
0x1800db22c  mov     rax, [rdi+8]
0x1800db230  xorps   xmm0, xmm0
0x1800db233  mov     ecx, [rdi+1Ch]
0x1800db236  cmp     ecx, 1
0x1800db239  mov     rdx, [rsp+140h+Src+8]
0x1800db23e  mov     qword ptr [rsp+140h+var_D8], rax
0x1800db243  mov     rax, [rdi+10h]
0x1800db247  mov     qword ptr [rsp+140h+var_D8+8], rax
0x1800db24c  mov     eax, [rdi+18h]
0x1800db24f  movups  xmm1, [rsp+140h+var_D8]
0x1800db254  mov     dword ptr [rsp+140h+var_C8], eax
0x1800db258  mov     eax, esi
0x1800db25a  setnz   al
0x1800db25d  mov     dword ptr [rbp+40h+var_C8+8], 1
0x1800db264  movdqu  xmmword ptr [rbp+40h+var_B8+8], xmm0
0x1800db269  mov     dword ptr [rsp+140h+var_C8+4], eax
0x1800db26d  mov     dword ptr [rbp+40h+var_C8+0Ch], ecx
0x1800db270  movups  xmm2, [rsp+140h+var_C8]
0x1800db275  mov     dword ptr [rbp+40h+var_B8], esi
0x1800db278  mov     dword ptr [rbp+40h+var_B8+4], 1
0x1800db27f  movups  xmm3, xmmword ptr [rbp+40h+var_B8]
0x1800db283  unpckhpd xmm0, xmm0
0x1800db287  movups  [rbp+40h+var_90], xmm2
0x1800db28b  movups  [rbp+40h+var_A0], xmm1
0x1800db28f  movups  [rbp+40h+var_80], xmm3
0x1800db293  movsd   [rbp+40h+var_70], xmm0
0x1800db298  cmp     rdx, [rsp+140h+var_F8]
0x1800db29d  jz      loc_1800DB4C9
0x1800db2a3  movups  xmmword ptr [rdx], xmm1
0x1800db2a6  movups  xmmword ptr [rdx+10h], xmm2
0x1800db2aa  movups  xmmword ptr [rdx+20h], xmm3
0x1800db2ae  movsd   qword ptr [rdx+30h], xmm0
0x1800db2b3  add     [rsp+140h+Src+8], 38h ; '8'
0x1800db2b9  add     rdi, 20h ; ' '
0x1800db2bd  cmp     rdi, rbx
0x1800db2c0  jnz     loc_1800DB22C
0x1800db2c6  mov     rcx, r15
0x1800db2c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db2ce  mov     rcx, r15; ppLinker
0x1800db2d1  call    cs:__imp_D3DCreateLinker
0x1800db2d7  mov     edi, eax
0x1800db2d9  mov     r14, 6DB6DB6DB6DB6DB7h
0x1800db2e3  test    eax, eax
0x1800db2e5  js      loc_1800DB499
0x1800db2eb  lea     rbx, [r15+8]
0x1800db2ef  mov     rcx, rbx
0x1800db2f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db2f7  mov     rdx, rbx; ppFunctionLinkingGraph
0x1800db2fa  xor     ecx, ecx; uFlags
0x1800db2fc  call    cs:__imp_D3DCreateFunctionLinkingGraph
0x1800db302  mov     edi, eax
0x1800db304  test    eax, eax
0x1800db306  js      loc_1800DB4F8
0x1800db30c  mov     rdi, [rbx]
0x1800db30f  lea     rcx, [rsp+140h+var_110]
0x1800db314  mov     rax, [rdi]
0x1800db317  mov     rbx, [rax+20h]
0x1800db31b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db320  mov     rdx, [rsp+140h+Src]
0x1800db325  lea     r9, [rsp+140h+var_110]
0x1800db32a  mov     r8, [rsp+140h+Src+8]
0x1800db32f  mov     rcx, rdi
0x1800db332  sub     r8, rdx
0x1800db335  mov     rax, rbx
0x1800db338  sar     r8, 3
0x1800db33c  imul    r8, r14
0x1800db340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db345  mov     edi, eax
0x1800db347  test    eax, eax
0x1800db349  js      loc_1800DB4E9
0x1800db34f  mov     r14d, esi
0x1800db352  cmp     [r12], esi
0x1800db356  jbe     loc_1800DB428
0x1800db35c  mov     rbx, [rsp+140h+var_110]
0x1800db361  xor     eax, eax
0x1800db363  mov     [rsp+140h+var_F0], rsi
0x1800db368  mov     [rsp+140h+var_E0], rax
0x1800db36d  mov     [rsp+140h+var_E7], eax
0x1800db371  mov     [rsp+140h+var_E3], al
0x1800db375  mov     [rsp+140h+var_E2], ax
0x1800db37a  cmp     rsi, rbx
0x1800db37d  jz      short loc_1800DB3AF
0x1800db37f  test    rbx, rbx
0x1800db382  jz      short loc_1800DB393
0x1800db384  mov     rax, [rbx]
0x1800db387  mov     rcx, rbx
0x1800db38a  mov     rax, [rax+8]
0x1800db38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db393  mov     rcx, rsi
0x1800db396  mov     [rsp+140h+var_F0], rbx
0x1800db39b  mov     rsi, rbx
0x1800db39e  test    rcx, rcx
0x1800db3a1  jz      short loc_1800DB3AF
0x1800db3a3  mov     rax, [rcx]
0x1800db3a6  mov     rax, [rax+10h]
0x1800db3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db3af  mov     eax, r14d
0x1800db3b2  mov     [rsp+140h+var_E8], r14b
0x1800db3b7  cmp     rax, [r12]
0x1800db3bb  jnb     loc_1800DB4DC
0x1800db3c1  shl     rax, 5
0x1800db3c5  mov     [rbp+40h+var_50], rsi
0x1800db3c9  movzx   eax, word ptr [rax+r13]
0x1800db3ce  mov     [rbp+40h+var_58], ax
0x1800db3d2  test    rsi, rsi
0x1800db3d5  jz      short loc_1800DB3E6
0x1800db3d7  mov     rax, [rsi]
0x1800db3da  mov     rcx, rsi
0x1800db3dd  mov     rax, [rax+8]
0x1800db3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db3e6  mov     rax, [rsp+140h+var_E0]
0x1800db3eb  lea     r8, [rbp+40h+var_58]
0x1800db3ef  lea     rdx, [rbp+40h+var_68]
0x1800db3f3  mov     [rbp+40h+var_47], eax
0x1800db3f6  lea     rcx, [r15+10h]
0x1800db3fa  mov     [rbp+40h+var_43], al
0x1800db3fd  mov     [rbp+40h+var_48], r14b
0x1800db401  call    ??$emplace@U?$pair@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@?$_Hash@V?$_Umap_traits@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@V?$_Uhash_compare@W4ShaderLinkingArgument@@U?$hash@W4ShaderLinkingArgument@@@std@@U?$equal_to@W4ShaderLinkingArgument@@@3@@std@@V?$allocator@U?$pair@$$CBW4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@1@@Z; std::_Hash<std::_Umap_traits<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node,std::_Uhash_compare<ShaderLinkingArgument,std::hash<ShaderLinkingArgument>,std::equal_to<ShaderLinkingArgument>>,std::allocator<std::pair<ShaderLinkingArgument const,CShaderLinkingGraphBuilder::Node>>,0>>::emplace<std::pair<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node>>(std::pair<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node> &&)
0x1800db406  lea     rcx, [rbp+40h+var_50]
0x1800db40a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db40f  lea     rcx, [rsp+140h+var_F0]
0x1800db414  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800db419  inc     r14d
0x1800db41c  xor     esi, esi
0x1800db41e  cmp     r14d, [r12]
0x1800db422  jb      loc_1800DB35C
0x1800db428  mov     r14, 6DB6DB6DB6DB6DB7h
0x1800db432  mov     rcx, [rsp+140h+var_110]
0x1800db437  test    rcx, rcx
0x1800db43a  jz      short loc_1800DB44D
0x1800db43c  mov     [rsp+140h+var_110], rsi
0x1800db441  mov     rax, [rcx]
0x1800db444  mov     rax, [rax+10h]
0x1800db448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db44d  mov     rcx, [rsp+140h+Src]
0x1800db452  test    rcx, rcx
0x1800db455  jz      short loc_1800DB470
0x1800db457  mov     rax, [rsp+140h+var_F8]
0x1800db45c  sub     rax, rcx
0x1800db45f  sar     rax, 3
0x1800db463  imul    rax, r14
0x1800db467  imul    rdx, rax, 38h ; '8'
0x1800db46b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800db470  mov     eax, edi
0x1800db472  mov     rcx, [rbp+40h+var_40]
0x1800db476  xor     rcx, rsp; StackCookie
0x1800db479  call    __security_check_cookie
0x1800db47e  mov     rbx, [rsp+140h+arg_8]
0x1800db486  add     rsp, 110h
0x1800db48d  pop     r15
0x1800db48f  pop     r14
0x1800db491  pop     r13
0x1800db493  pop     r12
0x1800db495  pop     rdi
0x1800db496  pop     rsi
0x1800db497  pop     rbp
0x1800db498  retn
0x1800db499  mov     [rsp+140h+var_118], rsi; void *
0x1800db49e  mov     [rsp+140h+var_120], 45h ; 'E'; unsigned int
0x1800db4a6  xor     edx, edx; int *
0x1800db4a8  mov     r9d, eax; int
0x1800db4ab  xor     r8d, r8d; unsigned int
0x1800db4ae  lea     ecx, [rdx+14h]; unsigned int
0x1800db4b1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800db4b6  jmp     loc_1800DB432
0x1800db4bb  lea     rcx, aVectorTooLong; "vector too long"
0x1800db4c2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800db4c9  lea     r8, [rbp+40h+var_A0]
0x1800db4cd  lea     rcx, [rsp+140h+Src]
0x1800db4d2  call    ??$_Emplace_reallocate@AEBU_D3D11_PARAMETER_DESC@@@?$vector@U_D3D11_PARAMETER_DESC@@V?$allocator@U_D3D11_PARAMETER_DESC@@@std@@@std@@AEAAPEAU_D3D11_PARAMETER_DESC@@QEAU2@AEBU2@@Z; std::vector<_D3D11_PARAMETER_DESC>::_Emplace_reallocate<_D3D11_PARAMETER_DESC const &>(_D3D11_PARAMETER_DESC * const,_D3D11_PARAMETER_DESC const &)
0x1800db4d7  jmp     loc_1800DB2B9
0x1800db4dc  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1800db4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db4e8  int     3; Trap to Debugger
0x1800db4e9  mov     [rsp+140h+var_118], rsi
0x1800db4ee  mov     [rsp+140h+var_120], 4Ah ; 'J'
0x1800db4f6  jmp     short loc_1800DB4A6
0x1800db4f8  mov     [rsp+140h+var_118], rsi
0x1800db4fd  mov     [rsp+140h+var_120], 46h ; 'F'
0x1800db505  jmp     short loc_1800DB4A6
```

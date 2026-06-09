# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::DequantizeEmbeddingIfQuantized(std::shared_ptr<asg::SemanticPipelines::IModelEmbedding>)

- ea: `0x180008cf0`
- end: `0x180009218`
- name: `?DequantizeEmbeddingIfQuantized@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AV?$shared_ptr@UIModelEmbedding@SemanticPipelines@asg@@@std@@V89@@Z`
- size: `1320`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009220`
- `0x180009820`

## callees

- `0x180003df0`
- `0x180006e30`
- `0x180007ba0`
- `0x180008180`
- `0x180008cf0`
- `0x18000b7d0`
- `0x18000d230`
- `0x180078ed0`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180242120`
- `0x180242860`

## string_xrefs

- `0x180008ef1`: `C:\__w\1\s\src\VectorSpaceRegistry\internal\libSemanticRegistryTypes\include\SemanticRegistryTypes\RegistryBaseTypes.h`
- `0x180008efd`: `void __cdecl asg::SemanticRegistry::DequantizeLinear(class std::span<unsigned char const ,-1>,class std::span<float,-1>,float,float)`
- `0x180009185`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\EmbeddingHelpers.cpp`
- `0x1800091cf`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\EmbeddingHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::DequantizeEmbeddingIfQuantized(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v5; // rbx
  int v6; // eax
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int64 v11; // rbx
  size_t v12; // rbx
  _QWORD *v13; // r12
  char *v14; // rbx
  float *v15; // r15
  unsigned __int64 v16; // rsi
  __int64 v17; // rdi
  unsigned __int8 *v18; // rbx
  unsigned __int64 v19; // r8
  float v20; // xmm1_4
  float v21; // xmm2_4
  int v22; // ecx
  float *v23; // rdx
  volatile signed __int32 *v24; // r15
  __int64 v25; // rax
  __int64 v26; // xmm6_8
  int v27; // edi
  int v28; // ebx
  __int128 v29; // xmm1
  _QWORD *v30; // rax
  volatile signed __int32 *v31; // rbx
  volatile signed __int32 *v32; // rbx
  _QWORD pExceptionObject[3]; // [rsp+30h] [rbp-91h] BYREF
  const char *v34; // [rsp+48h] [rbp-79h]
  __int128 v35; // [rsp+58h] [rbp-69h] BYREF
  char *v36; // [rsp+68h] [rbp-59h]
  __int128 v37; // [rsp+70h] [rbp-51h] BYREF
  __int128 v38; // [rsp+88h] [rbp-39h] BYREF
  const char *v39; // [rsp+98h] [rbp-29h]
  __int64 v40; // [rsp+A8h] [rbp-19h] BYREF
  int v41; // [rsp+B0h] [rbp-11h]
  volatile signed __int32 *v42; // [rsp+C0h] [rbp-1h]
  volatile signed __int32 *v43; // [rsp+C8h] [rbp+7h]
  char *v44; // [rsp+138h] [rbp+77h]
  const char *v45; // [rsp+140h] [rbp+7Fh]

  if ( !*a2 )
  {
    LODWORD(v35) = 195;
    *((_QWORD *)&v35 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\EmbeddingHelpers.cpp";
    v36 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)&v38, L"quantizedEmbedding");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)&pExceptionObject[1],
      (const struct winrt::param::hstring *)&v38,
      (const struct winrt::impl::slim_source_location *)&v35);
    throw (winrt::hresult_invalid_argument *)&pExceptionObject[1];
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 48LL))(*a2) )
  {
    if ( !*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 56LL))(*a2) + 8) )
    {
      LODWORD(v35) = 203;
      *((_QWORD *)&v35 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\EmbeddingHelpers.cpp";
      v36 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)&v38,
        L"Can't dequantize embedding without quantization parameters");
      winrt::hresult_invalid_argument::hresult_invalid_argument(
        (winrt::hresult_invalid_argument *)&pExceptionObject[1],
        (const struct winrt::param::hstring *)&v38,
        (const struct winrt::impl::slim_source_location *)&v35);
      throw (winrt::hresult_invalid_argument *)&pExceptionObject[1];
    }
    v5 = *a2;
    v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    if ( v6 )
    {
      if ( v6 == 1 )
        v7 = 4;
      else
        v7 = 0;
    }
    else
    {
      v7 = 1;
    }
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    v11 = v8 / v7;
    v35 = 0;
    v45 = 0;
    v36 = 0;
    if ( v8 / v7 )
    {
      if ( v11 > 0x3FFFFFFFFFFFFFFFLL )
        std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
          v9,
          v8 % v7,
          v10);
      _mm_lfence();
      v12 = 4 * v11;
      v13 = std::_Allocate<16,std::_Default_allocate_traits>(v12);
      *(_QWORD *)&v35 = v13;
      v45 = (char *)v13 + v12;
      v36 = (char *)v13 + v12;
      memset(v13, 0, v12);
      v14 = (char *)v13 + v12;
      *((_QWORD *)&v35 + 1) = v14;
    }
    else
    {
      v14 = (char *)*((_QWORD *)&v35 + 1);
      v13 = (_QWORD *)v35;
    }
    v44 = v14;
    v15 = (float *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 56LL))(*a2);
    v16 = (v14 - (char *)v13) >> 2;
    v17 = *a2;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17) )
    {
      pExceptionObject[1] = 0xD00000060LL;
      pExceptionObject[2] = "C:\\__w\\1\\s\\src\\SemanticPipelines\\internal\\libSemanticPipelines\\include\\SemanticPipe"
                            "lines\\ModelEmbedding.h";
      v34 = "class std::span<unsigned char const ,-1> __cdecl asg::SemanticPipelines::IModelEmbedding::AsSpan<unsigned char>(void) const";
      v38 = *(_OWORD *)&pExceptionObject[1];
      v39 = "class std::span<unsigned char const ,-1> __cdecl asg::SemanticPipelines::IModelEmbedding::AsSpan<unsigned char>(void) const";
      asg::details::AsgAssertFail(&v38);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v18 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v20 = v15[1];
    v21 = *v15;
    pExceptionObject[1] = 0xE000000A5LL;
    pExceptionObject[2] = "C:\\__w\\1\\s\\src\\VectorSpaceRegistry\\internal\\libSemanticRegistryTypes\\include\\Semantic"
                          "RegistryTypes\\RegistryBaseTypes.h";
    v34 = "void __cdecl asg::SemanticRegistry::DequantizeLinear(class std::span<unsigned char const ,-1>,class std::span<"
          "float,-1>,float,float)";
    if ( v16 < v19 )
    {
      v38 = *(_OWORD *)&pExceptionObject[1];
      v39 = v34;
      asg::details::AsgAssertFail(&v38);
    }
    v22 = 0;
    if ( v19 )
    {
      v23 = (float *)v13;
      do
      {
        *v23 = (float)((float)*v18 - v20) * v21;
        ++v22;
        ++v18;
        ++v23;
      }
      while ( v22 < v19 );
    }
    v24 = (volatile signed __int32 *)operator new(0x30u);
    *(_QWORD *)&v37 = v24;
    *(_OWORD *)v24 = 0;
    *((_DWORD *)v24 + 2) = 1;
    *((_DWORD *)v24 + 3) = 1;
    *(_QWORD *)v24 = &std::_Ref_count_obj2<asg::SemanticPipelines::VectorData<float>>::`vftable';
    v36 = 0;
    v35 = 0u;
    pExceptionObject[1] = v13;
    pExceptionObject[2] = v44;
    v34 = v45;
    asg::SemanticPipelines::VectorData<float>::VectorData<float>(v24 + 4, &pExceptionObject[1]);
    v42 = v24 + 4;
    v43 = v24;
    v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 56LL))(*a2);
    v26 = *(_QWORD *)v25;
    v27 = *(_DWORD *)(v25 + 8);
    v28 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 40LL))(*a2);
    v29 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 32LL))(*a2);
    v37 = 0;
    _InterlockedIncrement(v24 + 2);
    *(_QWORD *)&v37 = v24 + 4;
    *((_QWORD *)&v37 + 1) = v24;
    v40 = v26;
    v41 = v27;
    v38 = v29;
    v30 = (_QWORD *)asg::SemanticPipelines::ModelEmbedding::Create(
                      (unsigned int)&pExceptionObject[1],
                      (unsigned int)&v37,
                      (unsigned int)&v38,
                      v28,
                      1,
                      (__int64)&v40);
    *a1 = *v30;
    a1[1] = v30[1];
    *v30 = 0;
    v30[1] = 0;
    v31 = (volatile signed __int32 *)pExceptionObject[2];
    if ( pExceptionObject[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
    v32 = (volatile signed __int32 *)a2[1];
    if ( v32 )
    {
      if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
  }
  else
  {
    *a1 = *a2;
    a1[1] = a2[1];
    *a2 = 0;
    a2[1] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180008cf0  mov     rax, rsp
0x180008cf3  mov     [rax+8], rbx
0x180008cf7  mov     [rax+10h], rdx
0x180008cfb  push    rbp
0x180008cfc  push    rsi
0x180008cfd  push    rdi
0x180008cfe  push    r12
0x180008d00  push    r13
0x180008d02  push    r14
0x180008d04  push    r15
0x180008d06  lea     rbp, [rax-5Fh]
0x180008d0a  sub     rsp, 0E0h
0x180008d11  movaps  xmmword ptr [rax-48h], xmm6
0x180008d15  mov     r14, rdx
0x180008d18  mov     r13, rcx
0x180008d1b  xor     esi, esi
0x180008d1d  mov     rcx, [rdx]
0x180008d20  test    rcx, rcx
0x180008d23  jz      loc_18000917E
0x180008d29  mov     rax, [rcx]
0x180008d2c  mov     rax, [rax+30h]
0x180008d30  call    cs:__guard_dispatch_icall_fptr
0x180008d36  test    al, al
0x180008d38  jnz     short loc_180008D76
0x180008d3a  mov     rax, [r14]
0x180008d3d  mov     [r13+0], rax
0x180008d41  mov     rax, [r14+8]
0x180008d45  mov     [r13+8], rax
0x180008d49  mov     [r14], rsi
0x180008d4c  mov     [r14+8], rsi
0x180008d50  mov     rax, r13
0x180008d53  mov     rbx, [rsp+110h+arg_0]
0x180008d5b  movaps  xmm6, [rsp+110h+var_48+8]
0x180008d63  add     rsp, 0E0h
0x180008d6a  pop     r15
0x180008d6c  pop     r14
0x180008d6e  pop     r13
0x180008d70  pop     r12
0x180008d72  pop     rdi
0x180008d73  pop     rsi
0x180008d74  pop     rbp
0x180008d75  retn
0x180008d76  mov     rcx, [r14]
0x180008d79  mov     rax, [rcx]
0x180008d7c  mov     rax, [rax+38h]
0x180008d80  call    cs:__guard_dispatch_icall_fptr
0x180008d86  cmp     byte ptr [rax+8], 0
0x180008d8a  jz      loc_1800091C8
0x180008d90  mov     rbx, [r14]
0x180008d93  mov     rax, [rbx]
0x180008d96  mov     rcx, rbx
0x180008d99  mov     rax, [rax+10h]
0x180008d9d  call    cs:__guard_dispatch_icall_fptr
0x180008da3  test    eax, eax
0x180008da5  jz      short loc_180008DB8
0x180008da7  cmp     eax, 1
0x180008daa  jz      short loc_180008DB1
0x180008dac  mov     rdi, rsi
0x180008daf  jmp     short loc_180008DBD
0x180008db1  mov     edi, 4
0x180008db6  jmp     short loc_180008DBD
0x180008db8  mov     edi, 1
0x180008dbd  mov     rax, [rbx]
0x180008dc0  mov     rcx, rbx
0x180008dc3  mov     rax, [rax+8]
0x180008dc7  call    cs:__guard_dispatch_icall_fptr
0x180008dcd  xor     edx, edx
0x180008dcf  div     rdi
0x180008dd2  mov     rbx, rax
0x180008dd5  xorps   xmm0, xmm0
0x180008dd8  movdqu  [rbp+57h+var_C0], xmm0
0x180008ddd  mov     rax, rsi
0x180008de0  mov     [rbp+57h+arg_18], rax
0x180008de4  mov     [rbp+57h+var_B0], rax
0x180008de8  test    rbx, rbx
0x180008deb  jz      short loc_180008E3C
0x180008ded  mov     rax, 3FFFFFFFFFFFFFFFh
0x180008df7  cmp     rbx, rax
0x180008dfa  ja      loc_180009212
0x180008e00  lfence
0x180008e03  lea     rbx, ds:0[rbx*4]
0x180008e0b  mov     rcx, rbx
0x180008e0e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008e13  mov     r12, rax
0x180008e16  mov     qword ptr [rbp+57h+var_C0], rax
0x180008e1a  lea     rsi, [rbx+rax]
0x180008e1e  mov     [rbp+57h+arg_18], rsi
0x180008e22  mov     [rbp+57h+var_B0], rsi
0x180008e26  mov     r8, rbx; Size
0x180008e29  xor     edx, edx; Val
0x180008e2b  mov     rcx, rax; void *
0x180008e2e  call    memset
0x180008e33  mov     rbx, rsi
0x180008e36  mov     qword ptr [rbp+57h+var_C0+8], rbx
0x180008e3a  jmp     short loc_180008E44
0x180008e3c  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x180008e40  mov     r12, qword ptr [rbp+57h+var_C0]
0x180008e44  mov     [rbp+57h+arg_10], rbx
0x180008e48  mov     rcx, [r14]
0x180008e4b  mov     rax, [rcx]
0x180008e4e  mov     rax, [rax+38h]
0x180008e52  call    cs:__guard_dispatch_icall_fptr
0x180008e58  mov     r15, rax
0x180008e5b  mov     rsi, rbx
0x180008e5e  sub     rsi, r12
0x180008e61  sar     rsi, 2
0x180008e65  mov     rdi, [r14]
0x180008e68  mov     rcx, [rdi]
0x180008e6b  mov     rax, [rcx+10h]
0x180008e6f  mov     rcx, rdi
0x180008e72  call    cs:__guard_dispatch_icall_fptr
0x180008e78  mov     rcx, [rdi]
0x180008e7b  mov     rax, [rcx+10h]
0x180008e7f  mov     rcx, rdi
0x180008e82  call    cs:__guard_dispatch_icall_fptr
0x180008e88  test    eax, eax
0x180008e8a  jnz     loc_18000911D
0x180008e90  mov     rax, [rdi]
0x180008e93  mov     rcx, rdi
0x180008e96  mov     rax, [rax+10h]
0x180008e9a  call    cs:__guard_dispatch_icall_fptr
0x180008ea0  mov     rax, [rdi]
0x180008ea3  mov     rcx, rdi
0x180008ea6  mov     rax, [rax+8]
0x180008eaa  call    cs:__guard_dispatch_icall_fptr
0x180008eb0  mov     rax, [rdi]
0x180008eb3  mov     rcx, rdi
0x180008eb6  mov     rax, [rax+18h]
0x180008eba  call    cs:__guard_dispatch_icall_fptr
0x180008ec0  mov     rbx, rax
0x180008ec3  mov     rdx, [rdi]
0x180008ec6  mov     rcx, rdi
0x180008ec9  mov     rax, [rdx+8]
0x180008ecd  call    cs:__guard_dispatch_icall_fptr
0x180008ed3  mov     r8, rax
0x180008ed6  movss   xmm1, dword ptr [r15+4]
0x180008edc  movss   xmm2, dword ptr [r15]
0x180008ee1  mov     dword ptr [rsp+110h+pExceptionObject+8], 0A5h
0x180008ee9  mov     dword ptr [rsp+110h+pExceptionObject+0Ch], 0Eh
0x180008ef1  lea     rax, aCW1SSrcVectors; "C:\\__w\\1\\s\\src\\VectorSpaceRegistry"...
0x180008ef8  mov     qword ptr [rsp+110h+pExceptionObject+10h], rax
0x180008efd  lea     rdx, aVoidCdeclAsgSe_1; "void __cdecl asg::SemanticRegistry::Deq"...
0x180008f04  mov     [rbp+57h+var_D0], rdx
0x180008f08  cmp     rsi, r8
0x180008f0b  jb      loc_180009161
0x180008f11  xor     edi, edi
0x180008f13  mov     ecx, edi
0x180008f15  test    r8, r8
0x180008f18  jz      short loc_180008F47
0x180008f1a  mov     rdx, r12
0x180008f1d  nop     dword ptr [rax]
0x180008f20  movzx   eax, byte ptr [rbx]
0x180008f23  movd    xmm0, eax
0x180008f27  cvtdq2ps xmm0, xmm0
0x180008f2a  subss   xmm0, xmm1
0x180008f2e  mulss   xmm0, xmm2
0x180008f32  movss   dword ptr [rdx], xmm0
0x180008f36  inc     ecx
0x180008f38  inc     rbx
0x180008f3b  add     rdx, 4
0x180008f3f  movsxd  rax, ecx
0x180008f42  cmp     rax, r8
0x180008f45  jb      short loc_180008F20
0x180008f47  mov     ecx, 30h ; '0'; Size
0x180008f4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008f51  mov     r15, rax
0x180008f54  mov     qword ptr [rbp+57h+var_A8], rax
0x180008f58  xorps   xmm0, xmm0
0x180008f5b  movups  xmmword ptr [rax], xmm0
0x180008f5e  mov     dword ptr [rax+8], 1
0x180008f65  mov     dword ptr [rax+0Ch], 1
0x180008f6c  lea     rax, ??_7?$_Ref_count_obj2@V?$VectorData@M@SemanticPipelines@asg@@@std@@6B@; const std::_Ref_count_obj2<asg::SemanticPipelines::VectorData<float>>::`vftable'
0x180008f73  mov     [r15], rax
0x180008f76  lea     rsi, [r15+10h]
0x180008f7a  mov     [rbp+57h+var_B0], rdi
0x180008f7e  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x180008f82  mov     qword ptr [rbp+57h+var_C0], rdi
0x180008f86  mov     qword ptr [rsp+110h+pExceptionObject+8], r12
0x180008f8b  mov     rax, [rbp+57h+arg_10]
0x180008f8f  mov     qword ptr [rsp+110h+pExceptionObject+10h], rax
0x180008f94  mov     rax, [rbp+57h+arg_18]
0x180008f98  mov     [rbp+57h+var_D0], rax
0x180008f9c  lea     rdx, [rsp+110h+pExceptionObject+8]
0x180008fa1  mov     rcx, rsi
0x180008fa4  call    ??0?$VectorData@M@SemanticPipelines@asg@@QEAA@V?$vector@MV?$allocator@M@std@@@std@@@Z; asg::SemanticPipelines::VectorData<float>::VectorData<float>(std::vector<float>)
0x180008fa9  nop
0x180008faa  mov     [rbp+57h+var_58], rsi
0x180008fae  mov     [rbp+57h+var_50], r15
0x180008fb2  mov     rcx, [r14]
0x180008fb5  mov     rax, [rcx]
0x180008fb8  mov     rax, [rax+38h]
0x180008fbc  call    cs:__guard_dispatch_icall_fptr
0x180008fc2  movsd   xmm6, qword ptr [rax]
0x180008fc6  mov     edi, [rax+8]
0x180008fc9  mov     rcx, [r14]
0x180008fcc  mov     rax, [rcx]
0x180008fcf  mov     rax, [rax+28h]
0x180008fd3  call    cs:__guard_dispatch_icall_fptr
0x180008fd9  mov     ebx, eax
0x180008fdb  mov     rcx, [r14]
0x180008fde  mov     rdx, [rcx]
0x180008fe1  mov     rax, [rdx+20h]
0x180008fe5  call    cs:__guard_dispatch_icall_fptr
0x180008feb  movups  xmm1, xmmword ptr [rax]
0x180008fee  xorps   xmm0, xmm0
0x180008ff1  movdqu  [rbp+57h+var_A8], xmm0
0x180008ff6  lock inc dword ptr [r15+8]
0x180008ffb  mov     qword ptr [rbp+57h+var_A8], rsi
0x180008fff  mov     qword ptr [rbp+57h+var_A8+8], r15
0x180009003  movsd   [rbp+57h+var_70], xmm6
0x180009008  mov     [rbp+57h+var_68], edi
0x18000900b  movaps  [rbp+57h+var_90], xmm1
0x18000900f  lea     rax, [rbp+57h+var_70]
0x180009013  mov     qword ptr [rsp+110h+pExceptionObject], rax
0x180009018  mov     dword ptr [rsp+110h+var_F0], 1
0x180009020  mov     r9d, ebx
0x180009023  lea     r8, [rbp+57h+var_90]
0x180009027  lea     rdx, [rbp+57h+var_A8]
0x18000902b  lea     rcx, [rsp+110h+pExceptionObject+8]
0x180009030  call    ?Create@ModelEmbedding@SemanticPipelines@asg@@SA?AV?$shared_ptr@VModelEmbedding@SemanticPipelines@asg@@@std@@V?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@5@UGuid@3@W4SemanticContentType@SemanticRegistry@3@W4EmbeddingElementType@93@V?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@5@@Z; asg::SemanticPipelines::ModelEmbedding::Create(std::shared_ptr<asg::SemanticRegistry::IVectorData const>,asg::Guid,asg::SemanticRegistry::SemanticContentType,asg::SemanticRegistry::EmbeddingElementType,std::optional<asg::SemanticRegistry::EmbeddingQuantizationParameters>)
0x180009035  mov     rcx, [rax]
0x180009038  mov     [r13+0], rcx
0x18000903c  mov     rcx, [rax+8]
0x180009040  mov     [r13+8], rcx
0x180009044  xor     ecx, ecx
0x180009046  mov     [rax], rcx
0x180009049  mov     [rax+8], rcx
0x18000904d  mov     edi, 0FFFFFFFFh
0x180009052  mov     rbx, qword ptr [rsp+110h+pExceptionObject+10h]
0x180009057  test    rbx, rbx
0x18000905a  jz      short loc_180009094
0x18000905c  mov     eax, edi
0x18000905e  lock xadd [rbx+8], eax
0x180009063  cmp     eax, 1
0x180009066  jnz     short loc_180009094
0x180009068  mov     rax, [rbx]
0x18000906b  mov     rcx, rbx
0x18000906e  mov     rax, [rax]
0x180009071  call    cs:__guard_dispatch_icall_fptr
0x180009077  mov     eax, edi
0x180009079  lock xadd [rbx+0Ch], eax
0x18000907e  cmp     eax, 1
0x180009081  jnz     short loc_180009094
0x180009083  mov     rax, [rbx]
0x180009086  mov     rcx, rbx
0x180009089  mov     rax, [rax+8]
0x18000908d  call    cs:__guard_dispatch_icall_fptr
0x180009093  nop
0x180009094  mov     eax, edi
0x180009096  lock xadd [r15+8], eax
0x18000909c  cmp     eax, 1
0x18000909f  jnz     short loc_1800090CE
0x1800090a1  mov     rax, [r15]
0x1800090a4  mov     rcx, r15
0x1800090a7  mov     rax, [rax]
0x1800090aa  call    cs:__guard_dispatch_icall_fptr
0x1800090b0  mov     eax, edi
0x1800090b2  lock xadd [r15+0Ch], eax
0x1800090b8  cmp     eax, 1
0x1800090bb  jnz     short loc_1800090CE
0x1800090bd  mov     rax, [r15]
0x1800090c0  mov     rcx, r15
0x1800090c3  mov     rax, [rax+8]
0x1800090c7  call    cs:__guard_dispatch_icall_fptr
0x1800090cd  nop
0x1800090ce  mov     rbx, [r14+8]
0x1800090d2  test    rbx, rbx
0x1800090d5  jz      loc_180008D50
0x1800090db  mov     eax, edi
0x1800090dd  lock xadd [rbx+8], eax
0x1800090e2  cmp     eax, 1
0x1800090e5  jnz     loc_180008D50
0x1800090eb  mov     rax, [rbx]
0x1800090ee  mov     rcx, rbx
0x1800090f1  mov     rax, [rax]
0x1800090f4  call    cs:__guard_dispatch_icall_fptr
0x1800090fa  lock xadd [rbx+0Ch], edi
0x1800090ff  cmp     edi, 1
0x180009102  jnz     loc_180008D50
0x180009108  mov     rax, [rbx]
0x18000910b  mov     rcx, rbx
0x18000910e  mov     rax, [rax+8]
0x180009112  call    cs:__guard_dispatch_icall_fptr
0x180009118  jmp     loc_180008D50
0x18000911d  mov     dword ptr [rsp+110h+pExceptionObject+8], 60h ; '`'
0x180009125  mov     dword ptr [rsp+110h+pExceptionObject+0Ch], 0Dh
0x18000912d  lea     rax, aCW1SSrcSemanti_8; "C:\\__w\\1\\s\\src\\SemanticPipelines\\"...
0x180009134  mov     qword ptr [rsp+110h+pExceptionObject+10h], rax
0x180009139  lea     rdx, aClassStdSpanUn; "class std::span<unsigned char const ,-1"...
0x180009140  mov     [rbp+57h+var_D0], rdx
0x180009144  movaps  xmm0, xmmword ptr [rsp+110h+pExceptionObject+8]
0x180009149  movaps  [rbp+57h+var_90], xmm0
0x18000914d  movsd   xmm1, [rbp+57h+var_D0]
0x180009152  movsd   [rbp+57h+var_80], xmm1
0x180009157  lea     rcx, [rbp+57h+var_90]
0x18000915b  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x180009161  movaps  xmm0, xmmword ptr [rsp+110h+pExceptionObject+8]
0x180009166  movaps  [rbp+57h+var_90], xmm0
0x18000916a  movsd   xmm1, [rbp+57h+var_D0]
0x18000916f  movsd   [rbp+57h+var_80], xmm1
  ... truncated ...
```

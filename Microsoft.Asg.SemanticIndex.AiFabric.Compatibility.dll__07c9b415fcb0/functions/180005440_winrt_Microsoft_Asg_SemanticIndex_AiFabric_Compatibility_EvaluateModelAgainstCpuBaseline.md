# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EvaluateModelAgainstCpuBaseline

- ea: `0x180005440`
- end: `0x180005cb5`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EvaluateModelAgainstCpuBaseline`
- size: `2165`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005d50`

## callees

- `0x180004140`
- `0x180004640`
- `0x180004a80`
- `0x180005440`
- `0x180005fe0`
- `0x180006470`
- `0x180006670`
- `0x180006e30`
- `0x180007ba0`
- `0x180078ed0`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206ec0`
- `0x180242120`
- `0x180242860`

## string_xrefs

- `0x180005c72`: `C:\__w\1\s\src\VectorSpaceRegistry\internal\libSemanticRegistryTypes\include\SemanticRegistryTypes\RegistryBaseTypes.h`
- `0x180005c7d`: `void __cdecl asg::SemanticRegistry::DequantizeLinear(class std::span<unsigned char const ,-1>,class std::span<float,-1>,float,float)`
- `0x180005c92`: `Model descriptor has no quantization parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__m128 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::EvaluateModelAgainstCpuBaseline(
        asg::SemanticRegistry::ModelDescriptor *a1,
        __int64 *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // r12
  __int64 *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 *v10; // rax
  volatile signed __int32 *v11; // rdi
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  __int64 v13; // rcx
  void (__fastcall ***v14)(_QWORD, __int64); // r8
  void (__fastcall *v15)(__int64, __int64 *, __int64, void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int, _DWORD); // r10
  volatile signed __int32 *v16; // rdx
  _QWORD *v17; // rax
  char v18; // al
  __int64 v19; // r9
  __int64 v20; // rax
  __int64 v21; // rcx
  void (__fastcall ***v22)(_QWORD, __int64); // r8
  void (__fastcall *v23)(_QWORD, __int64 *, __int64 *, __int64, _DWORD); // r11
  __int64 v24; // rcx
  _QWORD *v25; // rax
  volatile signed __int32 *v26; // rbx
  __int64 v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // rax
  double v30; // xmm0_8
  __m128 v31; // xmm6
  __m128 v32; // xmm6
  volatile signed __int32 *v33; // rbx
  __int64 v35; // rax
  __int64 v36; // rcx
  void (__fastcall ***v37)(_QWORD, __int64); // r8
  void (__fastcall *v38)(_QWORD, __int64 *, __int64 *, _QWORD, _DWORD); // r11
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r8
  volatile signed __int32 *v43; // rbx
  __int64 v44; // rax
  volatile signed __int32 *v45; // rbx
  __int64 v46; // rdx
  signed __int32 v47; // eax
  signed __int32 v48; // ett
  int v49; // edi
  char *v50; // rdi
  char *v51; // r13
  _QWORD *v52; // r14
  __int64 v53; // rbx
  unsigned __int64 v54; // r12
  unsigned __int8 *v55; // r8
  int v56; // ecx
  float *v57; // rdx
  float v58; // xmm1_4
  float v59; // xmm2_4
  double v60; // xmm0_8
  __m128 v61; // xmm6
  char *v62; // rax
  volatile signed __int32 *v63; // rbx
  void (__fastcall ***v64)(_QWORD, __int64 *, __int64 *, __int64, _DWORD); // [rsp+40h] [rbp-99h] BYREF
  volatile signed __int32 *v65; // [rsp+48h] [rbp-91h]
  __int128 pExceptionObject; // [rsp+50h] [rbp-89h] BYREF
  char *v67; // [rsp+60h] [rbp-79h]
  __int64 v68; // [rsp+70h] [rbp-69h] BYREF
  const char *v69; // [rsp+78h] [rbp-61h]
  const char *v70; // [rsp+80h] [rbp-59h]
  __int64 v71; // [rsp+90h] [rbp-49h] BYREF
  volatile signed __int32 *v72; // [rsp+98h] [rbp-41h]
  __int64 v73; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v74; // [rsp+A8h] [rbp-31h]
  _QWORD *v75; // [rsp+B0h] [rbp-29h]
  __int64 v76; // [rsp+B8h] [rbp-21h]
  __int64 v77; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v78; // [rsp+C8h] [rbp-11h]
  __int64 v79; // [rsp+D8h] [rbp-1h]
  volatile signed __int32 *v80; // [rsp+E0h] [rbp+7h]
  __int64 v81; // [rsp+140h] [rbp+67h]
  __int64 v82; // [rsp+150h] [rbp+77h]
  unsigned __int64 v83; // [rsp+158h] [rbp+7Fh]

  v82 = *((_QWORD *)a1 + 16);
  v6 = asg::SemanticRegistry::ModelDescriptor::Dimension(a1);
  v83 = v6;
  if ( v6 != (__int64)(a3[5] - a3[4]) >> 2 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)&pExceptionObject,
      "Baseline content embedding size does not match model dimension");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  v7 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a2 + 8))(a2, &v68);
  v9 = *v7;
  *v7 = 0;
  v71 = v9;
  LOBYTE(v72) = 1;
  if ( !v9 || *(_BYTE *)(v9 + 200) )
    std::_Throw_future_error2(4);
  LOBYTE(v8) = 1;
  v10 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 16LL))(v9, v8);
  v81 = *v10;
  v79 = *v10;
  v11 = (volatile signed __int32 *)v10[1];
  v80 = v11;
  *v10 = 0;
  v10[1] = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
  {
    v12 = *(void (__fastcall ****)(_QWORD, __int64))(v9 + 216);
    if ( v12 )
      (**v12)(v12, v9);
    else
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  }
  v13 = v68;
  if ( v68 && _InterlockedExchangeAdd((volatile signed __int32 *)(v68 + 8), 0xFFFFFFFF) == 1 )
  {
    v14 = *(void (__fastcall ****)(_QWORD, __int64))(v13 + 216);
    if ( v14 )
      (**v14)(*(_QWORD *)(v13 + 216), v13);
    else
      (**(void (__fastcall ***)(__int64, __int64))v13)(v13, 1);
  }
  v15 = *(void (__fastcall **)(__int64, __int64 *, __int64, void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD), int, _DWORD))(*(_QWORD *)v81 + 8LL);
  v16 = (volatile signed __int32 *)a3[2];
  v17 = a3;
  if ( a3[3] > 7u )
    v17 = (_QWORD *)*a3;
  v64 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *, __int64, _DWORD))v17;
  v65 = v16;
  v15(v81, &v77, v82, (void (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD))&v64, 1, 0);
  v79 = 0;
  v80 = 0;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 16))(a2, 1);
  v19 = *a2;
  if ( v18 )
  {
    LOBYTE(v69) = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))v19)(a2, &pExceptionObject, &v68);
    std::future<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>>::get(v20, &v64);
    v21 = pExceptionObject;
    if ( (_QWORD)pExceptionObject
      && _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject + 8), 0xFFFFFFFF) == 1 )
    {
      v22 = *(void (__fastcall ****)(_QWORD, __int64))(v21 + 216);
      if ( v22 )
        (**v22)(*(_QWORD *)(v21 + 216), v21);
      else
        (**(void (__fastcall ***)(__int64, __int64))v21)(v21, 1);
    }
    v23 = **v64;
    v24 = a3[2];
    v25 = a3;
    if ( a3[3] > 7u )
      v25 = (_QWORD *)*a3;
    v73 = v77;
    v74 = (v78 - v77) / 24;
    v75 = v25;
    v76 = v24;
    v23(v64, &v71, &v73, 1, 0);
    v64 = 0;
    v26 = v65;
    v65 = 0;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    v27 = a3[4];
    v28 = v71;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
    v30 = asg::SemanticIndex::DistanceFunctionHelpers::CosineDistance<float>(v6, v29, v27);
    v31 = (__m128)(unsigned __int64)a3[7];
    *(double *)v31.m128_u64 = *(double *)v31.m128_u64 - (2.0 - v30) * 0.5;
    v32 = _mm_and_ps(v31, (__m128)_xmm);
    v33 = v72;
    if ( v72 )
    {
      if ( _InterlockedExchangeAdd(v72 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    goto LABEL_35;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64 *, _QWORD))(v19 + 16))(a2, 0) )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)&pExceptionObject,
      "Unsupported embedding element type");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  LOBYTE(v69) = 0;
  v35 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))*a2)(a2, &pExceptionObject, &v68);
  std::future<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>>::get(v35, &v64);
  v36 = pExceptionObject;
  if ( (_QWORD)pExceptionObject
    && _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject + 8), 0xFFFFFFFF) == 1 )
  {
    v37 = *(void (__fastcall ****)(_QWORD, __int64))(v36 + 216);
    if ( v37 )
      (**v37)(*(_QWORD *)(v36 + 216), v36);
    else
      (**(void (__fastcall ***)(__int64, __int64))v36)(v36, 1);
  }
  v38 = **v64;
  v39 = a3[2];
  v40 = a3;
  if ( a3[3] > 7u )
    v40 = (_QWORD *)*a3;
  v73 = v77;
  v74 = (v78 - v77) / 24;
  v75 = v40;
  v76 = v39;
  v38(v64, &v71, &v73, 0, 0);
  v64 = 0;
  v43 = v65;
  v65 = 0;
  if ( v43 )
  {
    if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
      if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
    }
  }
  v44 = 0;
  v45 = 0;
  v46 = *((_QWORD *)a1 + 3);
  if ( !v46 )
    goto LABEL_54;
  v47 = *(_DWORD *)(v46 + 8);
  if ( v47 )
  {
    while ( 1 )
    {
      v41 = (unsigned int)(v47 + 1);
      v48 = v47;
      v47 = _InterlockedCompareExchange((volatile signed __int32 *)(v46 + 8), v41, v47);
      if ( v48 == v47 )
        break;
      if ( !v47 )
        goto LABEL_52;
    }
    v44 = *((_QWORD *)a1 + 2);
    v45 = (volatile signed __int32 *)*((_QWORD *)a1 + 3);
LABEL_54:
    v68 = *(_QWORD *)(v44 + 108);
    v49 = *(_DWORD *)(v44 + 116);
    if ( v45 )
    {
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    goto LABEL_58;
  }
LABEL_52:
  v68 = MEMORY[0x6C];
  LOBYTE(v49) = MEMORY[0x74];
LABEL_58:
  if ( !(_BYTE)v49 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)&pExceptionObject,
      "Model descriptor has no quantization parameters");
    throw (std::invalid_argument *)&pExceptionObject;
  }
  pExceptionObject = 0;
  v50 = 0;
  v67 = 0;
  v51 = 0;
  if ( v6 )
  {
    if ( v6 > 0x3FFFFFFFFFFFFFFFLL )
      std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
        v41,
        v46,
        v42);
    _mm_lfence();
    v52 = std::_Allocate<16,std::_Default_allocate_traits>(4 * v6);
    *(_QWORD *)&pExceptionObject = v52;
    v50 = (char *)v52 + 4 * v6;
    v67 = v50;
    memset(v52, 0, 4 * v6);
    *((_QWORD *)&pExceptionObject + 1) = v50;
    v51 = v50;
  }
  else
  {
    v52 = (_QWORD *)pExceptionObject;
  }
  v53 = v71;
  v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 8LL))(v53);
  v55 = (unsigned __int8 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 24LL))(v53);
  if ( (v51 - (char *)v52) >> 2 < v54 )
  {
    v68 = 0xE000000A5LL;
    v69 = "C:\\__w\\1\\s\\src\\VectorSpaceRegistry\\internal\\libSemanticRegistryTypes\\include\\SemanticRegistryTypes\\R"
          "egistryBaseTypes.h";
    v70 = "void __cdecl asg::SemanticRegistry::DequantizeLinear(class std::span<unsigned char const ,-1>,class std::span<"
          "float,-1>,float,float)";
    asg::details::AsgAssertFail(&v68);
  }
  v56 = 0;
  if ( v54 )
  {
    v57 = (float *)v52;
    v58 = *((float *)&v68 + 1);
    v59 = *(float *)&v68;
    do
    {
      *v57 = (float)((float)*v55 - v58) * v59;
      ++v56;
      ++v55;
      ++v57;
    }
    while ( v56 < v54 );
  }
  v60 = asg::SemanticIndex::DistanceFunctionHelpers::CosineDistance<float>(v83, v52, a3[4]);
  v61 = (__m128)(unsigned __int64)a3[7];
  *(double *)v61.m128_u64 = *(double *)v61.m128_u64 - (2.0 - v60) * 0.5;
  v32 = _mm_and_ps(v61, (__m128)_xmm);
  if ( v52 )
  {
    v62 = (char *)v52;
    if ( ((v50 - (char *)v52) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
    {
      _mm_lfence();
      v52 = (_QWORD *)*(v52 - 1);
      if ( (unsigned __int64)(v62 - (char *)v52 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v52);
  }
  v63 = v72;
  if ( v72 )
  {
    if ( _InterlockedExchangeAdd(v72 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
      if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
    }
  }
LABEL_35:
  std::vector<asg::SemanticRegistry::TokenText>::_Tidy(&v77);
  return v32;
}

```

## disassembly

```asm
0x180005440  mov     [rsp-8+arg_8], rbx
0x180005445  push    rbp
0x180005446  push    rsi
0x180005447  push    rdi
0x180005448  push    r12
0x18000544a  push    r13
0x18000544c  push    r14
0x18000544e  push    r15
0x180005450  lea     rbp, [rsp-27h]
0x180005455  sub     rsp, 100h
0x18000545c  movaps  [rsp+130h+var_40], xmm6
0x180005464  mov     r15, r8
0x180005467  mov     r14, rdx
0x18000546a  mov     r13, rcx
0x18000546d  xor     esi, esi
0x18000546f  mov     rax, [rcx+80h]
0x180005476  mov     [rbp+57h+arg_10], rax
0x18000547a  call    ?Dimension@ModelDescriptor@SemanticRegistry@asg@@QEBA_KXZ; asg::SemanticRegistry::ModelDescriptor::Dimension(void)
0x18000547f  mov     r12, rax
0x180005482  mov     [rbp+57h+arg_18], rax
0x180005486  mov     r8, [r15+28h]
0x18000548a  sub     r8, [r15+20h]
0x18000548e  sar     r8, 2
0x180005492  cmp     rax, r8
0x180005495  jnz     loc_180005C22
0x18000549b  mov     rax, [r14]
0x18000549e  lea     rdx, [rbp+57h+var_C0]
0x1800054a2  mov     rcx, r14
0x1800054a5  mov     rax, [rax+8]
0x1800054a9  call    cs:__guard_dispatch_icall_fptr
0x1800054af  nop
0x1800054b0  mov     rbx, [rax]
0x1800054b3  mov     [rax], rsi
0x1800054b6  mov     [rbp+57h+var_A0], rbx
0x1800054ba  mov     byte ptr [rbp+57h+var_98], 1
0x1800054be  test    rbx, rbx
0x1800054c1  jz      loc_180005C17
0x1800054c7  cmp     [rbx+0C8h], sil
0x1800054ce  jnz     loc_180005C17
0x1800054d4  mov     rax, [rbx]
0x1800054d7  mov     dl, 1
0x1800054d9  mov     rcx, rbx
0x1800054dc  mov     rax, [rax+10h]
0x1800054e0  call    cs:__guard_dispatch_icall_fptr
0x1800054e6  mov     rcx, [rax]
0x1800054e9  mov     [rbp+57h+arg_0], rcx
0x1800054ed  mov     [rbp+57h+var_58], rcx
0x1800054f1  mov     rdi, [rax+8]
0x1800054f5  mov     [rbp+57h+var_50], rdi
0x1800054f9  mov     [rax], rsi
0x1800054fc  mov     [rax+8], rsi
0x180005500  mov     esi, 0FFFFFFFFh
0x180005505  mov     eax, esi
0x180005507  lock xadd [rbx+8], eax
0x18000550c  cmp     eax, 1
0x18000550f  jnz     short loc_180005543
0x180005511  mov     rcx, [rbx+0D8h]
0x180005518  test    rcx, rcx
0x18000551b  jz      short loc_18000552E
0x18000551d  mov     rax, [rcx]
0x180005520  mov     rdx, rbx
0x180005523  mov     rax, [rax]
0x180005526  call    cs:__guard_dispatch_icall_fptr
0x18000552c  jmp     short loc_180005543
0x18000552e  mov     rax, [rbx]
0x180005531  mov     edx, 1
0x180005536  mov     rcx, rbx
0x180005539  mov     rax, [rax]
0x18000553c  call    cs:__guard_dispatch_icall_fptr
0x180005542  nop
0x180005543  mov     rcx, [rbp+57h+var_C0]
0x180005547  test    rcx, rcx
0x18000554a  jz      short loc_180005589
0x18000554c  mov     eax, esi
0x18000554e  lock xadd [rcx+8], eax
0x180005553  cmp     eax, 1
0x180005556  jnz     short loc_180005589
0x180005558  mov     r8, [rcx+0D8h]
0x18000555f  test    r8, r8
0x180005562  jz      short loc_180005578
0x180005564  mov     rax, [r8]
0x180005567  mov     rdx, rcx
0x18000556a  mov     rcx, r8
0x18000556d  mov     rax, [rax]
0x180005570  call    cs:__guard_dispatch_icall_fptr
0x180005576  jmp     short loc_180005589
0x180005578  mov     rax, [rcx]
0x18000557b  mov     edx, 1
0x180005580  mov     rax, [rax]
0x180005583  call    cs:__guard_dispatch_icall_fptr
0x180005589  mov     rcx, [rbp+57h+arg_0]
0x18000558d  mov     rax, [rcx]
0x180005590  mov     r10, [rax+8]
0x180005594  mov     rdx, [r15+10h]
0x180005598  mov     rax, r15
0x18000559b  cmp     qword ptr [r15+18h], 7
0x1800055a0  jbe     short loc_1800055A5
0x1800055a2  mov     rax, [r15]
0x1800055a5  mov     [rsp+130h+var_F0], rax
0x1800055aa  mov     [rsp+130h+var_E8], rdx
0x1800055af  xor     ebx, ebx
0x1800055b1  mov     [rsp+130h+var_108], ebx
0x1800055b5  mov     dword ptr [rsp+130h+Reserved], 1
0x1800055bd  lea     r9, [rsp+130h+var_F0]
0x1800055c2  mov     r8, [rbp+57h+arg_10]
0x1800055c6  lea     rdx, [rbp+57h+var_70]
0x1800055ca  mov     rax, r10
0x1800055cd  call    cs:__guard_dispatch_icall_fptr
0x1800055d3  nop
0x1800055d4  mov     [rbp+57h+var_58], rbx
0x1800055d8  mov     [rbp+57h+var_50], rbx
0x1800055dc  test    rdi, rdi
0x1800055df  jz      short loc_180005618
0x1800055e1  mov     eax, esi
0x1800055e3  lock xadd [rdi+8], eax
0x1800055e8  cmp     eax, 1
0x1800055eb  jnz     short loc_180005618
0x1800055ed  mov     rax, [rdi]
0x1800055f0  mov     rcx, rdi
0x1800055f3  mov     rax, [rax]
0x1800055f6  call    cs:__guard_dispatch_icall_fptr
0x1800055fc  mov     eax, esi
0x1800055fe  lock xadd [rdi+0Ch], eax
0x180005603  cmp     eax, 1
0x180005606  jnz     short loc_180005618
0x180005608  mov     rax, [rdi]
0x18000560b  mov     rcx, rdi
0x18000560e  mov     rax, [rax+8]
0x180005612  call    cs:__guard_dispatch_icall_fptr
0x180005618  mov     rax, [r14]
0x18000561b  mov     edx, 1
0x180005620  mov     rcx, r14
0x180005623  mov     rax, [rax+10h]
0x180005627  call    cs:__guard_dispatch_icall_fptr
0x18000562d  mov     r9, [r14]
0x180005630  mov     rcx, r14
0x180005633  test    al, al
0x180005635  jz      loc_180005854
0x18000563b  mov     byte ptr [rbp+57h+var_B8], 0
0x18000563f  lea     r8, [rbp+57h+var_C0]
0x180005643  lea     rdx, [rsp+130h+pExceptionObject]
0x180005648  mov     rax, [r9]
0x18000564b  call    cs:__guard_dispatch_icall_fptr
0x180005651  nop
0x180005652  lea     rdx, [rsp+130h+var_F0]
0x180005657  mov     rcx, rax
0x18000565a  call    ?get@?$future@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA?AV?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@2@XZ; std::future<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>>::get(void)
0x18000565f  nop
0x180005660  mov     rcx, qword ptr [rsp+130h+pExceptionObject]
0x180005665  test    rcx, rcx
0x180005668  jz      short loc_1800056A7
0x18000566a  mov     eax, esi
0x18000566c  lock xadd [rcx+8], eax
0x180005671  cmp     eax, 1
0x180005674  jnz     short loc_1800056A7
0x180005676  mov     r8, [rcx+0D8h]
0x18000567d  test    r8, r8
0x180005680  jz      short loc_180005696
0x180005682  mov     rax, [r8]
0x180005685  mov     rdx, rcx
0x180005688  mov     rcx, r8
0x18000568b  mov     rax, [rax]
0x18000568e  call    cs:__guard_dispatch_icall_fptr
0x180005694  jmp     short loc_1800056A7
0x180005696  mov     rax, [rcx]
0x180005699  mov     edx, 1
0x18000569e  mov     rax, [rax]
0x1800056a1  call    cs:__guard_dispatch_icall_fptr
0x1800056a7  mov     r10, [rsp+130h+var_F0]
0x1800056ac  mov     rax, [r10]
0x1800056af  mov     r11, [rax]
0x1800056b2  mov     rcx, [rbp+57h+var_68]
0x1800056b6  mov     r8, [rbp+57h+var_70]
0x1800056ba  sub     rcx, r8
0x1800056bd  mov     rax, 2AAAAAAAAAAAAAABh
0x1800056c7  imul    rcx
0x1800056ca  sar     rdx, 2
0x1800056ce  mov     rax, rdx
0x1800056d1  shr     rax, 3Fh
0x1800056d5  add     rdx, rax
0x1800056d8  mov     rcx, [r15+10h]
0x1800056dc  mov     rax, r15
0x1800056df  cmp     qword ptr [r15+18h], 7
0x1800056e4  jbe     short loc_1800056E9
0x1800056e6  mov     rax, [r15]
0x1800056e9  mov     [rbp+57h+var_90], r8
0x1800056ed  mov     [rbp+57h+var_88], rdx
0x1800056f1  mov     [rbp+57h+var_80], rax
0x1800056f5  mov     [rbp+57h+var_78], rcx
0x1800056f9  mov     dword ptr [rsp+130h+Reserved], ebx
0x1800056fd  mov     r9d, 1
0x180005703  lea     r8, [rbp+57h+var_90]
0x180005707  lea     rdx, [rbp+57h+var_A0]
0x18000570b  mov     rcx, r10
0x18000570e  mov     rax, r11
0x180005711  call    cs:__guard_dispatch_icall_fptr
0x180005717  nop
0x180005718  mov     [rsp+130h+var_F0], rbx
0x18000571d  mov     rbx, [rsp+130h+var_E8]
0x180005722  mov     [rsp+130h+var_E8], 0
0x18000572b  test    rbx, rbx
0x18000572e  jz      short loc_180005767
0x180005730  mov     eax, esi
0x180005732  lock xadd [rbx+8], eax
0x180005737  cmp     eax, 1
0x18000573a  jnz     short loc_180005767
0x18000573c  mov     rax, [rbx]
0x18000573f  mov     rcx, rbx
0x180005742  mov     rax, [rax]
0x180005745  call    cs:__guard_dispatch_icall_fptr
0x18000574b  mov     eax, esi
0x18000574d  lock xadd [rbx+0Ch], eax
0x180005752  cmp     eax, 1
0x180005755  jnz     short loc_180005767
0x180005757  mov     rax, [rbx]
0x18000575a  mov     rcx, rbx
0x18000575d  mov     rax, [rax+8]
0x180005761  call    cs:__guard_dispatch_icall_fptr
0x180005767  mov     rdi, [r15+20h]
0x18000576b  mov     rbx, [rbp+57h+var_A0]
0x18000576f  mov     rax, [rbx]
0x180005772  mov     rcx, rbx
0x180005775  mov     rax, [rax+8]
0x180005779  call    cs:__guard_dispatch_icall_fptr
0x18000577f  mov     rax, [rbx]
0x180005782  mov     rcx, rbx
0x180005785  mov     rax, [rax+10h]
0x180005789  call    cs:__guard_dispatch_icall_fptr
0x18000578f  mov     rax, [rbx]
0x180005792  mov     rcx, rbx
0x180005795  mov     rax, [rax+8]
0x180005799  call    cs:__guard_dispatch_icall_fptr
0x18000579f  mov     rax, [rbx]
0x1800057a2  mov     rcx, rbx
0x1800057a5  mov     rax, [rax+18h]
0x1800057a9  call    cs:__guard_dispatch_icall_fptr
0x1800057af  xorps   xmm3, xmm3
0x1800057b2  mov     r8, rdi
0x1800057b5  mov     rdx, rax
0x1800057b8  mov     rcx, r12
0x1800057bb  call    ??$CosineDistance@M@DistanceFunctionHelpers@SemanticIndex@asg@@YAN_KPEBM1M@Z; asg::SemanticIndex::DistanceFunctionHelpers::CosineDistance<float>(unsigned __int64,float const *,float const *,float)
0x1800057c0  movsd   xmm1, cs:__real@4000000000000000
0x1800057c8  subsd   xmm1, xmm0
0x1800057cc  mulsd   xmm1, cs:__real@3fe0000000000000
0x1800057d4  movsd   xmm6, qword ptr [r15+38h]
0x1800057da  subsd   xmm6, xmm1
0x1800057de  andps   xmm6, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1800057e5  mov     rbx, [rbp+57h+var_98]
0x1800057e9  test    rbx, rbx
0x1800057ec  jz      short loc_180005824
0x1800057ee  mov     eax, esi
0x1800057f0  lock xadd [rbx+8], eax
0x1800057f5  cmp     eax, 1
0x1800057f8  jnz     short loc_180005824
0x1800057fa  mov     rax, [rbx]
0x1800057fd  mov     rcx, rbx
0x180005800  mov     rax, [rax]
0x180005803  call    cs:__guard_dispatch_icall_fptr
0x180005809  lock xadd [rbx+0Ch], esi
0x18000580e  cmp     esi, 1
0x180005811  jnz     short loc_180005824
0x180005813  mov     rax, [rbx]
0x180005816  mov     rcx, rbx
0x180005819  mov     rax, [rax+8]
0x18000581d  call    cs:__guard_dispatch_icall_fptr
0x180005823  nop
0x180005824  lea     rcx, [rbp+57h+var_70]
0x180005828  call    ?_Tidy@?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@AEAAXXZ; std::vector<asg::SemanticRegistry::TokenText>::_Tidy(void)
0x18000582d  nop
0x18000582e  movaps  xmm0, xmm6
0x180005831  mov     rbx, [rsp+130h+arg_8]
0x180005839  movaps  xmm6, [rsp+130h+var_40]
0x180005841  add     rsp, 100h
0x180005848  pop     r15
0x18000584a  pop     r14
0x18000584c  pop     r13
0x18000584e  pop     r12
0x180005850  pop     rdi
0x180005851  pop     rsi
0x180005852  pop     rbp
0x180005853  retn
0x180005854  xor     edx, edx
0x180005856  mov     rax, [r9+10h]
0x18000585a  call    cs:__guard_dispatch_icall_fptr
0x180005860  test    al, al
0x180005862  jz      loc_180005BF4
0x180005868  mov     byte ptr [rbp+57h+var_B8], 0
0x18000586c  mov     rax, [r14]
0x18000586f  lea     r8, [rbp+57h+var_C0]
0x180005873  lea     rdx, [rsp+130h+pExceptionObject]
0x180005878  mov     rcx, r14
0x18000587b  mov     rax, [rax]
0x18000587e  call    cs:__guard_dispatch_icall_fptr
0x180005884  nop
0x180005885  lea     rdx, [rsp+130h+var_F0]
0x18000588a  mov     rcx, rax
0x18000588d  call    ?get@?$future@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@std@@@std@@QEAA?AV?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@2@XZ; std::future<std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>>::get(void)
0x180005892  nop
0x180005893  mov     rcx, qword ptr [rsp+130h+pExceptionObject]
0x180005898  test    rcx, rcx
  ... truncated ...
```

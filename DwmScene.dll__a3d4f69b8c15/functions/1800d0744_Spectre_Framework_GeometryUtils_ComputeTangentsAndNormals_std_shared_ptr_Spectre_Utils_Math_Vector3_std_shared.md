# Spectre::Framework::GeometryUtils::ComputeTangentsAndNormals(std::shared_ptr<Spectre::Utils::Math::Vector3>,std::shared_ptr<Spectre::Utils::Math::Vector2>,uint,std::shared_ptr<void>,uint,bool,Spectre::Framework::GeometryUtils::TriangularMeshTopology,bool,std::function<void (std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)>,void *,std::shared_ptr<Spectre::Utils::ICancellationToken> const &)

- ea: `0x1800d0744`
- end: `0x1800d0c2e`
- name: `?ComputeTangentsAndNormals@GeometryUtils@Framework@Spectre@@SAXV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@V?$shared_ptr@UVector2@Math@Utils@Spectre@@@5@IV?$shared_ptr@X@5@I_NW4TriangularMeshTopology@123@3V?$function@$$A6AXAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@std@@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@2@PEAX@Z@5@PEAXAEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@5@@Z`
- size: `1258`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045024`

## callees

- `0x18000d678`
- `0x18000dfa2`
- `0x18001128c`
- `0x18001c290`
- `0x18007c958`
- `0x180082a38`
- `0x1800cf630`
- `0x1800cf83c`
- `0x1800cfa98`
- `0x1800cfaf4`
- `0x1800cfd24`
- `0x1800d0744`
- `0x1800d0f50`
- `0x1800d1130`
- `0x1800d11e8`
- `0x1800d12a0`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d0817`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d090e`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d0817`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d090e`

## string_xrefs

- `0x1800d0771`: `ComputeTangentsAndNormals`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void Spectre::Framework::GeometryUtils::ComputeTangentsAndNormals(
        size_t *a1,
        struct Spectre::Utils::Math::Vector3 **a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int a5,
        char a6,
        unsigned int a7,
        char a8,
        __int64 a9,
        ...)
{
  __int64 v10; // rsi
  __int64 v13; // rdi
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // rcx
  Spectre *v19; // r15
  _DWORD *v20; // rax
  struct Spectre::Utils::Math::Vector3 *v21; // r15
  _DWORD *v22; // rax
  std::_Ref_count_base *v23; // rcx
  struct Spectre::Utils::Math::Vector3 *v24; // rdi
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26; // rcx
  std::_Ref_count_base *v27; // rcx
  __int64 v28; // rcx
  const char *v29; // rax
  struct Spectre::Utils::Math::Vector3 *v30; // [rsp+28h] [rbp-100h]
  bool v31; // [rsp+30h] [rbp-F8h]
  size_t Size[2]; // [rsp+50h] [rbp-D8h] BYREF
  std::_Ref_count_base *v33[2]; // [rsp+60h] [rbp-C8h] BYREF
  size_t v34[2]; // [rsp+70h] [rbp-B8h] BYREF
  char v35; // [rsp+80h] [rbp-A8h]
  Spectre *v36[2]; // [rsp+88h] [rbp-A0h] BYREF
  struct Spectre::Utils::Math::Vector3 *v37[3]; // [rsp+98h] [rbp-90h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD v39[2]; // [rsp+C0h] [rbp-68h] BYREF
  _QWORD v40[2]; // [rsp+D0h] [rbp-58h] BYREF
  char v41; // [rsp+E0h] [rbp-48h]
  const Spectre::Framework::GeometryProcessingException *v42; // [rsp+E8h] [rbp-40h] BYREF
  struct Spectre::Utils::Math::Vector3 *v46; // [rsp+178h] [rbp+50h] BYREF
  va_list va; // [rsp+178h] [rbp+50h]
  __int64 v48; // [rsp+180h] [rbp+58h]
  va_list va1; // [rsp+188h] [rbp+60h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v46 = va_arg(va1, struct Spectre::Utils::Math::Vector3 *);
  v48 = va_arg(va1, _QWORD);
  v10 = a3;
  if ( (unsigned __int8)Spectre::Framework::ValidateVertexCount(a3, "ComputeTangentsAndNormals") )
  {
    Size[0] = 16 * v10;
    v19 = (Spectre *)_aligned_malloc(16 * v10, 0x10u);
    *(_OWORD *)v36 = 0;
    LOBYTE(v46) = 0;
    v34[0] = (size_t)v19;
    va_copy((va_list)&v34[1], va);
    v20 = operator new(0x18u);
    if ( v20 )
    {
      v20[2] = 1;
      v20[3] = 1;
      *(_QWORD *)v20 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_96ffd31a4081c2af17eae963fb5dd7cc_>::`vftable';
      *((_QWORD *)v20 + 2) = v19;
    }
    else
    {
      v20 = 0;
    }
    v36[0] = v19;
    v36[1] = (Spectre *)v20;
    v35 = 0;
    std::_Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___::__Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___(v34);
    if ( !v36[0] )
    {
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &stdext::bad_alloc::`vftable';
      throw (stdext::bad_alloc *)pExceptionObject;
    }
    memset_0(v36[0], 0, Size[0]);
    std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(v37, (unsigned int)(2 * v10));
    v21 = v37[0];
    v34[0] = 12 * v10;
    Size[0] = (size_t)_aligned_malloc(12 * v10, 0x10u);
    *(_OWORD *)v33 = 0;
    LOBYTE(v46) = 0;
    v40[0] = Size[0];
    va_copy((va_list)&v40[1], va);
    v22 = operator new(0x18u);
    if ( v22 )
    {
      v22[2] = 1;
      v22[3] = 1;
      *(_QWORD *)v22 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_fdb7222a856e1b31897eb021985012a7_>::`vftable';
      v23 = (std::_Ref_count_base *)Size[0];
      *((_QWORD *)v22 + 2) = Size[0];
    }
    else
    {
      v22 = 0;
      v23 = (std::_Ref_count_base *)Size[0];
    }
    v33[0] = v23;
    v33[1] = (std::_Ref_count_base *)v22;
    v41 = 0;
    std::_Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___::__Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___(v40);
    if ( !v33[0] )
    {
      v39[1] = "bad allocation";
      v39[0] = &stdext::bad_alloc::`vftable';
      throw (stdext::bad_alloc *)v39;
    }
    v24 = (struct Spectre::Utils::Math::Vector3 *)((char *)v21 + v34[0]);
    memset_0(v33[0], 0, v34[0]);
    Size[0] = *a1;
    v46 = *a2;
    try
    {
      if ( a6 )
      {
        if ( *a4 )
        {
          Spectre::Framework::ValidateTopologyIndexCount(a5, a7);
          Spectre::Framework::CalculateIndexedTangentsAndNormals<unsigned int>(
            Size[0],
            v10,
            *a4,
            a5,
            v46,
            a7,
            v48,
            (__int64)v33[0],
            v21,
            (__int64)v24);
        }
        else
        {
          Spectre::Framework::ValidateTopologyVertexCount((unsigned int)v10, a7);
          Spectre::Framework::CalculateNonIndexedeTangentsAndNormals((Spectre *)Size[0], v48, (bool)v33[0], v21, v24);
        }
      }
      else
      {
        Spectre::Framework::ValidateTopologyIndexCount(a5, a7);
        Spectre::Framework::CalculateIndexedTangentsAndNormals<unsigned short>(
          Size[0],
          v10,
          *a4,
          a5,
          v46,
          a7,
          v48,
          (__int64)v33[0],
          v21,
          (__int64)v24);
      }
    }
    catch ( Spectre::Utils::CancelledException )
    {
      throw;
    }
    catch ( const Spectre::Framework::GeometryProcessingException *v42 )
    {
      v29 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v42 + 16);
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, v29);
      *(_OWORD *)Size = 0;
      *(_OWORD *)v34 = 0;
      std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(
        a9,
        v34,
        Size);
      if ( v34[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v34[1]);
      if ( Size[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)Size[1]);
      goto LABEL_33;
    }
    catch ( ... )
    {
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, "ComputeTangentsAndNormals threw exception");
      *(_OWORD *)Size = 0;
      *(_OWORD *)v34 = 0;
      std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(
        a9,
        v34,
        Size);
      if ( v34[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v34[1]);
      if ( Size[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)Size[1]);
LABEL_33:
      if ( v33[1] )
        std::_Ref_count_base::_Decref(v33[1]);
      std::vector<Spectre::Utils::Math::Vector3>::_Tidy(v37);
      if ( v36[1] )
        std::_Ref_count_base::_Decref(v36[1]);
      v25 = (std::_Ref_count_base *)a1[1];
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
      v26 = a2[1];
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      v27 = (std::_Ref_count_base *)a4[1];
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
      v13 = a9;
LABEL_44:
      v28 = *(_QWORD *)(v13 + 56);
      if ( v28 )
      {
        LOBYTE(v14) = v28 != v13;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 32LL))(v28, v14);
        *(_QWORD *)(v13 + 56) = 0;
      }
    }
    LOBYTE(v30) = a8;
    Spectre::FinalizeVertexTangents(
      v36[0],
      (struct Spectre::Utils::Math::Vector4 *)(unsigned int)v10,
      (unsigned int)v33[0],
      v21,
      v24,
      v30,
      v31);
    v13 = a9;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(
      a9,
      v36,
      v33);
    if ( v33[1] )
      std::_Ref_count_base::_Decref(v33[1]);
    std::vector<Spectre::Utils::Math::Vector3>::_Tidy(v37);
    v15 = v36[1];
  }
  else
  {
    *(_OWORD *)Size = 0;
    *(_OWORD *)v34 = 0;
    v13 = a9;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(
      a9,
      v34,
      Size);
    if ( v34[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v34[1]);
    v15 = (std::_Ref_count_base *)Size[1];
  }
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v16 = (std::_Ref_count_base *)a1[1];
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v17 = a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  v18 = (std::_Ref_count_base *)a4[1];
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  goto LABEL_44;
}

```

## disassembly

```asm
0x1800d0744  mov     [rsp+arg_18], r9
0x1800d0749  mov     [rsp+arg_8], rdx
0x1800d074e  mov     [rsp+arg_0], rcx
0x1800d0753  push    rbx
0x1800d0754  push    rsi
0x1800d0755  push    rdi
0x1800d0756  push    r12
0x1800d0758  push    r13
0x1800d075a  push    r14
0x1800d075c  push    r15
0x1800d075e  sub     rsp, 0F0h
0x1800d0765  mov     r14, r9
0x1800d0768  mov     esi, r8d
0x1800d076b  mov     r13, rdx
0x1800d076e  mov     r12, rcx
0x1800d0771  lea     rdx, aComputetangent_1; "ComputeTangentsAndNormals"
0x1800d0778  mov     ecx, r8d
0x1800d077b  call    Spectre__Framework__ValidateVertexCount
0x1800d0780  xor     ebx, ebx
0x1800d0782  test    al, al
0x1800d0784  jnz     short loc_1800D0803
0x1800d0786  xorps   xmm0, xmm0
0x1800d0789  movdqu  xmmword ptr [rsp+128h+Size], xmm0
0x1800d078f  movdqu  xmmword ptr [rsp+128h+var_B8], xmm0
0x1800d0795  lea     r8, [rsp+128h+Size]
0x1800d079a  lea     rdx, [rsp+128h+var_B8]
0x1800d079f  mov     rdi, [rsp+128h+arg_40]
0x1800d07a7  mov     rcx, rdi
0x1800d07aa  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@std@@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@2@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@1@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d07af  nop
0x1800d07b0  mov     rcx, [rsp+128h+var_B8+8]; this
0x1800d07b5  test    rcx, rcx
0x1800d07b8  jz      short loc_1800D07C0
0x1800d07ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d07bf  nop
0x1800d07c0  mov     rcx, [rsp+128h+Size+8]; this
0x1800d07c5  test    rcx, rcx
0x1800d07c8  jz      short loc_1800D07D0
0x1800d07ca  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d07cf  nop
0x1800d07d0  mov     rcx, [r12+8]; this
0x1800d07d5  test    rcx, rcx
0x1800d07d8  jz      short loc_1800D07E0
0x1800d07da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d07df  nop
0x1800d07e0  mov     rcx, [r13+8]; this
0x1800d07e4  test    rcx, rcx
0x1800d07e7  jz      short loc_1800D07EF
0x1800d07e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d07ee  nop
0x1800d07ef  mov     rcx, [r14+8]; this
0x1800d07f3  test    rcx, rcx
0x1800d07f6  jz      short loc_1800D07FE
0x1800d07f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d07fd  nop
0x1800d07fe  jmp     loc_1800D0BFC
0x1800d0803  mov     rax, rsi
0x1800d0806  shl     rax, 4
0x1800d080a  mov     [rsp+128h+Size], rax
0x1800d080f  mov     edx, 10h; Alignment
0x1800d0814  mov     rcx, rax; Size
0x1800d0817  call    cs:__imp__aligned_malloc
0x1800d081d  mov     r15, rax
0x1800d0820  xorps   xmm0, xmm0
0x1800d0823  movdqu  xmmword ptr [rsp+128h+var_A0], xmm0
0x1800d082c  mov     byte ptr [rsp+128h+arg_48], bl
0x1800d0833  mov     [rsp+128h+var_B8], rax
0x1800d0838  lea     rax, [rsp+128h+arg_48]
0x1800d0840  mov     [rsp+128h+var_B8+8], rax
0x1800d0845  mov     ecx, 18h; unsigned __int64
0x1800d084a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d084f  mov     edi, 1
0x1800d0854  test    rax, rax
0x1800d0857  jz      short loc_1800D086F
0x1800d0859  mov     [rax+8], edi
0x1800d085c  mov     [rax+0Ch], edi
0x1800d085f  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector4@Math@Utils@Spectre@@V_lambda_96ffd31a4081c2af17eae963fb5dd7cc_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_96ffd31a4081c2af17eae963fb5dd7cc_>::`vftable'
0x1800d0866  mov     [rax], rcx
0x1800d0869  mov     [rax+10h], r15
0x1800d086d  jmp     short loc_1800D0872
0x1800d086f  mov     rax, rbx
0x1800d0872  mov     [rsp+128h+var_A0], r15
0x1800d087a  mov     [rsp+128h+var_A0+8], rax
0x1800d0882  mov     [rsp+128h+var_A8], bl
0x1800d0889  lea     rcx, [rsp+128h+var_B8]
0x1800d088e  call    std___Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6_______Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___
0x1800d0893  nop
0x1800d0894  mov     rcx, [rsp+128h+var_A0]; void *
0x1800d089c  test    rcx, rcx
0x1800d089f  jnz     short loc_1800D08D4
0x1800d08a1  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; "bad allocation"
0x1800d08a8  mov     [rsp+128h+var_70], rax
0x1800d08b0  lea     rax, ??_7bad_alloc@stdext@@6B@; const stdext::bad_alloc::`vftable'
0x1800d08b7  mov     [rsp+128h+pExceptionObject], rax
0x1800d08bf  lea     rdx, _TI2?AVbad_alloc@stdext@@; pThrowInfo
0x1800d08c6  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x1800d08ce  call    _CxxThrowException_0
0x1800d08d4  mov     r8, [rsp+128h+Size]; Size
0x1800d08d9  xor     edx, edx; Val
0x1800d08db  call    memset_0
0x1800d08e0  lea     edx, [rsi+rsi]
0x1800d08e3  lea     rcx, [rsp+128h+var_90]
0x1800d08eb  call    ??0?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@QEAA@_KAEBV?$allocator@UVector3@Math@Utils@Spectre@@@1@@Z; std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(unsigned __int64,std::allocator<Spectre::Utils::Math::Vector3> const &)
0x1800d08f0  nop
0x1800d08f1  mov     r15, [rsp+128h+var_90]
0x1800d08f9  lea     rax, [rsi+rsi*2]
0x1800d08fd  shl     rax, 2
0x1800d0901  mov     [rsp+128h+var_B8], rax
0x1800d0906  mov     edx, 10h; Alignment
0x1800d090b  mov     rcx, rax; Size
0x1800d090e  call    cs:__imp__aligned_malloc
0x1800d0914  mov     [rsp+128h+Size], rax
0x1800d0919  xorps   xmm0, xmm0
0x1800d091c  movdqu  xmmword ptr [rsp+128h+var_C8], xmm0
0x1800d0922  mov     byte ptr [rsp+128h+arg_48], bl
0x1800d0929  mov     [rsp+128h+var_58], rax
0x1800d0931  lea     rax, [rsp+128h+arg_48]
0x1800d0939  mov     [rsp+128h+var_50], rax
0x1800d0941  mov     ecx, 18h; unsigned __int64
0x1800d0946  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d094b  test    rax, rax
0x1800d094e  jz      short loc_1800D096B
0x1800d0950  mov     [rax+8], edi
0x1800d0953  mov     [rax+0Ch], edi
0x1800d0956  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector3@Math@Utils@Spectre@@V_lambda_fdb7222a856e1b31897eb021985012a7_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_fdb7222a856e1b31897eb021985012a7_>::`vftable'
0x1800d095d  mov     [rax], rcx
0x1800d0960  mov     rcx, [rsp+128h+Size]
0x1800d0965  mov     [rax+10h], rcx
0x1800d0969  jmp     short loc_1800D0973
0x1800d096b  mov     rax, rbx
0x1800d096e  mov     rcx, [rsp+128h+Size]
0x1800d0973  mov     [rsp+128h+var_C8], rcx
0x1800d0978  mov     [rsp+128h+var_C8+8], rax
0x1800d097d  mov     [rsp+128h+var_48], bl
0x1800d0984  lea     rcx, [rsp+128h+var_58]
0x1800d098c  call    std___Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6_______Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___
0x1800d0991  nop
0x1800d0992  mov     rcx, [rsp+128h+var_C8]; void *
0x1800d0997  test    rcx, rcx
0x1800d099a  jnz     short loc_1800D09CF
0x1800d099c  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; "bad allocation"
0x1800d09a3  mov     [rsp+128h+var_60], rax
0x1800d09ab  lea     rax, ??_7bad_alloc@stdext@@6B@; const stdext::bad_alloc::`vftable'
0x1800d09b2  mov     [rsp+128h+var_68], rax
0x1800d09ba  lea     rdx, _TI2?AVbad_alloc@stdext@@; pThrowInfo
0x1800d09c1  lea     rcx, [rsp+128h+var_68]; pExceptionObject
0x1800d09c9  call    _CxxThrowException_0
0x1800d09cf  mov     r8, [rsp+128h+var_B8]; Size
0x1800d09d4  lea     rdi, [r8+r15]
0x1800d09d8  xor     edx, edx; Val
0x1800d09da  call    memset_0
0x1800d09df  mov     rax, [r12]
0x1800d09e3  mov     [rsp+128h+Size], rax
0x1800d09e8  mov     rax, [r13+0]
0x1800d09ec  mov     [rsp+128h+arg_48], rax
0x1800d09f4  mov     edx, [rsp+128h+arg_30]
0x1800d09fb  cmp     [rsp+128h+arg_28], bl
0x1800d0a02  jnz     short loc_1800D0A62
0x1800d0a04  mov     ecx, [rsp+128h+arg_20]
0x1800d0a0b  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d0a10  mov     [rsp+128h+var_E0], rdi; __int64
0x1800d0a15  mov     [rsp+128h+var_E8], r15; struct Spectre::Utils::Math::Vector3 *
0x1800d0a1a  mov     rax, [rsp+128h+var_C8]
0x1800d0a1f  mov     [rsp+128h+var_F0], rax; __int64
0x1800d0a24  mov     rax, [rsp+128h+arg_50]
0x1800d0a2c  mov     [rsp+128h+var_F8], rax; __int64
0x1800d0a31  mov     eax, [rsp+128h+arg_30]
0x1800d0a38  mov     dword ptr [rsp+128h+var_100], eax; int
0x1800d0a3c  mov     r8, [rsp+128h+arg_48]
0x1800d0a44  mov     [rsp+128h+var_108], r8; struct Spectre::Utils::Math::Vector3 *
0x1800d0a49  mov     r9d, [rsp+128h+arg_20]; int
0x1800d0a51  mov     r8, [r14]; int
0x1800d0a54  mov     edx, esi; int
0x1800d0a56  mov     rcx, [rsp+128h+Size]; int
0x1800d0a5b  call    ??$CalculateIndexedTangentsAndNormals@G@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBGIQEBUVector2@341@W4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@55@Z; Spectre::Framework::CalculateIndexedTangentsAndNormals<ushort>(Spectre::Utils::Math::Vector3 const * const,uint,ushort const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d0a60  jmp     short loc_1800D0AC3
0x1800d0a62  cmp     [r14], rbx
0x1800d0a65  jz      short loc_1800D0AC5
0x1800d0a67  mov     ecx, [rsp+128h+arg_20]
0x1800d0a6e  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d0a73  mov     [rsp+128h+var_E0], rdi; __int64
0x1800d0a78  mov     [rsp+128h+var_E8], r15; struct Spectre::Utils::Math::Vector3 *
0x1800d0a7d  mov     rax, [rsp+128h+var_C8]
0x1800d0a82  mov     [rsp+128h+var_F0], rax; __int64
0x1800d0a87  mov     rax, [rsp+128h+arg_50]
0x1800d0a8f  mov     [rsp+128h+var_F8], rax; __int64
0x1800d0a94  mov     eax, [rsp+128h+arg_30]
0x1800d0a9b  mov     dword ptr [rsp+128h+var_100], eax; int
0x1800d0a9f  mov     r8, [rsp+128h+arg_48]
0x1800d0aa7  mov     [rsp+128h+var_108], r8; struct Spectre::Utils::Math::Vector3 *
0x1800d0aac  mov     r9d, [rsp+128h+arg_20]; int
0x1800d0ab4  mov     r8, [r14]; int
0x1800d0ab7  mov     edx, esi; int
0x1800d0ab9  mov     rcx, [rsp+128h+Size]; int
0x1800d0abe  call    ??$CalculateIndexedTangentsAndNormals@I@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBIIQEBUVector2@341@W4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@55@Z; Spectre::Framework::CalculateIndexedTangentsAndNormals<uint>(Spectre::Utils::Math::Vector3 const * const,uint,uint const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d0ac3  jmp     short loc_1800D0B0A
0x1800d0ac5  mov     ecx, esi
0x1800d0ac7  call    Spectre__Framework__ValidateTopologyVertexCount
0x1800d0acc  mov     [rsp+128h+var_F0], rdi; struct Spectre::Utils::Math::Vector3 *
0x1800d0ad1  mov     [rsp+128h+var_F8], r15; bool
0x1800d0ad6  mov     rax, [rsp+128h+var_C8]
0x1800d0adb  mov     [rsp+128h+var_100], rax; bool
0x1800d0ae0  mov     rax, [rsp+128h+arg_50]
0x1800d0ae8  mov     [rsp+128h+var_108], rax; __int64
0x1800d0aed  mov     r9d, [rsp+128h+arg_30]
0x1800d0af5  mov     r8, [rsp+128h+arg_48]
0x1800d0afd  mov     edx, esi
0x1800d0aff  mov     rcx, [rsp+128h+Size]; this
0x1800d0b04  call    ?CalculateNonIndexedeTangentsAndNormals@Framework@Spectre@@YAXQEBUVector3@Math@Utils@2@IQEBUVector2@452@W4TriangularMeshTopology@GeometryUtils@12@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU3452@44@Z; Spectre::Framework::CalculateNonIndexedeTangentsAndNormals(Spectre::Utils::Math::Vector3 const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d0b09  nop
0x1800d0b0a  mov     al, byte ptr [rsp+128h+arg_38]
0x1800d0b11  mov     byte ptr [rsp+128h+var_100], al; struct Spectre::Utils::Math::Vector3 *
0x1800d0b15  mov     [rsp+128h+var_108], rdi; struct Spectre::Utils::Math::Vector3 *
0x1800d0b1a  mov     r9, r15; struct Spectre::Utils::Math::Vector3 *
0x1800d0b1d  mov     r8, [rsp+128h+var_C8]; unsigned int
0x1800d0b22  mov     edx, esi; struct Spectre::Utils::Math::Vector4 *
0x1800d0b24  mov     rcx, [rsp+128h+var_A0]; this
0x1800d0b2c  call    ?FinalizeVertexTangents@Spectre@@YAXPEAUVector4@Math@Utils@1@IPEBUVector3@341@11_N@Z; Spectre::FinalizeVertexTangents(Spectre::Utils::Math::Vector4 *,uint,Spectre::Utils::Math::Vector3 const *,Spectre::Utils::Math::Vector3 const *,Spectre::Utils::Math::Vector3 const *,bool)
0x1800d0b31  lea     r8, [rsp+128h+var_C8]
0x1800d0b36  lea     rdx, [rsp+128h+var_A0]
0x1800d0b3e  mov     rdi, [rsp+128h+arg_40]
0x1800d0b46  mov     rcx, rdi
0x1800d0b49  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@std@@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@2@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@1@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d0b4e  nop
0x1800d0b4f  mov     rcx, [rsp+128h+var_C8+8]; this
0x1800d0b54  test    rcx, rcx
0x1800d0b57  jz      short loc_1800D0B5F
0x1800d0b59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0b5e  nop
0x1800d0b5f  lea     rcx, [rsp+128h+var_90]
0x1800d0b67  call    ?_Tidy@?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Utils::Math::Vector3>::_Tidy(void)
0x1800d0b6c  nop
0x1800d0b6d  mov     rcx, [rsp+128h+var_A0+8]
0x1800d0b75  jmp     loc_1800D07C5
0x1800d0b7a  jmp     short $+2
0x1800d0b7c  xor     ebx, ebx
0x1800d0b7e  mov     rcx, [rsp+128h+var_C8+8]; this
0x1800d0b83  test    rcx, rcx
0x1800d0b86  jz      short loc_1800D0B8E
0x1800d0b88  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0b8d  nop
0x1800d0b8e  lea     rcx, [rsp+128h+var_90]
0x1800d0b96  call    ?_Tidy@?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Utils::Math::Vector3>::_Tidy(void)
0x1800d0b9b  nop
0x1800d0b9c  mov     rcx, [rsp+128h+var_A0+8]; this
0x1800d0ba4  test    rcx, rcx
0x1800d0ba7  jz      short loc_1800D0BAF
0x1800d0ba9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0bae  nop
0x1800d0baf  mov     rax, [rsp+128h+arg_0]
0x1800d0bb7  mov     rcx, [rax+8]; this
0x1800d0bbb  test    rcx, rcx
0x1800d0bbe  jz      short loc_1800D0BC6
0x1800d0bc0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0bc5  nop
0x1800d0bc6  mov     rax, [rsp+128h+arg_8]
0x1800d0bce  mov     rcx, [rax+8]; this
0x1800d0bd2  test    rcx, rcx
0x1800d0bd5  jz      short loc_1800D0BDD
0x1800d0bd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0bdc  nop
0x1800d0bdd  mov     rax, [rsp+128h+arg_18]
0x1800d0be5  mov     rcx, [rax+8]; this
0x1800d0be9  test    rcx, rcx
0x1800d0bec  jz      short loc_1800D0BF4
0x1800d0bee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0bf3  nop
0x1800d0bf4  mov     rdi, [rsp+128h+arg_40]
0x1800d0bfc  mov     rcx, [rdi+38h]
0x1800d0c00  test    rcx, rcx
0x1800d0c03  jz      short loc_1800D0C1B
0x1800d0c05  cmp     rcx, rdi
0x1800d0c08  mov     rax, [rcx]
0x1800d0c0b  setnz   dl
0x1800d0c0e  mov     rax, [rax+20h]
0x1800d0c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0c17  mov     [rdi+38h], rbx
0x1800d0c1b  add     rsp, 0F0h
0x1800d0c22  pop     r15
0x1800d0c24  pop     r14
0x1800d0c26  pop     r13
0x1800d0c28  pop     r12
0x1800d0c2a  pop     rdi
0x1800d0c2b  pop     rsi
0x1800d0c2c  pop     rbx
0x1800d0c2d  retn
```

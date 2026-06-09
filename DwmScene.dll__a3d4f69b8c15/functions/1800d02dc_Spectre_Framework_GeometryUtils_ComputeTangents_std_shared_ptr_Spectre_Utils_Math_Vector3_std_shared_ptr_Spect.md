# Spectre::Framework::GeometryUtils::ComputeTangents(std::shared_ptr<Spectre::Utils::Math::Vector3>,std::shared_ptr<Spectre::Utils::Math::Vector2>,std::shared_ptr<Spectre::Utils::Math::Vector3>,uint,std::shared_ptr<void>,uint,bool,Spectre::Framework::GeometryUtils::TriangularMeshTopology,bool,std::function<void (std::shared_ptr<Spectre::Utils::Math::Vector4> const &,void *)>,void *,std::shared_ptr<Spectre::Utils::ICancellationToken> const &)

- ea: `0x1800d02dc`
- end: `0x1800d073b`
- name: `?ComputeTangents@GeometryUtils@Framework@Spectre@@SAXV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@V?$shared_ptr@UVector2@Math@Utils@Spectre@@@5@0IV?$shared_ptr@X@5@I_NW4TriangularMeshTopology@123@3V?$function@$$A6AXAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@std@@PEAX@Z@5@PEAXAEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@5@@Z`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045368`

## callees

- `0x18000d678`
- `0x18000dfa2`
- `0x18001128c`
- `0x18001c290`
- `0x18007c958`
- `0x180082a38`
- `0x1800cf288`
- `0x1800cf45c`
- `0x1800cfa98`
- `0x1800cfab8`
- `0x1800cfc14`
- `0x1800d02dc`
- `0x1800d0f50`
- `0x1800d1130`
- `0x1800d11e8`
- `0x1800d12a0`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d03a6`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d03a6`

## string_xrefs

- `0x1800d030b`: `ComputeTangents`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Spectre::Framework::GeometryUtils::ComputeTangents(
        Spectre **a1,
        struct Spectre::Utils::Math::Vector3 **a2,
        std::_Ref_count_base **a3,
        unsigned int a4,
        _QWORD *a5,
        unsigned int a6,
        char a7,
        unsigned int a8,
        char a9,
        __int64 a10,
        struct Spectre::Utils::Math::Vector3 *a11,
        __int64 a12)
{
  __int64 v12; // rsi
  __int64 v16; // rdi
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  std::_Ref_count_base *v19; // rcx
  std::_Ref_count_base *v20; // rcx
  std::_Ref_count_base *v21; // rcx
  std::_Ref_count_base *v22; // rdi
  _DWORD *v23; // rax
  Spectre *v24; // rdi
  struct Spectre::Utils::Math::Vector3 *v25; // r14
  _QWORD *v26; // r14
  std::_Ref_count_base *v27; // rcx
  std::_Ref_count_base *v28; // rcx
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v30; // rcx
  std::_Ref_count_base *v31; // rcx
  std::_Ref_count_base *v32; // rcx
  std::_Ref_count_base *v33; // rcx
  __int64 v34; // rcx
  const char *v35; // rax
  struct Spectre::Utils::Math::Vector3 *v36; // [rsp+20h] [rbp-C8h]
  struct Spectre::Utils::Math::Vector3 *v37; // [rsp+28h] [rbp-C0h]
  bool v38; // [rsp+30h] [rbp-B8h]
  struct Spectre::Utils::Math::Vector3 *v39; // [rsp+50h] [rbp-98h]
  std::_Ref_count_base *v40[2]; // [rsp+58h] [rbp-90h] BYREF
  char v41; // [rsp+68h] [rbp-80h]
  Spectre *v42[2]; // [rsp+70h] [rbp-78h] BYREF
  Spectre *v43; // [rsp+80h] [rbp-68h]
  struct Spectre::Utils::Math::Vector3 *v44; // [rsp+88h] [rbp-60h]
  _QWORD v45[3]; // [rsp+90h] [rbp-58h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+A8h] [rbp-40h] BYREF
  const Spectre::Framework::GeometryProcessingException *v47; // [rsp+B8h] [rbp-30h] BYREF

  v12 = a4;
  if ( (unsigned __int8)Spectre::Framework::ValidateVertexCount(a4, "ComputeTangents") )
  {
    v22 = (std::_Ref_count_base *)_aligned_malloc(16 * v12, 0x10u);
    *(_OWORD *)v42 = 0;
    LOBYTE(a11) = 0;
    v40[0] = v22;
    v40[1] = (std::_Ref_count_base *)&a11;
    v23 = operator new(0x18u);
    if ( v23 )
    {
      v23[2] = 1;
      v23[3] = 1;
      *(_QWORD *)v23 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_dc718d396f0c2d0078465762313bdcf6_>::`vftable';
      *((_QWORD *)v23 + 2) = v22;
    }
    v42[0] = v22;
    v42[1] = (Spectre *)v23;
    v41 = 0;
    std::_Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___::__Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___(v40);
    if ( !v42[0] )
    {
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &stdext::bad_alloc::`vftable';
      throw (stdext::bad_alloc *)pExceptionObject;
    }
    memset_0(v42[0], 0, 16 * v12);
    std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(v45, (unsigned int)(2 * v12));
    v39 = (struct Spectre::Utils::Math::Vector3 *)v45[0];
    a11 = (struct Spectre::Utils::Math::Vector3 *)(v45[0] + 12 * v12);
    v24 = *a1;
    v43 = *a1;
    v25 = *a2;
    v44 = *a2;
    v40[0] = *a3;
    if ( a7 )
    {
      v26 = a5;
      if ( *a5 )
      {
        Spectre::Framework::ValidateTopologyIndexCount(a6, a8);
        Spectre::Framework::CalculateIndexedTangents<unsigned int>(v43, v44, a8, a12, (__int64)v39, (__int64)a11);
      }
      else
      {
        Spectre::Framework::ValidateTopologyVertexCount((unsigned int)v12, a8);
        Spectre::Framework::CalculateNonIndexedTangents(v24, a12, (bool)v39, a11);
      }
    }
    else
    {
      try
      {
        Spectre::Framework::ValidateTopologyIndexCount(a6, a8);
        v36 = v25;
        v26 = a5;
        Spectre::Framework::CalculateIndexedTangents<unsigned short>(v43, v36, a8, a12, (__int64)v39, (__int64)a11);
      }
      catch ( Spectre::Utils::CancelledException )
      {
        throw;
      }
      catch ( const Spectre::Framework::GeometryProcessingException *v47 )
      {
        v35 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v47 + 16);
        Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, v35);
        *(_OWORD *)v40 = 0;
        std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a10, v40);
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
        goto LABEL_32;
      }
      catch ( ... )
      {
        Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, "ComputeTangents threw exception");
        *(_OWORD *)v40 = 0;
        std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a10, v40);
        if ( v40[1] )
          std::_Ref_count_base::_Decref(v40[1]);
LABEL_32:
        std::vector<Spectre::Utils::Math::Vector3>::_Tidy(v45);
        if ( v42[1] )
          std::_Ref_count_base::_Decref(v42[1]);
        v30 = a1[1];
        if ( v30 )
          std::_Ref_count_base::_Decref(v30);
        v31 = a2[1];
        if ( v31 )
          std::_Ref_count_base::_Decref(v31);
        v32 = a3[1];
        if ( v32 )
          std::_Ref_count_base::_Decref(v32);
        v33 = (std::_Ref_count_base *)a5[1];
        if ( v33 )
          std::_Ref_count_base::_Decref(v33);
        v16 = a10;
LABEL_43:
        v34 = *(_QWORD *)(v16 + 56);
        if ( v34 )
        {
          LOBYTE(v17) = v34 != v16;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 32LL))(v34, v17);
          *(_QWORD *)(v16 + 56) = 0;
        }
      }
    }
    LOBYTE(v37) = a9;
    Spectre::FinalizeVertexTangents(
      v42[0],
      (struct Spectre::Utils::Math::Vector4 *)(unsigned int)v12,
      (unsigned int)v40[0],
      v39,
      a11,
      v37,
      v38);
    v16 = a10;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a10, v42);
    std::vector<Spectre::Utils::Math::Vector3>::_Tidy(v45);
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
    v27 = a1[1];
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    v28 = a2[1];
    if ( v28 )
      std::_Ref_count_base::_Decref(v28);
    v29 = a3[1];
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    v21 = (std::_Ref_count_base *)v26[1];
  }
  else
  {
    *(_OWORD *)v40 = 0;
    v16 = a10;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a10, v40);
    if ( v40[1] )
      std::_Ref_count_base::_Decref(v40[1]);
    v18 = a1[1];
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    v19 = a2[1];
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    v20 = a3[1];
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    v21 = (std::_Ref_count_base *)a5[1];
  }
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  goto LABEL_43;
}

```

## disassembly

```asm
0x1800d02dc  mov     rax, rsp
0x1800d02df  mov     [rax+20h], rsi
0x1800d02e3  mov     [rax+18h], r8
0x1800d02e7  mov     [rax+10h], rdx
0x1800d02eb  mov     [rax+8], rcx
0x1800d02ef  push    rdi
0x1800d02f0  push    r12
0x1800d02f2  push    r13
0x1800d02f4  push    r14
0x1800d02f6  push    r15
0x1800d02f8  sub     rsp, 0C0h
0x1800d02ff  mov     esi, r9d
0x1800d0302  mov     r14, r8
0x1800d0305  mov     r13, rdx
0x1800d0308  mov     r12, rcx
0x1800d030b  lea     rdx, aComputetangent_2; "ComputeTangents"
0x1800d0312  mov     ecx, r9d
0x1800d0315  call    Spectre__Framework__ValidateVertexCount
0x1800d031a  test    al, al
0x1800d031c  jnz     short loc_1800D0397
0x1800d031e  xorps   xmm0, xmm0
0x1800d0321  movdqu  xmmword ptr [rsp+0E8h+var_90], xmm0
0x1800d0327  lea     rdx, [rsp+0E8h+var_90]
0x1800d032c  mov     rdi, [rsp+0E8h+arg_48]
0x1800d0334  mov     rcx, rdi
0x1800d0337  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d033c  nop
0x1800d033d  mov     rcx, [rsp+0E8h+var_90+8]; this
0x1800d0342  test    rcx, rcx
0x1800d0345  jz      short loc_1800D034D
0x1800d0347  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d034c  nop
0x1800d034d  mov     rcx, [r12+8]; this
0x1800d0352  test    rcx, rcx
0x1800d0355  jz      short loc_1800D035D
0x1800d0357  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d035c  nop
0x1800d035d  mov     rcx, [r13+8]; this
0x1800d0361  test    rcx, rcx
0x1800d0364  jz      short loc_1800D036C
0x1800d0366  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d036b  nop
0x1800d036c  mov     rcx, [r14+8]; this
0x1800d0370  test    rcx, rcx
0x1800d0373  jz      short loc_1800D037B
0x1800d0375  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d037a  nop
0x1800d037b  mov     rax, [rsp+0E8h+arg_20]
0x1800d0383  mov     rcx, [rax+8]; this
0x1800d0387  test    rcx, rcx
0x1800d038a  jz      short loc_1800D0392
0x1800d038c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0391  nop
0x1800d0392  jmp     loc_1800D06FF
0x1800d0397  mov     r14, rsi
0x1800d039a  shl     r14, 4
0x1800d039e  mov     edx, 10h; Alignment
0x1800d03a3  mov     rcx, r14; Size
0x1800d03a6  call    cs:__imp__aligned_malloc
0x1800d03ac  mov     rdi, rax
0x1800d03af  xorps   xmm0, xmm0
0x1800d03b2  movdqu  xmmword ptr [rsp+0E8h+var_78], xmm0
0x1800d03b8  mov     byte ptr [rsp+0E8h+arg_50], 0
0x1800d03c0  mov     [rsp+0E8h+var_90], rax
0x1800d03c5  lea     rax, [rsp+0E8h+arg_50]
0x1800d03cd  mov     [rsp+0E8h+var_90+8], rax
0x1800d03d2  mov     ecx, 18h; unsigned __int64
0x1800d03d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d03dc  test    rax, rax
0x1800d03df  jz      short loc_1800D03FA
0x1800d03e1  mov     ecx, 1
0x1800d03e6  mov     [rax+8], ecx
0x1800d03e9  mov     [rax+0Ch], ecx
0x1800d03ec  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector4@Math@Utils@Spectre@@V_lambda_dc718d396f0c2d0078465762313bdcf6_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_dc718d396f0c2d0078465762313bdcf6_>::`vftable'
0x1800d03f3  mov     [rax], rcx
0x1800d03f6  mov     [rax+10h], rdi
0x1800d03fa  mov     [rsp+0E8h+var_78], rdi
0x1800d03ff  mov     [rsp+0E8h+var_78+8], rax
0x1800d0404  mov     [rsp+0E8h+var_80], 0
0x1800d0409  lea     rcx, [rsp+0E8h+var_90]
0x1800d040e  call    std___Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6_______Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___
0x1800d0413  nop
0x1800d0414  mov     rcx, [rsp+0E8h+var_78]; void *
0x1800d0419  test    rcx, rcx
0x1800d041c  jnz     short loc_1800D0451
0x1800d041e  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; "bad allocation"
0x1800d0425  mov     [rsp+0E8h+var_38], rax
0x1800d042d  lea     rax, ??_7bad_alloc@stdext@@6B@; const stdext::bad_alloc::`vftable'
0x1800d0434  mov     [rsp+0E8h+pExceptionObject], rax
0x1800d043c  lea     rdx, _TI2?AVbad_alloc@stdext@@; pThrowInfo
0x1800d0443  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1800d044b  call    _CxxThrowException_0
0x1800d0451  mov     r8, r14; Size
0x1800d0454  xor     edx, edx; Val
0x1800d0456  call    memset_0
0x1800d045b  lea     edx, [rsi+rsi]
0x1800d045e  lea     rcx, [rsp+0E8h+var_58]
0x1800d0466  call    ??0?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@QEAA@_KAEBV?$allocator@UVector3@Math@Utils@Spectre@@@1@@Z; std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(unsigned __int64,std::allocator<Spectre::Utils::Math::Vector3> const &)
0x1800d046b  nop
0x1800d046c  mov     rcx, [rsp+0E8h+var_58]
0x1800d0474  mov     [rsp+0E8h+var_98], rcx
0x1800d0479  lea     rax, [rsi+rsi*2]
0x1800d047d  lea     rax, [rcx+rax*4]
0x1800d0481  mov     [rsp+0E8h+arg_50], rax
0x1800d0489  mov     rdi, [r12]
0x1800d048d  mov     [rsp+0E8h+var_68], rdi
0x1800d0495  mov     r14, [r13+0]
0x1800d0499  mov     [rsp+0E8h+var_60], r14
0x1800d04a1  mov     r15, [rsp+0E8h+arg_10]
0x1800d04a9  mov     rax, [r15]
0x1800d04ac  mov     [rsp+0E8h+var_90], rax
0x1800d04b1  cmp     [rsp+0E8h+arg_30], 0
0x1800d04b9  jnz     short loc_1800D0521
0x1800d04bb  mov     edi, [rsp+0E8h+arg_38]
0x1800d04c2  mov     edx, edi
0x1800d04c4  mov     ecx, [rsp+0E8h+arg_28]
0x1800d04cb  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d04d0  mov     rax, [rsp+0E8h+arg_50]
0x1800d04d8  mov     [rsp+0E8h+var_A8], rax; __int64
0x1800d04dd  mov     rax, [rsp+0E8h+var_98]
0x1800d04e2  mov     [rsp+0E8h+var_B0], rax; __int64
0x1800d04e7  mov     rax, [rsp+0E8h+arg_58]
0x1800d04ef  mov     [rsp+0E8h+var_B8], rax; __int64
0x1800d04f4  mov     dword ptr [rsp+0E8h+var_C0], edi; int
0x1800d04f8  mov     [rsp+0E8h+var_C8], r14; struct Spectre::Utils::Math::Vector3 *
0x1800d04fd  mov     r9d, [rsp+0E8h+arg_28]
0x1800d0505  mov     r14, [rsp+0E8h+arg_20]
0x1800d050d  mov     r8, [r14]
0x1800d0510  mov     edx, esi
0x1800d0512  mov     rcx, [rsp+0E8h+var_68]; this
0x1800d051a  call    ??$CalculateIndexedTangents@G@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBGIQEBUVector2@341@W4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@5@Z; Spectre::Framework::CalculateIndexedTangents<ushort>(Spectre::Utils::Math::Vector3 const * const,uint,ushort const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d051f  jmp     short loc_1800D0593
0x1800d0521  mov     r14, [rsp+0E8h+arg_20]
0x1800d0529  cmp     qword ptr [r14], 0
0x1800d052d  jz      short loc_1800D0595
0x1800d052f  mov     edi, [rsp+0E8h+arg_38]
0x1800d0536  mov     edx, edi
0x1800d0538  mov     ecx, [rsp+0E8h+arg_28]
0x1800d053f  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d0544  mov     rax, [rsp+0E8h+arg_50]
0x1800d054c  mov     [rsp+0E8h+var_A8], rax; __int64
0x1800d0551  mov     rax, [rsp+0E8h+var_98]
0x1800d0556  mov     [rsp+0E8h+var_B0], rax; __int64
0x1800d055b  mov     rax, [rsp+0E8h+arg_58]
0x1800d0563  mov     [rsp+0E8h+var_B8], rax; __int64
0x1800d0568  mov     dword ptr [rsp+0E8h+var_C0], edi; int
0x1800d056c  mov     r8, [rsp+0E8h+var_60]
0x1800d0574  mov     [rsp+0E8h+var_C8], r8; struct Spectre::Utils::Math::Vector3 *
0x1800d0579  mov     r9d, [rsp+0E8h+arg_28]
0x1800d0581  mov     r8, [r14]
0x1800d0584  mov     edx, esi
0x1800d0586  mov     rcx, [rsp+0E8h+var_68]; this
0x1800d058e  call    ??$CalculateIndexedTangents@I@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBIIQEBUVector2@341@W4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@5@Z; Spectre::Framework::CalculateIndexedTangents<uint>(Spectre::Utils::Math::Vector3 const * const,uint,uint const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d0593  jmp     short loc_1800D05E2
0x1800d0595  mov     edx, [rsp+0E8h+arg_38]
0x1800d059c  mov     ecx, esi
0x1800d059e  call    Spectre__Framework__ValidateTopologyVertexCount
0x1800d05a3  mov     rax, [rsp+0E8h+arg_50]
0x1800d05ab  mov     [rsp+0E8h+var_B8], rax; bool
0x1800d05b0  mov     rax, [rsp+0E8h+var_98]
0x1800d05b5  mov     [rsp+0E8h+var_C0], rax; bool
0x1800d05ba  mov     rax, [rsp+0E8h+arg_58]
0x1800d05c2  mov     [rsp+0E8h+var_C8], rax; __int64
0x1800d05c7  mov     r9d, [rsp+0E8h+arg_38]
0x1800d05cf  mov     r8, [rsp+0E8h+var_60]
0x1800d05d7  mov     edx, esi
0x1800d05d9  mov     rcx, rdi; this
0x1800d05dc  call    ?CalculateNonIndexedTangents@Framework@Spectre@@YAXQEBUVector3@Math@Utils@2@IQEBUVector2@452@W4TriangularMeshTopology@GeometryUtils@12@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU3452@4@Z; Spectre::Framework::CalculateNonIndexedTangents(Spectre::Utils::Math::Vector3 const * const,uint,Spectre::Utils::Math::Vector2 const * const,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const,Spectre::Utils::Math::Vector3 * const)
0x1800d05e1  nop
0x1800d05e2  mov     al, byte ptr [rsp+0E8h+arg_40]
0x1800d05e9  mov     byte ptr [rsp+0E8h+var_C0], al; struct Spectre::Utils::Math::Vector3 *
0x1800d05ed  mov     rax, [rsp+0E8h+arg_50]
0x1800d05f5  mov     [rsp+0E8h+var_C8], rax; struct Spectre::Utils::Math::Vector3 *
0x1800d05fa  mov     r9, [rsp+0E8h+var_98]; struct Spectre::Utils::Math::Vector3 *
0x1800d05ff  mov     r8, [rsp+0E8h+var_90]; unsigned int
0x1800d0604  mov     edx, esi; struct Spectre::Utils::Math::Vector4 *
0x1800d0606  mov     rcx, [rsp+0E8h+var_78]; this
0x1800d060b  call    ?FinalizeVertexTangents@Spectre@@YAXPEAUVector4@Math@Utils@1@IPEBUVector3@341@11_N@Z; Spectre::FinalizeVertexTangents(Spectre::Utils::Math::Vector4 *,uint,Spectre::Utils::Math::Vector3 const *,Spectre::Utils::Math::Vector3 const *,Spectre::Utils::Math::Vector3 const *,bool)
0x1800d0610  lea     rdx, [rsp+0E8h+var_78]
0x1800d0615  mov     rdi, [rsp+0E8h+arg_48]
0x1800d061d  mov     rcx, rdi
0x1800d0620  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d0625  nop
0x1800d0626  lea     rcx, [rsp+0E8h+var_58]
0x1800d062e  call    ?_Tidy@?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Utils::Math::Vector3>::_Tidy(void)
0x1800d0633  nop
0x1800d0634  mov     rcx, [rsp+0E8h+var_78+8]; this
0x1800d0639  test    rcx, rcx
0x1800d063c  jz      short loc_1800D0644
0x1800d063e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0643  nop
0x1800d0644  mov     rcx, [r12+8]; this
0x1800d0649  test    rcx, rcx
0x1800d064c  jz      short loc_1800D0654
0x1800d064e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0653  nop
0x1800d0654  mov     rcx, [r13+8]; this
0x1800d0658  test    rcx, rcx
0x1800d065b  jz      short loc_1800D0663
0x1800d065d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0662  nop
0x1800d0663  mov     rcx, [r15+8]; this
0x1800d0667  test    rcx, rcx
0x1800d066a  jz      short loc_1800D0672
0x1800d066c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0671  nop
0x1800d0672  mov     rcx, [r14+8]
0x1800d0676  jmp     loc_1800D0387
0x1800d067b  jmp     short $+2
0x1800d067d  lea     rcx, [rsp+0E8h+var_58]
0x1800d0685  call    ?_Tidy@?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@AEAAXXZ; std::vector<Spectre::Utils::Math::Vector3>::_Tidy(void)
0x1800d068a  nop
0x1800d068b  mov     rcx, [rsp+0E8h+var_78+8]; this
0x1800d0690  test    rcx, rcx
0x1800d0693  jz      short loc_1800D069B
0x1800d0695  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d069a  nop
0x1800d069b  mov     rax, [rsp+0E8h+arg_0]
0x1800d06a3  mov     rcx, [rax+8]; this
0x1800d06a7  test    rcx, rcx
0x1800d06aa  jz      short loc_1800D06B2
0x1800d06ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d06b1  nop
0x1800d06b2  mov     rax, [rsp+0E8h+arg_8]
0x1800d06ba  mov     rcx, [rax+8]; this
0x1800d06be  test    rcx, rcx
0x1800d06c1  jz      short loc_1800D06C9
0x1800d06c3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d06c8  nop
0x1800d06c9  mov     rax, [rsp+0E8h+arg_10]
0x1800d06d1  mov     rcx, [rax+8]; this
0x1800d06d5  test    rcx, rcx
0x1800d06d8  jz      short loc_1800D06E0
0x1800d06da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d06df  nop
0x1800d06e0  mov     rax, [rsp+0E8h+arg_20]
0x1800d06e8  mov     rcx, [rax+8]; this
0x1800d06ec  test    rcx, rcx
0x1800d06ef  jz      short loc_1800D06F7
0x1800d06f1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d06f6  nop
0x1800d06f7  mov     rdi, [rsp+0E8h+arg_48]
0x1800d06ff  mov     rcx, [rdi+38h]
0x1800d0703  test    rcx, rcx
0x1800d0706  jz      short loc_1800D0722
0x1800d0708  cmp     rcx, rdi
0x1800d070b  mov     rax, [rcx]
0x1800d070e  setnz   dl
0x1800d0711  mov     rax, [rax+20h]
0x1800d0715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d071a  mov     qword ptr [rdi+38h], 0
0x1800d0722  mov     rsi, [rsp+0E8h+arg_18]
0x1800d072a  add     rsp, 0C0h
0x1800d0731  pop     r15
0x1800d0733  pop     r14
0x1800d0735  pop     r13
0x1800d0737  pop     r12
0x1800d0739  pop     rdi
0x1800d073a  retn
```

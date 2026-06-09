# Spectre::Framework::GeometryUtils::ComputeNormals(std::shared_ptr<Spectre::Utils::Math::Vector3>,uint,std::shared_ptr<void>,uint,bool,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::function<void (std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)>,void *,std::shared_ptr<Spectre::Utils::ICancellationToken> const &)

- ea: `0x1800cfffc`
- end: `0x1800d02d5`
- name: `?ComputeNormals@GeometryUtils@Framework@Spectre@@SAXV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@IV?$shared_ptr@X@5@I_NW4TriangularMeshTopology@123@V?$function@$$A6AXAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@PEAX@Z@5@PEAXAEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@5@@Z`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180044e64`

## callees

- `0x18000d678`
- `0x18000dfa2`
- `0x18001128c`
- `0x18001c290`
- `0x18003ae38`
- `0x1800cef68`
- `0x1800cf0f8`
- `0x1800cfa98`
- `0x1800cfab8`
- `0x1800cfb58`
- `0x1800cfffc`
- `0x1800d1130`
- `0x1800d11e8`
- `0x1800d12a0`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d009b`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_malloc` at `0x1800d009b`

## string_xrefs

- `0x1800d0026`: `ComputeNormals`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Spectre::Framework::GeometryUtils::ComputeNormals(
        Spectre **a1,
        unsigned int a2,
        _QWORD *a3,
        unsigned int a4,
        char a5,
        unsigned int a6,
        __int64 a7,
        char a8,
        __int64 a9)
{
  __int64 v11; // rdi
  __int64 v13; // rdi
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rcx
  std::_Ref_count_base *v17; // rcx
  std::_Ref_count_base *v18; // r15
  _DWORD *v19; // rax
  Spectre *v20; // r13
  __int64 i; // rdx
  int v22; // edx
  std::_Ref_count_base *v23; // rcx
  std::_Ref_count_base *v24; // rcx
  __int64 v25; // rcx
  const char *v26; // rax
  const Spectre::Framework::GeometryProcessingException *v27; // [rsp+40h] [rbp-68h] BYREF
  std::_Ref_count_base *v28[2]; // [rsp+48h] [rbp-60h] BYREF
  std::_Ref_count_base *v29[2]; // [rsp+58h] [rbp-50h] BYREF
  char v30; // [rsp+68h] [rbp-40h]
  _QWORD pExceptionObject[7]; // [rsp+70h] [rbp-38h] BYREF

  v11 = a2;
  if ( (unsigned __int8)Spectre::Framework::ValidateVertexCount(a2, "ComputeNormals") )
  {
    v18 = (std::_Ref_count_base *)_aligned_malloc(12 * v11, 0x10u);
    *(_OWORD *)v28 = 0;
    a8 = 0;
    v29[0] = v18;
    v29[1] = (std::_Ref_count_base *)&a8;
    v19 = operator new(0x18u);
    if ( v19 )
    {
      v19[2] = 1;
      v19[3] = 1;
      *(_QWORD *)v19 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_eee906239c744569acc5ea6e5be29b09_>::`vftable';
      *((_QWORD *)v19 + 2) = v18;
    }
    v28[0] = v18;
    v28[1] = (std::_Ref_count_base *)v19;
    v30 = 0;
    std::_Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___::__Temporary_owner_del_Spectre::Utils::Math::Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___(v29);
    if ( !v18 )
    {
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &stdext::bad_alloc::`vftable';
      throw (stdext::bad_alloc *)pExceptionObject;
    }
    memset_0(v18, 0, 12 * v11);
    try
    {
      v20 = *a1;
      if ( a5 )
      {
        if ( *a3 )
        {
          Spectre::Framework::ValidateTopologyIndexCount(a4, a6);
          Spectre::Framework::CalculateIndexedNormals<unsigned int>(v20, a6, a9, (bool)v28[0]);
        }
        else
        {
          Spectre::Framework::ValidateTopologyVertexCount((unsigned int)v11, a6);
          Spectre::Framework::CalculateNonIndexedNormals(v20, (bool)v28[0]);
        }
      }
      else
      {
        Spectre::Framework::ValidateTopologyIndexCount(a4, a6);
        Spectre::Framework::CalculateIndexedNormals<unsigned short>(v20, a6, a9, (bool)v28[0]);
      }
    }
    catch ( Spectre::Utils::CancelledException )
    {
      throw;
    }
    catch ( const Spectre::Framework::GeometryProcessingException *v27 )
    {
      v26 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr((char *)v27 + 16);
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, v26);
      *(_OWORD *)v29 = 0;
      std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a7, v29);
      if ( v29[1] )
        std::_Ref_count_base::_Decref(v29[1]);
      goto LABEL_23;
    }
    catch ( ... )
    {
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, "ComputeNormals threw unexpected exception");
      *(_OWORD *)v29 = 0;
      std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a7, v29);
      if ( v29[1] )
        std::_Ref_count_base::_Decref(v29[1]);
LABEL_23:
      if ( v28[1] )
        std::_Ref_count_base::_Decref(v28[1]);
      v23 = a1[1];
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      v24 = (std::_Ref_count_base *)a3[1];
      if ( v24 )
        std::_Ref_count_base::_Decref(v24);
      v13 = a7;
LABEL_30:
      v25 = *(_QWORD *)(v13 + 56);
      if ( v25 )
      {
        LOBYTE(v14) = v25 != v13;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL))(v25, v14);
        *(_QWORD *)(v13 + 56) = 0;
      }
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v11; i = (unsigned int)(v22 + 1) )
      Spectre::Utils::Math::Vector3::Normalize((std::_Ref_count_base *)((char *)v28[0] + 12 * i));
    v13 = a7;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a7, v28);
    v15 = v28[1];
  }
  else
  {
    *(_OWORD *)v29 = 0;
    v13 = a7;
    std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(a7, v29);
    v15 = v29[1];
  }
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v16 = a1[1];
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  v17 = (std::_Ref_count_base *)a3[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  goto LABEL_30;
}

```

## disassembly

```asm
0x1800cfffc  mov     [rsp+arg_8], rsi
0x1800d0001  mov     [rsp+arg_10], r8
0x1800d0006  mov     [rsp+arg_0], rcx
0x1800d000b  push    rdi
0x1800d000c  push    r12
0x1800d000e  push    r13
0x1800d0010  push    r14
0x1800d0012  push    r15
0x1800d0014  sub     rsp, 80h
0x1800d001b  mov     r14d, r9d
0x1800d001e  mov     rsi, r8
0x1800d0021  mov     edi, edx
0x1800d0023  mov     r12, rcx
0x1800d0026  lea     rdx, aComputenormals_0; "ComputeNormals"
0x1800d002d  mov     ecx, edi
0x1800d002f  call    Spectre__Framework__ValidateVertexCount
0x1800d0034  test    al, al
0x1800d0036  jnz     short loc_1800D008B
0x1800d0038  xorps   xmm0, xmm0
0x1800d003b  movdqu  xmmword ptr [rsp+0A8h+var_50], xmm0
0x1800d0041  lea     rdx, [rsp+0A8h+var_50]
0x1800d0046  mov     rdi, [rsp+0A8h+arg_30]
0x1800d004e  mov     rcx, rdi
0x1800d0051  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d0056  nop
0x1800d0057  mov     rcx, [rsp+0A8h+var_50+8]; this
0x1800d005c  test    rcx, rcx
0x1800d005f  jz      short loc_1800D0067
0x1800d0061  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0066  nop
0x1800d0067  mov     rcx, [r12+8]; this
0x1800d006c  test    rcx, rcx
0x1800d006f  jz      short loc_1800D0077
0x1800d0071  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0076  nop
0x1800d0077  mov     rcx, [rsi+8]; this
0x1800d007b  test    rcx, rcx
0x1800d007e  jz      short loc_1800D0086
0x1800d0080  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0085  nop
0x1800d0086  jmp     loc_1800D0299
0x1800d008b  lea     r13, [rdi+rdi*2]
0x1800d008f  shl     r13, 2
0x1800d0093  mov     edx, 10h; Alignment
0x1800d0098  mov     rcx, r13; Size
0x1800d009b  call    cs:__imp__aligned_malloc
0x1800d00a1  mov     r15, rax
0x1800d00a4  xorps   xmm0, xmm0
0x1800d00a7  movdqu  xmmword ptr [rsp+0A8h+var_60], xmm0
0x1800d00ad  mov     [rsp+0A8h+arg_38], 0
0x1800d00b5  mov     [rsp+0A8h+var_50], rax
0x1800d00ba  lea     rax, [rsp+0A8h+arg_38]
0x1800d00c2  mov     [rsp+0A8h+var_50+8], rax
0x1800d00c7  mov     ecx, 18h; unsigned __int64
0x1800d00cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d00d1  test    rax, rax
0x1800d00d4  jz      short loc_1800D00F2
0x1800d00d6  mov     dword ptr [rax+8], 1
0x1800d00dd  mov     dword ptr [rax+0Ch], 1
0x1800d00e4  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector3@Math@Utils@Spectre@@V_lambda_eee906239c744569acc5ea6e5be29b09_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_eee906239c744569acc5ea6e5be29b09_>::`vftable'
0x1800d00eb  mov     [rax], rcx
0x1800d00ee  mov     [rax+10h], r15
0x1800d00f2  mov     [rsp+0A8h+var_60], r15
0x1800d00f7  mov     [rsp+0A8h+var_60+8], rax
0x1800d00fc  mov     [rsp+0A8h+var_40], 0
0x1800d0101  lea     rcx, [rsp+0A8h+var_50]
0x1800d0106  call    std___Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6_______Temporary_owner_del_Spectre__Utils__Math__Vector4____lambda_dc718d396f0c2d0078465762313bdcf6___
0x1800d010b  nop
0x1800d010c  mov     rcx, [rsp+0A8h+var_60]; void *
0x1800d0111  test    rcx, rcx
0x1800d0114  jnz     short loc_1800D0140
0x1800d0116  lea     rax, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBE_KAEAY0IB@D@Z@4QBDB+40h; "bad allocation"
0x1800d011d  mov     [rsp+0A8h+var_30], rax
0x1800d0122  lea     rax, ??_7bad_alloc@stdext@@6B@; const stdext::bad_alloc::`vftable'
0x1800d0129  mov     [rsp+0A8h+pExceptionObject], rax
0x1800d012e  lea     rdx, _TI2?AVbad_alloc@stdext@@; pThrowInfo
0x1800d0135  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800d013a  call    _CxxThrowException_0
0x1800d0140  mov     r8, r13; Size
0x1800d0143  xor     edx, edx; Val
0x1800d0145  call    memset_0
0x1800d014a  mov     r13, [r12]
0x1800d014e  cmp     [rsp+0A8h+arg_20], 0
0x1800d0156  jnz     short loc_1800D0199
0x1800d0158  mov     r15d, [rsp+0A8h+arg_28]
0x1800d0160  mov     edx, r15d
0x1800d0163  mov     ecx, r14d
0x1800d0166  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d016b  mov     rax, [rsp+0A8h+var_60]
0x1800d0170  mov     qword ptr [rsp+0A8h+var_78], rax; bool
0x1800d0175  mov     rax, [rsp+0A8h+arg_40]
0x1800d017d  mov     [rsp+0A8h+var_80], rax; __int64
0x1800d0182  mov     dword ptr [rsp+0A8h+var_88], r15d; int
0x1800d0187  mov     r9d, r14d
0x1800d018a  mov     r8, [rsi]
0x1800d018d  mov     edx, edi
0x1800d018f  mov     rcx, r13; this
0x1800d0192  call    ??$CalculateIndexedNormals@G@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBGIW4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@@Z; Spectre::Framework::CalculateIndexedNormals<ushort>(Spectre::Utils::Math::Vector3 const * const,uint,ushort const * const,uint,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const)
0x1800d0197  jmp     short loc_1800D01DE
0x1800d0199  cmp     qword ptr [rsi], 0
0x1800d019d  jz      short loc_1800D01E0
0x1800d019f  mov     r15d, [rsp+0A8h+arg_28]
0x1800d01a7  mov     edx, r15d
0x1800d01aa  mov     ecx, r14d
0x1800d01ad  call    Spectre__Framework__ValidateTopologyIndexCount
0x1800d01b2  mov     rax, [rsp+0A8h+var_60]
0x1800d01b7  mov     qword ptr [rsp+0A8h+var_78], rax; bool
0x1800d01bc  mov     rax, [rsp+0A8h+arg_40]
0x1800d01c4  mov     [rsp+0A8h+var_80], rax; __int64
0x1800d01c9  mov     dword ptr [rsp+0A8h+var_88], r15d; int
0x1800d01ce  mov     r9d, r14d
0x1800d01d1  mov     r8, [rsi]
0x1800d01d4  mov     edx, edi
0x1800d01d6  mov     rcx, r13; this
0x1800d01d9  call    ??$CalculateIndexedNormals@I@Framework@Spectre@@YAXQEBUVector3@Math@Utils@1@IQEBIIW4TriangularMeshTopology@GeometryUtils@01@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU2341@@Z; Spectre::Framework::CalculateIndexedNormals<uint>(Spectre::Utils::Math::Vector3 const * const,uint,uint const * const,uint,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const)
0x1800d01de  jmp     short loc_1800D0213
0x1800d01e0  mov     edx, [rsp+0A8h+arg_28]
0x1800d01e7  mov     ecx, edi
0x1800d01e9  call    Spectre__Framework__ValidateTopologyVertexCount
0x1800d01ee  mov     rax, [rsp+0A8h+var_60]
0x1800d01f3  mov     qword ptr [rsp+0A8h+var_88], rax; bool
0x1800d01f8  mov     r9, [rsp+0A8h+arg_40]
0x1800d0200  mov     r8d, [rsp+0A8h+arg_28]
0x1800d0208  mov     edx, edi
0x1800d020a  mov     rcx, r13; this
0x1800d020d  call    ?CalculateNonIndexedNormals@Framework@Spectre@@YAXQEBUVector3@Math@Utils@2@IW4TriangularMeshTopology@GeometryUtils@12@AEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@std@@QEAU3452@@Z; Spectre::Framework::CalculateNonIndexedNormals(Spectre::Utils::Math::Vector3 const * const,uint,Spectre::Framework::GeometryUtils::TriangularMeshTopology,std::shared_ptr<Spectre::Utils::ICancellationToken> const &,Spectre::Utils::Math::Vector3 * const)
0x1800d0212  nop
0x1800d0213  xor     edx, edx
0x1800d0215  test    edi, edi
0x1800d0217  jz      short loc_1800D0231
0x1800d0219  lea     rcx, [rdx+rdx*2]
0x1800d021d  mov     rax, [rsp+0A8h+var_60]
0x1800d0222  lea     rcx, [rax+rcx*4]; this
0x1800d0226  call    ?Normalize@Vector3@Math@Utils@Spectre@@QEAAXXZ; Spectre::Utils::Math::Vector3::Normalize(void)
0x1800d022b  inc     edx
0x1800d022d  cmp     edx, edi
0x1800d022f  jb      short loc_1800D0219
0x1800d0231  lea     rdx, [rsp+0A8h+var_60]
0x1800d0236  mov     rdi, [rsp+0A8h+arg_30]
0x1800d023e  mov     rcx, rdi
0x1800d0241  call    ??R?$_Func_class@XAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@PEAX@std@@QEBAXAEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@1@PEAX@Z; std::_Func_class<void,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *>::operator()(std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)
0x1800d0246  nop
0x1800d0247  mov     rcx, [rsp+0A8h+var_60+8]
0x1800d024c  jmp     loc_1800D005C
0x1800d0251  jmp     short $+2
0x1800d0253  mov     rcx, [rsp+0A8h+var_60+8]; this
0x1800d0258  test    rcx, rcx
0x1800d025b  jz      short loc_1800D0263
0x1800d025d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0262  nop
0x1800d0263  mov     rax, [rsp+0A8h+arg_0]
0x1800d026b  mov     rcx, [rax+8]; this
0x1800d026f  test    rcx, rcx
0x1800d0272  jz      short loc_1800D027A
0x1800d0274  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0279  nop
0x1800d027a  mov     rax, [rsp+0A8h+arg_10]
0x1800d0282  mov     rcx, [rax+8]; this
0x1800d0286  test    rcx, rcx
0x1800d0289  jz      short loc_1800D0291
0x1800d028b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d0290  nop
0x1800d0291  mov     rdi, [rsp+0A8h+arg_30]
0x1800d0299  mov     rcx, [rdi+38h]
0x1800d029d  test    rcx, rcx
0x1800d02a0  jz      short loc_1800D02BC
0x1800d02a2  cmp     rcx, rdi
0x1800d02a5  mov     rax, [rcx]
0x1800d02a8  setnz   dl
0x1800d02ab  mov     rax, [rax+20h]
0x1800d02af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d02b4  mov     qword ptr [rdi+38h], 0
0x1800d02bc  mov     rsi, [rsp+0A8h+arg_8]
0x1800d02c4  add     rsp, 80h
0x1800d02cb  pop     r15
0x1800d02cd  pop     r14
0x1800d02cf  pop     r13
0x1800d02d1  pop     r12
0x1800d02d3  pop     rdi
0x1800d02d4  retn
```

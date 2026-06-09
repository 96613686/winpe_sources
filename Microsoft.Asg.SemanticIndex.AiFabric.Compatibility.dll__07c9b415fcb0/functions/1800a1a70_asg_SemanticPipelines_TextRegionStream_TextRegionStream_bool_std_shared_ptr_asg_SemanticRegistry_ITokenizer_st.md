# asg::SemanticPipelines::TextRegionStream::TextRegionStream(bool,std::shared_ptr<asg::SemanticRegistry::ITokenizer>,std::shared_ptr<asg::SemanticRegistry::ModelDescriptor const>,std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::ExecutionPriorityHint)

- ea: `0x1800a1a70`
- end: `0x1800a1dbc`
- name: `??0TextRegionStream@SemanticPipelines@asg@@QEAA@_NV?$shared_ptr@VITokenizer@SemanticRegistry@asg@@@std@@V?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@4@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@4@W4EmbeddingElementType@SemanticRegistry@2@W4ExecutionPriorityHint@82@@Z`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800a2aa0`

## callees

- `0x180004140`
- `0x180078ed0`
- `0x1800a1a70`
- `0x1801f7190`
- `0x1801f97e0`
- `0x1802114e0`

## string_xrefs

- `0x1800a1cfd`: `maxTokenCount`
- `0x1800a1d53`: `tokenizer`
- `0x1800a1d76`: `modelDescriptor`
- `0x1800a1d99`: `textModelAccessor`
- `0x1800a1d3c`: `__cdecl asg::SemanticPipelines::TextRegionStream::TextRegionStream(bool,class std::shared_ptr<class asg::SemanticRegistry::ITokenizer>,class std::shared_ptr<struct asg::SemanticRegistry::ModelDescriptor const >,class std::shared_ptr<struct asg::SemanticPipelines::ITextModelAccessor>,enum asg::SemanticRegistry::EmbeddingElementType,enum asg::SemanticRegistry::ExecutionPriorityHint)`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall asg::SemanticPipelines::TextRegionStream::TextRegionStream(
        __int64 a1,
        char a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        int a6,
        int a7)
{
  char *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  float v15; // xmm0_4
  double v16; // xmm1_8
  __int64 v17; // rcx
  double v18; // xmm0_8
  __int64 v19; // rax
  double v20; // xmm0_8
  unsigned __int64 v21; // rcx
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 *v24; // rdi
  _DWORD pExceptionObject[2]; // [rsp+20h] [rbp-88h] BYREF
  const char *v27; // [rsp+28h] [rbp-80h]
  const char *v28; // [rsp+30h] [rbp-78h]
  __int64 v29; // [rsp+48h] [rbp-60h]
  _QWORD *v30; // [rsp+50h] [rbp-58h]
  _QWORD *v31; // [rsp+58h] [rbp-50h]
  _QWORD *v32; // [rsp+60h] [rbp-48h]

  v29 = a1;
  v30 = a3;
  v31 = a4;
  v32 = a5;
  v11 = (char *)operator new(0x50u);
  if ( v11 )
  {
    *(_QWORD *)v11 = 2;
    *(_OWORD *)(v11 + 24) = 0;
    *(_OWORD *)(v11 + 40) = 0;
    *(_OWORD *)(v11 + 56) = 0;
    *((_QWORD *)v11 + 1) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_DWORD *)v11 + 18) = -1;
    *((_DWORD *)v11 + 19) = 0;
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)a1 = v11;
  *(_BYTE *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = *a3;
  *(_QWORD *)(a1 + 32) = a3[1];
  *a3 = 0;
  a3[1] = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 40) = *a5;
  *(_QWORD *)(a1 + 48) = a5[1];
  *a5 = 0;
  a5[1] = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 64) = *a4;
  *(_QWORD *)(a1 + 72) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 7;
  *(_WORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = a6;
  *(_BYTE *)(a1 + 124) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_DWORD *)(a1 + 136) = a7;
  v12 = *(_QWORD *)(a1 + 24);
  if ( !v12 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "tokenizer");
    throw (std::invalid_argument *)pExceptionObject;
  }
  v13 = *(_QWORD *)(a1 + 64);
  if ( !v13 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "modelDescriptor");
    throw (std::invalid_argument *)pExceptionObject;
  }
  if ( !*(_QWORD *)(a1 + 40) )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "textModelAccessor");
    throw (std::invalid_argument *)pExceptionObject;
  }
  v14 = *(_QWORD *)(v13 + 128);
  *(_QWORD *)(a1 + 8) = v14;
  if ( !v14 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "maxTokenCount");
    throw (std::invalid_argument *)pExceptionObject;
  }
  *(_DWORD *)(a1 + 56) = _mm_cvtsi128_si32(*(__m128i *)(v13 + 120));
  v15 = (*(float (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v15 < 1.0 )
  {
    pExceptionObject[0] = 100;
    pExceptionObject[1] = 13;
    v27 = "C:\\__w\\1\\s\\src\\SemanticPipelines\\internal\\libSemanticPipelines\\include\\SemanticPipelines\\TextRegionStream.h";
    v28 = "__cdecl asg::SemanticPipelines::TextRegionStream::TextRegionStream(bool,class std::shared_ptr<class asg::Seman"
          "ticRegistry::ITokenizer>,class std::shared_ptr<struct asg::SemanticRegistry::ModelDescriptor const >,class std"
          "::shared_ptr<struct asg::SemanticPipelines::ITextModelAccessor>,enum asg::SemanticRegistry::EmbeddingElementTy"
          "pe,enum asg::SemanticRegistry::ExecutionPriorityHint)";
    asg::details::AsgAssertFail(pExceptionObject);
  }
  v16 = v15 * 4.0;
  v17 = *(_QWORD *)(a1 + 8);
  if ( v17 < 0 )
  {
    v19 = *(_QWORD *)(a1 + 8) & 1LL | ((unsigned __int64)v17 >> 1);
    v18 = (double)(int)v19 + (double)(int)v19;
  }
  else
  {
    v18 = (double)(int)v17;
  }
  v20 = ceil(v18 * v16);
  v21 = 0;
  if ( v20 >= 9.223372036854776e18 )
  {
    v20 = v20 - 9.223372036854776e18;
    if ( v20 < 9.223372036854776e18 )
      v21 = 0x8000000000000000uLL;
  }
  *(_QWORD *)(a1 + 128) = v21 + (unsigned int)(int)v20;
  v22 = (volatile signed __int32 *)a3[1];
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = (volatile signed __int32 *)a4[1];
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  v24 = (volatile signed __int32 *)a5[1];
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800a1a70  push    rbx
0x1800a1a72  push    rbp
0x1800a1a73  push    rsi
0x1800a1a74  push    rdi
0x1800a1a75  push    r12
0x1800a1a77  push    r14
0x1800a1a79  push    r15
0x1800a1a7b  sub     rsp, 70h
0x1800a1a7f  mov     r14, r9
0x1800a1a82  mov     rdi, r8
0x1800a1a85  movzx   ebp, dl
0x1800a1a88  mov     rbx, rcx
0x1800a1a8b  mov     [rsp+0A8h+var_60], rcx
0x1800a1a90  mov     [rsp+0A8h+var_58], r8
0x1800a1a95  mov     [rsp+0A8h+var_50], r9
0x1800a1a9a  mov     r15, [rsp+0A8h+arg_20]
0x1800a1aa2  mov     [rsp+0A8h+var_48], r15
0x1800a1aa7  xor     r12d, r12d
0x1800a1aaa  mov     ecx, 50h ; 'P'; Size
0x1800a1aaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a1ab4  mov     esi, 0FFFFFFFFh
0x1800a1ab9  test    rax, rax
0x1800a1abc  jz      short loc_1800A1AE5
0x1800a1abe  mov     qword ptr [rax], 2
0x1800a1ac5  xorps   xmm0, xmm0
0x1800a1ac8  movups  xmmword ptr [rax+18h], xmm0
0x1800a1acc  movups  xmmword ptr [rax+28h], xmm0
0x1800a1ad0  movups  xmmword ptr [rax+38h], xmm0
0x1800a1ad4  mov     [rax+8], r12
0x1800a1ad8  mov     [rax+10h], r12
0x1800a1adc  mov     [rax+48h], esi
0x1800a1adf  mov     [rax+4Ch], r12d
0x1800a1ae3  jmp     short loc_1800A1AE8
0x1800a1ae5  mov     rax, r12
0x1800a1ae8  mov     [rbx], rax
0x1800a1aeb  mov     [rbx+10h], bpl
0x1800a1aef  mov     [rbx+18h], r12
0x1800a1af3  mov     [rbx+20h], r12
0x1800a1af7  mov     rax, [rdi]
0x1800a1afa  mov     [rbx+18h], rax
0x1800a1afe  mov     rax, [rdi+8]
0x1800a1b02  mov     [rbx+20h], rax
0x1800a1b06  mov     [rdi], r12
0x1800a1b09  mov     [rdi+8], r12
0x1800a1b0d  mov     [rbx+28h], r12
0x1800a1b11  mov     [rbx+30h], r12
0x1800a1b15  mov     rax, [r15]
0x1800a1b18  mov     [rbx+28h], rax
0x1800a1b1c  mov     rax, [r15+8]
0x1800a1b20  mov     [rbx+30h], rax
0x1800a1b24  mov     [r15], r12
0x1800a1b27  mov     [r15+8], r12
0x1800a1b2b  mov     [rbx+40h], r12
0x1800a1b2f  mov     [rbx+48h], r12
0x1800a1b33  mov     rax, [r14]
0x1800a1b36  mov     [rbx+40h], rax
0x1800a1b3a  mov     rax, [r14+8]
0x1800a1b3e  mov     [rbx+48h], rax
0x1800a1b42  mov     [r14], r12
0x1800a1b45  mov     [r14+8], r12
0x1800a1b49  xorps   xmm0, xmm0
0x1800a1b4c  movups  xmmword ptr [rbx+50h], xmm0
0x1800a1b50  mov     [rbx+60h], r12
0x1800a1b54  mov     qword ptr [rbx+68h], 7
0x1800a1b5c  mov     [rbx+50h], r12w
0x1800a1b61  mov     [rbx+70h], r12
0x1800a1b65  mov     eax, [rsp+0A8h+arg_28]
0x1800a1b6c  mov     [rbx+78h], eax
0x1800a1b6f  mov     byte ptr [rbx+7Ch], 0
0x1800a1b73  mov     [rbx+80h], r12
0x1800a1b7a  mov     eax, [rsp+0A8h+arg_30]
0x1800a1b81  mov     [rbx+88h], eax
0x1800a1b87  mov     rdx, [rbx+18h]
0x1800a1b8b  test    rdx, rdx
0x1800a1b8e  jz      loc_1800A1D53
0x1800a1b94  mov     rcx, [rbx+40h]
0x1800a1b98  test    rcx, rcx
0x1800a1b9b  jz      loc_1800A1D76
0x1800a1ba1  cmp     qword ptr [rbx+28h], 0
0x1800a1ba6  jz      loc_1800A1D99
0x1800a1bac  mov     rax, [rcx+80h]
0x1800a1bb3  mov     [rbx+8], rax
0x1800a1bb7  test    rax, rax
0x1800a1bba  jz      loc_1800A1CFD
0x1800a1bc0  movups  xmm0, xmmword ptr [rcx+78h]
0x1800a1bc4  movd    dword ptr [rbx+38h], xmm0
0x1800a1bc9  mov     rax, [rdx]
0x1800a1bcc  mov     rcx, rdx
0x1800a1bcf  call    qword ptr [rax+10h]
0x1800a1bd2  comiss  xmm0, cs:__real@3f800000
0x1800a1bd9  jb      loc_1800A1D20
0x1800a1bdf  xorps   xmm1, xmm1
0x1800a1be2  cvtss2sd xmm1, xmm0
0x1800a1be6  mulsd   xmm1, cs:__real@4010000000000000
0x1800a1bee  mov     rcx, [rbx+8]
0x1800a1bf2  xorps   xmm0, xmm0
0x1800a1bf5  test    rcx, rcx
0x1800a1bf8  js      short loc_1800A1C01
0x1800a1bfa  cvtsi2sd xmm0, rcx
0x1800a1bff  jmp     short loc_1800A1C16
0x1800a1c01  mov     rax, rcx
0x1800a1c04  shr     rax, 1
0x1800a1c07  and     ecx, 1
0x1800a1c0a  or      rax, rcx
0x1800a1c0d  cvtsi2sd xmm0, rax
0x1800a1c12  addsd   xmm0, xmm0
0x1800a1c16  mulsd   xmm0, xmm1; X
0x1800a1c1a  call    ceil
0x1800a1c1f  xor     ecx, ecx
0x1800a1c21  movsd   xmm1, cs:__real@43e0000000000000
0x1800a1c29  comisd  xmm0, xmm1
0x1800a1c2d  jb      short loc_1800A1C46
0x1800a1c2f  subsd   xmm0, xmm1
0x1800a1c33  comisd  xmm0, xmm1
0x1800a1c37  jnb     short loc_1800A1C46
0x1800a1c39  mov     rax, 8000000000000000h
0x1800a1c43  mov     rcx, rax
0x1800a1c46  cvttsd2si rax, xmm0
0x1800a1c4b  add     rax, rcx
0x1800a1c4e  mov     [rbx+80h], rax
0x1800a1c55  mov     rdi, [rdi+8]
0x1800a1c59  test    rdi, rdi
0x1800a1c5c  jz      short loc_1800A1C88
0x1800a1c5e  mov     eax, esi
0x1800a1c60  lock xadd [rdi+8], eax
0x1800a1c65  cmp     eax, 1
0x1800a1c68  jnz     short loc_1800A1C88
0x1800a1c6a  mov     rax, [rdi]
0x1800a1c6d  mov     rcx, rdi
0x1800a1c70  call    qword ptr [rax]
0x1800a1c72  mov     eax, esi
0x1800a1c74  lock xadd [rdi+0Ch], eax
0x1800a1c79  cmp     eax, 1
0x1800a1c7c  jnz     short loc_1800A1C88
0x1800a1c7e  mov     rax, [rdi]
0x1800a1c81  mov     rcx, rdi
0x1800a1c84  call    qword ptr [rax+8]
0x1800a1c87  nop
0x1800a1c88  mov     rdi, [r14+8]
0x1800a1c8c  test    rdi, rdi
0x1800a1c8f  jz      short loc_1800A1CBB
0x1800a1c91  mov     eax, esi
0x1800a1c93  lock xadd [rdi+8], eax
0x1800a1c98  cmp     eax, 1
0x1800a1c9b  jnz     short loc_1800A1CBB
0x1800a1c9d  mov     rax, [rdi]
0x1800a1ca0  mov     rcx, rdi
0x1800a1ca3  call    qword ptr [rax]
0x1800a1ca5  mov     eax, esi
0x1800a1ca7  lock xadd [rdi+0Ch], eax
0x1800a1cac  cmp     eax, 1
0x1800a1caf  jnz     short loc_1800A1CBB
0x1800a1cb1  mov     rax, [rdi]
0x1800a1cb4  mov     rcx, rdi
0x1800a1cb7  call    qword ptr [rax+8]
0x1800a1cba  nop
0x1800a1cbb  mov     rdi, [r15+8]
0x1800a1cbf  test    rdi, rdi
0x1800a1cc2  jz      short loc_1800A1CEB
0x1800a1cc4  mov     eax, esi
0x1800a1cc6  lock xadd [rdi+8], eax
0x1800a1ccb  cmp     eax, 1
0x1800a1cce  jnz     short loc_1800A1CEB
0x1800a1cd0  mov     rax, [rdi]
0x1800a1cd3  mov     rcx, rdi
0x1800a1cd6  call    qword ptr [rax]
0x1800a1cd8  lock xadd [rdi+0Ch], esi
0x1800a1cdd  cmp     esi, 1
0x1800a1ce0  jnz     short loc_1800A1CEB
0x1800a1ce2  mov     rdx, [rdi]
0x1800a1ce5  mov     rcx, rdi
0x1800a1ce8  call    qword ptr [rdx+8]
0x1800a1ceb  mov     rax, rbx
0x1800a1cee  add     rsp, 70h
0x1800a1cf2  pop     r15
0x1800a1cf4  pop     r14
0x1800a1cf6  pop     r12
0x1800a1cf8  pop     rdi
0x1800a1cf9  pop     rsi
0x1800a1cfa  pop     rbp
0x1800a1cfb  pop     rbx
0x1800a1cfc  retn
0x1800a1cfd  lea     rdx, aMaxtokencount; "maxTokenCount"
0x1800a1d04  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1800a1d09  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800a1d0e  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800a1d15  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800a1d1a  call    _CxxThrowException
0x1800a1d20  mov     [rsp+0A8h+pExceptionObject], 64h ; 'd'
0x1800a1d28  mov     [rsp+0A8h+var_84], 0Dh
0x1800a1d30  lea     rax, aCW1SSrcSemanti_5; "C:\\__w\\1\\s\\src\\SemanticPipelines\\"...
0x1800a1d37  mov     [rsp+0A8h+var_80], rax
0x1800a1d3c  lea     rdx, aCdeclAsgSemant_2; "__cdecl asg::SemanticPipelines::TextReg"...
0x1800a1d43  mov     [rsp+0A8h+var_78], rdx
0x1800a1d48  lea     rcx, [rsp+0A8h+pExceptionObject]
0x1800a1d4d  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x1800a1d53  lea     rdx, aTokenizer; "tokenizer"
0x1800a1d5a  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1800a1d5f  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800a1d64  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800a1d6b  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800a1d70  call    _CxxThrowException
0x1800a1d76  lea     rdx, aModeldescripto; "modelDescriptor"
0x1800a1d7d  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1800a1d82  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800a1d87  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800a1d8e  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800a1d93  call    _CxxThrowException
0x1800a1d99  lea     rdx, aTextmodelacces; "textModelAccessor"
0x1800a1da0  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x1800a1da5  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800a1daa  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800a1db1  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800a1db6  call    _CxxThrowException
```

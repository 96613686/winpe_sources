# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::FromMatchResult(asg::SemanticIndex::ItemMatch const &,uint)

- ea: `0x180054fd0`
- end: `0x1800551c4`
- name: `?FromMatchResult@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUItemQueryMatch@345678@AEBUItemMatch@5asg@@I@Z`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180055350`

## callees

- `0x180003bd0`
- `0x180010dd0`
- `0x180054fd0`
- `0x1800551d0`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x180055057`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18005500a`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180055015`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibilit`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::FromMatchResult(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        int a4)
{
  int v7; // eax
  _QWORD *v8; // rdi
  float v9; // xmm6_4
  _QWORD *v10; // rbx
  _QWORD *v11; // rdi
  _QWORD *v13; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v15[2]; // [rsp+50h] [rbp-30h] BYREF
  const char *v16; // [rsp+58h] [rbp-28h]
  const char *v17; // [rsp+60h] [rbp-20h]
  _QWORD *pExceptionObject; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v19; // [rsp+C0h] [rbp+40h] BYREF

  v15[0] = 1825;
  v15[1] = 20;
  v16 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  v17 = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg::S"
        "emanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexS"
        "tore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt:"
        ":Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::M"
        "icrosoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::Sem"
        "anticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::TryGetEmbedding(const struct asg:"
        ":SemanticIndex::ItemEmbeddingKey &)";
  v14[0] = a1;
  v14[1] = a3;
  ___InvokeDbMethod_V_lambda_1___1__TryGetEmbedding___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUEmbedding_56789winrt__AEBUItemEmbeddingKey_7asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1__TryGetEmbedding_01234567_AEAA_AUEmbedding_234567_AEBUItemEmbeddingKey_4asg___Z___Q6AXX_EAEBUsource_location_std___Z(
    a1,
    &v19,
    v14);
  if ( !v19 )
  {
    LODWORD(pExceptionObject) = 102;
    throw (winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResultStatus *)&pExceptionObject;
  }
  pExceptionObject = 0;
  v15[0] = 373;
  v16 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Microso"
        "ft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v19 + 64LL))(v19, &pExceptionObject);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v15);
  }
  v8 = pExceptionObject;
  v14[0] = pExceptionObject;
  if ( !pExceptionObject )
  {
    LODWORD(pExceptionObject) = 103;
    throw (winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResultStatus *)&pExceptionObject;
  }
  v9 = *(double *)(a3 + 48);
  v10 = operator new(0x60u);
  v13 = v10;
  (*(void (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
  v13 = v8;
  v10[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IItemQueryMatch>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v10[1] = 1;
  *v10 = &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch::`vftable';
  *((_DWORD *)v10 + 6) = a4;
  v11 = pExceptionObject;
  v10[4] = pExceptionObject;
  if ( v11 )
    (*(void (__fastcall **)(_QWORD *))(*v11 + 8LL))(v11);
  *((float *)v10 + 10) = v9;
  *((_OWORD *)v10 + 3) = *(_OWORD *)a3;
  *((_OWORD *)v10 + 4) = *(_OWORD *)(a3 + 16);
  *((_OWORD *)v10 + 5) = *(_OWORD *)(a3 + 32);
  if ( v11 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v13);
  *v10 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch>::`vftable';
  *a2 = v10 + 2;
  if ( v11 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v14);
  if ( v19 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v19);
  return a2;
}

```

## disassembly

```asm
0x180054fd0  mov     [rsp-28h+arg_8], rbx
0x180054fd5  mov     [rsp-28h+arg_18], rsi
0x180054fda  push    rbp
0x180054fdb  push    rdi
0x180054fdc  push    r12
0x180054fde  push    r14
0x180054fe0  push    r15
0x180054fe2  mov     rbp, rsp
0x180054fe5  sub     rsp, 80h
0x180054fec  movaps  [rsp+80h+var_10], xmm6
0x180054ff1  mov     r12d, r9d
0x180054ff4  mov     rsi, r8
0x180054ff7  mov     r14, rdx
0x180054ffa  xor     ebx, ebx
0x180054ffc  mov     [rbp+var_30], 721h
0x180055003  mov     [rbp+var_2C], 14h
0x18005500a  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180055011  mov     [rbp+var_28], rax
0x180055015  lea     rax, aStructWinrtMic_28; "struct winrt::Microsoft::Asg::SemanticI"...
0x18005501c  mov     [rbp+var_20], rax
0x180055020  mov     [rbp+var_40], rcx
0x180055024  mov     [rbp+var_38], r8
0x180055028  lea     rax, [rbp+var_30]
0x18005502c  mov     [rsp+80h+var_60], rax
0x180055031  lea     r8, [rbp+var_40]
0x180055035  lea     rdx, [rbp+arg_10]
0x180055039  call    ??$InvokeDbMethod@V_lambda_1_@?1??TryGetEmbedding@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUEmbedding@56789winrt@@AEBUItemEmbeddingKey@7asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??TryGetEmbedding@01234567@AEAA?AUEmbedding@234567@AEBUItemEmbeddingKey@4asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x18005503e  nop
0x18005503f  mov     rcx, [rbp+arg_10]
0x180055043  test    rcx, rcx
0x180055046  jz      loc_18005519D
0x18005504c  mov     [rbp+pExceptionObject], rbx
0x180055050  mov     [rbp+var_30], 175h
0x180055057  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18005505e  mov     [rbp+var_28], rax
0x180055062  mov     [rbp+var_20], rbx
0x180055066  mov     rax, [rcx]
0x180055069  lea     rdx, [rbp+pExceptionObject]
0x18005506d  mov     rax, [rax+40h]
0x180055071  call    cs:__guard_dispatch_icall_fptr
0x180055077  test    eax, eax
0x180055079  js      loc_1800551B5
0x18005507f  mov     rdi, [rbp+pExceptionObject]
0x180055083  mov     [rbp+var_40], rdi
0x180055087  test    rdi, rdi
0x18005508a  jz      loc_180055185
0x180055090  movsd   xmm6, qword ptr [rsi+30h]
0x180055095  cvtpd2ps xmm6, xmm6
0x180055099  mov     ecx, 60h ; '`'; Size
0x18005509e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800550a3  mov     rbx, rax
0x1800550a6  mov     [rbp+var_48], rax
0x1800550aa  test    rdi, rdi
0x1800550ad  jz      short loc_1800550BF
0x1800550af  mov     rcx, [rdi]
0x1800550b2  mov     rax, [rcx+8]
0x1800550b6  mov     rcx, rdi
0x1800550b9  call    cs:__guard_dispatch_icall_fptr
0x1800550bf  mov     [rbp+var_48], rdi
0x1800550c3  lea     r15, [rbx+10h]
0x1800550c7  lea     rax, ??_7?$produce@UItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIItemQueryMatch@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IItemQueryMatch>::`vftable'
0x1800550ce  mov     [r15], rax
0x1800550d1  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800550d8  mov     qword ptr [rbx+8], 1
0x1800550e0  lea     rax, ??_7ItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch::`vftable'
0x1800550e7  mov     [rbx], rax
0x1800550ea  mov     [rbx+18h], r12d
0x1800550ee  mov     rdi, [rbp+pExceptionObject]
0x1800550f2  mov     [rbx+20h], rdi
0x1800550f6  test    rdi, rdi
0x1800550f9  jz      short loc_18005510B
0x1800550fb  mov     rax, [rdi]
0x1800550fe  mov     rcx, rdi
0x180055101  mov     rax, [rax+8]
0x180055105  call    cs:__guard_dispatch_icall_fptr
0x18005510b  movss   dword ptr [rbx+28h], xmm6
0x180055110  movups  xmm0, xmmword ptr [rsi]
0x180055113  movups  xmmword ptr [rbx+30h], xmm0
0x180055117  movups  xmm1, xmmword ptr [rsi+10h]
0x18005511b  movups  xmmword ptr [rbx+40h], xmm1
0x18005511f  movups  xmm0, xmmword ptr [rsi+20h]
0x180055123  movups  xmmword ptr [rbx+50h], xmm0
0x180055127  test    rdi, rdi
0x18005512a  jz      short loc_180055135
0x18005512c  lea     rcx, [rbp+var_48]
0x180055130  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180055135  lea     rax, ??_7?$heap_implements@UItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch>::`vftable'
0x18005513c  mov     [rbx], rax
0x18005513f  mov     [r14], r15
0x180055142  test    rdi, rdi
0x180055145  jz      short loc_180055151
0x180055147  lea     rcx, [rbp+var_40]
0x18005514b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180055150  nop
0x180055151  cmp     [rbp+arg_10], 0
0x180055156  jz      short loc_180055161
0x180055158  lea     rcx, [rbp+arg_10]
0x18005515c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180055161  mov     rax, r14
0x180055164  lea     r11, [rsp+80h+var_s0]
0x18005516c  mov     rbx, [r11+38h]
0x180055170  mov     rsi, [r11+48h]
0x180055174  movaps  xmm6, [rsp+80h+var_10]
0x180055179  mov     rsp, r11
0x18005517c  pop     r15
0x18005517e  pop     r14
0x180055180  pop     r12
0x180055182  pop     rdi
0x180055183  pop     rbp
0x180055184  retn
0x180055185  mov     dword ptr [rbp+pExceptionObject], 67h ; 'g'
0x18005518c  lea     rdx, _TI1?AW4QueryResultStatus@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@; pThrowInfo
0x180055193  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180055197  call    _CxxThrowException
0x18005519d  mov     dword ptr [rbp+pExceptionObject], 66h ; 'f'
0x1800551a4  lea     rdx, _TI1?AW4QueryResultStatus@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@; pThrowInfo
0x1800551ab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800551af  call    _CxxThrowException
0x1800551b5  lfence
0x1800551b8  lea     rdx, [rbp+var_30]
0x1800551bc  mov     ecx, eax
0x1800551be  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

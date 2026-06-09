# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::FromMatchResult(asg::SemanticIndex::ItemMatch const &,uint)

- ea: `0x18002f3d0`
- end: `0x18002f5c4`
- name: `?FromMatchResult@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUItemQueryMatch@345678@AEBUItemMatch@5asg@@I@Z`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180031170`

## callees

- `0x180003bd0`
- `0x180010dd0`
- `0x18002f3d0`
- `0x18002f890`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x18002f457`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18002f40a`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18002f415`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::FromMatchResult(
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
        "tore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt"
        "::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt:"
        ":Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::S"
        "emanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::TryGetEmbedding(const struct as"
        "g::SemanticIndex::ItemEmbeddingKey &)";
  v14[0] = a1;
  v14[1] = a3;
  ___InvokeDbMethod_V_lambda_1___1__TryGetEmbedding___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUEmbedding_56789winrt__AEBUItemEmbeddingKey_7asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1__TryGetEmbedding_01234567_AEAA_AUEmbedding_234567_AEBUItemEmbeddingKey_4asg___Z___Q6AXX_EAEBUsource_location_std___Z(
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
0x18002f3d0  mov     [rsp-28h+arg_8], rbx
0x18002f3d5  mov     [rsp-28h+arg_18], rsi
0x18002f3da  push    rbp
0x18002f3db  push    rdi
0x18002f3dc  push    r12
0x18002f3de  push    r14
0x18002f3e0  push    r15
0x18002f3e2  mov     rbp, rsp
0x18002f3e5  sub     rsp, 80h
0x18002f3ec  movaps  [rsp+80h+var_10], xmm6
0x18002f3f1  mov     r12d, r9d
0x18002f3f4  mov     rsi, r8
0x18002f3f7  mov     r14, rdx
0x18002f3fa  xor     ebx, ebx
0x18002f3fc  mov     [rbp+var_30], 721h
0x18002f403  mov     [rbp+var_2C], 14h
0x18002f40a  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18002f411  mov     [rbp+var_28], rax
0x18002f415  lea     rax, aStructWinrtMic_8; "struct winrt::Microsoft::Asg::SemanticI"...
0x18002f41c  mov     [rbp+var_20], rax
0x18002f420  mov     [rbp+var_40], rcx
0x18002f424  mov     [rbp+var_38], r8
0x18002f428  lea     rax, [rbp+var_30]
0x18002f42c  mov     [rsp+80h+var_60], rax
0x18002f431  lea     r8, [rbp+var_40]
0x18002f435  lea     rdx, [rbp+arg_10]
0x18002f439  call    ??$InvokeDbMethod@V_lambda_1_@?1??TryGetEmbedding@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUEmbedding@56789winrt@@AEBUItemEmbeddingKey@7asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??TryGetEmbedding@01234567@AEAA?AUEmbedding@234567@AEBUItemEmbeddingKey@4asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x18002f43e  nop
0x18002f43f  mov     rcx, [rbp+arg_10]
0x18002f443  test    rcx, rcx
0x18002f446  jz      loc_18002F59D
0x18002f44c  mov     [rbp+pExceptionObject], rbx
0x18002f450  mov     [rbp+var_30], 175h
0x18002f457  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18002f45e  mov     [rbp+var_28], rax
0x18002f462  mov     [rbp+var_20], rbx
0x18002f466  mov     rax, [rcx]
0x18002f469  lea     rdx, [rbp+pExceptionObject]
0x18002f46d  mov     rax, [rax+40h]
0x18002f471  call    cs:__guard_dispatch_icall_fptr
0x18002f477  test    eax, eax
0x18002f479  js      loc_18002F5B5
0x18002f47f  mov     rdi, [rbp+pExceptionObject]
0x18002f483  mov     [rbp+var_40], rdi
0x18002f487  test    rdi, rdi
0x18002f48a  jz      loc_18002F585
0x18002f490  movsd   xmm6, qword ptr [rsi+30h]
0x18002f495  cvtpd2ps xmm6, xmm6
0x18002f499  mov     ecx, 60h ; '`'; Size
0x18002f49e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f4a3  mov     rbx, rax
0x18002f4a6  mov     [rbp+var_48], rax
0x18002f4aa  test    rdi, rdi
0x18002f4ad  jz      short loc_18002F4BF
0x18002f4af  mov     rcx, [rdi]
0x18002f4b2  mov     rax, [rcx+8]
0x18002f4b6  mov     rcx, rdi
0x18002f4b9  call    cs:__guard_dispatch_icall_fptr
0x18002f4bf  mov     [rbp+var_48], rdi
0x18002f4c3  lea     r15, [rbx+10h]
0x18002f4c7  lea     rax, ??_7?$produce@UItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIItemQueryMatch@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IItemQueryMatch>::`vftable'
0x18002f4ce  mov     [r15], rax
0x18002f4d1  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002f4d8  mov     qword ptr [rbx+8], 1
0x18002f4e0  lea     rax, ??_7ItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@6B@; const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch::`vftable'
0x18002f4e7  mov     [rbx], rax
0x18002f4ea  mov     [rbx+18h], r12d
0x18002f4ee  mov     rdi, [rbp+pExceptionObject]
0x18002f4f2  mov     [rbx+20h], rdi
0x18002f4f6  test    rdi, rdi
0x18002f4f9  jz      short loc_18002F50B
0x18002f4fb  mov     rax, [rdi]
0x18002f4fe  mov     rcx, rdi
0x18002f501  mov     rax, [rax+8]
0x18002f505  call    cs:__guard_dispatch_icall_fptr
0x18002f50b  movss   dword ptr [rbx+28h], xmm6
0x18002f510  movups  xmm0, xmmword ptr [rsi]
0x18002f513  movups  xmmword ptr [rbx+30h], xmm0
0x18002f517  movups  xmm1, xmmword ptr [rsi+10h]
0x18002f51b  movups  xmmword ptr [rbx+40h], xmm1
0x18002f51f  movups  xmm0, xmmword ptr [rsi+20h]
0x18002f523  movups  xmmword ptr [rbx+50h], xmm0
0x18002f527  test    rdi, rdi
0x18002f52a  jz      short loc_18002F535
0x18002f52c  lea     rcx, [rbp+var_48]
0x18002f530  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18002f535  lea     rax, ??_7?$heap_implements@UItemQueryMatch@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemQueryMatch>::`vftable'
0x18002f53c  mov     [rbx], rax
0x18002f53f  mov     [r14], r15
0x18002f542  test    rdi, rdi
0x18002f545  jz      short loc_18002F551
0x18002f547  lea     rcx, [rbp+var_40]
0x18002f54b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18002f550  nop
0x18002f551  cmp     [rbp+arg_10], 0
0x18002f556  jz      short loc_18002F561
0x18002f558  lea     rcx, [rbp+arg_10]
0x18002f55c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18002f561  mov     rax, r14
0x18002f564  lea     r11, [rsp+80h+var_s0]
0x18002f56c  mov     rbx, [r11+38h]
0x18002f570  mov     rsi, [r11+48h]
0x18002f574  movaps  xmm6, [rsp+80h+var_10]
0x18002f579  mov     rsp, r11
0x18002f57c  pop     r15
0x18002f57e  pop     r14
0x18002f580  pop     r12
0x18002f582  pop     rdi
0x18002f583  pop     rbp
0x18002f584  retn
0x18002f585  mov     dword ptr [rbp+pExceptionObject], 67h ; 'g'
0x18002f58c  lea     rdx, _TI1?AW4QueryResultStatus@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@; pThrowInfo
0x18002f593  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002f597  call    _CxxThrowException
0x18002f59d  mov     dword ptr [rbp+pExceptionObject], 66h ; 'f'
0x18002f5a4  lea     rdx, _TI1?AW4QueryResultStatus@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@; pThrowInfo
0x18002f5ab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002f5af  call    _CxxThrowException
0x18002f5b5  lfence
0x18002f5b8  lea     rdx, [rbp+var_30]
0x18002f5bc  mov     ecx, eax
0x18002f5be  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```

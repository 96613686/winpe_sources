# Cache::Cache::EvictOrAddToMap(Cache::KeyHolder const &,Mso::IRefCounted &,uint,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *,Cache::CacheManager &,std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>> &,unsigned __int64 &,unsigned __int64 &)

- ea: `0x180067750`
- end: `0x180067d15`
- name: `?EvictOrAddToMap@Cache@1@AEAAXAEBVKeyHolder@1@AEAUIRefCounted@Mso@@IW4EvictionType@1@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@4@AEAVCacheManager@1@AEAV?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEA_K7@Z`
- size: `1477`
- prototype: `__int64 __usercall@<rax>(Cache::Cache *this@<rcx>, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180067d18`

## callees

- `0x180004640`
- `0x1800089b0`
- `0x18000d7fc`
- `0x18000e488`
- `0x18000edd0`
- `0x18000f890`
- `0x180056ee0`
- `0x1800573f0`
- `0x180067254`
- `0x180067430`
- `0x180067750`
- `0x18007aa30`
- `0x180112480`
- `0x18017e794`
- `0x1801fcd2c`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x180067906`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x180067906`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006795f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006796d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006795f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006796d`

## string_xrefs

- `0x180067ab0`: `cacheType`
- `0x180067c56`: `cacheType`
- `0x180067aeb`: `Gfx::Cache::EvictOrAddToMap - Evicted a memory-managed object`
- `0x1800679d1`: `objectMemSizeBytes`
- `0x180067c91`: `Gfx::Cache::EvictOrAddToMap - Evicted a count-managed object`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Cache::Cache::EvictOrAddToMap(
        Cache::Cache *this,
        __int64 a2,
        const struct Mso::IRefCounted *a3,
        int a4,
        unsigned int a5,
        unsigned __int64 a6,
        _QWORD *a7,
        Cache::CacheManager *a8,
        __int64 a9,
        unsigned __int64 *a10,
        void *a11)
{
  __int64 v12; // rbx
  const struct Cache::IResourceState *CachedResourceStateForObject; // r15
  __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64); // rbx
  __int64 v18; // r12
  __int64 v19; // r12
  __m128i si128; // xmm6
  int v21; // eax
  __int64 v22; // r8
  int v23; // edx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int128 *v27; // rcx
  int v28; // eax
  void **v29; // r8
  int v30; // edx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  void *v35; // [rsp+70h] [rbp-98h] BYREF
  __int64 v36; // [rsp+78h] [rbp-90h]
  unsigned __int64 *v37; // [rsp+80h] [rbp-88h]
  const struct Mso::IRefCounted *v38; // [rsp+88h] [rbp-80h]
  __int64 v39; // [rsp+90h] [rbp-78h]
  Cache::CacheManager *v40; // [rsp+98h] [rbp-70h]
  __int64 v41; // [rsp+A0h] [rbp-68h] BYREF
  void **v42; // [rsp+B0h] [rbp-58h] BYREF
  const char *v43; // [rsp+B8h] [rbp-50h]
  int v44; // [rsp+C0h] [rbp-48h]
  __int16 v45; // [rsp+C4h] [rbp-44h]
  __int128 v46; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v47; // [rsp+D8h] [rbp-30h]
  void **v48; // [rsp+E8h] [rbp-20h] BYREF
  const char *v49; // [rsp+F0h] [rbp-18h]
  int v50; // [rsp+F8h] [rbp-10h]
  __int16 v51; // [rsp+FCh] [rbp-Ch]
  __int128 v52; // [rsp+100h] [rbp-8h] BYREF
  __m128i v53; // [rsp+110h] [rbp+8h]
  void **v54; // [rsp+128h] [rbp+20h] BYREF
  const char *v55; // [rsp+130h] [rbp+28h]
  __int64 v56; // [rsp+138h] [rbp+30h]
  __int16 v57; // [rsp+140h] [rbp+38h]
  __int128 v58; // [rsp+148h] [rbp+40h] BYREF
  __m128i v59; // [rsp+158h] [rbp+50h]
  void **v60; // [rsp+168h] [rbp+60h] BYREF
  const char *v61; // [rsp+170h] [rbp+68h]
  __int64 v62; // [rsp+178h] [rbp+70h]
  __int16 v63; // [rsp+180h] [rbp+78h]
  __int128 v64; // [rsp+188h] [rbp+80h] BYREF
  __m128i v65; // [rsp+198h] [rbp+90h]
  void **v66; // [rsp+1A8h] [rbp+A0h] BYREF
  const char *v67; // [rsp+1B0h] [rbp+A8h]
  __int64 v68; // [rsp+1B8h] [rbp+B0h]
  __int16 v69; // [rsp+1C0h] [rbp+B8h]
  __int128 v70; // [rsp+1C8h] [rbp+C0h] BYREF
  __m128i v71; // [rsp+1D8h] [rbp+D0h]
  _QWORD v72[3]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int16 v73; // [rsp+200h] [rbp+F8h]
  _OWORD v74[2]; // [rsp+208h] [rbp+100h] BYREF

  v38 = a3;
  v12 = a2;
  v41 = a2;
  v40 = a8;
  v39 = a9;
  v37 = a10;
  v35 = a11;
  CachedResourceStateForObject = Cache::Cache::GetCachedResourceStateForObject(this, a3);
  if ( a5 != 2 )
  {
    if ( !a5
      || (a5 == 1 || a5 == 4 && *v37 < a6)
      && (**(unsigned int (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject) == 1 )
    {
      goto LABEL_8;
    }
LABEL_6:
    v35 = a3;
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(&v35);
    LODWORD(v36) = a4;
    v15 = *(_QWORD *)std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(
                       v39,
                       &v41,
                       v12);
    Mso::TCntPtr<Mso::IRefCounted>::operator=((void *)(v15 + 48));
    *(_DWORD *)(v15 + 56) = a4;
    Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(&v35);
    return;
  }
  if ( !a7 )
  {
LABEL_18:
    CrashWithRecovery(0x2351871Au, 0);
    __debugbreak();
  }
  if ( !*a7 )
  {
    CrashWithRecovery(0x25D9804u, 0);
    goto LABEL_18;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, const struct Cache::IResourceState *))*a7)(
          a7,
          *(_QWORD *)(v12 + 8),
          CachedResourceStateForObject) )
    goto LABEL_6;
LABEL_8:
  Cache::CacheManager::AppendLingeringResource(v40, a3);
  if ( *((_DWORD *)this + 34) == 1 )
  {
    v16 = *(_QWORD *)(v12 + 8);
    v17 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL);
    v18 = (*(__int64 (__fastcall **)(const struct Cache::IResourceState *))(*(_QWORD *)CachedResourceStateForObject
                                                                          + 16LL))(CachedResourceStateForObject);
    v19 = v17(v16) + v18;
    v12 = v41;
  }
  else
  {
    v19 = 0;
  }
  *v37 += v19;
  ++*(_QWORD *)v35;
  if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(48) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( *((_DWORD *)this + 34) == 1 )
    {
      v48 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v49 = "mruVal";
      v50 = a4;
      v51 = 4;
      v52 = 0;
      v53 = si128;
      LOWORD(v52) = 0;
      v66 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v67 = "objectMemSizeBytes";
      v68 = v19;
      v69 = 4;
      v70 = 0;
      v71 = si128;
      LOWORD(v70) = 0;
      v21 = (**(__int64 (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject);
      v42 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v43 = "refCount";
      v44 = v21 - 1;
      v45 = 4;
      v46 = 0;
      v47 = si128;
      LOWORD(v46) = 0;
      v60 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v61 = "evictType";
      v62 = sub_180004640(a5);
      v63 = 4;
      v64 = 0;
      v65 = si128;
      LOWORD(v64) = 0;
      v54 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
      v55 = "objectPtr";
      v56 = (__int64)v38;
      v57 = 4;
      v58 = 0;
      v59 = si128;
      LOWORD(v58) = 0;
      v72[0] = v22;
      v72[1] = "cacheType";
      v72[2] = sub_18000D7FC(*((unsigned int *)this + 28));
      v73 = 4;
      v74[0] = 0;
      v74[1] = si128;
      LOWORD(v74[0]) = 0;
      v35 = "Gfx::Cache::EvictOrAddToMap - Evicted a memory-managed object";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        v24,
        v23,
        v25,
        v26,
        (__int64)&v35,
        (__int64)v72,
        (__int64)&v54,
        (__int64)&v60,
        (__int64)&v42,
        (__int64)&v66,
        (__int64)&v48);
      std::wstring::~wstring(v74);
      std::wstring::~wstring(&v58);
      std::wstring::~wstring(&v64);
      std::wstring::~wstring(&v46);
      std::wstring::~wstring(&v70);
      v27 = &v52;
    }
    else
    {
      v42 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v43 = "mruVal";
      v44 = a4;
      v45 = 4;
      v46 = 0;
      v47 = si128;
      LOWORD(v46) = 0;
      v28 = (**(__int64 (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject);
      v48 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v49 = "refCount";
      v50 = v28 - 1;
      v51 = 4;
      v52 = 0;
      v53 = si128;
      LOWORD(v52) = 0;
      v54 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v55 = "evictType";
      v56 = sub_180004640(a5);
      v57 = 4;
      v58 = 0;
      v59 = si128;
      LOWORD(v58) = 0;
      v60 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
      v61 = "objectPtr";
      v62 = (__int64)v38;
      v63 = 4;
      v64 = 0;
      v65 = si128;
      LOWORD(v64) = 0;
      v66 = v29;
      v67 = "cacheType";
      v68 = sub_18000D7FC(*((unsigned int *)this + 28));
      v69 = 4;
      v70 = 0;
      v71 = si128;
      LOWORD(v70) = 0;
      v35 = "Gfx::Cache::EvictOrAddToMap - Evicted a count-managed object";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        v31,
        v30,
        v32,
        v33,
        (__int64)&v35,
        (__int64)&v66,
        (__int64)&v60,
        (__int64)&v54,
        (__int64)&v48,
        (__int64)&v42);
      std::wstring::~wstring(&v70);
      std::wstring::~wstring(&v64);
      std::wstring::~wstring(&v58);
      std::wstring::~wstring(&v52);
      v27 = &v46;
    }
    std::wstring::~wstring(v27);
  }
  Cache::Cache::RefreshEvictedMap(this, v12, a5, 0);
}

```

## disassembly

```asm
0x180067750  mov     rax, rsp
0x180067753  mov     [rax+20h], rbx
0x180067757  push    rbp
0x180067758  push    rsi
0x180067759  push    rdi
0x18006775a  push    r12
0x18006775c  push    r13
0x18006775e  push    r14
0x180067760  push    r15
0x180067762  lea     rbp, [rax-178h]
0x180067769  sub     rsp, 240h
0x180067770  movaps  xmmword ptr [rax-48h], xmm6
0x180067774  mov     rax, cs:__security_cookie
0x18006777b  xor     rax, rsp
0x18006777e  mov     [rbp+170h+var_50], rax
0x180067785  mov     dword ptr [rsp+270h+var_210], r9d
0x18006778a  mov     r12, r8
0x18006778d  mov     [rbp+170h+var_1F0], r8
0x180067791  mov     rbx, rdx
0x180067794  mov     [rbp+170h+var_1D8], rdx
0x180067798  mov     r13, rcx
0x18006779b  mov     rdi, [rbp+170h+arg_30]
0x1800677a2  mov     r14d, [rbp+170h+arg_20]
0x1800677a9  mov     rax, [rbp+170h+arg_38]
0x1800677b0  mov     [rbp+170h+var_1E0], rax
0x1800677b4  mov     rax, [rbp+170h+arg_40]
0x1800677bb  mov     [rbp+170h+var_1E8], rax
0x1800677bf  mov     rax, [rbp+170h+arg_48]
0x1800677c6  mov     [rsp+270h+var_1F8], rax
0x1800677cb  mov     rcx, [rbp+170h+arg_50]
0x1800677d2  mov     [rsp+270h+var_208], rcx
0x1800677d7  mov     rdx, r8; struct Mso::IRefCounted *
0x1800677da  mov     rcx, r13; this
0x1800677dd  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x1800677e2  mov     r15, rax
0x1800677e5  xor     esi, esi
0x1800677e7  cmp     r14d, 2
0x1800677eb  jz      loc_18006792B
0x1800677f1  test    r14d, r14d
0x1800677f4  jz      loc_1800678A7
0x1800677fa  cmp     r14d, 1
0x1800677fe  jz      loc_18006788F
0x180067804  cmp     r14d, 4
0x180067808  jnz     short loc_18006781B
0x18006780a  mov     rax, [rbp+170h+arg_28]
0x180067811  mov     rcx, [rsp+270h+var_1F8]
0x180067816  cmp     [rcx], rax
0x180067819  jb      short loc_18006788F
0x18006781b  mov     [rsp+270h+var_208], r12
0x180067820  lea     rcx, [rsp+270h+var_208]; void **
0x180067825  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18006782a  mov     edi, dword ptr [rsp+270h+var_210]
0x18006782e  mov     dword ptr [rsp+270h+var_200], edi
0x180067832  mov     r8, rbx
0x180067835  lea     rdx, [rbp+170h+var_1D8]
0x180067839  mov     rcx, [rbp+170h+var_1E8]
0x18006783d  call    ??$_Try_emplace@AEBVKeyHolder@Cache@@$$V@?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@_N@1@AEBVKeyHolder@Cache@@@Z; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(Cache::KeyHolder const &)
0x180067842  mov     rbx, [rax]
0x180067845  lea     rdx, [rsp+270h+var_208]
0x18006784a  lea     rcx, [rbx+30h]
0x18006784e  call    ??4?$TCntPtr@UIRefCounted@Mso@@@Mso@@QEAAAEAV01@AEBV01@@Z; Mso::TCntPtr<Mso::IRefCounted>::operator=(Mso::TCntPtr<Mso::IRefCounted> const &)
0x180067853  mov     [rbx+38h], edi
0x180067856  lea     rcx, [rsp+270h+var_208]; void *
0x18006785b  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x180067860  mov     rcx, [rbp+170h+var_50]
0x180067867  xor     rcx, rsp; StackCookie
0x18006786a  call    __security_check_cookie
0x18006786f  lea     r11, [rsp+270h+var_30]
0x180067877  mov     rbx, [r11+58h]
0x18006787b  movaps  xmm6, xmmword ptr [r11-10h]
0x180067880  mov     rsp, r11
0x180067883  pop     r15
0x180067885  pop     r14
0x180067887  pop     r13
0x180067889  pop     r12
0x18006788b  pop     rdi
0x18006788c  pop     rsi
0x18006788d  pop     rbp
0x18006788e  retn
0x18006788f  mov     rax, [r15]
0x180067892  mov     rcx, r15
0x180067895  mov     rax, [rax]
0x180067898  call    cs:__guard_dispatch_icall_fptr
0x18006789e  cmp     eax, 1
0x1800678a1  jnz     loc_18006781B
0x1800678a7  mov     rdx, r12; struct Mso::IRefCounted *
0x1800678aa  mov     rcx, [rbp+170h+var_1E0]; this
0x1800678ae  call    ?AppendLingeringResource@CacheManager@Cache@@QEAAXAEBUIRefCounted@Mso@@@Z; Cache::CacheManager::AppendLingeringResource(Mso::IRefCounted const &)
0x1800678b3  cmp     dword ptr [r13+88h], 1
0x1800678bb  jnz     short loc_180067926
0x1800678bd  mov     rdi, [rbx+8]
0x1800678c1  mov     rax, [r15]
0x1800678c4  mov     rcx, [rdi]
0x1800678c7  mov     rbx, [rcx+20h]
0x1800678cb  mov     rcx, r15
0x1800678ce  mov     rax, [rax+10h]
0x1800678d2  call    cs:__guard_dispatch_icall_fptr
0x1800678d8  mov     r12, rax
0x1800678db  mov     rcx, rdi
0x1800678de  mov     rax, rbx
0x1800678e1  call    cs:__guard_dispatch_icall_fptr
0x1800678e7  add     r12, rax
0x1800678ea  mov     rbx, [rbp+170h+var_1D8]
0x1800678ee  mov     rax, [rsp+270h+var_1F8]
0x1800678f3  add     [rax], r12
0x1800678f6  mov     rax, [rsp+270h+var_208]
0x1800678fb  inc     qword ptr [rax]
0x1800678fe  mov     edx, 64h ; 'd'
0x180067903  lea     ecx, [rdx-34h]
0x180067906  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x18006790c  test    al, al
0x18006790e  jnz     short loc_180067974
0x180067910  xor     r9d, r9d
0x180067913  mov     r8d, r14d
0x180067916  mov     rdx, rbx
0x180067919  mov     rcx, r13
0x18006791c  call    ?RefreshEvictedMap@Cache@1@AEAAXAEBVKeyHolder@1@W4EvictionType@1@_N@Z; Cache::Cache::RefreshEvictedMap(Cache::KeyHolder const &,Cache::EvictionType,bool)
0x180067921  jmp     loc_180067860
0x180067926  mov     r12, rsi
0x180067929  jmp     short loc_1800678EE
0x18006792b  test    rdi, rdi
0x18006792e  jz      short loc_180067966
0x180067930  mov     rax, [rdi]
0x180067933  test    rax, rax
0x180067936  jz      short loc_180067958
0x180067938  mov     r8, r15
0x18006793b  mov     rdx, [rbx+8]
0x18006793f  mov     rcx, rdi
0x180067942  mov     rax, [rax]
0x180067945  call    cs:__guard_dispatch_icall_fptr
0x18006794b  test    al, al
0x18006794d  jnz     loc_1800678A7
0x180067953  jmp     loc_18006781B
0x180067958  xor     edx, edx
0x18006795a  mov     ecx, 25D9804h
0x18006795f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180067965  nop
0x180067966  xor     edx, edx
0x180067968  mov     ecx, 2351871Ah
0x18006796d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180067973  int     3; Trap to Debugger
0x180067974  lea     rax, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18006797b  mov     edi, dword ptr [rsp+270h+var_210]
0x18006797f  xorps   xmm0, xmm0
0x180067982  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18006798a  mov     rcx, r15
0x18006798d  cmp     dword ptr [r13+88h], 1
0x180067995  jnz     loc_180067B81
0x18006799b  mov     [rbp+170h+var_190], rax
0x18006799f  lea     rax, aMruval; "mruVal"
0x1800679a6  mov     [rbp+170h+var_188], rax
0x1800679aa  mov     [rbp+170h+var_180], edi
0x1800679ad  mov     edi, 4
0x1800679b2  mov     [rbp+170h+var_17C], di
0x1800679b6  movups  [rbp+170h+var_178], xmm0
0x1800679ba  movdqu  [rbp+170h+var_168], xmm6
0x1800679bf  mov     word ptr [rbp+170h+var_178], si
0x1800679c3  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x1800679ca  mov     [rbp+170h+var_D0], rax
0x1800679d1  lea     rax, aObjectmemsizeb; "objectMemSizeBytes"
0x1800679d8  mov     [rbp+170h+var_C8], rax
0x1800679df  mov     [rbp+170h+var_C0], r12
0x1800679e6  mov     [rbp+170h+var_B8], di
0x1800679ed  movups  [rbp+170h+var_B0], xmm0
0x1800679f4  movdqa  [rbp+170h+var_A0], xmm6
0x1800679fc  mov     word ptr [rbp+170h+var_B0], si
0x180067a03  mov     rax, [r15]
0x180067a06  mov     rax, [rax]
0x180067a09  call    cs:__guard_dispatch_icall_fptr
0x180067a0f  dec     eax
0x180067a11  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x180067a18  mov     [rbp+170h+var_1C8], rcx
0x180067a1c  lea     rcx, aRefcount; "refCount"
0x180067a23  mov     [rbp+170h+var_1C0], rcx
0x180067a27  mov     [rbp+170h+var_1B8], eax
0x180067a2a  mov     [rbp+170h+var_1B4], di
0x180067a2e  xorps   xmm0, xmm0
0x180067a31  movups  [rbp+170h+var_1B0], xmm0
0x180067a35  movdqu  [rbp+170h+var_1A0], xmm6
0x180067a3a  mov     word ptr [rbp+170h+var_1B0], si
0x180067a3e  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180067a45  mov     [rbp+170h+var_110], r8
0x180067a49  lea     rax, aEvicttype; "evictType"
0x180067a50  mov     [rbp+170h+var_108], rax
0x180067a54  mov     ecx, r14d
0x180067a57  call    sub_180004640
0x180067a5c  mov     [rbp+170h+var_100], rax
0x180067a60  mov     [rbp+170h+var_F8], di
0x180067a64  movups  [rbp+170h+var_F0], xmm0
0x180067a6b  movdqa  [rbp+170h+var_E0], xmm6
0x180067a73  mov     word ptr [rbp+170h+var_F0], si
0x180067a7a  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x180067a81  mov     [rbp+170h+var_150], rax
0x180067a85  lea     rax, aObjectptr; "objectPtr"
0x180067a8c  mov     [rbp+170h+var_148], rax
0x180067a90  mov     rax, [rbp+170h+var_1F0]
0x180067a94  mov     [rbp+170h+var_140], rax
0x180067a98  mov     [rbp+170h+var_138], di
0x180067a9c  movups  [rbp+170h+var_130], xmm0
0x180067aa0  movdqa  [rbp+170h+var_120], xmm6
0x180067aa5  mov     word ptr [rbp+170h+var_130], si
0x180067aa9  mov     [rbp+170h+var_90], r8
0x180067ab0  lea     rax, aCachetype; "cacheType"
0x180067ab7  mov     [rbp+170h+var_88], rax
0x180067abe  mov     ecx, [r13+70h]
0x180067ac2  call    sub_18000D7FC
0x180067ac7  mov     [rbp+170h+var_80], rax
0x180067ace  mov     [rbp+170h+var_78], di
0x180067ad5  movups  [rbp+170h+var_70], xmm0
0x180067adc  movdqa  [rbp+170h+var_60], xmm6
0x180067ae4  mov     word ptr [rbp+170h+var_70], si
0x180067aeb  lea     rax, aGfxCacheEvicto; "Gfx::Cache::EvictOrAddToMap - Evicted a"...
0x180067af2  mov     [rsp+270h+var_208], rax
0x180067af7  lea     rax, [rbp+170h+var_190]
0x180067afb  mov     [rsp+270h+var_220], rax
0x180067b00  lea     rax, [rbp+170h+var_D0]
0x180067b07  mov     [rsp+270h+var_228], rax
0x180067b0c  lea     rax, [rbp+170h+var_1C8]
0x180067b10  mov     [rsp+270h+var_230], rax
0x180067b15  lea     rax, [rbp+170h+var_110]
0x180067b19  mov     [rsp+270h+var_238], rax
0x180067b1e  lea     rax, [rbp+170h+var_150]
0x180067b22  mov     [rsp+270h+var_240], rax
0x180067b27  lea     rax, [rbp+170h+var_90]
0x180067b2e  mov     [rsp+270h+var_248], rax
0x180067b33  lea     rax, [rsp+270h+var_208]
0x180067b38  mov     [rsp+270h+var_250], rax
0x180067b3d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEBX@23@U123@U?$ClassifiedStructuredObject@H@23@U?$ClassifiedStructuredObject@_K@23@U?$ClassifiedStructuredObject@I@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@4$$QEAU?$ClassifiedStructuredObject@H@01@$$QEAU?$ClassifiedStructuredObject@_K@01@$$QEAU?$ClassifiedStructuredObject@I@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<int> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x180067b42  lea     rcx, [rbp+170h+var_70]
0x180067b49  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067b4e  lea     rcx, [rbp+170h+var_130]
0x180067b52  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067b57  lea     rcx, [rbp+170h+var_F0]
0x180067b5e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067b63  lea     rcx, [rbp+170h+var_1B0]
0x180067b67  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067b6c  lea     rcx, [rbp+170h+var_B0]
0x180067b73  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180067b78  lea     rcx, [rbp+170h+var_178]
0x180067b7c  jmp     loc_180067D0A
0x180067b81  mov     [rbp+170h+var_1C8], rax
0x180067b85  lea     rax, aMruval; "mruVal"
0x180067b8c  mov     [rbp+170h+var_1C0], rax
0x180067b90  mov     [rbp+170h+var_1B8], edi
0x180067b93  mov     edi, 4
0x180067b98  mov     [rbp+170h+var_1B4], di
0x180067b9c  movups  [rbp+170h+var_1B0], xmm0
0x180067ba0  movdqu  [rbp+170h+var_1A0], xmm6
0x180067ba5  mov     word ptr [rbp+170h+var_1B0], si
0x180067ba9  mov     rax, [r15]
0x180067bac  mov     rax, [rax]
0x180067baf  call    cs:__guard_dispatch_icall_fptr
0x180067bb5  dec     eax
0x180067bb7  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x180067bbe  mov     [rbp+170h+var_190], rcx
0x180067bc2  lea     rcx, aRefcount; "refCount"
0x180067bc9  mov     [rbp+170h+var_188], rcx
0x180067bcd  mov     [rbp+170h+var_180], eax
0x180067bd0  mov     [rbp+170h+var_17C], di
0x180067bd4  xorps   xmm0, xmm0
0x180067bd7  movups  [rbp+170h+var_178], xmm0
0x180067bdb  movdqu  [rbp+170h+var_168], xmm6
0x180067be0  mov     word ptr [rbp+170h+var_178], si
0x180067be4  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180067beb  mov     [rbp+170h+var_150], r8
0x180067bef  lea     rax, aEvicttype; "evictType"
0x180067bf6  mov     [rbp+170h+var_148], rax
0x180067bfa  mov     ecx, r14d
0x180067bfd  call    sub_180004640
0x180067c02  mov     [rbp+170h+var_140], rax
0x180067c06  mov     [rbp+170h+var_138], di
0x180067c0a  movups  [rbp+170h+var_130], xmm0
0x180067c0e  movdqa  [rbp+170h+var_120], xmm6
0x180067c13  mov     word ptr [rbp+170h+var_130], si
0x180067c17  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x180067c1e  mov     [rbp+170h+var_110], rax
0x180067c22  lea     rax, aObjectptr; "objectPtr"
0x180067c29  mov     [rbp+170h+var_108], rax
0x180067c2d  mov     rax, [rbp+170h+var_1F0]
0x180067c31  mov     [rbp+170h+var_100], rax
0x180067c35  mov     [rbp+170h+var_F8], di
0x180067c39  movups  [rbp+170h+var_F0], xmm0
0x180067c40  movdqa  [rbp+170h+var_E0], xmm6
0x180067c48  mov     word ptr [rbp+170h+var_F0], si
0x180067c4f  mov     [rbp+170h+var_D0], r8
0x180067c56  lea     rax, aCachetype; "cacheType"
0x180067c5d  mov     [rbp+170h+var_C8], rax
0x180067c64  mov     ecx, [r13+70h]
0x180067c68  call    sub_18000D7FC
0x180067c6d  mov     [rbp+170h+var_C0], rax
0x180067c74  mov     [rbp+170h+var_B8], di
0x180067c7b  movups  [rbp+170h+var_B0], xmm0
0x180067c82  movdqa  [rbp+170h+var_A0], xmm6
0x180067c8a  mov     word ptr [rbp+170h+var_B0], si
0x180067c91  lea     rax, aGfxCacheEvicto_0; "Gfx::Cache::EvictOrAddToMap - Evicted a"...
0x180067c98  mov     [rsp+270h+var_208], rax
0x180067c9d  lea     rax, [rbp+170h+var_1C8]
0x180067ca1  mov     [rsp+270h+var_228], rax
0x180067ca6  lea     rax, [rbp+170h+var_190]
0x180067caa  mov     [rsp+270h+var_230], rax
  ... truncated ...
```

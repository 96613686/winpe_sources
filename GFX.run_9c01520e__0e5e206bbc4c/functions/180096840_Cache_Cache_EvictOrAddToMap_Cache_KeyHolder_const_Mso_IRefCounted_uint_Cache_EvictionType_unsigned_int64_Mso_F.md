# Cache::Cache::EvictOrAddToMap(Cache::KeyHolder const &,Mso::IRefCounted &,uint,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *,Cache::CacheManager &,std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>> &,unsigned __int64 &,unsigned __int64 &)

- ea: `0x180096840`
- end: `0x180096e05`
- name: `?EvictOrAddToMap@Cache@1@AEAAXAEBVKeyHolder@1@AEAUIRefCounted@Mso@@IW4EvictionType@1@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@4@AEAVCacheManager@1@AEAV?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEA_K7@Z`
- size: `1477`
- prototype: `__int64 __usercall@<rax>(Cache::Cache *this@<rcx>, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180096e08`

## callees

- `0x1800047f0`
- `0x180009510`
- `0x18000d6bc`
- `0x18000da20`
- `0x18000e36c`
- `0x18000ef20`
- `0x18000f790`
- `0x1800578b0`
- `0x180057e70`
- `0x180077780`
- `0x1800963c0`
- `0x180096840`
- `0x18010c8f0`
- `0x180182df4`
- `0x180200060`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800969f6`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z` at `0x1800969f6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180096a4f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180096a5d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180096a4f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180096a5d`

## string_xrefs

- `0x180096ba0`: `cacheType`
- `0x180096d46`: `cacheType`
- `0x180096ac1`: `objectMemSizeBytes`
- `0x180096d81`: `Gfx::Cache::EvictOrAddToMap - Evicted a count-managed object`
- `0x180096bdb`: `Gfx::Cache::EvictOrAddToMap - Evicted a memory-managed object`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cache::Cache::EvictOrAddToMap(
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
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64); // rbx
  __int64 v19; // r12
  __int64 v20; // r12
  __m128i si128; // xmm6
  int v22; // eax
  __int64 v23; // r8
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int128 *v28; // rcx
  int v29; // eax
  void **v30; // r8
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  void *v36; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-90h]
  unsigned __int64 *v38; // [rsp+80h] [rbp-88h]
  const struct Mso::IRefCounted *v39; // [rsp+88h] [rbp-80h]
  __int64 v40; // [rsp+90h] [rbp-78h]
  Cache::CacheManager *v41; // [rsp+98h] [rbp-70h]
  __int64 v42; // [rsp+A0h] [rbp-68h] BYREF
  void **v43; // [rsp+B0h] [rbp-58h] BYREF
  const char *v44; // [rsp+B8h] [rbp-50h]
  int v45; // [rsp+C0h] [rbp-48h]
  __int16 v46; // [rsp+C4h] [rbp-44h]
  __int128 v47; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v48; // [rsp+D8h] [rbp-30h]
  void **v49; // [rsp+E8h] [rbp-20h] BYREF
  const char *v50; // [rsp+F0h] [rbp-18h]
  int v51; // [rsp+F8h] [rbp-10h]
  __int16 v52; // [rsp+FCh] [rbp-Ch]
  __int128 v53; // [rsp+100h] [rbp-8h] BYREF
  __m128i v54; // [rsp+110h] [rbp+8h]
  void **v55; // [rsp+128h] [rbp+20h] BYREF
  const char *v56; // [rsp+130h] [rbp+28h]
  __int64 v57; // [rsp+138h] [rbp+30h]
  __int16 v58; // [rsp+140h] [rbp+38h]
  __int128 v59; // [rsp+148h] [rbp+40h] BYREF
  __m128i v60; // [rsp+158h] [rbp+50h]
  void **v61; // [rsp+168h] [rbp+60h] BYREF
  const char *v62; // [rsp+170h] [rbp+68h]
  __int64 v63; // [rsp+178h] [rbp+70h]
  __int16 v64; // [rsp+180h] [rbp+78h]
  __int128 v65; // [rsp+188h] [rbp+80h] BYREF
  __m128i v66; // [rsp+198h] [rbp+90h]
  void **v67; // [rsp+1A8h] [rbp+A0h] BYREF
  const char *v68; // [rsp+1B0h] [rbp+A8h]
  __int64 v69; // [rsp+1B8h] [rbp+B0h]
  __int16 v70; // [rsp+1C0h] [rbp+B8h]
  __int128 v71; // [rsp+1C8h] [rbp+C0h] BYREF
  __m128i v72; // [rsp+1D8h] [rbp+D0h]
  _QWORD v73[3]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int16 v74; // [rsp+200h] [rbp+F8h]
  _OWORD v75[2]; // [rsp+208h] [rbp+100h] BYREF

  v39 = a3;
  v12 = a2;
  v42 = a2;
  v41 = a8;
  v40 = a9;
  v38 = a10;
  v36 = a11;
  CachedResourceStateForObject = Cache::Cache::GetCachedResourceStateForObject(this, a3);
  if ( a5 != 2 )
  {
    if ( !a5
      || (a5 == 1 || a5 == 4 && *v38 < a6)
      && (**(unsigned int (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject) == 1 )
    {
      goto LABEL_8;
    }
LABEL_6:
    v36 = a3;
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(&v36);
    LODWORD(v37) = a4;
    v15 = *(_QWORD *)std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(
                       v40,
                       &v42,
                       v12);
    Mso::TCntPtr<Mso::IRefCounted>::operator=(v15 + 48, &v36);
    *(_DWORD *)(v15 + 56) = a4;
    return Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(&v36);
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
  Cache::CacheManager::AppendLingeringResource(v41, a3);
  if ( *((_DWORD *)this + 34) == 1 )
  {
    v17 = *(_QWORD *)(v12 + 8);
    v18 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL);
    v19 = (*(__int64 (__fastcall **)(const struct Cache::IResourceState *))(*(_QWORD *)CachedResourceStateForObject
                                                                          + 16LL))(CachedResourceStateForObject);
    v20 = v18(v17) + v19;
    v12 = v42;
  }
  else
  {
    v20 = 0;
  }
  *v38 += v20;
  ++*(_QWORD *)v36;
  if ( (unsigned __int8)Mso::Logging::MsoShouldTrace(48) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    if ( *((_DWORD *)this + 34) == 1 )
    {
      v49 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v50 = "mruVal";
      v51 = a4;
      v52 = 4;
      v53 = 0;
      v54 = si128;
      LOWORD(v53) = 0;
      v67 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
      v68 = "objectMemSizeBytes";
      v69 = v20;
      v70 = 4;
      v71 = 0;
      v72 = si128;
      LOWORD(v71) = 0;
      v22 = (**(__int64 (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject);
      v43 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v44 = "refCount";
      v45 = v22 - 1;
      v46 = 4;
      v47 = 0;
      v48 = si128;
      LOWORD(v47) = 0;
      v61 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v62 = "evictType";
      v63 = sub_1800047F0(a5);
      v64 = 4;
      v65 = 0;
      v66 = si128;
      LOWORD(v65) = 0;
      v55 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
      v56 = "objectPtr";
      v57 = (__int64)v39;
      v58 = 4;
      v59 = 0;
      v60 = si128;
      LOWORD(v59) = 0;
      v73[0] = v23;
      v73[1] = "cacheType";
      v73[2] = sub_18000D6BC(*((unsigned int *)this + 28));
      v74 = 4;
      v75[0] = 0;
      v75[1] = si128;
      LOWORD(v75[0]) = 0;
      v36 = "Gfx::Cache::EvictOrAddToMap - Evicted a memory-managed object";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        v25,
        v24,
        v26,
        v27,
        (__int64)&v36,
        (__int64)v73,
        (__int64)&v55,
        (__int64)&v61,
        (__int64)&v43,
        (__int64)&v67,
        (__int64)&v49);
      std::wstring::~wstring(v75);
      std::wstring::~wstring(&v59);
      std::wstring::~wstring(&v65);
      std::wstring::~wstring(&v47);
      std::wstring::~wstring(&v71);
      v28 = &v53;
    }
    else
    {
      v43 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v44 = "mruVal";
      v45 = a4;
      v46 = 4;
      v47 = 0;
      v48 = si128;
      LOWORD(v47) = 0;
      v29 = (**(__int64 (__fastcall ***)(const struct Cache::IResourceState *))CachedResourceStateForObject)(CachedResourceStateForObject);
      v49 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v50 = "refCount";
      v51 = v29 - 1;
      v52 = 4;
      v53 = 0;
      v54 = si128;
      LOWORD(v53) = 0;
      v55 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v56 = "evictType";
      v57 = sub_1800047F0(a5);
      v58 = 4;
      v59 = 0;
      v60 = si128;
      LOWORD(v59) = 0;
      v61 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
      v62 = "objectPtr";
      v63 = (__int64)v39;
      v64 = 4;
      v65 = 0;
      v66 = si128;
      LOWORD(v65) = 0;
      v67 = v30;
      v68 = "cacheType";
      v69 = sub_18000D6BC(*((unsigned int *)this + 28));
      v70 = 4;
      v71 = 0;
      v72 = si128;
      LOWORD(v71) = 0;
      v36 = "Gfx::Cache::EvictOrAddToMap - Evicted a count-managed object";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        v32,
        v31,
        v33,
        v34,
        (__int64)&v36,
        (__int64)&v67,
        (__int64)&v61,
        (__int64)&v55,
        (__int64)&v49,
        (__int64)&v43);
      std::wstring::~wstring(&v71);
      std::wstring::~wstring(&v65);
      std::wstring::~wstring(&v59);
      std::wstring::~wstring(&v53);
      v28 = &v47;
    }
    std::wstring::~wstring(v28);
  }
  return Cache::Cache::RefreshEvictedMap(this, v12, a5, 0);
}

```

## disassembly

```asm
0x180096840  mov     rax, rsp
0x180096843  mov     [rax+20h], rbx
0x180096847  push    rbp
0x180096848  push    rsi
0x180096849  push    rdi
0x18009684a  push    r12
0x18009684c  push    r13
0x18009684e  push    r14
0x180096850  push    r15
0x180096852  lea     rbp, [rax-178h]
0x180096859  sub     rsp, 240h
0x180096860  movaps  xmmword ptr [rax-48h], xmm6
0x180096864  mov     rax, cs:__security_cookie
0x18009686b  xor     rax, rsp
0x18009686e  mov     [rbp+170h+var_50], rax
0x180096875  mov     dword ptr [rsp+270h+var_210], r9d
0x18009687a  mov     r12, r8
0x18009687d  mov     [rbp+170h+var_1F0], r8
0x180096881  mov     rbx, rdx
0x180096884  mov     [rbp+170h+var_1D8], rdx
0x180096888  mov     r13, rcx
0x18009688b  mov     rdi, [rbp+170h+arg_30]
0x180096892  mov     r14d, [rbp+170h+arg_20]
0x180096899  mov     rax, [rbp+170h+arg_38]
0x1800968a0  mov     [rbp+170h+var_1E0], rax
0x1800968a4  mov     rax, [rbp+170h+arg_40]
0x1800968ab  mov     [rbp+170h+var_1E8], rax
0x1800968af  mov     rax, [rbp+170h+arg_48]
0x1800968b6  mov     [rsp+270h+var_1F8], rax
0x1800968bb  mov     rcx, [rbp+170h+arg_50]
0x1800968c2  mov     [rsp+270h+var_208], rcx
0x1800968c7  mov     rdx, r8; struct Mso::IRefCounted *
0x1800968ca  mov     rcx, r13; this
0x1800968cd  call    ?GetCachedResourceStateForObject@Cache@1@QEBAAEBUIResourceState@1@AEBUIRefCounted@Mso@@@Z; Cache::Cache::GetCachedResourceStateForObject(Mso::IRefCounted const &)
0x1800968d2  mov     r15, rax
0x1800968d5  xor     esi, esi
0x1800968d7  cmp     r14d, 2
0x1800968db  jz      loc_180096A1B
0x1800968e1  test    r14d, r14d
0x1800968e4  jz      loc_180096997
0x1800968ea  cmp     r14d, 1
0x1800968ee  jz      loc_18009697F
0x1800968f4  cmp     r14d, 4
0x1800968f8  jnz     short loc_18009690B
0x1800968fa  mov     rax, [rbp+170h+arg_28]
0x180096901  mov     rcx, [rsp+270h+var_1F8]
0x180096906  cmp     [rcx], rax
0x180096909  jb      short loc_18009697F
0x18009690b  mov     [rsp+270h+var_208], r12
0x180096910  lea     rcx, [rsp+270h+var_208]; void **
0x180096915  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x18009691a  mov     edi, dword ptr [rsp+270h+var_210]
0x18009691e  mov     dword ptr [rsp+270h+var_200], edi
0x180096922  mov     r8, rbx
0x180096925  lea     rdx, [rbp+170h+var_1D8]
0x180096929  mov     rcx, [rbp+170h+var_1E8]
0x18009692d  call    ??$_Try_emplace@AEBVKeyHolder@Cache@@$$V@?$map@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@std@@_N@1@AEBVKeyHolder@Cache@@@Z; std::map<Cache::KeyHolder,Cache::Cache::ValueMRUPair>::_Try_emplace<Cache::KeyHolder const &,>(Cache::KeyHolder const &)
0x180096932  mov     rbx, [rax]
0x180096935  lea     rdx, [rsp+270h+var_208]
0x18009693a  lea     rcx, [rbx+30h]
0x18009693e  call    ??4?$TCntPtr@UIRefCounted@Mso@@@Mso@@QEAAAEAV01@AEBV01@@Z; Mso::TCntPtr<Mso::IRefCounted>::operator=(Mso::TCntPtr<Mso::IRefCounted> const &)
0x180096943  mov     [rbx+38h], edi
0x180096946  lea     rcx, [rsp+270h+var_208]
0x18009694b  call    ??1?$TCntPtr@UIScene@GEL@@@Mso@@QEAA@XZ; Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(void)
0x180096950  mov     rcx, [rbp+170h+var_50]
0x180096957  xor     rcx, rsp; StackCookie
0x18009695a  call    __security_check_cookie
0x18009695f  lea     r11, [rsp+270h+var_30]
0x180096967  mov     rbx, [r11+58h]
0x18009696b  movaps  xmm6, xmmword ptr [r11-10h]
0x180096970  mov     rsp, r11
0x180096973  pop     r15
0x180096975  pop     r14
0x180096977  pop     r13
0x180096979  pop     r12
0x18009697b  pop     rdi
0x18009697c  pop     rsi
0x18009697d  pop     rbp
0x18009697e  retn
0x18009697f  mov     rax, [r15]
0x180096982  mov     rcx, r15
0x180096985  mov     rax, [rax]
0x180096988  call    cs:__guard_dispatch_icall_fptr
0x18009698e  cmp     eax, 1
0x180096991  jnz     loc_18009690B
0x180096997  mov     rdx, r12; struct Mso::IRefCounted *
0x18009699a  mov     rcx, [rbp+170h+var_1E0]; this
0x18009699e  call    ?AppendLingeringResource@CacheManager@Cache@@QEAAXAEBUIRefCounted@Mso@@@Z; Cache::CacheManager::AppendLingeringResource(Mso::IRefCounted const &)
0x1800969a3  cmp     dword ptr [r13+88h], 1
0x1800969ab  jnz     short loc_180096A16
0x1800969ad  mov     rdi, [rbx+8]
0x1800969b1  mov     rax, [r15]
0x1800969b4  mov     rcx, [rdi]
0x1800969b7  mov     rbx, [rcx+20h]
0x1800969bb  mov     rcx, r15
0x1800969be  mov     rax, [rax+10h]
0x1800969c2  call    cs:__guard_dispatch_icall_fptr
0x1800969c8  mov     r12, rax
0x1800969cb  mov     rcx, rdi
0x1800969ce  mov     rax, rbx
0x1800969d1  call    cs:__guard_dispatch_icall_fptr
0x1800969d7  add     r12, rax
0x1800969da  mov     rbx, [rbp+170h+var_1D8]
0x1800969de  mov     rax, [rsp+270h+var_1F8]
0x1800969e3  add     [rax], r12
0x1800969e6  mov     rax, [rsp+270h+var_208]
0x1800969eb  inc     qword ptr [rax]
0x1800969ee  mov     edx, 64h ; 'd'
0x1800969f3  lea     ecx, [rdx-34h]
0x1800969f6  call    cs:__imp_?MsoShouldTrace@Logging@Mso@@YA_NW4Category@12@W4Severity@12@@Z; Mso::Logging::MsoShouldTrace(Mso::Logging::Category,Mso::Logging::Severity)
0x1800969fc  test    al, al
0x1800969fe  jnz     short loc_180096A64
0x180096a00  xor     r9d, r9d
0x180096a03  mov     r8d, r14d
0x180096a06  mov     rdx, rbx
0x180096a09  mov     rcx, r13
0x180096a0c  call    ?RefreshEvictedMap@Cache@1@AEAAXAEBVKeyHolder@1@W4EvictionType@1@_N@Z; Cache::Cache::RefreshEvictedMap(Cache::KeyHolder const &,Cache::EvictionType,bool)
0x180096a11  jmp     loc_180096950
0x180096a16  mov     r12, rsi
0x180096a19  jmp     short loc_1800969DE
0x180096a1b  test    rdi, rdi
0x180096a1e  jz      short loc_180096A56
0x180096a20  mov     rax, [rdi]
0x180096a23  test    rax, rax
0x180096a26  jz      short loc_180096A48
0x180096a28  mov     r8, r15
0x180096a2b  mov     rdx, [rbx+8]
0x180096a2f  mov     rcx, rdi
0x180096a32  mov     rax, [rax]
0x180096a35  call    cs:__guard_dispatch_icall_fptr
0x180096a3b  test    al, al
0x180096a3d  jnz     loc_180096997
0x180096a43  jmp     loc_18009690B
0x180096a48  xor     edx, edx
0x180096a4a  mov     ecx, 25D9804h
0x180096a4f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180096a55  nop
0x180096a56  xor     edx, edx
0x180096a58  mov     ecx, 2351871Ah
0x180096a5d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180096a63  int     3; Trap to Debugger
0x180096a64  lea     rax, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180096a6b  mov     edi, dword ptr [rsp+270h+var_210]
0x180096a6f  xorps   xmm0, xmm0
0x180096a72  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180096a7a  mov     rcx, r15
0x180096a7d  cmp     dword ptr [r13+88h], 1
0x180096a85  jnz     loc_180096C71
0x180096a8b  mov     [rbp+170h+var_190], rax
0x180096a8f  lea     rax, aMruval; "mruVal"
0x180096a96  mov     [rbp+170h+var_188], rax
0x180096a9a  mov     [rbp+170h+var_180], edi
0x180096a9d  mov     edi, 4
0x180096aa2  mov     [rbp+170h+var_17C], di
0x180096aa6  movups  [rbp+170h+var_178], xmm0
0x180096aaa  movdqu  [rbp+170h+var_168], xmm6
0x180096aaf  mov     word ptr [rbp+170h+var_178], si
0x180096ab3  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x180096aba  mov     [rbp+170h+var_D0], rax
0x180096ac1  lea     rax, aObjectmemsizeb; "objectMemSizeBytes"
0x180096ac8  mov     [rbp+170h+var_C8], rax
0x180096acf  mov     [rbp+170h+var_C0], r12
0x180096ad6  mov     [rbp+170h+var_B8], di
0x180096add  movups  [rbp+170h+var_B0], xmm0
0x180096ae4  movdqa  [rbp+170h+var_A0], xmm6
0x180096aec  mov     word ptr [rbp+170h+var_B0], si
0x180096af3  mov     rax, [r15]
0x180096af6  mov     rax, [rax]
0x180096af9  call    cs:__guard_dispatch_icall_fptr
0x180096aff  dec     eax
0x180096b01  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x180096b08  mov     [rbp+170h+var_1C8], rcx
0x180096b0c  lea     rcx, aRefcount; "refCount"
0x180096b13  mov     [rbp+170h+var_1C0], rcx
0x180096b17  mov     [rbp+170h+var_1B8], eax
0x180096b1a  mov     [rbp+170h+var_1B4], di
0x180096b1e  xorps   xmm0, xmm0
0x180096b21  movups  [rbp+170h+var_1B0], xmm0
0x180096b25  movdqu  [rbp+170h+var_1A0], xmm6
0x180096b2a  mov     word ptr [rbp+170h+var_1B0], si
0x180096b2e  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180096b35  mov     [rbp+170h+var_110], r8
0x180096b39  lea     rax, aEvicttype; "evictType"
0x180096b40  mov     [rbp+170h+var_108], rax
0x180096b44  mov     ecx, r14d
0x180096b47  call    sub_1800047F0
0x180096b4c  mov     [rbp+170h+var_100], rax
0x180096b50  mov     [rbp+170h+var_F8], di
0x180096b54  movups  [rbp+170h+var_F0], xmm0
0x180096b5b  movdqa  [rbp+170h+var_E0], xmm6
0x180096b63  mov     word ptr [rbp+170h+var_F0], si
0x180096b6a  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x180096b71  mov     [rbp+170h+var_150], rax
0x180096b75  lea     rax, aObjectptr; "objectPtr"
0x180096b7c  mov     [rbp+170h+var_148], rax
0x180096b80  mov     rax, [rbp+170h+var_1F0]
0x180096b84  mov     [rbp+170h+var_140], rax
0x180096b88  mov     [rbp+170h+var_138], di
0x180096b8c  movups  [rbp+170h+var_130], xmm0
0x180096b90  movdqa  [rbp+170h+var_120], xmm6
0x180096b95  mov     word ptr [rbp+170h+var_130], si
0x180096b99  mov     [rbp+170h+var_90], r8
0x180096ba0  lea     rax, aCachetype; "cacheType"
0x180096ba7  mov     [rbp+170h+var_88], rax
0x180096bae  mov     ecx, [r13+70h]
0x180096bb2  call    sub_18000D6BC
0x180096bb7  mov     [rbp+170h+var_80], rax
0x180096bbe  mov     [rbp+170h+var_78], di
0x180096bc5  movups  [rbp+170h+var_70], xmm0
0x180096bcc  movdqa  [rbp+170h+var_60], xmm6
0x180096bd4  mov     word ptr [rbp+170h+var_70], si
0x180096bdb  lea     rax, aGfxCacheEvicto; "Gfx::Cache::EvictOrAddToMap - Evicted a"...
0x180096be2  mov     [rsp+270h+var_208], rax
0x180096be7  lea     rax, [rbp+170h+var_190]
0x180096beb  mov     [rsp+270h+var_220], rax
0x180096bf0  lea     rax, [rbp+170h+var_D0]
0x180096bf7  mov     [rsp+270h+var_228], rax
0x180096bfc  lea     rax, [rbp+170h+var_1C8]
0x180096c00  mov     [rsp+270h+var_230], rax
0x180096c05  lea     rax, [rbp+170h+var_110]
0x180096c09  mov     [rsp+270h+var_238], rax
0x180096c0e  lea     rax, [rbp+170h+var_150]
0x180096c12  mov     [rsp+270h+var_240], rax
0x180096c17  lea     rax, [rbp+170h+var_90]
0x180096c1e  mov     [rsp+270h+var_248], rax
0x180096c23  lea     rax, [rsp+270h+var_208]
0x180096c28  mov     [rsp+270h+var_250], rax
0x180096c2d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEBX@23@U123@U?$ClassifiedStructuredObject@H@23@U?$ClassifiedStructuredObject@_K@23@U?$ClassifiedStructuredObject@I@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@4$$QEAU?$ClassifiedStructuredObject@H@01@$$QEAU?$ClassifiedStructuredObject@_K@01@$$QEAU?$ClassifiedStructuredObject@I@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<int> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x180096c32  lea     rcx, [rbp+170h+var_70]
0x180096c39  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180096c3e  lea     rcx, [rbp+170h+var_130]
0x180096c42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180096c47  lea     rcx, [rbp+170h+var_F0]
0x180096c4e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180096c53  lea     rcx, [rbp+170h+var_1B0]
0x180096c57  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180096c5c  lea     rcx, [rbp+170h+var_B0]
0x180096c63  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180096c68  lea     rcx, [rbp+170h+var_178]
0x180096c6c  jmp     loc_180096DFA
0x180096c71  mov     [rbp+170h+var_1C8], rax
0x180096c75  lea     rax, aMruval; "mruVal"
0x180096c7c  mov     [rbp+170h+var_1C0], rax
0x180096c80  mov     [rbp+170h+var_1B8], edi
0x180096c83  mov     edi, 4
0x180096c88  mov     [rbp+170h+var_1B4], di
0x180096c8c  movups  [rbp+170h+var_1B0], xmm0
0x180096c90  movdqu  [rbp+170h+var_1A0], xmm6
0x180096c95  mov     word ptr [rbp+170h+var_1B0], si
0x180096c99  mov     rax, [r15]
0x180096c9c  mov     rax, [rax]
0x180096c9f  call    cs:__guard_dispatch_icall_fptr
0x180096ca5  dec     eax
0x180096ca7  lea     rcx, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x180096cae  mov     [rbp+170h+var_190], rcx
0x180096cb2  lea     rcx, aRefcount; "refCount"
0x180096cb9  mov     [rbp+170h+var_188], rcx
0x180096cbd  mov     [rbp+170h+var_180], eax
0x180096cc0  mov     [rbp+170h+var_17C], di
0x180096cc4  xorps   xmm0, xmm0
0x180096cc7  movups  [rbp+170h+var_178], xmm0
0x180096ccb  movdqu  [rbp+170h+var_168], xmm6
0x180096cd0  mov     word ptr [rbp+170h+var_178], si
0x180096cd4  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180096cdb  mov     [rbp+170h+var_150], r8
0x180096cdf  lea     rax, aEvicttype; "evictType"
0x180096ce6  mov     [rbp+170h+var_148], rax
0x180096cea  mov     ecx, r14d
0x180096ced  call    sub_1800047F0
0x180096cf2  mov     [rbp+170h+var_140], rax
0x180096cf6  mov     [rbp+170h+var_138], di
0x180096cfa  movups  [rbp+170h+var_130], xmm0
0x180096cfe  movdqa  [rbp+170h+var_120], xmm6
0x180096d03  mov     word ptr [rbp+170h+var_130], si
0x180096d07  lea     rax, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x180096d0e  mov     [rbp+170h+var_110], rax
0x180096d12  lea     rax, aObjectptr; "objectPtr"
0x180096d19  mov     [rbp+170h+var_108], rax
0x180096d1d  mov     rax, [rbp+170h+var_1F0]
0x180096d21  mov     [rbp+170h+var_100], rax
0x180096d25  mov     [rbp+170h+var_F8], di
0x180096d29  movups  [rbp+170h+var_F0], xmm0
0x180096d30  movdqa  [rbp+170h+var_E0], xmm6
0x180096d38  mov     word ptr [rbp+170h+var_F0], si
0x180096d3f  mov     [rbp+170h+var_D0], r8
0x180096d46  lea     rax, aCachetype; "cacheType"
0x180096d4d  mov     [rbp+170h+var_C8], rax
0x180096d54  mov     ecx, [r13+70h]
0x180096d58  call    sub_18000D6BC
0x180096d5d  mov     [rbp+170h+var_C0], rax
0x180096d64  mov     [rbp+170h+var_B8], di
0x180096d6b  movups  [rbp+170h+var_B0], xmm0
0x180096d72  movdqa  [rbp+170h+var_A0], xmm6
0x180096d7a  mov     word ptr [rbp+170h+var_B0], si
0x180096d81  lea     rax, aGfxCacheEvicto_0; "Gfx::Cache::EvictOrAddToMap - Evicted a"...
0x180096d88  mov     [rsp+270h+var_208], rax
0x180096d8d  lea     rax, [rbp+170h+var_1C8]
0x180096d91  mov     [rsp+270h+var_228], rax
0x180096d96  lea     rax, [rbp+170h+var_190]
0x180096d9a  mov     [rsp+270h+var_230], rax
  ... truncated ...
```

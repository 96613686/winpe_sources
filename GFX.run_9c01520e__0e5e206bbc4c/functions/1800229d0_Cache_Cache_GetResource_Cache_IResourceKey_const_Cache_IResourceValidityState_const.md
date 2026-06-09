# Cache::Cache::GetResource(Cache::IResourceKey const &,Cache::IResourceValidityState const *)

- ea: `0x1800229d0`
- end: `0x180022fba`
- name: `?GetResource@Cache@1@QEAA?AV?$TCntPtr@UIRefCounted@Mso@@@Mso@@AEBUIResourceKey@1@PEBUIResourceValidityState@1@@Z`
- size: `1514`
- prototype: `__int64 __fastcall(Cache::Cache *this, void **)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18000e5d8`
- `0x180022814`
- `0x1800962d0`

## callees

- `0x1800074c0`
- `0x18000d6bc`
- `0x18000d920`
- `0x18000f790`
- `0x18000f974`
- `0x18001f854`
- `0x180021624`
- `0x1800229d0`
- `0x180022fc0`
- `0x180025520`
- `0x1800578b0`
- `0x180057e70`
- `0x180077780`
- `0x180096404`
- `0x180104138`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180022c01`
- `KERNEL32!GetCurrentThreadId` at `0x180022e16`
- `KERNEL32!GetCurrentThreadId` at `0x180022f07`
- `KERNEL32!GetCurrentThreadId` at `0x180022c01`
- `KERNEL32!GetCurrentThreadId` at `0x180022e16`
- `KERNEL32!GetCurrentThreadId` at `0x180022f07`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180022d27`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180022d27`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022ee7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022ef5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022ee7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022ef5`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180022b37`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180022b37`

## string_xrefs

- `0x180022c12`: `threadID`
- `0x180022e20`: `threadID`
- `0x180022f18`: `threadID`
- `0x180022c4f`: `cacheType`
- `0x180022e57`: `cacheType`
- `0x180022f4f`: `cacheType`
- `0x180022c70`: `Gfx::Cache::GetResource - removed invalid object`
- `0x180022e78`: `Gfx::Cache::GetResource - cache hit`
- `0x180022f70`: `Gfx::Cache::GetResource - cache miss`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void **__fastcall Cache::Cache::GetResource(Cache::Cache *this, void **a2, __int64 a3, const char *a4)
{
  void (__fastcall ***v6)(_QWORD); // rdi
  Cache::IResourceKey **v7; // rax
  Cache::IResourceKey *v8; // rsi
  __int64 v9; // rdx
  char v10; // r12
  void **v11; // r13
  __int64 v12; // rax
  __int64 v13; // rbx
  __m128i si128; // xmm6
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 (__fastcall *v18)(__int64, _QWORD); // rax
  void (__fastcall ***v19)(_QWORD); // rbx
  bool v20; // al
  DWORD v21; // eax
  __int64 v22; // rax
  int v23; // edx
  int v24; // r8d
  int v25; // r9d
  unsigned __int64 (__fastcall *v26)(GEL::MipmapInstanceCacheKey *__hidden); // rax
  Cache::IResourceKey *v27; // rcx
  __int64 EstimatedMemSizeBytes; // rax
  __int64 v29; // rax
  DWORD CurrentThreadId; // eax
  __int64 v31; // rax
  int v32; // edx
  int v33; // r8d
  int v34; // r9d
  DWORD v35; // eax
  __int64 v36; // rax
  int v37; // edx
  int v38; // r8d
  int v39; // r9d
  const char *v40; // [rsp+58h] [rbp-B0h] BYREF
  const char *v41; // [rsp+60h] [rbp-A8h] BYREF
  const char *v42; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v43[3]; // [rsp+70h] [rbp-98h] BYREF
  void **v44; // [rsp+88h] [rbp-80h] BYREF
  const char *v45; // [rsp+90h] [rbp-78h]
  DWORD v46; // [rsp+98h] [rbp-70h]
  __int16 v47; // [rsp+9Ch] [rbp-6Ch]
  __int128 v48; // [rsp+A0h] [rbp-68h] BYREF
  __m128i v49; // [rsp+B0h] [rbp-58h]
  void **v50; // [rsp+C8h] [rbp-40h] BYREF
  const char *v51; // [rsp+D0h] [rbp-38h]
  __int64 v52; // [rsp+D8h] [rbp-30h]
  __int16 v53; // [rsp+E0h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v55; // [rsp+F8h] [rbp-10h]
  _QWORD v56[2]; // [rsp+108h] [rbp+0h] BYREF
  DWORD v57; // [rsp+118h] [rbp+10h]
  __int16 v58; // [rsp+11Ch] [rbp+14h]
  _OWORD v59[2]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v60[3]; // [rsp+148h] [rbp+40h] BYREF
  __int16 v61; // [rsp+160h] [rbp+58h]
  _OWORD v62[2]; // [rsp+168h] [rbp+60h] BYREF

  v42 = a4;
  v6 = 0;
  v41 = 0;
  v43[0] = &Cache::KeyHolder::`vftable';
  v7 = (Cache::IResourceKey **)(*(__int64 (__fastcall **)(__int64, const char **))(*(_QWORD *)a3 + 8LL))(a3, &v40);
  v8 = *v7;
  *v7 = 0;
  v43[1] = v8;
  if ( v40 )
    (**(void (__fastcall ***)(const char *, __int64))v40)(v40, 1);
  v40 = "KeyHolder ctor should not set m_pKeyVal as null";
  Cache::KeyHolder::TrackICachedResourceKey(v43, &v40);
  if ( byte_180522F70 < 0 )
    v10 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180522F70);
  else
    v10 = byte_180522F70 != 0;
  LOBYTE(v9) = 1;
  Cache::CacheManager::AcquireLock(&v40, v9);
  v11 = (void **)((char *)this + 32);
  v12 = std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(
          (char *)this + 32,
          v43);
  v13 = v12;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v12 == *((_QWORD *)this + 4) )
    goto LABEL_27;
  v15 = *(_QWORD *)(v12 + 48);
  v16 = 0;
  if ( !v15 )
  {
    *a2 = 0;
LABEL_8:
    if ( v40 )
      (*(void (__fastcall **)(const char *, __int64))(*(_QWORD *)v40 + 8LL))(v40, v16);
    if ( v8 )
    {
      if ( *(void (__fastcall **)(Cache::IResourceKey *__hidden))(*(_QWORD *)v8 + 16LL) == Cache::IResourceKey::Destroy )
        Cache::IResourceKey::Destroy(v8);
      else
        (*(void (__fastcall **)(Cache::IResourceKey *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return a2;
  }
  v18 = (__int64 (__fastcall *)(__int64, _QWORD))*((_QWORD *)this + 16);
  if ( !v18 )
    goto LABEL_46;
  v41 = (const char *)v18(v15, 0);
  if ( (*(unsigned __int8 (__fastcall **)(const char *, const char *))(*(_QWORD *)v41 + 8LL))(v41, v42) )
  {
    *(_DWORD *)(v13 + 56) = *((_DWORD *)this + 26);
    Cache::Cache::IncrementNextMRUVal(this);
    v6 = 0;
    if ( !v10 )
    {
LABEL_18:
      *a2 = *(void **)(v13 + 48);
      Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(a2);
      goto LABEL_8;
    }
    v11 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v44 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v45 = "foundObjectMRUVal";
    v46 = *(_DWORD *)(v13 + 56);
    v10 = 4;
    v47 = 4;
    v48 = 0;
    v49 = si128;
    LOWORD(v48) = 0;
    v29 = *(_QWORD *)(v13 + 48);
    if ( v29 )
    {
      v50 = &Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable';
      v51 = "foundObjectPtr";
      v52 = v29;
      v53 = 4;
      v54 = 0;
      v55 = si128;
      LOWORD(v54) = 0;
      CurrentThreadId = GetCurrentThreadId();
      v56[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
      v56[1] = "threadID";
      v57 = CurrentThreadId;
      v58 = 4;
      v59[0] = 0;
      v59[1] = si128;
      LOWORD(v59[0]) = 0;
      v31 = sub_18000D6BC(*((unsigned int *)this + 28));
      v60[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
      v60[1] = "cacheType";
      v60[2] = v31;
      v61 = 4;
      v62[0] = 0;
      v62[1] = si128;
      LOWORD(v62[0]) = 0;
      v42 = "Gfx::Cache::GetResource - cache hit";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        (unsigned int)"cacheType",
        v32,
        v33,
        v34,
        (__int64)&v42,
        (__int64)v60,
        (__int64)v56,
        (__int64)&v50,
        (__int64)&v44);
      std::wstring::~wstring(v62);
      std::wstring::~wstring(v59);
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(&v48);
      goto LABEL_18;
    }
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_46:
    CrashWithRecovery(0x23518707u, 0);
LABEL_47:
    EstimatedMemSizeBytes = v26(v27);
    goto LABEL_42;
  }
  v19 = *(void (__fastcall ****)(_QWORD))(v13 + 48);
  if ( v19 )
  {
    (**v19)(v19);
    v6 = v19;
  }
  if ( byte_180522F60 < 0 )
    v20 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180522F60);
  else
    v20 = byte_180522F60 != 0;
  if ( !v20 || *((_DWORD *)this + 34) != 1 )
    goto LABEL_25;
  v26 = *(unsigned __int64 (__fastcall **)(GEL::MipmapInstanceCacheKey *__hidden))(*(_QWORD *)v8 + 32LL);
  v27 = v8;
  if ( v26 != GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes )
    goto LABEL_47;
  EstimatedMemSizeBytes = GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(v8);
LABEL_42:
  *((_QWORD *)this + 18) -= EstimatedMemSizeBytes
                          + (*(__int64 (__fastcall **)(const char *))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_25:
  std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::erase(
    v11,
    v43);
  if ( v10 )
  {
    v21 = GetCurrentThreadId();
    v44 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v45 = "threadID";
    v46 = v21;
    v47 = 4;
    v48 = 0;
    v49 = si128;
    LOWORD(v48) = 0;
    v22 = sub_18000D6BC(*((unsigned int *)this + 28));
    v50 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v51 = "cacheType";
    v52 = v22;
    v53 = 4;
    v54 = 0;
    v55 = si128;
    LOWORD(v54) = 0;
    v41 = "Gfx::Cache::GetResource - removed invalid object";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      592545604,
      v23,
      v24,
      v25,
      (__int64)&v41,
      (__int64)&v50,
      (__int64)&v44);
    std::wstring::~wstring(&v54);
    std::wstring::~wstring(&v48);
  }
LABEL_27:
  if ( v40 )
    (*(void (__fastcall **)(const char *))(*(_QWORD *)v40 + 8LL))(v40);
  if ( v10 )
  {
    v35 = GetCurrentThreadId();
    v44 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v45 = "threadID";
    v46 = v35;
    v47 = 4;
    v48 = 0;
    v49 = si128;
    LOWORD(v48) = 0;
    v36 = sub_18000D6BC(*((unsigned int *)this + 28));
    v50 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v51 = "cacheType";
    v52 = v36;
    v53 = 4;
    v54 = 0;
    v55 = si128;
    LOWORD(v54) = 0;
    v41 = "Gfx::Cache::GetResource - cache miss";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      592545603,
      v37,
      v38,
      v39,
      (__int64)&v41,
      (__int64)&v50,
      (__int64)&v44);
    std::wstring::~wstring(&v54);
    std::wstring::~wstring(&v48);
  }
  *a2 = 0;
  if ( v8 )
  {
    if ( *(void (__fastcall **)(Cache::IResourceKey *__hidden))(*(_QWORD *)v8 + 16LL) == Cache::IResourceKey::Destroy )
      Cache::IResourceKey::Destroy(v8);
    else
      (*(void (__fastcall **)(Cache::IResourceKey *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( v6 )
    (*v6)[1](v6);
  return a2;
}

```

## disassembly

```asm
0x1800229d0  mov     rax, rsp
0x1800229d3  push    rbp
0x1800229d4  push    rbx
0x1800229d5  push    rsi
0x1800229d6  push    rdi
0x1800229d7  push    r12
0x1800229d9  push    r13
0x1800229db  push    r14
0x1800229dd  push    r15
0x1800229df  lea     rbp, [rax-0E8h]
0x1800229e6  sub     rsp, 1A8h
0x1800229ed  movaps  xmmword ptr [rax-58h], xmm6
0x1800229f1  mov     rax, cs:__security_cookie
0x1800229f8  xor     rax, rsp
0x1800229fb  mov     [rbp+0E0h+var_60], rax
0x180022a02  mov     [rsp+1E0h+var_180], r9
0x180022a07  mov     r14, rdx
0x180022a0a  mov     r15, rcx
0x180022a0d  mov     [rsp+1E0h+var_188], rdx
0x180022a12  xor     ebx, ebx
0x180022a14  mov     edi, ebx
0x180022a16  mov     [rsp+1E0h+var_188], rbx
0x180022a1b  lea     rax, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x180022a22  mov     [rsp+1E0h+var_178], rax
0x180022a27  mov     rax, [r8]
0x180022a2a  lea     rdx, [rsp+1E0h+var_190]
0x180022a2f  mov     rcx, r8
0x180022a32  mov     rax, [rax+8]
0x180022a36  call    cs:__guard_dispatch_icall_fptr
0x180022a3c  mov     rsi, [rax]
0x180022a3f  mov     [rax], rbx
0x180022a42  mov     [rsp+1E0h+var_178+8], rsi
0x180022a47  mov     rcx, [rsp+1E0h+var_190]
0x180022a4c  test    rcx, rcx
0x180022a4f  jnz     loc_180022D32
0x180022a55  lea     rax, aKeyholderCtorS; "KeyHolder ctor should not set m_pKeyVal"...
0x180022a5c  mov     [rsp+1E0h+var_190], rax
0x180022a61  lea     rdx, [rsp+1E0h+var_190]
0x180022a66  lea     rcx, [rsp+1E0h+var_178]
0x180022a6b  call    ?TrackICachedResourceKey@KeyHolder@Cache@@AEBAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; Cache::KeyHolder::TrackICachedResourceKey(Mso::StringLiterals::StringLiteral<char> const &)
0x180022a70  mov     al, cs:byte_180522F70
0x180022a76  test    al, al
0x180022a78  js      loc_180022B30
0x180022a7e  setnz   r12b
0x180022a82  mov     dl, 1
0x180022a84  lea     rcx, [rsp+1E0h+var_190]
0x180022a89  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x180022a8e  lea     r13, [r15+20h]
0x180022a92  lea     rdx, [rsp+1E0h+var_178]
0x180022a97  mov     rcx, r13
0x180022a9a  call    ??$_Find@VKeyHolder@Cache@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@1@AEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(Cache::KeyHolder const &)
0x180022a9f  mov     rbx, rax
0x180022aa2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180022aaa  cmp     rax, [r13+0]
0x180022aae  jz      loc_180022D16
0x180022ab4  mov     rcx, [rax+30h]
0x180022ab8  xor     edx, edx
0x180022aba  test    rcx, rcx
0x180022abd  jnz     loc_180022B45
0x180022ac3  mov     [r14], rdx
0x180022ac6  mov     rcx, [rsp+1E0h+var_190]
0x180022acb  test    rcx, rcx
0x180022ace  jz      short loc_180022ADD
0x180022ad0  mov     rax, [rcx]
0x180022ad3  mov     rax, [rax+8]
0x180022ad7  call    cs:__guard_dispatch_icall_fptr
0x180022add  test    rsi, rsi
0x180022ae0  jz      short loc_180022B02
0x180022ae2  mov     rax, [rsi]
0x180022ae5  mov     rdx, [rax+10h]
0x180022ae9  lea     rax, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022af0  mov     rcx, rsi; this
0x180022af3  cmp     rdx, rax
0x180022af6  jnz     loc_180022BA7
0x180022afc  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022b01  nop
0x180022b02  mov     rax, r14
0x180022b05  mov     rcx, [rbp+0E0h+var_60]
0x180022b0c  xor     rcx, rsp; StackCookie
0x180022b0f  call    __security_check_cookie
0x180022b14  movaps  xmm6, [rsp+1E0h+var_58+8]
0x180022b1c  add     rsp, 1A8h
0x180022b23  pop     r15
0x180022b25  pop     r14
0x180022b27  pop     r13
0x180022b29  pop     r12
0x180022b2b  pop     rdi
0x180022b2c  pop     rsi
0x180022b2d  pop     rbx
0x180022b2e  pop     rbp
0x180022b2f  retn
0x180022b30  lea     rcx, byte_180522F70
0x180022b37  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x180022b3d  mov     r12b, al
0x180022b40  jmp     loc_180022A82
0x180022b45  mov     rax, [r15+80h]
0x180022b4c  test    rax, rax
0x180022b4f  jz      loc_180022EEE
0x180022b55  call    cs:__guard_dispatch_icall_fptr
0x180022b5b  mov     rcx, rax
0x180022b5e  mov     [rsp+1E0h+var_188], rax
0x180022b63  mov     rax, [rax]
0x180022b66  mov     rdx, [rsp+1E0h+var_180]
0x180022b6b  mov     rax, [rax+8]
0x180022b6f  call    cs:__guard_dispatch_icall_fptr
0x180022b75  test    al, al
0x180022b77  jz      short loc_180022BB5
0x180022b79  mov     eax, [r15+68h]
0x180022b7d  mov     [rbx+38h], eax
0x180022b80  mov     rcx, r15; this
0x180022b83  call    ?IncrementNextMRUVal@Cache@1@IEAAXXZ; Cache::Cache::IncrementNextMRUVal(void)
0x180022b88  xor     edi, edi
0x180022b8a  test    r12b, r12b
0x180022b8d  jnz     loc_180022DA6
0x180022b93  mov     rax, [rbx+30h]
0x180022b97  mov     [r14], rax
0x180022b9a  mov     rcx, r14; void **
0x180022b9d  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x180022ba2  jmp     loc_180022AC6
0x180022ba7  mov     rax, rdx
0x180022baa  call    cs:__guard_dispatch_icall_fptr
0x180022bb0  jmp     loc_180022B02
0x180022bb5  mov     rbx, [rbx+30h]
0x180022bb9  test    rbx, rbx
0x180022bbc  jz      short loc_180022BD0
0x180022bbe  mov     rax, [rbx]
0x180022bc1  mov     rcx, rbx
0x180022bc4  mov     rax, [rax]
0x180022bc7  call    cs:__guard_dispatch_icall_fptr
0x180022bcd  mov     rdi, rbx
0x180022bd0  mov     al, cs:byte_180522F60
0x180022bd6  xor     ebx, ebx
0x180022bd8  test    al, al
0x180022bda  js      loc_180022D20
0x180022be0  setnz   al
0x180022be3  test    al, al
0x180022be5  jnz     loc_180022D53
0x180022beb  lea     rdx, [rsp+1E0h+var_178]
0x180022bf0  mov     rcx, r13
0x180022bf3  call    ?erase@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@QEAA_KAEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::erase(Cache::KeyHolder const &)
0x180022bf8  test    r12b, r12b
0x180022bfb  jz      loc_180022D18
0x180022c01  call    cs:__imp_GetCurrentThreadId
0x180022c07  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180022c0e  mov     [rbp+0E0h+var_160], rcx
0x180022c12  lea     rcx, aThreadid; "threadID"
0x180022c19  mov     [rbp+0E0h+var_158], rcx
0x180022c1d  mov     [rbp+0E0h+var_150], eax
0x180022c20  mov     r13d, 4
0x180022c26  mov     [rbp+0E0h+var_14C], r13w
0x180022c2b  xorps   xmm0, xmm0
0x180022c2e  movups  [rbp+0E0h+var_148], xmm0
0x180022c32  movdqu  [rbp+0E0h+var_138], xmm6
0x180022c37  mov     word ptr [rbp+0E0h+var_148], bx
0x180022c3b  mov     ecx, [r15+70h]
0x180022c3f  call    sub_18000D6BC
0x180022c44  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180022c4b  mov     [rbp+0E0h+var_120], rcx
0x180022c4f  lea     rcx, aCachetype; "cacheType"
0x180022c56  mov     [rbp+0E0h+var_118], rcx
0x180022c5a  mov     [rbp+0E0h+var_110], rax
0x180022c5e  mov     [rbp+0E0h+var_108], r13w
0x180022c63  movups  [rbp+0E0h+var_100], xmm0
0x180022c67  movdqa  [rbp+0E0h+var_F0], xmm6
0x180022c6c  mov     word ptr [rbp+0E0h+var_100], bx
0x180022c70  lea     rax, aGfxCacheGetres; "Gfx::Cache::GetResource - removed inval"...
0x180022c77  mov     [rsp+1E0h+var_188], rax
0x180022c7c  lea     rax, [rbp+0E0h+var_160]
0x180022c80  mov     [rsp+1E0h+var_1B0], rax
0x180022c85  lea     rax, [rbp+0E0h+var_120]
0x180022c89  mov     [rsp+1E0h+var_1B8], rax
0x180022c8e  lea     rax, [rsp+1E0h+var_188]
0x180022c93  mov     [rsp+1E0h+var_1C0], rax
0x180022c98  mov     ecx, 23518744h
0x180022c9d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x180022ca2  lea     rcx, [rbp+0E0h+var_100]
0x180022ca6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022cab  lea     rcx, [rbp+0E0h+var_148]
0x180022caf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022cb4  mov     rcx, [rsp+1E0h+var_190]
0x180022cb9  test    rcx, rcx
0x180022cbc  jz      short loc_180022CCB
0x180022cbe  mov     rax, [rcx]
0x180022cc1  mov     rax, [rax+8]
0x180022cc5  call    cs:__guard_dispatch_icall_fptr
0x180022ccb  test    r12b, r12b
0x180022cce  jnz     loc_180022F07
0x180022cd4  mov     [r14], rbx
0x180022cd7  test    rsi, rsi
0x180022cda  jz      short loc_180022CF8
0x180022cdc  mov     rax, [rsi]
0x180022cdf  mov     rdx, [rax+10h]
0x180022ce3  lea     rax, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022cea  mov     rcx, rsi; this
0x180022ced  cmp     rdx, rax
0x180022cf0  jnz     short loc_180022D48
0x180022cf2  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022cf7  nop
0x180022cf8  test    rdi, rdi
0x180022cfb  jz      loc_180022B02
0x180022d01  mov     rax, [rdi]
0x180022d04  mov     rcx, rdi
0x180022d07  mov     rax, [rax+8]
0x180022d0b  call    cs:__guard_dispatch_icall_fptr
0x180022d11  jmp     loc_180022B02
0x180022d16  xor     ebx, ebx
0x180022d18  mov     r13d, 4
0x180022d1e  jmp     short loc_180022CB4
0x180022d20  lea     rcx, byte_180522F60
0x180022d27  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180022d2d  jmp     loc_180022BE3
0x180022d32  mov     rax, [rcx]
0x180022d35  mov     edx, 1
0x180022d3a  mov     rax, [rax]
0x180022d3d  call    cs:__guard_dispatch_icall_fptr
0x180022d43  jmp     loc_180022A55
0x180022d48  mov     rax, rdx
0x180022d4b  call    cs:__guard_dispatch_icall_fptr
0x180022d51  jmp     short loc_180022CF8
0x180022d53  cmp     dword ptr [r15+88h], 1
0x180022d5b  jnz     loc_180022BEB
0x180022d61  mov     rax, [rsi]
0x180022d64  mov     rax, [rax+20h]
0x180022d68  lea     rcx, ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x180022d6f  cmp     rax, rcx
0x180022d72  mov     rcx, rsi; this
0x180022d75  jnz     loc_180022EFC
0x180022d7b  call    ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x180022d80  mov     rbx, rax
0x180022d83  mov     rcx, [rsp+1E0h+var_188]
0x180022d88  mov     rax, [rcx]
0x180022d8b  mov     rax, [rax+10h]
0x180022d8f  call    cs:__guard_dispatch_icall_fptr
0x180022d95  add     rax, rbx
0x180022d98  sub     [r15+90h], rax
0x180022d9f  xor     ebx, ebx
0x180022da1  jmp     loc_180022BEB
0x180022da6  lea     r13, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180022dad  mov     [rbp+0E0h+var_160], r13
0x180022db1  lea     rax, aFoundobjectmru; "foundObjectMRUVal"
0x180022db8  mov     [rbp+0E0h+var_158], rax
0x180022dbc  mov     eax, [rbx+38h]
0x180022dbf  mov     [rbp+0E0h+var_150], eax
0x180022dc2  mov     r12d, 4
0x180022dc8  mov     [rbp+0E0h+var_14C], r12w
0x180022dcd  xorps   xmm0, xmm0
0x180022dd0  movups  [rbp+0E0h+var_148], xmm0
0x180022dd4  movdqu  [rbp+0E0h+var_138], xmm6
0x180022dd9  mov     word ptr [rbp+0E0h+var_148], di
0x180022ddd  mov     rax, [rbx+30h]
0x180022de1  test    rax, rax
0x180022de4  jz      loc_180022EE0
0x180022dea  lea     rcx, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x180022df1  mov     [rbp+0E0h+var_120], rcx
0x180022df5  lea     rcx, aFoundobjectptr; "foundObjectPtr"
0x180022dfc  mov     [rbp+0E0h+var_118], rcx
0x180022e00  mov     [rbp+0E0h+var_110], rax
0x180022e04  mov     [rbp+0E0h+var_108], r12w
0x180022e09  movups  [rbp+0E0h+var_100], xmm0
0x180022e0d  movdqa  [rbp+0E0h+var_F0], xmm6
0x180022e12  mov     word ptr [rbp+0E0h+var_100], di
0x180022e16  call    cs:__imp_GetCurrentThreadId
0x180022e1c  mov     [rbp+0E0h+var_E0], r13
0x180022e20  lea     rcx, aThreadid; "threadID"
0x180022e27  mov     [rbp+0E0h+var_D8], rcx
0x180022e2b  mov     [rbp+0E0h+var_D0], eax
0x180022e2e  mov     [rbp+0E0h+var_CC], r12w
0x180022e33  xorps   xmm0, xmm0
0x180022e36  movups  [rbp+0E0h+var_C8], xmm0
0x180022e3a  movdqu  [rbp+0E0h+var_B8], xmm6
0x180022e3f  mov     word ptr [rbp+0E0h+var_C8], di
0x180022e43  mov     ecx, [r15+70h]
0x180022e47  call    sub_18000D6BC
0x180022e4c  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180022e53  mov     [rbp+0E0h+var_A0], rcx
0x180022e57  lea     rcx, aCachetype; "cacheType"
0x180022e5e  mov     [rbp+0E0h+var_98], rcx
0x180022e62  mov     [rbp+0E0h+var_90], rax
0x180022e66  mov     [rbp+0E0h+var_88], r12w
0x180022e6b  movups  [rbp+0E0h+var_80], xmm0
0x180022e6f  movdqa  [rbp+0E0h+var_70], xmm6
0x180022e74  mov     word ptr [rbp+0E0h+var_80], di
0x180022e78  lea     rax, aGfxCacheGetres_1; "Gfx::Cache::GetResource - cache hit"
0x180022e7f  mov     [rsp+1E0h+var_180], rax
0x180022e84  lea     rax, [rbp+0E0h+var_160]
0x180022e88  mov     [rsp+40h], rax
0x180022e8d  lea     rax, [rbp+0E0h+var_120]
0x180022e91  mov     [rsp+1E0h+var_1A8], rax
0x180022e96  lea     rax, [rbp+0E0h+var_E0]
0x180022e9a  mov     [rsp+1E0h+var_1B0], rax
0x180022e9f  lea     rax, [rbp+0E0h+var_A0]
0x180022ea3  mov     [rsp+1E0h+var_1B8], rax
0x180022ea8  lea     rax, [rsp+1E0h+var_180]
0x180022ead  mov     [rsp+1E0h+var_1C0], rax
0x180022eb2  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@I@23@U?$ClassifiedStructuredObject@PEBX@23@U423@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@5@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x180022eb7  lea     rcx, [rbp+0E0h+var_80]
0x180022ebb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022ec0  lea     rcx, [rbp+0E0h+var_C8]
0x180022ec4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022ec9  lea     rcx, [rbp+0E0h+var_100]
  ... truncated ...
```

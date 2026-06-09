# Cache::Cache::GetResource(Cache::IResourceKey const &,Cache::IResourceValidityState const *)

- ea: `0x180022370`
- end: `0x180022965`
- name: `?GetResource@Cache@1@QEAA?AV?$TCntPtr@UIRefCounted@Mso@@@Mso@@AEBUIResourceKey@1@PEBUIResourceValidityState@1@@Z`
- size: `1525`
- prototype: `__int64 __fastcall(Cache::Cache *this, void **)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18000db54`
- `0x1800221b4`
- `0x18006715c`

## callees

- `0x180007a40`
- `0x18000d7fc`
- `0x18000da60`
- `0x18000f890`
- `0x18000fa80`
- `0x18001f6c0`
- `0x180020254`
- `0x180022370`
- `0x180022970`
- `0x180025000`
- `0x180056ee0`
- `0x1800573f0`
- `0x180067298`
- `0x18007aa30`
- `0x180106b6c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800225a1`
- `KERNEL32!GetCurrentThreadId` at `0x1800227c1`
- `KERNEL32!GetCurrentThreadId` at `0x1800228b2`
- `KERNEL32!GetCurrentThreadId` at `0x1800225a1`
- `KERNEL32!GetCurrentThreadId` at `0x1800227c1`
- `KERNEL32!GetCurrentThreadId` at `0x1800228b2`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800226e8`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800226e8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022892`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800228a0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180022892`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800228a0`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800224d7`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800224d7`

## string_xrefs

- `0x1800225b2`: `threadID`
- `0x1800227cb`: `threadID`
- `0x1800228c3`: `threadID`
- `0x1800225ef`: `cacheType`
- `0x180022802`: `cacheType`
- `0x1800228fa`: `cacheType`
- `0x180022610`: `Gfx::Cache::GetResource - removed invalid object`
- `0x180022823`: `Gfx::Cache::GetResource - cache hit`
- `0x18002291b`: `Gfx::Cache::GetResource - cache miss`

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
  if ( byte_18051EEC8 < 0 )
    v10 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18051EEC8);
  else
    v10 = byte_18051EEC8 != 0;
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
      v31 = sub_18000D7FC(*((unsigned int *)this + 28));
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
  if ( byte_18051EEE0 < 0 )
    v20 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051EEE0);
  else
    v20 = byte_18051EEE0 != 0;
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
    v22 = sub_18000D7FC(*((unsigned int *)this + 28));
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
    v36 = sub_18000D7FC(*((unsigned int *)this + 28));
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
0x180022370  mov     rax, rsp
0x180022373  push    rbp
0x180022374  push    rbx
0x180022375  push    rsi
0x180022376  push    rdi
0x180022377  push    r12
0x180022379  push    r13
0x18002237b  push    r14
0x18002237d  push    r15
0x18002237f  lea     rbp, [rax-0E8h]
0x180022386  sub     rsp, 1A8h
0x18002238d  movaps  xmmword ptr [rax-58h], xmm6
0x180022391  mov     rax, cs:__security_cookie
0x180022398  xor     rax, rsp
0x18002239b  mov     [rbp+0E0h+var_60], rax
0x1800223a2  mov     [rsp+1E0h+var_180], r9
0x1800223a7  mov     r14, rdx
0x1800223aa  mov     r15, rcx
0x1800223ad  mov     [rsp+1E0h+var_188], rdx
0x1800223b2  xor     ebx, ebx
0x1800223b4  mov     edi, ebx
0x1800223b6  mov     [rsp+1E0h+var_188], rbx
0x1800223bb  lea     rax, ??_7KeyHolder@Cache@@6B@; const Cache::KeyHolder::`vftable'
0x1800223c2  mov     [rsp+1E0h+var_178], rax
0x1800223c7  mov     rax, [r8]
0x1800223ca  lea     rdx, [rsp+1E0h+var_190]
0x1800223cf  mov     rcx, r8
0x1800223d2  mov     rax, [rax+8]
0x1800223d6  call    cs:__guard_dispatch_icall_fptr
0x1800223dc  mov     rsi, [rax]
0x1800223df  mov     [rax], rbx
0x1800223e2  mov     [rsp+1E0h+var_178+8], rsi
0x1800223e7  mov     rcx, [rsp+1E0h+var_190]
0x1800223ec  test    rcx, rcx
0x1800223ef  jnz     loc_1800226BE
0x1800223f5  lea     rax, aKeyholderCtorS; "KeyHolder ctor should not set m_pKeyVal"...
0x1800223fc  mov     [rsp+1E0h+var_190], rax
0x180022401  lea     rdx, [rsp+1E0h+var_190]
0x180022406  lea     rcx, [rsp+1E0h+var_178]
0x18002240b  call    ?TrackICachedResourceKey@KeyHolder@Cache@@AEBAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; Cache::KeyHolder::TrackICachedResourceKey(Mso::StringLiterals::StringLiteral<char> const &)
0x180022410  mov     al, cs:byte_18051EEC8
0x180022416  test    al, al
0x180022418  js      loc_1800224D0
0x18002241e  setnz   r12b
0x180022422  mov     dl, 1
0x180022424  lea     rcx, [rsp+1E0h+var_190]
0x180022429  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x18002242e  lea     r13, [r15+20h]
0x180022432  lea     rdx, [rsp+1E0h+var_178]
0x180022437  mov     rcx, r13
0x18002243a  call    ??$_Find@VKeyHolder@Cache@@@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@PEAX@1@AEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::_Find<Cache::KeyHolder>(Cache::KeyHolder const &)
0x18002243f  mov     rbx, rax
0x180022442  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002244a  cmp     rax, [r13+0]
0x18002244e  jz      loc_1800226D4
0x180022454  mov     rcx, [rax+30h]
0x180022458  xor     edx, edx
0x18002245a  test    rcx, rcx
0x18002245d  jnz     loc_1800224E5
0x180022463  mov     [r14], rdx
0x180022466  mov     rcx, [rsp+1E0h+var_190]
0x18002246b  test    rcx, rcx
0x18002246e  jz      short loc_18002247D
0x180022470  mov     rax, [rcx]
0x180022473  mov     rax, [rax+8]
0x180022477  call    cs:__guard_dispatch_icall_fptr
0x18002247d  test    rsi, rsi
0x180022480  jz      short loc_1800224A2
0x180022482  mov     rax, [rsi]
0x180022485  mov     rdx, [rax+10h]
0x180022489  lea     rax, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022490  mov     rcx, rsi; this
0x180022493  cmp     rdx, rax
0x180022496  jnz     loc_180022547
0x18002249c  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x1800224a1  nop
0x1800224a2  mov     rax, r14
0x1800224a5  mov     rcx, [rbp+0E0h+var_60]
0x1800224ac  xor     rcx, rsp; StackCookie
0x1800224af  call    __security_check_cookie
0x1800224b4  movaps  xmm6, [rsp+1E0h+var_58+8]
0x1800224bc  add     rsp, 1A8h
0x1800224c3  pop     r15
0x1800224c5  pop     r14
0x1800224c7  pop     r13
0x1800224c9  pop     r12
0x1800224cb  pop     rdi
0x1800224cc  pop     rsi
0x1800224cd  pop     rbx
0x1800224ce  pop     rbp
0x1800224cf  retn
0x1800224d0  lea     rcx, byte_18051EEC8
0x1800224d7  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1800224dd  mov     r12b, al
0x1800224e0  jmp     loc_180022422
0x1800224e5  mov     rax, [r15+80h]
0x1800224ec  test    rax, rax
0x1800224ef  jz      loc_180022899
0x1800224f5  call    cs:__guard_dispatch_icall_fptr
0x1800224fb  mov     rcx, rax
0x1800224fe  mov     [rsp+1E0h+var_188], rax
0x180022503  mov     rax, [rax]
0x180022506  mov     rdx, [rsp+1E0h+var_180]
0x18002250b  mov     rax, [rax+8]
0x18002250f  call    cs:__guard_dispatch_icall_fptr
0x180022515  test    al, al
0x180022517  jz      short loc_180022555
0x180022519  mov     eax, [r15+68h]
0x18002251d  mov     [rbx+38h], eax
0x180022520  mov     rcx, r15; this
0x180022523  call    ?IncrementNextMRUVal@Cache@1@IEAAXXZ; Cache::Cache::IncrementNextMRUVal(void)
0x180022528  xor     edi, edi
0x18002252a  test    r12b, r12b
0x18002252d  jnz     loc_180022751
0x180022533  mov     rax, [rbx+30h]
0x180022537  mov     [r14], rax
0x18002253a  mov     rcx, r14; void **
0x18002253d  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x180022542  jmp     loc_180022466
0x180022547  mov     rax, rdx
0x18002254a  call    cs:__guard_dispatch_icall_fptr
0x180022550  jmp     loc_1800224A2
0x180022555  mov     rbx, [rbx+30h]
0x180022559  test    rbx, rbx
0x18002255c  jz      short loc_180022570
0x18002255e  mov     rax, [rbx]
0x180022561  mov     rcx, rbx
0x180022564  mov     rax, [rax]
0x180022567  call    cs:__guard_dispatch_icall_fptr
0x18002256d  mov     rdi, rbx
0x180022570  mov     al, cs:byte_18051EEE0
0x180022576  xor     ebx, ebx
0x180022578  test    al, al
0x18002257a  js      loc_1800226E1
0x180022580  setnz   al
0x180022583  test    al, al
0x180022585  jnz     loc_1800226FE
0x18002258b  lea     rdx, [rsp+1E0h+var_178]
0x180022590  mov     rcx, r13
0x180022593  call    ?erase@?$_Tree@V?$_Tmap_traits@VKeyHolder@Cache@@UValueMRUPair@22@U?$less@VKeyHolder@Cache@@@std@@V?$allocator@U?$pair@$$CBVKeyHolder@Cache@@UValueMRUPair@22@@std@@@5@$0A@@std@@@std@@QEAA_KAEBVKeyHolder@Cache@@@Z; std::_Tree<std::_Tmap_traits<Cache::KeyHolder,Cache::Cache::ValueMRUPair,std::less<Cache::KeyHolder>,std::allocator<std::pair<Cache::KeyHolder const,Cache::Cache::ValueMRUPair>>,0>>::erase(Cache::KeyHolder const &)
0x180022598  test    r12b, r12b
0x18002259b  jz      loc_1800226D6
0x1800225a1  call    cs:__imp_GetCurrentThreadId
0x1800225a7  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800225ae  mov     [rbp+0E0h+var_160], rcx
0x1800225b2  lea     rcx, aThreadid; "threadID"
0x1800225b9  mov     [rbp+0E0h+var_158], rcx
0x1800225bd  mov     [rbp+0E0h+var_150], eax
0x1800225c0  mov     r13d, 4
0x1800225c6  mov     [rbp+0E0h+var_14C], r13w
0x1800225cb  xorps   xmm0, xmm0
0x1800225ce  movups  [rbp+0E0h+var_148], xmm0
0x1800225d2  movdqu  [rbp+0E0h+var_138], xmm6
0x1800225d7  mov     word ptr [rbp+0E0h+var_148], bx
0x1800225db  mov     ecx, [r15+70h]
0x1800225df  call    sub_18000D7FC
0x1800225e4  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800225eb  mov     [rbp+0E0h+var_120], rcx
0x1800225ef  lea     rcx, aCachetype; "cacheType"
0x1800225f6  mov     [rbp+0E0h+var_118], rcx
0x1800225fa  mov     [rbp+0E0h+var_110], rax
0x1800225fe  mov     [rbp+0E0h+var_108], r13w
0x180022603  movups  [rbp+0E0h+var_100], xmm0
0x180022607  movdqa  [rbp+0E0h+var_F0], xmm6
0x18002260c  mov     word ptr [rbp+0E0h+var_100], bx
0x180022610  lea     rax, aGfxCacheGetres; "Gfx::Cache::GetResource - removed inval"...
0x180022617  mov     [rsp+1E0h+var_188], rax
0x18002261c  lea     rax, [rbp+0E0h+var_160]
0x180022620  mov     [rsp+1E0h+var_1B0], rax
0x180022625  lea     rax, [rbp+0E0h+var_120]
0x180022629  mov     [rsp+1E0h+var_1B8], rax
0x18002262e  lea     rax, [rsp+1E0h+var_188]
0x180022633  mov     [rsp+1E0h+var_1C0], rax
0x180022638  mov     ecx, 23518744h
0x18002263d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x180022642  lea     rcx, [rbp+0E0h+var_100]
0x180022646  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002264b  lea     rcx, [rbp+0E0h+var_148]
0x18002264f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022654  mov     rcx, [rsp+1E0h+var_190]
0x180022659  test    rcx, rcx
0x18002265c  jz      short loc_18002266B
0x18002265e  mov     rax, [rcx]
0x180022661  mov     rax, [rax+8]
0x180022665  call    cs:__guard_dispatch_icall_fptr
0x18002266b  test    r12b, r12b
0x18002266e  jnz     loc_1800228B2
0x180022674  mov     [r14], rbx
0x180022677  test    rsi, rsi
0x18002267a  jz      short loc_1800226A0
0x18002267c  mov     rax, [rsi]
0x18002267f  mov     rdx, [rax+10h]
0x180022683  lea     rax, ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x18002268a  mov     rcx, rsi; this
0x18002268d  cmp     rdx, rax
0x180022690  jnz     short loc_1800226F3
0x180022692  call    ?Destroy@IResourceKey@Cache@@UEAAXXZ; Cache::IResourceKey::Destroy(void)
0x180022697  nop
0x180022698  nop     dword ptr [rax+rax+00000000h]
0x1800226a0  test    rdi, rdi
0x1800226a3  jz      loc_1800224A2
0x1800226a9  mov     rax, [rdi]
0x1800226ac  mov     rcx, rdi
0x1800226af  mov     rax, [rax+8]
0x1800226b3  call    cs:__guard_dispatch_icall_fptr
0x1800226b9  jmp     loc_1800224A2
0x1800226be  mov     rax, [rcx]
0x1800226c1  mov     edx, 1
0x1800226c6  mov     rax, [rax]
0x1800226c9  call    cs:__guard_dispatch_icall_fptr
0x1800226cf  jmp     loc_1800223F5
0x1800226d4  xor     ebx, ebx
0x1800226d6  mov     r13d, 4
0x1800226dc  jmp     loc_180022654
0x1800226e1  lea     rcx, byte_18051EEE0
0x1800226e8  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800226ee  jmp     loc_180022583
0x1800226f3  mov     rax, rdx
0x1800226f6  call    cs:__guard_dispatch_icall_fptr
0x1800226fc  jmp     short loc_1800226A0
0x1800226fe  cmp     dword ptr [r15+88h], 1
0x180022706  jnz     loc_18002258B
0x18002270c  mov     rax, [rsi]
0x18002270f  mov     rax, [rax+20h]
0x180022713  lea     rcx, ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18002271a  cmp     rax, rcx
0x18002271d  mov     rcx, rsi; this
0x180022720  jnz     loc_1800228A7
0x180022726  call    ?GetEstimatedMemSizeBytes@MipmapInstanceCacheKey@GEL@@UEBA_KXZ; GEL::MipmapInstanceCacheKey::GetEstimatedMemSizeBytes(void)
0x18002272b  mov     rbx, rax
0x18002272e  mov     rcx, [rsp+1E0h+var_188]
0x180022733  mov     rax, [rcx]
0x180022736  mov     rax, [rax+10h]
0x18002273a  call    cs:__guard_dispatch_icall_fptr
0x180022740  add     rax, rbx
0x180022743  sub     [r15+90h], rax
0x18002274a  xor     ebx, ebx
0x18002274c  jmp     loc_18002258B
0x180022751  lea     r13, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180022758  mov     [rbp+0E0h+var_160], r13
0x18002275c  lea     rax, aFoundobjectmru; "foundObjectMRUVal"
0x180022763  mov     [rbp+0E0h+var_158], rax
0x180022767  mov     eax, [rbx+38h]
0x18002276a  mov     [rbp+0E0h+var_150], eax
0x18002276d  mov     r12d, 4
0x180022773  mov     [rbp+0E0h+var_14C], r12w
0x180022778  xorps   xmm0, xmm0
0x18002277b  movups  [rbp+0E0h+var_148], xmm0
0x18002277f  movdqu  [rbp+0E0h+var_138], xmm6
0x180022784  mov     word ptr [rbp+0E0h+var_148], di
0x180022788  mov     rax, [rbx+30h]
0x18002278c  test    rax, rax
0x18002278f  jz      loc_18002288B
0x180022795  lea     rcx, ??_7?$ClassifiedStructuredObject@PEBX@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<void const *>::`vftable'
0x18002279c  mov     [rbp+0E0h+var_120], rcx
0x1800227a0  lea     rcx, aFoundobjectptr; "foundObjectPtr"
0x1800227a7  mov     [rbp+0E0h+var_118], rcx
0x1800227ab  mov     [rbp+0E0h+var_110], rax
0x1800227af  mov     [rbp+0E0h+var_108], r12w
0x1800227b4  movups  [rbp+0E0h+var_100], xmm0
0x1800227b8  movdqa  [rbp+0E0h+var_F0], xmm6
0x1800227bd  mov     word ptr [rbp+0E0h+var_100], di
0x1800227c1  call    cs:__imp_GetCurrentThreadId
0x1800227c7  mov     [rbp+0E0h+var_E0], r13
0x1800227cb  lea     rcx, aThreadid; "threadID"
0x1800227d2  mov     [rbp+0E0h+var_D8], rcx
0x1800227d6  mov     [rbp+0E0h+var_D0], eax
0x1800227d9  mov     [rbp+0E0h+var_CC], r12w
0x1800227de  xorps   xmm0, xmm0
0x1800227e1  movups  [rbp+0E0h+var_C8], xmm0
0x1800227e5  movdqu  [rbp+0E0h+var_B8], xmm6
0x1800227ea  mov     word ptr [rbp+0E0h+var_C8], di
0x1800227ee  mov     ecx, [r15+70h]
0x1800227f2  call    sub_18000D7FC
0x1800227f7  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800227fe  mov     [rbp+0E0h+var_A0], rcx
0x180022802  lea     rcx, aCachetype; "cacheType"
0x180022809  mov     [rbp+0E0h+var_98], rcx
0x18002280d  mov     [rbp+0E0h+var_90], rax
0x180022811  mov     [rbp+0E0h+var_88], r12w
0x180022816  movups  [rbp+0E0h+var_80], xmm0
0x18002281a  movdqa  [rbp+0E0h+var_70], xmm6
0x18002281f  mov     word ptr [rbp+0E0h+var_80], di
0x180022823  lea     rax, aGfxCacheGetres_1; "Gfx::Cache::GetResource - cache hit"
0x18002282a  mov     [rsp+1E0h+var_180], rax
0x18002282f  lea     rax, [rbp+0E0h+var_160]
0x180022833  mov     [rsp+40h], rax
0x180022838  lea     rax, [rbp+0E0h+var_120]
0x18002283c  mov     [rsp+1E0h+var_1A8], rax
0x180022841  lea     rax, [rbp+0E0h+var_E0]
0x180022845  mov     [rsp+1E0h+var_1B0], rax
0x18002284a  lea     rax, [rbp+0E0h+var_A0]
0x18002284e  mov     [rsp+1E0h+var_1B8], rax
0x180022853  lea     rax, [rsp+1E0h+var_180]
0x180022858  mov     [rsp+1E0h+var_1C0], rax
0x18002285d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@U?$ClassifiedStructuredObject@I@23@U?$ClassifiedStructuredObject@PEBX@23@U423@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEBX@01@5@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<void const *>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<void const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x180022862  lea     rcx, [rbp+0E0h+var_80]
0x180022866  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002286b  lea     rcx, [rbp+0E0h+var_C8]
0x18002286f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```

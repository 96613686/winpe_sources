# Cache::CacheManager::EvictCore(Cache::CacheType,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)

- ea: `0x180004378`
- end: `0x1800047f0`
- name: `?EvictCore@CacheManager@Cache@@AEAA_KW4CacheType@2@W4EvictionType@2@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z`
- size: `1144`
- prototype: `__int64 __usercall@<rax>(Cache::CacheManager *this@<rcx>, __int64)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180004360`
- `0x180009a00`
- `0x1800b1760`
- `0x1801743c0`

## callees

- `0x180003c90`
- `0x180004378`
- `0x1800047f0`
- `0x180007280`
- `0x18000d6bc`
- `0x18001f854`
- `0x1800578b0`
- `0x180057e70`
- `0x180077780`
- `0x1800b17a0`
- `0x1800b17dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800046f0`
- `KERNEL32!GetCurrentThreadId` at `0x1800046f0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800044f3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18000451b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800044f3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18000451b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800044d5`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800044d5`

## string_xrefs

- `0x180004701`: `threadID`
- `0x1800046c6`: `cacheType`
- `0x1800045f0`: `oldCacheSize`
- `0x1800045ac`: `newCacheSize`
- `0x180004729`: `CacheManager::Evict`

## pseudocode

```c
__int64 __fastcall Cache::CacheManager::EvictCore(
        Cache::CacheManager *this,
        __int64 a2,
        unsigned int a3,
        const char *a4,
        __int64 a5)
{
  const char *v5; // r15
  unsigned int v6; // ebx
  __int64 v7; // r13
  __int64 v9; // rsi
  unsigned __int64 TotalCachesSize; // r14
  unsigned int v11; // r15d
  _QWORD *v12; // r14
  __int64 v13; // rcx
  char v14; // al
  bool v15; // al
  bool v17; // zf
  __m128i si128; // xmm6
  unsigned __int64 v19; // rax
  __int16 v20; // r9
  __int64 v21; // r8
  __int16 v22; // r9
  DWORD CurrentThreadId; // eax
  int v24; // edx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v28; // [rsp+80h] [rbp-88h]
  const char *v29; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v30; // [rsp+90h] [rbp-78h]
  __int64 v31; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v32[2]; // [rsp+A0h] [rbp-68h] BYREF
  DWORD v33; // [rsp+B0h] [rbp-58h]
  __int16 v34; // [rsp+B4h] [rbp-54h]
  _OWORD v35[2]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v36[3]; // [rsp+D8h] [rbp-30h] BYREF
  __int16 v37; // [rsp+F0h] [rbp-18h]
  _OWORD v38[2]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v39[3]; // [rsp+118h] [rbp+10h] BYREF
  __int16 v40; // [rsp+130h] [rbp+28h]
  _OWORD v41[2]; // [rsp+138h] [rbp+30h] BYREF
  _QWORD v42[3]; // [rsp+158h] [rbp+50h] BYREF
  __int16 v43; // [rsp+170h] [rbp+68h]
  _OWORD v44[2]; // [rsp+178h] [rbp+70h] BYREF
  _QWORD v45[3]; // [rsp+198h] [rbp+90h] BYREF
  __int16 v46; // [rsp+1B0h] [rbp+A8h]
  _OWORD v47[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  _QWORD v48[3]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int16 v49; // [rsp+1F0h] [rbp+E8h]
  _OWORD v50[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _QWORD v51[3]; // [rsp+218h] [rbp+110h] BYREF
  __int16 v52; // [rsp+230h] [rbp+128h]
  _OWORD v53[2]; // [rsp+238h] [rbp+130h] BYREF
  _QWORD v54[3]; // [rsp+258h] [rbp+150h] BYREF
  __int16 v55; // [rsp+270h] [rbp+168h]
  _OWORD v56[2]; // [rsp+278h] [rbp+170h] BYREF

  v5 = a4;
  v29 = a4;
  v6 = a3;
  v7 = (unsigned int)a2;
  v27 = (__int64)a4;
  if ( a3 == 2 )
  {
    if ( !a5 )
    {
      CrashWithRecovery(0x23518757u, 0);
      __debugbreak();
    }
    if ( (unsigned int)a2 >= 0x11 )
    {
      CrashWithRecovery(0x23518756u, 0);
      __debugbreak();
    }
  }
  LOBYTE(a2) = 1;
  Cache::CacheManager::AcquireLock(&v31, a2);
  v9 = 0;
  TotalCachesSize = Cache::CacheManager::GetTotalCachesSize(this);
  v30 = TotalCachesSize;
  v28 = v6;
  if ( v6 == 3 )
  {
    v6 = 4;
    v17 = ((TotalCachesSize - *((_QWORD *)this + 2)) & -(__int64)(*((_QWORD *)this + 2) < TotalCachesSize)) == 0;
    v27 = (TotalCachesSize - *((_QWORD *)this + 2)) & -(__int64)(*((_QWORD *)this + 2) < TotalCachesSize);
    v14 = v17;
    goto LABEL_15;
  }
  if ( v6 == 2 )
  {
    v13 = *((_QWORD *)this + v7 + 81);
    if ( v13 )
      v9 = Cache::CacheManager::EvictFromCache(v13, 2, &v27, a5);
    v14 = 1;
LABEL_15:
    if ( v14 )
      goto LABEL_16;
  }
  v11 = 0;
  v12 = (_QWORD *)((char *)this + 648);
  do
  {
    if ( v6 == 4 && !v27 )
      break;
    if ( *v12 )
      v9 += Cache::CacheManager::EvictFromCache(*v12, v6, &v27, a5);
    ++v11;
    ++v12;
  }
  while ( v11 < 0x11 );
  TotalCachesSize = v30;
  v5 = v29;
LABEL_16:
  if ( byte_180522F70 < 0 )
    v15 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180522F70);
  else
    v15 = byte_180522F70 != 0;
  if ( v15 )
  {
    v54[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v54[1] = "totalEvictedBytes";
    v54[2] = v9;
    v55 = 4;
    v56[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v56[1] = si128;
    LOWORD(v56[0]) = 0;
    v19 = Cache::CacheManager::GetTotalCachesSize(this);
    v51[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v51[1] = "newCacheSize";
    v51[2] = v19;
    v52 = 4;
    v53[0] = 0;
    v53[1] = si128;
    LOWORD(v53[0]) = 0;
    v48[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v48[1] = "oldCacheSize";
    v48[2] = TotalCachesSize;
    v49 = 4;
    v50[0] = 0;
    v50[1] = si128;
    LOWORD(v50[0]) = 0;
    v45[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v45[1] = "memoryLimit";
    v45[2] = *((_QWORD *)this + 2);
    v46 = 4;
    v47[0] = 0;
    v47[1] = si128;
    LOWORD(v47[0]) = 0;
    v42[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v42[1] = "explicitGoal";
    v42[2] = v5;
    v43 = 4;
    v44[0] = 0;
    v44[1] = si128;
    LOWORD(v44[0]) = 0;
    v39[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v39[1] = "evictionType";
    v39[2] = sub_1800047F0(v28);
    v40 = v20;
    v41[0] = 0;
    v41[1] = si128;
    LOWORD(v41[0]) = 0;
    v36[0] = v21;
    v36[1] = "cacheType";
    v36[2] = sub_18000D6BC((unsigned int)v7);
    v37 = v22;
    v38[0] = 0;
    v38[1] = si128;
    LOWORD(v38[0]) = 0;
    CurrentThreadId = GetCurrentThreadId();
    v32[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v32[1] = "threadID";
    v33 = CurrentThreadId;
    v34 = 4;
    v35[0] = 0;
    v35[1] = si128;
    LOWORD(v35[0]) = 0;
    v29 = "CacheManager::Evict";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      (unsigned int)"threadID",
      v24,
      v25,
      v26,
      (__int64)&v29,
      (__int64)v32,
      (__int64)v36,
      (__int64)v39,
      (__int64)v42,
      (__int64)v45,
      (__int64)v48,
      (__int64)v51,
      (__int64)v54);
    std::wstring::~wstring(v35);
    std::wstring::~wstring(v38);
    std::wstring::~wstring(v41);
    std::wstring::~wstring(v44);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v50);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v56);
  }
  Cache::CacheManager::CheckAllCachesForResurrectionTelemetry(this);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
  return v9;
}

```

## disassembly

```asm
0x180004378  mov     rax, rsp
0x18000437b  push    rbp
0x18000437c  push    rbx
0x18000437d  push    rsi
0x18000437e  push    rdi
0x18000437f  push    r12
0x180004381  push    r13
0x180004383  push    r14
0x180004385  push    r15
0x180004387  lea     rbp, [rax-1F8h]
0x18000438e  sub     rsp, 2B8h
0x180004395  movaps  xmmword ptr [rax-58h], xmm6
0x180004399  mov     rax, cs:__security_cookie
0x1800043a0  xor     rax, rsp
0x1800043a3  mov     [rbp+1F0h+var_60], rax
0x1800043aa  mov     r15, r9
0x1800043ad  mov     [rbp+1F0h+var_270], r9
0x1800043b1  mov     ebx, r8d
0x1800043b4  mov     r13d, edx
0x1800043b7  mov     rdi, rcx
0x1800043ba  mov     [rsp+2F0h+var_280], r9
0x1800043bf  mov     r12, [rbp+1F0h+arg_20]
0x1800043c6  cmp     r8d, 2
0x1800043ca  jz      loc_1800044DD
0x1800043d0  mov     dl, 1
0x1800043d2  lea     rcx, [rbp+1F0h+var_260]
0x1800043d6  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x1800043db  xor     esi, esi
0x1800043dd  mov     rcx, rdi; this
0x1800043e0  call    ?GetTotalCachesSize@CacheManager@Cache@@UEBA_KXZ; Cache::CacheManager::GetTotalCachesSize(void)
0x1800043e5  mov     r14, rax
0x1800043e8  mov     [rbp+1F0h+var_268], rax
0x1800043ec  mov     [rsp+2F0h+var_278], ebx
0x1800043f0  lea     eax, [rsi+4]
0x1800043f3  cmp     ebx, 3
0x1800043f6  jz      loc_180004522
0x1800043fc  cmp     ebx, 2
0x1800043ff  jz      short loc_18000444F
0x180004401  xor     r15d, r15d
0x180004404  lea     r14, [rdi+288h]
0x18000440b  cmp     ebx, eax
0x18000440d  jz      short loc_180004445
0x18000440f  mov     rcx, [r14]
0x180004412  test    rcx, rcx
0x180004415  jz      short loc_18000442E
0x180004417  mov     r9, r12
0x18000441a  lea     r8, [rsp+2F0h+var_280]
0x18000441f  mov     edx, ebx
0x180004421  call    ?EvictFromCache@CacheManager@Cache@@CA_KAEAV22@W4EvictionType@2@AEA_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z; Cache::CacheManager::EvictFromCache(Cache::Cache &,Cache::EvictionType,unsigned __int64 &,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)
0x180004426  add     rsi, rax
0x180004429  mov     eax, 4
0x18000442e  inc     r15d
0x180004431  add     r14, 8
0x180004435  cmp     r15d, 11h
0x180004439  jb      short loc_18000440B
0x18000443b  mov     r14, [rbp+1F0h+var_268]
0x18000443f  mov     r15, [rbp+1F0h+var_270]
0x180004443  jmp     short loc_18000446A
0x180004445  cmp     [rsp+2F0h+var_280], 0
0x18000444b  ja      short loc_18000440F
0x18000444d  jmp     short loc_18000443B
0x18000444f  mov     rcx, [rdi+r13*8+288h]
0x180004457  test    rcx, rcx
0x18000445a  jnz     loc_1800044FA
0x180004460  mov     al, 1
0x180004462  test    al, al
0x180004464  jz      loc_180004542
0x18000446a  mov     al, cs:byte_180522F70
0x180004470  xor     r12d, r12d
0x180004473  test    al, al
0x180004475  js      short loc_1800044CE
0x180004477  setnz   al
0x18000447a  test    al, al
0x18000447c  jnz     loc_18000454C
0x180004482  mov     rcx, rdi; this
0x180004485  call    ?CheckAllCachesForResurrectionTelemetry@CacheManager@Cache@@AEAAXXZ; Cache::CacheManager::CheckAllCachesForResurrectionTelemetry(void)
0x18000448a  mov     rcx, [rbp+1F0h+var_260]
0x18000448e  test    rcx, rcx
0x180004491  jz      short loc_1800044A0
0x180004493  mov     rax, [rcx]
0x180004496  mov     rax, [rax+8]
0x18000449a  call    cs:__guard_dispatch_icall_fptr
0x1800044a0  mov     rax, rsi
0x1800044a3  mov     rcx, [rbp+1F0h+var_60]
0x1800044aa  xor     rcx, rsp; StackCookie
0x1800044ad  call    __security_check_cookie
0x1800044b2  movaps  xmm6, [rsp+2F0h+var_58+8]
0x1800044ba  add     rsp, 2B8h
0x1800044c1  pop     r15
0x1800044c3  pop     r14
0x1800044c5  pop     r13
0x1800044c7  pop     r12
0x1800044c9  pop     rdi
0x1800044ca  pop     rsi
0x1800044cb  pop     rbx
0x1800044cc  pop     rbp
0x1800044cd  retn
0x1800044ce  lea     rcx, byte_180522F70
0x1800044d5  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1800044db  jmp     short loc_18000447A
0x1800044dd  test    r12, r12
0x1800044e0  jz      short loc_180004514
0x1800044e2  cmp     r13d, 11h
0x1800044e6  jb      loc_1800043D0
0x1800044ec  xor     edx, edx
0x1800044ee  mov     ecx, 23518756h
0x1800044f3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800044f9  int     3; Trap to Debugger
0x1800044fa  mov     r9, r12
0x1800044fd  lea     r8, [rsp+2F0h+var_280]
0x180004502  mov     edx, 2
0x180004507  call    ?EvictFromCache@CacheManager@Cache@@CA_KAEAV22@W4EvictionType@2@AEA_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z; Cache::CacheManager::EvictFromCache(Cache::Cache &,Cache::EvictionType,unsigned __int64 &,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)
0x18000450c  mov     rsi, rax
0x18000450f  jmp     loc_180004460
0x180004514  xor     edx, edx
0x180004516  mov     ecx, 23518757h
0x18000451b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180004521  int     3; Trap to Debugger
0x180004522  mov     ebx, eax
0x180004524  mov     rcx, r14
0x180004527  sub     rcx, [rdi+10h]
0x18000452b  cmp     [rdi+10h], r14
0x18000452f  sbb     rax, rax
0x180004532  and     rax, rcx
0x180004535  mov     [rsp+2F0h+var_280], rax
0x18000453a  setz    al
0x18000453d  jmp     loc_180004462
0x180004542  mov     eax, 4
0x180004547  jmp     loc_180004401
0x18000454c  lea     rbx, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x180004553  mov     [rbp+1F0h+var_A0], rbx
0x18000455a  lea     rax, aTotalevictedby; "totalEvictedBytes"
0x180004561  mov     [rbp+1F0h+var_98], rax
0x180004568  mov     [rbp+1F0h+var_90], rsi
0x18000456f  mov     eax, 4
0x180004574  mov     [rbp+1F0h+var_88], ax
0x18000457b  xorps   xmm0, xmm0
0x18000457e  movups  [rbp+1F0h+var_80], xmm0
0x180004585  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000458d  movdqa  [rbp+1F0h+var_70], xmm6
0x180004595  mov     word ptr [rbp+1F0h+var_80], r12w
0x18000459d  mov     rcx, rdi; this
0x1800045a0  call    ?GetTotalCachesSize@CacheManager@Cache@@UEBA_KXZ; Cache::CacheManager::GetTotalCachesSize(void)
0x1800045a5  mov     [rbp+1F0h+var_E0], rbx
0x1800045ac  lea     rcx, aNewcachesize; "newCacheSize"
0x1800045b3  mov     [rbp+1F0h+var_D8], rcx
0x1800045ba  mov     [rbp+1F0h+var_D0], rax
0x1800045c1  mov     r9d, 4
0x1800045c7  mov     [rbp+1F0h+var_C8], r9w
0x1800045cf  xorps   xmm0, xmm0
0x1800045d2  movups  [rbp+1F0h+var_C0], xmm0
0x1800045d9  movdqa  [rbp+1F0h+var_B0], xmm6
0x1800045e1  mov     word ptr [rbp+1F0h+var_C0], r12w
0x1800045e9  mov     [rbp+1F0h+var_120], rbx
0x1800045f0  lea     rax, aOldcachesize; "oldCacheSize"
0x1800045f7  mov     [rbp+1F0h+var_118], rax
0x1800045fe  mov     [rbp+1F0h+var_110], r14
0x180004605  mov     [rbp+1F0h+var_108], r9w
0x18000460d  movups  [rbp+1F0h+var_100], xmm0
0x180004614  movdqa  [rbp+1F0h+var_F0], xmm6
0x18000461c  mov     word ptr [rbp+1F0h+var_100], r12w
0x180004624  mov     [rbp+1F0h+var_160], rbx
0x18000462b  lea     rax, aMemorylimit; "memoryLimit"
0x180004632  mov     [rbp+1F0h+var_158], rax
0x180004639  mov     rax, [rdi+10h]
0x18000463d  mov     [rbp+1F0h+var_150], rax
0x180004644  mov     [rbp+1F0h+var_148], r9w
0x18000464c  movups  [rbp+1F0h+var_140], xmm0
0x180004653  movdqa  [rbp+1F0h+var_130], xmm6
0x18000465b  mov     word ptr [rbp+1F0h+var_140], r12w
0x180004663  mov     [rbp+1F0h+var_1A0], rbx
0x180004667  lea     rax, aExplicitgoal; "explicitGoal"
0x18000466e  mov     [rbp+1F0h+var_198], rax
0x180004672  mov     [rbp+1F0h+var_190], r15
0x180004676  mov     [rbp+1F0h+var_188], r9w
0x18000467b  movups  [rbp+1F0h+var_180], xmm0
0x18000467f  movdqa  [rbp+1F0h+var_170], xmm6
0x180004687  mov     word ptr [rbp+1F0h+var_180], r12w
0x18000468c  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180004693  mov     [rbp+1F0h+var_1E0], r8
0x180004697  lea     rax, aEvictiontype; "evictionType"
0x18000469e  mov     [rbp+1F0h+var_1D8], rax
0x1800046a2  mov     ecx, [rsp+2F0h+var_278]
0x1800046a6  call    sub_1800047F0
0x1800046ab  mov     [rbp+1F0h+var_1D0], rax
0x1800046af  mov     [rbp+1F0h+var_1C8], r9w
0x1800046b4  movups  [rbp+1F0h+var_1C0], xmm0
0x1800046b8  movdqa  [rbp+1F0h+var_1B0], xmm6
0x1800046bd  mov     word ptr [rbp+1F0h+var_1C0], r12w
0x1800046c2  mov     [rbp+1F0h+var_220], r8
0x1800046c6  lea     rax, aCachetype; "cacheType"
0x1800046cd  mov     [rbp+1F0h+var_218], rax
0x1800046d1  mov     ecx, r13d
0x1800046d4  call    sub_18000D6BC
0x1800046d9  mov     [rbp+1F0h+var_210], rax
0x1800046dd  mov     [rbp+1F0h+var_208], r9w
0x1800046e2  movups  [rbp+1F0h+var_200], xmm0
0x1800046e6  movdqa  [rbp+1F0h+var_1F0], xmm6
0x1800046eb  mov     word ptr [rbp+1F0h+var_200], r12w
0x1800046f0  call    cs:__imp_GetCurrentThreadId
0x1800046f6  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1800046fd  mov     [rbp+1F0h+var_258], rcx
0x180004701  lea     rcx, aThreadid; "threadID"
0x180004708  mov     [rbp+1F0h+var_250], rcx
0x18000470c  mov     [rbp+1F0h+var_248], eax
0x18000470f  mov     eax, 4
0x180004714  mov     [rbp+1F0h+var_244], ax
0x180004718  xorps   xmm0, xmm0
0x18000471b  movups  [rbp+1F0h+var_240], xmm0
0x18000471f  movdqu  [rbp+1F0h+var_230], xmm6
0x180004724  mov     word ptr [rbp+1F0h+var_240], r12w
0x180004729  lea     rax, aCachemanagerEv; "CacheManager::Evict"
0x180004730  mov     [rbp+1F0h+var_270], rax
0x180004734  lea     rax, [rbp+1F0h+var_A0]
0x18000473b  mov     [rsp+60h], rax
0x180004740  lea     rax, [rbp+1F0h+var_E0]
0x180004747  mov     [rsp+2F0h+var_298], rax
0x18000474c  lea     rax, [rbp+1F0h+var_120]
0x180004753  mov     [rsp+2F0h+var_2A0], rax
0x180004758  lea     rax, [rbp+1F0h+var_160]
0x18000475f  mov     [rsp+2F0h+var_2A8], rax
0x180004764  lea     rax, [rbp+1F0h+var_1A0]
0x180004768  mov     [rsp+2F0h+var_2B0], rax
0x18000476d  lea     rax, [rbp+1F0h+var_1E0]
0x180004771  mov     [rsp+2F0h+var_2B8], rax
0x180004776  lea     rax, [rbp+1F0h+var_220]
0x18000477a  mov     [rsp+2F0h+var_2C0], rax
0x18000477f  lea     rax, [rbp+1F0h+var_258]
0x180004783  mov     [rsp+2F0h+var_2C8], rax
0x180004788  lea     rax, [rbp+1F0h+var_270]
0x18000478c  mov     [rsp+2F0h+var_2D0], rax
0x180004791  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEB_W@23@U423@U?$ClassifiedStructuredObject@_K@23@U523@U523@U523@U523@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@6666@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x180004796  lea     rcx, [rbp+1F0h+var_240]
0x18000479a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000479f  lea     rcx, [rbp+1F0h+var_200]
0x1800047a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047a8  lea     rcx, [rbp+1F0h+var_1C0]
0x1800047ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047b1  lea     rcx, [rbp+1F0h+var_180]
0x1800047b5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047ba  lea     rcx, [rbp+1F0h+var_140]
0x1800047c1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047c6  lea     rcx, [rbp+1F0h+var_100]
0x1800047cd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047d2  lea     rcx, [rbp+1F0h+var_C0]
0x1800047d9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047de  lea     rcx, [rbp+1F0h+var_80]
0x1800047e5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800047ea  jmp     loc_180004482
```

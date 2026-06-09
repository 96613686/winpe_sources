# Cache::CacheManager::EvictCore(Cache::CacheType,Cache::EvictionType,unsigned __int64,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)

- ea: `0x1800041c8`
- end: `0x180004640`
- name: `?EvictCore@CacheManager@Cache@@AEAA_KW4CacheType@2@W4EvictionType@2@_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z`
- size: `1144`
- prototype: `__int64 __usercall@<rax>(Cache::CacheManager *this@<rcx>, __int64)`
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x1800041b0`
- `0x18000a368`
- `0x1800fc900`
- `0x18016fa20`

## callees

- `0x180003bf4`
- `0x1800041c8`
- `0x180004640`
- `0x180007180`
- `0x18000d7fc`
- `0x18001f6c0`
- `0x180056ee0`
- `0x1800573f0`
- `0x18007aa30`
- `0x1800fce10`
- `0x1800fce4c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004540`
- `KERNEL32!GetCurrentThreadId` at `0x180004540`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004343`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18000436b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180004343`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18000436b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180004325`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180004325`

## string_xrefs

- `0x180004551`: `threadID`
- `0x180004516`: `cacheType`
- `0x180004440`: `oldCacheSize`
- `0x1800043fc`: `newCacheSize`
- `0x180004579`: `CacheManager::Evict`

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
  if ( byte_18051EEC8 < 0 )
    v15 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_18051EEC8);
  else
    v15 = byte_18051EEC8 != 0;
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
    v39[2] = sub_180004640(v28);
    v40 = v20;
    v41[0] = 0;
    v41[1] = si128;
    LOWORD(v41[0]) = 0;
    v36[0] = v21;
    v36[1] = "cacheType";
    v36[2] = sub_18000D7FC((unsigned int)v7);
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
0x1800041c8  mov     rax, rsp
0x1800041cb  push    rbp
0x1800041cc  push    rbx
0x1800041cd  push    rsi
0x1800041ce  push    rdi
0x1800041cf  push    r12
0x1800041d1  push    r13
0x1800041d3  push    r14
0x1800041d5  push    r15
0x1800041d7  lea     rbp, [rax-1F8h]
0x1800041de  sub     rsp, 2B8h
0x1800041e5  movaps  xmmword ptr [rax-58h], xmm6
0x1800041e9  mov     rax, cs:__security_cookie
0x1800041f0  xor     rax, rsp
0x1800041f3  mov     [rbp+1F0h+var_60], rax
0x1800041fa  mov     r15, r9
0x1800041fd  mov     [rbp+1F0h+var_270], r9
0x180004201  mov     ebx, r8d
0x180004204  mov     r13d, edx
0x180004207  mov     rdi, rcx
0x18000420a  mov     [rsp+2F0h+var_280], r9
0x18000420f  mov     r12, [rbp+1F0h+arg_20]
0x180004216  cmp     r8d, 2
0x18000421a  jz      loc_18000432D
0x180004220  mov     dl, 1
0x180004222  lea     rcx, [rbp+1F0h+var_260]
0x180004226  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x18000422b  xor     esi, esi
0x18000422d  mov     rcx, rdi; this
0x180004230  call    ?GetTotalCachesSize@CacheManager@Cache@@UEBA_KXZ; Cache::CacheManager::GetTotalCachesSize(void)
0x180004235  mov     r14, rax
0x180004238  mov     [rbp+1F0h+var_268], rax
0x18000423c  mov     [rsp+2F0h+var_278], ebx
0x180004240  lea     eax, [rsi+4]
0x180004243  cmp     ebx, 3
0x180004246  jz      loc_180004372
0x18000424c  cmp     ebx, 2
0x18000424f  jz      short loc_18000429F
0x180004251  xor     r15d, r15d
0x180004254  lea     r14, [rdi+288h]
0x18000425b  cmp     ebx, eax
0x18000425d  jz      short loc_180004295
0x18000425f  mov     rcx, [r14]
0x180004262  test    rcx, rcx
0x180004265  jz      short loc_18000427E
0x180004267  mov     r9, r12
0x18000426a  lea     r8, [rsp+2F0h+var_280]
0x18000426f  mov     edx, ebx
0x180004271  call    ?EvictFromCache@CacheManager@Cache@@CA_KAEAV22@W4EvictionType@2@AEA_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z; Cache::CacheManager::EvictFromCache(Cache::Cache &,Cache::EvictionType,unsigned __int64 &,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)
0x180004276  add     rsi, rax
0x180004279  mov     eax, 4
0x18000427e  inc     r15d
0x180004281  add     r14, 8
0x180004285  cmp     r15d, 11h
0x180004289  jb      short loc_18000425B
0x18000428b  mov     r14, [rbp+1F0h+var_268]
0x18000428f  mov     r15, [rbp+1F0h+var_270]
0x180004293  jmp     short loc_1800042BA
0x180004295  cmp     [rsp+2F0h+var_280], 0
0x18000429b  ja      short loc_18000425F
0x18000429d  jmp     short loc_18000428B
0x18000429f  mov     rcx, [rdi+r13*8+288h]
0x1800042a7  test    rcx, rcx
0x1800042aa  jnz     loc_18000434A
0x1800042b0  mov     al, 1
0x1800042b2  test    al, al
0x1800042b4  jz      loc_180004392
0x1800042ba  mov     al, cs:byte_18051EEC8
0x1800042c0  xor     r12d, r12d
0x1800042c3  test    al, al
0x1800042c5  js      short loc_18000431E
0x1800042c7  setnz   al
0x1800042ca  test    al, al
0x1800042cc  jnz     loc_18000439C
0x1800042d2  mov     rcx, rdi; this
0x1800042d5  call    ?CheckAllCachesForResurrectionTelemetry@CacheManager@Cache@@AEAAXXZ; Cache::CacheManager::CheckAllCachesForResurrectionTelemetry(void)
0x1800042da  mov     rcx, [rbp+1F0h+var_260]
0x1800042de  test    rcx, rcx
0x1800042e1  jz      short loc_1800042F0
0x1800042e3  mov     rax, [rcx]
0x1800042e6  mov     rax, [rax+8]
0x1800042ea  call    cs:__guard_dispatch_icall_fptr
0x1800042f0  mov     rax, rsi
0x1800042f3  mov     rcx, [rbp+1F0h+var_60]
0x1800042fa  xor     rcx, rsp; StackCookie
0x1800042fd  call    __security_check_cookie
0x180004302  movaps  xmm6, [rsp+2F0h+var_58+8]
0x18000430a  add     rsp, 2B8h
0x180004311  pop     r15
0x180004313  pop     r14
0x180004315  pop     r13
0x180004317  pop     r12
0x180004319  pop     rdi
0x18000431a  pop     rsi
0x18000431b  pop     rbx
0x18000431c  pop     rbp
0x18000431d  retn
0x18000431e  lea     rcx, byte_18051EEC8
0x180004325  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x18000432b  jmp     short loc_1800042CA
0x18000432d  test    r12, r12
0x180004330  jz      short loc_180004364
0x180004332  cmp     r13d, 11h
0x180004336  jb      loc_180004220
0x18000433c  xor     edx, edx
0x18000433e  mov     ecx, 23518756h
0x180004343  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180004349  int     3; Trap to Debugger
0x18000434a  mov     r9, r12
0x18000434d  lea     r8, [rsp+2F0h+var_280]
0x180004352  mov     edx, 2
0x180004357  call    ?EvictFromCache@CacheManager@Cache@@CA_KAEAV22@W4EvictionType@2@AEA_KPEBV?$FunctorRef@$$A6A_NAEBUIResourceKey@Cache@@AEBUIResourceState@2@@Z@Mso@@@Z; Cache::CacheManager::EvictFromCache(Cache::Cache &,Cache::EvictionType,unsigned __int64 &,Mso::FunctorRef<bool (Cache::IResourceKey const &,Cache::IResourceState const &)> const *)
0x18000435c  mov     rsi, rax
0x18000435f  jmp     loc_1800042B0
0x180004364  xor     edx, edx
0x180004366  mov     ecx, 23518757h
0x18000436b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180004371  int     3; Trap to Debugger
0x180004372  mov     ebx, eax
0x180004374  mov     rcx, r14
0x180004377  sub     rcx, [rdi+10h]
0x18000437b  cmp     [rdi+10h], r14
0x18000437f  sbb     rax, rax
0x180004382  and     rax, rcx
0x180004385  mov     [rsp+2F0h+var_280], rax
0x18000438a  setz    al
0x18000438d  jmp     loc_1800042B2
0x180004392  mov     eax, 4
0x180004397  jmp     loc_180004251
0x18000439c  lea     rbx, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x1800043a3  mov     [rbp+1F0h+var_A0], rbx
0x1800043aa  lea     rax, aTotalevictedby; "totalEvictedBytes"
0x1800043b1  mov     [rbp+1F0h+var_98], rax
0x1800043b8  mov     [rbp+1F0h+var_90], rsi
0x1800043bf  mov     eax, 4
0x1800043c4  mov     [rbp+1F0h+var_88], ax
0x1800043cb  xorps   xmm0, xmm0
0x1800043ce  movups  [rbp+1F0h+var_80], xmm0
0x1800043d5  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800043dd  movdqa  [rbp+1F0h+var_70], xmm6
0x1800043e5  mov     word ptr [rbp+1F0h+var_80], r12w
0x1800043ed  mov     rcx, rdi; this
0x1800043f0  call    ?GetTotalCachesSize@CacheManager@Cache@@UEBA_KXZ; Cache::CacheManager::GetTotalCachesSize(void)
0x1800043f5  mov     [rbp+1F0h+var_E0], rbx
0x1800043fc  lea     rcx, aNewcachesize; "newCacheSize"
0x180004403  mov     [rbp+1F0h+var_D8], rcx
0x18000440a  mov     [rbp+1F0h+var_D0], rax
0x180004411  mov     r9d, 4
0x180004417  mov     [rbp+1F0h+var_C8], r9w
0x18000441f  xorps   xmm0, xmm0
0x180004422  movups  [rbp+1F0h+var_C0], xmm0
0x180004429  movdqa  [rbp+1F0h+var_B0], xmm6
0x180004431  mov     word ptr [rbp+1F0h+var_C0], r12w
0x180004439  mov     [rbp+1F0h+var_120], rbx
0x180004440  lea     rax, aOldcachesize; "oldCacheSize"
0x180004447  mov     [rbp+1F0h+var_118], rax
0x18000444e  mov     [rbp+1F0h+var_110], r14
0x180004455  mov     [rbp+1F0h+var_108], r9w
0x18000445d  movups  [rbp+1F0h+var_100], xmm0
0x180004464  movdqa  [rbp+1F0h+var_F0], xmm6
0x18000446c  mov     word ptr [rbp+1F0h+var_100], r12w
0x180004474  mov     [rbp+1F0h+var_160], rbx
0x18000447b  lea     rax, aMemorylimit; "memoryLimit"
0x180004482  mov     [rbp+1F0h+var_158], rax
0x180004489  mov     rax, [rdi+10h]
0x18000448d  mov     [rbp+1F0h+var_150], rax
0x180004494  mov     [rbp+1F0h+var_148], r9w
0x18000449c  movups  [rbp+1F0h+var_140], xmm0
0x1800044a3  movdqa  [rbp+1F0h+var_130], xmm6
0x1800044ab  mov     word ptr [rbp+1F0h+var_140], r12w
0x1800044b3  mov     [rbp+1F0h+var_1A0], rbx
0x1800044b7  lea     rax, aExplicitgoal; "explicitGoal"
0x1800044be  mov     [rbp+1F0h+var_198], rax
0x1800044c2  mov     [rbp+1F0h+var_190], r15
0x1800044c6  mov     [rbp+1F0h+var_188], r9w
0x1800044cb  movups  [rbp+1F0h+var_180], xmm0
0x1800044cf  movdqa  [rbp+1F0h+var_170], xmm6
0x1800044d7  mov     word ptr [rbp+1F0h+var_180], r12w
0x1800044dc  lea     r8, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800044e3  mov     [rbp+1F0h+var_1E0], r8
0x1800044e7  lea     rax, aEvictiontype; "evictionType"
0x1800044ee  mov     [rbp+1F0h+var_1D8], rax
0x1800044f2  mov     ecx, [rsp+2F0h+var_278]
0x1800044f6  call    sub_180004640
0x1800044fb  mov     [rbp+1F0h+var_1D0], rax
0x1800044ff  mov     [rbp+1F0h+var_1C8], r9w
0x180004504  movups  [rbp+1F0h+var_1C0], xmm0
0x180004508  movdqa  [rbp+1F0h+var_1B0], xmm6
0x18000450d  mov     word ptr [rbp+1F0h+var_1C0], r12w
0x180004512  mov     [rbp+1F0h+var_220], r8
0x180004516  lea     rax, aCachetype; "cacheType"
0x18000451d  mov     [rbp+1F0h+var_218], rax
0x180004521  mov     ecx, r13d
0x180004524  call    sub_18000D7FC
0x180004529  mov     [rbp+1F0h+var_210], rax
0x18000452d  mov     [rbp+1F0h+var_208], r9w
0x180004532  movups  [rbp+1F0h+var_200], xmm0
0x180004536  movdqa  [rbp+1F0h+var_1F0], xmm6
0x18000453b  mov     word ptr [rbp+1F0h+var_200], r12w
0x180004540  call    cs:__imp_GetCurrentThreadId
0x180004546  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x18000454d  mov     [rbp+1F0h+var_258], rcx
0x180004551  lea     rcx, aThreadid; "threadID"
0x180004558  mov     [rbp+1F0h+var_250], rcx
0x18000455c  mov     [rbp+1F0h+var_248], eax
0x18000455f  mov     eax, 4
0x180004564  mov     [rbp+1F0h+var_244], ax
0x180004568  xorps   xmm0, xmm0
0x18000456b  movups  [rbp+1F0h+var_240], xmm0
0x18000456f  movdqu  [rbp+1F0h+var_230], xmm6
0x180004574  mov     word ptr [rbp+1F0h+var_240], r12w
0x180004579  lea     rax, aCachemanagerEv; "CacheManager::Evict"
0x180004580  mov     [rbp+1F0h+var_270], rax
0x180004584  lea     rax, [rbp+1F0h+var_A0]
0x18000458b  mov     [rsp+60h], rax
0x180004590  lea     rax, [rbp+1F0h+var_E0]
0x180004597  mov     [rsp+2F0h+var_298], rax
0x18000459c  lea     rax, [rbp+1F0h+var_120]
0x1800045a3  mov     [rsp+2F0h+var_2A0], rax
0x1800045a8  lea     rax, [rbp+1F0h+var_160]
0x1800045af  mov     [rsp+2F0h+var_2A8], rax
0x1800045b4  lea     rax, [rbp+1F0h+var_1A0]
0x1800045b8  mov     [rsp+2F0h+var_2B0], rax
0x1800045bd  lea     rax, [rbp+1F0h+var_1E0]
0x1800045c1  mov     [rsp+2F0h+var_2B8], rax
0x1800045c6  lea     rax, [rbp+1F0h+var_220]
0x1800045ca  mov     [rsp+2F0h+var_2C0], rax
0x1800045cf  lea     rax, [rbp+1F0h+var_258]
0x1800045d3  mov     [rsp+2F0h+var_2C8], rax
0x1800045d8  lea     rax, [rbp+1F0h+var_270]
0x1800045dc  mov     [rsp+2F0h+var_2D0], rax
0x1800045e1  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEB_W@23@U423@U?$ClassifiedStructuredObject@_K@23@U523@U523@U523@U523@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@5$$QEAU?$ClassifiedStructuredObject@_K@01@6666@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x1800045e6  lea     rcx, [rbp+1F0h+var_240]
0x1800045ea  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800045ef  lea     rcx, [rbp+1F0h+var_200]
0x1800045f3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800045f8  lea     rcx, [rbp+1F0h+var_1C0]
0x1800045fc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004601  lea     rcx, [rbp+1F0h+var_180]
0x180004605  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000460a  lea     rcx, [rbp+1F0h+var_140]
0x180004611  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004616  lea     rcx, [rbp+1F0h+var_100]
0x18000461d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180004622  lea     rcx, [rbp+1F0h+var_C0]
0x180004629  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000462e  lea     rcx, [rbp+1F0h+var_80]
0x180004635  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000463a  jmp     loc_1800042D2
```

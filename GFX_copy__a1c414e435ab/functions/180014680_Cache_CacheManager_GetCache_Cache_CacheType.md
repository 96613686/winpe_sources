# Cache::CacheManager::GetCache(Cache::CacheType)

- ea: `0x180014680`
- end: `0x1800148f6`
- name: `?GetCache@CacheManager@Cache@@AEAAAEAV22@W4CacheType@2@@Z`
- size: `630`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800221b4`
- `0x18006715c`

## callees

- `0x1800051a4`
- `0x180005340`
- `0x1800053e4`
- `0x18000d7fc`
- `0x180014680`
- `0x18001f6c0`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800786fc`
- `0x18007aa30`
- `0x1800fc9a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800147f6`
- `KERNEL32!GetCurrentThreadId` at `0x1800147f6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800148d4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800148d4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148ef`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148c1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148e1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800148ef`

## string_xrefs

- `0x180014808`: `threadID`
- `0x1800147d5`: `cacheType`
- `0x180014792`: `numCaches`
- `0x180014839`: `CacheManager::GetCache - created cache on-demand`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Cache::CacheManager::GetCache(Cache::CacheManager *a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // r14
  unsigned __int64 v5; // rdx
  unsigned int v6; // r8d
  _BYTE *v7; // r15
  __int64 v8; // rdi
  Cache::Cache *v10; // rax
  Cache *v11; // rax
  unsigned __int64 NumCaches; // rax
  __m128i si128; // xmm1
  __int64 v14; // rax
  DWORD CurrentThreadId; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  const char *v22; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v24; // [rsp+60h] [rbp-A0h]
  __int16 v25; // [rsp+64h] [rbp-9Ch]
  _OWORD v26[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v27[3]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v28; // [rsp+A8h] [rbp-58h]
  _OWORD v29[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v30[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v31; // [rsp+E8h] [rbp-18h]
  _OWORD v32[2]; // [rsp+F0h] [rbp-10h] BYREF

  v2 = (unsigned int)a2;
  if ( (unsigned int)a2 >= 0x11 )
  {
    CrashWithRecovery(0x23518781u, 0);
    __debugbreak();
  }
  if ( !BYTE1(xmmword_18051FD50) )
  {
    v20 = 592545669;
    goto LABEL_18;
  }
  if ( *((_BYTE *)a1 + 852) )
  {
    v20 = 592545668;
LABEL_18:
    MsoShipAssertTagProc(v20);
    CrashWithRecovery(0x23518780u, 0);
    __debugbreak();
  }
  v4 = 32LL * (unsigned int)a2;
  if ( !*(_DWORD *)((char *)a1 + v4 + 104) )
  {
    CrashWithRecovery(0x23518763u, 0);
    JUMPOUT(0x1800148F5LL);
  }
  LOBYTE(a2) = 1;
  Cache::CacheManager::AcquireLock(&v21, a2);
  v7 = (char *)a1 + 8 * v2;
  v8 = *((_QWORD *)v7 + 81);
  if ( v8 )
  {
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    return v8;
  }
  else
  {
    v10 = (Cache::Cache *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x98, v5, v6);
    v22 = (const char *)v10;
    if ( v10 )
      v11 = Cache::Cache::Cache(v10, (Cache::CacheManager *)((char *)a1 + v4 + 104));
    else
      v11 = 0;
    std::unique_ptr<Cache::Cache>::reset(v7 + 648, v11);
    NumCaches = Cache::CacheManager::GetNumCaches(a1);
    v30[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
    v30[1] = "numCaches";
    v30[2] = NumCaches;
    v31 = 4;
    v32[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v32[1] = si128;
    LOWORD(v32[0]) = 0;
    v14 = sub_18000D7FC((unsigned int)v2);
    v27[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v27[1] = "cacheType";
    v27[2] = v14;
    v28 = 4;
    v29[0] = 0;
    v29[1] = si128;
    LOWORD(v29[0]) = 0;
    CurrentThreadId = GetCurrentThreadId();
    v23[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v23[1] = "threadID";
    v24 = CurrentThreadId;
    v25 = 4;
    v26[0] = 0;
    v26[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v26[0]) = 0;
    v22 = "CacheManager::GetCache - created cache on-demand";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      (unsigned int)"threadID",
      v16,
      v17,
      v18,
      (__int64)&v22,
      (__int64)v23,
      (__int64)v27,
      (__int64)v30);
    std::wstring::~wstring(v26);
    std::wstring::~wstring(v29);
    std::wstring::~wstring(v32);
    v19 = *((_QWORD *)v7 + 81);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    return v19;
  }
}

```

## disassembly

```asm
0x180014680  mov     [rsp-8+arg_10], rbx
0x180014685  mov     [rsp-8+arg_18], rsi
0x18001468a  push    rbp
0x18001468b  push    rdi
0x18001468c  push    r12
0x18001468e  push    r14
0x180014690  push    r15
0x180014692  lea     rbp, [rsp-20h]
0x180014697  sub     rsp, 120h
0x18001469e  mov     rax, cs:__security_cookie
0x1800146a5  xor     rax, rsp
0x1800146a8  mov     [rbp+40h+var_30], rax
0x1800146ac  mov     esi, edx
0x1800146ae  mov     rbx, rcx
0x1800146b1  xor     r12d, r12d
0x1800146b4  cmp     edx, 11h
0x1800146b7  jnb     loc_1800148BA
0x1800146bd  cmp     byte ptr cs:xmmword_18051FD50+1, r12b
0x1800146c4  jz      loc_1800148C8
0x1800146ca  cmp     [rcx+354h], r12b
0x1800146d1  jnz     loc_1800148CF
0x1800146d7  mov     r14d, esi
0x1800146da  shl     r14, 5
0x1800146de  cmp     [r14+rcx+68h], r12d
0x1800146e3  jz      loc_1800148E8
0x1800146e9  mov     dl, 1
0x1800146eb  lea     rcx, [rsp+140h+var_100]
0x1800146f0  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x1800146f5  lea     r15, [rbx+rsi*8]
0x1800146f9  mov     rdi, [r15+288h]
0x180014700  test    rdi, rdi
0x180014703  jz      short loc_180014747
0x180014705  mov     rcx, [rsp+140h+var_100]
0x18001470a  test    rcx, rcx
0x18001470d  jz      short loc_18001471C
0x18001470f  mov     rdx, [rcx]
0x180014712  mov     rax, [rdx+8]
0x180014716  call    cs:__guard_dispatch_icall_fptr
0x18001471c  mov     rax, rdi
0x18001471f  mov     rcx, [rbp+40h+var_30]
0x180014723  xor     rcx, rsp; StackCookie
0x180014726  call    __security_check_cookie
0x18001472b  lea     r11, [rsp+140h+var_20]
0x180014733  mov     rbx, [r11+40h]
0x180014737  mov     rsi, [r11+48h]
0x18001473b  mov     rsp, r11
0x18001473e  pop     r15
0x180014740  pop     r14
0x180014742  pop     r12
0x180014744  pop     rdi
0x180014745  pop     rbp
0x180014746  retn
0x180014747  mov     ecx, 98h; this
0x18001474c  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180014751  mov     [rsp+140h+var_F8], rax
0x180014756  test    rax, rax
0x180014759  jz      loc_1800148B2
0x18001475f  lea     rdx, [rbx+68h]
0x180014763  add     rdx, r14; struct Cache::CacheDescriptor *
0x180014766  mov     rcx, rax; this
0x180014769  call    ??0Cache@0@QEAA@AEBUCacheDescriptor@0@@Z; Cache::Cache::Cache(Cache::CacheDescriptor const &)
0x18001476e  nop
0x18001476f  nop
0x180014770  mov     rdx, rax
0x180014773  lea     rcx, [r15+288h]
0x18001477a  call    ?reset@?$unique_ptr@VCache@1@U?$default_delete@VCache@1@@std@@@std@@QEAAXPEAVCache@3@@Z; std::unique_ptr<Cache::Cache>::reset(Cache::Cache *)
0x18001477f  mov     rcx, rbx; this
0x180014782  call    ?GetNumCaches@CacheManager@Cache@@AEBA_KXZ; Cache::CacheManager::GetNumCaches(void)
0x180014787  lea     rcx, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18001478e  mov     [rbp+40h+var_70], rcx
0x180014792  lea     rcx, aNumcaches; "numCaches"
0x180014799  mov     [rbp+40h+var_68], rcx
0x18001479d  mov     [rbp+40h+var_60], rax
0x1800147a1  mov     ebx, 4
0x1800147a6  mov     [rbp+40h+var_58], bx
0x1800147aa  xorps   xmm0, xmm0
0x1800147ad  movups  [rbp+40h+var_50], xmm0
0x1800147b1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800147b9  movdqa  [rbp+40h+var_40], xmm1
0x1800147be  mov     word ptr [rbp+40h+var_50], r12w
0x1800147c3  mov     ecx, esi
0x1800147c5  call    sub_18000D7FC
0x1800147ca  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1800147d1  mov     [rbp+40h+var_B0], rcx
0x1800147d5  lea     rcx, aCachetype; "cacheType"
0x1800147dc  mov     [rbp+40h+var_A8], rcx
0x1800147e0  mov     [rbp+40h+var_A0], rax
0x1800147e4  mov     [rbp+40h+var_98], bx
0x1800147e8  movups  [rbp+40h+var_90], xmm0
0x1800147ec  movdqa  [rbp+40h+var_80], xmm1
0x1800147f1  mov     word ptr [rbp+40h+var_90], r12w
0x1800147f6  call    cs:__imp_GetCurrentThreadId
0x1800147fc  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180014803  mov     [rsp+140h+var_F0], rcx
0x180014808  lea     rcx, aThreadid; "threadID"
0x18001480f  mov     [rsp+140h+var_E8], rcx
0x180014814  mov     [rsp+140h+var_E0], eax
0x180014818  mov     [rsp+140h+var_DC], bx
0x18001481d  xorps   xmm0, xmm0
0x180014820  movups  [rsp+140h+var_D8], xmm0
0x180014825  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001482d  movdqu  [rsp+140h+var_C8], xmm1
0x180014833  mov     word ptr [rsp+140h+var_D8], r12w
0x180014839  lea     rax, aCachemanagerGe; "CacheManager::GetCache - created cache "...
0x180014840  mov     [rsp+140h+var_F8], rax
0x180014845  lea     rax, [rbp+40h+var_70]
0x180014849  mov     [rsp+140h+var_108], rax
0x18001484e  lea     rax, [rbp+40h+var_B0]
0x180014852  mov     [rsp+140h+var_110], rax
0x180014857  lea     rax, [rsp+140h+var_F0]
0x18001485c  mov     [rsp+140h+var_118], rax
0x180014861  lea     rax, [rsp+140h+var_F8]
0x180014866  mov     [rsp+140h+var_120], rax
0x18001486b  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEB_W@23@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x180014870  lea     rcx, [rsp+140h+var_D8]
0x180014875  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001487a  lea     rcx, [rbp+40h+var_90]
0x18001487e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014883  lea     rcx, [rbp+40h+var_50]
0x180014887  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001488c  mov     rbx, [r15+288h]
0x180014893  mov     rcx, [rsp+140h+var_100]
0x180014898  test    rcx, rcx
0x18001489b  jz      short loc_1800148AA
0x18001489d  mov     rdx, [rcx]
0x1800148a0  mov     rax, [rdx+8]
0x1800148a4  call    cs:__guard_dispatch_icall_fptr
0x1800148aa  mov     rax, rbx
0x1800148ad  jmp     loc_18001471F
0x1800148b2  mov     rax, r12
0x1800148b5  jmp     loc_180014770
0x1800148ba  xor     edx, edx
0x1800148bc  mov     ecx, 23518781h
0x1800148c1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800148c7  int     3; Trap to Debugger
0x1800148c8  mov     ecx, 23518785h
0x1800148cd  jmp     short loc_1800148D4
0x1800148cf  mov     ecx, 23518784h
0x1800148d4  call    cs:__imp_MsoShipAssertTagProc
0x1800148da  xor     edx, edx
0x1800148dc  mov     ecx, 23518780h
0x1800148e1  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800148e7  int     3; Trap to Debugger
0x1800148e8  xor     edx, edx
0x1800148ea  mov     ecx, 23518763h
0x1800148ef  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```

# Cache::CacheManager::GetCache(Cache::CacheType)

- ea: `0x180014c30`
- end: `0x180014ea5`
- name: `?GetCache@CacheManager@Cache@@AEAAAEAV22@W4CacheType@2@@Z`
- size: `629`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180022814`
- `0x1800962d0`

## callees

- `0x180004fb8`
- `0x180005430`
- `0x1800054d4`
- `0x18000d6bc`
- `0x180014c30`
- `0x18001f854`
- `0x1800578b0`
- `0x180057e70`
- `0x180077780`
- `0x180092a58`
- `0x1800b1120`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180014da5`
- `KERNEL32!GetCurrentThreadId` at `0x180014da5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180014e83`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180014e83`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e70`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e90`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e9e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e70`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e90`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180014e9e`

## string_xrefs

- `0x180014db7`: `threadID`
- `0x180014d84`: `cacheType`
- `0x180014d41`: `numCaches`
- `0x180014de8`: `CacheManager::GetCache - created cache on-demand`

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
  if ( !BYTE1(xmmword_180523DD0) )
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
    JUMPOUT(0x180014EA4LL);
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
    v14 = sub_18000D6BC((unsigned int)v2);
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
0x180014c30  mov     [rsp-8+arg_10], rbx
0x180014c35  mov     [rsp-8+arg_18], rsi
0x180014c3a  push    rbp
0x180014c3b  push    rdi
0x180014c3c  push    r12
0x180014c3e  push    r14
0x180014c40  push    r15
0x180014c42  lea     rbp, [rsp-20h]
0x180014c47  sub     rsp, 120h
0x180014c4e  mov     rax, cs:__security_cookie
0x180014c55  xor     rax, rsp
0x180014c58  mov     [rbp+40h+var_30], rax
0x180014c5c  mov     esi, edx
0x180014c5e  mov     rbx, rcx
0x180014c61  xor     r12d, r12d
0x180014c64  cmp     edx, 11h
0x180014c67  jnb     loc_180014E69
0x180014c6d  cmp     byte ptr cs:xmmword_180523DD0+1, r12b
0x180014c74  jz      loc_180014E77
0x180014c7a  cmp     [rcx+354h], r12b
0x180014c81  jnz     loc_180014E7E
0x180014c87  mov     r14d, esi
0x180014c8a  shl     r14, 5
0x180014c8e  cmp     [r14+rcx+68h], r12d
0x180014c93  jz      loc_180014E97
0x180014c99  mov     dl, 1
0x180014c9b  lea     rcx, [rsp+140h+var_100]
0x180014ca0  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x180014ca5  lea     r15, [rbx+rsi*8]
0x180014ca9  mov     rdi, [r15+288h]
0x180014cb0  test    rdi, rdi
0x180014cb3  jz      short loc_180014CF7
0x180014cb5  mov     rcx, [rsp+140h+var_100]
0x180014cba  test    rcx, rcx
0x180014cbd  jz      short loc_180014CCC
0x180014cbf  mov     rdx, [rcx]
0x180014cc2  mov     rax, [rdx+8]
0x180014cc6  call    cs:__guard_dispatch_icall_fptr
0x180014ccc  mov     rax, rdi
0x180014ccf  mov     rcx, [rbp+40h+var_30]
0x180014cd3  xor     rcx, rsp; StackCookie
0x180014cd6  call    __security_check_cookie
0x180014cdb  lea     r11, [rsp+140h+var_20]
0x180014ce3  mov     rbx, [r11+40h]
0x180014ce7  mov     rsi, [r11+48h]
0x180014ceb  mov     rsp, r11
0x180014cee  pop     r15
0x180014cf0  pop     r14
0x180014cf2  pop     r12
0x180014cf4  pop     rdi
0x180014cf5  pop     rbp
0x180014cf6  retn
0x180014cf7  mov     ecx, 98h; this
0x180014cfc  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180014d01  mov     [rsp+140h+var_F8], rax
0x180014d06  test    rax, rax
0x180014d09  jz      loc_180014E61
0x180014d0f  lea     rdx, [rbx+68h]
0x180014d13  add     rdx, r14; struct Cache::CacheDescriptor *
0x180014d16  mov     rcx, rax; this
0x180014d19  call    ??0Cache@0@QEAA@AEBUCacheDescriptor@0@@Z; Cache::Cache::Cache(Cache::CacheDescriptor const &)
0x180014d1e  nop
0x180014d1f  mov     rdx, rax
0x180014d22  lea     rcx, [r15+288h]
0x180014d29  call    ?reset@?$unique_ptr@VCache@1@U?$default_delete@VCache@1@@std@@@std@@QEAAXPEAVCache@3@@Z; std::unique_ptr<Cache::Cache>::reset(Cache::Cache *)
0x180014d2e  mov     rcx, rbx; this
0x180014d31  call    ?GetNumCaches@CacheManager@Cache@@AEBA_KXZ; Cache::CacheManager::GetNumCaches(void)
0x180014d36  lea     rcx, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x180014d3d  mov     [rbp+40h+var_70], rcx
0x180014d41  lea     rcx, aNumcaches; "numCaches"
0x180014d48  mov     [rbp+40h+var_68], rcx
0x180014d4c  mov     [rbp+40h+var_60], rax
0x180014d50  mov     ebx, 4
0x180014d55  mov     [rbp+40h+var_58], bx
0x180014d59  xorps   xmm0, xmm0
0x180014d5c  movups  [rbp+40h+var_50], xmm0
0x180014d60  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180014d68  movdqa  [rbp+40h+var_40], xmm1
0x180014d6d  mov     word ptr [rbp+40h+var_50], r12w
0x180014d72  mov     ecx, esi
0x180014d74  call    sub_18000D6BC
0x180014d79  lea     rcx, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x180014d80  mov     [rbp+40h+var_B0], rcx
0x180014d84  lea     rcx, aCachetype; "cacheType"
0x180014d8b  mov     [rbp+40h+var_A8], rcx
0x180014d8f  mov     [rbp+40h+var_A0], rax
0x180014d93  mov     [rbp+40h+var_98], bx
0x180014d97  movups  [rbp+40h+var_90], xmm0
0x180014d9b  movdqa  [rbp+40h+var_80], xmm1
0x180014da0  mov     word ptr [rbp+40h+var_90], r12w
0x180014da5  call    cs:__imp_GetCurrentThreadId
0x180014dab  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180014db2  mov     [rsp+140h+var_F0], rcx
0x180014db7  lea     rcx, aThreadid; "threadID"
0x180014dbe  mov     [rsp+140h+var_E8], rcx
0x180014dc3  mov     [rsp+140h+var_E0], eax
0x180014dc7  mov     [rsp+140h+var_DC], bx
0x180014dcc  xorps   xmm0, xmm0
0x180014dcf  movups  [rsp+140h+var_D8], xmm0
0x180014dd4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180014ddc  movdqu  [rsp+140h+var_C8], xmm1
0x180014de2  mov     word ptr [rsp+140h+var_D8], r12w
0x180014de8  lea     rax, aCachemanagerGe; "CacheManager::GetCache - created cache "...
0x180014def  mov     [rsp+140h+var_F8], rax
0x180014df4  lea     rax, [rbp+40h+var_70]
0x180014df8  mov     [rsp+140h+var_108], rax
0x180014dfd  lea     rax, [rbp+40h+var_B0]
0x180014e01  mov     [rsp+140h+var_110], rax
0x180014e06  lea     rax, [rsp+140h+var_F0]
0x180014e0b  mov     [rsp+140h+var_118], rax
0x180014e10  lea     rax, [rsp+140h+var_F8]
0x180014e15  mov     [rsp+140h+var_120], rax
0x180014e1a  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@PEB_W@23@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x180014e1f  lea     rcx, [rsp+140h+var_D8]
0x180014e24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014e29  lea     rcx, [rbp+40h+var_90]
0x180014e2d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014e32  lea     rcx, [rbp+40h+var_50]
0x180014e36  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014e3b  mov     rbx, [r15+288h]
0x180014e42  mov     rcx, [rsp+140h+var_100]
0x180014e47  test    rcx, rcx
0x180014e4a  jz      short loc_180014E59
0x180014e4c  mov     rdx, [rcx]
0x180014e4f  mov     rax, [rdx+8]
0x180014e53  call    cs:__guard_dispatch_icall_fptr
0x180014e59  mov     rax, rbx
0x180014e5c  jmp     loc_180014CCF
0x180014e61  mov     rax, r12
0x180014e64  jmp     loc_180014D1F
0x180014e69  xor     edx, edx
0x180014e6b  mov     ecx, 23518781h
0x180014e70  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180014e76  int     3; Trap to Debugger
0x180014e77  mov     ecx, 23518785h
0x180014e7c  jmp     short loc_180014E83
0x180014e7e  mov     ecx, 23518784h
0x180014e83  call    cs:__imp_MsoShipAssertTagProc
0x180014e89  xor     edx, edx
0x180014e8b  mov     ecx, 23518780h
0x180014e90  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180014e96  int     3; Trap to Debugger
0x180014e97  xor     edx, edx
0x180014e99  mov     ecx, 23518763h
0x180014e9e  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```

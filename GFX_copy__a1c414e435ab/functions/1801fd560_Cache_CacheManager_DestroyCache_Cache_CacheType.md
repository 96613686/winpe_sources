# Cache::CacheManager::DestroyCache(Cache::CacheType)

- ea: `0x1801fd560`
- end: `0x1801fd6d3`
- name: `?DestroyCache@CacheManager@Cache@@UEAAXW4CacheType@2@@Z`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000d7fc`
- `0x18000fa80`
- `0x18001f6c0`
- `0x180056ee0`
- `0x180067430`
- `0x18007aa30`
- `0x1800fc9a0`
- `0x1801fd560`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801fd628`
- `KERNEL32!GetCurrentThreadId` at `0x1801fd628`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801fd599`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801fd5b8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801fd599`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801fd5b8`

## string_xrefs

- `0x1801fd639`: `threadID`
- `0x1801fd5f0`: `cacheType`
- `0x1801fd664`: `CacheManager::DestroyCache - removing cache`

## pseudocode

```c
void __fastcall Cache::CacheManager::DestroyCache(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rcx
  DWORD CurrentThreadId; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  const char *v9; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v10[8]; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v11[2]; // [rsp+50h] [rbp-49h] BYREF
  DWORD v12; // [rsp+60h] [rbp-39h]
  __int16 v13; // [rsp+64h] [rbp-35h]
  _OWORD v14[2]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v15[3]; // [rsp+90h] [rbp-9h] BYREF
  __int16 v16; // [rsp+A8h] [rbp+Fh]
  _OWORD v17[2]; // [rsp+B0h] [rbp+17h] BYREF

  v2 = (unsigned int)a2;
  if ( (unsigned int)a2 >= 0x11 )
  {
    CrashWithRecovery(0x23518761u, 0);
    __debugbreak();
  }
  if ( !*(_DWORD *)(32LL * (unsigned int)a2 + a1 + 104) )
  {
    CrashWithRecovery(0x23518760u, 0);
    __debugbreak();
  }
  LOBYTE(a2) = 1;
  Cache::CacheManager::AcquireLock(v10, a2);
  v4 = (_QWORD *)(a1 + 648 + 8 * v2);
  if ( *v4 )
  {
    std::unique_ptr<Cache::Cache>::reset(v4, 0);
    v15[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v15[1] = "cacheType";
    v15[2] = sub_18000D7FC((unsigned int)v2);
    v16 = 4;
    v17[0] = 0;
    v17[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v17[0]) = 0;
    CurrentThreadId = GetCurrentThreadId();
    v11[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v11[1] = "threadID";
    v12 = CurrentThreadId;
    v13 = 4;
    v14[0] = 0;
    v14[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v14[0]) = 0;
    v9 = "CacheManager::DestroyCache - removing cache";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      592545631,
      v6,
      v7,
      v8,
      (__int64)&v9,
      (__int64)v11,
      (__int64)v15);
    std::wstring::~wstring(v14);
    std::wstring::~wstring(v17);
  }
  Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(v10);
}

```

## disassembly

```asm
0x1801fd560  mov     [rsp-8+arg_10], rbx
0x1801fd565  mov     [rsp-8+arg_18], rsi
0x1801fd56a  push    rbp
0x1801fd56b  push    rdi
0x1801fd56c  push    r14
0x1801fd56e  lea     rbp, [rsp-47h]
0x1801fd573  sub     rsp, 0E0h
0x1801fd57a  mov     rax, cs:__security_cookie
0x1801fd581  xor     rax, rsp
0x1801fd584  mov     [rbp+57h+var_20], rax
0x1801fd588  mov     ebx, edx
0x1801fd58a  mov     rsi, rcx
0x1801fd58d  cmp     edx, 11h
0x1801fd590  jb      short loc_1801FD5A0
0x1801fd592  xor     edx, edx
0x1801fd594  mov     ecx, 23518761h
0x1801fd599  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801fd59f  int     3; Trap to Debugger
0x1801fd5a0  mov     rax, rbx
0x1801fd5a3  shl     rax, 5
0x1801fd5a7  xor     r14d, r14d
0x1801fd5aa  cmp     [rax+rcx+68h], r14d
0x1801fd5af  jnz     short loc_1801FD5BF
0x1801fd5b1  xor     edx, edx
0x1801fd5b3  mov     ecx, 23518760h
0x1801fd5b8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801fd5be  int     3; Trap to Debugger
0x1801fd5bf  mov     dl, 1
0x1801fd5c1  lea     rcx, [rbp+57h+var_A8]
0x1801fd5c5  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x1801fd5ca  lea     rcx, [rsi+288h]
0x1801fd5d1  lea     rcx, [rcx+rbx*8]
0x1801fd5d5  cmp     [rcx], r14
0x1801fd5d8  jz      loc_1801FD6A6
0x1801fd5de  xor     edx, edx
0x1801fd5e0  call    ?reset@?$unique_ptr@VCache@1@U?$default_delete@VCache@1@@std@@@std@@QEAAXPEAVCache@3@@Z; std::unique_ptr<Cache::Cache>::reset(Cache::Cache *)
0x1801fd5e5  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x1801fd5ec  mov     [rbp+57h+var_60], rax
0x1801fd5f0  lea     rax, aCachetype; "cacheType"
0x1801fd5f7  mov     [rbp+57h+var_58], rax
0x1801fd5fb  mov     ecx, ebx
0x1801fd5fd  call    sub_18000D7FC
0x1801fd602  mov     [rbp+57h+var_50], rax
0x1801fd606  mov     ebx, 4
0x1801fd60b  mov     [rbp+57h+var_48], bx
0x1801fd60f  xorps   xmm0, xmm0
0x1801fd612  movups  [rbp+57h+var_40], xmm0
0x1801fd616  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801fd61e  movdqa  [rbp+57h+var_30], xmm1
0x1801fd623  mov     word ptr [rbp+57h+var_40], r14w
0x1801fd628  call    cs:__imp_GetCurrentThreadId
0x1801fd62e  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x1801fd635  mov     [rbp+57h+var_A0], rcx
0x1801fd639  lea     rcx, aThreadid; "threadID"
0x1801fd640  mov     [rbp+57h+var_98], rcx
0x1801fd644  mov     [rbp+57h+var_90], eax
0x1801fd647  mov     [rbp+57h+var_8C], bx
0x1801fd64b  xorps   xmm0, xmm0
0x1801fd64e  movups  [rbp+57h+var_88], xmm0
0x1801fd652  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801fd65a  movdqu  [rbp+57h+var_78], xmm1
0x1801fd65f  mov     word ptr [rbp+57h+var_88], r14w
0x1801fd664  lea     rax, aCachemanagerDe; "CacheManager::DestroyCache - removing c"...
0x1801fd66b  mov     [rbp+57h+var_B0], rax
0x1801fd66f  lea     rax, [rbp+57h+var_60]
0x1801fd673  mov     [rsp+0F0h+var_C0], rax
0x1801fd678  lea     rax, [rbp+57h+var_A0]
0x1801fd67c  mov     [rsp+0F0h+var_C8], rax
0x1801fd681  lea     rax, [rbp+57h+var_B0]
0x1801fd685  mov     [rsp+0F0h+var_D0], rax
0x1801fd68a  mov     ecx, 2351875Fh
0x1801fd68f  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x1801fd694  lea     rcx, [rbp+57h+var_88]
0x1801fd698  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801fd69d  lea     rcx, [rbp+57h+var_40]
0x1801fd6a1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801fd6a6  lea     rcx, [rbp+57h+var_A8]; void *
0x1801fd6aa  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x1801fd6af  mov     rcx, [rbp+57h+var_20]
0x1801fd6b3  xor     rcx, rsp; StackCookie
0x1801fd6b6  call    __security_check_cookie
0x1801fd6bb  lea     r11, [rsp+0F0h+var_10]
0x1801fd6c3  mov     rbx, [r11+30h]
0x1801fd6c7  mov     rsi, [r11+38h]
0x1801fd6cb  mov     rsp, r11
0x1801fd6ce  pop     r14
0x1801fd6d0  pop     rdi
0x1801fd6d1  pop     rbp
0x1801fd6d2  retn
```

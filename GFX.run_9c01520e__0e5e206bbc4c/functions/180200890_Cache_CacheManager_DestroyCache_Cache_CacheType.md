# Cache::CacheManager::DestroyCache(Cache::CacheType)

- ea: `0x180200890`
- end: `0x180200a03`
- name: `?DestroyCache@CacheManager@Cache@@UEAAXW4CacheType@2@@Z`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000d6bc`
- `0x18000ef20`
- `0x18000f974`
- `0x18001f854`
- `0x1800578b0`
- `0x180077780`
- `0x1800b1120`
- `0x180200890`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180200958`
- `KERNEL32!GetCurrentThreadId` at `0x180200958`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802008c9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802008e8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802008c9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1802008e8`

## string_xrefs

- `0x180200969`: `threadID`
- `0x180200920`: `cacheType`
- `0x180200994`: `CacheManager::DestroyCache - removing cache`

## pseudocode

```c
__int64 __fastcall Cache::CacheManager::DestroyCache(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rcx
  DWORD CurrentThreadId; // eax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  const char *v10; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v12[2]; // [rsp+50h] [rbp-49h] BYREF
  DWORD v13; // [rsp+60h] [rbp-39h]
  __int16 v14; // [rsp+64h] [rbp-35h]
  _OWORD v15[2]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v16[3]; // [rsp+90h] [rbp-9h] BYREF
  __int16 v17; // [rsp+A8h] [rbp+Fh]
  _OWORD v18[2]; // [rsp+B0h] [rbp+17h] BYREF

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
  Cache::CacheManager::AcquireLock(v11, a2);
  v4 = (_QWORD *)(a1 + 648 + 8 * v2);
  if ( *v4 )
  {
    std::unique_ptr<Cache::Cache>::reset(v4, 0);
    v16[0] = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
    v16[1] = "cacheType";
    v16[2] = sub_18000D6BC((unsigned int)v2);
    v17 = 4;
    v18[0] = 0;
    v18[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18[0]) = 0;
    CurrentThreadId = GetCurrentThreadId();
    v12[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
    v12[1] = "threadID";
    v13 = CurrentThreadId;
    v14 = 4;
    v15[0] = 0;
    v15[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v15[0]) = 0;
    v10 = "CacheManager::DestroyCache - removing cache";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
      592545631,
      v6,
      v7,
      v8,
      (__int64)&v10,
      (__int64)v12,
      (__int64)v16);
    std::wstring::~wstring(v15);
    std::wstring::~wstring(v18);
  }
  return Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(v11);
}

```

## disassembly

```asm
0x180200890  mov     [rsp-8+arg_10], rbx
0x180200895  mov     [rsp-8+arg_18], rsi
0x18020089a  push    rbp
0x18020089b  push    rdi
0x18020089c  push    r14
0x18020089e  lea     rbp, [rsp-47h]
0x1802008a3  sub     rsp, 0E0h
0x1802008aa  mov     rax, cs:__security_cookie
0x1802008b1  xor     rax, rsp
0x1802008b4  mov     [rbp+57h+var_20], rax
0x1802008b8  mov     ebx, edx
0x1802008ba  mov     rsi, rcx
0x1802008bd  cmp     edx, 11h
0x1802008c0  jb      short loc_1802008D0
0x1802008c2  xor     edx, edx
0x1802008c4  mov     ecx, 23518761h
0x1802008c9  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802008cf  int     3; Trap to Debugger
0x1802008d0  mov     rax, rbx
0x1802008d3  shl     rax, 5
0x1802008d7  xor     r14d, r14d
0x1802008da  cmp     [rax+rcx+68h], r14d
0x1802008df  jnz     short loc_1802008EF
0x1802008e1  xor     edx, edx
0x1802008e3  mov     ecx, 23518760h
0x1802008e8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1802008ee  int     3; Trap to Debugger
0x1802008ef  mov     dl, 1
0x1802008f1  lea     rcx, [rbp+57h+var_A8]
0x1802008f5  call    ?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z; Cache::CacheManager::AcquireLock(bool)
0x1802008fa  lea     rcx, [rsi+288h]
0x180200901  lea     rcx, [rcx+rbx*8]
0x180200905  cmp     [rcx], r14
0x180200908  jz      loc_1802009D6
0x18020090e  xor     edx, edx
0x180200910  call    ?reset@?$unique_ptr@VCache@1@U?$default_delete@VCache@1@@std@@@std@@QEAAXPEAVCache@3@@Z; std::unique_ptr<Cache::Cache>::reset(Cache::Cache *)
0x180200915  lea     rax, ??_7?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable'
0x18020091c  mov     [rbp+57h+var_60], rax
0x180200920  lea     rax, aCachetype; "cacheType"
0x180200927  mov     [rbp+57h+var_58], rax
0x18020092b  mov     ecx, ebx
0x18020092d  call    sub_18000D6BC
0x180200932  mov     [rbp+57h+var_50], rax
0x180200936  mov     ebx, 4
0x18020093b  mov     [rbp+57h+var_48], bx
0x18020093f  xorps   xmm0, xmm0
0x180200942  movups  [rbp+57h+var_40], xmm0
0x180200946  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18020094e  movdqa  [rbp+57h+var_30], xmm1
0x180200953  mov     word ptr [rbp+57h+var_40], r14w
0x180200958  call    cs:__imp_GetCurrentThreadId
0x18020095e  lea     rcx, ??_7?$ClassifiedStructuredObject@I@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<uint>::`vftable'
0x180200965  mov     [rbp+57h+var_A0], rcx
0x180200969  lea     rcx, aThreadid; "threadID"
0x180200970  mov     [rbp+57h+var_98], rcx
0x180200974  mov     [rbp+57h+var_90], eax
0x180200977  mov     [rbp+57h+var_8C], bx
0x18020097b  xorps   xmm0, xmm0
0x18020097e  movups  [rbp+57h+var_88], xmm0
0x180200982  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18020098a  movdqu  [rbp+57h+var_78], xmm1
0x18020098f  mov     word ptr [rbp+57h+var_88], r14w
0x180200994  lea     rax, aCachemanagerDe; "CacheManager::DestroyCache - removing c"...
0x18020099b  mov     [rbp+57h+var_B0], rax
0x18020099f  lea     rax, [rbp+57h+var_60]
0x1802009a3  mov     [rsp+0F0h+var_C0], rax
0x1802009a8  lea     rax, [rbp+57h+var_A0]
0x1802009ac  mov     [rsp+0F0h+var_C8], rax
0x1802009b1  lea     rax, [rbp+57h+var_B0]
0x1802009b5  mov     [rsp+0F0h+var_D0], rax
0x1802009ba  mov     ecx, 2351875Fh
0x1802009bf  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U?$ClassifiedStructuredObject@_K@23@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@$$QEAU?$ClassifiedStructuredObject@_K@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64> &&)
0x1802009c4  lea     rcx, [rbp+57h+var_88]
0x1802009c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802009cd  lea     rcx, [rbp+57h+var_40]
0x1802009d1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802009d6  lea     rcx, [rbp+57h+var_A8]
0x1802009da  call    ??1?$TCntPtr@UIScene@GEL@@@Mso@@QEAA@XZ; Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(void)
0x1802009df  mov     rcx, [rbp+57h+var_20]
0x1802009e3  xor     rcx, rsp; StackCookie
0x1802009e6  call    __security_check_cookie
0x1802009eb  lea     r11, [rsp+0F0h+var_10]
0x1802009f3  mov     rbx, [r11+30h]
0x1802009f7  mov     rsi, [r11+38h]
0x1802009fb  mov     rsp, r11
0x1802009fe  pop     r14
0x180200a00  pop     rdi
0x180200a01  pop     rbp
0x180200a02  retn
```

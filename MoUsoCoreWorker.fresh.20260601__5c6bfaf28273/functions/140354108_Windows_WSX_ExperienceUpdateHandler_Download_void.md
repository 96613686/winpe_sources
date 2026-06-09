# Windows::WSX::ExperienceUpdateHandler::Download(void)

- ea: `0x140354108`
- end: `0x1403545a6`
- name: `?Download@ExperienceUpdateHandler@WSX@Windows@@QEAA_NXZ`
- size: `1182`
- prototype: `bool __fastcall(Windows::WSX::ExperienceUpdateHandler *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1403530e4`

## callees

- `0x140040d18`
- `0x140040dd0`
- `0x1400413a8`
- `0x14004296c`
- `0x140045404`
- `0x1400a593c`
- `0x1400b22e4`
- `0x1400c695c`
- `0x140119004`
- `0x140152b94`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x14034a5a4`
- `0x140354108`
- `0x1403545f4`
- `0x140354704`
- `0x140355370`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1403544b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1403544b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1403544c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1403544c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14035443e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14035443e`

## string_xrefs

- `0x140354569`: `create_directories`
- `0x14035415b`: `ExperienceUpdateHandler_Download`
- `0x140354471`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x1403544fe`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140354510`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140354525`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x14035453a`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x14035454f`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140354579`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall Windows::WSX::ExperienceUpdateHandler::Download(RTL_SRWLOCK *this)
{
  struct WSXProviderTelemetry *v2; // rax
  char v3; // si
  __int64 v4; // rcx
  int v5; // eax
  _DWORD *v6; // rax
  int v7; // eax
  int v8; // eax
  std::filesystem *v9; // r14
  struct std::error_code *v10; // r8
  const struct std::filesystem::path *v11; // r9
  RTL_SRWLOCK *Ptr; // rax
  _QWORD *v13; // rcx
  int v14; // eax
  __int64 v15; // r12
  __int64 v16; // r14
  _BYTE *v17; // r15
  int v19; // eax
  void *v20; // rbx
  HANDLE ProcessHeap; // rax
  char v23[16]; // [rsp+28h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v24; // [rsp+38h] [rbp-D0h] BYREF
  PVOID v25; // [rsp+40h] [rbp-C8h]
  _QWORD v26[3]; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v27[2]; // [rsp+68h] [rbp-A0h] BYREF
  int *v28; // [rsp+88h] [rbp-80h]
  __int64 *v29; // [rsp+90h] [rbp-78h]
  char v30; // [rsp+98h] [rbp-70h]
  int v31; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-60h] BYREF
  char *v33; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v34[10]; // [rsp+B8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]

  memset(v34, 0, 0x48u);
  v2 = WSXProviderTelemetry::Instance();
  LOBYTE(v34[3]) = 0;
  LODWORD(v34[0]) = 0;
  v34[1] = "ExperienceUpdateHandler_Download";
  v34[2] = 0;
  v34[4] = 0;
  v34[5] = v2;
  v34[6] = 0;
  LODWORD(v34[7]) = 0;
  v34[8] = v34;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)&v34[4]);
  v26[1] = this;
  v3 = 1;
  v26[2] = 1;
  v32 = 0;
  Windows::WSX::ExperienceUpdateHandler::CreateJob(v4, &v32);
  LOBYTE(v31) = 0;
  LODWORD(v33) = 0;
  v28 = &v31;
  v29 = &v32;
  v30 = 1;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 232LL))(v32, 1800);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)(unsigned int)v5,
      *(int *)v23);
  v6 = operator new(0x38u);
  *(_QWORD *)v6 = &winrt::impl::producers_base<Windows::WSX::CNotifyInterface,std::tuple<IBackgroundCopyCallback>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v6[4] = 1;
  *((_QWORD *)v6 + 3) = this + 14;
  *((_QWORD *)v6 + 4) = this + 23;
  *((_QWORD *)v6 + 5) = &v31;
  *((_QWORD *)v6 + 6) = &v33;
  *(_QWORD *)v6 = &winrt::impl::heap_implements<Windows::WSX::CNotifyInterface>::`vftable'{for `winrt::impl::producers_base<Windows::WSX::CNotifyInterface,std::tuple<IBackgroundCopyCallback>>'};
  *((_QWORD *)v6 + 1) = &winrt::impl::heap_implements<Windows::WSX::CNotifyInterface>::`vftable'{for `winrt::impl::root_implements<Windows::WSX::CNotifyInterface,IBackgroundCopyCallback>'};
  v26[0] = v6;
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 200LL))(v32);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)(unsigned int)v7,
      *(int *)v23);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 184LL))(v32, 3);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)(unsigned int)v8,
      *(int *)v23);
  v9 = (std::filesystem *)std::filesystem::path::parent_path(&this[8], v27);
  *(_QWORD *)v23 = 0;
  *(_QWORD *)&v23[8] = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  std::filesystem::create_directories(v9, (const struct std::filesystem::path *)v23, v10);
  if ( *(_DWORD *)v23 )
    std::filesystem::_Throw_fs_error((std::filesystem *)"create_directories", v23, v9, v11);
  std::wstring::~wstring(v27);
  Ptr = this;
  if ( this[3].Ptr > (PVOID)7 )
    Ptr = (RTL_SRWLOCK *)this->Ptr;
  v24 = Ptr;
  v25 = this[2].Ptr;
  v13 = this[12].Ptr;
  if ( v13 )
  {
    *(_QWORD *)v23 = v13[2];
    *(_QWORD *)&v23[8] = *((unsigned int *)v13 + 1);
  }
  else
  {
    *(_QWORD *)v23 = &psz;
    *(_QWORD *)&v23[8] = 0;
  }
  Windows::WSX::ExperienceUpdateHandler::AddFileWithRanges(v32, &this[4], v23, &v24);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 56LL))(v32);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)(unsigned int)v14,
      *(int *)v23);
  v24 = this + 23;
  v25 = 0;
  if ( (unsigned int)mtx_do_lock(&this[23], 0) )
    std::_Throw_Cpp_error(5);
  if ( HIDWORD(this[32].Ptr) == 0x7FFFFFFF )
  {
    HIDWORD(this[32].Ptr) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  LOBYTE(v25) = 1;
  *(_QWORD *)v23 = &v31;
  *(_QWORD *)&v23[8] = this;
  v27[0] = *(_OWORD *)v23;
  v15 = std::_To_absolute_time<__int64,std::ratio<1,1>>(
          v23,
          &Windows::WSX::ExperienceUpdateHandler::c_jobProgressTimeout);
  v16 = *((_QWORD *)&v27[0] + 1);
  v17 = *(_BYTE **)&v27[0];
  while ( !*v17
       && !*(_BYTE *)(v16 + 264)
       && !*(_BYTE *)(v16 + 265)
       && (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                          &this[14],
                          &v24,
                          v15) != 1 )
    ;
  if ( (_BYTE)v31 )
  {
    if ( (int)v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
        (const char *)(unsigned int)v33,
        *(int *)v23);
  }
  else
  {
    if ( LOBYTE(this[33].Ptr) || BYTE1(this[33].Ptr) )
      v3 = 0;
    if ( v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
        (const char *)0x800705B4LL,
        *(int *)v23);
    v3 = 0;
  }
  if ( HIDWORD(this[32].Ptr)-- == 1 )
  {
    LODWORD(this[32].Ptr) = -1;
    ReleaseSRWLockExclusive(this + 25);
  }
  winrt::com_ptr<IBackgroundCopyCallback>::unconditional_release_ref(v26);
  if ( !(_BYTE)v31 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 64LL))(v32);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
        (const char *)(unsigned int)v19,
        *(int *)v23);
  }
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  LOWORD(this[33].Ptr) = 0;
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&v34[4]);
  if ( LOBYTE(v34[3]) )
  {
    v20 = (void *)v34[2];
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
  }
  return v3;
}

```

## disassembly

```asm
0x140354108  mov     rax, rsp
0x14035410b  mov     [rax+10h], rbx
0x14035410f  mov     [rax+18h], rsi
0x140354113  mov     [rax+20h], rdi
0x140354117  push    rbp
0x140354118  push    r12
0x14035411a  push    r13
0x14035411c  push    r14
0x14035411e  push    r15
0x140354120  lea     rbp, [rax-38h]
0x140354124  sub     rsp, 110h
0x14035412b  mov     rax, cs:__security_cookie
0x140354132  xor     rax, rsp
0x140354135  mov     [rbp+30h+var_30], rax
0x140354139  mov     rbx, rcx
0x14035413c  xor     r15d, r15d
0x14035413f  xor     edx, edx; Val
0x140354141  lea     r8d, [r15+48h]; Size
0x140354145  lea     rcx, [rbp+30h+var_80]; void *
0x140354149  call    memset
0x14035414e  call    ?Instance@WSXProviderTelemetry@@KAPEAU1@XZ; WSXProviderTelemetry::Instance(void)
0x140354153  mov     [rbp+30h+var_68], r15b
0x140354157  mov     [rbp+30h+var_80], r15d
0x14035415b  lea     rcx, aExperienceupda_1; "ExperienceUpdateHandler_Download"
0x140354162  mov     [rbp+30h+var_78], rcx
0x140354166  mov     [rbp+30h+lpMem], r15
0x14035416a  mov     [rbp+30h+var_60], r15
0x14035416e  mov     [rbp+30h+var_58], rax
0x140354172  mov     [rbp+30h+var_50], r15
0x140354176  mov     [rbp+30h+var_48], r15d
0x14035417a  lea     rax, [rbp+30h+var_80]
0x14035417e  mov     [rbp+30h+var_40], rax
0x140354182  lea     rcx, [rbp+30h+var_60]; this
0x140354186  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14035418b  nop
0x14035418c  xorps   xmm0, xmm0
0x14035418f  movups  [rsp+130h+var_F0+8], xmm0
0x140354194  mov     qword ptr [rsp+130h+var_F0+8], rbx
0x140354199  lea     esi, [r15+1]
0x14035419d  mov     [rsp+130h+var_E0], sil
0x1403541a2  mov     [rbp+30h+var_90], r15
0x1403541a6  lea     rdx, [rbp+30h+var_90]
0x1403541aa  call    ?CreateJob@ExperienceUpdateHandler@WSX@Windows@@AEAA?AV?$com_ptr_t@UIBackgroundCopyJob@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::WSX::ExperienceUpdateHandler::CreateJob(void)
0x1403541af  nop
0x1403541b0  mov     byte ptr [rbp+30h+var_98], r15b
0x1403541b4  mov     dword ptr [rbp+30h+var_88], r15d
0x1403541b8  lea     rax, [rbp+30h+var_98]
0x1403541bc  mov     [rbp+30h+var_B0], rax
0x1403541c0  lea     rax, [rbp+30h+var_90]
0x1403541c4  mov     [rbp+30h+var_A8], rax
0x1403541c8  mov     [rbp+30h+var_A0], sil
0x1403541cc  mov     rcx, [rbp+30h+var_90]
0x1403541d0  mov     rax, [rcx]
0x1403541d3  mov     edx, 708h
0x1403541d8  mov     rax, [rax+0E8h]
0x1403541df  call    _guard_dispatch_icall
0x1403541e4  mov     rcx, [rbp+38h]; this
0x1403541e8  test    eax, eax
0x1403541ea  js      loc_140354522
0x1403541f0  lea     ecx, [rsi+37h]; Size
0x1403541f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1403541f8  mov     rdx, rax
0x1403541fb  mov     qword ptr [rsp+130h+var_F0], rax
0x140354200  lea     rax, ??_7?$producers_base@UCNotifyInterface@WSX@Windows@@V?$tuple@UIBackgroundCopyCallback@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<Windows::WSX::CNotifyInterface,std::tuple<IBackgroundCopyCallback>>::`vftable'
0x140354207  mov     [rdx], rax
0x14035420a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140354211  mov     [rdx+10h], esi
0x140354214  lea     r13, [rbx+70h]
0x140354218  mov     [rdx+18h], r13
0x14035421c  lea     rdi, [rbx+0B8h]
0x140354223  mov     [rdx+20h], rdi
0x140354227  lea     rax, [rbp+30h+var_98]
0x14035422b  mov     [rdx+28h], rax
0x14035422f  lea     rax, [rbp+30h+var_88]
0x140354233  mov     [rdx+30h], rax
0x140354237  lea     rax, ??_7?$heap_implements@UCNotifyInterface@WSX@Windows@@@impl@winrt@@6B?$producers_base@UCNotifyInterface@WSX@Windows@@V?$tuple@UIBackgroundCopyCallback@@@std@@@12@@; const winrt::impl::heap_implements<Windows::WSX::CNotifyInterface>::`vftable'{for `winrt::impl::producers_base<Windows::WSX::CNotifyInterface,std::tuple<IBackgroundCopyCallback>>'}
0x14035423e  mov     [rdx], rax
0x140354241  lea     rax, ??_7?$heap_implements@UCNotifyInterface@WSX@Windows@@@impl@winrt@@6B?$root_implements@UCNotifyInterface@WSX@Windows@@UIBackgroundCopyCallback@@@12@@; const winrt::impl::heap_implements<Windows::WSX::CNotifyInterface>::`vftable'{for `winrt::impl::root_implements<Windows::WSX::CNotifyInterface,IBackgroundCopyCallback>'}
0x140354248  mov     [rdx+8], rax
0x14035424c  mov     qword ptr [rsp+130h+var_F0], rdx
0x140354251  mov     rcx, [rbp+30h+var_90]
0x140354255  mov     rax, [rcx]
0x140354258  mov     rax, [rax+0C8h]
0x14035425f  call    _guard_dispatch_icall
0x140354264  mov     rcx, [rbp+38h]; this
0x140354268  test    eax, eax
0x14035426a  js      loc_140354537
0x140354270  mov     rcx, [rbp+30h+var_90]
0x140354274  mov     rax, [rcx]
0x140354277  lea     edx, [rsi+2]
0x14035427a  mov     rax, [rax+0B8h]
0x140354281  call    _guard_dispatch_icall
0x140354286  mov     rcx, [rbp+38h]; this
0x14035428a  test    eax, eax
0x14035428c  js      loc_14035454C
0x140354292  lea     rcx, [rbx+40h]
0x140354296  lea     rdx, [rsp+130h+var_D8+8]
0x14035429b  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x1403542a0  mov     r14, rax
0x1403542a3  mov     qword ptr [rsp+130h+var_118+8], r15
0x1403542a8  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x1403542af  mov     qword ptr [rsp+130h+var_108], rax
0x1403542b4  lea     rdx, [rsp+130h+var_118+8]; struct std::filesystem::path *
0x1403542b9  mov     rcx, r14; this
0x1403542bc  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x1403542c1  cmp     dword ptr [rsp+130h+var_118+8], r15d
0x1403542c6  jnz     loc_140354561
0x1403542cc  lea     rcx, [rsp+130h+var_D8+8]
0x1403542d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403542d6  mov     rax, rbx
0x1403542d9  cmp     qword ptr [rbx+18h], 7
0x1403542de  jbe     short loc_1403542E3
0x1403542e0  mov     rax, [rbx]
0x1403542e3  mov     qword ptr [rsp+130h+var_108+8], rax
0x1403542e8  mov     rax, [rbx+10h]
0x1403542ec  mov     [rsp+130h+var_F8], rax
0x1403542f1  mov     rcx, [rbx+60h]
0x1403542f5  test    rcx, rcx
0x1403542f8  jz      short loc_14035430D
0x1403542fa  mov     rax, [rcx+10h]
0x1403542fe  mov     qword ptr [rsp+130h+var_118+8], rax
0x140354303  mov     eax, [rcx+4]
0x140354306  mov     qword ptr [rsp+130h+var_108], rax
0x14035430b  jmp     short loc_14035431E
0x14035430d  lea     rax, psz
0x140354314  mov     qword ptr [rsp+130h+var_118+8], rax; int
0x140354319  mov     qword ptr [rsp+130h+var_108], r15
0x14035431e  lea     rdx, [rbx+20h]
0x140354322  lea     r9, [rsp+130h+var_108+8]
0x140354327  lea     r8, [rsp+130h+var_118+8]
0x14035432c  mov     rcx, [rbp+30h+var_90]
0x140354330  call    ?AddFileWithRanges@ExperienceUpdateHandler@WSX@Windows@@CAXPEAUIBackgroundCopyJob@@AEBVpath@filesystem@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@7@2@Z; Windows::WSX::ExperienceUpdateHandler::AddFileWithRanges(IBackgroundCopyJob *,std::filesystem::path const &,std::wstring_view const &,std::wstring_view const &)
0x140354335  mov     rcx, [rbp+30h+var_90]
0x140354339  mov     rax, [rcx]
0x14035433c  mov     rax, [rax+38h]
0x140354340  call    _guard_dispatch_icall
0x140354345  mov     rcx, [rbp+38h]; this
0x140354349  test    eax, eax
0x14035434b  js      loc_140354576
0x140354351  xorps   xmm0, xmm0
0x140354354  movups  [rsp+130h+var_108+8], xmm0
0x140354359  mov     qword ptr [rsp+130h+var_108+8], rdi
0x14035435e  mov     byte ptr [rsp+130h+var_F8], r15b
0x140354363  xor     edx, edx
0x140354365  mov     rcx, rdi
0x140354368  call    mtx_do_lock
0x14035436d  test    eax, eax
0x14035436f  jnz     loc_14035458B
0x140354375  mov     eax, [rdi+4Ch]
0x140354378  cmp     eax, 7FFFFFFFh
0x14035437d  jz      loc_140354596
0x140354383  mov     byte ptr [rsp+130h+var_F8], sil
0x140354388  lea     rax, [rbp+30h+var_98]
0x14035438c  mov     qword ptr [rsp+130h+var_118+8], rax; int
0x140354391  mov     qword ptr [rsp+130h+var_108], rbx
0x140354396  movaps  xmm0, xmmword ptr [rsp+130h+var_118+8]
0x14035439b  movdqa  [rsp+130h+var_D8+8], xmm0
0x1403543a1  lea     rdx, ?c_jobProgressTimeout@ExperienceUpdateHandler@WSX@Windows@@0V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@B; std::chrono::duration<__int64,std::ratio<1,1>> const Windows::WSX::ExperienceUpdateHandler::c_jobProgressTimeout
0x1403543a8  lea     rcx, [rsp+130h+var_118+8]
0x1403543ad  call    ??$_To_absolute_time@_JU?$ratio@$00$00@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@0@@Z
0x1403543b2  mov     r12, rax
0x1403543b5  mov     r14, [rsp+130h+var_C8]
0x1403543ba  mov     r15, qword ptr [rsp+130h+var_D8+8]
0x1403543bf  xor     eax, eax
0x1403543c1  cmp     [r15], al
0x1403543c4  jnz     short loc_1403543EC
0x1403543c6  cmp     [r14+108h], al
0x1403543cd  jnz     short loc_1403543EC
0x1403543cf  cmp     [r14+109h], al
0x1403543d6  jnz     short loc_1403543EC
0x1403543d8  mov     r8, r12
0x1403543db  lea     rdx, [rsp+130h+var_108+8]
0x1403543e0  mov     rcx, r13
0x1403543e3  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x1403543e8  cmp     eax, esi
0x1403543ea  jnz     short loc_1403543BF
0x1403543ec  xor     r14d, r14d
0x1403543ef  cmp     byte ptr [rbp+30h+var_98], r14b
0x1403543f3  jz      short loc_140354408
0x1403543f5  mov     rcx, [rbp+38h]; this
0x1403543f9  mov     r9d, dword ptr [rbp+30h+var_88]; char *
0x1403543fd  test    r9d, r9d
0x140354400  js      loc_140354510
0x140354406  jmp     short loc_14035442D
0x140354408  cmp     [rbx+108h], r14b
0x14035440f  jnz     short loc_14035441A
0x140354411  cmp     [rbx+109h], r14b
0x140354418  jz      short loc_14035441D
0x14035441a  mov     sil, r14b
0x14035441d  mov     rcx, [rbp+38h]; this
0x140354421  test    sil, sil
0x140354424  jnz     loc_1403544F8
0x14035442a  mov     sil, r14b
0x14035442d  sub     dword ptr [rdi+4Ch], 1
0x140354431  jnz     short loc_140354445
0x140354433  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x14035443a  lea     rcx, [rdi+10h]; SRWLock
0x14035443e  call    cs:__imp_ReleaseSRWLockExclusive
0x140354444  nop
0x140354445  lea     rcx, [rsp+130h+var_F0]
0x14035444a  call    ?unconditional_release_ref@?$com_ptr@UIBackgroundCopyCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IBackgroundCopyCallback>::unconditional_release_ref(void)
0x14035444f  nop
0x140354450  cmp     byte ptr [rbp+30h+var_98], r14b
0x140354454  jnz     short loc_140354483
0x140354456  mov     rcx, [rbp+30h+var_90]
0x14035445a  mov     rax, [rcx]
0x14035445d  mov     rax, [rax+40h]
0x140354461  call    _guard_dispatch_icall
0x140354466  mov     rcx, [rbp+38h]; this
0x14035446a  test    eax, eax
0x14035446c  jns     short loc_140354483
0x14035446e  mov     r9d, eax; char *
0x140354471  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354478  mov     edx, 0A7h; void *
0x14035447d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140354482  nop
0x140354483  mov     rcx, [rbp+30h+var_90]
0x140354487  test    rcx, rcx
0x14035448a  jz      short loc_140354499
0x14035448c  mov     rax, [rcx]
0x14035448f  mov     rax, [rax+10h]
0x140354493  call    _guard_dispatch_icall
0x140354498  nop
0x140354499  mov     [rbx+108h], r14w
0x1403544a1  lea     rcx, [rbp+30h+var_60]; this
0x1403544a5  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1403544aa  cmp     [rbp+30h+var_68], r14b
0x1403544ae  jz      short loc_1403544C8
0x1403544b0  mov     rbx, [rbp+30h+lpMem]
0x1403544b4  call    cs:__imp_GetProcessHeap
0x1403544ba  mov     r8, rbx; lpMem
0x1403544bd  xor     edx, edx; dwFlags
0x1403544bf  mov     rcx, rax; hHeap
0x1403544c2  call    cs:__imp_HeapFree
0x1403544c8  mov     al, sil
0x1403544cb  mov     rcx, [rbp+30h+var_30]
0x1403544cf  xor     rcx, rsp; StackCookie
0x1403544d2  call    __security_check_cookie
0x1403544d7  lea     r11, [rsp+130h+var_20]
0x1403544df  mov     rbx, [r11+38h]
0x1403544e3  mov     rsi, [r11+40h]
0x1403544e7  mov     rdi, [r11+48h]
0x1403544eb  mov     rsp, r11
0x1403544ee  pop     r15
0x1403544f0  pop     r14
0x1403544f2  pop     r13
0x1403544f4  pop     r12
0x1403544f6  pop     rbp
0x1403544f7  retn
0x1403544f8  mov     r9d, 800705B4h; char *
0x1403544fe  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354505  mov     edx, 0CCh; void *
0x14035450a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140354510  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354517  mov     edx, 0C7h; void *
0x14035451c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140354522  mov     r9d, eax; char *
0x140354525  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14035452c  mov     edx, 0E3h; void *
0x140354531  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140354537  mov     r9d, eax; char *
0x14035453a  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354541  mov     edx, 0B3h; void *
0x140354546  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14035454c  mov     r9d, eax; char *
0x14035454f  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354556  mov     edx, 0B6h; void *
0x14035455b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140354561  mov     r8, r14; struct std::error_code *
0x140354564  lea     rdx, [rsp+130h+var_118+8]; char *
0x140354569  lea     rcx, aCreateDirector_0; "create_directories"
0x140354570  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x140354576  mov     r9d, eax; char *
0x140354579  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354580  mov     edx, 0BFh; void *
0x140354585  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14035458b  mov     ecx, 5; int
0x140354590  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140354596  dec     eax
0x140354598  mov     [rdi+4Ch], eax
0x14035459b  mov     ecx, 6; int
0x1403545a0  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

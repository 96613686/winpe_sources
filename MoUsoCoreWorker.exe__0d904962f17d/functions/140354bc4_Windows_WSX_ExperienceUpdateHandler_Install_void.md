# Windows::WSX::ExperienceUpdateHandler::Install(void)

- ea: `0x140354bc4`
- end: `0x140355122`
- name: `?Install@ExperienceUpdateHandler@WSX@Windows@@QEAAXXZ`
- size: `1374`
- prototype: `void __fastcall(Windows::WSX::ExperienceUpdateHandler *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140352af0`

## callees

- `0x14003c578`
- `0x140040d18`
- `0x140040dd0`
- `0x1400413a8`
- `0x14004296c`
- `0x1400741c4`
- `0x1400743a8`
- `0x1400a593c`
- `0x1400b22e4`
- `0x140118c84`
- `0x140150f10`
- `0x140152b94`
- `0x14018b0dc`
- `0x14018c370`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x14030535c`
- `0x140326100`
- `0x1403266c4`
- `0x14034a5a4`
- `0x140354bc4`
- `0x140355128`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140355047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140355047`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140355055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140355055`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140354f8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140354f8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140354d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140354d69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140354d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140354d69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140354f17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140354f17`
- `WOFUTIL!WofSetFileDataLocation` at `0x140354f3a`
- `WOFUTIL!WofSetFileDataLocation` at `0x140354f3a`
- `SETUPAPI!SetupIterateCabinetW` at `0x140354e09`
- `SETUPAPI!SetupIterateCabinetW` at `0x140354e09`

## string_xrefs

- `0x140355103`: `create_directories`
- `0x14035508c`: `directory_entry::status`
- `0x14035509b`: `recursive_directory_iterator::operator++`
- `0x140354f57`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140354f6e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x1403550ae`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x1403550e6`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140355110`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\WSXProvider\ExperienceUpdateHandler.cpp`
- `0x140354c17`: `ExperienceUpdateHandler_Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::WSX::ExperienceUpdateHandler::Install(RTL_SRWLOCK *this)
{
  struct WSXProviderTelemetry *v2; // rax
  unsigned int v3; // r14d
  RTL_SRWLOCK *v4; // rsi
  RTL_SRWLOCK *Ptr; // rcx
  __int64 v6; // rax
  __int64 v7; // r12
  char v8; // al
  bool v9; // zf
  unsigned int *v10; // rax
  unsigned __int64 v11; // rcx
  const OLECHAR *v12; // rdx
  struct std::error_code *v13; // r8
  RTL_SRWLOCK *v14; // rdi
  const struct std::filesystem::path *v15; // r9
  void *v16; // r9
  const char *v17; // r9
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rbx
  const WCHAR *v20; // rcx
  char *FileW; // rbx
  const char *v22; // r9
  unsigned int v23; // eax
  unsigned int v24; // eax
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  void *v27; // rbx
  HANDLE ProcessHeap; // rax
  DWORD dwCreationDisposition; // [rsp+28h] [rbp-A9h]
  char v30[8]; // [rsp+48h] [rbp-89h] BYREF
  void ***v31; // [rsp+50h] [rbp-81h]
  unsigned __int128 v32; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int128 v33; // [rsp+68h] [rbp-69h] BYREF
  _QWORD v34[2]; // [rsp+80h] [rbp-51h] BYREF
  __int128 v35; // [rsp+90h] [rbp-41h]
  __int64 ExternalFileInfo; // [rsp+A0h] [rbp-31h] BYREF
  _QWORD v37[10]; // [rsp+A8h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+5Fh]

  memset(v37, 0, 0x48u);
  v2 = WSXProviderTelemetry::Instance();
  LOBYTE(v37[3]) = 0;
  LODWORD(v37[0]) = 0;
  v37[1] = "ExperienceUpdateHandler_Install";
  v37[2] = 0;
  v37[4] = 0;
  v37[5] = v2;
  v37[6] = 0;
  LODWORD(v37[7]) = 0;
  v37[8] = v37;
  wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)&v37[4]);
  v34[1] = 1;
  v34[0] = this;
  v3 = 0;
  v4 = this + 4;
LABEL_2:
  Ptr = this + 4;
  if ( this[7].Ptr > (PVOID)7 )
    Ptr = (RTL_SRWLOCK *)v4->Ptr;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)&Ptr->Ptr + v6) );
  *(_QWORD *)&v33 = Ptr;
  *((_QWORD *)&v33 + 1) = v6;
  if ( !(unsigned __int8)Windows::Trust::IsFileSelfSigned(&v33) && ++v3 < 3 )
  {
    v32 = (unsigned __int64)&this[23];
    if ( (unsigned int)mtx_do_lock(&this[23], 0) )
      std::_Throw_Cpp_error(5);
    if ( HIDWORD(this[32].Ptr) == 0x7FFFFFFF )
    {
      HIDWORD(this[32].Ptr) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v32) = 1;
    v7 = std::_To_absolute_time<__int64,std::ratio<1,1>>(
           v30,
           &Windows::WSX::ExperienceUpdateHandler::c_selfSignVerificationAttemptInterval);
    while ( !LOBYTE(this[33].Ptr) && !BYTE1(this[33].Ptr) )
    {
      if ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                           &this[14],
                           &v32,
                           v7) == 1 )
      {
        if ( LOBYTE(this[33].Ptr) || (v8 = 0, BYTE1(this[33].Ptr)) )
          v8 = 1;
        if ( !v8 )
        {
          v9 = HIDWORD(this[32].Ptr)-- == 1;
          if ( v9 )
          {
            LODWORD(this[32].Ptr) = -1;
            ReleaseSRWLockExclusive(this + 25);
          }
          goto LABEL_2;
        }
        break;
      }
    }
    v3 = 3;
    v9 = HIDWORD(this[32].Ptr)-- == 1;
    if ( v9 )
    {
      LODWORD(this[32].Ptr) = -1;
      ReleaseSRWLockExclusive(this + 25);
    }
  }
  if ( v3 >= 3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)0x800B010BLL,
      dwCreationDisposition);
  v10 = (unsigned int *)this[13].Ptr;
  if ( v10 )
  {
    v11 = v10[1];
    v12 = (const OLECHAR *)*((_QWORD *)v10 + 2);
  }
  else
  {
    v11 = 0;
    v12 = &psz;
  }
  v32 = __PAIR128__(v11, (unsigned __int64)v12);
  if ( !(unsigned __int8)Windows::Trust::VerifyFileHash(&this[4], v12, &v32) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      (const char *)0x8024A108LL,
      dwCreationDisposition);
  v14 = this + 8;
  *(_QWORD *)v30 = 0;
  v31 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  std::filesystem::create_directories((std::filesystem *)v14, (const struct std::filesystem::path *)v30, v13);
  if ( *(_DWORD *)v30 )
    std::filesystem::_Throw_fs_error(
      (std::filesystem *)"create_directories",
      v30,
      (const struct std::error_code *)v14,
      v15);
  v16 = v14;
  if ( v14[3].Ptr > (PVOID)7 )
    v16 = v14->Ptr;
  if ( v4[3].Ptr > (PVOID)7 )
    v4 = (RTL_SRWLOCK *)v4->Ptr;
  if ( !SetupIterateCabinetW((PCWSTR)v4, 0, Windows::WSX::_anonymous_namespace_::CabinetCallbackToExpand, v16) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x189,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
      v17);
  ExternalFileInfo = 1;
  std::filesystem::recursive_directory_iterator::recursive_directory_iterator(
    (std::filesystem::recursive_directory_iterator *)&v33,
    (const struct std::filesystem::path *)v14);
  v32 = 0;
  v18 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL));
    v18 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  }
  v32 = v33;
  if ( v18 )
  {
    _InterlockedIncrement(v18 + 2);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  }
  v35 = 0;
  if ( v18 )
  {
    if ( !_InterlockedDecrement(v18 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( !_InterlockedDecrement(v18 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  while ( 1 )
  {
    v19 = v32;
    if ( !(_QWORD)v32 )
      break;
    std::filesystem::directory_entry::_Get_any_status(v32, v30, 3);
    if ( (_DWORD)v31 && ((*(_DWORD *)v30 - 1) & 0xFFFFFFF7) != 0 )
      std::filesystem::_Throw_fs_error("directory_entry::status", (unsigned int)v31, v19 + 32);
    if ( *(_DWORD *)v30 == 2 )
    {
      v20 = (const WCHAR *)(v19 + 32);
      if ( *(_QWORD *)(v19 + 56) > 7u )
        v20 = *(const WCHAR **)v20;
      FileW = (char *)CreateFileW(v20, 0xC0000000, 1u, 0, 3u, 0x80u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x197,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
          v22);
      }
      else
      {
        v23 = WofSetFileDataLocation(FileW, 2u, &ExternalFileInfo, 8u);
        wil::details::in1diag3::Log_IfFailedWithExpected(
          retaddr,
          (void *)0x19C,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\WSXProvider\\ExperienceUpdateHandler.cpp",
          (const char *)v23,
          1,
          0x80070158);
        CloseHandle(FileW);
      }
    }
    v24 = std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(&v32);
    if ( v24 )
      std::filesystem::_Throw_fs_error("recursive_directory_iterator::operator++", v24);
  }
  v25 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( !_InterlockedDecrement(v25 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( !_InterlockedDecrement(v26 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  wil::details::lambda_call__Windows::WSX::ExperienceUpdateHandler::Install_::_2_::_lambda_1___::_lambda_call__Windows::WSX::ExperienceUpdateHandler::Install_::_2_::_lambda_1___(v34);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)&v37[4]);
  if ( LOBYTE(v37[3]) )
  {
    v27 = (void *)v37[2];
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v27);
  }
}

```

## disassembly

```asm
0x140354bc4  mov     rax, rsp
0x140354bc7  mov     [rax+10h], rbx
0x140354bcb  mov     [rax+18h], rsi
0x140354bcf  mov     [rax+20h], rdi
0x140354bd3  push    rbp
0x140354bd4  push    r12
0x140354bd6  push    r13
0x140354bd8  push    r14
0x140354bda  push    r15
0x140354bdc  lea     rbp, [rax-5Fh]
0x140354be0  sub     rsp, 100h
0x140354be7  mov     rax, cs:__security_cookie
0x140354bee  xor     rax, rsp
0x140354bf1  mov     [rbp+57h+var_30], rax
0x140354bf5  mov     rdi, rcx
0x140354bf8  xor     edx, edx; Val
0x140354bfa  lea     r8d, [rdx+48h]; Size
0x140354bfe  lea     rcx, [rbp+57h+var_80]; void *
0x140354c02  call    memset
0x140354c07  call    ?Instance@WSXProviderTelemetry@@KAPEAU1@XZ; WSXProviderTelemetry::Instance(void)
0x140354c0c  xor     r13d, r13d
0x140354c0f  mov     [rbp+57h+var_68], r13b
0x140354c13  mov     [rbp+57h+var_80], r13d
0x140354c17  lea     rcx, aExperienceupda; "ExperienceUpdateHandler_Install"
0x140354c1e  mov     [rbp+57h+var_78], rcx
0x140354c22  mov     [rbp+57h+lpMem], r13
0x140354c26  mov     [rbp+57h+var_60], r13
0x140354c2a  mov     [rbp+57h+var_58], rax
0x140354c2e  mov     [rbp+57h+var_50], r13
0x140354c32  mov     [rbp+57h+var_48], r13d
0x140354c36  lea     rax, [rbp+57h+var_80]
0x140354c3a  mov     [rbp+57h+var_40], rax
0x140354c3e  lea     rcx, [rbp+57h+var_60]; this
0x140354c42  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140354c47  nop
0x140354c48  xorps   xmm0, xmm0
0x140354c4b  movups  [rbp+57h+var_A8], xmm0
0x140354c4f  mov     qword ptr [rbp+57h+var_A8], rdi
0x140354c53  mov     byte ptr [rbp+57h+var_A8+8], 1
0x140354c57  mov     r14d, r13d
0x140354c5a  lea     rsi, [rdi+20h]
0x140354c5e  or      r15, 0FFFFFFFFFFFFFFFFh
0x140354c62  mov     rcx, rsi
0x140354c65  cmp     qword ptr [rdi+38h], 7
0x140354c6a  jbe     short loc_140354C6F
0x140354c6c  mov     rcx, [rsi]
0x140354c6f  mov     rax, r15
0x140354c72  inc     rax
0x140354c75  cmp     [rcx+rax*2], r13w
0x140354c7a  jnz     short loc_140354C72
0x140354c7c  mov     qword ptr [rbp+57h+var_C0], rcx
0x140354c80  mov     qword ptr [rbp+57h+var_C0+8], rax
0x140354c84  lea     rcx, [rbp+57h+var_C0]
0x140354c88  call    ?IsFileSelfSigned@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsFileSelfSigned(wil::basic_zstring_view<wchar_t>,bool)
0x140354c8d  test    al, al
0x140354c8f  jnz     loc_140354D6F
0x140354c95  inc     r14d
0x140354c98  cmp     r14d, 3
0x140354c9c  jnb     loc_140354D6F
0x140354ca2  xorps   xmm0, xmm0
0x140354ca5  movups  [rbp+57h+var_D0], xmm0
0x140354ca9  lea     rbx, [rdi+0B8h]
0x140354cb0  mov     qword ptr [rbp+57h+var_D0], rbx
0x140354cb4  xor     edx, edx
0x140354cb6  mov     rcx, rbx
0x140354cb9  call    mtx_do_lock
0x140354cbe  test    eax, eax
0x140354cc0  jnz     loc_1403550D5
0x140354cc6  cmp     dword ptr [rdi+104h], 7FFFFFFFh
0x140354cd0  jz      loc_1403550C0
0x140354cd6  mov     byte ptr [rbp+57h+var_D0+8], 1
0x140354cda  lea     rdx, ?c_selfSignVerificationAttemptInterval@ExperienceUpdateHandler@WSX@Windows@@0V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@B; std::chrono::duration<__int64,std::ratio<1,1>> const Windows::WSX::ExperienceUpdateHandler::c_selfSignVerificationAttemptInterval
0x140354ce1  lea     rcx, [rsp+120h+var_E0]
0x140354ce6  call    ??$_To_absolute_time@_JU?$ratio@$00$00@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@0@@Z
0x140354ceb  mov     r12, rax
0x140354cee  cmp     [rdi+108h], r13b
0x140354cf5  jnz     short loc_140354D51
0x140354cf7  cmp     [rdi+109h], r13b
0x140354cfe  jnz     short loc_140354D51
0x140354d00  mov     r8, r12
0x140354d03  lea     rdx, [rbp+57h+var_D0]
0x140354d07  lea     rcx, [rdi+70h]
0x140354d0b  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x140354d10  cmp     eax, 1
0x140354d13  jnz     short loc_140354CEE
0x140354d15  cmp     [rdi+108h], r13b
0x140354d1c  jnz     short loc_140354D2A
0x140354d1e  cmp     [rdi+109h], r13b
0x140354d25  mov     al, r13b
0x140354d28  jz      short loc_140354D2C
0x140354d2a  mov     al, 1
0x140354d2c  test    al, al
0x140354d2e  jnz     short loc_140354D51
0x140354d30  or      r15, 0FFFFFFFFFFFFFFFFh
0x140354d34  add     [rbx+4Ch], r15d
0x140354d38  jnz     loc_140354C62
0x140354d3e  mov     [rbx+48h], r15d
0x140354d42  lea     rcx, [rbx+10h]; SRWLock
0x140354d46  call    cs:__imp_ReleaseSRWLockExclusive
0x140354d4c  jmp     loc_140354C62
0x140354d51  mov     r14d, 3
0x140354d57  or      r15, 0FFFFFFFFFFFFFFFFh
0x140354d5b  add     [rbx+4Ch], r15d
0x140354d5f  jnz     short loc_140354D6F
0x140354d61  mov     [rbx+48h], r15d
0x140354d65  lea     rcx, [rbx+10h]; SRWLock
0x140354d69  call    cs:__imp_ReleaseSRWLockExclusive
0x140354d6f  mov     rcx, [rbp+5Fh]; this
0x140354d73  cmp     r14d, 3
0x140354d77  jnb     loc_1403550A8
0x140354d7d  mov     rax, [rdi+68h]
0x140354d81  test    rax, rax
0x140354d84  jz      short loc_140354D8F
0x140354d86  mov     ecx, [rax+4]
0x140354d89  mov     rdx, [rax+10h]
0x140354d8d  jmp     short loc_140354D99
0x140354d8f  mov     rcx, r13
0x140354d92  lea     rdx, psz
0x140354d99  mov     qword ptr [rbp+57h+var_D0], rdx
0x140354d9d  mov     qword ptr [rbp+57h+var_D0+8], rcx
0x140354da1  mov     rbx, [rbp+5Fh]
0x140354da5  lea     r8, [rbp+57h+var_D0]
0x140354da9  mov     rcx, rsi
0x140354dac  call    ?VerifyFileHash@Trust@Windows@@YA_NAEBVpath@filesystem@std@@W4AlgorithmType@Hash@2@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Windows::Trust::VerifyFileHash(std::filesystem::path const &,Windows::Hash::AlgorithmType,std::wstring_view)
0x140354db1  test    al, al
0x140354db3  jz      loc_1403550E0
0x140354db9  add     rdi, 40h ; '@'
0x140354dbd  mov     qword ptr [rsp+120h+var_E0], r13
0x140354dc2  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x140354dc9  mov     [rsp+120h+var_D8], rax
0x140354dce  lea     rdx, [rsp+120h+var_E0]; struct std::filesystem::path *
0x140354dd3  mov     rcx, rdi; this
0x140354dd6  call    ?create_directories@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::create_directories(std::filesystem::path const &,std::error_code &)
0x140354ddb  cmp     dword ptr [rsp+120h+var_E0], r13d
0x140354de0  jnz     loc_1403550FB
0x140354de6  mov     r9, rdi
0x140354de9  cmp     qword ptr [rdi+18h], 7
0x140354dee  jbe     short loc_140354DF3
0x140354df0  mov     r9, [rdi]; Context
0x140354df3  cmp     qword ptr [rsi+18h], 7
0x140354df8  jbe     short loc_140354DFD
0x140354dfa  mov     rsi, [rsi]
0x140354dfd  lea     r8, Windows__WSX___anonymous_namespace___CabinetCallbackToExpand; MsgHandler
0x140354e04  xor     edx, edx; Reserved
0x140354e06  mov     rcx, rsi; CabinetFile
0x140354e09  call    cs:__imp_SetupIterateCabinetW
0x140354e0f  mov     rcx, [rbp+5Fh]; this
0x140354e13  test    eax, eax
0x140354e15  jz      loc_140355110
0x140354e1b  mov     [rbp+57h+ExternalFileInfo], 1
0x140354e23  mov     rdx, rdi; struct std::filesystem::path *
0x140354e26  lea     rcx, [rbp+57h+var_C0]; this
0x140354e2a  call    ??0recursive_directory_iterator@filesystem@std@@QEAA@AEBVpath@12@@Z; std::filesystem::recursive_directory_iterator::recursive_directory_iterator(std::filesystem::path const &)
0x140354e2f  nop
0x140354e30  xorps   xmm0, xmm0
0x140354e33  movups  [rbp+57h+var_D0], xmm0
0x140354e37  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x140354e3b  test    rbx, rbx
0x140354e3e  jz      short loc_140354E48
0x140354e40  lock inc dword ptr [rbx+8]
0x140354e44  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x140354e48  movaps  xmm0, [rbp+57h+var_C0]
0x140354e4c  movdqa  [rbp+57h+var_D0], xmm0
0x140354e51  test    rbx, rbx
0x140354e54  jz      short loc_140354E5E
0x140354e56  lock inc dword ptr [rbx+8]
0x140354e5a  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x140354e5e  xorps   xmm1, xmm1
0x140354e61  movdqu  [rbp+57h+var_98], xmm1
0x140354e66  test    rbx, rbx
0x140354e69  jz      short loc_140354EA3
0x140354e6b  mov     eax, r15d
0x140354e6e  lock xadd [rbx+8], eax
0x140354e73  add     eax, r15d
0x140354e76  jnz     short loc_140354EA3
0x140354e78  mov     rax, [rbx]
0x140354e7b  mov     rcx, rbx
0x140354e7e  mov     rax, [rax]
0x140354e81  call    _guard_dispatch_icall
0x140354e86  mov     eax, r15d
0x140354e89  lock xadd [rbx+0Ch], eax
0x140354e8e  add     eax, r15d
0x140354e91  jnz     short loc_140354EA3
0x140354e93  mov     rax, [rbx]
0x140354e96  mov     rcx, rbx
0x140354e99  mov     rax, [rax+8]
0x140354e9d  call    _guard_dispatch_icall
0x140354ea2  nop
0x140354ea3  mov     rbx, qword ptr [rbp+57h+var_D0]
0x140354ea7  test    rbx, rbx
0x140354eaa  jz      loc_140354FA8
0x140354eb0  mov     r8d, 3
0x140354eb6  lea     rdx, [rsp+120h+var_E0]
0x140354ebb  mov     rcx, rbx
0x140354ebe  call    ?_Get_any_status@directory_entry@filesystem@std@@AEBA?AU_File_status_and_error@23@W4__std_fs_stats_flags@@@Z; std::filesystem::directory_entry::_Get_any_status(__std_fs_stats_flags)
0x140354ec3  mov     rax, qword ptr [rsp+120h+var_E0]
0x140354ec8  mov     edx, dword ptr [rsp+120h+var_D8]
0x140354ecc  test    edx, edx
0x140354ece  jz      short loc_140354EDF
0x140354ed0  lea     ecx, [rax-1]
0x140354ed3  test    ecx, 0FFFFFFF7h
0x140354ed9  jnz     loc_140355088
0x140354edf  cmp     eax, 2
0x140354ee2  jnz     loc_140354F92
0x140354ee8  lea     rcx, [rbx+20h]
0x140354eec  cmp     qword ptr [rbx+38h], 7
0x140354ef1  jbe     short loc_140354EF6
0x140354ef3  mov     rcx, [rcx]; lpFileName
0x140354ef6  mov     [rsp+120h+hTemplateFile], r13; hTemplateFile
0x140354efb  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140354f03  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x140354f0b  xor     r9d, r9d; lpSecurityAttributes
0x140354f0e  mov     edx, 0C0000000h; dwDesiredAccess
0x140354f13  lea     r8d, [r9+1]; dwShareMode
0x140354f17  call    cs:__imp_CreateFileW
0x140354f1d  mov     rbx, rax
0x140354f20  dec     rax
0x140354f23  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140354f27  ja      short loc_140354F6A
0x140354f29  mov     r9d, 8; Length
0x140354f2f  lea     r8, [rbp+57h+ExternalFileInfo]; ExternalFileInfo
0x140354f33  lea     edx, [r9-6]; Provider
0x140354f37  mov     rcx, rbx; FileHandle
0x140354f3a  call    cs:__imp_WofSetFileDataLocation
0x140354f40  mov     rcx, [rbp+5Fh]; this
0x140354f44  mov     [rsp+120h+dwFlagsAndAttributes], 80070158h; unsigned int
0x140354f4c  mov     [rsp+120h+dwCreationDisposition], 1; int
0x140354f54  mov     r9d, eax; char *
0x140354f57  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354f5e  mov     edx, 19Ch; void *
0x140354f63  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x140354f68  jmp     short loc_140354F89
0x140354f6a  mov     rcx, [rbp+5Fh]; this
0x140354f6e  lea     r8, aCW1SSrcOrchest_8; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140354f75  mov     edx, 197h; void *
0x140354f7a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140354f7f  lea     rax, [rbx-1]
0x140354f83  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140354f87  ja      short loc_140354F92
0x140354f89  mov     rcx, rbx; hObject
0x140354f8c  call    cs:__imp_CloseHandle
0x140354f92  lea     rcx, [rbp+57h+var_D0]
0x140354f96  call    ?_Advance_and_reset_if_no_more_files@_Recursive_dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Recursive_dir_enum_impl@filesystem@std@@@3@@Z; std::filesystem::_Recursive_dir_enum_impl::_Advance_and_reset_if_no_more_files(std::shared_ptr<std::filesystem::_Recursive_dir_enum_impl> &)
0x140354f9b  test    eax, eax
0x140354f9d  jnz     loc_140355099
0x140354fa3  jmp     loc_140354EA3
0x140354fa8  mov     rbx, qword ptr [rbp+57h+var_D0+8]
0x140354fac  test    rbx, rbx
0x140354faf  jz      short loc_140354FE9
0x140354fb1  mov     eax, r15d
0x140354fb4  lock xadd [rbx+8], eax
0x140354fb9  add     eax, r15d
0x140354fbc  jnz     short loc_140354FE9
0x140354fbe  mov     rax, [rbx]
0x140354fc1  mov     rcx, rbx
0x140354fc4  mov     rax, [rax]
0x140354fc7  call    _guard_dispatch_icall
0x140354fcc  mov     eax, r15d
0x140354fcf  lock xadd [rbx+0Ch], eax
0x140354fd4  add     eax, r15d
0x140354fd7  jnz     short loc_140354FE9
0x140354fd9  mov     rax, [rbx]
0x140354fdc  mov     rcx, rbx
0x140354fdf  mov     rax, [rax+8]
0x140354fe3  call    _guard_dispatch_icall
0x140354fe8  nop
0x140354fe9  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x140354fed  test    rbx, rbx
0x140354ff0  jz      short loc_14035502A
0x140354ff2  mov     eax, r15d
0x140354ff5  lock xadd [rbx+8], eax
0x140354ffa  add     eax, r15d
0x140354ffd  jnz     short loc_14035502A
0x140354fff  mov     rax, [rbx]
0x140355002  mov     rcx, rbx
0x140355005  mov     rax, [rax]
0x140355008  call    _guard_dispatch_icall
0x14035500d  mov     eax, r15d
0x140355010  lock xadd [rbx+0Ch], eax
0x140355015  add     eax, r15d
0x140355018  jnz     short loc_14035502A
0x14035501a  mov     rax, [rbx]
0x14035501d  mov     rcx, rbx
0x140355020  mov     rax, [rax+8]
0x140355024  call    _guard_dispatch_icall
0x140355029  nop
0x14035502a  lea     rcx, [rbp+57h+var_A8]
0x14035502e  call    wil__details__lambda_call__Windows__WSX__ExperienceUpdateHandler__Install____2____lambda_1______lambda_call__Windows__WSX__ExperienceUpdateHandler__Install____2____lambda_1___
0x140355033  nop
0x140355034  lea     rcx, [rbp+57h+var_60]; this
0x140355038  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14035503d  cmp     [rbp+57h+var_68], r13b
0x140355041  jz      short loc_14035505B
0x140355043  mov     rbx, [rbp+57h+lpMem]
0x140355047  call    cs:__imp_GetProcessHeap
0x14035504d  mov     r8, rbx; lpMem
0x140355050  xor     edx, edx; dwFlags
0x140355052  mov     rcx, rax; hHeap
0x140355055  call    cs:__imp_HeapFree
0x14035505b  mov     rcx, [rbp+57h+var_30]
  ... truncated ...
```

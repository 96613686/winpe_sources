# UpdateManager::StartWorkerIfNeeded(void)

- ea: `0x14007e87c`
- end: `0x14007ed94`
- name: `?StartWorkerIfNeeded@UpdateManager@@AEAAXXZ`
- size: `1304`
- prototype: `void __fastcall(UpdateManager *__hidden this)`
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140082af0`
- `0x14008a974`
- `0x1400971d0`

## callees

- `0x140040184`
- `0x1400433b0`
- `0x140057a20`
- `0x14007e87c`
- `0x1400a4c60`
- `0x1400a516c`
- `0x1400abd70`
- `0x1400b4f14`
- `0x1400b8788`
- `0x1400c6774`
- `0x1400c679c`
- `0x14012d7d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140378b3e`
- `0x140379070`
- `0x1403790d8`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007ec8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007ec8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ecc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ecd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ecc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14007ecd4`

## string_xrefs

- `0x14007ed0b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14007e8e1`: `StartWorkerIfNeeded:  Acquiring lock on m_workThreadMutex to check if starting a new worker thread is allowed`
- `0x14007e9f7`: `UpdateManagerWorkThreadWaitInMinutes`
- `0x14007e98b`: `StartWorkerIfNeeded:  Wait for m_workThreadCondition to be signaled when any existing thread has fully exited`
- `0x14007eb35`: `StartWorkerIfNeeded:  Re-acquired lock on m_workThreadMutex`
- `0x14007ed1d`: `UpdateManager timed out waiting for the work thread to exit`
- `0x14007ec5c`: `StartWorkerIfNeeded:  Signaled m_workThreadCondition, and releasing lock on m_workThreadMutex as the lock is going out of scope`
- `0x14007ec20`: `StartWorkerIfNeeded:  Release lock on m_workThreadMutex and wait for m_workThreadCondition to be signaled to indicate the background thread has started`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall UpdateManager::StartWorkerIfNeeded(__m128i *this)
{
  __m128i *v2; // rbx
  __int64 System; // rax
  __int64 v4; // rcx
  __int64 (__fastcall *v5)(__int64, __m128i *, _QWORD **); // r14
  __int16 *traits_2_unsigned_short; // rax
  const char *v7; // r9
  __int64 v8; // r11
  __int64 v9; // rax
  int v10; // r15d
  volatile signed __int32 *v11; // r14
  volatile signed __int32 *v12; // r14
  _QWORD *v13; // r15
  char v14; // al
  __int64 v15; // rdx
  __int64 v16; // rdx
  signed __int32 v17; // eax
  signed __int32 v18; // ett
  __m128i v19; // xmm6
  _QWORD *v20; // rax
  __int64 v21; // rcx
  bool v22; // zf
  __m128i v23; // [rsp+38h] [rbp-59h] BYREF
  __m128i pExceptionObject; // [rsp+48h] [rbp-49h] BYREF
  __int64 v25; // [rsp+68h] [rbp-29h] BYREF
  volatile signed __int32 *v26; // [rsp+70h] [rbp-21h]
  __m128i *v27; // [rsp+78h] [rbp-19h]
  _QWORD *v28; // [rsp+80h] [rbp-11h] BYREF
  __int128 v29; // [rsp+88h] [rbp-9h] BYREF
  HANDLE hObject[2]; // [rsp+98h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v2 = this + 58;
  v27 = this + 58;
  if ( (unsigned int)mtx_do_lock(&this[58], 0) )
    std::_Throw_Cpp_error(5);
  if ( v2[4].m128i_i32[3] == 0x7FFFFFFF )
  {
    v2[4].m128i_i32[3] = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Acquiring lock on m_workThreadMutex to check if starting a new worke"
                               "r thread is allowed";
  v23.m128i_i64[1] = 109;
  SystemInterface::LogVerbose<>(&v23);
  v29 = (unsigned __int64)&this[63];
  if ( (unsigned int)mtx_do_lock(&this[63], 0) )
    std::_Throw_Cpp_error(5);
  if ( this[67].m128i_i32[3] == 0x7FFFFFFF )
  {
    this[67].m128i_i32[3] = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v29) = 1;
  v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Lock acquired";
  v23.m128i_i64[1] = 35;
  SystemInterface::LogVerbose<>(&v23);
  if ( !this[73].m128i_i8[10] && !this[74].m128i_i8[4] && this[73].m128i_i8[11] )
  {
    v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Wait for m_workThreadCondition to be signaled when any existing th"
                                 "read has fully exited";
    v23.m128i_i64[1] = 109;
    SystemInterface::LogVerbose<>(&v23);
    System = SystemInterface::Providers::GetSystem(&pExceptionObject);
    v4 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v5 = *(__int64 (__fastcall **)(__int64, __m128i *, _QWORD **))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL))(
                                                                                  v4,
                                                                                  &v25)
                                                                 + 56LL);
    LODWORD(v28) = 30;
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"UpdateManagerWorkThreadWaitInMinutes",
                                           word_1403FF87A,
                                           0);
    if ( traits_2_unsigned_short == word_1403FF87A
      || (v9 = ((char *)traits_2_unsigned_short - (char *)L"UpdateManagerWorkThreadWaitInMinutes") >> 1, v9 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v7);
    }
    v23.m128i_i64[0] = (__int64)L"UpdateManagerWorkThreadWaitInMinutes";
    v23.m128i_i64[1] = v9;
    v10 = v5(v8, &v23, &v28);
    v11 = v26;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    v12 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    LODWORD(v28) = v10;
    v13 = (_QWORD *)std::_To_absolute_time<int,std::ratio<60,1>>(&v23, &v28);
    while ( !this[73].m128i_i8[9] )
    {
      std::chrono::steady_clock::now(&v28);
      if ( (_QWORD *)*v13 == v28 )
        goto LABEL_24;
      v14 = 1;
      if ( *v13 < (__int64)v28 )
        v14 = -1;
      if ( v14 <= 0 )
LABEL_24:
        v15 = 0;
      else
        v15 = *v13 - (_QWORD)v28;
      v25 = v15;
      if ( (unsigned int)std::condition_variable_any::wait_for<std::unique_lock<std::recursive_mutex>,__int64,std::ratio<1,1000000000>>(
                           &this[68],
                           &v29,
                           &v25) == 1 )
      {
        if ( !this[73].m128i_i8[9] )
        {
          std::runtime_error::runtime_error(
            (std::runtime_error *)&pExceptionObject,
            "UpdateManager timed out waiting for the work thread to exit");
          throw (std::runtime_error *)&pExceptionObject;
        }
        break;
      }
    }
    v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Re-acquired lock on m_workThreadMutex";
    v23.m128i_i64[1] = 59;
    pExceptionObject = v23;
    SystemInterface::LogVerbose<>(&pExceptionObject);
    this[73].m128i_i8[8] = 0;
    v23 = 0;
    v16 = this->m128i_i64[1];
    if ( !v16 )
LABEL_49:
      std::_Throw_bad_weak_ptr();
    v17 = *(_DWORD *)(v16 + 8);
    do
    {
      if ( !v17 )
        goto LABEL_49;
      v18 = v17;
      v17 = _InterlockedCompareExchange((volatile signed __int32 *)(v16 + 8), v17 + 1, v17);
    }
    while ( v18 != v17 );
    v23 = *this;
    v19 = v23;
    pExceptionObject = v23;
    v23 = 0;
    v20 = operator new(0x10u);
    *v20 = v19.m128i_i64[0];
    v20[1] = _mm_srli_si128(v19, 8).m128i_u64[0];
    pExceptionObject = 0;
    v28 = v20;
    hObject[0] = (HANDLE)o__beginthreadex_0(
                           0,
                           0,
                           std::thread::_Invoke_std::tuple__UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2____0_,
                           v20,
                           0);
    if ( !hObject[0] )
    {
      LODWORD(hObject[1]) = 0;
      std::_Throw_Cpp_error(6);
    }
    v28 = 0;
    std::unique_ptr_std::tuple__UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2____std::default_delete_std::tuple__UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2_______::_unique_ptr_std::tuple__UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2____std::default_delete_std::tuple__UpdateManager::StartWorkerIfNeeded_::_2_::_lambda_2_______(&v28);
    v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Release lock on m_workThreadMutex and wait for m_workThreadConditi"
                                 "on to be signaled to indicate the background thread has started";
    v23.m128i_i64[1] = 151;
    pExceptionObject = v23;
    SystemInterface::LogVerbose<>(&pExceptionObject);
    while ( !this[73].m128i_i8[8] )
      std::condition_variable_any::wait<std::unique_lock<std::recursive_mutex>>(&this[68], &v29);
    v23.m128i_i64[0] = (__int64)L"StartWorkerIfNeeded:  Signaled m_workThreadCondition, and releasing lock on m_workThread"
                                 "Mutex as the lock is going out of scope";
    v23.m128i_i64[1] = 127;
    pExceptionObject = v23;
    SystemInterface::LogVerbose<>(&pExceptionObject);
    if ( !LODWORD(hObject[1]) || !CloseHandle(hObject[0]) )
      std::_Throw_Cpp_error(1);
    *(_OWORD *)hObject = 0;
  }
  if ( BYTE8(v29) )
  {
    v21 = v29;
    v22 = (*(_DWORD *)(v29 + 76))-- == 1;
    if ( v22 )
    {
      *(_DWORD *)(v21 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v21 + 16));
    }
  }
  v22 = v2[4].m128i_i32[3]-- == 1;
  if ( v22 )
  {
    v2[4].m128i_i32[2] = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)&v2[1]);
  }
}

```

## disassembly

```asm
0x14007e87c  mov     rax, rsp
0x14007e87f  mov     [rax+10h], rbx
0x14007e883  mov     [rax+18h], rsi
0x14007e887  push    rbp
0x14007e888  push    rdi
0x14007e889  push    r12
0x14007e88b  push    r14
0x14007e88d  push    r15
0x14007e88f  lea     rbp, [rax-5Fh]
0x14007e893  sub     rsp, 0C0h
0x14007e89a  movaps  xmmword ptr [rax-38h], xmm6
0x14007e89e  mov     rax, cs:__security_cookie
0x14007e8a5  xor     rax, rsp
0x14007e8a8  mov     [rbp+57h+var_40], rax
0x14007e8ac  mov     rsi, rcx
0x14007e8af  xor     r12d, r12d
0x14007e8b2  lea     rbx, [rcx+3A0h]
0x14007e8b9  mov     [rbp+57h+var_70], rbx
0x14007e8bd  xor     edx, edx
0x14007e8bf  mov     rcx, rbx
0x14007e8c2  call    mtx_do_lock
0x14007e8c7  test    eax, eax
0x14007e8c9  jnz     loc_14007ED44
0x14007e8cf  mov     eax, [rbx+4Ch]
0x14007e8d2  mov     r14d, 7FFFFFFFh
0x14007e8d8  cmp     eax, r14d
0x14007e8db  jz      loc_14007ED4F
0x14007e8e1  lea     rax, aStartworkerifn_1; "StartWorkerIfNeeded:  Acquiring lock on"...
0x14007e8e8  mov     qword ptr [rbp+57h+var_B0], rax
0x14007e8ec  lea     r15d, [r12+6Dh]
0x14007e8f1  mov     qword ptr [rbp+57h+var_B0+8], r15
0x14007e8f5  movaps  xmm0, [rbp+57h+var_B0]
0x14007e8f9  movdqa  [rbp+57h+var_B0], xmm0
0x14007e8fe  lea     rcx, [rbp+57h+var_B0]
0x14007e902  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007e907  xorps   xmm0, xmm0
0x14007e90a  movups  [rbp+57h+var_60], xmm0
0x14007e90e  lea     rdi, [rsi+3F0h]
0x14007e915  mov     qword ptr [rbp+57h+var_60], rdi
0x14007e919  mov     byte ptr [rbp+57h+var_60+8], r12b
0x14007e91d  xor     edx, edx
0x14007e91f  mov     rcx, rdi
0x14007e922  call    mtx_do_lock
0x14007e927  test    eax, eax
0x14007e929  jnz     loc_14007ED5F
0x14007e92f  mov     eax, [rdi+4Ch]
0x14007e932  cmp     eax, r14d
0x14007e935  jz      loc_14007ED6A
0x14007e93b  mov     byte ptr [rbp+57h+var_60+8], 1
0x14007e93f  lea     rax, aStartworkerifn_2; "StartWorkerIfNeeded:  Lock acquired"
0x14007e946  mov     qword ptr [rbp+57h+var_B0], rax
0x14007e94a  mov     qword ptr [rbp+57h+var_B0+8], 23h ; '#'
0x14007e952  movaps  xmm0, [rbp+57h+var_B0]
0x14007e956  movdqa  [rbp+57h+var_B0], xmm0
0x14007e95b  lea     rcx, [rbp+57h+var_B0]
0x14007e95f  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007e964  cmp     [rsi+49Ah], r12b
0x14007e96b  jnz     loc_14007ECA7
0x14007e971  cmp     [rsi+4A4h], r12b
0x14007e978  jnz     loc_14007ECA7
0x14007e97e  cmp     [rsi+49Bh], r12b
0x14007e985  jz      loc_14007ECA7
0x14007e98b  lea     rax, aStartworkerifn_4; "StartWorkerIfNeeded:  Wait for m_workTh"...
0x14007e992  mov     qword ptr [rbp+57h+var_B0], rax
0x14007e996  mov     qword ptr [rbp+57h+var_B0+8], r15
0x14007e99a  movaps  xmm0, [rbp+57h+var_B0]
0x14007e99e  movdqa  [rbp+57h+var_B0], xmm0
0x14007e9a3  lea     rcx, [rbp+57h+var_B0]
0x14007e9a7  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007e9ac  lea     rcx, [rbp+57h+pExceptionObject]
0x14007e9b0  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x14007e9b5  nop
0x14007e9b6  mov     rdx, [rax]
0x14007e9b9  mov     rax, [rdx+8]
0x14007e9bd  movsxd  rcx, dword ptr [rax+4]
0x14007e9c1  add     rdx, 8
0x14007e9c5  add     rcx, rdx
0x14007e9c8  mov     rax, [rcx]
0x14007e9cb  lea     rdx, [rbp+57h+var_80]
0x14007e9cf  mov     rax, [rax+28h]
0x14007e9d3  call    _guard_dispatch_icall
0x14007e9d8  nop
0x14007e9d9  mov     r11, [rax]
0x14007e9dc  mov     rax, [r11]
0x14007e9df  mov     r14, [rax+38h]
0x14007e9e3  mov     dword ptr [rbp+57h+var_68], 1Eh
0x14007e9ea  xor     r8d, r8d
0x14007e9ed  lea     rdi, word_1403FF87A
0x14007e9f4  mov     rdx, rdi
0x14007e9f7  lea     r15, aUpdatemanagerw; "UpdateManagerWorkThreadWaitInMinutes"
0x14007e9fe  mov     rcx, r15
0x14007ea01  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14007ea06  cmp     rax, rdi
0x14007ea09  jz      loc_14007ED07
0x14007ea0f  sub     rax, r15
0x14007ea12  sar     rax, 1
0x14007ea15  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14007ea19  cmp     rax, rdi
0x14007ea1c  jz      loc_14007ED07
0x14007ea22  mov     qword ptr [rbp+57h+var_B0], r15
0x14007ea26  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14007ea2a  movaps  xmm0, [rbp+57h+var_B0]
0x14007ea2e  movdqa  [rbp+57h+var_B0], xmm0
0x14007ea33  lea     r8, [rbp+57h+var_68]
0x14007ea37  lea     rdx, [rbp+57h+var_B0]
0x14007ea3b  mov     rcx, r11
0x14007ea3e  mov     rax, r14
0x14007ea41  call    _guard_dispatch_icall
0x14007ea46  mov     r15d, eax
0x14007ea49  mov     r14, [rbp+57h+var_78]
0x14007ea4d  test    r14, r14
0x14007ea50  jz      short loc_14007EA88
0x14007ea52  mov     ecx, edi
0x14007ea54  lock xadd [r14+8], ecx
0x14007ea5a  add     ecx, edi
0x14007ea5c  jnz     short loc_14007EA88
0x14007ea5e  mov     rdx, [r14]
0x14007ea61  mov     rcx, r14
0x14007ea64  mov     rax, [rdx]
0x14007ea67  call    _guard_dispatch_icall
0x14007ea6c  mov     eax, edi
0x14007ea6e  lock xadd [r14+0Ch], eax
0x14007ea74  add     eax, edi
0x14007ea76  jnz     short loc_14007EA88
0x14007ea78  mov     rax, [r14]
0x14007ea7b  mov     rcx, r14
0x14007ea7e  mov     rax, [rax+8]
0x14007ea82  call    _guard_dispatch_icall
0x14007ea87  nop
0x14007ea88  mov     r14, qword ptr [rbp+57h+pExceptionObject+8]
0x14007ea8c  test    r14, r14
0x14007ea8f  jz      short loc_14007EAC6
0x14007ea91  mov     eax, edi
0x14007ea93  lock xadd [r14+8], eax
0x14007ea99  add     eax, edi
0x14007ea9b  jnz     short loc_14007EAC6
0x14007ea9d  mov     rax, [r14]
0x14007eaa0  mov     rcx, r14
0x14007eaa3  mov     rax, [rax]
0x14007eaa6  call    _guard_dispatch_icall
0x14007eaab  mov     eax, edi
0x14007eaad  lock xadd [r14+0Ch], eax
0x14007eab3  add     eax, edi
0x14007eab5  jnz     short loc_14007EAC6
0x14007eab7  mov     rax, [r14]
0x14007eaba  mov     rcx, r14
0x14007eabd  mov     rax, [rax+8]
0x14007eac1  call    _guard_dispatch_icall
0x14007eac6  lea     r14, [rsi+440h]
0x14007eacd  mov     dword ptr [rbp+57h+var_68], r15d
0x14007ead1  lea     rdx, [rbp+57h+var_68]
0x14007ead5  lea     rcx, [rbp+57h+var_B0]
0x14007ead9  call    ??$_To_absolute_time@HU?$ratio@$0DM@$00@std@@@std@@YA?A_PAEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@0@@Z
0x14007eade  mov     r15, rax
0x14007eae1  jmp     short loc_14007EB2C
0x14007eae3  lea     rcx, [rbp+57h+var_68]
0x14007eae7  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x14007eaec  mov     rdx, [r15]
0x14007eaef  mov     rcx, [rbp+57h+var_68]
0x14007eaf3  cmp     rdx, rcx
0x14007eaf6  jz      short loc_14007EB10
0x14007eaf8  mov     eax, 1
0x14007eafd  mov     r8d, 0FFh
0x14007eb03  cmovl   eax, r8d
0x14007eb07  test    al, al
0x14007eb09  jle     short loc_14007EB10
0x14007eb0b  sub     rdx, rcx
0x14007eb0e  jmp     short loc_14007EB13
0x14007eb10  mov     rdx, r12
0x14007eb13  mov     [rbp+57h+var_80], rdx
0x14007eb17  lea     r8, [rbp+57h+var_80]
0x14007eb1b  lea     rdx, [rbp+57h+var_60]
0x14007eb1f  mov     rcx, r14
0x14007eb22  call    ??$wait_for@V?$unique_lock@Vrecursive_mutex@std@@@std@@_JU?$ratio@$00$0DLJKMKAA@@2@@condition_variable_any@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vrecursive_mutex@std@@@1@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@1@@Z; std::condition_variable_any::wait_for<std::unique_lock<std::recursive_mutex>,__int64,std::ratio<1,1000000000>>(std::unique_lock<std::recursive_mutex> &,std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x14007eb27  cmp     eax, 1
0x14007eb2a  jz      short loc_14007EB7B
0x14007eb2c  cmp     [rsi+499h], r12b
0x14007eb33  jz      short loc_14007EAE3
0x14007eb35  lea     rax, aStartworkerifn_3; "StartWorkerIfNeeded:  Re-acquired lock "...
0x14007eb3c  mov     qword ptr [rbp+57h+var_B0], rax
0x14007eb40  mov     qword ptr [rbp+57h+var_B0+8], 3Bh ; ';'
0x14007eb48  movaps  xmm0, [rbp+57h+var_B0]
0x14007eb4c  movdqa  [rbp+57h+pExceptionObject], xmm0
0x14007eb51  lea     rcx, [rbp+57h+pExceptionObject]
0x14007eb55  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007eb5a  mov     [rsi+498h], r12b
0x14007eb61  xorps   xmm0, xmm0
0x14007eb64  movdqa  [rbp+57h+var_B0], xmm0
0x14007eb69  mov     rdx, [rsi+8]
0x14007eb6d  test    rdx, rdx
0x14007eb70  jz      loc_14007ED3E
0x14007eb76  mov     eax, [rdx+8]
0x14007eb79  jmp     short loc_14007EB94
0x14007eb7b  cmp     [rsi+499h], r12b
0x14007eb82  jz      loc_14007ED1D
0x14007eb88  jmp     short loc_14007EB35
0x14007eb8a  lea     ecx, [rax+1]
0x14007eb8d  lock cmpxchg [rdx+8], ecx
0x14007eb92  jz      short loc_14007EB9E
0x14007eb94  test    eax, eax
0x14007eb96  jz      loc_14007ED3E
0x14007eb9c  jmp     short loc_14007EB8A
0x14007eb9e  mov     rax, [rsi]
0x14007eba1  mov     qword ptr [rbp+57h+var_B0], rax
0x14007eba5  mov     rax, [rsi+8]
0x14007eba9  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14007ebad  movaps  xmm6, [rbp+57h+var_B0]
0x14007ebb1  movdqa  [rbp+57h+pExceptionObject], xmm6
0x14007ebb6  xorps   xmm0, xmm0
0x14007ebb9  movdqa  [rbp+57h+var_B0], xmm0
0x14007ebbe  mov     ecx, 10h; Size
0x14007ebc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14007ebc8  movq    qword ptr [rax], xmm6
0x14007ebcd  psrldq  xmm6, 8
0x14007ebd2  movq    qword ptr [rax+8], xmm6
0x14007ebd8  xorps   xmm0, xmm0
0x14007ebdb  movdqa  [rbp+57h+pExceptionObject], xmm0
0x14007ebe0  mov     [rbp+57h+var_68], rax
0x14007ebe4  lea     rcx, [rbp+57h+hObject+8]
0x14007ebe8  mov     [rsp+0E0h+var_B8], rcx
0x14007ebed  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x14007ebf2  mov     r9, rax
0x14007ebf5  lea     r8, std__thread___Invoke_std__tuple__UpdateManager__StartWorkerIfNeeded____2____lambda_2____0_
0x14007ebfc  xor     edx, edx
0x14007ebfe  xor     ecx, ecx
0x14007ec00  call    _o__beginthreadex_0
0x14007ec05  mov     [rbp+57h+hObject], rax
0x14007ec09  test    rax, rax
0x14007ec0c  jz      loc_14007ED85
0x14007ec12  mov     [rbp+57h+var_68], r12
0x14007ec16  lea     rcx, [rbp+57h+var_68]
0x14007ec1a  call    std__unique_ptr_std__tuple__UpdateManager__StartWorkerIfNeeded____2____lambda_2____std__default_delete_std__tuple__UpdateManager__StartWorkerIfNeeded____2____lambda_2__________unique_ptr_std__tuple__UpdateManager__StartWorkerIfNeeded____2____lambda_2____std__default_delete_std__tuple__UpdateManager__StartWorkerIfNeeded____2____lambda_2_______
0x14007ec1f  nop
0x14007ec20  lea     rax, aStartworkerifn; "StartWorkerIfNeeded:  Release lock on m"...
0x14007ec27  mov     qword ptr [rbp+57h+var_B0], rax
0x14007ec2b  mov     qword ptr [rbp+57h+var_B0+8], 97h
0x14007ec33  movaps  xmm0, [rbp+57h+var_B0]
0x14007ec37  movdqa  [rbp+57h+pExceptionObject], xmm0
0x14007ec3c  lea     rcx, [rbp+57h+pExceptionObject]
0x14007ec40  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007ec45  jmp     short loc_14007EC53
0x14007ec47  lea     rdx, [rbp+57h+var_60]
0x14007ec4b  mov     rcx, r14
0x14007ec4e  call    ??$wait@V?$unique_lock@Vrecursive_mutex@std@@@std@@@condition_variable_any@std@@QEAAXAEAV?$unique_lock@Vrecursive_mutex@std@@@1@@Z; std::condition_variable_any::wait<std::unique_lock<std::recursive_mutex>>(std::unique_lock<std::recursive_mutex> &)
0x14007ec53  cmp     [rsi+498h], r12b
0x14007ec5a  jz      short loc_14007EC47
0x14007ec5c  lea     rax, aStartworkerifn_0; "StartWorkerIfNeeded:  Signaled m_workTh"...
0x14007ec63  mov     qword ptr [rbp+57h+var_B0], rax
0x14007ec67  mov     qword ptr [rbp+57h+var_B0+8], 7Fh
0x14007ec6f  movaps  xmm0, [rbp+57h+var_B0]
0x14007ec73  movdqa  [rbp+57h+pExceptionObject], xmm0
0x14007ec78  lea     rcx, [rbp+57h+pExceptionObject]
0x14007ec7c  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14007ec81  cmp     dword ptr [rbp+57h+hObject+8], r12d
0x14007ec85  jz      loc_14007ED7A
0x14007ec8b  mov     rcx, [rbp+57h+hObject]; hObject
0x14007ec8f  call    cs:__imp_CloseHandle
0x14007ec95  test    eax, eax
0x14007ec97  jz      loc_14007ED7A
0x14007ec9d  xorps   xmm0, xmm0
0x14007eca0  movdqa  xmmword ptr [rbp+57h+hObject], xmm0
0x14007eca5  jmp     short loc_14007ECAB
0x14007eca7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14007ecab  cmp     byte ptr [rbp+57h+var_60+8], r12b
0x14007ecaf  jz      short loc_14007ECC8
0x14007ecb1  mov     rcx, qword ptr [rbp+57h+var_60]
0x14007ecb5  add     [rcx+4Ch], edi
0x14007ecb8  jnz     short loc_14007ECC8
0x14007ecba  mov     [rcx+48h], edi
0x14007ecbd  add     rcx, 10h; SRWLock
0x14007ecc1  call    cs:__imp_ReleaseSRWLockExclusive
0x14007ecc7  nop
0x14007ecc8  add     [rbx+4Ch], edi
0x14007eccb  jnz     short loc_14007ECDA
0x14007eccd  mov     [rbx+48h], edi
0x14007ecd0  lea     rcx, [rbx+10h]; SRWLock
0x14007ecd4  call    cs:__imp_ReleaseSRWLockExclusive
0x14007ecda  mov     rcx, [rbp+57h+var_40]
0x14007ecde  xor     rcx, rsp; StackCookie
0x14007ece1  call    __security_check_cookie
0x14007ece6  lea     r11, [rsp+0E0h+var_20]
0x14007ecee  mov     rbx, [r11+38h]
0x14007ecf2  mov     rsi, [r11+40h]
0x14007ecf6  movaps  xmm6, xmmword ptr [r11-10h]
0x14007ecfb  mov     rsp, r11
0x14007ecfe  pop     r15
0x14007ed00  pop     r14
0x14007ed02  pop     r12
0x14007ed04  pop     rdi
0x14007ed05  pop     rbp
0x14007ed06  retn
0x14007ed07  mov     rcx, [rbp+5Fh]; this
0x14007ed0b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14007ed12  mov     edx, 0C9h; void *
0x14007ed17  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14007ed1d  lea     rdx, aUpdatemanagerT_1; "UpdateManager timed out waiting for the"...
0x14007ed24  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14007ed28  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x14007ed2d  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14007ed34  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
  ... truncated ...
```

# UpdateManager::EndWorkThread(CancelReason)

- ea: `0x1400826a4`
- end: `0x140082ae7`
- name: `?EndWorkThread@UpdateManager@@AEAAXW4CancelReason@@@Z`
- size: `1091`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140082030`
- `0x1400831b4`

## callees

- `0x140040184`
- `0x1400433b0`
- `0x140057a20`
- `0x1400826a4`
- `0x1400a4c60`
- `0x1400a516c`
- `0x1400b55b8`
- `0x1400b8788`
- `0x1400c679c`
- `0x1400c7188`
- `0x14012d7d8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400827b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140082a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400827b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140082a2c`

## string_xrefs

- `0x140082a9b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1400826d6`: `Ending work thread`
- `0x14008274d`: `EndWorkThread:  Lock acquired on m_workThreadMutex`
- `0x1400826f5`: `EndWorkThread:  Acquiring lock on m_workThreadMutex to check if background thread is running`
- `0x1400827da`: `EndWorkThread:  Calling notify_all on m_workThreadCondition`
- `0x1400827b9`: `EndWorkThread:  Releasing lock on m_workThreadMutex`
- `0x1400828a7`: `EndWorkThreadTimeout`
- `0x140082802`: `EndWorkThread:  Acquiring lock on m_workThreadMutex before waiting for background thread to exit`
- `0x140082a76`: `UpdateManager::EndWorkThread timed out waiting for thread to exit`
- `0x14008296d`: `EndWorkThread:  Releasing lock on m_workThreadMutex and waiting on m_workThreadCondition until m_workThreadEnded is set to true`
- `0x140082a32`: `EndWorkThread:  Releasing lock on m_workThreadMutex, work thread has ended`
- `0x1400829f5`: `EndWorkThread:  Signaled m_workThreadCondition, reacquiring lock on m_workThreadMutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UpdateManager::EndWorkThread(__int64 a1, int a2)
{
  bool v4; // r14
  char v5; // di
  char IsEnabled; // al
  char v7; // cl
  bool v8; // zf
  __int64 System; // rax
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(__int64, const wchar_t **, _QWORD *); // rbx
  __int16 *traits_2_unsigned_short; // rax
  const char *v13; // r9
  __int64 v14; // r11
  __int64 v15; // rax
  int v16; // r15d
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  _QWORD *v19; // rbx
  __int64 v20; // rdx
  int v21; // eax
  char v22; // cl
  __int64 v23; // rcx
  _QWORD v25[2]; // [rsp+20h] [rbp-39h] BYREF
  const wchar_t *v26; // [rsp+30h] [rbp-29h] BYREF
  __int64 v27; // [rsp+38h] [rbp-21h]
  __int64 v28; // [rsp+40h] [rbp-19h] BYREF
  volatile signed __int32 *v29; // [rsp+48h] [rbp-11h]
  _BYTE pExceptionObject[8]; // [rsp+50h] [rbp-9h] BYREF
  volatile signed __int32 *v31; // [rsp+58h] [rbp-1h]
  __int128 v32; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *(_QWORD *)&v32 = L"Ending work thread";
  *((_QWORD *)&v32 + 1) = 18;
  SystemInterface::LogVerbose<>(&v32);
  v4 = 0;
  *(_QWORD *)&v32 = L"EndWorkThread:  Acquiring lock on m_workThreadMutex to check if background thread is running";
  *((_QWORD *)&v32 + 1) = 92;
  SystemInterface::LogVerbose<>(&v32);
  v32 = (unsigned __int64)(a1 + 1008);
  if ( (unsigned int)mtx_do_lock(a1 + 1008, 0) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 1084) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 1084) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v5 = 1;
  BYTE8(v32) = 1;
  v26 = L"EndWorkThread:  Lock acquired on m_workThreadMutex";
  v27 = 50;
  SystemInterface::LogVerbose<>(&v26);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458>::GetImpl'::`2'::impl);
  v7 = *(_BYTE *)(a1 + 1178);
  if ( IsEnabled )
  {
    v4 = v7 != 0;
  }
  else
  {
    if ( !v7 )
      goto LABEL_8;
    v4 = 1;
  }
  LODWORD(v25[0]) = a2;
  BYTE4(v25[0]) = 1;
  *(_QWORD *)(a1 + 1184) = v25[0];
LABEL_8:
  v8 = (*(_DWORD *)(a1 + 1084))-- == 1;
  if ( v8 )
  {
    *(_DWORD *)(a1 + 1080) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 1024));
  }
  *(_QWORD *)&v32 = L"EndWorkThread:  Releasing lock on m_workThreadMutex";
  *((_QWORD *)&v32 + 1) = 51;
  SystemInterface::LogVerbose<>(&v32);
  if ( v4 )
  {
    *(_QWORD *)&v32 = L"EndWorkThread:  Calling notify_all on m_workThreadCondition";
    *((_QWORD *)&v32 + 1) = 59;
    SystemInterface::LogVerbose<>(&v32);
    std::condition_variable_any::notify_all((std::condition_variable_any *)(a1 + 1088));
  }
  v26 = L"EndWorkThread:  Acquiring lock on m_workThreadMutex before waiting for background thread to exit";
  v27 = 96;
  SystemInterface::LogVerbose<>(&v26);
  v32 = (unsigned __int64)(a1 + 1008);
  if ( (unsigned int)mtx_do_lock(a1 + 1008, 0) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 1084) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 1084) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v32) = 1;
  if ( !*(_BYTE *)(a1 + 1177) )
  {
    System = SystemInterface::Providers::GetSystem(pExceptionObject);
    v10 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v11 = *(__int64 (__fastcall **)(__int64, const wchar_t **, _QWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 40LL))(
                                                                                         v10,
                                                                                         &v28)
                                                                        + 56LL);
    LODWORD(v25[0]) = 65;
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"EndWorkThreadTimeout",
                                           word_1404002B2,
                                           0);
    if ( traits_2_unsigned_short == word_1404002B2
      || (v15 = ((char *)traits_2_unsigned_short - (char *)L"EndWorkThreadTimeout") >> 1, v15 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v13);
    }
    v26 = L"EndWorkThreadTimeout";
    v27 = v15;
    v16 = v11(v14, &v26, v25);
    v17 = v29;
    if ( v29 )
    {
      if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    v18 = v31;
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v26 = L"EndWorkThread:  Releasing lock on m_workThreadMutex and waiting on m_workThreadCondition until m_workThreadEnd"
           "ed is set to true";
    v27 = 127;
    SystemInterface::LogVerbose<>(&v26);
    LODWORD(v25[0]) = v16;
    v19 = (_QWORD *)std::_To_absolute_time<int,std::ratio<60,1>>(&v26, v25);
    if ( *(_BYTE *)(a1 + 1177) )
    {
LABEL_32:
      v22 = 1;
    }
    else
    {
      while ( 1 )
      {
        std::chrono::steady_clock::now(v25);
        if ( *v19 == v25[0] || *v19 < v25[0] )
          v20 = 0;
        else
          v20 = *v19 - v25[0];
        v28 = v20;
        v21 = std::condition_variable_any::wait_for<std::unique_lock<std::recursive_mutex>,__int64,std::ratio<1,1000000000>>(
                a1 + 1088,
                &v32,
                &v28);
        v22 = *(_BYTE *)(a1 + 1177);
        if ( v21 == 1 )
          break;
        if ( v22 )
          goto LABEL_32;
      }
    }
    if ( !v22 )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "UpdateManager::EndWorkThread timed out waiting for thread to exit");
      throw (std::runtime_error *)pExceptionObject;
    }
    v26 = L"EndWorkThread:  Signaled m_workThreadCondition, reacquiring lock on m_workThreadMutex";
    v27 = 85;
    SystemInterface::LogVerbose<>(&v26);
    v5 = BYTE8(v32);
  }
  if ( v5 )
  {
    v23 = v32;
    v8 = (*(_DWORD *)(v32 + 76))-- == 1;
    if ( v8 )
    {
      *(_DWORD *)(v23 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v23 + 16));
    }
  }
  *(_QWORD *)&v32 = L"EndWorkThread:  Releasing lock on m_workThreadMutex, work thread has ended";
  *((_QWORD *)&v32 + 1) = 74;
  return SystemInterface::LogVerbose<>(&v32);
}

```

## disassembly

```asm
0x1400826a4  mov     [rsp-8+arg_8], rbx
0x1400826a9  mov     [rsp-8+arg_10], rsi
0x1400826ae  push    rbp
0x1400826af  push    rdi
0x1400826b0  push    r13
0x1400826b2  push    r14
0x1400826b4  push    r15
0x1400826b6  lea     rbp, [rsp-37h]
0x1400826bb  sub     rsp, 90h
0x1400826c2  mov     rax, cs:__security_cookie
0x1400826c9  xor     rax, rsp
0x1400826cc  mov     [rbp+57h+var_30], rax
0x1400826d0  mov     r15d, edx
0x1400826d3  mov     rsi, rcx
0x1400826d6  lea     rax, aEndingWorkThre; "Ending work thread"
0x1400826dd  mov     qword ptr [rbp+57h+var_40], rax
0x1400826e1  mov     qword ptr [rbp+57h+var_40+8], 12h
0x1400826e9  lea     rcx, [rbp+57h+var_40]
0x1400826ed  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x1400826f2  xor     r14b, r14b
0x1400826f5  lea     rax, aEndworkthreadA_0; "EndWorkThread:  Acquiring lock on m_wor"...
0x1400826fc  mov     qword ptr [rbp+57h+var_40], rax
0x140082700  mov     qword ptr [rbp+57h+var_40+8], 5Ch ; '\'
0x140082708  lea     rcx, [rbp+57h+var_40]
0x14008270c  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x140082711  xorps   xmm0, xmm0
0x140082714  movups  [rbp+57h+var_40], xmm0
0x140082718  lea     rbx, [rsi+3F0h]
0x14008271f  mov     qword ptr [rbp+57h+var_40], rbx
0x140082723  mov     byte ptr [rbp+57h+var_40+8], r14b
0x140082727  xor     edx, edx
0x140082729  mov     rcx, rbx
0x14008272c  call    mtx_do_lock
0x140082731  test    eax, eax
0x140082733  jnz     loc_140082AAD
0x140082739  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x140082740  jz      loc_140082AB8
0x140082746  lea     edi, [rax+1]
0x140082749  mov     byte ptr [rbp+57h+var_40+8], dil
0x14008274d  lea     rax, aEndworkthreadL; "EndWorkThread:  Lock acquired on m_work"...
0x140082754  mov     [rbp+57h+var_80], rax
0x140082758  mov     [rbp+57h+var_78], 32h ; '2'
0x140082760  lea     rcx, [rbp+57h+var_80]
0x140082764  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x140082769  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458>::GetImpl(void)'::`2'::impl
0x140082770  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_WorkThreadTiming_57103458>::__private_IsEnabled(void)
0x140082775  mov     cl, [rsi+49Ah]
0x14008277b  test    al, al
0x14008277d  jz      short loc_140082787
0x14008277f  test    cl, cl
0x140082781  setnz   r14b
0x140082785  jmp     short loc_14008278E
0x140082787  test    cl, cl
0x140082789  jz      short loc_1400827A1
0x14008278b  mov     r14b, dil
0x14008278e  mov     dword ptr [rbp+57h+var_90], r15d
0x140082792  mov     byte ptr [rbp+57h+var_90+4], dil
0x140082796  mov     rax, [rbp+57h+var_90]
0x14008279a  mov     [rsi+4A0h], rax
0x1400827a1  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400827a5  add     [rbx+4Ch], r13d
0x1400827a9  jnz     short loc_1400827B9
0x1400827ab  mov     [rbx+48h], r13d
0x1400827af  lea     rcx, [rbx+10h]; SRWLock
0x1400827b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400827b9  lea     rax, aEndworkthreadR; "EndWorkThread:  Releasing lock on m_wor"...
0x1400827c0  mov     qword ptr [rbp+57h+var_40], rax
0x1400827c4  mov     qword ptr [rbp+57h+var_40+8], 33h ; '3'
0x1400827cc  lea     rcx, [rbp+57h+var_40]
0x1400827d0  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x1400827d5  test    r14b, r14b
0x1400827d8  jz      short loc_140082802
0x1400827da  lea     rax, aEndworkthreadC; "EndWorkThread:  Calling notify_all on m"...
0x1400827e1  mov     qword ptr [rbp+57h+var_40], rax
0x1400827e5  mov     qword ptr [rbp+57h+var_40+8], 3Bh ; ';'
0x1400827ed  lea     rcx, [rbp+57h+var_40]
0x1400827f1  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x1400827f6  lea     rcx, [rsi+440h]; this
0x1400827fd  call    ?notify_all@condition_variable_any@std@@QEAAXXZ; std::condition_variable_any::notify_all(void)
0x140082802  lea     rax, aEndworkthreadA; "EndWorkThread:  Acquiring lock on m_wor"...
0x140082809  mov     [rbp+57h+var_80], rax
0x14008280d  mov     [rbp+57h+var_78], 60h ; '`'
0x140082815  lea     rcx, [rbp+57h+var_80]
0x140082819  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x14008281e  xorps   xmm0, xmm0
0x140082821  movups  [rbp+57h+var_40], xmm0
0x140082825  mov     qword ptr [rbp+57h+var_40], rbx
0x140082829  mov     byte ptr [rbp+57h+var_40+8], 0
0x14008282d  xor     edx, edx
0x14008282f  mov     rcx, rbx
0x140082832  call    mtx_do_lock
0x140082837  test    eax, eax
0x140082839  jnz     loc_140082ACA
0x14008283f  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x140082846  jz      loc_140082AD5
0x14008284c  mov     byte ptr [rbp+57h+var_40+8], dil
0x140082850  cmp     [rsi+499h], al
0x140082856  jnz     loc_140082A15
0x14008285c  lea     rcx, [rbp+57h+pExceptionObject]
0x140082860  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140082865  nop
0x140082866  mov     rdx, [rax]
0x140082869  mov     rax, [rdx+8]
0x14008286d  movsxd  rcx, dword ptr [rax+4]
0x140082871  add     rdx, 8
0x140082875  add     rcx, rdx
0x140082878  mov     rax, [rcx]
0x14008287b  lea     rdx, [rbp+57h+var_70]
0x14008287f  mov     rax, [rax+28h]
0x140082883  call    _guard_dispatch_icall
0x140082888  nop
0x140082889  mov     r11, [rax]
0x14008288c  mov     rax, [r11]
0x14008288f  mov     rbx, [rax+38h]
0x140082893  mov     dword ptr [rbp+57h+var_90], 41h ; 'A'
0x14008289a  xor     r8d, r8d
0x14008289d  lea     r14, word_1404002B2
0x1400828a4  mov     rdx, r14
0x1400828a7  lea     r15, aEndworkthreadt; "EndWorkThreadTimeout"
0x1400828ae  mov     rcx, r15
0x1400828b1  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1400828b6  cmp     rax, r14
0x1400828b9  jz      loc_140082A97
0x1400828bf  sub     rax, r15
0x1400828c2  sar     rax, 1
0x1400828c5  cmp     rax, r13
0x1400828c8  jz      loc_140082A97
0x1400828ce  mov     [rbp+57h+var_80], r15
0x1400828d2  mov     [rbp+57h+var_78], rax
0x1400828d6  lea     r8, [rbp+57h+var_90]
0x1400828da  lea     rdx, [rbp+57h+var_80]
0x1400828de  mov     rcx, r11
0x1400828e1  mov     rax, rbx
0x1400828e4  call    _guard_dispatch_icall
0x1400828e9  mov     r15d, eax
0x1400828ec  mov     rbx, [rbp+57h+var_68]
0x1400828f0  test    rbx, rbx
0x1400828f3  jz      short loc_14008292D
0x1400828f5  mov     ecx, r13d
0x1400828f8  lock xadd [rbx+8], ecx
0x1400828fd  add     ecx, r13d
0x140082900  jnz     short loc_14008292D
0x140082902  mov     rdx, [rbx]
0x140082905  mov     rcx, rbx
0x140082908  mov     rax, [rdx]
0x14008290b  call    _guard_dispatch_icall
0x140082910  mov     eax, r13d
0x140082913  lock xadd [rbx+0Ch], eax
0x140082918  add     eax, r13d
0x14008291b  jnz     short loc_14008292D
0x14008291d  mov     rax, [rbx]
0x140082920  mov     rcx, rbx
0x140082923  mov     rax, [rax+8]
0x140082927  call    _guard_dispatch_icall
0x14008292c  nop
0x14008292d  mov     rbx, [rbp+57h+var_58]
0x140082931  test    rbx, rbx
0x140082934  jz      short loc_14008296D
0x140082936  mov     eax, r13d
0x140082939  lock xadd [rbx+8], eax
0x14008293e  add     eax, r13d
0x140082941  jnz     short loc_14008296D
0x140082943  mov     rax, [rbx]
0x140082946  mov     rcx, rbx
0x140082949  mov     rax, [rax]
0x14008294c  call    _guard_dispatch_icall
0x140082951  mov     eax, r13d
0x140082954  lock xadd [rbx+0Ch], eax
0x140082959  add     eax, r13d
0x14008295c  jnz     short loc_14008296D
0x14008295e  mov     rax, [rbx]
0x140082961  mov     rcx, rbx
0x140082964  mov     rax, [rax+8]
0x140082968  call    _guard_dispatch_icall
0x14008296d  lea     rax, aEndworkthreadR_0; "EndWorkThread:  Releasing lock on m_wor"...
0x140082974  mov     [rbp+57h+var_80], rax
0x140082978  mov     [rbp+57h+var_78], 7Fh
0x140082980  lea     rcx, [rbp+57h+var_80]
0x140082984  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x140082989  mov     dword ptr [rbp+57h+var_90], r15d
0x14008298d  lea     rdx, [rbp+57h+var_90]
0x140082991  lea     rcx, [rbp+57h+var_80]
0x140082995  call    ??$_To_absolute_time@HU?$ratio@$0DM@$00@std@@@std@@YA?A_PAEBV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@0@@Z
0x14008299a  mov     rbx, rax
0x14008299d  cmp     byte ptr [rsi+499h], 0
0x1400829a4  jnz     short loc_1400829EA
0x1400829a6  lea     rcx, [rbp+57h+var_90]
0x1400829aa  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1400829af  mov     rdx, [rbx]
0x1400829b2  mov     rcx, [rbp+57h+var_90]
0x1400829b6  cmp     rdx, rcx
0x1400829b9  jz      short loc_1400829C2
0x1400829bb  jl      short loc_1400829C2
0x1400829bd  sub     rdx, rcx
0x1400829c0  jmp     short loc_1400829C4
0x1400829c2  xor     edx, edx
0x1400829c4  mov     [rbp+57h+var_70], rdx
0x1400829c8  lea     r8, [rbp+57h+var_70]
0x1400829cc  lea     rdx, [rbp+57h+var_40]
0x1400829d0  lea     rcx, [rsi+440h]
0x1400829d7  call    ??$wait_for@V?$unique_lock@Vrecursive_mutex@std@@@std@@_JU?$ratio@$00$0DLJKMKAA@@2@@condition_variable_any@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vrecursive_mutex@std@@@1@AEBV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@1@@Z; std::condition_variable_any::wait_for<std::unique_lock<std::recursive_mutex>,__int64,std::ratio<1,1000000000>>(std::unique_lock<std::recursive_mutex> &,std::chrono::duration<__int64,std::ratio<1,1000000000>> const &)
0x1400829dc  mov     cl, [rsi+499h]
0x1400829e2  cmp     eax, edi
0x1400829e4  jz      short loc_1400829ED
0x1400829e6  test    cl, cl
0x1400829e8  jz      short loc_1400829A6
0x1400829ea  mov     cl, dil
0x1400829ed  test    cl, cl
0x1400829ef  jz      loc_140082A76
0x1400829f5  lea     rax, aEndworkthreadS; "EndWorkThread:  Signaled m_workThreadCo"...
0x1400829fc  mov     [rbp+57h+var_80], rax
0x140082a00  mov     [rbp+57h+var_78], 55h ; 'U'
0x140082a08  lea     rcx, [rbp+57h+var_80]
0x140082a0c  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x140082a11  mov     dil, byte ptr [rbp+57h+var_40+8]
0x140082a15  test    dil, dil
0x140082a18  jz      short loc_140082A32
0x140082a1a  mov     rcx, qword ptr [rbp+57h+var_40]
0x140082a1e  add     [rcx+4Ch], r13d
0x140082a22  jnz     short loc_140082A32
0x140082a24  mov     [rcx+48h], r13d
0x140082a28  add     rcx, 10h; SRWLock
0x140082a2c  call    cs:__imp_ReleaseSRWLockExclusive
0x140082a32  lea     rax, aEndworkthreadR_1; "EndWorkThread:  Releasing lock on m_wor"...
0x140082a39  mov     qword ptr [rbp+57h+var_40], rax
0x140082a3d  mov     qword ptr [rbp+57h+var_40+8], 4Ah ; 'J'
0x140082a45  lea     rcx, [rbp+57h+var_40]
0x140082a49  call    ??$LogVerbose@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::LogVerbose<>(std::wstring_view)
0x140082a4e  mov     rcx, [rbp+57h+var_30]
0x140082a52  xor     rcx, rsp; StackCookie
0x140082a55  call    __security_check_cookie
0x140082a5a  lea     r11, [rsp+0B0h+var_20]
0x140082a62  mov     rbx, [r11+38h]
0x140082a66  mov     rsi, [r11+40h]
0x140082a6a  mov     rsp, r11
0x140082a6d  pop     r15
0x140082a6f  pop     r14
0x140082a71  pop     r13
0x140082a73  pop     rdi
0x140082a74  pop     rbp
0x140082a75  retn
0x140082a76  lea     rdx, aUpdatemanagerE; "UpdateManager::EndWorkThread timed out "...
0x140082a7d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140082a81  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x140082a86  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x140082a8d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140082a91  call    _CxxThrowException
0x140082a97  mov     rcx, [rbp+5Fh]; this
0x140082a9b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140082aa2  mov     edx, 0C9h; void *
0x140082aa7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140082aad  mov     ecx, 5; int
0x140082ab2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140082ab8  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x140082abf  mov     ecx, 6; int
0x140082ac4  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140082aca  mov     ecx, 5; int
0x140082acf  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140082ad5  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x140082adc  mov     ecx, 6; int
0x140082ae1  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```

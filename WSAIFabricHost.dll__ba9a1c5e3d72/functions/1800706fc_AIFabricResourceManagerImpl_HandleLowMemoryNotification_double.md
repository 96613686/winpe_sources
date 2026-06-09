# AIFabricResourceManagerImpl::HandleLowMemoryNotification(double)

- ea: `0x1800706fc`
- end: `0x180070d4d`
- name: `?HandleLowMemoryNotification@AIFabricResourceManagerImpl@@AEAAXN@Z`
- size: `1617`
- prototype: `void __fastcall(AIFabricResourceManagerImpl *__hidden this, double)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006fe10`

## callees

- `0x1800017dc`
- `0x180004ca0`
- `0x180005758`
- `0x180007ad0`
- `0x180065380`
- `0x18006c1a4`
- `0x18006c980`
- `0x18006cb80`
- `0x18006ce70`
- `0x18006d1a4`
- `0x18006d22c`
- `0x18006d3f0`
- `0x18006d754`
- `0x18006dddc`
- `0x18006e03c`
- `0x18006f488`
- `0x18006f510`
- `0x1800706fc`
- `0x180072e40`
- `0x180073370`
- `0x180073474`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007091e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007091e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007098a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007098a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800708ae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800708ae`
- `msvcp_win!_Mtx_unlock` at `0x1800707ee`
- `msvcp_win!_Mtx_unlock` at `0x180070ab6`
- `msvcp_win!_Mtx_unlock` at `0x180070c67`
- `msvcp_win!_Mtx_unlock` at `0x180070d02`
- `msvcp_win!_Mtx_unlock` at `0x1800707ee`
- `msvcp_win!_Mtx_unlock` at `0x180070ab6`
- `msvcp_win!_Mtx_unlock` at `0x180070c67`
- `msvcp_win!_Mtx_unlock` at `0x180070d02`
- `msvcp_win!_Mtx_lock` at `0x180070784`
- `msvcp_win!_Mtx_lock` at `0x180070c3a`
- `msvcp_win!_Mtx_lock` at `0x180070cc5`
- `msvcp_win!_Mtx_lock` at `0x180070784`
- `msvcp_win!_Mtx_lock` at `0x180070c3a`
- `msvcp_win!_Mtx_lock` at `0x180070cc5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070793`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800707ae`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070d19`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070d25`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070793`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800707ae`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070d19`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180070d25`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800708e5`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800708e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AIFabricResourceManagerImpl::HandleLowMemoryNotification(AIFabricResourceManagerImpl *this, double a2)
{
  const struct _tlgProvider_t *v3; // rax
  struct _Mtx_internal_imp_t *v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  __int64 *v6; // r9
  __int64 v7; // r15
  __int64 **v8; // r14
  __int64 *v9; // rsi
  AIFabricResourceManagerImpl *v10; // r12
  char *v11; // rdi
  unsigned __int64 *v12; // rcx
  signed int LastError; // eax
  unsigned __int64 v14; // r10
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // r15
  int *v18; // r12
  __int64 v19; // rdi
  __int64 *v20; // r14
  __int64 v21; // rcx
  __int64 i; // rsi
  __int64 v23; // r13
  ULONGLONG v24; // rax
  ULONGLONG v25; // rdi
  ULONGLONG v26; // r14
  void (__fastcall ***v27)(_QWORD, ULONGLONG); // rcx
  __int64 v28; // rdx
  int v29; // r15d
  void (__fastcall ***v30)(_QWORD, ULONGLONG); // rcx
  int v31; // eax
  void (__fastcall ***v32)(_QWORD, ULONGLONG); // rcx
  char *v33; // rdi
  signed int v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+34h] [rbp-CCh]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v37; // [rsp+40h] [rbp-C0h] BYREF
  double v38; // [rsp+50h] [rbp-B0h]
  __int128 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  char *v41; // [rsp+70h] [rbp-90h]
  AIFabricResourceManagerImpl *v42; // [rsp+78h] [rbp-88h] BYREF
  char v43; // [rsp+80h] [rbp-80h]
  char *v44; // [rsp+88h] [rbp-78h]
  char v45; // [rsp+90h] [rbp-70h]
  void *v46; // [rsp+98h] [rbp-68h]
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-18h]
  __int64 v49; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DATA_DESCRIPTOR v50; // [rsp+100h] [rbp+0h] BYREF
  char v51; // [rsp+110h] [rbp+10h]

  v42 = this;
  v3 = AIFabricTraceLogger::Provider();
  if ( *(_DWORD *)v3 > 5u )
    tlgWriteTransfer_EventWriteTransfer((__int64)v3, (unsigned __int8 *)&dword_18009E44C, 0, 0, 2u, &v50);
  v39 = 0;
  v40 = 0;
  v4 = (AIFabricResourceManagerImpl *)((char *)this + 112);
  v44 = (char *)this + 112;
  if ( _Mtx_lock((AIFabricResourceManagerImpl *)((char *)this + 112)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)this + 47) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 47) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_QWORD *)this + 5) )
  {
    std::chrono::steady_clock::now(&v36);
    v7 = *((unsigned int *)this + 48);
    v37 = 0;
    v38 = 0.0;
    v41 = (char *)this + 24;
    v8 = (__int64 **)*((_QWORD *)this + 4);
    v9 = *v8;
    v10 = v42;
    while ( v9 != (__int64 *)v8 )
    {
      if ( v9[4] && !*((_BYTE *)v9 + 48) && v36 - v9[5] >= 1000000000 * v7 )
      {
        v42 = (AIFabricResourceManagerImpl *)((char *)v9 + 52);
        v11 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)v9 + 13));
        v46 = v11;
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          memset_0(&ppsmemCounters.PageFaultCount, 0, 0x5Cu);
          ppsmemCounters.cb = 96;
          if ( K32GetProcessMemoryInfo(v11, &ppsmemCounters, 0x60u) )
          {
            v9[7] = v48;
            v9[8] = v49;
            v9[9] = ppsmemCounters.WorkingSetSize;
          }
        }
        v12 = (unsigned __int64 *)(v9 + 9);
        if ( !v9[9] && !v9[7] && !v9[8] )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v34 = LastError;
          AIFabricTraceLogger::GetProcessMemoryInfoFailed<unsigned long &,long>((char *)v9 + 52, &v34);
          v12 = (unsigned __int64 *)(v9 + 9);
        }
        v14 = *((unsigned int *)v10 + 49);
        if ( *v12 >= v14 || (v6 = v9 + 7, v9[7] + v9[8] >= v14) )
        {
          v42 = (AIFabricResourceManagerImpl *)(v9 + 4);
          v15 = *((_QWORD *)&v37 + 1);
          if ( *((_QWORD *)&v37 + 1) == *(_QWORD *)&v38 )
          {
            std::vector<std::pair<winrt::guid,ClientInfo *>>::_Emplace_reallocate<winrt::guid const &,ClientInfo *>(
              &v37,
              *((_QWORD *)&v37 + 1),
              v9 + 2,
              &v42);
          }
          else
          {
            **((_OWORD **)&v37 + 1) = *((_OWORD *)v9 + 1);
            *(_QWORD *)(v15 + 16) = v9 + 4;
            *((_QWORD *)&v37 + 1) += 24LL;
          }
        }
        else
        {
          AIFabricTraceLogger::ClientBelowMemoryThreshold<winrt::guid const &,unsigned long &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(
            (_DWORD)v9 + 16,
            (_DWORD)v42,
            (_DWORD)v12,
            (_DWORD)v6,
            (__int64)(v9 + 8));
        }
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v11);
      }
      v9 = (__int64 *)*v9;
    }
    LOBYTE(v6) = v35;
    std::_Sort_unchecked_std::pair_winrt::guid_ClientInfo_______lambda_8ebed0c59b5b3c3e1207f0b6a9ebaf9b___(
      v37,
      *((_QWORD *)&v37 + 1),
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v37 + 1) - v37) >> 3),
      v6);
    v17 = *((_QWORD *)&v37 + 1);
    v16 = v37;
    v18 = (int *)((char *)v4 + 76);
    if ( (_QWORD)v37 != *((_QWORD *)&v37 + 1) )
    {
      v19 = *((_QWORD *)&v39 + 1);
      do
      {
        v20 = *(__int64 **)(v16 + 16);
        if ( v19 == v40 )
        {
          std::vector<std::pair<winrt::guid,ClientInfo>>::_Emplace_reallocate<winrt::guid &,ClientInfo &>(
            &v39,
            v19,
            v16,
            *(_QWORD *)(v16 + 16));
          v19 = *((_QWORD *)&v39 + 1);
        }
        else
        {
          *(_OWORD *)v19 = *(_OWORD *)v16;
          v21 = *v20;
          *(_QWORD *)(v19 + 16) = *v20;
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
          *(_QWORD *)(v19 + 24) = v20[1];
          *(_BYTE *)(v19 + 32) = *((_BYTE *)v20 + 16);
          *(_DWORD *)(v19 + 36) = *((_DWORD *)v20 + 5);
          *(_QWORD *)(v19 + 40) = v20[3];
          *(_QWORD *)(v19 + 48) = v20[4];
          *(_QWORD *)(v19 + 56) = v20[5];
          v19 = *((_QWORD *)&v39 + 1) + 64LL;
          *((_QWORD *)&v39 + 1) += 64LL;
        }
        v16 += 24;
      }
      while ( v16 != v17 );
    }
    std::vector<std::pair<winrt::guid,ClientInfo *>>::~vector<std::pair<winrt::guid,ClientInfo *>>(&v37);
    _Mtx_unlock(v4);
    v23 = *((_QWORD *)&v39 + 1);
    for ( i = v39; ; i += 64 )
    {
      if ( i == v23 )
        goto LABEL_11;
      if ( *(_QWORD *)(i + 16) )
        break;
LABEL_70:
      ;
    }
    *(_QWORD *)&v37 = i + 16;
    *((_QWORD *)&v37 + 1) = i;
    v38 = a2;
    v46 = operator new(0x120u);
    v24 = std::_Task_async_state_long_::_Task_async_state_long__std::_Fake_no_copy_callable_adapter__lambda_693768bffad3694950c90f6a8799758a_____(
            v46,
            &v37);
    v25 = v24;
    v50.Ptr = v24;
    LOBYTE(v50.Size) = 0;
    v51 = 0;
    if ( !v24 )
      std::_Throw_future_error2(4);
    v26 = v24;
    v44 = (char *)v24;
    v45 = 1;
    _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v24 + 8), 0xFFFFFFFF) == 1 )
    {
      v27 = *(void (__fastcall ****)(_QWORD, ULONGLONG))(v24 + 200);
      if ( v27 )
        (**v27)(v27, v24);
      else
        (**(void (__fastcall ***)(ULONGLONG, __int64))v24)(v24, 1);
    }
    v36 = 5;
    if ( *(_BYTE *)(v25 + 184) )
      std::_Throw_future_error2(4);
    if ( (unsigned int)std::_Associated_state<long>::_Wait_for<__int64,std::ratio<1,1>>(v25, &v36) )
    {
      AIFabricTraceLogger::ShutdownTimedOut<winrt::guid &>(i);
    }
    else
    {
      v26 = 0;
      v44 = 0;
      v42 = (AIFabricResourceManagerImpl *)v25;
      v43 = 1;
      if ( *(_BYTE *)(v25 + 184) )
        std::_Throw_future_error2(4);
      LOBYTE(v28) = 1;
      v29 = *(_DWORD *)(*(__int64 (__fastcall **)(ULONGLONG, __int64))(*(_QWORD *)v25 + 16LL))(v25, v28);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 8), 0xFFFFFFFF) == 1 )
      {
        v30 = *(void (__fastcall ****)(_QWORD, ULONGLONG))(v25 + 200);
        if ( v30 )
          (**v30)(v30, v25);
        else
          (**(void (__fastcall ***)(ULONGLONG, __int64))v25)(v25, 1);
      }
      v34 = v29;
      AIFabricTraceLogger::SignalShutdown<winrt::guid &,long &>(i, &v34);
      if ( v29 >= 0 )
      {
        if ( _Mtx_lock(v4) )
        {
LABEL_79:
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        v31 = *v18;
        if ( *v18 == 0x7FFFFFFF )
        {
LABEL_78:
          *v18 = v31 - 1;
          std::_Throw_Cpp_error(6);
          __debugbreak();
        }
        v33 = v41;
        std::_Hash<std::_Umap_traits<winrt::guid,ClientInfo,std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>,std::allocator<std::pair<winrt::guid const,ClientInfo>>,0>>::find(
          v41,
          &v36,
          i);
        if ( v36 != *((_QWORD *)v33 + 1) )
          *(_BYTE *)(v36 + 48) = 1;
        _Mtx_unlock(v4);
        goto LABEL_11;
      }
      if ( v29 != -2147417848 && v29 != -2147023174 )
        goto LABEL_65;
    }
    if ( _Mtx_lock(v4) )
      goto LABEL_79;
    v31 = *v18;
    if ( *v18 == 0x7FFFFFFF )
      goto LABEL_78;
    std::_Hash<std::_Umap_traits<winrt::guid,ClientInfo,std::_Uhash_compare<winrt::guid,std::hash<winrt::guid>,std::equal_to<winrt::guid>>,std::allocator<std::pair<winrt::guid const,ClientInfo>>,0>>::erase(
      v41,
      i);
    _Mtx_unlock(v4);
LABEL_65:
    if ( v26 && _InterlockedExchangeAdd((volatile signed __int32 *)(v26 + 8), 0xFFFFFFFF) == 1 )
    {
      v32 = *(void (__fastcall ****)(_QWORD, ULONGLONG))(v26 + 200);
      if ( v32 )
        (**v32)(v32, v26);
      else
        (**(void (__fastcall ***)(ULONGLONG, __int64))v26)(v26, 1);
    }
    goto LABEL_70;
  }
  v5 = AIFabricTraceLogger::Provider();
  if ( *(_DWORD *)v5 > 5u )
    tlgWriteTransfer_EventWriteTransfer((__int64)v5, (unsigned __int8 *)&byte_18009E42F, 0, 0, 2u, &v50);
  _Mtx_unlock((AIFabricResourceManagerImpl *)((char *)this + 112));
LABEL_11:
  std::vector<std::pair<winrt::guid,ClientInfo>>::~vector<std::pair<winrt::guid,ClientInfo>>(&v39);
}

```

## disassembly

```asm
0x1800706fc  mov     rax, rsp
0x1800706ff  push    rbp
0x180070700  push    rbx
0x180070701  push    rsi
0x180070702  push    rdi
0x180070703  push    r12
0x180070705  push    r13
0x180070707  push    r14
0x180070709  push    r15
0x18007070b  lea     rbp, [rsp-48h]
0x180070710  sub     rsp, 148h
0x180070717  movaps  xmmword ptr [rax-58h], xmm6
0x18007071b  mov     rax, cs:__security_cookie
0x180070722  xor     rax, rsp
0x180070725  mov     [rbp+80h+var_60], rax
0x180070729  movaps  xmm6, xmm1
0x18007072c  mov     rdi, rcx
0x18007072f  mov     [rsp+180h+var_108], rcx
0x180070734  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x180070739  mov     edx, [rax]
0x18007073b  mov     esi, 2
0x180070740  cmp     edx, 5
0x180070743  jbe     short loc_180070767
0x180070745  lea     rcx, [rbp+80h+var_80]
0x180070749  mov     [rsp+180h+var_158], rcx
0x18007074e  mov     dword ptr [rsp+180h+var_160], esi
0x180070752  xor     r9d, r9d
0x180070755  xor     r8d, r8d
0x180070758  lea     rdx, dword_18009E44C
0x18007075f  mov     rcx, rax
0x180070762  call    _tlgWriteTransfer_EventWriteTransfer
0x180070767  xorps   xmm0, xmm0
0x18007076a  movdqu  [rsp+180h+var_128], xmm0
0x180070770  mov     [rsp+180h+var_118], 0
0x180070779  lea     rbx, [rdi+70h]
0x18007077d  mov     [rbp+80h+var_F8], rbx
0x180070781  mov     rcx, rbx; _Mtx_t
0x180070784  call    cs:__imp__Mtx_lock
0x18007078a  test    eax, eax
0x18007078c  jz      short loc_18007079A
0x18007078e  mov     ecx, 5
0x180070793  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180070799  int     3; Trap to Debugger
0x18007079a  mov     eax, [rbx+4Ch]
0x18007079d  cmp     eax, 7FFFFFFFh
0x1800707a2  jnz     short loc_1800707B5
0x1800707a4  dec     eax
0x1800707a6  mov     [rbx+4Ch], eax
0x1800707a9  mov     ecx, 6
0x1800707ae  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800707b4  nop
0x1800707b5  cmp     qword ptr [rdi+28h], 0
0x1800707ba  jnz     short loc_180070827
0x1800707bc  call    ?Provider@AIFabricTraceLogger@@SAPEBU_tlgProvider_t@@XZ; AIFabricTraceLogger::Provider(void)
0x1800707c1  mov     ecx, [rax]
0x1800707c3  cmp     ecx, 5
0x1800707c6  jbe     short loc_1800707EB
0x1800707c8  lea     rcx, [rbp+80h+var_80]
0x1800707cc  mov     [rsp+180h+var_158], rcx
0x1800707d1  mov     dword ptr [rsp+180h+var_160], esi
0x1800707d5  xor     r9d, r9d
0x1800707d8  xor     r8d, r8d
0x1800707db  lea     rdx, byte_18009E42F
0x1800707e2  mov     rcx, rax
0x1800707e5  call    _tlgWriteTransfer_EventWriteTransfer
0x1800707ea  nop
0x1800707eb  mov     rcx, rbx; _Mtx_t
0x1800707ee  call    cs:__imp__Mtx_unlock
0x1800707f4  nop
0x1800707f5  lea     rcx, [rsp+180h+var_128]
0x1800707fa  call    ??1?$vector@U?$pair@Uguid@winrt@@UClientInfo@@@std@@V?$allocator@U?$pair@Uguid@winrt@@UClientInfo@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<winrt::guid,ClientInfo>>::~vector<std::pair<winrt::guid,ClientInfo>>(void)
0x1800707ff  mov     rcx, [rbp+80h+var_60]
0x180070803  xor     rcx, rsp; StackCookie
0x180070806  call    __security_check_cookie
0x18007080b  movaps  xmm6, [rsp+180h+var_50]
0x180070813  add     rsp, 148h
0x18007081a  pop     r15
0x18007081c  pop     r14
0x18007081e  pop     r13
0x180070820  pop     r12
0x180070822  pop     rdi
0x180070823  pop     rsi
0x180070824  pop     rbx
0x180070825  pop     rbp
0x180070826  retn
0x180070827  lea     rcx, [rsp+180h+var_148]
0x18007082c  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180070831  mov     r15d, [rdi+0C0h]
0x180070838  xorps   xmm0, xmm0
0x18007083b  movdqu  [rsp+180h+var_140], xmm0
0x180070841  mov     [rsp+180h+var_130], 0
0x18007084a  lea     rax, [rdi+18h]
0x18007084e  mov     [rsp+180h+var_110], rax
0x180070853  mov     r14, [rax+8]
0x180070857  mov     rsi, [r14]
0x18007085a  mov     r12, [rsp+180h+var_108]
0x18007085f  cmp     rsi, r14
0x180070862  jz      loc_1800709D2
0x180070868  lea     r13, [rsi+20h]
0x18007086c  cmp     qword ptr [r13+0], 0
0x180070871  jz      loc_180070990
0x180070877  cmp     byte ptr [r13+10h], 0
0x18007087c  jnz     loc_180070990
0x180070882  imul    rcx, r15, 3B9ACA00h
0x180070889  mov     rax, [rsp+180h+var_148]
0x18007088e  sub     rax, [r13+8]
0x180070892  cmp     rax, rcx
0x180070895  jl      loc_180070990
0x18007089b  lea     rax, [r13+14h]
0x18007089f  mov     [rsp+180h+var_108], rax
0x1800708a4  mov     r8d, [rax]; dwProcessId
0x1800708a7  xor     edx, edx; bInheritHandle
0x1800708a9  mov     ecx, 1000h; dwDesiredAccess
0x1800708ae  call    cs:__imp_OpenProcess
0x1800708b4  mov     rdi, rax
0x1800708b7  mov     [rbp+80h+var_E8], rax
0x1800708bb  dec     rax
0x1800708be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800708c2  ja      short loc_180070907
0x1800708c4  xor     edx, edx; Val
0x1800708c6  lea     r8d, [rdx+5Ch]; Size
0x1800708ca  lea     rcx, [rbp+80h+ppsmemCounters.PageFaultCount]; void *
0x1800708ce  call    memset_0
0x1800708d3  mov     eax, 60h ; '`'
0x1800708d8  mov     [rbp+80h+ppsmemCounters.cb], eax
0x1800708db  mov     r8d, eax; cb
0x1800708de  lea     rdx, [rbp+80h+ppsmemCounters]; ppsmemCounters
0x1800708e2  mov     rcx, rdi; Process
0x1800708e5  call    cs:__imp_K32GetProcessMemoryInfo
0x1800708eb  test    eax, eax
0x1800708ed  jz      short loc_180070907
0x1800708ef  mov     rax, [rbp+80h+var_98]
0x1800708f3  mov     [r13+18h], rax
0x1800708f7  mov     rax, [rbp+80h+var_88]
0x1800708fb  mov     [r13+20h], rax
0x1800708ff  mov     rax, [rbp+80h+ppsmemCounters.WorkingSetSize]
0x180070903  mov     [r13+28h], rax
0x180070907  lea     rcx, [r13+28h]
0x18007090b  xor     eax, eax
0x18007090d  cmp     [rcx], rax
0x180070910  jnz     short loc_180070946
0x180070912  cmp     [r13+18h], rax
0x180070916  jnz     short loc_180070946
0x180070918  cmp     [r13+20h], rax
0x18007091c  jnz     short loc_180070946
0x18007091e  call    cs:__imp_GetLastError
0x180070924  test    eax, eax
0x180070926  jle     short loc_180070930
0x180070928  movzx   eax, ax
0x18007092b  or      eax, 80070000h
0x180070930  mov     [rsp+180h+var_150], eax
0x180070934  lea     rdx, [rsp+180h+var_150]
0x180070939  lea     rcx, [r13+14h]
0x18007093d  call    ??$GetProcessMemoryInfoFailed@AEAKJ@AIFabricTraceLogger@@SAXAEAK$$QEAJ@Z; AIFabricTraceLogger::GetProcessMemoryInfoFailed<ulong &,long>(ulong &,long &&)
0x180070942  lea     rcx, [r13+28h]
0x180070946  mov     r10d, [r12+0C4h]
0x18007094e  cmp     [rcx], r10
0x180070951  jnb     short loc_180070998
0x180070953  lea     r11, [r13+20h]
0x180070957  lea     r9, [r13+18h]
0x18007095b  mov     rax, [r11]
0x18007095e  add     rax, [r9]
0x180070961  cmp     rax, r10
0x180070964  jnb     short loc_180070998
0x180070966  mov     [rsp+180h+var_160], r11
0x18007096b  mov     r8, rcx
0x18007096e  mov     rdx, [rsp+180h+var_108]
0x180070973  lea     rcx, [rsi+10h]
0x180070977  call    ??$ClientBelowMemoryThreshold@AEBUguid@winrt@@AEAKAEA_KAEA_KAEA_K@AIFabricTraceLogger@@SAXAEBUguid@winrt@@AEAKAEA_K22@Z; AIFabricTraceLogger::ClientBelowMemoryThreshold<winrt::guid const &,ulong &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &>(winrt::guid const &,ulong &,unsigned __int64 &,unsigned __int64 &,unsigned __int64 &)
0x18007097c  nop
0x18007097d  lea     rax, [rdi-1]
0x180070981  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180070985  ja      short loc_180070990
0x180070987  mov     rcx, rdi; hObject
0x18007098a  call    cs:__imp_CloseHandle
0x180070990  mov     rsi, [rsi]
0x180070993  jmp     loc_18007085F
0x180070998  mov     [rsp+180h+var_108], r13
0x18007099d  mov     rdx, qword ptr [rsp+180h+var_140+8]
0x1800709a2  cmp     rdx, [rsp+180h+var_130]
0x1800709a7  jz      short loc_1800709BD
0x1800709a9  movups  xmm0, xmmword ptr [rsi+10h]
0x1800709ad  movdqu  xmmword ptr [rdx], xmm0
0x1800709b1  mov     [rdx+10h], r13
0x1800709b5  add     qword ptr [rsp+180h+var_140+8], 18h
0x1800709bb  jmp     short loc_18007097D
0x1800709bd  lea     r9, [rsp+180h+var_108]
0x1800709c2  lea     r8, [rsi+10h]
0x1800709c6  lea     rcx, [rsp+180h+var_140]
0x1800709cb  call    ??$_Emplace_reallocate@AEBUguid@winrt@@PEAUClientInfo@@@?$vector@U?$pair@Uguid@winrt@@PEAUClientInfo@@@std@@V?$allocator@U?$pair@Uguid@winrt@@PEAUClientInfo@@@std@@@2@@std@@AEAAPEAU?$pair@Uguid@winrt@@PEAUClientInfo@@@1@QEAU21@AEBUguid@winrt@@$$QEAPEAUClientInfo@@@Z; std::vector<std::pair<winrt::guid,ClientInfo *>>::_Emplace_reallocate<winrt::guid const &,ClientInfo *>(std::pair<winrt::guid,ClientInfo *> * const,winrt::guid const &,ClientInfo * &&)
0x1800709d0  jmp     short loc_18007097D
0x1800709d2  mov     rdx, qword ptr [rsp+180h+var_140+8]
0x1800709d7  mov     rcx, qword ptr [rsp+180h+var_140]
0x1800709dc  mov     r8, rdx
0x1800709df  sub     r8, rcx
0x1800709e2  sar     r8, 3
0x1800709e6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800709f0  imul    r8, rax
0x1800709f4  mov     r9b, [rsp+180h+var_14C]
0x1800709f9  call    std___Sort_unchecked_std__pair_winrt__guid_ClientInfo_______lambda_8ebed0c59b5b3c3e1207f0b6a9ebaf9b___
0x1800709fe  mov     rsi, qword ptr [rsp+180h+var_140]
0x180070a03  mov     r15, qword ptr [rsp+180h+var_140+8]
0x180070a08  cmp     rsi, r15
0x180070a0b  lea     r12, [rbx+4Ch]
0x180070a0f  jz      loc_180070AA8
0x180070a15  mov     rdi, qword ptr [rsp+180h+var_128+8]
0x180070a1a  mov     r14, [rsi+10h]
0x180070a1e  cmp     rdi, [rsp+180h+var_118]
0x180070a23  jz      short loc_180070A83
0x180070a25  movups  xmm0, xmmword ptr [rsi]
0x180070a28  movdqu  xmmword ptr [rdi], xmm0
0x180070a2c  mov     rcx, [r14]
0x180070a2f  mov     [rdi+10h], rcx
0x180070a33  test    rcx, rcx
0x180070a36  jz      short loc_180070A45
0x180070a38  mov     rax, [rcx]
0x180070a3b  mov     rax, [rax+8]
0x180070a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070a44  nop
0x180070a45  mov     rax, [r14+8]
0x180070a49  mov     [rdi+18h], rax
0x180070a4d  mov     al, [r14+10h]
0x180070a51  mov     [rdi+20h], al
0x180070a54  mov     eax, [r14+14h]
0x180070a58  mov     [rdi+24h], eax
0x180070a5b  mov     rax, [r14+18h]
0x180070a5f  mov     [rdi+28h], rax
0x180070a63  mov     rax, [r14+20h]
0x180070a67  mov     [rdi+30h], rax
0x180070a6b  mov     rax, [r14+28h]
0x180070a6f  mov     [rdi+38h], rax
0x180070a73  mov     rdi, qword ptr [rsp+180h+var_128+8]
0x180070a78  add     rdi, 40h ; '@'
0x180070a7c  mov     qword ptr [rsp+180h+var_128+8], rdi
0x180070a81  jmp     short loc_180070A9B
0x180070a83  mov     r9, r14
0x180070a86  mov     r8, rsi
0x180070a89  mov     rdx, rdi
0x180070a8c  lea     rcx, [rsp+180h+var_128]
0x180070a91  call    ??$_Emplace_reallocate@AEAUguid@winrt@@AEAUClientInfo@@@?$vector@U?$pair@Uguid@winrt@@UClientInfo@@@std@@V?$allocator@U?$pair@Uguid@winrt@@UClientInfo@@@std@@@2@@std@@AEAAPEAU?$pair@Uguid@winrt@@UClientInfo@@@1@QEAU21@AEAUguid@winrt@@AEAUClientInfo@@@Z; std::vector<std::pair<winrt::guid,ClientInfo>>::_Emplace_reallocate<winrt::guid &,ClientInfo &>(std::pair<winrt::guid,ClientInfo> * const,winrt::guid &,ClientInfo &)
0x180070a96  mov     rdi, qword ptr [rsp+180h+var_128+8]
0x180070a9b  add     rsi, 18h
0x180070a9f  cmp     rsi, r15
0x180070aa2  jnz     loc_180070A1A
0x180070aa8  lea     rcx, [rsp+180h+var_140]
0x180070aad  call    ??1?$vector@U?$pair@Uguid@winrt@@PEAUClientInfo@@@std@@V?$allocator@U?$pair@Uguid@winrt@@PEAUClientInfo@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<winrt::guid,ClientInfo *>>::~vector<std::pair<winrt::guid,ClientInfo *>>(void)
0x180070ab2  nop
0x180070ab3  mov     rcx, rbx; _Mtx_t
0x180070ab6  call    cs:__imp__Mtx_unlock
0x180070abc  mov     rsi, qword ptr [rsp+180h+var_128]
0x180070ac1  mov     r13, qword ptr [rsp+180h+var_128+8]
0x180070ac6  jmp     loc_180070CB4
0x180070acb  lea     rax, [rsi+10h]
0x180070acf  cmp     qword ptr [rax], 0
0x180070ad3  jz      loc_180070CB0
0x180070ad9  mov     qword ptr [rsp+180h+var_140], rax
0x180070ade  mov     qword ptr [rsp+180h+var_140+8], rsi
0x180070ae3  movsd   [rsp+180h+var_130], xmm6
0x180070ae9  mov     ecx, 120h; Size
0x180070aee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180070af3  mov     [rbp+80h+var_E8], rax
0x180070af7  lea     rdx, [rsp+180h+var_140]
0x180070afc  mov     rcx, rax
0x180070aff  call    std___Task_async_state_long____Task_async_state_long__std___Fake_no_copy_callable_adapter__lambda_693768bffad3694950c90f6a8799758a_____
0x180070b04  mov     rdi, rax
0x180070b07  mov     [rbp+80h+var_80], rax
0x180070b0b  mov     [rbp+80h+var_78], 0
0x180070b0f  mov     [rbp+80h+var_70], 0
0x180070b13  test    rax, rax
0x180070b16  jz      loc_180070D37
0x180070b1c  mov     r14, rax
0x180070b1f  mov     [rbp+80h+var_F8], rax
0x180070b23  mov     [rbp+80h+var_F0], 1
0x180070b27  lock inc dword ptr [rax+8]
0x180070b2b  or      eax, 0FFFFFFFFh
0x180070b2e  lock xadd [rdi+8], eax
0x180070b33  cmp     eax, 1
0x180070b36  jnz     short loc_180070B68
0x180070b38  mov     rcx, [r14+0C8h]
0x180070b3f  test    rcx, rcx
0x180070b42  jz      short loc_180070B54
0x180070b44  mov     rax, [rcx]
0x180070b47  mov     rdx, r14
0x180070b4a  mov     rax, [rax]
0x180070b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b52  jmp     short loc_180070B68
0x180070b54  mov     rax, [rdi]
0x180070b57  mov     edx, 1
0x180070b5c  mov     rcx, rdi
0x180070b5f  mov     rax, [rax]
0x180070b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b67  nop
0x180070b68  mov     [rsp+180h+var_148], 5
0x180070b71  cmp     byte ptr [rdi+0B8h], 0
0x180070b78  jnz     loc_180070D2C
0x180070b7e  lea     rdx, [rsp+180h+var_148]
0x180070b83  mov     rcx, rdi
0x180070b86  call    ??$_Wait_for@_JU?$ratio@$00$00@std@@@?$_Associated_state@J@std@@QEAA?AW4future_status@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::_Associated_state<long>::_Wait_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x180070b8b  test    eax, eax
0x180070b8d  jnz     loc_180070C2F
  ... truncated ...
```

# JobScheduler::_Run(void)

- ea: `0x18002b458`
- end: `0x18002b8d5`
- name: `?_Run@JobScheduler@@AEAAXXZ`
- size: `1149`
- prototype: `void __fastcall(JobScheduler *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002b110`

## callees

- `0x18000ec38`
- `0x180010d9c`
- `0x1800128ac`
- `0x18001370c`
- `0x180013864`
- `0x180013c1c`
- `0x180015474`
- `0x180015f70`
- `0x18001baa8`
- `0x18001de4c`
- `0x180021790`
- `0x180021fac`
- `0x180022070`
- `0x180025ff8`
- `0x1800260f4`
- `0x18002ae28`
- `0x18002b014`
- `0x18002b390`
- `0x18002b458`
- `0x18002ba00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b50c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b6c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b50c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b6c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b55a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b843`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b55a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002b843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b894`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002b7b4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002b7b4`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002b830`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002b830`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b5f3`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b5f3`

## string_xrefs

- `0x18002b873`: `onecoreuap\base\devices\setup\dsm\service\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall JobScheduler::_Run(JobScheduler *this)
{
  char *v2; // r15
  RTL_SRWLOCK *v3; // rbx
  std::_Ref_count_base *Ptr; // rcx
  void *v5; // rbx
  DWORD v6; // eax
  unsigned int v7; // r8d
  const char *v8; // r9
  int NextJobs; // eax
  _QWORD *v10; // rdi
  DWORD v11; // eax
  _QWORD *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // edx
  __int64 v16; // r14
  char *v17; // r13
  __int64 v18; // rbx
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  int v21; // ebx
  _QWORD *v22; // rax
  DWORD LastError; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  DWORD v26; // ebx
  unsigned int v27; // [rsp+20h] [rbp-69h]
  _BYTE v28[8]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v29; // [rsp+48h] [rbp-41h]
  HANDLE Handles[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v31; // [rsp+60h] [rbp-29h] BYREF
  std::_Ref_count_base *v32; // [rsp+68h] [rbp-21h]
  __int64 v33; // [rsp+70h] [rbp-19h] BYREF
  std::_Ref_count_base *v34; // [rsp+78h] [rbp-11h]
  char *v35; // [rsp+80h] [rbp-9h]
  char *v36; // [rsp+88h] [rbp-1h]
  _BYTE v37[16]; // [rsp+90h] [rbp+7h] BYREF
  __int128 v38; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v39; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  RTL_SRWLOCK *v41; // [rsp+F0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
  }
  v2 = (char *)operator new(0x50u);
  v41 = (RTL_SRWLOCK *)v2;
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  *((_DWORD *)v2 + 3) = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<std::function<void (unsigned short const *,bool)>>::`vftable';
  *((_QWORD *)v2 + 2) = off_180046C70;
  *((_QWORD *)v2 + 3) = this;
  *((_QWORD *)v2 + 9) = v2 + 16;
  v35 = v2 + 16;
  v36 = v2;
  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 57);
  _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
  AcquireSRWLockExclusive(v3);
  v41 = v3;
  _InterlockedIncrement((volatile signed __int32 *)v2 + 3);
  v3[20].Ptr = v2 + 16;
  Ptr = (std::_Ref_count_base *)v3[21].Ptr;
  v3[21].Ptr = v2;
  if ( Ptr )
    std::_Ref_count_base::_Decwref(Ptr);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v41);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v2);
  while ( 1 )
  {
    v5 = (void *)*((_QWORD *)this + 71);
    v6 = WaitForSingleObjectEx(v5, 0, 0);
    if ( v6 != 258 )
      break;
    Handles[0] = *((HANDLE *)this + 71);
    Handles[1] = *((HANDLE *)this + 72);
    v38 = 0;
    v39 = 0;
    NextJobs = ContainerManager::GetNextJobs(*((_QWORD *)this + 57), &v38);
    if ( NextJobs < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\scheduler.cpp",
        (const char *)(unsigned int)NextJobs,
        v27);
    v10 = (_QWORD *)v38;
    if ( (_QWORD)v38 == *((_QWORD *)&v38 + 1) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
      }
      v11 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
        }
        std::vector<std::shared_ptr<Job>>::_Tidy(&v38);
        goto LABEL_53;
      }
      if ( v11 != 1 )
      {
        LastError = GetLastError();
        v26 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids, LastError);
        }
        wil::details::in1diag3::Throw_Win32(retaddr, v24, v25, (const char *)v26, v27);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids);
      }
    }
    else
    {
      v12 = (_QWORD *)v38;
      do
      {
        Job::GetOwningContainer(*v12, &v31);
        v13 = std::shared_ptr<Container>::shared_ptr<Container>(v37, v12);
        Container::AddRunningJob(v14, v13);
        if ( v32 )
          std::_Ref_count_base::_Decref(v32);
        v12 += 2;
      }
      while ( v12 != *((_QWORD **)&v38 + 1) );
      for ( ; v10 != *((_QWORD **)&v38 + 1); v10 += 2 )
      {
        v15 = *(_DWORD *)(*v10 + 28LL);
        if ( v15 )
        {
          if ( (unsigned int)(v15 - 2) < 2 )
            v16 = 168;
          else
            v16 = 312;
        }
        else
        {
          v16 = 24;
        }
        AcquireSRWLockExclusive((PSRWLOCK)((char *)this + v16 + 120));
        v41 = (RTL_SRWLOCK *)((char *)this + v16 + 120);
        v17 = (char *)this + v16;
        if ( *(_QWORD *)((char *)this + v16 + 112) == 0x7FFFFFFFFFFFFFFLL )
          std::_Xlength_error("list too long");
        v18 = *((_QWORD *)v17 + 13);
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Job>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Job>,void *>>>(
          v28,
          v17 + 104,
          v10);
        ++*((_QWORD *)v17 + 14);
        v19 = *(_QWORD **)(v18 + 8);
        *v29 = v18;
        v29[1] = v19;
        v20 = v29;
        v29 = 0;
        *(_QWORD *)(v18 + 8) = v20;
        *v19 = v20;
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Container>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Container>,void *>>>(v28);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
          &v41,
          0);
        Job::GetOwningContainer(*v10, &v33);
        v21 = v33;
        if ( *((_QWORD *)this + 66) )
          std::_Func_class<void,enum SchedulerEvent>::operator()((char *)this + 472, 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v22 = (_QWORD *)(*v10 + 40LL);
          if ( *(_QWORD *)(*v10 + 64LL) > 7u )
            v22 = (_QWORD *)*v22;
          WPP_SF__guid_LSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *v10,
            *(_DWORD *)((char *)this + v16),
            v21 + 16,
            *(_DWORD *)(*v10 + 28LL),
            (__int64)v22,
            *(_DWORD *)((char *)this + v16));
        }
        SubmitThreadpoolWork(*(PTP_WORK *)((char *)this + v16 + 80));
        if ( v34 )
          std::_Ref_count_base::_Decref(v34);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v41);
      }
    }
    std::vector<std::shared_ptr<Job>>::_Tidy(&v38);
  }
  if ( v6 || WaitForSingleObjectEx(v5, 0, 0) )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v7, v8);
LABEL_53:
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v2);
}

```

## disassembly

```asm
0x18002b458  mov     [rsp-8+arg_8], rbx
0x18002b45d  mov     [rsp-8+arg_10], rsi
0x18002b462  push    rbp
0x18002b463  push    rdi
0x18002b464  push    r13
0x18002b466  push    r14
0x18002b468  push    r15
0x18002b46a  lea     rbp, [rsp-37h]
0x18002b46f  sub     rsp, 0C0h
0x18002b476  mov     rsi, rcx
0x18002b479  lea     r14, WPP_GLOBAL_Control
0x18002b480  lea     r13, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x18002b487  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b48e  cmp     rcx, r14
0x18002b491  jz      short loc_18002B4B0
0x18002b493  test    byte ptr [rcx+1Ch], 80h
0x18002b497  jz      short loc_18002B4B0
0x18002b499  cmp     byte ptr [rcx+19h], 4
0x18002b49d  jb      short loc_18002B4B0
0x18002b49f  mov     edx, 13h
0x18002b4a4  mov     r8, r13
0x18002b4a7  mov     rcx, [rcx+10h]
0x18002b4ab  call    WPP_SF_
0x18002b4b0  mov     ecx, 50h ; 'P'; Size
0x18002b4b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b4ba  mov     r15, rax
0x18002b4bd  mov     [rbp+57h+arg_0], rax
0x18002b4c1  xorps   xmm0, xmm0
0x18002b4c4  movups  xmmword ptr [rax], xmm0
0x18002b4c7  mov     dword ptr [rax+8], 1
0x18002b4ce  mov     dword ptr [rax+0Ch], 1
0x18002b4d5  lea     rax, ??_7?$_Ref_count_obj2@V?$function@$$A6AXPEBG_N@Z@std@@@std@@6B@; const std::_Ref_count_obj2<std::function<void (ushort const *,bool)>>::`vftable'
0x18002b4dc  mov     [r15], rax
0x18002b4df  lea     rdi, [r15+10h]
0x18002b4e3  lea     rax, off_180046C70
0x18002b4ea  mov     [rdi], rax
0x18002b4ed  mov     [rdi+8], rsi
0x18002b4f1  mov     [rdi+38h], rdi
0x18002b4f5  mov     [rbp+57h+var_60], rdi
0x18002b4f9  mov     [rbp+57h+var_58], r15
0x18002b4fd  mov     rbx, [rsi+1C8h]
0x18002b504  lock inc dword ptr [r15+8]
0x18002b509  mov     rcx, rbx; SRWLock
0x18002b50c  call    cs:__imp_AcquireSRWLockExclusive
0x18002b512  mov     [rbp+57h+arg_0], rbx
0x18002b516  lock inc dword ptr [r15+0Ch]
0x18002b51b  mov     [rbx+0A0h], rdi
0x18002b522  mov     rcx, [rbx+0A8h]; this
0x18002b529  mov     [rbx+0A8h], r15
0x18002b530  test    rcx, rcx
0x18002b533  jz      short loc_18002B53A
0x18002b535  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18002b53a  lea     rcx, [rbp+57h+arg_0]
0x18002b53e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b543  mov     rcx, r15; this
0x18002b546  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b54b  mov     rbx, [rsi+238h]
0x18002b552  xor     r8d, r8d; bAlertable
0x18002b555  xor     edx, edx; dwMilliseconds
0x18002b557  mov     rcx, rbx; hHandle
0x18002b55a  call    cs:__imp_WaitForSingleObjectEx
0x18002b560  cmp     eax, 102h
0x18002b565  jnz     loc_18002B837
0x18002b56b  mov     rax, [rsi+238h]
0x18002b572  mov     [rbp+57h+Handles], rax
0x18002b576  mov     rax, [rsi+240h]
0x18002b57d  mov     [rbp+57h+var_88], rax
0x18002b581  xorps   xmm0, xmm0
0x18002b584  movdqu  [rbp+57h+var_40], xmm0
0x18002b589  mov     [rbp+57h+var_30], 0
0x18002b591  lea     rdx, [rbp+57h+var_40]
0x18002b595  mov     rcx, [rsi+1C8h]
0x18002b59c  call    ?GetNextJobs@ContainerManager@@QEAAJAEAV?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@@Z; ContainerManager::GetNextJobs(std::vector<std::shared_ptr<Job>> &)
0x18002b5a1  mov     rcx, [rbp+5Fh]; this
0x18002b5a5  test    eax, eax
0x18002b5a7  js      loc_18002B870
0x18002b5ad  mov     rdi, qword ptr [rbp+57h+var_40]
0x18002b5b1  cmp     rdi, qword ptr [rbp+57h+var_40+8]
0x18002b5b5  jnz     loc_18002B640
0x18002b5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5c2  cmp     rcx, r14
0x18002b5c5  jz      short loc_18002B5E4
0x18002b5c7  test    byte ptr [rcx+1Ch], 80h
0x18002b5cb  jz      short loc_18002B5E4
0x18002b5cd  cmp     byte ptr [rcx+19h], 4
0x18002b5d1  jb      short loc_18002B5E4
0x18002b5d3  mov     edx, 14h
0x18002b5d8  mov     r8, r13
0x18002b5db  mov     rcx, [rcx+10h]
0x18002b5df  call    WPP_SF_
0x18002b5e4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002b5e8  xor     r8d, r8d; bWaitAll
0x18002b5eb  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18002b5ef  lea     ecx, [r8+2]; nCount
0x18002b5f3  call    cs:__imp_WaitForMultipleObjects
0x18002b5f9  test    eax, eax
0x18002b5fb  jz      loc_18002B7F4
0x18002b601  cmp     eax, 1
0x18002b604  jnz     loc_18002B894
0x18002b60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b611  cmp     rcx, r14
0x18002b614  jz      short loc_18002B632
0x18002b616  test    byte ptr [rcx+1Ch], 80h
0x18002b61a  jz      short loc_18002B632
0x18002b61c  cmp     byte ptr [rcx+19h], 4
0x18002b620  jb      short loc_18002B632
0x18002b622  lea     edx, [rax+15h]
0x18002b625  mov     r8, r13
0x18002b628  mov     rcx, [rcx+10h]
0x18002b62c  call    WPP_SF_
0x18002b631  nop
0x18002b632  lea     rcx, [rbp+57h+var_40]
0x18002b636  call    ?_Tidy@?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Job>>::_Tidy(void)
0x18002b63b  jmp     loc_18002B54B
0x18002b640  mov     rbx, rdi
0x18002b643  jz      short loc_18002B686
0x18002b645  lea     rdx, [rbp+57h+var_80]
0x18002b649  mov     rcx, [rbx]
0x18002b64c  call    ?GetOwningContainer@Job@@QEAA?AV?$shared_ptr@VContainer@@@std@@XZ; Job::GetOwningContainer(void)
0x18002b651  nop
0x18002b652  mov     r8, [rbp+57h+var_80]
0x18002b656  mov     rdx, rbx
0x18002b659  lea     rcx, [rbp+57h+var_50]
0x18002b65d  call    ??0?$shared_ptr@VContainer@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Container>::shared_ptr<Container>(std::shared_ptr<Container> const &)
0x18002b662  mov     rdx, rax
0x18002b665  mov     rcx, r8
0x18002b668  call    ?AddRunningJob@Container@@QEAAXV?$shared_ptr@VJob@@@std@@@Z; Container::AddRunningJob(std::shared_ptr<Job>)
0x18002b66d  nop
0x18002b66e  mov     rcx, [rbp+57h+var_78]; this
0x18002b672  test    rcx, rcx
0x18002b675  jz      short loc_18002B67C
0x18002b677  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b67c  add     rbx, 10h
0x18002b680  cmp     rbx, qword ptr [rbp+57h+var_40+8]
0x18002b684  jnz     short loc_18002B645
0x18002b686  cmp     rdi, qword ptr [rbp+57h+var_40+8]
0x18002b68a  jz      short loc_18002B632
0x18002b68c  mov     rcx, [rdi]
0x18002b68f  mov     edx, [rcx+1Ch]
0x18002b692  test    edx, edx
0x18002b694  jz      short loc_18002B6B0
0x18002b696  sub     edx, 2
0x18002b699  jz      short loc_18002B6A8
0x18002b69b  cmp     edx, 1
0x18002b69e  jz      short loc_18002B6A8
0x18002b6a0  mov     r14d, 138h
0x18002b6a6  jmp     short loc_18002B6B6
0x18002b6a8  mov     r14d, 0A8h
0x18002b6ae  jmp     short loc_18002B6B6
0x18002b6b0  mov     r14d, 18h
0x18002b6b6  lea     rbx, [rsi+78h]
0x18002b6ba  add     rbx, r14
0x18002b6bd  mov     rcx, rbx; SRWLock
0x18002b6c0  call    cs:__imp_AcquireSRWLockExclusive
0x18002b6c6  mov     [rbp+57h+arg_0], rbx
0x18002b6ca  lea     r13, [r14+rsi]
0x18002b6ce  mov     rax, 7FFFFFFFFFFFFFFh
0x18002b6d8  cmp     [r13+70h], rax
0x18002b6dc  jz      loc_18002B829
0x18002b6e2  mov     rbx, [r13+68h]
0x18002b6e6  mov     r8, rdi
0x18002b6e9  lea     rdx, [r13+68h]
0x18002b6ed  lea     rcx, [rbp+57h+var_A0]
0x18002b6f1  call    ??$?0AEBV?$shared_ptr@VJob@@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VJob@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$shared_ptr@VJob@@@std@@PEAX@std@@@1@AEBV?$shared_ptr@VJob@@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Job>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Job>,void *>>>(std::allocator<std::_List_node<std::shared_ptr<Job>,void *>> &,std::shared_ptr<Job> const &)
0x18002b6f6  inc     qword ptr [r13+70h]
0x18002b6fa  mov     rcx, [rbx+8]
0x18002b6fe  mov     rax, [rbp+57h+var_98]
0x18002b702  mov     [rax], rbx
0x18002b705  mov     rax, [rbp+57h+var_98]
0x18002b709  mov     [rax+8], rcx
0x18002b70d  mov     rax, [rbp+57h+var_98]
0x18002b711  mov     [rbp+57h+var_98], 0
0x18002b719  mov     [rbx+8], rax
0x18002b71d  mov     [rcx], rax
0x18002b720  lea     rcx, [rbp+57h+var_A0]
0x18002b724  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VContainer@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Container>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Container>,void *>>>(void)
0x18002b729  xor     edx, edx
0x18002b72b  lea     rcx, [rbp+57h+arg_0]
0x18002b72f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18002b734  lea     rdx, [rbp+57h+var_70]
0x18002b738  mov     rcx, [rdi]
0x18002b73b  call    ?GetOwningContainer@Job@@QEAA?AV?$shared_ptr@VContainer@@@std@@XZ; Job::GetOwningContainer(void)
0x18002b740  nop
0x18002b741  mov     rbx, [rbp+57h+var_70]
0x18002b745  cmp     qword ptr [rsi+210h], 0
0x18002b74d  jz      short loc_18002B75D
0x18002b74f  lea     rcx, [rsi+1D8h]
0x18002b756  xor     edx, edx
0x18002b758  call    ??R?$_Func_class@XW4SchedulerEvent@@@std@@QEBAXW4SchedulerEvent@@@Z; std::_Func_class<void,SchedulerEvent>::operator()(SchedulerEvent)
0x18002b75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b764  lea     rax, WPP_GLOBAL_Control
0x18002b76b  cmp     rcx, rax
0x18002b76e  jz      short loc_18002B7AF
0x18002b770  test    byte ptr [rcx+1Ch], 80h
0x18002b774  jz      short loc_18002B7AF
0x18002b776  cmp     byte ptr [rcx+19h], 4
0x18002b77a  jb      short loc_18002B7AF
0x18002b77c  mov     r8d, [r14+rsi]
0x18002b780  mov     rdx, [rdi]
0x18002b783  lea     rax, [rdx+28h]
0x18002b787  cmp     qword ptr [rax+18h], 7
0x18002b78c  jbe     short loc_18002B791
0x18002b78e  mov     rax, [rax]
0x18002b791  mov     [rsp+0E0h+var_B0], r8d
0x18002b796  mov     [rsp+0E0h+var_B8], rax
0x18002b79b  mov     eax, [rdx+1Ch]
0x18002b79e  mov     [rsp+0E0h+var_C0], eax
0x18002b7a2  lea     r9, [rbx+10h]
0x18002b7a6  mov     rcx, [rcx+10h]
0x18002b7aa  call    WPP_SF__guid_LSD
0x18002b7af  mov     rcx, [r14+rsi+50h]; pwk
0x18002b7b4  call    cs:__imp_SubmitThreadpoolWork
0x18002b7ba  nop
0x18002b7bb  mov     rcx, [rbp+57h+var_68]; this
0x18002b7bf  test    rcx, rcx
0x18002b7c2  jz      short loc_18002B7CA
0x18002b7c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b7c9  nop
0x18002b7ca  lea     rcx, [rbp+57h+arg_0]
0x18002b7ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b7d3  add     rdi, 10h
0x18002b7d7  cmp     rdi, qword ptr [rbp+57h+var_40+8]
0x18002b7db  jnz     loc_18002B68C
0x18002b7e1  lea     r14, WPP_GLOBAL_Control
0x18002b7e8  lea     r13, WPP_4a19ff13275d346bcbd49403e9cec97f_Traceguids
0x18002b7ef  jmp     loc_18002B632
0x18002b7f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7fb  cmp     rcx, r14
0x18002b7fe  jz      short loc_18002B81E
0x18002b800  test    byte ptr [rcx+1Ch], 80h
0x18002b804  jz      short loc_18002B81E
0x18002b806  cmp     byte ptr [rcx+19h], 4
0x18002b80a  jb      short loc_18002B81E
0x18002b80c  mov     edx, 15h
0x18002b811  mov     r8, r13
0x18002b814  mov     rcx, [rcx+10h]
0x18002b818  call    WPP_SF_
0x18002b81d  nop
0x18002b81e  lea     rcx, [rbp+57h+var_40]
0x18002b822  call    ?_Tidy@?$vector@V?$shared_ptr@VJob@@@std@@V?$allocator@V?$shared_ptr@VJob@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Job>>::_Tidy(void)
0x18002b827  jmp     short loc_18002B84D
0x18002b829  lea     rcx, aListTooLong; "list too long"
0x18002b830  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002b837  test    eax, eax
0x18002b839  jnz     short loc_18002B885
0x18002b83b  xor     r8d, r8d; bAlertable
0x18002b83e  xor     edx, edx; dwMilliseconds
0x18002b840  mov     rcx, rbx; hHandle
0x18002b843  call    cs:__imp_WaitForSingleObjectEx
0x18002b849  test    eax, eax
0x18002b84b  jnz     short loc_18002B885
0x18002b84d  mov     rcx, r15; this
0x18002b850  lea     r11, [rsp+0E0h+var_20]
0x18002b858  mov     rbx, [r11+38h]
0x18002b85c  mov     rsi, [r11+40h]
0x18002b860  mov     rsp, r11
0x18002b863  pop     r15
0x18002b865  pop     r14
0x18002b867  pop     r13
0x18002b869  pop     rdi
0x18002b86a  pop     rbp
0x18002b86b  jmp     ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002b870  mov     r9d, eax; char *
0x18002b873  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002b87a  mov     edx, 80h; void *
0x18002b87f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002b885  mov     rcx, [rbp+5Fh]; this
0x18002b889  mov     edx, 0B07h; void *
0x18002b88e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002b894  call    cs:__imp_GetLastError
0x18002b89a  mov     ebx, eax
0x18002b89c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8a3  cmp     rcx, r14
0x18002b8a6  jz      short loc_18002B8C8
0x18002b8a8  test    byte ptr [rcx+1Ch], 80h
0x18002b8ac  jz      short loc_18002B8C8
0x18002b8ae  cmp     byte ptr [rcx+19h], 2
0x18002b8b2  jb      short loc_18002B8C8
0x18002b8b4  mov     edx, 17h
0x18002b8b9  mov     r9d, eax
0x18002b8bc  mov     r8, r13
0x18002b8bf  mov     rcx, [rcx+10h]
0x18002b8c3  call    WPP_SF_d
0x18002b8c8  mov     rcx, [rbp+5Fh]; this
0x18002b8cc  mov     r9d, ebx; char *
0x18002b8cf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```

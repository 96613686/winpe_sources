# Vml::VmModule<CExec::Svc::Service>::Finalize(void)

- ea: `0x140013914`
- end: `0x140013bbc`
- name: `?Finalize@?$VmModule@VService@Svc@CExec@@@Vml@@QEAAXXZ`
- size: `680`
- prototype: `int()`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140014ac0`

## callees

- `0x140002310`
- `0x1400026b8`
- `0x14000f1ac`
- `0x14000f278`
- `0x140013808`
- `0x140013914`
- `0x140013bc4`
- `0x140014100`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400139ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013a8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400139ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140013a8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013ac6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013a57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140013ac6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013982`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140013982`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140013a80`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140013b1c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140013a80`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x140013b1c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140013a0c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140013a0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400139bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400139df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013a25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013a34`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400139bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400139df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013a25`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140013a34`

## string_xrefs

- `0x140013b85`: `Detected a leaked instance - this leak should be fixed ASAP - terminating process rather than waiting forever or risking crash during module cleanup due to invalid state.\n`

## pseudocode

```c
int Vml::VmModule<CExec::Svc::Service>::Finalize()
{
  unsigned int v0; // ebx
  DWORD TickCount; // esi
  unsigned int v2; // edi
  unsigned int v3; // eax
  DWORD v4; // r8d
  BOOL v5; // eax
  unsigned int v6; // ecx
  Vml *v7; // rcx
  void *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  REGHANDLE v11; // rcx
  const unsigned __int16 *CurrentModuleName; // rbx
  unsigned __int64 *v13; // r9
  unsigned int v15[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-20h]
  int v17; // [rsp+50h] [rbp-18h] BYREF
  DWORD v18; // [rsp+54h] [rbp-14h] BYREF

  if ( Vml::VmSharableObject::gm_AllocatedObjectCount )
  {
    v17 = 0;
    v18 = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\VML",
           L"LeakWaitSeconds",
           0x10u,
           0,
           &v17,
           &v18) )
    {
      v0 = 120;
      v17 = 120;
    }
    else
    {
      v0 = v17;
    }
    if ( v0 != -1 )
    {
      if ( v0 >= 4 )
      {
        if ( v0 > 0xFFFFFED7 )
          v0 = -297;
      }
      else
      {
        v0 = 4;
      }
      v0 *= 1000;
      v17 = v0;
    }
    TickCount = GetTickCount();
    AcquireSRWLockExclusive(&Vml::VmSharableObject::gm_AllocatedObjectLock);
    v2 = Vml::VmSharableObject::gm_AllocatedObjectCount;
    if ( Vml::VmSharableObject::gm_AllocatedObjectCount )
    {
      while ( 1 )
      {
        if ( v0 == -1 )
        {
          v4 = -1;
        }
        else
        {
          v3 = GetTickCount() - TickCount;
          v4 = v3 >= v0 ? 0 : v0 - v3;
        }
        v5 = SleepConditionVariableSRW(
               &Vml::VmSharableObject::gm_AllocatedObjectCountIsZeroCondition,
               &Vml::VmSharableObject::gm_AllocatedObjectLock,
               v4,
               0);
        v6 = Vml::VmSharableObject::gm_AllocatedObjectCount;
        if ( !v5 && Vml::VmSharableObject::gm_AllocatedObjectCount < v2 )
          break;
        if ( v0 != -1 )
          goto LABEL_21;
LABEL_23:
        v2 = v6;
        if ( !v6 )
          goto LABEL_24;
      }
      v0 = 4000;
      TickCount = GetTickCount();
LABEL_21:
      if ( GetTickCount() - TickCount >= v0 )
      {
        CurrentModuleName = Vml::GetCurrentModuleName(v7);
        if ( (unsigned int)VmlIsDebugTraceEnabled(32774) )
          VmlDebugTrace(
            32774,
            L"%hs is taking a long time - giving up on module: %ws\n",
            "Vml::VmSharableObject::WaitUntilAllocatedObjectCountIsZero",
            CurrentModuleName);
        if ( (unsigned int)VmlIsDebugTraceEnabled(32774) )
          VmlDebugTrace(
            32774,
            L"Detected a leaked instance - this leak should be fixed ASAP - terminating process rather than waiting foreve"
             "r or risking crash during module cleanup due to invalid state.\n");
        v16 = Vml::VmSharableObject::gm_AllocatedObjectCount;
        *(_QWORD *)v15 = 1465205071;
        Vml::RaiseExceptionAndTerminate((Vml *)0xC0000194LL, 2u, (unsigned int)v15, v13);
        JUMPOUT(0x140013BBBLL);
      }
      v6 = Vml::VmSharableObject::gm_AllocatedObjectCount;
      goto LABEL_23;
    }
LABEL_24:
    ReleaseSRWLockExclusive(&Vml::VmSharableObject::gm_AllocatedObjectLock);
  }
  if ( g_VmlEtwTrace )
  {
    _InterlockedExchange64(
      (volatile __int64 *)&g_TraceOutput,
      (__int64)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy);
    EventUnregister(*((_QWORD *)g_VmlEtwTrace + 2));
    AcquireSRWLockExclusive(&Vml::VmpModuleInfo::gm_ModuleInfoMapLock);
    v8 = Vml::VmpModuleInfo::gm_ModuleInfoMap;
    if ( Vml::VmpModuleInfo::gm_ModuleInfoMap )
    {
      std::_Tree<std::_Tmap_traits<void *,Vml::VmpModuleInfo,std::less<void *>,std::allocator<std::pair<void * const,Vml::VmpModuleInfo>>,0>>::~_Tree<std::_Tmap_traits<void *,Vml::VmpModuleInfo,std::less<void *>,std::allocator<std::pair<void * const,Vml::VmpModuleInfo>>,0>>(Vml::VmpModuleInfo::gm_ModuleInfoMap);
      operator delete(v8);
    }
    Vml::VmpModuleInfo::gm_ModuleInfoMap = 0;
    ReleaseSRWLockExclusive(&Vml::VmpModuleInfo::gm_ModuleInfoMapLock);
    g_VmlEtwTrace = 0;
  }
  v9 = (*(__int64 (__fastcall **)(__int64 *))(g_Module + 48))(&g_Module);
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *))(g_Module + 40))(&g_Module);
    v11 = *(_QWORD *)(v10 + 32);
    *(_DWORD *)v10 = 0;
    *(_QWORD *)(v10 + 32) = 0;
    LODWORD(v9) = EventUnregister(v11);
  }
  Vml::VmModuleBase::gm_ModuleBase = 0;
  return v9;
}

```

## disassembly

```asm
0x140013914  mov     r11, rsp
0x140013917  mov     [r11+8], rbx
0x14001391b  mov     [r11+10h], rsi
0x14001391f  push    rdi
0x140013920  sub     rsp, 60h
0x140013924  mov     rax, cs:__security_cookie
0x14001392b  xor     rax, rsp
0x14001392e  mov     [rsp+68h+var_10], rax
0x140013933  cmp     cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA, 0; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x14001393a  jz      loc_140013A5D
0x140013940  lea     rax, [r11-14h]
0x140013944  mov     [rsp+68h+var_18], 0
0x14001394c  mov     [r11-38h], rax
0x140013950  lea     r8, aLeakwaitsecond; "LeakWaitSeconds"
0x140013957  mov     edi, 4
0x14001395c  lea     rax, [r11-18h]
0x140013960  mov     [r11-40h], rax
0x140013964  lea     rdx, ?g_VmlRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001396b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140013972  mov     qword ptr [r11-48h], 0
0x14001397a  mov     [rsp+68h+var_14], edi
0x14001397e  lea     r9d, [rdi+0Ch]; dwFlags
0x140013982  call    cs:__imp_RegGetValueW
0x140013988  test    eax, eax
0x14001398a  jz      short loc_140013995
0x14001398c  lea     ebx, [rdi+74h]
0x14001398f  mov     [rsp+68h+var_18], ebx
0x140013993  jmp     short loc_140013999
0x140013995  mov     ebx, [rsp+68h+var_18]
0x140013999  cmp     ebx, 0FFFFFFFFh
0x14001399c  jz      short loc_1400139BB
0x14001399e  cmp     ebx, edi
0x1400139a0  jnb     short loc_1400139A6
0x1400139a2  mov     ebx, edi
0x1400139a4  jmp     short loc_1400139B1
0x1400139a6  mov     eax, 0FFFFFED7h
0x1400139ab  cmp     ebx, eax
0x1400139ad  jbe     short loc_1400139B1
0x1400139af  mov     ebx, eax
0x1400139b1  imul    ebx, 3E8h
0x1400139b7  mov     [rsp+68h+var_18], ebx
0x1400139bb  call    cs:__imp_GetTickCount
0x1400139c1  lea     rcx, ?gm_AllocatedObjectLock@VmSharableObject@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x1400139c8  mov     esi, eax
0x1400139ca  call    cs:__imp_AcquireSRWLockExclusive
0x1400139d0  mov     edi, cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x1400139d6  test    edi, edi
0x1400139d8  jz      short loc_140013A50
0x1400139da  cmp     ebx, 0FFFFFFFFh
0x1400139dd  jz      short loc_1400139F8
0x1400139df  call    cs:__imp_GetTickCount
0x1400139e5  sub     eax, esi
0x1400139e7  cmp     eax, ebx
0x1400139e9  jnb     short loc_1400139F3
0x1400139eb  mov     r8d, ebx
0x1400139ee  sub     r8d, eax
0x1400139f1  jmp     short loc_1400139FB
0x1400139f3  xor     r8d, r8d
0x1400139f6  jmp     short loc_1400139FB
0x1400139f8  mov     r8d, ebx; dwMilliseconds
0x1400139fb  xor     r9d, r9d; Flags
0x1400139fe  lea     rdx, ?gm_AllocatedObjectLock@VmSharableObject@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x140013a05  lea     rcx, ?gm_AllocatedObjectCountIsZeroCondition@VmSharableObject@Vml@@0U_RTL_CONDITION_VARIABLE@@A; ConditionVariable
0x140013a0c  call    cs:__imp_SleepConditionVariableSRW
0x140013a12  mov     ecx, cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x140013a18  test    eax, eax
0x140013a1a  jnz     short loc_140013A2F
0x140013a1c  cmp     ecx, edi
0x140013a1e  jnb     short loc_140013A2F
0x140013a20  mov     ebx, 0FA0h
0x140013a25  call    cs:__imp_GetTickCount
0x140013a2b  mov     esi, eax
0x140013a2d  jmp     short loc_140013A34
0x140013a2f  cmp     ebx, 0FFFFFFFFh
0x140013a32  jz      short loc_140013A4A
0x140013a34  call    cs:__imp_GetTickCount
0x140013a3a  sub     eax, esi
0x140013a3c  cmp     eax, ebx
0x140013a3e  jnb     loc_140013B4A
0x140013a44  mov     ecx, cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x140013a4a  mov     edi, ecx
0x140013a4c  test    ecx, ecx
0x140013a4e  jnz     short loc_1400139DA
0x140013a50  lea     rcx, ?gm_AllocatedObjectLock@VmSharableObject@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x140013a57  call    cs:__imp_ReleaseSRWLockExclusive
0x140013a5d  cmp     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, 0; _VML_ETW_TRACE * g_VmlEtwTrace
0x140013a65  jz      short loc_140013AD7
0x140013a67  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x140013a6e  xchg    rax, cs:?g_TraceOutput@@3R6AXGPEBG@ZEA; void (*g_TraceOutput)(ushort,ushort const *)
0x140013a75  mov     rcx, cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA; _VML_ETW_TRACE * g_VmlEtwTrace
0x140013a7c  mov     rcx, [rcx+10h]; RegHandle
0x140013a80  call    cs:__imp_EventUnregister
0x140013a86  lea     rcx, ?gm_ModuleInfoMapLock@VmpModuleInfo@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x140013a8d  call    cs:__imp_AcquireSRWLockExclusive
0x140013a93  mov     rbx, cs:?gm_ModuleInfoMap@VmpModuleInfo@Vml@@0PEAV?$map@PEAXVVmpModuleInfo@Vml@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXVVmpModuleInfo@Vml@@@std@@@4@@std@@EA; std::map<void *,Vml::VmpModuleInfo> * Vml::VmpModuleInfo::gm_ModuleInfoMap
0x140013a9a  test    rbx, rbx
0x140013a9d  jz      short loc_140013AB4
0x140013a9f  mov     rcx, rbx
0x140013aa2  call    ??1?$_Tree@V?$_Tmap_traits@PEAXVVmpModuleInfo@Vml@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXVVmpModuleInfo@Vml@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,Vml::VmpModuleInfo,std::less<void *>,std::allocator<std::pair<void * const,Vml::VmpModuleInfo>>,0>>::~_Tree<std::_Tmap_traits<void *,Vml::VmpModuleInfo,std::less<void *>,std::allocator<std::pair<void * const,Vml::VmpModuleInfo>>,0>>(void)
0x140013aa7  mov     edx, 10h; unsigned __int64
0x140013aac  mov     rcx, rbx; void *
0x140013aaf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140013ab4  lea     rcx, ?gm_ModuleInfoMapLock@VmpModuleInfo@Vml@@0U_RTL_SRWLOCK@@A; SRWLock
0x140013abb  mov     cs:?gm_ModuleInfoMap@VmpModuleInfo@Vml@@0PEAV?$map@PEAXVVmpModuleInfo@Vml@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXVVmpModuleInfo@Vml@@@std@@@4@@std@@EA, 0; std::map<void *,Vml::VmpModuleInfo> * Vml::VmpModuleInfo::gm_ModuleInfoMap
0x140013ac6  call    cs:__imp_ReleaseSRWLockExclusive
0x140013acc  mov     cs:?g_VmlEtwTrace@@3PEAU_VML_ETW_TRACE@@EA, 0; _VML_ETW_TRACE * g_VmlEtwTrace
0x140013ad7  mov     rax, cs:?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140013ade  lea     rcx, ?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140013ae5  mov     rax, [rax+30h]
0x140013ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013aee  test    rax, rax
0x140013af1  jz      short loc_140013B22
0x140013af3  mov     rax, cs:?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140013afa  lea     rcx, ?g_Module@@3VService@Svc@CExec@@A; CExec::Svc::Service g_Module
0x140013b01  mov     rax, [rax+28h]
0x140013b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b0a  mov     rcx, [rax+20h]; RegHandle
0x140013b0e  mov     dword ptr [rax], 0
0x140013b14  mov     qword ptr [rax+20h], 0
0x140013b1c  call    cs:__imp_EventUnregister
0x140013b22  mov     cs:?gm_ModuleBase@VmModuleBase@Vml@@1PEAV12@EA, 0; Vml::VmModuleBase * Vml::VmModuleBase::gm_ModuleBase
0x140013b2d  mov     rcx, [rsp+68h+var_10]
0x140013b32  xor     rcx, rsp; StackCookie
0x140013b35  call    __security_check_cookie
0x140013b3a  mov     rbx, [rsp+68h+arg_0]
0x140013b3f  mov     rsi, [rsp+68h+arg_8]
0x140013b44  add     rsp, 60h
0x140013b48  pop     rdi
0x140013b49  retn
0x140013b4a  call    ?GetCurrentModuleName@Vml@@YAPEBGXZ; Vml::GetCurrentModuleName(void)
0x140013b4f  mov     edi, 8006h
0x140013b54  mov     rbx, rax
0x140013b57  mov     ecx, edi
0x140013b59  call    VmlIsDebugTraceEnabled
0x140013b5e  test    eax, eax
0x140013b60  jz      short loc_140013B7A
0x140013b62  mov     r9, rbx
0x140013b65  lea     r8, aVmlVmsharableo; "Vml::VmSharableObject::WaitUntilAllocat"...
0x140013b6c  lea     rdx, aHsIsTakingALon; "%hs is taking a long time - giving up o"...
0x140013b73  mov     ecx, edi
0x140013b75  call    VmlDebugTrace
0x140013b7a  mov     ecx, edi
0x140013b7c  call    VmlIsDebugTraceEnabled
0x140013b81  test    eax, eax
0x140013b83  jz      short loc_140013B93
0x140013b85  lea     rdx, aDetectedALeake; "Detected a leaked instance - this leak "...
0x140013b8c  mov     ecx, edi
0x140013b8e  call    VmlDebugTrace
0x140013b93  mov     eax, cs:?gm_AllocatedObjectCount@VmSharableObject@Vml@@0KA; ulong Vml::VmSharableObject::gm_AllocatedObjectCount
0x140013b99  lea     r8, [rsp+68h+var_28]; unsigned int
0x140013b9e  mov     edx, 2; unsigned int
0x140013ba3  mov     [rsp+68h+var_20], rax
0x140013ba8  mov     ecx, 0C0000194h; this
0x140013bad  mov     qword ptr [rsp+68h+var_28], 5755414Fh
0x140013bb6  call    ?RaiseExceptionAndTerminate@Vml@@YAXIIPEA_K@Z; Vml::RaiseExceptionAndTerminate(uint,uint,unsigned __int64 *)
```

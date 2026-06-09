# ServiceThreadProc(void *)

- ea: `0x18002fd70`
- end: `0x18003015e`
- name: `?ServiceThreadProc@@YAKPEAX@Z`
- size: `1006`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update`

## callees

- `0x1800026b0`
- `0x18002e318`
- `0x18002f800`
- `0x18002fb4c`
- `0x18002fd70`
- `0x180030a68`
- `0x180030aac`
- `0x180030d2c`
- `0x180030dbc`
- `0x180033af0`
- `0x180034270`
- `0x180035384`
- `0x1800354bc`
- `0x180042640`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ff9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002ff9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fdb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fdb1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003002b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003002b`

## string_xrefs

- `0x18003014a`: `onecoreuap\enduser\winstore\pushtoinstall\lib\nexus.cpp`

## pseudocode

```c
__int64 __fastcall ServiceThreadProc(PVOID Parameter)
{
  PVOID v1; // rbx
  char v2; // r14
  WinStoreAuth::AuthenticationInternal **v3; // rdx
  WinStoreAuth::AuthenticationInternal *v4; // rax
  WinStoreAuth::AuthenticationInternal *v5; // rcx
  volatile signed __int32 *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r13
  __int64 *v10; // rdx
  __int64 v11; // r15
  __int64 v12; // rdi
  __int64 v13; // rax
  WinStoreAuth::AuthenticationInternal *v14; // r10
  __int64 v15; // r12
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r15
  __int64 v19; // rdi
  __int64 v20; // r13
  __int64 v21; // r14
  __int64 v22; // rbx
  __int64 i; // rax
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // rdx
  struct HttpRequest *v27; // r15
  const char *v28; // r9
  volatile signed __int32 *v29; // rdi
  char v31; // [rsp+20h] [rbp-A8h]
  __int64 v32; // [rsp+28h] [rbp-A0h] BYREF
  PVOID v33; // [rsp+30h] [rbp-98h]
  WinStoreAuth::AuthenticationInternal *v34[2]; // [rsp+38h] [rbp-90h]
  PVOID v35; // [rsp+48h] [rbp-80h]
  __int64 v36; // [rsp+50h] [rbp-78h] BYREF
  struct _WNF_STATE_NAME v37; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v1 = Parameter;
  v33 = Parameter;
  v35 = Parameter;
  do
  {
    *(_OWORD *)v34 = 0;
    AcquireSRWLockExclusive(&srwWorkQueue);
    if ( qword_180066490 )
    {
      v2 = 1;
      v31 = 1;
      v3 = (WinStoreAuth::AuthenticationInternal **)*((_QWORD *)qword_180066478
                                                    + (qword_180066488 & (qword_180066480 - 1)));
      v4 = v3[1];
      if ( v4 )
        _InterlockedIncrement((volatile signed __int32 *)v4 + 2);
      v5 = v3[1];
      v34[0] = *v3;
      v6 = (volatile signed __int32 *)v34[1];
      v34[1] = v5;
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      std::deque<std::shared_ptr<WorkItem>>::pop_front();
      v7 = qword_180066488;
      v8 = qword_180066490;
      v9 = qword_180066488 + qword_180066490;
      v10 = (__int64 *)workQueue;
      if ( workQueue )
        v11 = *(_QWORD *)workQueue;
      else
        v11 = 0;
      v12 = qword_180066488;
      v13 = qword_180066488;
      v14 = v34[0];
      while ( v13 != v9
           && *((_DWORD *)v34[0] + 2) != *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(v11 + 8)
                                                                 + 8 * (v12 & (*(_QWORD *)(v11 + 16) - 1LL)))
                                                   + 8LL) )
        v13 = ++v12;
      v15 = v12;
      if ( v12 != v9 )
      {
        while ( ++v12 != v9 )
        {
          v16 = *(_QWORD *)(v11 + 8);
          v17 = *(_QWORD *)(v16 + 8 * (v12 & (*(_QWORD *)(v11 + 16) - 1LL)));
          if ( *((_DWORD *)v14 + 2) != *(_DWORD *)(*(_QWORD *)v17 + 8LL) )
          {
            std::shared_ptr<WorkItem>::operator=(*(_QWORD *)(v16 + 8 * ((*(_QWORD *)(v11 + 16) - 1LL) & v15++)), v17);
            v14 = v34[0];
          }
        }
        v8 = qword_180066490;
        v7 = qword_180066488;
        v10 = (__int64 *)workQueue;
      }
      v18 = v7 + v8;
      v19 = v7 + v8 - v15;
      if ( v7 + v8 != v15 )
      {
        if ( v10 )
        {
          v20 = *v10;
          v21 = *v10;
        }
        else
        {
          v20 = 0;
          v21 = 0;
        }
        v22 = v7 + v8;
        for ( i = v7 + v8; i != v18; i = v22 )
          std::shared_ptr<WorkItem>::operator=(
            *(_QWORD *)(*(_QWORD *)(v21 + 8) + 8 * (v15++ & (*(_QWORD *)(v21 + 16) - 1LL))),
            *(_QWORD *)(*(_QWORD *)(v20 + 8) + 8 * (v22++ & (*(_QWORD *)(v20 + 16) - 1LL))));
        v1 = v33;
        v2 = 1;
        do
        {
          std::deque<std::shared_ptr<WorkItem>>::pop_back(&workQueue);
          --v19;
        }
        while ( v19 );
      }
    }
    else
    {
      v2 = 0;
      v31 = 0;
      workQueueRunning = 0;
    }
    ReleaseSRWLockExclusive(&srwWorkQueue);
    if ( v2 )
    {
      try
      {
        v26 = *((unsigned int *)v34[0] + 2);
        if ( (_DWORD)v26 )
        {
          if ( (_DWORD)v26 == 1 )
          {
            if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v34[0]) )
              QueryRemoteQueueForDeviceAndInstall();
            else
              QueryRemoteQueueForAllUsersAndInstallWithImpersonation();
          }
        }
        else
        {
          try
          {
            v37 = WNF_PTI_WNS_RECEIVED;
            RegisterForWns(v38, v26, v24, &v37);
            v27 = _correlationVector;
            CreateWnsRegistrationBody(&v32, v38);
            if ( !InitOnceExecuteOnce(&InitOnce, Nexus::InitializeOnce, &g_nexus, 0) )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0x49,
                (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\nexus.cpp",
                v28);
            MakePostRequest((struct TraceLoggingCorrelationVector *)&v36, v27);
            if ( v36 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 192LL))(v36, 1);
            if ( v32 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 192LL))(v32, 1);
            UpdateWNSRegistrationTask(0x14u);
            std::wstring::_Tidy_deallocate(v38);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x126,
              (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
              v25);
            UpdateWNSRegistrationTask(1u);
            v1 = v35;
            v33 = v35;
            v2 = v31;
          }
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x130,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          v25);
        v1 = v35;
        v33 = v35;
        v2 = v31;
      }
    }
    v29 = (volatile signed __int32 *)v34[1];
    if ( v34[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
  }
  while ( v2 );
  if ( v1 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v1 + 16LL))(v1);
  return 0;
}

```

## disassembly

```asm
0x18002fd70  push    rbx
0x18002fd72  push    rdi
0x18002fd73  push    r12
0x18002fd75  push    r13
0x18002fd77  push    r14
0x18002fd79  push    r15
0x18002fd7b  sub     rsp, 98h
0x18002fd82  mov     rax, cs:__security_cookie
0x18002fd89  xor     rax, rsp
0x18002fd8c  mov     [rsp+0C8h+var_48], rax
0x18002fd94  mov     rbx, rcx
0x18002fd97  mov     [rsp+0C8h+var_98], rcx
0x18002fd9c  mov     [rsp+0C8h+var_80], rcx
0x18002fda1  xorps   xmm0, xmm0
0x18002fda4  movdqu  xmmword ptr [rsp+0C8h+var_90], xmm0
0x18002fdaa  lea     rcx, ?srwWorkQueue@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18002fdb1  call    cs:__imp_AcquireSRWLockExclusive
0x18002fdb7  cmp     cs:qword_180066490, 0
0x18002fdbf  jz      loc_18002FF84
0x18002fdc5  mov     r14b, 1
0x18002fdc8  mov     [rsp+0C8h+var_A8], r14b
0x18002fdcd  mov     rcx, cs:qword_180066480
0x18002fdd4  dec     rcx
0x18002fdd7  and     rcx, cs:qword_180066488
0x18002fdde  mov     rax, cs:qword_180066478
0x18002fde5  mov     rdx, [rax+rcx*8]
0x18002fde9  mov     rax, [rdx+8]
0x18002fded  test    rax, rax
0x18002fdf0  jz      short loc_18002FDF6
0x18002fdf2  lock inc dword ptr [rax+8]
0x18002fdf6  mov     rcx, [rdx+8]
0x18002fdfa  mov     rax, [rdx]
0x18002fdfd  mov     [rsp+0C8h+var_90], rax
0x18002fe02  mov     rdi, [rsp+0C8h+var_90+8]
0x18002fe07  mov     [rsp+0C8h+var_90+8], rcx
0x18002fe0c  test    rdi, rdi
0x18002fe0f  jz      short loc_18002FE48
0x18002fe11  or      eax, 0FFFFFFFFh
0x18002fe14  lock xadd [rdi+8], eax
0x18002fe19  cmp     eax, 1
0x18002fe1c  jnz     short loc_18002FE48
0x18002fe1e  mov     rax, [rdi]
0x18002fe21  mov     rcx, rdi
0x18002fe24  mov     rax, [rax]
0x18002fe27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe2c  or      eax, 0FFFFFFFFh
0x18002fe2f  lock xadd [rdi+0Ch], eax
0x18002fe34  cmp     eax, 1
0x18002fe37  jnz     short loc_18002FE48
0x18002fe39  mov     rax, [rdi]
0x18002fe3c  mov     rcx, rdi
0x18002fe3f  mov     rax, [rax+8]
0x18002fe43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe48  call    ?pop_front@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<WorkItem>>::pop_front(void)
0x18002fe4d  mov     r8, cs:qword_180066488
0x18002fe54  mov     r9, cs:qword_180066490
0x18002fe5b  lea     r13, [r8+r9]
0x18002fe5f  mov     rdx, cs:?workQueue@@3V?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@A; std::deque<std::shared_ptr<WorkItem>> workQueue
0x18002fe66  test    rdx, rdx
0x18002fe69  jz      short loc_18002FE70
0x18002fe6b  mov     r15, [rdx]
0x18002fe6e  jmp     short loc_18002FE73
0x18002fe70  xor     r15d, r15d
0x18002fe73  mov     rdi, r8
0x18002fe76  mov     rax, r8
0x18002fe79  mov     r10, [rsp+0C8h+var_90]
0x18002fe7e  cmp     rax, r13
0x18002fe81  jz      short loc_18002FEA9
0x18002fe83  mov     rcx, [r15+10h]
0x18002fe87  dec     rcx
0x18002fe8a  and     rcx, rdi
0x18002fe8d  mov     rax, [r15+8]
0x18002fe91  mov     rcx, [rax+rcx*8]
0x18002fe95  mov     rax, [rcx]
0x18002fe98  mov     ecx, [rax+8]
0x18002fe9b  cmp     [r10+8], ecx
0x18002fe9f  jz      short loc_18002FEA9
0x18002fea1  inc     rdi
0x18002fea4  mov     rax, rdi
0x18002fea7  jmp     short loc_18002FE7E
0x18002fea9  mov     r12, rdi
0x18002feac  cmp     rdi, r13
0x18002feaf  jz      short loc_18002FF08
0x18002feb1  inc     rdi
0x18002feb4  cmp     rdi, r13
0x18002feb7  jz      short loc_18002FEF3
0x18002feb9  mov     r8, [r15+10h]
0x18002febd  dec     r8
0x18002fec0  mov     r9, [r15+8]
0x18002fec4  mov     rax, r8
0x18002fec7  and     rax, rdi
0x18002feca  mov     rdx, [r9+rax*8]
0x18002fece  mov     rax, [rdx]
0x18002fed1  mov     ecx, [rax+8]
0x18002fed4  cmp     [r10+8], ecx
0x18002fed8  jz      short loc_18002FEB1
0x18002feda  mov     rcx, r12
0x18002fedd  and     rcx, r8
0x18002fee0  mov     rcx, [r9+rcx*8]
0x18002fee4  call    ??4?$shared_ptr@VWorkItem@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WorkItem>::operator=(std::shared_ptr<WorkItem> &&)
0x18002fee9  inc     r12
0x18002feec  mov     r10, [rsp+0C8h+var_90]
0x18002fef1  jmp     short loc_18002FEB1
0x18002fef3  mov     r9, cs:qword_180066490
0x18002fefa  mov     r8, cs:qword_180066488
0x18002ff01  mov     rdx, cs:?workQueue@@3V?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@A; std::deque<std::shared_ptr<WorkItem>> workQueue
0x18002ff08  lea     r15, [r8+r9]
0x18002ff0c  mov     rdi, r15
0x18002ff0f  sub     rdi, r12
0x18002ff12  jz      short loc_18002FF93
0x18002ff14  test    rdx, rdx
0x18002ff17  jz      short loc_18002FF21
0x18002ff19  mov     r13, [rdx]
0x18002ff1c  mov     r14, r13
0x18002ff1f  jmp     short loc_18002FF27
0x18002ff21  xor     r13d, r13d
0x18002ff24  xor     r14d, r14d
0x18002ff27  mov     rbx, r15
0x18002ff2a  mov     rax, r15
0x18002ff2d  cmp     rax, r15
0x18002ff30  jz      short loc_18002FF66
0x18002ff32  mov     r8, [r13+10h]
0x18002ff36  dec     r8
0x18002ff39  and     r8, rbx
0x18002ff3c  mov     rdx, [r13+8]
0x18002ff40  mov     rax, [r14+10h]
0x18002ff44  dec     rax
0x18002ff47  and     rax, r12
0x18002ff4a  mov     rcx, [r14+8]
0x18002ff4e  mov     rdx, [rdx+r8*8]
0x18002ff52  mov     rcx, [rcx+rax*8]
0x18002ff56  call    ??4?$shared_ptr@VWorkItem@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WorkItem>::operator=(std::shared_ptr<WorkItem> &&)
0x18002ff5b  inc     r12
0x18002ff5e  inc     rbx
0x18002ff61  mov     rax, rbx
0x18002ff64  jmp     short loc_18002FF2D
0x18002ff66  mov     rbx, [rsp+0C8h+var_98]
0x18002ff6b  mov     r14b, [rsp+0C8h+var_A8]
0x18002ff70  lea     rcx, ?workQueue@@3V?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@A; std::deque<std::shared_ptr<WorkItem>> workQueue
0x18002ff77  call    ?pop_back@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<WorkItem>>::pop_back(void)
0x18002ff7c  sub     rdi, 1
0x18002ff80  jnz     short loc_18002FF70
0x18002ff82  jmp     short loc_18002FF93
0x18002ff84  xor     r14b, r14b
0x18002ff87  mov     [rsp+0C8h+var_A8], r14b
0x18002ff8c  mov     cs:?workQueueRunning@@3_NA, r14b; bool workQueueRunning
0x18002ff93  lea     rcx, ?srwWorkQueue@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18002ff9a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002ffa0  test    r14b, r14b
0x18002ffa3  jz      loc_1800300C7
0x18002ffa9  mov     rcx, [rsp+0C8h+var_90]; this
0x18002ffae  mov     edx, [rcx+8]
0x18002ffb1  test    edx, edx
0x18002ffb3  jz      short loc_18002FFD8
0x18002ffb5  cmp     edx, 1
0x18002ffb8  jnz     loc_1800300B6
0x18002ffbe  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x18002ffc3  test    al, al
0x18002ffc5  jz      short loc_18002FFCE
0x18002ffc7  call    ?QueryRemoteQueueForDeviceAndInstall@@YAXXZ; QueryRemoteQueueForDeviceAndInstall(void)
0x18002ffcc  jmp     short loc_18002FFD3
0x18002ffce  call    ?QueryRemoteQueueForAllUsersAndInstallWithImpersonation@@YAXXZ; QueryRemoteQueueForAllUsersAndInstallWithImpersonation(void)
0x18002ffd3  jmp     loc_1800300B6
0x18002ffd8  mov     rax, qword ptr cs:WNF_PTI_WNS_RECEIVED.Data
0x18002ffdf  mov     [rsp+0C8h+var_70], rax
0x18002ffe4  lea     r9, [rsp+0C8h+var_70]
0x18002ffe9  lea     rcx, [rsp+0C8h+var_68]
0x18002ffee  call    ?RegisterForWns@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEAU_WNF_STATE_NAME@@@Z; RegisterForWns(ushort const *,ushort const *,_WNF_STATE_NAME *)
0x18002fff3  nop
0x18002fff4  mov     r15, cs:?_correlationVector@@3PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * _correlationVector
0x18002fffb  lea     rdx, [rsp+0C8h+var_68]
0x180030000  lea     rcx, [rsp+0C8h+var_A0]
0x180030005  call    ?CreateWnsRegistrationBody@@YA?AVvalue@json@web@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CreateWnsRegistrationBody(std::wstring const &)
0x18003000a  nop
0x18003000b  mov     rdi, [rsp+0C8h]
0x180030013  xor     r9d, r9d; Context
0x180030016  lea     r8, ?g_nexus@@3VNexus@@A; Parameter
0x18003001d  lea     rdx, ?InitializeOnce@Nexus@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180030024  lea     rcx, InitOnce; InitOnce
0x18003002b  call    cs:__imp_InitOnceExecuteOnce
0x180030031  test    eax, eax
0x180030033  jz      loc_18003014A
0x180030039  lea     r9, [rsp+0C8h+var_A0]
0x18003003e  lea     r8, qword_1800664B0
0x180030045  mov     rdx, r15
0x180030048  lea     rcx, [rsp+0C8h+var_78]
0x18003004d  call    ?MakePostRequest@@YA?AVvalue@json@web@@PEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV123@@Z; MakePostRequest(TraceLoggingCorrelationVector *,std::wstring const &,web::json::value const &)
0x180030052  mov     rcx, [rsp+0C8h+var_78]
0x180030057  test    rcx, rcx
0x18003005a  jz      short loc_180030071
0x18003005c  mov     rax, [rcx]
0x18003005f  mov     edx, 1
0x180030064  mov     rax, [rax+0C0h]
0x18003006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030070  nop
0x180030071  mov     rcx, [rsp+0C8h+var_A0]
0x180030076  test    rcx, rcx
0x180030079  jz      short loc_18003008F
0x18003007b  mov     rax, [rcx]
0x18003007e  mov     edx, 1
0x180030083  mov     rax, [rax+0C0h]
0x18003008a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003008f  mov     ecx, 14h; unsigned int
0x180030094  call    ?UpdateWNSRegistrationTask@@YAXK@Z; UpdateWNSRegistrationTask(ulong)
0x180030099  nop
0x18003009a  lea     rcx, [rsp+0C8h+var_68]
0x18003009f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800300a4  nop
0x1800300a5  jmp     short loc_1800300B6
0x1800300a7  mov     rbx, [rsp+0C8h+var_80]
0x1800300ac  mov     [rsp+0C8h+var_98], rbx
0x1800300b1  mov     r14b, [rsp+0C8h+var_A8]
0x1800300b6  jmp     short loc_1800300C7
0x1800300b8  mov     rbx, [rsp+0C8h+var_80]
0x1800300bd  mov     [rsp+0C8h+var_98], rbx
0x1800300c2  mov     r14b, [rsp+0C8h+var_A8]
0x1800300c7  mov     rdi, [rsp+0C8h+var_90+8]
0x1800300cc  test    rdi, rdi
0x1800300cf  jz      short loc_180030108
0x1800300d1  or      eax, 0FFFFFFFFh
0x1800300d4  lock xadd [rdi+8], eax
0x1800300d9  cmp     eax, 1
0x1800300dc  jnz     short loc_180030108
0x1800300de  mov     rax, [rdi]
0x1800300e1  mov     rcx, rdi
0x1800300e4  mov     rax, [rax]
0x1800300e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ec  or      eax, 0FFFFFFFFh
0x1800300ef  lock xadd [rdi+0Ch], eax
0x1800300f4  cmp     eax, 1
0x1800300f7  jnz     short loc_180030108
0x1800300f9  mov     rax, [rdi]
0x1800300fc  mov     rcx, rdi
0x1800300ff  mov     rax, [rax+8]
0x180030103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030108  test    r14b, r14b
0x18003010b  jnz     loc_18002FDA1
0x180030111  test    rbx, rbx
0x180030114  jz      short loc_180030126
0x180030116  mov     rax, [rbx]
0x180030119  mov     rcx, rbx
0x18003011c  mov     rax, [rax+10h]
0x180030120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030125  nop
0x180030126  xor     eax, eax
0x180030128  mov     rcx, [rsp+0C8h+var_48]
0x180030130  xor     rcx, rsp; StackCookie
0x180030133  call    __security_check_cookie
0x180030138  add     rsp, 98h
0x18003013f  pop     r15
0x180030141  pop     r14
0x180030143  pop     r13
0x180030145  pop     r12
0x180030147  pop     rdi
0x180030148  pop     rbx
0x180030149  retn
0x18003014a  lea     r8, aOnecoreuapEndu_4; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180030151  lea     edx, [rax+49h]; void *
0x180030154  mov     rcx, rdi; this
0x180030157  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

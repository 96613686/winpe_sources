# NetSetupSvcDeviceManager::SynchronizeNetworkInterfaces(details::WorkStateTracker &,bool &)

- ea: `0x180022e88`
- end: `0x180022fcb`
- name: `?SynchronizeNetworkInterfaces@NetSetupSvcDeviceManager@@AEAAXAEAVWorkStateTracker@details@@AEA_N@Z`
- size: `323`
- prototype: `void __fastcall(NetSetupSvcDeviceManager *this, RTL_SRWLOCK **, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18001ae54`

## callees

- `0x1800078f8`
- `0x180008eb8`
- `0x18001ae20`
- `0x18001cf10`
- `0x180022e30`
- `0x180022e5c`
- `0x180022e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022eaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022eaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022f81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022eb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022eb5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022f5f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180022f5f`

## pseudocode

```c
void __fastcall NetSetupSvcDeviceManager::SynchronizeNetworkInterfaces(
        NetSetupSvcDeviceManager *this,
        RTL_SRWLOCK **a2,
        bool *a3)
{
  RTL_SRWLOCK *v6; // rbx
  void *v7; // rdx
  void *v8; // rdx
  int v9; // ebx
  int v10; // eax
  bool v11; // al
  RTL_SRWLOCK *v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  void *v14; // rdx
  char v15; // bl
  __int128 v16; // [rsp+20h] [rbp-38h] BYREF
  char v17[40]; // [rsp+30h] [rbp-28h] BYREF

  do
  {
    *a3 = 0;
    v6 = *a2 + 3;
    AcquireSRWLockExclusive(v6);
    *(_QWORD *)&v16 = v6;
    LODWORD((*a2)->Ptr) = GetCurrentThreadId();
    wil::details::ResetEvent((wil::details *)(*a2)[2].Ptr, v7);
    wil::details::SetEvent((wil::details *)(*a2)[1].Ptr, v8);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    v9 = 0;
    while ( !*a3 )
    {
      *a3 = 1;
      v16 = *(_OWORD *)lambda_a0274ed53b49f1b1a31b51d4c91c6c4a_::_lambda_a0274ed53b49f1b1a31b51d4c91c6c4a_(
                         v17,
                         this,
                         a3);
      v10 = NetSetupExecuteInFrame__lambda_d0ad30ac51f536f6cc7d702066d3f3b6_(&v16);
      if ( v10 >= 0 )
      {
        v11 = *a3;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
            (unsigned int)v10);
        *a3 = 0;
        v11 = 0;
      }
      if ( v9 != 1 || v11 )
      {
        if ( ++v9 >= 3 )
          break;
      }
      else
      {
        Sleep(0x1F4u);
        v9 = 2;
      }
    }
    v12 = *a2 + 3;
    AcquireSRWLockExclusive(v12);
    v13 = *a2;
    *(_QWORD *)&v16 = v12;
    wil::details::SetEvent((wil::details *)v13[2].Ptr, v14);
    if ( LODWORD((*a2)->Ptr) == 1 )
    {
      v15 = 0;
    }
    else
    {
      LODWORD((*a2)->Ptr) = 0;
      v15 = 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  }
  while ( !v15 );
}

```

## disassembly

```asm
0x180022e88  mov     [rsp+arg_18], rbx
0x180022e8d  push    rbp
0x180022e8e  push    rsi
0x180022e8f  push    rdi
0x180022e90  sub     rsp, 40h
0x180022e94  mov     rdi, r8
0x180022e97  mov     rsi, rdx
0x180022e9a  mov     rbp, rcx
0x180022e9d  mov     byte ptr [rdi], 0
0x180022ea0  mov     rbx, [rsi]
0x180022ea3  add     rbx, 18h
0x180022ea7  mov     rcx, rbx; SRWLock
0x180022eaa  call    cs:__imp_AcquireSRWLockExclusive
0x180022eb0  mov     qword ptr [rsp+58h+var_38], rbx
0x180022eb5  call    cs:__imp_GetCurrentThreadId
0x180022ebb  mov     rcx, [rsi]
0x180022ebe  mov     [rcx], eax
0x180022ec0  mov     rcx, [rsi]
0x180022ec3  mov     rcx, [rcx+10h]; this
0x180022ec7  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x180022ecc  mov     rcx, [rsi]
0x180022ecf  mov     rcx, [rcx+8]; this
0x180022ed3  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180022ed8  lea     rcx, [rsp+58h+var_38]
0x180022edd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022ee2  xor     ebx, ebx
0x180022ee4  cmp     byte ptr [rdi], 0
0x180022ee7  jnz     loc_180022F77
0x180022eed  mov     r8, rdi
0x180022ef0  mov     byte ptr [rdi], 1
0x180022ef3  mov     rdx, rbp
0x180022ef6  lea     rcx, [rsp+58h+var_28]
0x180022efb  call    _lambda_a0274ed53b49f1b1a31b51d4c91c6c4a____lambda_a0274ed53b49f1b1a31b51d4c91c6c4a_
0x180022f00  lea     rcx, [rsp+58h+var_38]
0x180022f05  movups  xmm0, xmmword ptr [rax]
0x180022f08  movdqu  [rsp+58h+var_38], xmm0
0x180022f0e  call    NetSetupExecuteInFrame__lambda_d0ad30ac51f536f6cc7d702066d3f3b6___; NetSetupExecuteInFrame__lambda_d0ad30ac51f536f6cc7d702066d3f3b6_
0x180022f13  test    eax, eax
0x180022f15  jns     short loc_180022F4F
0x180022f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180022f1e  lea     rdx, WPP_GLOBAL_Control
0x180022f25  cmp     rcx, rdx
0x180022f28  jz      short loc_180022F48
0x180022f2a  cmp     byte ptr [rcx+19h], 3
0x180022f2e  jb      short loc_180022F48
0x180022f30  mov     rcx, [rcx+10h]
0x180022f34  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180022f3b  mov     edx, 13h
0x180022f40  mov     r9d, eax
0x180022f43  call    WPP_SF_d
0x180022f48  mov     byte ptr [rdi], 0
0x180022f4b  xor     al, al
0x180022f4d  jmp     short loc_180022F51
0x180022f4f  mov     al, [rdi]
0x180022f51  cmp     ebx, 1
0x180022f54  jnz     short loc_180022F6C
0x180022f56  test    al, al
0x180022f58  jnz     short loc_180022F6C
0x180022f5a  mov     ecx, 1F4h; dwMilliseconds
0x180022f5f  call    cs:__imp_Sleep
0x180022f65  inc     ebx
0x180022f67  jmp     loc_180022EE4
0x180022f6c  inc     ebx
0x180022f6e  cmp     ebx, 3
0x180022f71  jl      loc_180022EE4
0x180022f77  mov     rbx, [rsi]
0x180022f7a  add     rbx, 18h
0x180022f7e  mov     rcx, rbx; SRWLock
0x180022f81  call    cs:__imp_AcquireSRWLockExclusive
0x180022f87  mov     rcx, [rsi]
0x180022f8a  mov     qword ptr [rsp+58h+var_38], rbx
0x180022f8f  mov     rcx, [rcx+10h]; this
0x180022f93  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x180022f98  mov     rax, [rsi]
0x180022f9b  cmp     dword ptr [rax], 1
0x180022f9e  jnz     short loc_180022FA4
0x180022fa0  xor     bl, bl
0x180022fa2  jmp     short loc_180022FAC
0x180022fa4  mov     dword ptr [rax], 0
0x180022faa  mov     bl, 1
0x180022fac  lea     rcx, [rsp+58h+var_38]
0x180022fb1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022fb6  test    bl, bl
0x180022fb8  jz      loc_180022E9D
0x180022fbe  mov     rbx, [rsp+58h+arg_18]
0x180022fc3  add     rsp, 40h
0x180022fc7  pop     rdi
0x180022fc8  pop     rsi
0x180022fc9  pop     rbp
0x180022fca  retn
```

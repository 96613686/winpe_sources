# NetSetupLegacyPlugin::LoadNotifyObject(StackLock &,_GUID const &,_GUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,NetSetupObjectId const &)

- ea: `0x18005a654`
- end: `0x18005a79e`
- name: `?LoadNotifyObject@NetSetupLegacyPlugin@@QEAAXAEAVStackLock@@AEBU_GUID@@1AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBUNetSetupObjectId@@@Z`
- size: `330`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800170b4`

## callees

- `0x180033600`
- `0x180037858`
- `0x180037e40`
- `0x18005097c`
- `0x18005a654`
- `0x180065035`
- `0x18006ab04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a6ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a6ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a768`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005a6b6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18005a6b6`

## pseudocode

```c
void __fastcall NetSetupLegacyPlugin::LoadNotifyObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rbx
  __int64 v11; // rdi
  int v12; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  _QWORD v15[9]; // [rsp+30h] [rbp-158h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+78h] [rbp-110h] BYREF

  v15[6] = -2;
  if ( *(_DWORD *)(a1 + 32) == 3 )
  {
    v10 = *(unsigned int *)(a1 + 36);
    v15[7] = a2;
    v15[8] = v10;
    v11 = a2 + 8;
    RtlSrwLock::AcquireExclusive((RtlSrwLock *)(a2 + 8));
    **(_QWORD **)(a2 + 24) = v10;
    *(_DWORD *)(v11 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v11);
    WakeAllConditionVariable((PCONDITION_VARIABLE)a2);
    v15[0] = a1;
    v15[1] = a3;
    v15[2] = a4;
    v15[3] = a5;
    v15[4] = a6;
    v12 = NetSetupLegacyPlugin::InvokeRpcWithTimeout__lambda_8eb9db8e2684fa97bba02ec0f50b13de___(a1, v15);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF__guid_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids,
          a4,
          v12);
      HResultException::HResultException((HResultException *)pExceptionObject, v12);
      throw (HResultException *)pExceptionObject;
    }
    *(_DWORD *)(a1 + 32) = 4;
    RtlSrwLock::AcquireExclusive((RtlSrwLock *)v11);
    while ( 1 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *(_QWORD *)(a2 + 24);
      if ( *(_DWORD *)(v14 + 12) == CurrentThreadId )
        break;
      RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, (PSRWLOCK)v11);
    }
    *(_QWORD *)v14 = 0;
    *(_DWORD *)(v11 + 8) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v11);
  }
}

```

## disassembly

```asm
0x18005a654  push    rbx
0x18005a656  push    rbp
0x18005a657  push    rsi
0x18005a658  push    rdi
0x18005a659  push    r14
0x18005a65b  push    r15
0x18005a65d  sub     rsp, 158h
0x18005a664  mov     [rsp+188h+var_128], 0FFFFFFFFFFFFFFFEh
0x18005a66d  mov     r14, r9
0x18005a670  mov     r15, r8
0x18005a673  mov     rsi, rdx
0x18005a676  mov     rbp, rcx
0x18005a679  cmp     dword ptr [rcx+20h], 3
0x18005a67d  jnz     loc_18005A78E
0x18005a683  mov     ebx, [rcx+24h]
0x18005a686  mov     [rsp+188h+var_120], rdx
0x18005a68b  mov     [rsp+188h+var_118], rbx
0x18005a690  lea     rdi, [rdx+8]
0x18005a694  mov     rcx, rdi; this
0x18005a697  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18005a69c  mov     rax, [rsi+18h]
0x18005a6a0  mov     [rax], rbx
0x18005a6a3  mov     dword ptr [rdi+8], 0
0x18005a6aa  mov     rcx, rdi; SRWLock
0x18005a6ad  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a6b3  mov     rcx, rsi; ConditionVariable
0x18005a6b6  call    cs:__imp_WakeAllConditionVariable
0x18005a6bc  nop
0x18005a6bd  mov     [rsp+188h+var_158], rbp
0x18005a6c2  mov     [rsp+188h+var_150], r15
0x18005a6c7  mov     [rsp+188h+var_148], r14
0x18005a6cc  mov     rax, [rsp+188h+arg_20]
0x18005a6d4  mov     [rsp+188h+var_140], rax
0x18005a6d9  mov     rax, [rsp+188h+arg_28]
0x18005a6e1  mov     [rsp+188h+var_138], rax
0x18005a6e6  lea     rdx, [rsp+188h+var_158]
0x18005a6eb  mov     rcx, rbp
0x18005a6ee  call    NetSetupLegacyPlugin__InvokeRpcWithTimeout__lambda_8eb9db8e2684fa97bba02ec0f50b13de___
0x18005a6f3  mov     ebx, eax
0x18005a6f5  test    eax, eax
0x18005a6f7  jns     short loc_18005A74C
0x18005a6f9  lea     rax, WPP_GLOBAL_Control
0x18005a700  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a707  cmp     rcx, rax
0x18005a70a  jz      short loc_18005A72E
0x18005a70c  cmp     byte ptr [rcx+19h], 2
0x18005a710  jb      short loc_18005A72E
0x18005a712  mov     edx, 0Ah
0x18005a717  mov     [rsp+188h+var_168], ebx
0x18005a71b  mov     r9, r14
0x18005a71e  lea     r8, WPP_03481c4866a73467b9fbae87b5f6f576_Traceguids
0x18005a725  mov     rcx, [rcx+10h]
0x18005a729  call    WPP_SF__guid_D
0x18005a72e  mov     edx, ebx; int
0x18005a730  lea     rcx, [rsp+188h+pExceptionObject]; this
0x18005a735  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18005a73a  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18005a741  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x18005a746  call    _CxxThrowException_0
0x18005a74c  mov     dword ptr [rbp+20h], 4
0x18005a753  mov     rcx, rdi; this
0x18005a756  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18005a75b  jmp     short loc_18005A768
0x18005a75d  mov     rdx, rdi; SRWLock
0x18005a760  mov     rcx, rsi; ConditionVariable
0x18005a763  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18005a768  call    cs:__imp_GetCurrentThreadId
0x18005a76e  mov     rcx, [rsi+18h]
0x18005a772  cmp     [rcx+0Ch], eax
0x18005a775  jnz     short loc_18005A75D
0x18005a777  mov     qword ptr [rcx], 0
0x18005a77e  mov     dword ptr [rdi+8], 0
0x18005a785  mov     rcx, rdi; SRWLock
0x18005a788  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a78e  add     rsp, 158h
0x18005a795  pop     r15
0x18005a797  pop     r14
0x18005a799  pop     rdi
0x18005a79a  pop     rsi
0x18005a79b  pop     rbp
0x18005a79c  pop     rbx
0x18005a79d  retn
```

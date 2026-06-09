# InternalSinkMessageDispatcher::_BroadcastSinkMessage_ICallsStateChangeSink__lambda_92d415eeddfd7392f1ad88e9977be355___

- ea: `0x18000dfe0`
- end: `0x18000e19b`
- name: `InternalSinkMessageDispatcher::_BroadcastSinkMessage_ICallsStateChangeSink__lambda_92d415eeddfd7392f1ad88e9977be355___`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800454bc`

## callees

- `0x18000dfe0`
- `0x18000e1a4`
- `0x18000ec5c`
- `0x18000ec68`
- `0x18000f9f4`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e024`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e166`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e0ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e0ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e104`

## pseudocode

```c
void __fastcall InternalSinkMessageDispatcher::_BroadcastSinkMessage_ICallsStateChangeSink__lambda_92d415eeddfd7392f1ad88e9977be355___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  __int64 v5; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 *v11; // r14
  __int64 v12; // r15
  __int64 v13; // rsi
  unsigned __int64 v14; // rsi
  __int64 v15; // rbp
  __int64 v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // [rsp+30h] [rbp-58h] BYREF
  __int64 v23; // [rsp+38h] [rbp-50h]
  __int64 v24; // [rsp+40h] [rbp-48h]

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 200);
  v5 = -1;
  v22 = -1;
  v24 = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 200));
  if ( *(_DWORD *)(a1 + 192) )
  {
    Log_AssertionEvent_0(v9, v8, 145);
    if ( *(_DWORD *)(a1 + 192) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v11 = *(__int64 **)a2;
  v12 = -1;
  v13 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  v23 = -1;
  v14 = v13 >> 3;
  if ( v14 )
  {
    if ( v14 >= 0x1000000000000000LL
      || !(unsigned __int8)utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(&v22) )
    {
      Log_HREvent_2(2147942414LL, 0, v10, 151);
      LeaveCriticalSection(v3);
      goto LABEL_20;
    }
    v11 = *(__int64 **)a2;
    v12 = v23;
    v5 = v22;
  }
  v15 = 0;
  if ( v14 )
  {
    do
    {
      v16 = *v11;
      *(_QWORD *)(v12 + 8 * v15) = *v11;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      ++v11;
      ++v15;
    }
    while ( v15 != v14 );
  }
  v17 = v12 + 8 * v14;
  v23 = v17;
  LeaveCriticalSection(v3);
  if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_0(v19, v18, 157);
    if ( *(_DWORD *)(a1 + 216) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  while ( v5 != v17 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v5 + 24LL))(
            *(_QWORD *)v5,
            *(_QWORD *)a3,
            **(unsigned int **)(a3 + 8));
    if ( v20 < 0 )
      Log_HREvent_2((unsigned int)v20, 0, v21, 170);
    v5 += 8;
  }
LABEL_20:
  utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v22);
}

```

## disassembly

```asm
0x18000dfe0  mov     [rsp+arg_0], rbx
0x18000dfe5  push    rbp
0x18000dfe6  push    rsi
0x18000dfe7  push    rdi
0x18000dfe8  push    r12
0x18000dfea  push    r13
0x18000dfec  push    r14
0x18000dfee  push    r15
0x18000dff0  sub     rsp, 50h
0x18000dff4  mov     rax, cs:__security_cookie
0x18000dffb  xor     rax, rsp
0x18000dffe  mov     [rsp+88h+var_40], rax
0x18000e003  lea     rdi, [rcx+0C8h]
0x18000e00a  mov     r13, rcx
0x18000e00d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e011  mov     rcx, rdi; lpCriticalSection
0x18000e014  mov     r12, r8
0x18000e017  mov     [rsp+88h+var_58], rbx
0x18000e01c  mov     rbp, rdx
0x18000e01f  mov     [rsp+88h+var_48], rbx
0x18000e024  call    cs:__imp_EnterCriticalSection
0x18000e02a  cmp     dword ptr [r13+0C0h], 0
0x18000e032  jz      short loc_18000E04E
0x18000e034  mov     r8d, 91h
0x18000e03a  call    Log_AssertionEvent_0
0x18000e03f  cmp     dword ptr [r13+0C0h], 0
0x18000e047  jz      short loc_18000E04E
0x18000e049  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e04e  mov     r14, [rbp+0]
0x18000e052  mov     r15, rbx
0x18000e055  mov     rsi, [rbp+8]
0x18000e059  sub     rsi, r14
0x18000e05c  mov     [rsp+88h+var_50], rbx
0x18000e061  sar     rsi, 3
0x18000e065  test    rsi, rsi
0x18000e068  jz      short loc_18000E0AD
0x18000e06a  cmp     rsi, 8
0x18000e06e  jbe     short loc_18000E088
0x18000e070  mov     rax, 0FFFFFFFFFFFFFFFh
0x18000e07a  cmp     rsi, rax
0x18000e07d  ja      loc_18000E151
0x18000e083  mov     rdx, rsi
0x18000e086  jmp     short loc_18000E08D
0x18000e088  mov     edx, 8
0x18000e08d  lea     rcx, [rsp+88h+var_58]
0x18000e092  call    ?_SetCapacity@?$vector@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(unsigned __int64)
0x18000e097  test    al, al
0x18000e099  jz      loc_18000E151
0x18000e09f  mov     r14, [rbp+0]
0x18000e0a3  mov     r15, [rsp+88h+var_50]
0x18000e0a8  mov     rbx, [rsp+88h+var_58]
0x18000e0ad  xor     ebp, ebp
0x18000e0af  test    rsi, rsi
0x18000e0b2  jz      short loc_18000E0D8
0x18000e0b4  mov     rcx, [r14]
0x18000e0b7  mov     [r15+rbp*8], rcx
0x18000e0bb  test    rcx, rcx
0x18000e0be  jz      short loc_18000E0CC
0x18000e0c0  mov     rax, [rcx]
0x18000e0c3  mov     rax, [rax+8]
0x18000e0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0cc  add     r14, 8
0x18000e0d0  inc     rbp
0x18000e0d3  cmp     rbp, rsi
0x18000e0d6  jnz     short loc_18000E0B4
0x18000e0d8  lea     rsi, [r15+rsi*8]
0x18000e0dc  mov     rcx, rdi; lpCriticalSection
0x18000e0df  mov     [rsp+88h+var_50], rsi
0x18000e0e4  call    cs:__imp_LeaveCriticalSection
0x18000e0ea  call    cs:__imp_GetCurrentThreadId
0x18000e0f0  cmp     [r13+0D8h], eax
0x18000e0f7  jnz     short loc_18000E118
0x18000e0f9  mov     r8d, 9Dh
0x18000e0ff  call    Log_AssertionEvent_0
0x18000e104  call    cs:__imp_GetCurrentThreadId
0x18000e10a  cmp     [r13+0D8h], eax
0x18000e111  jnz     short loc_18000E118
0x18000e113  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e118  cmp     rbx, rsi
0x18000e11b  jz      short loc_18000E16C
0x18000e11d  mov     rcx, [rbx]
0x18000e120  mov     r8, [r12+8]
0x18000e125  mov     rdx, [r12]
0x18000e129  mov     rax, [rcx]
0x18000e12c  mov     r8d, [r8]
0x18000e12f  mov     rax, [rax+18h]
0x18000e133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e138  test    eax, eax
0x18000e13a  jns     short loc_18000E14B
0x18000e13c  xor     edx, edx
0x18000e13e  mov     r9d, 0AAh
0x18000e144  mov     ecx, eax
0x18000e146  call    Log_HREvent_2
0x18000e14b  add     rbx, 8
0x18000e14f  jmp     short loc_18000E118
0x18000e151  xor     edx, edx
0x18000e153  mov     ecx, 8007000Eh
0x18000e158  mov     r9d, 97h
0x18000e15e  call    Log_HREvent_2
0x18000e163  mov     rcx, rdi; lpCriticalSection
0x18000e166  call    cs:__imp_LeaveCriticalSection
0x18000e16c  lea     rcx, [rsp+88h+var_58]
0x18000e171  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x18000e176  mov     rcx, [rsp+88h+var_40]
0x18000e17b  xor     rcx, rsp; StackCookie
0x18000e17e  call    __security_check_cookie
0x18000e183  mov     rbx, [rsp+88h+arg_0]
0x18000e18b  add     rsp, 50h
0x18000e18f  pop     r15
0x18000e191  pop     r14
0x18000e193  pop     r13
0x18000e195  pop     r12
0x18000e197  pop     rdi
0x18000e198  pop     rsi
0x18000e199  pop     rbp
0x18000e19a  retn
```

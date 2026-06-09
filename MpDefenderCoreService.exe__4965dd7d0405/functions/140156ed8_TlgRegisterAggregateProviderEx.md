# TlgRegisterAggregateProviderEx

- ea: `0x140156ed8`
- end: `0x1401570e4`
- name: `TlgRegisterAggregateProviderEx`
- size: `524`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140083910`

## callees

- `0x140003954`
- `0x140017adc`
- `0x14015672c`
- `0x140156ed8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1401570a1`
- `KERNEL32!HeapFree` at `0x1401570c1`
- `KERNEL32!HeapFree` at `0x1401570a1`
- `KERNEL32!HeapFree` at `0x1401570c1`
- `KERNEL32!HeapAlloc` at `0x140156f03`
- `KERNEL32!HeapAlloc` at `0x140156f03`
- `KERNEL32!GetProcessHeap` at `0x140156eef`
- `KERNEL32!GetProcessHeap` at `0x140157093`
- `KERNEL32!GetProcessHeap` at `0x1401570b3`
- `KERNEL32!GetProcessHeap` at `0x140156eef`
- `KERNEL32!GetProcessHeap` at `0x140157093`
- `KERNEL32!GetProcessHeap` at `0x1401570b3`
- `KERNEL32!InitializeSRWLock` at `0x140156f1c`
- `KERNEL32!InitializeSRWLock` at `0x140156f1c`
- `KERNEL32!CreateThreadpoolTimer` at `0x140156f3c`
- `KERNEL32!CreateThreadpoolTimer` at `0x140156f3c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14015701f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14015701f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140157079`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140157079`

## pseudocode

```c
__int64 __fastcall TlgRegisterAggregateProviderEx(PVOID CallbackContext, __int64 a2, unsigned __int64 a3)
{
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v5; // rax
  unsigned __int64 v6; // rbx
  CommonUtil *v7; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned int v9; // edx
  __int128 v10; // xmm0
  unsigned __int64 v11; // r8
  int v12; // eax
  unsigned __int64 i; // r8
  int v14; // eax
  int v15; // esi
  __int64 v16; // rax
  __int64 *v17; // rcx
  HANDLE v19; // rax
  HANDLE v20; // rax
  __int128 v21; // [rsp+20h] [rbp-18h]
  unsigned __int64 v22; // [rsp+50h] [rbp+18h]

  v22 = a3;
  ProcessHeap = GetProcessHeap();
  v5 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v6 = (unsigned __int64)v5;
  if ( !v5 )
    return TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
  InitializeSRWLock(v5 + 33);
  if ( CommonUtil::IsDuringProcessShutdown(v7)
    || (ThreadpoolTimer = CreateThreadpoolTimer(FlushTimerCallbackUserMode, (PVOID)v6, 0),
        (*(_QWORD *)(v6 + 344) = ThreadpoolTimer) == 0) )
  {
    CancelTimerCallbacksAndDeleteTimer((PTP_TIMER *)v6);
    v20 = GetProcessHeap();
    HeapFree(v20, 0, (LPVOID)v6);
    return TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
  }
  *(_QWORD *)(v6 + 312) = 0;
  v9 = 0;
  *(_QWORD *)(v6 + 320) = 0;
  *(_QWORD *)(v6 + 328) = CallbackContext;
  v10 = *(_OWORD *)(*((_QWORD *)CallbackContext + 1) - 16LL);
  v22 = v6 >> 4;
  v11 = 0;
  v21 = v10;
  do
  {
    v12 = *((unsigned __int8 *)&v21 + v11++);
    v9 = (1025 * (v9 + v12)) ^ ((1025 * (v9 + v12)) >> 6);
  }
  while ( v11 < 0x10 );
  for ( i = 0; i < 8; ++i )
  {
    v14 = *((unsigned __int8 *)&v22 + i);
    v9 = (1025 * (v9 + v14)) ^ ((1025 * (v9 + v14)) >> 6);
  }
  *(_DWORD *)(v6 + 352) = 32769 * ((9 * v9) ^ ((9 * v9) >> 11)) % 0x927C0 + 600000;
  v15 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
  if ( v15 < 0 )
  {
    *((_QWORD *)CallbackContext + 5) = 0;
    CancelTimerCallbacksAndDeleteTimer((PTP_TIMER *)v6);
    v19 = GetProcessHeap();
    HeapFree(v19, 0, (LPVOID)v6);
    return (unsigned int)v15;
  }
  else
  {
    AcquireSRWLockExclusive(&stru_1401E75C0);
    v16 = qword_1401E75C8;
    if ( !qword_1401E75C8 )
    {
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1401D96A0);
      v16 = qword_1401E75C8;
    }
    v17 = &qword_1401E75C8;
    while ( v16 )
    {
      if ( *(PVOID *)(v16 + 328) == CallbackContext )
        goto LABEL_16;
      v17 = (__int64 *)(v16 + 336);
      v16 = *(_QWORD *)(v16 + 336);
    }
    *v17 = v6;
LABEL_16:
    ReleaseSRWLockExclusive(&stru_1401E75C0);
    return 0;
  }
}

```

## disassembly

```asm
0x140156ed8  mov     [rsp+arg_0], rbx
0x140156edd  mov     [rsp+arg_8], rsi
0x140156ee2  mov     [rsp+arg_10], r8
0x140156ee7  push    rdi
0x140156ee8  sub     rsp, 30h
0x140156eec  mov     rdi, rcx
0x140156eef  call    cs:__imp_GetProcessHeap
0x140156ef5  mov     edx, 8; dwFlags
0x140156efa  mov     r8d, 168h; dwBytes
0x140156f00  mov     rcx, rax; hHeap
0x140156f03  call    cs:__imp_HeapAlloc
0x140156f09  mov     rbx, rax
0x140156f0c  test    rax, rax
0x140156f0f  jz      loc_1401570C7
0x140156f15  lea     rcx, [rax+108h]; SRWLock
0x140156f1c  call    cs:__imp_InitializeSRWLock
0x140156f22  call    ?IsDuringProcessShutdown@CommonUtil@@YA_NXZ; CommonUtil::IsDuringProcessShutdown(void)
0x140156f27  test    al, al
0x140156f29  jnz     loc_1401570AB
0x140156f2f  xor     r8d, r8d; pcbe
0x140156f32  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x140156f39  mov     rdx, rbx; pv
0x140156f3c  call    cs:__imp_CreateThreadpoolTimer
0x140156f42  mov     [rbx+158h], rax
0x140156f49  test    rax, rax
0x140156f4c  jz      loc_1401570AB
0x140156f52  mov     qword ptr [rbx+138h], 0
0x140156f5d  xor     edx, edx
0x140156f5f  mov     qword ptr [rbx+140h], 0
0x140156f6a  mov     [rbx+148h], rdi
0x140156f71  mov     rax, [rdi+8]
0x140156f75  movups  xmm0, xmmword ptr [rax-10h]
0x140156f79  mov     rax, rbx
0x140156f7c  shr     rax, 4
0x140156f80  mov     [rsp+38h+arg_10], rax
0x140156f85  xor     r8d, r8d
0x140156f88  movdqu  [rsp+38h+var_18], xmm0
0x140156f8e  movzx   eax, byte ptr [rsp+r8+38h+var_18]
0x140156f94  inc     r8
0x140156f97  add     eax, edx
0x140156f99  imul    ecx, eax, 401h
0x140156f9f  mov     edx, ecx
0x140156fa1  shr     edx, 6
0x140156fa4  xor     edx, ecx
0x140156fa6  cmp     r8, 10h
0x140156faa  jb      short loc_140156F8E
0x140156fac  xor     r8d, r8d
0x140156faf  movzx   eax, byte ptr [rsp+r8+38h+arg_10]
0x140156fb5  inc     r8
0x140156fb8  add     eax, edx
0x140156fba  imul    ecx, eax, 401h
0x140156fc0  mov     edx, ecx
0x140156fc2  shr     edx, 6
0x140156fc5  xor     edx, ecx
0x140156fc7  cmp     r8, 8
0x140156fcb  jb      short loc_140156FAF
0x140156fcd  lea     eax, [rdx+rdx*8]
0x140156fd0  mov     ecx, eax
0x140156fd2  shr     ecx, 0Bh
0x140156fd5  xor     ecx, eax
0x140156fd7  mov     eax, 6FD91D85h
0x140156fdc  imul    r8d, ecx, 8001h
0x140156fe3  mov     rcx, rdi; CallbackContext
0x140156fe6  mul     r8d
0x140156fe9  shr     edx, 12h
0x140156fec  imul    eax, edx, 927C0h
0x140156ff2  lea     rdx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140156ff9  sub     r8d, eax
0x140156ffc  add     r8d, 927C0h
0x140157003  mov     [rbx+160h], r8d
0x14015700a  mov     r8, rbx
0x14015700d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140157012  mov     esi, eax
0x140157014  test    eax, eax
0x140157016  js      short loc_140157083
0x140157018  lea     rcx, stru_1401E75C0; SRWLock
0x14015701f  call    cs:__imp_AcquireSRWLockExclusive
0x140157025  mov     rax, cs:qword_1401E75C8
0x14015702c  test    rax, rax
0x14015702f  jnz     short loc_14015704E
0x140157031  xor     r8d, r8d
0x140157034  lea     rdx, ?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14015703b  lea     rcx, dword_1401D96A0; CallbackContext
0x140157042  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140157047  mov     rax, cs:qword_1401E75C8
0x14015704e  lea     rcx, qword_1401E75C8
0x140157055  jmp     short loc_14015706A
0x140157057  cmp     [rax+148h], rdi
0x14015705e  jz      short loc_140157072
0x140157060  lea     rcx, [rax+150h]
0x140157067  mov     rax, [rcx]
0x14015706a  test    rax, rax
0x14015706d  jnz     short loc_140157057
0x14015706f  mov     [rcx], rbx
0x140157072  lea     rcx, stru_1401E75C0; SRWLock
0x140157079  call    cs:__imp_ReleaseSRWLockExclusive
0x14015707f  xor     eax, eax
0x140157081  jmp     short loc_1401570D4
0x140157083  mov     rcx, rbx
0x140157086  mov     qword ptr [rdi+28h], 0
0x14015708e  call    CancelTimerCallbacksAndDeleteTimer
0x140157093  call    cs:__imp_GetProcessHeap
0x140157099  mov     r8, rbx; lpMem
0x14015709c  xor     edx, edx; dwFlags
0x14015709e  mov     rcx, rax; hHeap
0x1401570a1  call    cs:__imp_HeapFree
0x1401570a7  mov     eax, esi
0x1401570a9  jmp     short loc_1401570D4
0x1401570ab  mov     rcx, rbx
0x1401570ae  call    CancelTimerCallbacksAndDeleteTimer
0x1401570b3  call    cs:__imp_GetProcessHeap
0x1401570b9  mov     r8, rbx; lpMem
0x1401570bc  xor     edx, edx; dwFlags
0x1401570be  mov     rcx, rax; hHeap
0x1401570c1  call    cs:__imp_HeapFree
0x1401570c7  xor     r8d, r8d
0x1401570ca  xor     edx, edx
0x1401570cc  mov     rcx, rdi; CallbackContext
0x1401570cf  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1401570d4  mov     rbx, [rsp+38h+arg_0]
0x1401570d9  mov     rsi, [rsp+38h+arg_8]
0x1401570de  add     rsp, 30h
0x1401570e2  pop     rdi
0x1401570e3  retn
```

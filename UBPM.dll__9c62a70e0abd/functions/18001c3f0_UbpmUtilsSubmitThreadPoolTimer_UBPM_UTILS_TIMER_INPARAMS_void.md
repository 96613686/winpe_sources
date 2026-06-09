# UbpmUtilsSubmitThreadPoolTimer(_UBPM_UTILS_TIMER_INPARAMS *,void * *)

- ea: `0x18001c3f0`
- end: `0x18001c875`
- name: `?UbpmUtilsSubmitThreadPoolTimer@@YAKPEAU_UBPM_UTILS_TIMER_INPARAMS@@PEAPEAX@Z`
- size: `1157`
- prototype: `unsigned int __fastcall(struct _UBPM_UTILS_TIMER_INPARAMS *, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d9bc`
- `0x18001b07c`
- `0x18001c160`
- `0x18001c2e8`

## callees

- `0x1800150c0`
- `0x18001c3f0`
- `0x1800351ec`
- `0x180040222`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001c595`
- `ntdll!RtlFreeHeap` at `0x18001c595`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18001c4c1`
- `ntdll!RtlTryAcquireSRWLockShared` at `0x18001c4c1`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c690`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001c690`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c567`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c567`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c4ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c4ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c805`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c6a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c6dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c6a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c6dc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c79a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c79a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c749`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001c749`

## pseudocode

```c
__int64 __fastcall UbpmUtilsSubmitThreadPoolTimer(struct _UBPM_UTILS_TIMER_INPARAMS *a1, PTP_TIMER *a2)
{
  char v2; // r14
  struct _FILETIME *v5; // rax
  struct _FILETIME v6; // rax
  unsigned __int64 v7; // rdx
  _DWORD *v8; // rdi
  __int64 v9; // r15
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // r14
  void *v11; // rsi
  char v12; // r12
  PTP_TIMER ThreadpoolTimer; // r14
  char v14; // cl
  struct _FILETIME *p_SystemTimeAsFileTime; // rdx
  DWORD LastError; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD dwLowDateTime; // ecx
  FILETIME FileTime1; // [rsp+70h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+48h] BYREF
  struct _FILETIME FileTime; // [rsp+88h] [rbp+50h] BYREF

  SystemTimeAsFileTime = 0;
  v2 = 0;
  FileTime1 = 0;
  FileTime = 0;
  v5 = (struct _FILETIME *)*((_QWORD *)a1 + 7);
  if ( v5 )
  {
    v6 = *v5;
    SystemTimeAsFileTime = v6;
  }
  else
  {
    if ( *((_BYTE *)a1 + 36) )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v6 = (struct _FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 10000000 * (*((unsigned int *)a1 + 8) + 1LL));
    }
    else
    {
      v2 = 1;
      v6 = (struct _FILETIME)(-10000000LL * *((unsigned int *)a1 + 8));
    }
    SystemTimeAsFileTime = v6;
  }
  v7 = *(_QWORD *)((char *)a1 + 68);
  if ( !v7 )
    v7 = *(_QWORD *)((char *)a1 + 76) - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( v7 )
  {
    if ( v2 )
    {
      GetSystemTimeAsFileTime(&FileTime1);
      dwLowDateTime = FileTime1.dwLowDateTime + 10000000 * *((_DWORD *)a1 + 8);
      *(_QWORD *)&FileTime1 += 10000000LL * *((unsigned int *)a1 + 8);
      v6 = FileTime1;
    }
    else
    {
      FileTime1 = v6;
      dwLowDateTime = v6.dwLowDateTime;
    }
    FileTime1 = (FILETIME)((dwLowDateTime | *(_QWORD *)&v6 & 0xFFFFFFFF00000000uLL) - 10000000);
    if ( SystemTimeToFileTime((const SYSTEMTIME *)((char *)a1 + 68), &FileTime) )
    {
      if ( CompareFileTime(&FileTime1, &FileTime) <= 0 )
        goto LABEL_8;
      LastError = 4320;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v19 = 24;
    }
    else
    {
      LastError = GetLastError();
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return LastError;
      v19 = 23;
    }
LABEL_36:
    WPP_SF_d(v18[2], v19, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
    return LastError;
  }
LABEL_8:
  v8 = UbpmAlloc((unsigned int)*((unsigned __int16 *)a1 + 12) + 48);
  if ( !v8 )
  {
    LastError = GetLastError();
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return LastError;
    v19 = 25;
    goto LABEL_36;
  }
  v9 = *((_QWORD *)a1 + 6);
  if ( v9 )
  {
    v11 = (void *)*((_QWORD *)a1 + 11);
    v12 = 0;
    v10 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)a1 + 6);
    if ( !v11 )
      goto LABEL_14;
  }
  else
  {
    v10 = &g_CallbackEnv;
    v11 = &g_TpSubmitLock;
  }
  if ( !(unsigned __int8)RtlTryAcquireSRWLockShared(v11) )
  {
    LastError = 1235;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1235);
    goto LABEL_25;
  }
  if ( !v9 && !g_pThreadpool )
  {
    LastError = 1115;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, 1115);
LABEL_39:
    RtlReleaseSRWLockShared(v11);
    goto LABEL_24;
  }
  v12 = 1;
LABEL_14:
  ThreadpoolTimer = CreateThreadpoolTimer(UbpmUtilsTimerCallback, v8, v10);
  if ( ThreadpoolTimer )
  {
    v14 = *((_BYTE *)v8 + 24);
    *v8 = 1886667349;
    *((_QWORD *)v8 + 1) = *((_QWORD *)a1 + 1);
    *((_QWORD *)v8 + 2) = *(_QWORD *)a1;
    *((_BYTE *)v8 + 24) ^= (*((_BYTE *)a1 + 28) ^ v14) & 1;
    if ( *((_WORD *)a1 + 12) )
    {
      *((_QWORD *)v8 + 4) = v8 + 12;
      memcpy_0(v8 + 12, *((const void **)a1 + 2), *((unsigned __int16 *)a1 + 12));
    }
    if ( a2 )
    {
      if ( (*((_BYTE *)a1 + 96) & 1) != 0 )
      {
        *a2 = ThreadpoolTimer;
      }
      else
      {
        *a2 = (PTP_TIMER)v8;
        *((_BYTE *)v8 + 24) |= 2u;
        *((_QWORD *)v8 + 5) = ThreadpoolTimer;
      }
    }
    p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
    v8 = 0;
    if ( *((_DWORD *)a1 + 16) )
      p_SystemTimeAsFileTime = 0;
    SetThreadpoolTimer(ThreadpoolTimer, p_SystemTimeAsFileTime, *((_DWORD *)a1 + 10), 0);
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids, LastError);
  }
  if ( v12 )
    goto LABEL_39;
LABEL_24:
  if ( v8 )
LABEL_25:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return LastError;
}

```

## disassembly

```asm
0x18001c3f0  push    rbp
0x18001c3f2  push    rbx
0x18001c3f3  push    rsi
0x18001c3f4  push    rdi
0x18001c3f5  push    r13
0x18001c3f7  push    r14
0x18001c3f9  mov     rbp, rsp
0x18001c3fc  sub     rsp, 38h
0x18001c400  xor     eax, eax
0x18001c402  movaps  [rsp+38h+var_18], xmm6
0x18001c407  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001c40b  xor     r14b, r14b
0x18001c40e  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18001c412  mov     r13, rdx
0x18001c415  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18001c419  mov     rbx, rcx
0x18001c41c  mov     rax, [rcx+38h]
0x18001c420  xorps   xmm6, xmm6
0x18001c423  test    rax, rax
0x18001c426  jnz     loc_18001C5F3
0x18001c42c  cmp     [rcx+24h], r14b
0x18001c430  jnz     loc_18001C6A1
0x18001c436  mov     eax, [rcx+20h]
0x18001c439  mov     r14b, 1
0x18001c43c  imul    rax, 0FFFFFFFFFF676980h
0x18001c443  mov     rcx, rax
0x18001c446  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x18001c449  shr     rcx, 20h
0x18001c44d  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18001c450  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001c454  mov     rdx, [rbx+44h]
0x18001c458  movq    rcx, xmm6
0x18001c45d  sub     rdx, rcx
0x18001c460  jnz     short loc_18001C473
0x18001c462  mov     rdx, [rbx+4Ch]
0x18001c466  psrldq  xmm6, 8
0x18001c46b  movq    rcx, xmm6
0x18001c470  sub     rdx, rcx
0x18001c473  movaps  xmm6, [rsp+38h+var_18]
0x18001c478  test    rdx, rdx
0x18001c47b  jnz     loc_18001C6D3
0x18001c481  movzx   ecx, word ptr [rbx+18h]
0x18001c485  add     ecx, 30h ; '0'; Size
0x18001c488  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001c48d  mov     rdi, rax
0x18001c490  test    rax, rax
0x18001c493  jz      loc_18001C617
0x18001c499  mov     [rsp+38h+arg_8], r12
0x18001c49e  mov     [rsp+38h+var_8], r15
0x18001c4a3  mov     r15, [rbx+30h]
0x18001c4a7  test    r15, r15
0x18001c4aa  jnz     loc_18001C5FF
0x18001c4b0  lea     r14, ?g_CallbackEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A; _TP_CALLBACK_ENVIRON_V3 g_CallbackEnv
0x18001c4b7  lea     rsi, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x18001c4be  mov     rcx, rsi
0x18001c4c1  call    cs:__imp_RtlTryAcquireSRWLockShared
0x18001c4c8  nop     dword ptr [rax+rax+00h]
0x18001c4cd  test    al, al
0x18001c4cf  jz      loc_18001C5BB
0x18001c4d5  test    r15, r15
0x18001c4d8  jz      loc_18001C663
0x18001c4de  mov     r12b, 1
0x18001c4e1  mov     r8, r14; pcbe
0x18001c4e4  lea     rcx, ?UbpmUtilsTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c4eb  mov     rdx, rdi; pv
0x18001c4ee  call    cs:__imp_CreateThreadpoolTimer
0x18001c4f5  nop     dword ptr [rax+rax+00h]
0x18001c4fa  mov     r14, rax
0x18001c4fd  test    rax, rax
0x18001c500  jz      loc_18001C805
0x18001c506  movzx   ecx, byte ptr [rdi+18h]
0x18001c50a  mov     dword ptr [rdi], 70744255h
0x18001c510  mov     rax, [rbx+8]
0x18001c514  mov     [rdi+8], rax
0x18001c518  mov     rax, [rbx]
0x18001c51b  mov     [rdi+10h], rax
0x18001c51f  xor     cl, [rbx+1Ch]
0x18001c522  and     cl, 1
0x18001c525  xor     [rdi+18h], cl
0x18001c528  cmp     word ptr [rbx+18h], 0
0x18001c52d  ja      loc_18001C851
0x18001c533  test    r13, r13
0x18001c536  jz      short loc_18001C54E
0x18001c538  test    byte ptr [rbx+60h], 1
0x18001c53c  jnz     loc_18001C86C
0x18001c542  mov     [r13+0], rdi
0x18001c546  or      byte ptr [rdi+18h], 2
0x18001c54a  mov     [rdi+28h], r14
0x18001c54e  mov     r8d, [rbx+28h]; msPeriod
0x18001c552  lea     rdx, [rbp+SystemTimeAsFileTime]
0x18001c556  xor     eax, eax
0x18001c558  xor     edi, edi
0x18001c55a  cmp     [rbx+40h], eax
0x18001c55d  mov     rcx, r14; pti
0x18001c560  cmovnz  rdx, rax; pftDueTime
0x18001c564  xor     r9d, r9d; msWindowLength
0x18001c567  call    cs:__imp_SetThreadpoolTimer
0x18001c56e  nop     dword ptr [rax+rax+00h]
0x18001c573  xor     ebx, ebx
0x18001c575  test    r12b, r12b
0x18001c578  jnz     loc_18001C68D
0x18001c57e  test    rdi, rdi
0x18001c581  jz      short loc_18001C5A1
0x18001c583  mov     rcx, gs:60h
0x18001c58c  mov     r8, rdi; P
0x18001c58f  xor     edx, edx; Flags
0x18001c591  mov     rcx, [rcx+30h]; HeapHandle
0x18001c595  call    cs:__imp_RtlFreeHeap
0x18001c59c  nop     dword ptr [rax+rax+00h]
0x18001c5a1  mov     r12, [rsp+38h+arg_8]
0x18001c5a6  mov     r15, [rsp+38h+var_8]
0x18001c5ab  mov     eax, ebx
0x18001c5ad  add     rsp, 38h
0x18001c5b1  pop     r14
0x18001c5b3  pop     r13
0x18001c5b5  pop     rdi
0x18001c5b6  pop     rsi
0x18001c5b7  pop     rbx
0x18001c5b8  pop     rbp
0x18001c5b9  retn
0x18001c5bb  mov     ebx, 4D3h
0x18001c5c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5c7  lea     rax, WPP_GLOBAL_Control
0x18001c5ce  cmp     rcx, rax
0x18001c5d1  jz      short loc_18001C583
0x18001c5d3  test    byte ptr [rcx+1Ch], 1
0x18001c5d7  jz      short loc_18001C583
0x18001c5d9  mov     rcx, [rcx+10h]
0x18001c5dd  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001c5e4  mov     edx, 1Ah
0x18001c5e9  mov     r9d, ebx
0x18001c5ec  call    WPP_SF_d
0x18001c5f1  jmp     short loc_18001C583
0x18001c5f3  mov     rax, [rax]
0x18001c5f6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001c5fa  jmp     loc_18001C454
0x18001c5ff  mov     rsi, [rbx+58h]
0x18001c603  xor     r12b, r12b
0x18001c606  mov     r14, r15
0x18001c609  test    rsi, rsi
0x18001c60c  jnz     loc_18001C4BE
0x18001c612  jmp     loc_18001C4E1
0x18001c617  call    cs:__imp_GetLastError
0x18001c61e  nop     dword ptr [rax+rax+00h]
0x18001c623  mov     ebx, eax
0x18001c625  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c62c  lea     rax, WPP_GLOBAL_Control
0x18001c633  cmp     rcx, rax
0x18001c636  jz      loc_18001C5AB
0x18001c63c  test    byte ptr [rcx+1Ch], 1
0x18001c640  jz      loc_18001C5AB
0x18001c646  mov     edx, 19h
0x18001c64b  mov     rcx, [rcx+10h]
0x18001c64f  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001c656  mov     r9d, ebx
0x18001c659  call    WPP_SF_d
0x18001c65e  jmp     loc_18001C5AB
0x18001c663  cmp     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x18001c66b  jnz     loc_18001C4DE
0x18001c671  mov     ebx, 45Bh
0x18001c676  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c67d  lea     rax, WPP_GLOBAL_Control
0x18001c684  cmp     rcx, rax
0x18001c687  jnz     loc_18001C7DE
0x18001c68d  mov     rcx, rsi
0x18001c690  call    cs:__imp_RtlReleaseSRWLockShared
0x18001c697  nop     dword ptr [rax+rax+00h]
0x18001c69c  jmp     loc_18001C57E
0x18001c6a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c6a5  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c6ac  nop     dword ptr [rax+rax+00h]
0x18001c6b1  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001c6b4  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18001c6b7  shl     rcx, 20h
0x18001c6bb  or      rcx, rax
0x18001c6be  mov     eax, [rbx+20h]
0x18001c6c1  inc     rax
0x18001c6c4  imul    rax, 989680h
0x18001c6cb  add     rax, rcx
0x18001c6ce  jmp     loc_18001C443
0x18001c6d3  test    r14b, r14b
0x18001c6d6  jz      short loc_18001C715
0x18001c6d8  lea     rcx, [rbp+FileTime1]; lpSystemTimeAsFileTime
0x18001c6dc  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c6e3  nop     dword ptr [rax+rax+00h]
0x18001c6e8  mov     eax, [rbp+FileTime1.dwLowDateTime]
0x18001c6eb  mov     edx, [rbp+FileTime1.dwHighDateTime]
0x18001c6ee  shl     rdx, 20h
0x18001c6f2  or      rdx, rax
0x18001c6f5  mov     eax, [rbx+20h]
0x18001c6f8  imul    rcx, rax, 989680h
0x18001c6ff  add     rcx, rdx
0x18001c702  mov     rax, rcx
0x18001c705  mov     [rbp+FileTime1.dwLowDateTime], ecx
0x18001c708  shr     rax, 20h
0x18001c70c  mov     [rbp+FileTime1.dwHighDateTime], eax
0x18001c70f  mov     rax, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18001c713  jmp     short loc_18001C71C
0x18001c715  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rax
0x18001c719  mov     ecx, [rbp+FileTime1.dwLowDateTime]
0x18001c71c  mov     rdx, 0FFFFFFFF00000000h
0x18001c726  and     rax, rdx
0x18001c729  mov     edx, ecx
0x18001c72b  or      rax, rdx
0x18001c72e  lea     rcx, [rbx+44h]; lpSystemTime
0x18001c732  add     rax, 0FFFFFFFFFF676980h
0x18001c738  mov     rdx, rax
0x18001c73b  mov     [rbp+FileTime1.dwLowDateTime], eax
0x18001c73e  shr     rdx, 20h
0x18001c742  mov     [rbp+FileTime1.dwHighDateTime], edx
0x18001c745  lea     rdx, [rbp+FileTime]; lpFileTime
0x18001c749  call    cs:__imp_SystemTimeToFileTime
0x18001c750  nop     dword ptr [rax+rax+00h]
0x18001c755  test    eax, eax
0x18001c757  jnz     short loc_18001C792
0x18001c759  call    cs:__imp_GetLastError
0x18001c760  nop     dword ptr [rax+rax+00h]
0x18001c765  mov     ebx, eax
0x18001c767  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c76e  lea     rax, WPP_GLOBAL_Control
0x18001c775  cmp     rcx, rax
0x18001c778  jz      loc_18001C5AB
0x18001c77e  test    byte ptr [rcx+1Ch], 1
0x18001c782  jz      loc_18001C5AB
0x18001c788  mov     edx, 17h
0x18001c78d  jmp     loc_18001C64B
0x18001c792  lea     rdx, [rbp+FileTime]; lpFileTime2
0x18001c796  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18001c79a  call    cs:__imp_CompareFileTime
0x18001c7a1  nop     dword ptr [rax+rax+00h]
0x18001c7a6  test    eax, eax
0x18001c7a8  jle     loc_18001C481
0x18001c7ae  mov     ebx, 10E0h
0x18001c7b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7ba  lea     rax, WPP_GLOBAL_Control
0x18001c7c1  cmp     rcx, rax
0x18001c7c4  jz      loc_18001C5AB
0x18001c7ca  test    byte ptr [rcx+1Ch], 1
0x18001c7ce  jz      loc_18001C5AB
0x18001c7d4  mov     edx, 18h
0x18001c7d9  jmp     loc_18001C64B
0x18001c7de  test    byte ptr [rcx+1Ch], 1
0x18001c7e2  jz      loc_18001C68D
0x18001c7e8  mov     rcx, [rcx+10h]
0x18001c7ec  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001c7f3  mov     edx, 1Bh
0x18001c7f8  mov     r9d, ebx
0x18001c7fb  call    WPP_SF_d
0x18001c800  jmp     loc_18001C68D
0x18001c805  call    cs:__imp_GetLastError
0x18001c80c  nop     dword ptr [rax+rax+00h]
0x18001c811  mov     ebx, eax
0x18001c813  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c81a  lea     rax, WPP_GLOBAL_Control
0x18001c821  cmp     rcx, rax
0x18001c824  jz      loc_18001C575
0x18001c82a  test    byte ptr [rcx+1Ch], 1
0x18001c82e  jz      loc_18001C575
0x18001c834  mov     rcx, [rcx+10h]
0x18001c838  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x18001c83f  mov     edx, 1Ch
0x18001c844  mov     r9d, ebx
0x18001c847  call    WPP_SF_d
0x18001c84c  jmp     loc_18001C575
0x18001c851  lea     rcx, [rdi+30h]; void *
0x18001c855  mov     [rdi+20h], rcx
0x18001c859  movzx   r8d, word ptr [rbx+18h]; Size
0x18001c85e  mov     rdx, [rbx+10h]; Src
0x18001c862  call    memcpy_0
0x18001c867  jmp     loc_18001C533
0x18001c86c  mov     [r13+0], r14
0x18001c870  jmp     loc_18001C54E
```

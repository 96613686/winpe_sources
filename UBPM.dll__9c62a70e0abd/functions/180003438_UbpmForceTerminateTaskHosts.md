# UbpmForceTerminateTaskHosts

- ea: `0x180003438`
- end: `0x1800036ca`
- name: `UbpmForceTerminateTaskHosts`
- size: `658`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180001dc0`
- `0x180003060`

## callees

- `0x180003438`
- `0x180004c30`
- `0x180010220`
- `0x1800103c0`
- `0x180032f78`
- `0x1800351ec`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x1800035be`
- `ntdll!NtWaitForSingleObject` at `0x1800035be`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003481`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003481`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800034e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003539`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800035a8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800034e7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003539`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800035a8`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000361a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000361a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000348d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000348d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000363c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000363c`

## pseudocode

```c
__int64 UbpmForceTerminateTaskHosts()
{
  volatile signed __int64 *v0; // rbx
  char v1; // si
  _UNKNOWN **v2; // rbp
  _UNKNOWN **v3; // rax
  char *v4; // rdi
  bool v5; // zf
  __int64 result; // rax
  void *v7; // rsi
  void *v8; // r14
  _QWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // rdx
  char *i; // rcx
  _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF
  _UNKNOWN **v16; // [rsp+68h] [rbp+10h] BYREF

  Timeout.QuadPart = MEMORY[0x7FFE0014] + 300000000LL;
  while ( 1 )
  {
    v0 = 0;
    v16 = 0;
    v1 = 0;
    RtlAcquireSRWLockExclusive(&g_TaskHostContextListLock);
    dword_180050018 = GetCurrentThreadId();
    v2 = 0;
    v3 = (_UNKNOWN **)g_leTaskHostContextListHead;
    v4 = 0;
    while ( v3 != &g_leTaskHostContextListHead )
    {
      v0 = (volatile signed __int64 *)(v3 - 1);
      v5 = ((_BYTE)v3[12] & 4) == 0;
      v2 = v3 - 1;
      v16 = v3 - 1;
      v4 = (char *)(v3 - 1);
      if ( v5 )
      {
        _InterlockedIncrement64(v0 + 12);
        v1 = 1;
        break;
      }
      v3 = (_UNKNOWN **)*v3;
    }
    dword_180050018 = 0;
    result = RtlReleaseSRWLockExclusive(&g_TaskHostContextListLock);
    if ( !v1 )
      return result;
    v7 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v2 + 8));
    v8 = (void *)*((_QWORD *)v4 + 3);
    if ( !v8 )
      goto LABEL_12;
    if ( v4[104] < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_11;
      v12 = *((unsigned int *)v4 + 8);
      v13 = 54;
      goto LABEL_27;
    }
    if ( *((_WORD *)v4 + 98) )
    {
      for ( i = (char *)*((_QWORD *)v4 + 25); i != v4 + 200; i = *(char **)i )
      {
        if ( *((__int64 *)i - 1) > 1 )
        {
          *((_DWORD *)v0 + 18) = 0;
          RtlReleaseSRWLockExclusive(v0 + 8);
          NtWaitForSingleObject(v8, 0, &Timeout);
          UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v2 + 8));
          break;
        }
      }
    }
    if ( v4[104] >= 0 )
    {
      if ( TerminateProcess(*((HANDLE *)v4 + 3), 0x42Bu) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
            *((unsigned int *)v0 + 8));
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
          *((unsigned int *)v0 + 8));
      }
      v4[104] |= 0x80u;
      goto LABEL_11;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = *((unsigned int *)v0 + 8);
      v13 = 55;
LABEL_27:
      WPP_SF_d(v9[2], v13, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v12);
    }
LABEL_11:
    v7 = (void *)*((_QWORD *)v0 + 5);
    *((_QWORD *)v0 + 5) = 0;
LABEL_12:
    *((_DWORD *)v0 + 18) = 0;
    RtlReleaseSRWLockExclusive(v0 + 8);
    if ( v7 )
      UbpmpTaskHostTerminationCleanup((struct _UBPM_TASK_HOST_CONTEXT_BLOCK *)v0, v7);
    UbpmpDecrementRefAndDelete((__int64 *)&v16, 1, v10, v11);
  }
}

```

## disassembly

```asm
0x180003438  mov     r11, rsp
0x18000343b  mov     [r11+18h], rbx
0x18000343f  mov     [r11+20h], rbp
0x180003443  push    rsi
0x180003444  push    rdi
0x180003445  push    r12
0x180003447  push    r14
0x180003449  push    r15
0x18000344b  sub     rsp, 30h
0x18000344f  xor     r15d, r15d
0x180003452  lea     r12, WPP_GLOBAL_Control
0x180003459  mov     [r11+8], r15
0x18000345d  mov     eax, 7FFE0014h
0x180003462  mov     rax, [rax]
0x180003465  add     rax, 11E1A300h
0x18000346b  mov     [r11+8], rax
0x18000346f  mov     rbx, r15
0x180003472  lea     rcx, g_TaskHostContextListLock
0x180003479  mov     [rsp+58h+arg_8], rbx
0x18000347e  mov     sil, r15b
0x180003481  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003488  nop     dword ptr [rax+rax+00h]
0x18000348d  call    cs:__imp_GetCurrentThreadId
0x180003494  nop     dword ptr [rax+rax+00h]
0x180003499  mov     cs:dword_180050018, eax
0x18000349f  mov     rbp, r15
0x1800034a2  mov     rax, cs:g_leTaskHostContextListHead
0x1800034a9  mov     rdi, r15
0x1800034ac  lea     rcx, g_leTaskHostContextListHead
0x1800034b3  cmp     rax, rcx
0x1800034b6  jz      short loc_1800034D9
0x1800034b8  lea     rbx, [rax-8]
0x1800034bc  test    byte ptr [rbx+68h], 4
0x1800034c0  mov     rbp, rbx
0x1800034c3  mov     [rsp+58h+arg_8], rbx
0x1800034c8  mov     rdi, rbx
0x1800034cb  jnz     loc_180003562
0x1800034d1  lock inc qword ptr [rbx+60h]
0x1800034d6  mov     sil, 1
0x1800034d9  lea     rcx, g_TaskHostContextListLock
0x1800034e0  mov     cs:dword_180050018, r15d
0x1800034e7  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800034ee  nop     dword ptr [rax+rax+00h]
0x1800034f3  test    sil, sil
0x1800034f6  jz      loc_1800036B2
0x1800034fc  lea     rcx, [rbp+40h]; struct _UBPM_SRWLOCK *
0x180003500  mov     rsi, r15
0x180003503  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180003508  mov     r14, [rdi+18h]
0x18000350c  test    r14, r14
0x18000350f  jz      short loc_180003531
0x180003511  cmp     [rdi+68h], r15b
0x180003515  jge     short loc_180003578
0x180003517  mov     rcx, cs:WPP_GLOBAL_Control
0x18000351e  cmp     rcx, r12
0x180003521  jz      short loc_180003529
0x180003523  test    byte ptr [rcx+1Ch], 2
0x180003527  jnz     short loc_18000356A
0x180003529  mov     rsi, [rbx+28h]
0x18000352d  mov     [rbx+28h], r15
0x180003531  lea     rcx, [rbx+40h]
0x180003535  mov     [rcx+8], r15d
0x180003539  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003540  nop     dword ptr [rax+rax+00h]
0x180003545  test    rsi, rsi
0x180003548  jnz     loc_1800036A2
0x18000354e  mov     edx, 1
0x180003553  lea     rcx, [rsp+58h+arg_8]
0x180003558  call    UbpmpDecrementRefAndDelete
0x18000355d  jmp     loc_18000346F
0x180003562  mov     rax, [rax]
0x180003565  jmp     loc_1800034AC
0x18000356a  mov     r9d, [rdi+20h]
0x18000356e  mov     edx, 36h ; '6'
0x180003573  jmp     loc_1800035FC
0x180003578  cmp     [rdi+0C4h], r15w
0x180003580  jbe     short loc_1800035D3
0x180003582  lea     rdx, [rdi+0C8h]
0x180003589  mov     rcx, [rdx]
0x18000358c  cmp     rcx, rdx
0x18000358f  jz      short loc_1800035D3
0x180003591  mov     rax, [rcx-8]
0x180003595  cmp     rax, 1
0x180003599  jg      short loc_1800035A0
0x18000359b  mov     rcx, [rcx]
0x18000359e  jmp     short loc_18000358C
0x1800035a0  lea     rcx, [rbx+40h]
0x1800035a4  mov     [rcx+8], r15d
0x1800035a8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800035af  nop     dword ptr [rax+rax+00h]
0x1800035b4  lea     r8, [rsp+58h+Timeout]; Timeout
0x1800035b9  xor     edx, edx; Alertable
0x1800035bb  mov     rcx, r14; Handle
0x1800035be  call    cs:__imp_NtWaitForSingleObject
0x1800035c5  nop     dword ptr [rax+rax+00h]
0x1800035ca  lea     rcx, [rbp+40h]; struct _UBPM_SRWLOCK *
0x1800035ce  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800035d3  cmp     [rdi+68h], r15b
0x1800035d7  jge     short loc_180003611
0x1800035d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035e0  cmp     rcx, r12
0x1800035e3  jz      loc_180003529
0x1800035e9  test    byte ptr [rcx+1Ch], 2
0x1800035ed  jz      loc_180003529
0x1800035f3  mov     r9d, [rbx+20h]
0x1800035f7  mov     edx, 37h ; '7'
0x1800035fc  mov     rcx, [rcx+10h]
0x180003600  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180003607  call    WPP_SF_d
0x18000360c  jmp     loc_180003529
0x180003611  mov     rcx, [rdi+18h]; hProcess
0x180003615  mov     edx, 42Bh; uExitCode
0x18000361a  call    cs:__imp_TerminateProcess
0x180003621  nop     dword ptr [rax+rax+00h]
0x180003626  test    eax, eax
0x180003628  jnz     short loc_18000366E
0x18000362a  mov     rax, cs:WPP_GLOBAL_Control
0x180003631  cmp     rax, r12
0x180003634  jz      short loc_180003699
0x180003636  test    byte ptr [rax+1Ch], 2
0x18000363a  jz      short loc_180003699
0x18000363c  call    cs:__imp_GetLastError
0x180003643  nop     dword ptr [rax+rax+00h]
0x180003648  mov     rcx, cs:WPP_GLOBAL_Control
0x18000364f  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180003656  mov     r9d, [rbx+20h]
0x18000365a  mov     edx, 38h ; '8'
0x18000365f  mov     [rsp+58h+var_38], eax
0x180003663  mov     rcx, [rcx+10h]
0x180003667  call    WPP_SF_dd
0x18000366c  jmp     short loc_180003699
0x18000366e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003675  cmp     rcx, r12
0x180003678  jz      short loc_180003699
0x18000367a  test    byte ptr [rcx+1Ch], 80h
0x18000367e  jz      short loc_180003699
0x180003680  mov     r9d, [rbx+20h]
0x180003684  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18000368b  mov     rcx, [rcx+10h]
0x18000368f  mov     edx, 39h ; '9'
0x180003694  call    WPP_SF_d
0x180003699  or      byte ptr [rdi+68h], 80h
0x18000369d  jmp     loc_180003529
0x1800036a2  mov     rdx, rsi; WaitHandle
0x1800036a5  mov     rcx, rbx; struct _UBPM_TASK_HOST_CONTEXT_BLOCK *
0x1800036a8  call    ?UbpmpTaskHostTerminationCleanup@@YAXPEAU_UBPM_TASK_HOST_CONTEXT_BLOCK@@PEAX@Z; UbpmpTaskHostTerminationCleanup(_UBPM_TASK_HOST_CONTEXT_BLOCK *,void *)
0x1800036ad  jmp     loc_18000354E
0x1800036b2  mov     rbx, [rsp+58h+arg_10]
0x1800036b7  mov     rbp, [rsp+58h+arg_18]
0x1800036bc  add     rsp, 30h
0x1800036c0  pop     r15
0x1800036c2  pop     r14
0x1800036c4  pop     r12
0x1800036c6  pop     rdi
0x1800036c7  pop     rsi
0x1800036c8  retn
```

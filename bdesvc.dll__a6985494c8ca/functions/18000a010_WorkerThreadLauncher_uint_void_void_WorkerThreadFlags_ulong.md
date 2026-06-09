# WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)

- ea: `0x18000a010`
- end: `0x18000a37f`
- name: `?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z`
- size: `879`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800090d0`
- `0x1800209a0`
- `0x180024d40`
- `0x180025350`
- `0x18002dd88`
- `0x18002df1c`
- `0x180030fec`
- `0x180045640`
- `0x180046560`
- `0x18004f7e0`
- `0x180054ce8`
- `0x180055584`
- `0x180055894`
- `0x1800563dc`
- `0x180059c40`
- `0x18005b2a4`
- `0x18005c000`

## callees

- `0x180008f50`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x180034070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a0c1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a0c1`
- `ntdll!NtSetInformationThread` at `0x18000a29b`
- `ntdll!NtSetInformationThread` at `0x18000a29b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a084`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000a084`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a06a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000a06a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a1e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a1e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a33c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a0fa`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18000a0fa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000a232`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000a232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a139`

## pseudocode

```c
__int64 __fastcall WorkerThreadLauncher(__int64 a1, __int64 a2, char a3, _DWORD *a4)
{
  HANDLE v8; // rsi
  void *v9; // rax
  void *v10; // rbp
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  PVOID *v13; // rcx
  BdeSvcWorkTracking *v15; // rcx
  __int64 v16; // rdx
  NTSTATUS v17; // eax
  DWORD LastError; // eax
  int ThreadInformation; // [rsp+30h] [rbp-48h] BYREF
  int v20; // [rsp+34h] [rbp-44h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  ThreadInformation = 0;
  v20 = 0;
  AcquireSRWLockShared(&g_srwlStopEvent);
  v8 = g_hStopEvent;
  ReleaseSRWLockShared(&g_srwlStopEvent);
  if ( (a3 & 1) != 0 )
  {
    if ( v8 && WaitForSingleObject(v8, 0) == 258 )
    {
      if ( (unsigned int)BdeSvcWorkTracking::StartWorkImpl(v15) )
        goto LABEL_3;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_17;
      v16 = 12;
    }
    else
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_17;
      v16 = 11;
    }
    WPP_SF_(v13[2], v16, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
LABEL_41:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
    v11 = -1;
    goto LABEL_18;
  }
LABEL_3:
  v9 = (void *)_o__beginthreadex(0, 0, a1, a2, (a3 & 6) != 0 ? 4 : 0, &v20);
  v10 = v9;
  if ( !v9 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (a3 & 1) == 0 )
      goto LABEL_17;
    BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v13);
    goto LABEL_41;
  }
  v11 = 0;
  if ( (a3 & 4) == 0 )
    goto LABEL_5;
  ThreadInformation = 2;
  v17 = NtSetInformationThread(v9, ThreadPagePriority, &ThreadInformation, 4u);
  if ( v17 >= 0 )
    goto LABEL_5;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_ee35f73b350036074f815e40b51ef636_Traceguids,
      (unsigned int)v17);
LABEL_5:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (a3 & 2) != 0 )
  {
    if ( !SetThreadPriority(v10, -1) )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_7;
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, LastError);
    }
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_7:
  if ( (a3 & 6) != 0 )
  {
    ResumeThread(v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    *a4 = v20;
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_(v12[2], 16, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  CloseHandle(v10);
  v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_(v13[2], 17, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  return v11;
}

```

## disassembly

```asm
0x18000a010  mov     [rsp+arg_10], rbx
0x18000a015  push    rbp
0x18000a016  push    rsi
0x18000a017  push    rdi
0x18000a018  push    r12
0x18000a01a  push    r13
0x18000a01c  push    r14
0x18000a01e  push    r15
0x18000a020  sub     rsp, 40h
0x18000a024  mov     rax, cs:__security_cookie
0x18000a02b  xor     rax, rsp
0x18000a02e  mov     [rsp+78h+var_40], rax
0x18000a033  mov     r15, r9
0x18000a036  mov     edi, r8d
0x18000a039  mov     r14, rdx
0x18000a03c  mov     rbp, rcx
0x18000a03f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a046  lea     r12, WPP_GLOBAL_Control
0x18000a04d  cmp     rcx, r12
0x18000a050  jnz     loc_18000A1B5
0x18000a056  xor     r13d, r13d
0x18000a059  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000a060  mov     [rsp+78h+ThreadInformation], r13d
0x18000a065  mov     [rsp+78h+var_44], r13d
0x18000a06a  call    cs:__imp_AcquireSRWLockShared
0x18000a071  nop     dword ptr [rax+rax+00h]
0x18000a076  mov     rsi, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x18000a07d  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000a084  call    cs:__imp_ReleaseSRWLockShared
0x18000a08b  nop     dword ptr [rax+rax+00h]
0x18000a090  mov     ebx, edi
0x18000a092  and     ebx, 1
0x18000a095  jnz     loc_18000A1D9
0x18000a09b  mov     esi, edi
0x18000a09d  mov     r9, r14
0x18000a0a0  and     esi, 6
0x18000a0a3  mov     r8, rbp
0x18000a0a6  mov     eax, esi
0x18000a0a8  neg     eax
0x18000a0aa  lea     rax, [rsp+78h+var_44]
0x18000a0af  sbb     ecx, ecx
0x18000a0b1  mov     [rsp+78h+var_50], rax
0x18000a0b6  and     ecx, 4
0x18000a0b9  xor     edx, edx
0x18000a0bb  mov     [rsp+78h+var_58], ecx
0x18000a0bf  xor     ecx, ecx
0x18000a0c1  call    cs:__imp__o__beginthreadex
0x18000a0c8  nop     dword ptr [rax+rax+00h]
0x18000a0cd  mov     rbp, rax
0x18000a0d0  test    rax, rax
0x18000a0d3  jz      short loc_18000A14E
0x18000a0d5  mov     ebx, r13d
0x18000a0d8  test    dil, 4
0x18000a0dc  jnz     loc_18000A280
0x18000a0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0e9  test    dil, 2
0x18000a0ed  jnz     loc_18000A22A
0x18000a0f3  test    esi, esi
0x18000a0f5  jz      short loc_18000A10D
0x18000a0f7  mov     rcx, rbp; hThread
0x18000a0fa  call    cs:__imp_ResumeThread
0x18000a101  nop     dword ptr [rax+rax+00h]
0x18000a106  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a10d  test    r15, r15
0x18000a110  jnz     loc_18000A36C
0x18000a116  cmp     rcx, r12
0x18000a119  jz      short loc_18000A136
0x18000a11b  test    byte ptr [rcx+1Ch], 8
0x18000a11f  jz      short loc_18000A136
0x18000a121  mov     rcx, [rcx+10h]
0x18000a125  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a12c  mov     edx, 10h
0x18000a131  call    WPP_SF_
0x18000a136  mov     rcx, rbp; hObject
0x18000a139  call    cs:__imp_CloseHandle
0x18000a140  nop     dword ptr [rax+rax+00h]
0x18000a145  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a14c  jmp     short loc_18000A16B
0x18000a14e  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18000a155  cmp     rcx, r12
0x18000a158  jnz     loc_18000A2F7
0x18000a15e  test    ebx, ebx
0x18000a160  jnz     loc_18000A2E6
0x18000a166  mov     ebx, 0FFFFFFFFh
0x18000a16b  cmp     rcx, r12
0x18000a16e  jnz     short loc_18000A198
0x18000a170  mov     eax, ebx
0x18000a172  mov     rcx, [rsp+78h+var_40]
0x18000a177  xor     rcx, rsp; StackCookie
0x18000a17a  call    __security_check_cookie
0x18000a17f  mov     rbx, [rsp+78h+arg_10]
0x18000a187  add     rsp, 40h
0x18000a18b  pop     r15
0x18000a18d  pop     r14
0x18000a18f  pop     r13
0x18000a191  pop     r12
0x18000a193  pop     rdi
0x18000a194  pop     rsi
0x18000a195  pop     rbp
0x18000a196  retn
0x18000a198  test    byte ptr [rcx+1Ch], 20h
0x18000a19c  jz      short loc_18000A170
0x18000a19e  mov     rcx, [rcx+10h]
0x18000a1a2  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a1a9  mov     edx, 11h
0x18000a1ae  call    WPP_SF_
0x18000a1b3  jmp     short loc_18000A170
0x18000a1b5  test    byte ptr [rcx+1Ch], 20h
0x18000a1b9  jz      loc_18000A056
0x18000a1bf  mov     rcx, [rcx+10h]
0x18000a1c3  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a1ca  mov     edx, 0Ah
0x18000a1cf  call    WPP_SF_
0x18000a1d4  jmp     loc_18000A056
0x18000a1d9  test    rsi, rsi
0x18000a1dc  jz      short loc_18000A1F6
0x18000a1de  xor     edx, edx; dwMilliseconds
0x18000a1e0  mov     rcx, rsi; hHandle
0x18000a1e3  call    cs:__imp_WaitForSingleObject
0x18000a1ea  nop     dword ptr [rax+rax+00h]
0x18000a1ef  cmp     eax, 102h
0x18000a1f4  jz      short loc_18000A252
0x18000a1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1fd  cmp     rcx, r12
0x18000a200  jz      loc_18000A166
0x18000a206  test    byte ptr [rcx+1Ch], 2
0x18000a20a  jz      loc_18000A166
0x18000a210  mov     edx, 0Bh
0x18000a215  mov     rcx, [rcx+10h]
0x18000a219  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a220  call    WPP_SF_
0x18000a225  jmp     loc_18000A2EB
0x18000a22a  mov     edx, 0FFFFFFFFh; nPriority
0x18000a22f  mov     rcx, rbp; hThread
0x18000a232  call    cs:__imp_SetThreadPriority
0x18000a239  nop     dword ptr [rax+rax+00h]
0x18000a23e  test    eax, eax
0x18000a240  jz      loc_18000A322
0x18000a246  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a24d  jmp     loc_18000A0F3
0x18000a252  call    ?StartWorkImpl@BdeSvcWorkTracking@@AEAAHXZ; BdeSvcWorkTracking::StartWorkImpl(void)
0x18000a257  test    eax, eax
0x18000a259  jnz     loc_18000A09B
0x18000a25f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a266  cmp     rcx, r12
0x18000a269  jz      loc_18000A166
0x18000a26f  test    byte ptr [rcx+1Ch], 2
0x18000a273  jz      loc_18000A166
0x18000a279  mov     edx, 0Ch
0x18000a27e  jmp     short loc_18000A215
0x18000a280  mov     r9d, 4; ThreadInformationLength
0x18000a286  mov     [rsp+78h+ThreadInformation], 2
0x18000a28e  lea     r8, [rsp+78h+ThreadInformation]; ThreadInformation
0x18000a293  mov     edx, 18h; ThreadInformationClass
0x18000a298  mov     rcx, rbp; ThreadHandle
0x18000a29b  call    cs:__imp_NtSetInformationThread
0x18000a2a2  nop     dword ptr [rax+rax+00h]
0x18000a2a7  test    eax, eax
0x18000a2a9  jns     loc_18000A0E2
0x18000a2af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2b6  cmp     rcx, r12
0x18000a2b9  jz      loc_18000A0E9
0x18000a2bf  test    byte ptr [rcx+1Ch], 2
0x18000a2c3  jz      loc_18000A0E9
0x18000a2c9  mov     rcx, [rcx+10h]
0x18000a2cd  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a2d4  mov     edx, 0Eh
0x18000a2d9  mov     r9d, eax
0x18000a2dc  call    WPP_SF_d
0x18000a2e1  jmp     loc_18000A0E2
0x18000a2e6  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x18000a2eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2f2  jmp     loc_18000A166
0x18000a2f7  test    byte ptr [rcx+1Ch], 2
0x18000a2fb  jz      loc_18000A15E
0x18000a301  mov     rcx, [rcx+10h]
0x18000a305  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a30c  mov     edx, 0Dh
0x18000a311  call    WPP_SF_
0x18000a316  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a31d  jmp     loc_18000A15E
0x18000a322  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a329  cmp     rcx, r12
0x18000a32c  jz      loc_18000A0F3
0x18000a332  test    byte ptr [rcx+1Ch], 2
0x18000a336  jz      loc_18000A0F3
0x18000a33c  call    cs:__imp_GetLastError
0x18000a343  nop     dword ptr [rax+rax+00h]
0x18000a348  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a34f  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000a356  mov     edx, 0Fh
0x18000a35b  mov     r9d, eax
0x18000a35e  mov     rcx, [rcx+10h]
0x18000a362  call    WPP_SF_d
0x18000a367  jmp     loc_18000A246
0x18000a36c  mov     eax, [rsp+78h+var_44]
0x18000a370  mov     [r15], eax
0x18000a373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a37a  jmp     loc_18000A116
```

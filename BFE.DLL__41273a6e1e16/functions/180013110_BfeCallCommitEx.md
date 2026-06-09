# BfeCallCommitEx

- ea: `0x180013110`
- end: `0x180013399`
- name: `BfeCallCommitEx`
- size: `649`
- prototype: ``
- caller_count: `13`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800090f0`
- `0x18002e1a0`
- `0x18003b1ac`
- `0x180044f80`
- `0x180047cb0`
- `0x180062b30`
- `0x180063340`
- `0x1800635f0`
- `0x1800640b0`
- `0x1800641c0`
- `0x180064f10`
- `0x1800661a0`
- `0x18007588c`

## callees

- `0x180008dd0`
- `0x18000fb34`
- `0x180011510`
- `0x180013110`
- `0x1800197d0`
- `0x1800408e4`
- `0x180044954`
- `0x1800572ec`
- `0x1800592f4`
- `0x18005aa60`
- `0x180076208`

## import_xrefs

- `ntdll!TpWaitForTimer` at `0x18001318c`
- `ntdll!TpWaitForTimer` at `0x18001318c`
- `ntdll!TpSetTimer` at `0x180013174`
- `ntdll!TpSetTimer` at `0x180013174`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800131fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800131fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800131c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180013305`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001331f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800131c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180013305`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001331f`

## string_xrefs

- `0x180013246`: `BfeCallCommitEx`
- `0x18001322c`: `BfeTxnCommit`

## pseudocode

```c
__int64 __fastcall BfeCallCommitEx(_QWORD *a1, unsigned int a2)
{
  __int64 v4; // rsi
  _DWORD *v5; // r15
  int IsEnabledDeviceUsageInline; // eax
  int v7; // ebx
  int v8; // edx
  __int64 v9; // r8
  unsigned int v10; // r14d
  BOOL v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  int TickCount64; // ebx
  int v16; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v17[16]; // [rsp+38h] [rbp-60h] BYREF
  const char *v18; // [rsp+48h] [rbp-50h]
  __int64 v19; // [rsp+50h] [rbp-48h]
  int *v20; // [rsp+58h] [rbp-40h]
  __int64 v21; // [rsp+60h] [rbp-38h]

  if ( *a1 && *(_DWORD *)(*a1 + 36LL) )
    return 0;
  v4 = 0;
  v5 = (_DWORD *)a1[1];
  if ( dword_1800F5CE0 )
  {
    TpSetTimer(qword_1800F5CD8, 0, 0, 0);
    TpWaitForTimer(qword_1800F5CD8, 1);
    dword_1800F5CE0 = 0;
  }
  if ( !dword_1800F5CD0 )
  {
    TickCount64 = GetTickCount64();
    v4 = BfeTxnCoordinatorCommit(a2);
    dword_1800F5CF8 = GetTickCount64() - TickCount64;
  }
  IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
  *v5 = 0;
  if ( !IsEnabledDeviceUsageInline )
  {
    v7 = qword_1800F5CF0;
    v10 = GetTickCount64() - v7;
    if ( v10 >= dword_1800F5CE4 )
    {
      if ( (byte_1800F6115 & 2) != 0 )
        McTemplateU0qqqq_EtwEventWriteTransfer(
          dword_1800F5CF8,
          v8,
          dword_1800F5CE8,
          v10,
          dword_1800F5CF8,
          dword_1800F5CE4);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v9, (unsigned int)dword_1800F5CE8, v10, dword_1800F5CF8);
      }
    }
  }
  qword_1800F5CC8 = 0;
  v11 = ReleaseSemaphore(gBfeTxnComponent, 1, 0);
  if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12);
  if ( gBfePeriodicRundownEnabled && !dword_1800F5CD0 )
    BfeRundownState(v12);
  if ( v4 )
  {
    WfpReportError(v4, "BfeTxnCommit");
    a1[1] = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v13, 0, (__int64)"BfeCallCommitEx", v4);
    }
    if ( gWfpLogUserModeErrors )
    {
      if ( (byte_1800F6115 & 1) != 0 )
      {
        v16 = v4;
        v20 = &v16;
        v18 = "BfeCallCommitEx";
        v19 = 16;
        v21 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v13,
          3,
          (__int64)v17);
      }
    }
  }
  else
  {
    a1[1] = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180013110  push    rbp
0x180013112  push    rdi
0x180013113  push    r14
0x180013115  sub     rsp, 80h
0x18001311c  mov     rax, cs:__security_cookie
0x180013123  xor     rax, rsp
0x180013126  mov     [rsp+98h+var_30], rax
0x18001312b  mov     rax, [rcx]
0x18001312e  mov     r14d, edx
0x180013131  mov     rdi, rcx
0x180013134  test    rax, rax
0x180013137  jz      short loc_180013143
0x180013139  cmp     dword ptr [rax+24h], 0
0x18001313d  jnz     loc_180013338
0x180013143  mov     [rsp+98h+arg_10], rbx
0x18001314b  xor     ebp, ebp
0x18001314d  cmp     cs:dword_1800F5CE0, ebp
0x180013153  mov     [rsp+98h+var_20], rsi
0x180013158  mov     esi, ebp
0x18001315a  mov     [rsp+98h+var_28], r15
0x18001315f  mov     r15, [rcx+8]
0x180013163  jz      short loc_18001319E
0x180013165  mov     rcx, cs:qword_1800F5CD8
0x18001316c  xor     r9d, r9d
0x18001316f  xor     r8d, r8d
0x180013172  xor     edx, edx
0x180013174  call    cs:__imp_TpSetTimer
0x18001317b  nop     dword ptr [rax+rax+00h]
0x180013180  mov     rcx, cs:qword_1800F5CD8
0x180013187  mov     edx, 1
0x18001318c  call    cs:__imp_TpWaitForTimer
0x180013193  nop     dword ptr [rax+rax+00h]
0x180013198  mov     cs:dword_1800F5CE0, ebp
0x18001319e  cmp     cs:dword_1800F5CD0, ebp
0x1800131a4  jz      loc_180013305
0x1800131aa  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x1800131af  mov     [r15], ebp
0x1800131b2  lea     r15, WPP_GLOBAL_Control
0x1800131b9  test    eax, eax
0x1800131bb  jnz     short loc_1800131E4
0x1800131bd  mov     ebx, dword ptr cs:qword_1800F5CF0
0x1800131c3  call    cs:__imp_GetTickCount64
0x1800131ca  nop     dword ptr [rax+rax+00h]
0x1800131cf  mov     r14, rax
0x1800131d2  mov     eax, cs:dword_1800F5CE4
0x1800131d8  sub     r14d, ebx
0x1800131db  cmp     r14d, eax
0x1800131de  jnb     loc_180013357
0x1800131e4  mov     rcx, cs:gBfeTxnComponent; hSemaphore
0x1800131eb  xor     r8d, r8d; lpPreviousCount
0x1800131ee  mov     edx, 1; lReleaseCount
0x1800131f3  mov     cs:qword_1800F5CC8, rbp
0x1800131fa  call    cs:__imp_ReleaseSemaphore
0x180013201  nop     dword ptr [rax+rax+00h]
0x180013206  mov     ebx, eax
0x180013208  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x18001320d  test    eax, eax
0x18001320f  jnz     loc_180013387
0x180013215  cmp     cs:gBfePeriodicRundownEnabled, ebp
0x18001321b  jnz     loc_180013341
0x180013221  test    rsi, rsi
0x180013224  jnz     short loc_18001322C
0x180013226  mov     [rdi+8], rbp
0x18001322a  jmp     short loc_180013280
0x18001322c  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x180013233  mov     rcx, rsi
0x180013236  call    WfpReportError
0x18001323b  mov     [rdi+8], rbp
0x18001323f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013246  lea     rbx, aBfecallcommite; "BfeCallCommitEx"
0x18001324d  cmp     rcx, r15
0x180013250  jz      short loc_180013278
0x180013252  cmp     byte ptr [rcx+19h], 2
0x180013256  jb      short loc_180013278
0x180013258  test    byte ptr [rcx+1Ch], 1
0x18001325c  jz      short loc_180013278
0x18001325e  mov     rcx, [rcx+10h]
0x180013262  mov     edx, 1Ah
0x180013267  mov     [rsp+98h+var_70], esi
0x18001326b  xor     r9d, r9d
0x18001326e  mov     [rsp+98h+var_78], rbx
0x180013273  call    WPP_SF_Ssd
0x180013278  cmp     cs:gWfpLogUserModeErrors, ebp
0x18001327e  jnz     short loc_1800132AF
0x180013280  mov     rbx, [rsp+98h+arg_10]
0x180013288  mov     rax, rsi
0x18001328b  mov     rsi, [rsp+98h+var_20]
0x180013290  mov     r15, [rsp+98h+var_28]
0x180013295  mov     rcx, [rsp+98h+var_30]
0x18001329a  xor     rcx, rsp; StackCookie
0x18001329d  call    __security_check_cookie
0x1800132a2  add     rsp, 80h
0x1800132a9  pop     r14
0x1800132ab  pop     rdi
0x1800132ac  pop     rbp
0x1800132ad  retn
0x1800132af  test    cs:byte_1800F6115, 1
0x1800132b6  jz      short loc_180013280
0x1800132b8  lea     rax, [rsp+98h+var_68]
0x1800132bd  mov     [rsp+98h+var_68], esi
0x1800132c1  mov     [rsp+98h+var_40], rax
0x1800132c6  lea     rdx, WFP_USERMODE_ERROR
0x1800132cd  lea     rax, [rsp+98h+var_60]
0x1800132d2  mov     [rsp+98h+var_50], rbx
0x1800132d7  mov     r9d, 3
0x1800132dd  mov     [rsp+98h+var_78], rax
0x1800132e2  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800132e9  mov     [rsp+98h+var_48], 10h
0x1800132f2  mov     [rsp+98h+var_38], 4
0x1800132fb  call    McGenEventWrite_EtwEventWriteTransfer
0x180013300  jmp     loc_180013280
0x180013305  call    cs:__imp_GetTickCount64
0x18001330c  nop     dword ptr [rax+rax+00h]
0x180013311  mov     ecx, r14d
0x180013314  mov     rbx, rax
0x180013317  call    BfeTxnCoordinatorCommit
0x18001331c  mov     rsi, rax
0x18001331f  call    cs:__imp_GetTickCount64
0x180013326  nop     dword ptr [rax+rax+00h]
0x18001332b  sub     eax, ebx
0x18001332d  mov     cs:dword_1800F5CF8, eax
0x180013333  jmp     loc_1800131AA
0x180013338  xor     ebp, ebp
0x18001333a  mov     eax, ebp
0x18001333c  jmp     loc_180013295
0x180013341  cmp     cs:dword_1800F5CD0, ebp
0x180013347  jnz     loc_180013221
0x18001334d  call    BfeRundownState
0x180013352  jmp     loc_180013221
0x180013357  test    cs:byte_1800F6115, 2
0x18001335e  jz      loc_18008B93A
0x180013364  mov     ecx, cs:dword_1800F5CF8
0x18001336a  mov     r9d, r14d
0x18001336d  mov     r8d, cs:dword_1800F5CE8
0x180013374  mov     [rsp+98h+var_70], eax
0x180013378  mov     dword ptr [rsp+98h+var_78], ecx
0x18001337c  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x180013381  nop
0x180013382  jmp     loc_18008B93A
0x180013387  test    ebx, ebx
0x180013389  jnz     loc_180013215
0x18001338f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180013394  jmp     loc_180013215
0x18008b93a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b941  cmp     rcx, r15
0x18008b944  jz      loc_1800131E4
0x18008b94a  cmp     byte ptr [rcx+19h], 3
0x18008b94e  jb      loc_1800131E4
0x18008b954  test    byte ptr [rcx+1Ch], 2
0x18008b958  jz      loc_1800131E4
0x18008b95e  mov     eax, cs:dword_1800F5CF8
0x18008b964  mov     edx, 0Bh
0x18008b969  mov     r9d, cs:dword_1800F5CE8
0x18008b970  mov     rcx, [rcx+10h]
0x18008b974  mov     [rsp+98h+var_70], eax
0x18008b978  mov     dword ptr [rsp+98h+var_78], r14d
0x18008b97d  call    WPP_SF_LLL
0x18008b982  nop
0x18008b983  jmp     loc_1800131E4
```

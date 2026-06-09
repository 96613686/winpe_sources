# BfeCallCommitEx

- ea: `0x1800126e0`
- end: `0x180012944`
- name: `BfeCallCommitEx`
- size: `612`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c7b8`
- `0x180030abc`
- `0x180043320`
- `0x180045e30`
- `0x180060810`
- `0x180061010`
- `0x1800612c0`
- `0x180061d80`
- `0x180061e90`
- `0x180062bc0`
- `0x180063e40`
- `0x180072fdc`

## callees

- `0x1800087a0`
- `0x18000f1a8`
- `0x180010ad0`
- `0x1800126e0`
- `0x180018b74`
- `0x18003f5dc`
- `0x180042f04`
- `0x180055424`
- `0x1800575c4`
- `0x180058b30`
- `0x180073828`

## import_xrefs

- `ntdll!TpWaitForTimer` at `0x180012756`
- `ntdll!TpWaitForTimer` at `0x180012756`
- `ntdll!TpSetTimer` at `0x180012744`
- `ntdll!TpSetTimer` at `0x180012744`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800127b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800127b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012787`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012787`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800128d0`

## string_xrefs

- `0x1800127fe`: `BfeCallCommitEx`
- `0x1800127e4`: `BfeTxnCommit`

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
  if ( LODWORD(qword_1800F2668[203]) )
  {
    TpSetTimer(qword_1800F2668[202], 0, 0, 0);
    TpWaitForTimer(qword_1800F2668[202], 1);
    LODWORD(qword_1800F2668[203]) = 0;
  }
  if ( !LODWORD(qword_1800F2668[201]) )
  {
    TickCount64 = GetTickCount64();
    v4 = BfeTxnCoordinatorCommit(a2);
    LODWORD(qword_1800F2668[206]) = GetTickCount64() - TickCount64;
  }
  IsEnabledDeviceUsageInline = Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline();
  *v5 = 0;
  if ( !IsEnabledDeviceUsageInline )
  {
    v7 = qword_1800F2668[205];
    v10 = GetTickCount64() - v7;
    if ( v10 >= HIDWORD(qword_1800F2668[203]) )
    {
      if ( (qword_1800F2668[337] & 0x20000000000LL) != 0 )
        McTemplateU0qqqq_EtwEventWriteTransfer(
          qword_1800F2668[206],
          v8,
          qword_1800F2668[204],
          v10,
          qword_1800F2668[206],
          SBYTE4(qword_1800F2668[203]));
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_LLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          v9,
          LODWORD(qword_1800F2668[204]),
          v10,
          qword_1800F2668[206]);
      }
    }
  }
  qword_1800F2668[200] = 0;
  v11 = ReleaseSemaphore((HANDLE)qword_1800F2668[199], 1, 0);
  if ( (unsigned int)Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline() && !v11 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( LODWORD(qword_1800F2668[197]) && !LODWORD(qword_1800F2668[201]) )
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
    if ( MEMORY[0x1800EF078] )
    {
      if ( (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
0x1800126e0  push    rbp
0x1800126e2  push    rdi
0x1800126e3  push    r14
0x1800126e5  sub     rsp, 80h
0x1800126ec  mov     rax, cs:__security_cookie
0x1800126f3  xor     rax, rsp
0x1800126f6  mov     [rsp+98h+var_30], rax
0x1800126fb  mov     rax, [rcx]
0x1800126fe  mov     r14d, edx
0x180012701  mov     rdi, rcx
0x180012704  test    rax, rax
0x180012707  jz      short loc_180012713
0x180012709  cmp     dword ptr [rax+24h], 0
0x18001270d  jnz     loc_1800128E3
0x180012713  mov     [rsp+98h+arg_10], rbx
0x18001271b  xor     ebp, ebp
0x18001271d  cmp     dword ptr cs:qword_1800F2668+658h, ebp
0x180012723  mov     [rsp+98h+var_20], rsi
0x180012728  mov     esi, ebp
0x18001272a  mov     [rsp+98h+var_28], r15
0x18001272f  mov     r15, [rcx+8]
0x180012733  jz      short loc_180012762
0x180012735  mov     rcx, cs:qword_1800F2668+650h
0x18001273c  xor     r9d, r9d
0x18001273f  xor     r8d, r8d
0x180012742  xor     edx, edx
0x180012744  call    cs:__imp_TpSetTimer
0x18001274a  mov     rcx, cs:qword_1800F2668+650h
0x180012751  mov     edx, 1
0x180012756  call    cs:__imp_TpWaitForTimer
0x18001275c  mov     dword ptr cs:qword_1800F2668+658h, ebp
0x180012762  cmp     dword ptr cs:qword_1800F2668+648h, ebp
0x180012768  jz      loc_1800128BC
0x18001276e  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x180012773  mov     [r15], ebp
0x180012776  lea     r15, WPP_GLOBAL_Control
0x18001277d  test    eax, eax
0x18001277f  jnz     short loc_1800127A2
0x180012781  mov     ebx, dword ptr cs:qword_1800F2668+668h
0x180012787  call    cs:__imp_GetTickCount64
0x18001278d  mov     r14, rax
0x180012790  mov     eax, dword ptr cs:qword_1800F2668+65Ch
0x180012796  sub     r14d, ebx
0x180012799  cmp     r14d, eax
0x18001279c  jnb     loc_180012902
0x1800127a2  mov     rcx, cs:qword_1800F2668+638h; hSemaphore
0x1800127a9  xor     r8d, r8d; lpPreviousCount
0x1800127ac  mov     edx, 1; lReleaseCount
0x1800127b1  mov     cs:qword_1800F2668+640h, rbp
0x1800127b8  call    cs:__imp_ReleaseSemaphore
0x1800127be  mov     ebx, eax
0x1800127c0  call    Feature_BugFix_FwBfeSessions__private_IsEnabledDeviceUsageInline
0x1800127c5  test    eax, eax
0x1800127c7  jnz     loc_180012932
0x1800127cd  cmp     dword ptr cs:qword_1800F2668+628h, ebp
0x1800127d3  jnz     loc_1800128EC
0x1800127d9  test    rsi, rsi
0x1800127dc  jnz     short loc_1800127E4
0x1800127de  mov     [rdi+8], rbp
0x1800127e2  jmp     short loc_180012838
0x1800127e4  lea     rdx, aBfetxncommit; "BfeTxnCommit"
0x1800127eb  mov     rcx, rsi
0x1800127ee  call    WfpReportError
0x1800127f3  mov     [rdi+8], rbp
0x1800127f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127fe  lea     rbx, aBfecallcommite; "BfeCallCommitEx"
0x180012805  cmp     rcx, r15
0x180012808  jz      short loc_180012830
0x18001280a  cmp     byte ptr [rcx+19h], 2
0x18001280e  jb      short loc_180012830
0x180012810  test    byte ptr [rcx+1Ch], 1
0x180012814  jz      short loc_180012830
0x180012816  mov     rcx, [rcx+10h]
0x18001281a  mov     edx, 1Ah
0x18001281f  mov     [rsp+98h+var_70], esi
0x180012823  xor     r9d, r9d
0x180012826  mov     [rsp+98h+var_78], rbx
0x18001282b  call    WPP_SF_Ssd
0x180012830  cmp     cs:1800EF078h, ebp
0x180012836  jnz     short loc_180012866
0x180012838  mov     rbx, [rsp+98h+arg_10]
0x180012840  mov     rax, rsi
0x180012843  mov     rsi, [rsp+98h+var_20]
0x180012848  mov     r15, [rsp+98h+var_28]
0x18001284d  mov     rcx, [rsp+98h+var_30]
0x180012852  xor     rcx, rsp; StackCookie
0x180012855  call    __security_check_cookie
0x18001285a  add     rsp, 80h
0x180012861  pop     r14
0x180012863  pop     rdi
0x180012864  pop     rbp
0x180012865  retn
0x180012866  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x18001286d  jz      short loc_180012838
0x18001286f  lea     rax, [rsp+98h+var_68]
0x180012874  mov     [rsp+98h+var_68], esi
0x180012878  mov     [rsp+98h+var_40], rax
0x18001287d  lea     rdx, WFP_USERMODE_ERROR
0x180012884  lea     rax, [rsp+98h+var_60]
0x180012889  mov     [rsp+98h+var_50], rbx
0x18001288e  mov     r9d, 3
0x180012894  mov     [rsp+98h+var_78], rax
0x180012899  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800128a0  mov     [rsp+98h+var_48], 10h
0x1800128a9  mov     [rsp+98h+var_38], 4
0x1800128b2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800128b7  jmp     loc_180012838
0x1800128bc  call    cs:__imp_GetTickCount64
0x1800128c2  mov     ecx, r14d
0x1800128c5  mov     rbx, rax
0x1800128c8  call    BfeTxnCoordinatorCommit
0x1800128cd  mov     rsi, rax
0x1800128d0  call    cs:__imp_GetTickCount64
0x1800128d6  sub     eax, ebx
0x1800128d8  mov     dword ptr cs:qword_1800F2668+670h, eax
0x1800128de  jmp     loc_18001276E
0x1800128e3  xor     ebp, ebp
0x1800128e5  mov     eax, ebp
0x1800128e7  jmp     loc_18001284D
0x1800128ec  cmp     dword ptr cs:qword_1800F2668+648h, ebp
0x1800128f2  jnz     loc_1800127D9
0x1800128f8  call    BfeRundownState
0x1800128fd  jmp     loc_1800127D9
0x180012902  test    byte ptr cs:qword_1800F2668+0A8Dh, 2
0x180012909  jz      loc_180088A58
0x18001290f  mov     ecx, dword ptr cs:qword_1800F2668+670h
0x180012915  mov     r9d, r14d
0x180012918  mov     r8d, dword ptr cs:qword_1800F2668+660h
0x18001291f  mov     [rsp+98h+var_70], eax
0x180012923  mov     dword ptr [rsp+98h+var_78], ecx
0x180012927  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x18001292c  nop
0x18001292d  jmp     loc_180088A58
0x180012932  test    ebx, ebx
0x180012934  jnz     loc_1800127CD
0x18001293a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001293f  jmp     loc_1800127CD
0x180088a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a5f  cmp     rcx, r15
0x180088a62  jz      loc_1800127A2
0x180088a68  cmp     byte ptr [rcx+19h], 3
0x180088a6c  jb      loc_1800127A2
0x180088a72  test    byte ptr [rcx+1Ch], 2
0x180088a76  jz      loc_1800127A2
0x180088a7c  mov     eax, dword ptr cs:qword_1800F2668+670h
0x180088a82  mov     edx, 0Bh
0x180088a87  mov     r9d, dword ptr cs:qword_1800F2668+660h
0x180088a8e  mov     rcx, [rcx+10h]
0x180088a92  mov     [rsp+98h+var_70], eax
0x180088a96  mov     dword ptr [rsp+98h+var_78], r14d
0x180088a9b  call    WPP_SF_LLL
0x180088aa0  nop
0x180088aa1  jmp     loc_1800127A2
```

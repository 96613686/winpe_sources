# MpWatchDog::CWdResController::Uninitialize(void)

- ea: `0x140098f54`
- end: `0x14009913e`
- name: `?Uninitialize@CWdResController@MpWatchDog@@QEAAXXZ`
- size: `490`
- prototype: `void __fastcall(MpWatchDog::CWdResController *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140099140`

## callees

- `0x1400144dc`
- `0x14003a130`
- `0x14003a5c0`
- `0x140059e84`
- `0x14007d210`
- `0x140098998`
- `0x140098c70`
- `0x140098f54`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x14009906d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x14009906d`
- `KERNEL32!SetInformationJobObject` at `0x140099000`
- `KERNEL32!SetInformationJobObject` at `0x140099000`
- `KERNEL32!Sleep` at `0x140098fa6`
- `KERNEL32!Sleep` at `0x140098fa6`
- `KERNEL32!CloseHandle` at `0x1400990fb`
- `KERNEL32!CloseHandle` at `0x140099112`
- `KERNEL32!CloseHandle` at `0x1400990fb`
- `KERNEL32!CloseHandle` at `0x140099112`
- `KERNEL32!GetLastError` at `0x14009900a`
- `KERNEL32!GetLastError` at `0x140099077`
- `KERNEL32!GetLastError` at `0x14009900a`
- `KERNEL32!GetLastError` at `0x140099077`

## pseudocode

```c
void __fastcall MpWatchDog::CWdResController::Uninitialize(MpWatchDog::CWdResController *this)
{
  MpWatchDog::CWdResController *v1; // rdi
  _DWORD *v2; // rcx
  void *v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // r8d
  signed int v6; // eax
  void *v7; // rcx
  __int128 JobObjectInformation; // [rsp+20h] [rbp-28h] BYREF

  v1 = qword_1401E7358;
  *(_QWORD *)&JobObjectInformation = qword_1401E7358;
  if ( !*((_BYTE *)qword_1401E7358 + 24) )
  {
    if ( *((_QWORD *)qword_1401E7358 + 6) )
    {
      try
      {
        MpWatchDog::CWdResController::SimulateHighCpuUtilizationAsync(qword_1401E7358, 1);
        MpWatchDog::CWdResController::SimulateHighMemoryConsumptionAsync(v1, 0);
        Sleep(0x3E8u);
        v2 = (_DWORD *)*((_QWORD *)v1 + 6);
        *((_QWORD *)v1 + 6) = 0;
        if ( v2 )
        {
          if ( v2[2] )
            terminate();
          operator delete(v2, (const struct std::nothrow_t *)0x10);
        }
      }
      catch ( ... )
      {
        v1 = (MpWatchDog::CWdResController *)JobObjectInformation;
      }
    }
    v3 = (void *)*((_QWORD *)v1 + 1);
    if ( v3 )
    {
      if ( *(_QWORD *)v1 )
      {
        JobObjectInformation = 0;
        if ( !SetInformationJobObject(v3, JobObjectAssociateCompletionPortInformation, &JobObjectInformation, 0x10u) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              26,
              &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
              (unsigned int)LastError);
        }
      }
    }
    if ( *((_QWORD *)v1 + 7) )
    {
      if ( !PostQueuedCompletionStatus(*(HANDLE *)v1, 0xFFFFFFFF, 0, 0) )
      {
        v6 = GetLastError();
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            27,
            &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
            (unsigned int)v6);
      }
      if ( CommonUtil::UtilWaitForSingleObject(*((CommonUtil **)v1 + 7), (void *)0x3E8, v5)
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          28,
          &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
          2147943860LL);
      }
    }
    v7 = (void *)*((_QWORD *)v1 + 1);
    if ( v7 )
    {
      CloseHandle(v7);
      *((_QWORD *)v1 + 1) = 0;
    }
    if ( *(_QWORD *)v1 )
    {
      CloseHandle(*(HANDLE *)v1);
      *(_QWORD *)v1 = 0;
    }
  }
}

```

## disassembly

```asm
0x140098f54  mov     [rsp+arg_0], rsi
0x140098f59  push    rdi
0x140098f5a  sub     rsp, 40h
0x140098f5e  mov     rax, cs:__security_cookie
0x140098f65  xor     rax, rsp
0x140098f68  mov     [rsp+48h+var_18], rax
0x140098f6d  mov     rdi, cs:qword_1401E7358
0x140098f74  mov     qword ptr [rsp+48h+JobObjectInformation], rdi
0x140098f79  cmp     byte ptr [rdi+18h], 0
0x140098f7d  jnz     loc_14009911F
0x140098f83  cmp     qword ptr [rdi+30h], 0
0x140098f88  jz      short loc_140098FD9
0x140098f8a  mov     edx, 1; int
0x140098f8f  mov     rcx, rdi; this
0x140098f92  call    ?SimulateHighCpuUtilizationAsync@CWdResController@MpWatchDog@@AEAAJH@Z; MpWatchDog::CWdResController::SimulateHighCpuUtilizationAsync(int)
0x140098f97  xor     edx, edx; unsigned int
0x140098f99  mov     rcx, rdi; this
0x140098f9c  call    ?SimulateHighMemoryConsumptionAsync@CWdResController@MpWatchDog@@AEAAJK@Z; MpWatchDog::CWdResController::SimulateHighMemoryConsumptionAsync(ulong)
0x140098fa1  mov     ecx, 3E8h; dwMilliseconds
0x140098fa6  call    cs:__imp_Sleep
0x140098fac  mov     rcx, [rdi+30h]; void *
0x140098fb0  mov     qword ptr [rdi+30h], 0
0x140098fb8  test    rcx, rcx
0x140098fbb  jz      short loc_140098FD2
0x140098fbd  cmp     dword ptr [rcx+8], 0
0x140098fc1  jnz     loc_140099137
0x140098fc7  mov     edx, 10h; struct std::nothrow_t *
0x140098fcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140098fd1  nop
0x140098fd2  jmp     short loc_140098FD9
0x140098fd4  mov     rdi, qword ptr [rsp+48h+JobObjectInformation]
0x140098fd9  mov     rcx, [rdi+8]; hJob
0x140098fdd  test    rcx, rcx
0x140098fe0  jz      short loc_14009904F
0x140098fe2  cmp     qword ptr [rdi], 0
0x140098fe6  jz      short loc_14009904F
0x140098fe8  xorps   xmm0, xmm0
0x140098feb  movdqu  [rsp+48h+JobObjectInformation], xmm0
0x140098ff1  mov     r9d, 10h; cbJobObjectInformationLength
0x140098ff7  lea     r8, [rsp+48h+JobObjectInformation]; lpJobObjectInformation
0x140098ffc  lea     edx, [r9-9]; JobObjectInformationClass
0x140099000  call    cs:__imp_SetInformationJobObject
0x140099006  test    eax, eax
0x140099008  jnz     short loc_14009904F
0x14009900a  call    cs:__imp_GetLastError
0x140099010  test    eax, eax
0x140099012  jle     short loc_14009901C
0x140099014  movzx   eax, ax
0x140099017  or      eax, 80070000h
0x14009901c  lea     rsi, WPP_GLOBAL_Control
0x140099023  mov     rcx, cs:WPP_GLOBAL_Control
0x14009902a  cmp     rcx, rsi
0x14009902d  jz      short loc_140099056
0x14009902f  test    byte ptr [rcx+1Ch], 1
0x140099033  jz      short loc_140099056
0x140099035  mov     edx, 1Ah
0x14009903a  mov     r9d, eax
0x14009903d  lea     r8, WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids
0x140099044  mov     rcx, [rcx+10h]
0x140099048  call    WPP_SF_d
0x14009904d  jmp     short loc_140099056
0x14009904f  lea     rsi, WPP_GLOBAL_Control
0x140099056  cmp     qword ptr [rdi+38h], 0
0x14009905b  jz      loc_1400990F2
0x140099061  xor     r9d, r9d; lpOverlapped
0x140099064  xor     r8d, r8d; dwCompletionKey
0x140099067  or      edx, 0FFFFFFFFh; dwNumberOfBytesTransferred
0x14009906a  mov     rcx, [rdi]; CompletionPort
0x14009906d  call    cs:__imp_PostQueuedCompletionStatus
0x140099073  test    eax, eax
0x140099075  jnz     short loc_1400990B3
0x140099077  call    cs:__imp_GetLastError
0x14009907d  test    eax, eax
0x14009907f  jle     short loc_140099089
0x140099081  movzx   eax, ax
0x140099084  or      eax, 80070000h
0x140099089  mov     rcx, cs:WPP_GLOBAL_Control
0x140099090  cmp     rcx, rsi
0x140099093  jz      short loc_1400990B3
0x140099095  test    byte ptr [rcx+1Ch], 1
0x140099099  jz      short loc_1400990B3
0x14009909b  mov     edx, 1Bh
0x1400990a0  mov     r9d, eax
0x1400990a3  lea     r8, WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids
0x1400990aa  mov     rcx, [rcx+10h]
0x1400990ae  call    WPP_SF_d
0x1400990b3  mov     edx, 3E8h; void *
0x1400990b8  mov     rcx, [rdi+38h]; this
0x1400990bc  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x1400990c1  test    al, al
0x1400990c3  jz      short loc_1400990F2
0x1400990c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400990cc  cmp     rcx, rsi
0x1400990cf  jz      short loc_1400990F2
0x1400990d1  test    byte ptr [rcx+1Ch], 1
0x1400990d5  jz      short loc_1400990F2
0x1400990d7  mov     edx, 1Ch
0x1400990dc  mov     r9d, 800705B4h
0x1400990e2  lea     r8, WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids
0x1400990e9  mov     rcx, [rcx+10h]
0x1400990ed  call    WPP_SF_d
0x1400990f2  mov     rcx, [rdi+8]; hObject
0x1400990f6  test    rcx, rcx
0x1400990f9  jz      short loc_140099109
0x1400990fb  call    cs:__imp_CloseHandle
0x140099101  mov     qword ptr [rdi+8], 0
0x140099109  cmp     qword ptr [rdi], 0
0x14009910d  jz      short loc_14009911F
0x14009910f  mov     rcx, [rdi]; hObject
0x140099112  call    cs:__imp_CloseHandle
0x140099118  mov     qword ptr [rdi], 0
0x14009911f  mov     rcx, [rsp+48h+var_18]
0x140099124  xor     rcx, rsp; StackCookie
0x140099127  call    __security_check_cookie
0x14009912c  mov     rsi, [rsp+48h+arg_0]
0x140099131  add     rsp, 40h
0x140099135  pop     rdi
0x140099136  retn
0x140099137  call    terminate
```

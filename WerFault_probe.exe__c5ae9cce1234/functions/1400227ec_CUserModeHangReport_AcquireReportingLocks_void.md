# CUserModeHangReport::AcquireReportingLocks(void)

- ea: `0x1400227ec`
- end: `0x140022afc`
- name: `?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ`
- size: `784`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140025670`
- `0x140026410`

## callees

- `0x140002470`
- `0x1400032d7`
- `0x1400032ef`
- `0x14000b540`
- `0x140014474`
- `0x1400144b4`
- `0x140015b40`
- `0x1400227ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140022a41`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140022a41`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400229bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400229bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140022a0c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140022a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400228e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022a2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022a61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400228e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022966`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022a2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022a61`

## string_xrefs

- `0x1400228fb`: `Local\WERReportingForProcessComplete%u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserModeHangReport::AcquireReportingLocks(
        CUserModeHangReport *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  int v7; // r12d
  __int64 v8; // r15
  CUserModeHangReport *v9; // rcx
  unsigned int *v10; // rax
  unsigned int v11; // r14d
  __int64 v12; // rax
  void *v13; // rcx
  signed int LastError_0; // eax
  char *EventW; // rbx
  HANDLE MutexW; // rdi
  void *v18; // rcx
  bool v19; // sf
  __int64 v20; // [rsp+20h] [rbp-F8h]
  WCHAR Name[64]; // [rsp+40h] [rbp-D8h] BYREF

  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = WPP_GLOBAL_Control;
  do
  {
    if ( *((_QWORD *)this + v8 + 3118) != -1 && *((_QWORD *)this + v8 + 3118) != 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, &WPP_GLOBAL_Control, a3, a4);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v7 )
    {
      v12 = *((_QWORD *)this + 3054);
      if ( !v12 )
        goto LABEL_26;
      v11 = *(_DWORD *)(v12 + 4 * v8 + 1160);
      if ( !v11 )
        goto LABEL_26;
      if ( (*((_QWORD *)this + v8 + 3095) == -1 || *((_QWORD *)this + v8 + 3095) == 0)
        && v9 != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v9 + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v9 + 2), 101, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v11);
      }
    }
    else
    {
      v10 = (unsigned int *)*((_QWORD *)this + 2988);
      if ( v10 )
        v11 = *v10;
      else
        v11 = 0;
      if ( !v11 )
        goto LABEL_26;
    }
    v13 = (void *)*((_QWORD *)this + v8 + 3118);
    *((_QWORD *)this + v8 + 3118) = 0;
    if ( (unsigned __int64)v13 + 1 > 1 )
      CloseHandle(v13);
    LastError_0 = StringCchPrintfW(Name, 0x40u, L"Local\\WERReportingForProcessComplete%u", v11, v20);
    if ( LastError_0 < 0 )
    {
      EventW = 0;
LABEL_20:
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LODWORD(v20) = LastError_0;
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
LABEL_23:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_24;
      }
      goto LABEL_24;
    }
    EventW = (char *)CreateEventW(0, 1, 0, Name);
    if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
      goto LABEL_39;
    LastError_0 = StringCchPrintfW(Name, 0x40u, L"Local\\WERReportingForProcess%u", v11);
    if ( LastError_0 < 0 )
      goto LABEL_20;
    SetLastError_0(0);
    MutexW = CreateMutexW(0, 1, Name);
    if ( (unsigned __int64)MutexW + 1 <= 1 )
    {
LABEL_39:
      LastError_0 = GetLastError_0();
      v19 = LastError_0 < 0;
      if ( LastError_0 > 0 )
      {
        LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
        v19 = LastError_0 < 0;
      }
      if ( v19 )
        goto LABEL_20;
    }
    else
    {
      if ( GetLastError_0() == 183 )
      {
        CloseHandle(MutexW);
        LastError_0 = -2145681404;
        goto LABEL_20;
      }
      ResetEvent(EventW);
      v18 = (void *)*((_QWORD *)this + v8 + 3118);
      *((_QWORD *)this + v8 + 3118) = MutexW;
      if ( (unsigned __int64)v18 + 1 > 1 )
        CloseHandle(v18);
    }
    ++v5;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v11);
      goto LABEL_23;
    }
LABEL_24:
    ++v6;
    if ( (unsigned __int64)(EventW + 1) > 1 )
    {
      CloseHandle(EventW);
      v9 = WPP_GLOBAL_Control;
    }
LABEL_26:
    ++v7;
    ++v8;
  }
  while ( v7 < 16 );
  if ( v5 > v6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, &WPP_GLOBAL_Control, a3, a4);
  if ( v6 )
  {
    if ( v5 )
      return v5 != v6;
    return v6 != 0 ? 0x80004005 : 0;
  }
  else
  {
    if ( !v5 )
      return v6 != 0 ? 0x80004005 : 0;
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x1400227ec  push    rbx
0x1400227ee  push    rbp
0x1400227ef  push    rsi
0x1400227f0  push    rdi
0x1400227f1  push    r12
0x1400227f3  push    r13
0x1400227f5  push    r14
0x1400227f7  push    r15
0x1400227f9  sub     rsp, 0D8h
0x140022800  mov     rax, cs:__security_cookie
0x140022807  xor     rax, rsp
0x14002280a  mov     [rsp+118h+var_58], rax
0x140022812  mov     r13, rcx
0x140022815  xor     esi, esi
0x140022817  xor     ebp, ebp
0x140022819  xor     r12d, r12d
0x14002281c  xor     r15d, r15d
0x14002281f  lea     rdx, WPP_GLOBAL_Control
0x140022826  mov     rcx, cs:WPP_GLOBAL_Control
0x14002282d  mov     rax, [r13+r15*8+6170h]
0x140022835  inc     rax
0x140022838  cmp     rax, 1
0x14002283c  jbe     short loc_140022851
0x14002283e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140022843  mov     rcx, cs:WPP_GLOBAL_Control
0x14002284a  lea     rdx, WPP_GLOBAL_Control
0x140022851  test    r12d, r12d
0x140022854  jnz     short loc_140022875
0x140022856  mov     rax, [r13+5D60h]
0x14002285d  test    rax, rax
0x140022860  jz      short loc_140022867
0x140022862  mov     r14d, [rax]
0x140022865  jmp     short loc_14002286A
0x140022867  xor     r14d, r14d
0x14002286a  test    r14d, r14d
0x14002286d  jz      loc_140022973
0x140022873  jmp     short loc_1400228CB
0x140022875  mov     rax, [r13+5F70h]
0x14002287c  test    rax, rax
0x14002287f  jz      loc_140022973
0x140022885  mov     r14d, [rax+r15*4+488h]
0x14002288d  test    r14d, r14d
0x140022890  jz      loc_140022973
0x140022896  mov     rax, [r13+r15*8+60B8h]
0x14002289e  inc     rax
0x1400228a1  cmp     rax, 1
0x1400228a5  ja      short loc_1400228CB
0x1400228a7  cmp     rcx, rdx
0x1400228aa  jz      short loc_1400228CB
0x1400228ac  test    byte ptr [rcx+1Ch], 2
0x1400228b0  jz      short loc_1400228CB
0x1400228b2  mov     edx, 65h ; 'e'
0x1400228b7  mov     r9d, r14d
0x1400228ba  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400228c1  mov     rcx, [rcx+10h]
0x1400228c5  call    WPP_SF_d
0x1400228ca  nop
0x1400228cb  mov     rcx, [r13+r15*8+6170h]; hObject
0x1400228d3  mov     qword ptr [r13+r15*8+6170h], 0
0x1400228df  lea     rax, [rcx+1]
0x1400228e3  cmp     rax, 1
0x1400228e7  jbe     short loc_1400228EF
0x1400228e9  call    cs:__imp_CloseHandle
0x1400228ef  mov     [rsp+118h+var_E8], 0
0x1400228f8  mov     r9d, r14d
0x1400228fb  lea     r8, aLocalWerreport; "Local\\WERReportingForProcessComplete%u"
0x140022902  mov     edx, 40h ; '@'; unsigned __int64
0x140022907  lea     rcx, [rsp+118h+Name]; wchar_t *
0x14002290c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140022911  test    eax, eax
0x140022913  jns     loc_1400229AF
0x140022919  xor     ebx, ebx
0x14002291b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022922  lea     rdx, WPP_GLOBAL_Control
0x140022929  cmp     rcx, rdx
0x14002292c  jz      short loc_140022957
0x14002292e  test    byte ptr [rcx+1Ch], 2
0x140022932  jz      short loc_140022957
0x140022934  mov     edx, 67h ; 'g'
0x140022939  mov     [rsp+118h+var_F8], eax
0x14002293d  mov     r9d, r14d
0x140022940  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022947  mov     rcx, [rcx+10h]
0x14002294b  call    WPP_SF_Dd
0x140022950  mov     rcx, cs:WPP_GLOBAL_Control
0x140022957  inc     ebp
0x140022959  lea     rax, [rbx+1]
0x14002295d  cmp     rax, 1
0x140022961  jbe     short loc_140022973
0x140022963  mov     rcx, rbx; hObject
0x140022966  call    cs:__imp_CloseHandle
0x14002296c  mov     rcx, cs:WPP_GLOBAL_Control
0x140022973  inc     r12d
0x140022976  inc     r15
0x140022979  cmp     r12d, 10h
0x14002297d  lea     rdx, WPP_GLOBAL_Control
0x140022984  jl      loc_14002282D
0x14002298a  cmp     esi, ebp
0x14002298c  jbe     short loc_140022993
0x14002298e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140022993  test    ebp, ebp
0x140022995  jz      loc_140022AC2
0x14002299b  test    esi, esi
0x14002299d  jz      loc_140022AC6
0x1400229a3  xor     eax, eax
0x1400229a5  cmp     esi, ebp
0x1400229a7  setnz   al
0x1400229aa  jmp     loc_140022AD8
0x1400229af  lea     r9, [rsp+118h+Name]; lpName
0x1400229b4  xor     r8d, r8d; bInitialState
0x1400229b7  lea     edx, [r8+1]; bManualReset
0x1400229bb  xor     ecx, ecx; lpEventAttributes
0x1400229bd  call    cs:__imp_CreateEventW
0x1400229c3  mov     rbx, rax
0x1400229c6  mov     [rsp+118h+var_E8], rax
0x1400229cb  inc     rax
0x1400229ce  cmp     rax, 1
0x1400229d2  jbe     loc_140022A69
0x1400229d8  mov     r9d, r14d
0x1400229db  lea     r8, aLocalWerreport_0; "Local\\WERReportingForProcess%u"
0x1400229e2  mov     edx, 40h ; '@'; unsigned __int64
0x1400229e7  lea     rcx, [rsp+118h+Name]; wchar_t *
0x1400229ec  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400229f1  test    eax, eax
0x1400229f3  js      loc_14002291B
0x1400229f9  xor     ecx, ecx; dwErrCode
0x1400229fb  call    SetLastError_0
0x140022a00  lea     r8, [rsp+118h+Name]; lpName
0x140022a05  mov     edx, 1; bInitialOwner
0x140022a0a  xor     ecx, ecx; lpMutexAttributes
0x140022a0c  call    cs:__imp_CreateMutexW
0x140022a12  mov     rdi, rax
0x140022a15  lea     rcx, [rax+1]
0x140022a19  cmp     rcx, 1
0x140022a1d  jbe     short loc_140022A69
0x140022a1f  call    GetLastError_0
0x140022a24  cmp     eax, 0B7h
0x140022a29  jnz     short loc_140022A3E
0x140022a2b  mov     rcx, rdi; hObject
0x140022a2e  call    cs:__imp_CloseHandle
0x140022a34  mov     eax, 801B8004h
0x140022a39  jmp     loc_14002291B
0x140022a3e  mov     rcx, rbx; hEvent
0x140022a41  call    cs:__imp_ResetEvent
0x140022a47  mov     rcx, [r13+r15*8+6170h]; hObject
0x140022a4f  mov     [r13+r15*8+6170h], rdi
0x140022a57  lea     rax, [rcx+1]
0x140022a5b  cmp     rax, 1
0x140022a5f  jbe     short loc_140022A82
0x140022a61  call    cs:__imp_CloseHandle
0x140022a67  jmp     short loc_140022A82
0x140022a69  call    GetLastError_0
0x140022a6e  test    eax, eax
0x140022a70  jle     short loc_140022A7C
0x140022a72  movzx   eax, ax
0x140022a75  or      eax, 80070000h
0x140022a7a  test    eax, eax
0x140022a7c  js      loc_14002291B
0x140022a82  inc     esi
0x140022a84  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a8b  lea     rdx, WPP_GLOBAL_Control
0x140022a92  cmp     rcx, rdx
0x140022a95  jz      loc_140022957
0x140022a9b  test    byte ptr [rcx+1Ch], 4
0x140022a9f  jz      loc_140022957
0x140022aa5  mov     edx, 66h ; 'f'
0x140022aaa  mov     r9d, r14d
0x140022aad  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140022ab4  mov     rcx, [rcx+10h]
0x140022ab8  call    WPP_SF_d
0x140022abd  jmp     loc_140022950
0x140022ac2  test    esi, esi
0x140022ac4  jnz     short loc_140022AD3
0x140022ac6  xor     eax, eax
0x140022ac8  cmp     eax, ebp
0x140022aca  sbb     eax, eax
0x140022acc  and     eax, 80004005h
0x140022ad1  jmp     short loc_140022AD8
0x140022ad3  mov     eax, 80004005h
0x140022ad8  mov     rcx, [rsp+118h+var_58]
0x140022ae0  xor     rcx, rsp; StackCookie
0x140022ae3  call    __security_check_cookie
0x140022ae8  add     rsp, 0D8h
0x140022aef  pop     r15
0x140022af1  pop     r14
0x140022af3  pop     r13
0x140022af5  pop     r12
0x140022af7  pop     rdi
0x140022af8  pop     rsi
0x140022af9  pop     rbp
0x140022afa  pop     rbx
0x140022afb  retn
```

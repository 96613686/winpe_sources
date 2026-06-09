# CUserModeHangReport::AcquireReportingLocks(void)

- ea: `0x140023e8c`
- end: `0x1400241c7`
- name: `?AcquireReportingLocks@CUserModeHangReport@@AEAAJXZ`
- size: `827`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140026f70`
- `0x140027d70`

## callees

- `0x140002490`
- `0x140003327`
- `0x14000333f`
- `0x14000b580`
- `0x140014f14`
- `0x140014f58`
- `0x1400166ec`
- `0x140023e8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400240ff`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1400240ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140024069`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140024069`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400240be`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1400240be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002400c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400240e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024125`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002400c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400240e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024125`

## string_xrefs

- `0x140023fa1`: `Local\WERReportingForProcessComplete%u`

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
        WPP_SF_d(*((_QWORD *)v9 + 2), 101, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v11);
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
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v11);
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
0x140023e8c  push    rbx
0x140023e8e  push    rbp
0x140023e8f  push    rsi
0x140023e90  push    rdi
0x140023e91  push    r12
0x140023e93  push    r13
0x140023e95  push    r14
0x140023e97  push    r15
0x140023e99  sub     rsp, 0D8h
0x140023ea0  mov     rax, cs:__security_cookie
0x140023ea7  xor     rax, rsp
0x140023eaa  mov     [rsp+118h+var_58], rax
0x140023eb2  mov     r13, rcx
0x140023eb5  xor     esi, esi
0x140023eb7  xor     ebp, ebp
0x140023eb9  xor     r12d, r12d
0x140023ebc  xor     r15d, r15d
0x140023ebf  lea     rdx, WPP_GLOBAL_Control
0x140023ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ecd  mov     rax, [r13+r15*8+6170h]
0x140023ed5  inc     rax
0x140023ed8  cmp     rax, 1
0x140023edc  jbe     short loc_140023EF1
0x140023ede  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140023ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x140023eea  lea     rdx, WPP_GLOBAL_Control
0x140023ef1  test    r12d, r12d
0x140023ef4  jnz     short loc_140023F15
0x140023ef6  mov     rax, [r13+5D60h]
0x140023efd  test    rax, rax
0x140023f00  jz      short loc_140023F07
0x140023f02  mov     r14d, [rax]
0x140023f05  jmp     short loc_140023F0A
0x140023f07  xor     r14d, r14d
0x140023f0a  test    r14d, r14d
0x140023f0d  jz      loc_14002401F
0x140023f13  jmp     short loc_140023F6B
0x140023f15  mov     rax, [r13+5F70h]
0x140023f1c  test    rax, rax
0x140023f1f  jz      loc_14002401F
0x140023f25  mov     r14d, [rax+r15*4+488h]
0x140023f2d  test    r14d, r14d
0x140023f30  jz      loc_14002401F
0x140023f36  mov     rax, [r13+r15*8+60B8h]
0x140023f3e  inc     rax
0x140023f41  cmp     rax, 1
0x140023f45  ja      short loc_140023F6B
0x140023f47  cmp     rcx, rdx
0x140023f4a  jz      short loc_140023F6B
0x140023f4c  test    byte ptr [rcx+1Ch], 2
0x140023f50  jz      short loc_140023F6B
0x140023f52  mov     edx, 65h ; 'e'
0x140023f57  mov     r9d, r14d
0x140023f5a  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023f61  mov     rcx, [rcx+10h]
0x140023f65  call    WPP_SF_d
0x140023f6a  nop
0x140023f6b  mov     rcx, [r13+r15*8+6170h]; hObject
0x140023f73  mov     qword ptr [r13+r15*8+6170h], 0
0x140023f7f  lea     rax, [rcx+1]
0x140023f83  cmp     rax, 1
0x140023f87  jbe     short loc_140023F95
0x140023f89  call    cs:__imp_CloseHandle
0x140023f90  nop     dword ptr [rax+rax+00h]
0x140023f95  mov     [rsp+118h+var_E8], 0
0x140023f9e  mov     r9d, r14d
0x140023fa1  lea     r8, aLocalWerreport; "Local\\WERReportingForProcessComplete%u"
0x140023fa8  mov     edx, 40h ; '@'; unsigned __int64
0x140023fad  lea     rcx, [rsp+118h+Name]; wchar_t *
0x140023fb2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140023fb7  test    eax, eax
0x140023fb9  jns     loc_14002405B
0x140023fbf  xor     ebx, ebx
0x140023fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140023fc8  lea     rdx, WPP_GLOBAL_Control
0x140023fcf  cmp     rcx, rdx
0x140023fd2  jz      short loc_140023FFD
0x140023fd4  test    byte ptr [rcx+1Ch], 2
0x140023fd8  jz      short loc_140023FFD
0x140023fda  mov     edx, 67h ; 'g'
0x140023fdf  mov     [rsp+118h+var_F8], eax
0x140023fe3  mov     r9d, r14d
0x140023fe6  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023fed  mov     rcx, [rcx+10h]
0x140023ff1  call    WPP_SF_Dd
0x140023ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ffd  inc     ebp
0x140023fff  lea     rax, [rbx+1]
0x140024003  cmp     rax, 1
0x140024007  jbe     short loc_14002401F
0x140024009  mov     rcx, rbx; hObject
0x14002400c  call    cs:__imp_CloseHandle
0x140024013  nop     dword ptr [rax+rax+00h]
0x140024018  mov     rcx, cs:WPP_GLOBAL_Control
0x14002401f  inc     r12d
0x140024022  inc     r15
0x140024025  cmp     r12d, 10h
0x140024029  lea     rdx, WPP_GLOBAL_Control
0x140024030  jl      loc_140023ECD
0x140024036  cmp     esi, ebp
0x140024038  jbe     short loc_14002403F
0x14002403a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002403f  test    ebp, ebp
0x140024041  jz      loc_14002418C
0x140024047  test    esi, esi
0x140024049  jz      loc_140024190
0x14002404f  xor     eax, eax
0x140024051  cmp     esi, ebp
0x140024053  setnz   al
0x140024056  jmp     loc_1400241A2
0x14002405b  lea     r9, [rsp+118h+Name]; lpName
0x140024060  xor     r8d, r8d; bInitialState
0x140024063  lea     edx, [r8+1]; bManualReset
0x140024067  xor     ecx, ecx; lpEventAttributes
0x140024069  call    cs:__imp_CreateEventW
0x140024070  nop     dword ptr [rax+rax+00h]
0x140024075  mov     rbx, rax
0x140024078  mov     [rsp+118h+var_E8], rax
0x14002407d  inc     rax
0x140024080  cmp     rax, 1
0x140024084  jbe     loc_140024133
0x14002408a  mov     r9d, r14d
0x14002408d  lea     r8, aLocalWerreport_0; "Local\\WERReportingForProcess%u"
0x140024094  mov     edx, 40h ; '@'; unsigned __int64
0x140024099  lea     rcx, [rsp+118h+Name]; wchar_t *
0x14002409e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400240a3  test    eax, eax
0x1400240a5  js      loc_140023FC1
0x1400240ab  xor     ecx, ecx; dwErrCode
0x1400240ad  call    SetLastError_0
0x1400240b2  lea     r8, [rsp+118h+Name]; lpName
0x1400240b7  mov     edx, 1; bInitialOwner
0x1400240bc  xor     ecx, ecx; lpMutexAttributes
0x1400240be  call    cs:__imp_CreateMutexW
0x1400240c5  nop     dword ptr [rax+rax+00h]
0x1400240ca  mov     rdi, rax
0x1400240cd  lea     rcx, [rax+1]
0x1400240d1  cmp     rcx, 1
0x1400240d5  jbe     short loc_140024133
0x1400240d7  call    GetLastError_0
0x1400240dc  cmp     eax, 0B7h
0x1400240e1  jnz     short loc_1400240FC
0x1400240e3  mov     rcx, rdi; hObject
0x1400240e6  call    cs:__imp_CloseHandle
0x1400240ed  nop     dword ptr [rax+rax+00h]
0x1400240f2  mov     eax, 801B8004h
0x1400240f7  jmp     loc_140023FC1
0x1400240fc  mov     rcx, rbx; hEvent
0x1400240ff  call    cs:__imp_ResetEvent
0x140024106  nop     dword ptr [rax+rax+00h]
0x14002410b  mov     rcx, [r13+r15*8+6170h]; hObject
0x140024113  mov     [r13+r15*8+6170h], rdi
0x14002411b  lea     rax, [rcx+1]
0x14002411f  cmp     rax, 1
0x140024123  jbe     short loc_14002414C
0x140024125  call    cs:__imp_CloseHandle
0x14002412c  nop     dword ptr [rax+rax+00h]
0x140024131  jmp     short loc_14002414C
0x140024133  call    GetLastError_0
0x140024138  test    eax, eax
0x14002413a  jle     short loc_140024146
0x14002413c  movzx   eax, ax
0x14002413f  or      eax, 80070000h
0x140024144  test    eax, eax
0x140024146  js      loc_140023FC1
0x14002414c  inc     esi
0x14002414e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024155  lea     rdx, WPP_GLOBAL_Control
0x14002415c  cmp     rcx, rdx
0x14002415f  jz      loc_140023FFD
0x140024165  test    byte ptr [rcx+1Ch], 4
0x140024169  jz      loc_140023FFD
0x14002416f  mov     edx, 66h ; 'f'
0x140024174  mov     r9d, r14d
0x140024177  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x14002417e  mov     rcx, [rcx+10h]
0x140024182  call    WPP_SF_d
0x140024187  jmp     loc_140023FF6
0x14002418c  test    esi, esi
0x14002418e  jnz     short loc_14002419D
0x140024190  xor     eax, eax
0x140024192  cmp     eax, ebp
0x140024194  sbb     eax, eax
0x140024196  and     eax, 80004005h
0x14002419b  jmp     short loc_1400241A2
0x14002419d  mov     eax, 80004005h
0x1400241a2  mov     rcx, [rsp+118h+var_58]
0x1400241aa  xor     rcx, rsp; StackCookie
0x1400241ad  call    __security_check_cookie
0x1400241b2  add     rsp, 0D8h
0x1400241b9  pop     r15
0x1400241bb  pop     r14
0x1400241bd  pop     r13
0x1400241bf  pop     r12
0x1400241c1  pop     rdi
0x1400241c2  pop     rsi
0x1400241c3  pop     rbp
0x1400241c4  pop     rbx
0x1400241c5  retn
```

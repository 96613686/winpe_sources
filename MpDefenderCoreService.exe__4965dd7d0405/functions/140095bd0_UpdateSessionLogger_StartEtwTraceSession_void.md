# UpdateSessionLogger::StartEtwTraceSession(void)

- ea: `0x140095bd0`
- end: `0x140095e4e`
- name: `?StartEtwTraceSession@UpdateSessionLogger@@EEAAJXZ`
- size: `638`
- prototype: `__int64 __fastcall(UpdateSessionLogger *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140013cdc`
- `0x140017738`
- `0x14003a5c0`
- `0x140059d40`
- `0x14007d210`
- `0x140085d38`
- `0x1400950b0`
- `0x1400956e0`
- `0x140095bd0`
- `0x140096a0c`
- `0x140166990`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140095d51`
- `KERNEL32!CloseHandle` at `0x140095d51`
- `ADVAPI32!CloseTrace` at `0x140095dd8`
- `ADVAPI32!CloseTrace` at `0x140095dd8`
- `ADVAPI32!OpenTraceW` at `0x140095cee`
- `ADVAPI32!OpenTraceW` at `0x140095cee`
- `ADVAPI32!EnableTraceEx2` at `0x140095cab`
- `ADVAPI32!EnableTraceEx2` at `0x140095cab`
- `ADVAPI32!StartTraceW` at `0x140095c6a`
- `ADVAPI32!StartTraceW` at `0x140095c6a`

## pseudocode

```c
__int64 __fastcall UpdateSessionLogger::StartEtwTraceSession(UpdateSessionLogger *this)
{
  WCHAR *v1; // rdi
  const wchar_t *v3; // r8
  const wchar_t *v4; // r8
  const WCHAR *v5; // rdx
  ULONG started; // esi
  TRACEHANDLE v7; // rax
  int v8; // eax
  void *v9; // rcx
  int Thread; // eax
  unsigned int v11; // esi
  _QWORD *v12; // r9
  unsigned int LastFailure; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // ebx
  unsigned int *MatchAnyKeyword; // [rsp+20h] [rbp-1F8h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-1D8h] BYREF

  v1 = (WCHAR *)((char *)this + 56);
  if ( *((_QWORD *)this + 9) )
  {
    v3 = (const wchar_t *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 7u )
      v3 = *(const wchar_t **)v1;
    wcsncpy_s((wchar_t *)this + 120, 0x104u, v3, 0xFFFFFFFFFFFFFFFFuLL);
  }
  if ( *((_QWORD *)this + 13) )
  {
    v4 = (const wchar_t *)((char *)this + 88);
    if ( *((_QWORD *)this + 14) > 7u )
      v4 = *(const wchar_t **)v4;
    wcsncpy_s((wchar_t *)this + 380, 0x104u, v4, 0xFFFFFFFFFFFFFFFFuLL);
  }
  v5 = v1;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v5 = *(const WCHAR **)v1;
  started = StartTraceW((PTRACEHANDLE)this + 5, v5, (PEVENT_TRACE_PROPERTIES)this + 1);
  if ( started )
  {
    LastFailure = HrGetLastFailure();
    v17 = LastFailure;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_dL(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v15, v16, LastFailure, started);
    return v17;
  }
  else
  {
    EnableTraceEx2(*((_QWORD *)this + 5), &ProviderId, 1u, 5u, 0, 0, 0, 0);
    memset(&Logfile, 0, sizeof(Logfile));
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(WCHAR **)v1;
    Logfile.LoggerName = v1;
    Logfile.EventCallback = (PEVENT_CALLBACK)UpdateSessionLogger::EventRecordCallback;
    Logfile.LogFileMode = 268435712;
    v7 = OpenTraceW(&Logfile);
    *((_QWORD *)this + 6) = v7;
    if ( v7 == -1 )
      return 0;
    v8 = UpdateSessionLogger::OpenEtlFileProtectionHandle(this);
    if ( v8 < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        46,
        &WPP_59ae06a751773575a42227eddeae96fd_Traceguids,
        (unsigned int)v8);
    }
    v9 = (void *)*((_QWORD *)this + 160);
    if ( v9 )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 160) = 0;
    }
    Thread = CommonUtil::UtilSimpleCreateThread(
               (UpdateSessionLogger *)((char *)this + 1280),
               (void **)UpdateSessionLogger::RealtimeConsumerThreadProcStatic,
               (unsigned int (*)(void *))this,
               0,
               MatchAnyKeyword);
    v11 = Thread;
    if ( Thread >= 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v12 = (_QWORD *)((char *)this + 88);
        if ( *((_QWORD *)this + 14) > 7u )
          v12 = (_QWORD *)*v12;
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, &WPP_59ae06a751773575a42227eddeae96fd_Traceguids, v12);
      }
      return 0;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        48,
        &WPP_59ae06a751773575a42227eddeae96fd_Traceguids,
        (unsigned int)Thread);
    CloseTrace(*((_QWORD *)this + 6));
    *((_QWORD *)this + 6) = 0;
    UpdateSessionLogger::CloseEtlFileProtectionHandle(this);
    return v11;
  }
}

```

## disassembly

```asm
0x140095bd0  mov     [rsp+arg_8], rbx
0x140095bd5  mov     [rsp+arg_10], rsi
0x140095bda  mov     [rsp+arg_18], rdi
0x140095bdf  push    r14
0x140095be1  sub     rsp, 210h
0x140095be8  mov     rax, cs:__security_cookie
0x140095bef  xor     rax, rsp
0x140095bf2  mov     [rsp+218h+var_18], rax
0x140095bfa  cmp     qword ptr [rcx+48h], 0
0x140095bff  lea     rdi, [rcx+38h]
0x140095c03  mov     rbx, rcx
0x140095c06  mov     esi, 104h
0x140095c0b  jz      short loc_140095C2D
0x140095c0d  cmp     qword ptr [rdi+18h], 7
0x140095c12  mov     r8, rdi
0x140095c15  jbe     short loc_140095C1A
0x140095c17  mov     r8, [rdi]; Source
0x140095c1a  add     rcx, 0F0h; Destination
0x140095c21  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140095c25  mov     rdx, rsi; SizeInWords
0x140095c28  call    wcsncpy_s
0x140095c2d  cmp     qword ptr [rbx+68h], 0
0x140095c32  jz      short loc_140095C55
0x140095c34  lea     r8, [rbx+58h]
0x140095c38  cmp     qword ptr [r8+18h], 7
0x140095c3d  jbe     short loc_140095C42
0x140095c3f  mov     r8, [r8]; Source
0x140095c42  lea     rcx, [rbx+2F8h]; Destination
0x140095c49  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140095c4d  mov     rdx, rsi; SizeInWords
0x140095c50  call    wcsncpy_s
0x140095c55  cmp     qword ptr [rdi+18h], 7
0x140095c5a  mov     rdx, rdi
0x140095c5d  jbe     short loc_140095C62
0x140095c5f  mov     rdx, [rdi]; InstanceName
0x140095c62  lea     r8, [rbx+78h]; Properties
0x140095c66  lea     rcx, [rbx+28h]; TraceHandle
0x140095c6a  call    cs:__imp_StartTraceW
0x140095c70  mov     esi, eax
0x140095c72  test    eax, eax
0x140095c74  jnz     loc_140095DF2
0x140095c7a  mov     rcx, [rbx+28h]; TraceHandle
0x140095c7e  lea     r8d, [rax+1]; ControlCode
0x140095c82  mov     [rsp+218h+EnableParameters], 0; EnableParameters
0x140095c8b  lea     rdx, ProviderId; ProviderId
0x140095c92  mov     [rsp+218h+Timeout], eax; Timeout
0x140095c96  mov     r9b, 5; Level
0x140095c99  mov     [rsp+218h+MatchAllKeyword], 0; MatchAllKeyword
0x140095ca2  mov     [rsp+218h+MatchAnyKeyword], 0; unsigned int *
0x140095cab  call    cs:__imp_EnableTraceEx2
0x140095cb1  xor     edx, edx; Val
0x140095cb3  lea     rcx, [rsp+218h+Logfile]; void *
0x140095cb8  mov     r8d, 1C0h; Size
0x140095cbe  call    memset
0x140095cc3  cmp     qword ptr [rdi+18h], 7
0x140095cc8  jbe     short loc_140095CCD
0x140095cca  mov     rdi, [rdi]
0x140095ccd  lea     rax, ?EventRecordCallback@UpdateSessionLogger@@CAXPEAU_EVENT_RECORD@@@Z; UpdateSessionLogger::EventRecordCallback(_EVENT_RECORD *)
0x140095cd4  mov     [rsp+218h+Logfile.LoggerName], rdi
0x140095cd9  lea     rcx, [rsp+218h+Logfile]; Logfile
0x140095cde  mov     qword ptr [rsp+218h+Logfile.1A8h], rax
0x140095ce6  mov     dword ptr [rsp+218h+Logfile.1Ch], 10000100h
0x140095cee  call    cs:__imp_OpenTraceW
0x140095cf4  mov     [rbx+30h], rax
0x140095cf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140095cfc  jz      loc_140095DAA
0x140095d02  mov     rcx, rbx; this
0x140095d05  call    ?OpenEtlFileProtectionHandle@UpdateSessionLogger@@AEAAJXZ; UpdateSessionLogger::OpenEtlFileProtectionHandle(void)
0x140095d0a  lea     r14, WPP_59ae06a751773575a42227eddeae96fd_Traceguids
0x140095d11  lea     rdi, WPP_GLOBAL_Control
0x140095d18  test    eax, eax
0x140095d1a  jns     short loc_140095D42
0x140095d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d23  cmp     rcx, rdi
0x140095d26  jz      short loc_140095D42
0x140095d28  test    byte ptr [rcx+1Ch], 2
0x140095d2c  jz      short loc_140095D42
0x140095d2e  mov     rcx, [rcx+10h]
0x140095d32  mov     edx, 2Eh ; '.'
0x140095d37  mov     r9d, eax
0x140095d3a  mov     r8, r14
0x140095d3d  call    WPP_SF_d
0x140095d42  lea     rsi, [rbx+500h]
0x140095d49  mov     rcx, [rsi]; hObject
0x140095d4c  test    rcx, rcx
0x140095d4f  jz      short loc_140095D5E
0x140095d51  call    cs:__imp_CloseHandle
0x140095d57  mov     qword ptr [rsi], 0
0x140095d5e  xor     r9d, r9d; void *
0x140095d61  lea     rdx, ?RealtimeConsumerThreadProcStatic@UpdateSessionLogger@@CAIPEAX@Z; void **
0x140095d68  mov     r8, rbx; unsigned int (*)(void *)
0x140095d6b  mov     rcx, rsi; this
0x140095d6e  call    ?UtilSimpleCreateThread@CommonUtil@@YAJPEAPEAXP6AIPEAX@Z1PEAK@Z; CommonUtil::UtilSimpleCreateThread(void * *,uint (*)(void *),void *,ulong *)
0x140095d73  mov     esi, eax
0x140095d75  test    eax, eax
0x140095d77  js      short loc_140095DAE
0x140095d79  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d80  cmp     rcx, rdi
0x140095d83  jz      short loc_140095DAA
0x140095d85  test    byte ptr [rcx+1Ch], 4
0x140095d89  jz      short loc_140095DAA
0x140095d8b  lea     r9, [rbx+58h]
0x140095d8f  cmp     qword ptr [r9+18h], 7
0x140095d94  jbe     short loc_140095D99
0x140095d96  mov     r9, [r9]
0x140095d99  mov     rcx, [rcx+10h]
0x140095d9d  mov     edx, 2Fh ; '/'
0x140095da2  mov     r8, r14
0x140095da5  call    WPP_SF_S
0x140095daa  xor     eax, eax
0x140095dac  jmp     short loc_140095E24
0x140095dae  mov     rcx, cs:WPP_GLOBAL_Control
0x140095db5  cmp     rcx, rdi
0x140095db8  jz      short loc_140095DD4
0x140095dba  test    byte ptr [rcx+1Ch], 1
0x140095dbe  jz      short loc_140095DD4
0x140095dc0  mov     rcx, [rcx+10h]
0x140095dc4  mov     edx, 30h ; '0'
0x140095dc9  mov     r9d, esi
0x140095dcc  mov     r8, r14
0x140095dcf  call    WPP_SF_d
0x140095dd4  mov     rcx, [rbx+30h]; TraceHandle
0x140095dd8  call    cs:__imp_CloseTrace
0x140095dde  mov     rcx, rbx; this
0x140095de1  mov     qword ptr [rbx+30h], 0
0x140095de9  call    ?CloseEtlFileProtectionHandle@UpdateSessionLogger@@AEAAXXZ; UpdateSessionLogger::CloseEtlFileProtectionHandle(void)
0x140095dee  mov     eax, esi
0x140095df0  jmp     short loc_140095E24
0x140095df2  call    HrGetLastFailure
0x140095df7  mov     ebx, eax
0x140095df9  mov     rcx, cs:WPP_GLOBAL_Control
0x140095e00  lea     rdi, WPP_GLOBAL_Control
0x140095e07  cmp     rcx, rdi
0x140095e0a  jz      short loc_140095E22
0x140095e0c  test    byte ptr [rcx+1Ch], 1
0x140095e10  jz      short loc_140095E22
0x140095e12  mov     rcx, [rcx+10h]
0x140095e16  mov     r9d, eax
0x140095e19  mov     dword ptr [rsp+218h+MatchAnyKeyword], esi
0x140095e1d  call    WPP_SF_dL
0x140095e22  mov     eax, ebx
0x140095e24  mov     rcx, [rsp+218h+var_18]
0x140095e2c  xor     rcx, rsp; StackCookie
0x140095e2f  call    __security_check_cookie
0x140095e34  lea     r11, [rsp+218h+var_8]
0x140095e3c  mov     rbx, [r11+18h]
0x140095e40  mov     rsi, [r11+20h]
0x140095e44  mov     rdi, [r11+28h]
0x140095e48  mov     rsp, r11
0x140095e4b  pop     r14
0x140095e4d  retn
```

# CHangReport::StaticCancelCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x14001f870`
- end: `0x14001fa2b`
- name: `?StaticCancelCallback@CHangReport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `443`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14001444c`
- `0x140015b40`
- `0x14001f200`
- `0x14001f870`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fa0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fa0e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14001f9e8`
- `wer!WerpReportCancel` at `0x14001fa17`
- `wer!WerpReportCancel` at `0x14001fa17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHangReport::StaticCancelCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PTP_WAIT *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  CUserModeHangReport *v6; // rcx
  PTP_WAIT *v7; // rdi
  __int64 v8; // rdx
  PTP_WAIT v9; // rsi
  struct _TP_WAIT *v10; // rcx
  struct _TP_WAIT *v11; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-48h] BYREF
  char v13; // [rsp+28h] [rbp-40h]

  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance, 0, Wait, WaitResult);
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
  }
  CHangReport::Lock(Context, &lpCriticalSection, L"CHangReport::CancelCallback");
  if ( Wait != Context[3094] )
  {
    v7 = Context + 3093;
    if ( Wait == Context[3093] )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_23;
      }
      v8 = 12;
    }
    else if ( Wait == Context[3092] )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_23;
      }
      v8 = 13;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_23;
      }
      v8 = 14;
    }
    WPP_SF_(*((_QWORD *)v6 + 2), v8, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    v6 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = Context + 3093;
LABEL_23:
  v9 = Context[3055];
  if ( v6 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 15, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
  *((_DWORD *)Context + 15) = 1;
  v10 = Context[3094];
  if ( v10 )
    SetThreadpoolWait(v10, 0, 0);
  if ( *v7 )
    SetThreadpoolWait(*v7, 0, 0);
  v11 = Context[3092];
  if ( v11 )
    SetThreadpoolWait(v11, 0, 0);
  (*((void (__fastcall **)(PTP_WAIT *, PTP_WAIT))*Context + 7))(Context, Wait);
  if ( !v13 )
    __int2c();
  LeaveCriticalSection(lpCriticalSection);
  WerpReportCancel(v9);
}

```

## disassembly

```asm
0x14001f870  push    rbx
0x14001f872  push    rbp
0x14001f873  push    rsi
0x14001f874  push    rdi
0x14001f875  push    r14
0x14001f877  push    r15
0x14001f879  sub     rsp, 38h
0x14001f87d  mov     rbp, r8
0x14001f880  mov     rbx, rdx
0x14001f883  test    rdx, rdx
0x14001f886  jnz     short loc_14001F88D
0x14001f888  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14001f88d  lea     r14, WPP_GLOBAL_Control
0x14001f894  mov     sil, 4
0x14001f897  lea     r15, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x14001f89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8a5  cmp     rcx, r14
0x14001f8a8  jz      short loc_14001F8C1
0x14001f8aa  test    [rcx+1Ch], sil
0x14001f8ae  jz      short loc_14001F8C1
0x14001f8b0  mov     edx, 0Ah
0x14001f8b5  mov     r8, r15
0x14001f8b8  mov     rcx, [rcx+10h]
0x14001f8bc  call    WPP_SF_
0x14001f8c1  lea     r8, aChangreportCan; "CHangReport::CancelCallback"
0x14001f8c8  lea     rdx, [rsp+68h+lpCriticalSection]
0x14001f8cd  mov     rcx, rbx
0x14001f8d0  call    ?Lock@CHangReport@@IEAA?AV?$unique_lock@Vrecursive_mutex@utl@@@utl@@PEB_W@Z; CHangReport::Lock(wchar_t const *)
0x14001f8d5  nop
0x14001f8d6  cmp     rbp, [rbx+60B0h]
0x14001f8dd  jnz     short loc_14001F912
0x14001f8df  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8e6  cmp     rcx, r14
0x14001f8e9  jz      short loc_14001F909
0x14001f8eb  test    [rcx+1Ch], sil
0x14001f8ef  jz      short loc_14001F909
0x14001f8f1  mov     edx, 0Bh
0x14001f8f6  mov     r8, r15
0x14001f8f9  mov     rcx, [rcx+10h]
0x14001f8fd  call    WPP_SF_
0x14001f902  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f909  lea     rdi, [rbx+60A8h]
0x14001f910  jmp     short loc_14001F983
0x14001f912  lea     rdi, [rbx+60A8h]
0x14001f919  cmp     rbp, [rdi]
0x14001f91c  jnz     short loc_14001F937
0x14001f91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f925  cmp     rcx, r14
0x14001f928  jz      short loc_14001F983
0x14001f92a  test    [rcx+1Ch], sil
0x14001f92e  jz      short loc_14001F983
0x14001f930  mov     edx, 0Ch
0x14001f935  jmp     short loc_14001F970
0x14001f937  cmp     rbp, [rbx+60A0h]
0x14001f93e  jnz     short loc_14001F959
0x14001f940  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f947  cmp     rcx, r14
0x14001f94a  jz      short loc_14001F983
0x14001f94c  test    [rcx+1Ch], sil
0x14001f950  jz      short loc_14001F983
0x14001f952  mov     edx, 0Dh
0x14001f957  jmp     short loc_14001F970
0x14001f959  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f960  cmp     rcx, r14
0x14001f963  jz      short loc_14001F983
0x14001f965  test    byte ptr [rcx+1Ch], 1
0x14001f969  jz      short loc_14001F983
0x14001f96b  mov     edx, 0Eh
0x14001f970  mov     r8, r15
0x14001f973  mov     rcx, [rcx+10h]
0x14001f977  call    WPP_SF_
0x14001f97c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f983  mov     rsi, [rbx+5F78h]
0x14001f98a  cmp     rcx, r14
0x14001f98d  jz      short loc_14001F9A6
0x14001f98f  test    byte ptr [rcx+1Ch], 8
0x14001f993  jz      short loc_14001F9A6
0x14001f995  mov     edx, 0Fh
0x14001f99a  mov     r8, r15
0x14001f99d  mov     rcx, [rcx+10h]
0x14001f9a1  call    WPP_SF_
0x14001f9a6  mov     dword ptr [rbx+3Ch], 1
0x14001f9ad  mov     rcx, [rbx+60B0h]; pwa
0x14001f9b4  test    rcx, rcx
0x14001f9b7  jz      short loc_14001F9C4
0x14001f9b9  xor     r8d, r8d; pftTimeout
0x14001f9bc  xor     edx, edx; h
0x14001f9be  call    cs:__imp_SetThreadpoolWait
0x14001f9c4  mov     rcx, [rdi]; pwa
0x14001f9c7  test    rcx, rcx
0x14001f9ca  jz      short loc_14001F9D7
0x14001f9cc  xor     r8d, r8d; pftTimeout
0x14001f9cf  xor     edx, edx; h
0x14001f9d1  call    cs:__imp_SetThreadpoolWait
0x14001f9d7  mov     rcx, [rbx+60A0h]; pwa
0x14001f9de  test    rcx, rcx
0x14001f9e1  jz      short loc_14001F9EE
0x14001f9e3  xor     r8d, r8d; pftTimeout
0x14001f9e6  xor     edx, edx; h
0x14001f9e8  call    cs:__imp_SetThreadpoolWait
0x14001f9ee  mov     rax, [rbx]
0x14001f9f1  mov     rdx, rbp
0x14001f9f4  mov     rcx, rbx
0x14001f9f7  mov     rax, [rax+38h]
0x14001f9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fa00  cmp     [rsp+68h+var_40], 0
0x14001fa05  jnz     short loc_14001FA09
0x14001fa07  int     2Ch; Windows NT - assertion failure
0x14001fa09  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x14001fa0e  call    cs:__imp_LeaveCriticalSection
0x14001fa14  mov     rcx, rsi
0x14001fa17  call    cs:__imp_WerpReportCancel
0x14001fa1d  nop
0x14001fa1e  add     rsp, 38h
0x14001fa22  pop     r15
0x14001fa24  pop     r14
0x14001fa26  pop     rdi
0x14001fa27  pop     rsi
0x14001fa28  pop     rbp
0x14001fa29  pop     rbx
0x14001fa2a  retn
```

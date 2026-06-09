# CTieringEngineLib::ProcessEvents(void)

- ea: `0x140007c90`
- end: `0x140007e77`
- name: `?ProcessEvents@CTieringEngineLib@@AEAAJXZ`
- size: `487`
- prototype: `__int64 __fastcall(CTieringEngineLib *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140007f18`

## callees

- `0x140002323`
- `0x140002db0`
- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140007c90`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d4d`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x140007db6`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x140007db6`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x140007d3a`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x140007d3a`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::ProcessEvents(CTieringEngineLib *this)
{
  ULONG64 v2; // rax
  signed int LastError; // eax
  int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  ULONG v7; // eax
  _BYTE v9[8]; // [rsp+20h] [rbp-E0h] BYREF
  int v10; // [rsp+28h] [rbp-D8h]
  ULONG64 HandleArray[2]; // [rsp+30h] [rbp-D0h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineLib::ProcessEvents";
  CHResultImp::CHResultImp((CHResultImp *)v9);
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileMode = 268439808;
  Logfile.LoggerName = HeatTraceSessionName;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)CTieringEngineLib::TraceBufferCallback;
  Logfile.EventCallback = (PEVENT_CALLBACK)CTieringEngineLib::TraceEventRecordCallback;
  v2 = *((_QWORD *)this + 48);
  Logfile.Context = this;
  if ( v2 == -1 && (v2 = OpenTraceW(&Logfile), *((_QWORD *)this + 48) = v2, v2 == -1) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    v10 = v4;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 56;
LABEL_17:
      WPP_SF_d(v5[2], v6, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids, (unsigned int)v4);
    }
  }
  else
  {
    HandleArray[0] = v2;
    v7 = ProcessTrace(HandleArray, 1u, 0, 0);
    if ( !v7 || v7 == 1223 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids);
      }
      v10 = 0;
      v4 = 0;
    }
    else
    {
      v4 = ATL::AtlHresultFromWin32(v7);
      v10 = v4;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 57;
        goto LABEL_17;
      }
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140007c90  mov     [rsp-8+arg_8], rbx
0x140007c95  push    rbp
0x140007c96  lea     rbp, [rsp-110h]
0x140007c9e  sub     rsp, 210h
0x140007ca5  mov     rax, cs:__security_cookie
0x140007cac  xor     rax, rsp
0x140007caf  mov     [rbp+110h+var_10], rax
0x140007cb6  mov     rax, gs:58h
0x140007cbf  mov     rbx, rcx
0x140007cc2  mov     ecx, 8
0x140007cc7  mov     rdx, [rax]
0x140007cca  lea     rax, aCtieringengine_0; "CTieringEngineLib::ProcessEvents"
0x140007cd1  mov     [rcx+rdx], rax
0x140007cd5  lea     rcx, [rsp+210h+var_1F0]; this
0x140007cda  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140007cdf  xor     edx, edx; Val
0x140007ce1  lea     rcx, [rsp+210h+Logfile]; void *
0x140007ce6  mov     r8d, 1C0h; Size
0x140007cec  call    memset_0
0x140007cf1  lea     rax, ?HeatTraceSessionName@@3PAGA; "TieringPolicyEngineRealTimeTrace"
0x140007cf8  mov     dword ptr [rsp+210h+Logfile.1Ch], 10001100h
0x140007d00  mov     [rsp+210h+Logfile.LoggerName], rax
0x140007d05  lea     rax, ?TraceBufferCallback@CTieringEngineLib@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; CTieringEngineLib::TraceBufferCallback(_EVENT_TRACE_LOGFILEW *)
0x140007d0c  mov     [rbp+110h+Logfile.BufferCallback], rax
0x140007d13  lea     rax, ?TraceEventRecordCallback@CTieringEngineLib@@CAXPEAU_EVENT_RECORD@@@Z; CTieringEngineLib::TraceEventRecordCallback(_EVENT_RECORD *)
0x140007d1a  mov     qword ptr [rbp+110h+Logfile.1A8h], rax
0x140007d21  mov     rax, [rbx+180h]
0x140007d28  mov     [rbp+110h+Logfile.Context], rbx
0x140007d2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007d33  jnz     short loc_140007DA2
0x140007d35  lea     rcx, [rsp+210h+Logfile]; Logfile
0x140007d3a  call    cs:__imp_OpenTraceW
0x140007d40  mov     [rbx+180h], rax
0x140007d47  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140007d4b  jnz     short loc_140007DA2
0x140007d4d  call    cs:__imp_GetLastError
0x140007d53  mov     ebx, eax
0x140007d55  test    eax, eax
0x140007d57  jle     short loc_140007D62
0x140007d59  movzx   ebx, ax
0x140007d5c  or      ebx, 80070000h
0x140007d62  test    ebx, ebx
0x140007d64  mov     eax, 80004005h
0x140007d69  cmovns  ebx, eax
0x140007d6c  mov     [rsp+210h+var_1E8], ebx
0x140007d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d77  lea     rax, WPP_GLOBAL_Control
0x140007d7e  cmp     rcx, rax
0x140007d81  jz      loc_140007E4B
0x140007d87  test    byte ptr [rcx+1Ch], 1
0x140007d8b  jz      loc_140007E4B
0x140007d91  cmp     byte ptr [rcx+19h], 2
0x140007d95  jb      loc_140007E4B
0x140007d9b  mov     edx, 38h ; '8'
0x140007da0  jmp     short loc_140007DF8
0x140007da2  xor     r9d, r9d; EndTime
0x140007da5  mov     [rsp+210h+HandleArray], rax
0x140007daa  xor     r8d, r8d; StartTime
0x140007dad  lea     rcx, [rsp+210h+HandleArray]; HandleArray
0x140007db2  lea     edx, [r9+1]; HandleCount
0x140007db6  call    cs:__imp_ProcessTrace
0x140007dbc  test    eax, eax
0x140007dbe  jz      short loc_140007E0D
0x140007dc0  cmp     eax, 4C7h
0x140007dc5  jz      short loc_140007E0D
0x140007dc7  mov     ecx, eax; unsigned int
0x140007dc9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140007dce  mov     ebx, eax
0x140007dd0  mov     [rsp+210h+var_1E8], eax
0x140007dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ddb  lea     rax, WPP_GLOBAL_Control
0x140007de2  cmp     rcx, rax
0x140007de5  jz      short loc_140007E4B
0x140007de7  test    byte ptr [rcx+1Ch], 1
0x140007deb  jz      short loc_140007E4B
0x140007ded  cmp     byte ptr [rcx+19h], 2
0x140007df1  jb      short loc_140007E4B
0x140007df3  mov     edx, 39h ; '9'
0x140007df8  mov     rcx, [rcx+10h]
0x140007dfc  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007e03  mov     r9d, ebx
0x140007e06  call    WPP_SF_d
0x140007e0b  jmp     short loc_140007E4B
0x140007e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e14  lea     rax, WPP_GLOBAL_Control
0x140007e1b  cmp     rcx, rax
0x140007e1e  jz      short loc_140007E41
0x140007e20  test    byte ptr [rcx+1Ch], 1
0x140007e24  jz      short loc_140007E41
0x140007e26  cmp     byte ptr [rcx+19h], 4
0x140007e2a  jb      short loc_140007E41
0x140007e2c  mov     rcx, [rcx+10h]
0x140007e30  lea     r8, WPP_92e7e3ac78e237d967ac9be1c139aa53_Traceguids
0x140007e37  mov     edx, 3Ah ; ':'
0x140007e3c  call    WPP_SF_
0x140007e41  mov     [rsp+210h+var_1E8], 0
0x140007e49  xor     ebx, ebx
0x140007e4b  lea     rcx, [rsp+210h+var_1F0]; this
0x140007e50  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140007e55  mov     eax, ebx
0x140007e57  mov     rcx, [rbp+110h+var_10]
0x140007e5e  xor     rcx, rsp; StackCookie
0x140007e61  call    __security_check_cookie
0x140007e66  mov     rbx, [rsp+210h+arg_8]
0x140007e6e  add     rsp, 210h
0x140007e75  pop     rbp
0x140007e76  retn
```

# BdeSvcProcessWinREEvents(void)

- ea: `0x18000d904`
- end: `0x18000daf1`
- name: `?BdeSvcProcessWinREEvents@@YAXXZ`
- size: `493`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800429e0`

## callees

- `0x180009f30`
- `0x18000d904`
- `0x18000daf8`
- `0x18001b7f0`
- `0x180034070`
- `0x180034d28`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9ef`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000d9ef`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000da99`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000da99`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000da66`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18000da66`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18000da82`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18000da82`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000da3e`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18000da3e`

## pseudocode

```c
void BdeSvcProcessWinREEvents(void)
{
  int v0; // ebx
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-D0h] BYREF
  ULONG64 HandleArray[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR FileName[264]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v4[528]; // [rsp+410h] [rbp+310h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  memset_0(v4, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  memset_0(&Logfile, 0, sizeof(Logfile));
  HandleArray[0] = -1;
  v0 = 0;
  if ( (int)NgscbGetOSVolume(v4) >= 0
    && (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v4, L"BitLockerWinRELog.etl") >= 0
    && GetFileAttributesW(FileName) != -1 )
  {
    v0 = 1;
    memset_0(&Logfile, 0, sizeof(Logfile));
    Logfile.LogFileMode = 0x10000000;
    Logfile.LogFileName = FileName;
    Logfile.EventCallback = (PEVENT_CALLBACK)BdeSvcProcessWinREEvent;
    HandleArray[0] = OpenTraceW(&Logfile);
    if ( HandleArray[0] == -1 )
      goto LABEL_11;
    ProcessTrace(HandleArray, 1u, 0, 0);
  }
  if ( HandleArray[0] != -1 )
    CloseTrace(HandleArray[0]);
LABEL_11:
  if ( v0 )
    DeleteFileW(FileName);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x18000d904  mov     [rsp-8+arg_0], rbx
0x18000d909  mov     [rsp-8+arg_8], rdi
0x18000d90e  push    rbp
0x18000d90f  lea     rbp, [rsp-530h]
0x18000d917  sub     rsp, 630h
0x18000d91e  mov     rax, cs:__security_cookie
0x18000d925  xor     rax, rsp
0x18000d928  mov     [rbp+530h+var_10], rax
0x18000d92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d936  lea     rdi, WPP_GLOBAL_Control
0x18000d93d  cmp     rcx, rdi
0x18000d940  jz      short loc_18000D95D
0x18000d942  test    byte ptr [rcx+1Ch], 20h
0x18000d946  jz      short loc_18000D95D
0x18000d948  mov     rcx, [rcx+10h]
0x18000d94c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18000d953  mov     edx, 71h ; 'q'
0x18000d958  call    WPP_SF_
0x18000d95d  mov     ebx, 208h
0x18000d962  lea     rcx, [rbp+530h+var_220]; void *
0x18000d969  mov     r8d, ebx; Size
0x18000d96c  xor     edx, edx; Val
0x18000d96e  call    memset_0
0x18000d973  mov     r8d, ebx; Size
0x18000d976  lea     rcx, [rbp+530h+FileName]; void *
0x18000d97d  xor     edx, edx; Val
0x18000d97f  call    memset_0
0x18000d984  xor     edx, edx; Val
0x18000d986  lea     r8d, [rbx-48h]; Size
0x18000d98a  lea     rcx, [rsp+630h+Logfile]; void *
0x18000d98f  call    memset_0
0x18000d994  lea     rcx, [rbp+530h+var_220]
0x18000d99b  mov     [rbp+530h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x18000d9a6  xor     ebx, ebx
0x18000d9a8  call    NgscbGetOSVolume
0x18000d9ad  test    eax, eax
0x18000d9af  js      loc_18000DA72
0x18000d9b5  lea     rax, aBitlockerwinre_0; "BitLockerWinRELog.etl"
0x18000d9bc  mov     edx, 104h; unsigned __int64
0x18000d9c1  lea     r9, [rbp+530h+var_220]
0x18000d9c8  mov     [rsp+630h+var_610], rax
0x18000d9cd  lea     r8, aSS; "%s\\%s"
0x18000d9d4  lea     rcx, [rbp+530h+FileName]; unsigned __int16 *
0x18000d9db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d9e0  test    eax, eax
0x18000d9e2  js      loc_18000DA72
0x18000d9e8  lea     rcx, [rbp+530h+FileName]; lpFileName
0x18000d9ef  call    cs:__imp_GetFileAttributesW
0x18000d9f6  nop     dword ptr [rax+rax+00h]
0x18000d9fb  cmp     eax, 0FFFFFFFFh
0x18000d9fe  jz      short loc_18000DA72
0x18000da00  xor     edx, edx; Val
0x18000da02  lea     rcx, [rsp+630h+Logfile]; void *
0x18000da07  mov     r8d, 1C0h; Size
0x18000da0d  mov     ebx, 1
0x18000da12  call    memset_0
0x18000da17  lea     rax, [rbp+530h+FileName]
0x18000da1e  mov     dword ptr [rsp+630h+Logfile.1Ch], 10000000h
0x18000da26  mov     [rsp+630h+Logfile.LogFileName], rax
0x18000da2b  lea     rcx, [rsp+630h+Logfile]; Logfile
0x18000da30  lea     rax, ?BdeSvcProcessWinREEvent@@YAXPEAU_EVENT_RECORD@@@Z; BdeSvcProcessWinREEvent(_EVENT_RECORD *)
0x18000da37  mov     qword ptr [rbp+530h+Logfile.1A8h], rax
0x18000da3e  call    cs:__imp_OpenTraceW
0x18000da45  nop     dword ptr [rax+rax+00h]
0x18000da4a  mov     [rbp+530h+HandleArray], rax
0x18000da51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000da55  jz      short loc_18000DA8E
0x18000da57  xor     r9d, r9d; EndTime
0x18000da5a  lea     rcx, [rbp+530h+HandleArray]; HandleArray
0x18000da61  xor     r8d, r8d; StartTime
0x18000da64  mov     edx, ebx; HandleCount
0x18000da66  call    cs:__imp_ProcessTrace
0x18000da6d  nop     dword ptr [rax+rax+00h]
0x18000da72  mov     rax, [rbp+530h+HandleArray]
0x18000da79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000da7d  jz      short loc_18000DA8E
0x18000da7f  mov     rcx, rax; TraceHandle
0x18000da82  call    cs:__imp_CloseTrace
0x18000da89  nop     dword ptr [rax+rax+00h]
0x18000da8e  test    ebx, ebx
0x18000da90  jz      short loc_18000DAA5
0x18000da92  lea     rcx, [rbp+530h+FileName]; lpFileName
0x18000da99  call    cs:__imp_DeleteFileW
0x18000daa0  nop     dword ptr [rax+rax+00h]
0x18000daa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daac  cmp     rcx, rdi
0x18000daaf  jz      short loc_18000DACC
0x18000dab1  test    byte ptr [rcx+1Ch], 20h
0x18000dab5  jz      short loc_18000DACC
0x18000dab7  mov     rcx, [rcx+10h]
0x18000dabb  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18000dac2  mov     edx, 72h ; 'r'
0x18000dac7  call    WPP_SF_
0x18000dacc  mov     rcx, [rbp+530h+var_10]
0x18000dad3  xor     rcx, rsp; StackCookie
0x18000dad6  call    __security_check_cookie
0x18000dadb  lea     r11, [rsp+630h+var_s0]
0x18000dae3  mov     rbx, [r11+10h]
0x18000dae7  mov     rdi, [r11+18h]
0x18000daeb  mov     rsp, r11
0x18000daee  pop     rbp
0x18000daef  retn
```

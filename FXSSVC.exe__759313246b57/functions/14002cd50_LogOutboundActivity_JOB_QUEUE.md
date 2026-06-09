# LogOutboundActivity(_JOB_QUEUE *)

- ea: `0x14002cd50`
- end: `0x14002cf9b`
- name: `?LogOutboundActivity@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140016690`
- `0x140032e04`
- `0x14003354c`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x14002a8b8`
- `0x14002c820`
- `0x14002c8f8`
- `0x14002cd50`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002cef6`
- `KERNEL32!GetLastError` at `0x14002cef6`
- `KERNEL32!SetLastError` at `0x14002cf59`
- `KERNEL32!SetLastError` at `0x14002cf59`
- `KERNEL32!WriteFile` at `0x14002cee6`
- `KERNEL32!WriteFile` at `0x14002cee6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogOutboundActivity(struct _JOB_QUEUE *a1)
{
  DWORD v2; // ebx
  int OutboundCommandText; // eax
  DWORD v5; // eax
  HANDLE v6; // rcx
  LPCVOID *v7; // rdx
  DWORD LastError; // eax
  __int64 v9; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-48h] BYREF
  int v11; // [rsp+34h] [rbp-44h]
  exception *v12; // [rsp+38h] [rbp-40h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-28h]
  unsigned __int64 v15; // [rsp+58h] [rbp-20h]

  v2 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v15 = 7;
  v14 = 0;
  LOWORD(lpBuffer[0]) = 0;
  NumberOfBytesWritten = 0;
  if ( !*(&g_ActivityLoggingConfig + 2) )
    return 1;
  try
  {
    OutboundCommandText = GetOutboundCommandText(a1, lpBuffer);
  }
  catch ( exception *v12 )
  {
    v11 = 14;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v12 + 8LL))(v12);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v9);
    }
    v2 = v11;
    goto LABEL_37;
  }
  if ( OutboundCommandText )
  {
    if ( !(unsigned int)LogFileLimitReached(1) )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v5 = LogFileLimitReachAction((LPCWSTR)1);
    v2 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v5);
      }
      if ( !*(&g_ActivityLoggingConfig + 2) )
        goto LABEL_37;
      v6 = g_hOutboxActivityLogFile;
      if ( g_hOutboxActivityLogFile == (HANDLE)-1LL )
        goto LABEL_37;
      v2 = 0;
    }
    else
    {
LABEL_26:
      v6 = g_hOutboxActivityLogFile;
    }
    v7 = lpBuffer;
    if ( v15 >= 8 )
      v7 = (LPCVOID *)lpBuffer[0];
    if ( !WriteFile(v6, v7, 2 * v14, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      }
    }
    if ( !v2 )
    {
      if ( v15 >= 8 )
        operator delete((void *)lpBuffer[0]);
      return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v2 = 14;
  }
LABEL_37:
  SetLastError(v2);
  if ( v15 >= 8 )
    operator delete((void *)lpBuffer[0]);
  return 0;
}

```

## disassembly

```asm
0x14002cd50  mov     [rsp+arg_8], rbx
0x14002cd55  mov     [rsp+arg_10], rsi
0x14002cd5a  push    r15
0x14002cd5c  sub     rsp, 70h
0x14002cd60  mov     rax, cs:__security_cookie
0x14002cd67  xor     rax, rsp
0x14002cd6a  mov     [rsp+78h+var_18], rax
0x14002cd6f  mov     rsi, rcx
0x14002cd72  xor     ebx, ebx
0x14002cd74  lea     r15, WPP_GLOBAL_Control
0x14002cd7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cd82  cmp     rcx, r15
0x14002cd85  jz      short loc_14002CDA6
0x14002cd87  test    byte ptr [rcx+1Ch], 4
0x14002cd8b  jz      short loc_14002CDA6
0x14002cd8d  cmp     byte ptr [rcx+19h], 5
0x14002cd91  jb      short loc_14002CDA6
0x14002cd93  lea     edx, [rbx+10h]
0x14002cd96  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cd9d  mov     rcx, [rcx+10h]
0x14002cda1  call    WPP_SF_
0x14002cda6  mov     [rsp+78h+var_20], 7
0x14002cdaf  mov     [rsp+78h+var_28], rbx
0x14002cdb4  xor     eax, eax
0x14002cdb6  mov     word ptr [rsp+78h+lpBuffer], ax
0x14002cdbb  mov     [rsp+78h+NumberOfBytesWritten], eax
0x14002cdbf  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, eax; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002cdc5  jnz     short loc_14002CDD1
0x14002cdc7  mov     eax, 1
0x14002cdcc  jmp     loc_14002CF7A
0x14002cdd1  lea     rdx, [rsp+78h+lpBuffer]
0x14002cdd6  mov     rcx, rsi
0x14002cdd9  call    GetOutboundCommandText
0x14002cdde  test    eax, eax
0x14002cde0  jnz     short loc_14002CE17
0x14002cde2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cde9  cmp     rcx, r15
0x14002cdec  jz      short loc_14002CE0D
0x14002cdee  test    byte ptr [rcx+1Ch], 4
0x14002cdf2  jz      short loc_14002CE0D
0x14002cdf4  cmp     byte ptr [rcx+19h], 2
0x14002cdf8  jb      short loc_14002CE0D
0x14002cdfa  lea     edx, [rax+11h]
0x14002cdfd  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ce04  mov     rcx, [rcx+10h]
0x14002ce08  call    WPP_SF_
0x14002ce0d  mov     ebx, 0Eh
0x14002ce12  jmp     loc_14002CF57
0x14002ce17  mov     ecx, 1
0x14002ce1c  call    LogFileLimitReached
0x14002ce21  test    eax, eax
0x14002ce23  jz      loc_14002CEB8
0x14002ce29  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ce30  cmp     rcx, r15
0x14002ce33  jz      short loc_14002CE56
0x14002ce35  test    byte ptr [rcx+1Ch], 4
0x14002ce39  jz      short loc_14002CE56
0x14002ce3b  cmp     byte ptr [rcx+19h], 5
0x14002ce3f  jb      short loc_14002CE56
0x14002ce41  mov     edx, 13h
0x14002ce46  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ce4d  mov     rcx, [rcx+10h]
0x14002ce51  call    WPP_SF_
0x14002ce56  mov     ecx, 1; pszLogFileName
0x14002ce5b  call    LogFileLimitReachAction
0x14002ce60  mov     ebx, eax
0x14002ce62  test    eax, eax
0x14002ce64  jz      short loc_14002CEB8
0x14002ce66  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ce6d  cmp     rcx, r15
0x14002ce70  jz      short loc_14002CE96
0x14002ce72  test    byte ptr [rcx+1Ch], 4
0x14002ce76  jz      short loc_14002CE96
0x14002ce78  cmp     byte ptr [rcx+19h], 2
0x14002ce7c  jb      short loc_14002CE96
0x14002ce7e  mov     edx, 14h
0x14002ce83  mov     r9d, eax
0x14002ce86  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ce8d  mov     rcx, [rcx+10h]
0x14002ce91  call    WPP_SF_d
0x14002ce96  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, 0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002ce9d  jz      loc_14002CF57
0x14002cea3  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002ceaa  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002ceae  jz      loc_14002CF57
0x14002ceb4  xor     ebx, ebx
0x14002ceb6  jmp     short loc_14002CEBF
0x14002ceb8  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; hFile
0x14002cebf  mov     r8d, dword ptr [rsp+78h+var_28]
0x14002cec4  lea     rdx, [rsp+78h+lpBuffer]
0x14002cec9  cmp     [rsp+78h+var_20], 8
0x14002cecf  cmovnb  rdx, [rsp+78h+lpBuffer]; lpBuffer
0x14002ced5  add     r8d, r8d; nNumberOfBytesToWrite
0x14002ced8  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14002cee1  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002cee6  call    cs:__imp_WriteFile
0x14002ceed  nop     dword ptr [rax+rax+00h]
0x14002cef2  test    eax, eax
0x14002cef4  jnz     short loc_14002CF34
0x14002cef6  call    cs:__imp_GetLastError
0x14002cefd  nop     dword ptr [rax+rax+00h]
0x14002cf02  mov     ebx, eax
0x14002cf04  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf0b  cmp     rcx, r15
0x14002cf0e  jz      short loc_14002CF34
0x14002cf10  test    byte ptr [rcx+1Ch], 4
0x14002cf14  jz      short loc_14002CF34
0x14002cf16  cmp     byte ptr [rcx+19h], 2
0x14002cf1a  jb      short loc_14002CF34
0x14002cf1c  mov     edx, 15h
0x14002cf21  mov     r9d, eax
0x14002cf24  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cf2b  mov     rcx, [rcx+10h]
0x14002cf2f  call    WPP_SF_d
0x14002cf34  test    ebx, ebx
0x14002cf36  jnz     short loc_14002CF57
0x14002cf38  cmp     [rsp+78h+var_20], 8
0x14002cf3e  jb      loc_14002CDC7
0x14002cf44  mov     rcx, [rsp+78h+lpBuffer]; Block
0x14002cf49  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cf4e  jmp     loc_14002CDC7
0x14002cf53  mov     ebx, [rsp+78h+var_44]
0x14002cf57  mov     ecx, ebx; dwErrCode
0x14002cf59  call    cs:__imp_SetLastError
0x14002cf60  nop     dword ptr [rax+rax+00h]
0x14002cf65  nop
0x14002cf66  cmp     [rsp+78h+var_20], 8
0x14002cf6c  jb      short loc_14002CF78
0x14002cf6e  mov     rcx, [rsp+78h+lpBuffer]; Block
0x14002cf73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cf78  xor     eax, eax
0x14002cf7a  mov     rcx, [rsp+78h+var_18]
0x14002cf7f  xor     rcx, rsp; StackCookie
0x14002cf82  call    __security_check_cookie
0x14002cf87  lea     r11, [rsp+78h+var_8]
0x14002cf8c  mov     rbx, [r11+18h]
0x14002cf90  mov     rsi, [r11+20h]
0x14002cf94  mov     rsp, r11
0x14002cf97  pop     r15
0x14002cf99  retn
```

# LogInboundActivity(_JOB_QUEUE *,_FSPI_JOB_STATUS const *)

- ea: `0x14002cb00`
- end: `0x14002cd48`
- name: `?LogInboundActivity@@YAHPEAU_JOB_QUEUE@@PEBU_FSPI_JOB_STATUS@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, const struct _FSPI_JOB_STATUS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400411a0`

## callees

- `0x140001bac`
- `0x140004c78`
- `0x140004ca8`
- `0x140029f2c`
- `0x14002c820`
- `0x14002c8f8`
- `0x14002cb00`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002cca4`
- `KERNEL32!GetLastError` at `0x14002cca4`
- `KERNEL32!SetLastError` at `0x14002cd07`
- `KERNEL32!SetLastError` at `0x14002cd07`
- `KERNEL32!WriteFile` at `0x14002cc94`
- `KERNEL32!WriteFile` at `0x14002cc94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogInboundActivity(struct _JOB_QUEUE *a1, const struct _FSPI_JOB_STATUS *a2)
{
  DWORD v4; // ebx
  int InboundCommandText; // eax
  DWORD v7; // eax
  HANDLE v8; // rcx
  LPCVOID *v9; // rdx
  DWORD LastError; // eax
  __int64 v11; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-58h] BYREF
  int v13; // [rsp+34h] [rbp-54h]
  exception *v14; // [rsp+38h] [rbp-50h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v16; // [rsp+50h] [rbp-38h]
  unsigned __int64 v17; // [rsp+58h] [rbp-30h]

  v4 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v17 = 7;
  v16 = 0;
  LOWORD(lpBuffer[0]) = 0;
  NumberOfBytesWritten = 0;
  if ( !*(&g_ActivityLoggingConfig + 1) )
    return 1;
  try
  {
    InboundCommandText = GetInboundCommandText(a1, a2, lpBuffer);
  }
  catch ( exception *v14 )
  {
    v13 = 14;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v14 + 8LL))(v14);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v11);
    }
    v4 = v13;
    goto LABEL_37;
  }
  if ( InboundCommandText )
  {
    if ( !(unsigned int)LogFileLimitReached(0) )
      goto LABEL_26;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v7 = LogFileLimitReachAction(0);
    v4 = v7;
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v7);
      }
      if ( !*(&g_ActivityLoggingConfig + 1) )
        goto LABEL_37;
      v8 = g_hInboxActivityLogFile;
      if ( g_hInboxActivityLogFile == (HANDLE)-1LL )
        goto LABEL_37;
      v4 = 0;
    }
    else
    {
LABEL_26:
      v8 = g_hInboxActivityLogFile;
    }
    v9 = lpBuffer;
    if ( v17 >= 8 )
      v9 = (LPCVOID *)lpBuffer[0];
    if ( !WriteFile(v8, v9, 2 * v16, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      }
    }
    if ( !v4 )
    {
      if ( v17 >= 8 )
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
    }
    v4 = 14;
  }
LABEL_37:
  SetLastError(v4);
  if ( v17 >= 8 )
    operator delete((void *)lpBuffer[0]);
  return 0;
}

```

## disassembly

```asm
0x14002cb00  mov     [rsp+arg_10], rbx
0x14002cb05  push    rsi
0x14002cb06  push    r12
0x14002cb08  push    r14
0x14002cb0a  sub     rsp, 70h
0x14002cb0e  mov     rax, cs:__security_cookie
0x14002cb15  xor     rax, rsp
0x14002cb18  mov     [rsp+88h+var_28], rax
0x14002cb1d  mov     r14, rdx
0x14002cb20  mov     rsi, rcx
0x14002cb23  xor     ebx, ebx
0x14002cb25  lea     r12, WPP_GLOBAL_Control
0x14002cb2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cb33  cmp     rcx, r12
0x14002cb36  jz      short loc_14002CB57
0x14002cb38  test    byte ptr [rcx+1Ch], 4
0x14002cb3c  jz      short loc_14002CB57
0x14002cb3e  cmp     byte ptr [rcx+19h], 5
0x14002cb42  jb      short loc_14002CB57
0x14002cb44  lea     edx, [rbx+0Ah]
0x14002cb47  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cb4e  mov     rcx, [rcx+10h]
0x14002cb52  call    WPP_SF_
0x14002cb57  mov     [rsp+88h+var_30], 7
0x14002cb60  mov     [rsp+88h+var_38], rbx
0x14002cb65  xor     eax, eax
0x14002cb67  mov     word ptr [rsp+88h+lpBuffer], ax
0x14002cb6c  mov     [rsp+88h+NumberOfBytesWritten], eax
0x14002cb70  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, eax; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002cb76  jnz     short loc_14002CB82
0x14002cb78  mov     eax, 1
0x14002cb7d  jmp     loc_14002CD28
0x14002cb82  lea     r8, [rsp+88h+lpBuffer]
0x14002cb87  mov     rdx, r14
0x14002cb8a  mov     rcx, rsi
0x14002cb8d  call    GetInboundCommandText
0x14002cb92  test    eax, eax
0x14002cb94  jnz     short loc_14002CBCB
0x14002cb96  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cb9d  cmp     rcx, r12
0x14002cba0  jz      short loc_14002CBC1
0x14002cba2  test    byte ptr [rcx+1Ch], 4
0x14002cba6  jz      short loc_14002CBC1
0x14002cba8  cmp     byte ptr [rcx+19h], 2
0x14002cbac  jb      short loc_14002CBC1
0x14002cbae  lea     edx, [rax+0Bh]
0x14002cbb1  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cbb8  mov     rcx, [rcx+10h]
0x14002cbbc  call    WPP_SF_
0x14002cbc1  mov     ebx, 0Eh
0x14002cbc6  jmp     loc_14002CD05
0x14002cbcb  xor     ecx, ecx
0x14002cbcd  call    LogFileLimitReached
0x14002cbd2  test    eax, eax
0x14002cbd4  jz      loc_14002CC66
0x14002cbda  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cbe1  cmp     rcx, r12
0x14002cbe4  jz      short loc_14002CC07
0x14002cbe6  test    byte ptr [rcx+1Ch], 4
0x14002cbea  jz      short loc_14002CC07
0x14002cbec  cmp     byte ptr [rcx+19h], 5
0x14002cbf0  jb      short loc_14002CC07
0x14002cbf2  mov     edx, 0Dh
0x14002cbf7  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cbfe  mov     rcx, [rcx+10h]
0x14002cc02  call    WPP_SF_
0x14002cc07  xor     ecx, ecx; pszLogFileName
0x14002cc09  call    LogFileLimitReachAction
0x14002cc0e  mov     ebx, eax
0x14002cc10  test    eax, eax
0x14002cc12  jz      short loc_14002CC66
0x14002cc14  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cc1b  cmp     rcx, r12
0x14002cc1e  jz      short loc_14002CC44
0x14002cc20  test    byte ptr [rcx+1Ch], 4
0x14002cc24  jz      short loc_14002CC44
0x14002cc26  cmp     byte ptr [rcx+19h], 2
0x14002cc2a  jb      short loc_14002CC44
0x14002cc2c  mov     edx, 0Eh
0x14002cc31  mov     r9d, eax
0x14002cc34  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002cc3b  mov     rcx, [rcx+10h]
0x14002cc3f  call    WPP_SF_d
0x14002cc44  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, 0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002cc4b  jz      loc_14002CD05
0x14002cc51  mov     rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; void * g_hInboxActivityLogFile
0x14002cc58  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002cc5c  jz      loc_14002CD05
0x14002cc62  xor     ebx, ebx
0x14002cc64  jmp     short loc_14002CC6D
0x14002cc66  mov     rcx, cs:?g_hInboxActivityLogFile@@3PEAXEA; hFile
0x14002cc6d  mov     r8d, dword ptr [rsp+88h+var_38]
0x14002cc72  lea     rdx, [rsp+88h+lpBuffer]
0x14002cc77  cmp     [rsp+88h+var_30], 8
0x14002cc7d  cmovnb  rdx, [rsp+88h+lpBuffer]; lpBuffer
0x14002cc83  add     r8d, r8d; nNumberOfBytesToWrite
0x14002cc86  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14002cc8f  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002cc94  call    cs:__imp_WriteFile
0x14002cc9b  nop     dword ptr [rax+rax+00h]
0x14002cca0  test    eax, eax
0x14002cca2  jnz     short loc_14002CCE2
0x14002cca4  call    cs:__imp_GetLastError
0x14002ccab  nop     dword ptr [rax+rax+00h]
0x14002ccb0  mov     ebx, eax
0x14002ccb2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ccb9  cmp     rcx, r12
0x14002ccbc  jz      short loc_14002CCE2
0x14002ccbe  test    byte ptr [rcx+1Ch], 4
0x14002ccc2  jz      short loc_14002CCE2
0x14002ccc4  cmp     byte ptr [rcx+19h], 2
0x14002ccc8  jb      short loc_14002CCE2
0x14002ccca  mov     edx, 0Fh
0x14002cccf  mov     r9d, eax
0x14002ccd2  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ccd9  mov     rcx, [rcx+10h]
0x14002ccdd  call    WPP_SF_d
0x14002cce2  test    ebx, ebx
0x14002cce4  jnz     short loc_14002CD05
0x14002cce6  cmp     [rsp+88h+var_30], 8
0x14002ccec  jb      loc_14002CB78
0x14002ccf2  mov     rcx, [rsp+88h+lpBuffer]; Block
0x14002ccf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ccfc  jmp     loc_14002CB78
0x14002cd01  mov     ebx, [rsp+88h+var_54]
0x14002cd05  mov     ecx, ebx; dwErrCode
0x14002cd07  call    cs:__imp_SetLastError
0x14002cd0e  nop     dword ptr [rax+rax+00h]
0x14002cd13  nop
0x14002cd14  cmp     [rsp+88h+var_30], 8
0x14002cd1a  jb      short loc_14002CD26
0x14002cd1c  mov     rcx, [rsp+88h+lpBuffer]; Block
0x14002cd21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cd26  xor     eax, eax
0x14002cd28  mov     rcx, [rsp+88h+var_28]
0x14002cd2d  xor     rcx, rsp; StackCookie
0x14002cd30  call    __security_check_cookie
0x14002cd35  mov     rbx, [rsp+88h+arg_10]
0x14002cd3d  add     rsp, 70h
0x14002cd41  pop     r14
0x14002cd43  pop     r12
0x14002cd45  pop     rsi
0x14002cd46  retn
```

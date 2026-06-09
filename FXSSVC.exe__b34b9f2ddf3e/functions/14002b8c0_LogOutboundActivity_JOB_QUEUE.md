# LogOutboundActivity(_JOB_QUEUE *)

- ea: `0x14002b8c0`
- end: `0x14002baf8`
- name: `?LogOutboundActivity@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140015d90`
- `0x1400314a8`
- `0x140031b6c`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x1400294dc`
- `0x14002b3d0`
- `0x14002b4a8`
- `0x14002b8c0`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002ba60`
- `KERNEL32!GetLastError` at `0x14002ba60`
- `KERNEL32!SetLastError` at `0x14002babd`
- `KERNEL32!SetLastError` at `0x14002babd`
- `KERNEL32!WriteFile` at `0x14002ba56`
- `KERNEL32!WriteFile` at `0x14002ba56`

## pseudocode

```c
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
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    OutboundCommandText = GetOutboundCommandText(a1, lpBuffer);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v12) )
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
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_14002BAB7);
      goto LABEL_37;
    }
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
0x14002b8c0  mov     [rsp+arg_8], rbx
0x14002b8c5  mov     [rsp+arg_10], rsi
0x14002b8ca  push    r15
0x14002b8cc  sub     rsp, 70h
0x14002b8d0  mov     rax, cs:__security_cookie
0x14002b8d7  xor     rax, rsp
0x14002b8da  mov     [rsp+78h+var_18], rax
0x14002b8df  mov     rsi, rcx
0x14002b8e2  xor     ebx, ebx
0x14002b8e4  lea     r15, WPP_GLOBAL_Control
0x14002b8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8f2  cmp     rcx, r15
0x14002b8f5  jz      short loc_14002B916
0x14002b8f7  test    byte ptr [rcx+1Ch], 4
0x14002b8fb  jz      short loc_14002B916
0x14002b8fd  cmp     byte ptr [rcx+19h], 5
0x14002b901  jb      short loc_14002B916
0x14002b903  lea     edx, [rbx+10h]
0x14002b906  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b90d  mov     rcx, [rcx+10h]
0x14002b911  call    WPP_SF_
0x14002b916  mov     [rsp+78h+var_20], 7
0x14002b91f  mov     [rsp+78h+var_28], rbx
0x14002b924  xor     eax, eax
0x14002b926  mov     word ptr [rsp+78h+lpBuffer], ax
0x14002b92b  mov     [rsp+78h+NumberOfBytesWritten], eax
0x14002b92f  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, eax; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002b935  jnz     short loc_14002B941
0x14002b937  mov     eax, 1
0x14002b93c  jmp     loc_14002BAD8
0x14002b941  lea     rdx, [rsp+78h+lpBuffer]
0x14002b946  mov     rcx, rsi
0x14002b949  call    GetOutboundCommandText
0x14002b94e  test    eax, eax
0x14002b950  jnz     short loc_14002B987
0x14002b952  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b959  cmp     rcx, r15
0x14002b95c  jz      short loc_14002B97D
0x14002b95e  test    byte ptr [rcx+1Ch], 4
0x14002b962  jz      short loc_14002B97D
0x14002b964  cmp     byte ptr [rcx+19h], 2
0x14002b968  jb      short loc_14002B97D
0x14002b96a  lea     edx, [rax+11h]
0x14002b96d  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b974  mov     rcx, [rcx+10h]
0x14002b978  call    WPP_SF_
0x14002b97d  mov     ebx, 0Eh
0x14002b982  jmp     loc_14002BABB
0x14002b987  mov     ecx, 1
0x14002b98c  call    LogFileLimitReached
0x14002b991  test    eax, eax
0x14002b993  jz      loc_14002BA28
0x14002b999  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9a0  cmp     rcx, r15
0x14002b9a3  jz      short loc_14002B9C6
0x14002b9a5  test    byte ptr [rcx+1Ch], 4
0x14002b9a9  jz      short loc_14002B9C6
0x14002b9ab  cmp     byte ptr [rcx+19h], 5
0x14002b9af  jb      short loc_14002B9C6
0x14002b9b1  mov     edx, 13h
0x14002b9b6  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b9bd  mov     rcx, [rcx+10h]
0x14002b9c1  call    WPP_SF_
0x14002b9c6  mov     ecx, 1; pszLogFileName
0x14002b9cb  call    LogFileLimitReachAction
0x14002b9d0  mov     ebx, eax
0x14002b9d2  test    eax, eax
0x14002b9d4  jz      short loc_14002BA28
0x14002b9d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b9dd  cmp     rcx, r15
0x14002b9e0  jz      short loc_14002BA06
0x14002b9e2  test    byte ptr [rcx+1Ch], 4
0x14002b9e6  jz      short loc_14002BA06
0x14002b9e8  cmp     byte ptr [rcx+19h], 2
0x14002b9ec  jb      short loc_14002BA06
0x14002b9ee  mov     edx, 14h
0x14002b9f3  mov     r9d, eax
0x14002b9f6  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002b9fd  mov     rcx, [rcx+10h]
0x14002ba01  call    WPP_SF_d
0x14002ba06  cmp     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, 0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002ba0d  jz      loc_14002BABB
0x14002ba13  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; void * g_hOutboxActivityLogFile
0x14002ba1a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002ba1e  jz      loc_14002BABB
0x14002ba24  xor     ebx, ebx
0x14002ba26  jmp     short loc_14002BA2F
0x14002ba28  mov     rcx, cs:?g_hOutboxActivityLogFile@@3PEAXEA; hFile
0x14002ba2f  mov     r8d, dword ptr [rsp+78h+var_28]
0x14002ba34  lea     rdx, [rsp+78h+lpBuffer]
0x14002ba39  cmp     [rsp+78h+var_20], 8
0x14002ba3f  cmovnb  rdx, [rsp+78h+lpBuffer]; lpBuffer
0x14002ba45  add     r8d, r8d; nNumberOfBytesToWrite
0x14002ba48  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14002ba51  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002ba56  call    cs:__imp_WriteFile
0x14002ba5c  test    eax, eax
0x14002ba5e  jnz     short loc_14002BA98
0x14002ba60  call    cs:__imp_GetLastError
0x14002ba66  mov     ebx, eax
0x14002ba68  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ba6f  cmp     rcx, r15
0x14002ba72  jz      short loc_14002BA98
0x14002ba74  test    byte ptr [rcx+1Ch], 4
0x14002ba78  jz      short loc_14002BA98
0x14002ba7a  cmp     byte ptr [rcx+19h], 2
0x14002ba7e  jb      short loc_14002BA98
0x14002ba80  mov     edx, 15h
0x14002ba85  mov     r9d, eax
0x14002ba88  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ba8f  mov     rcx, [rcx+10h]
0x14002ba93  call    WPP_SF_d
0x14002ba98  test    ebx, ebx
0x14002ba9a  jnz     short loc_14002BABB
0x14002ba9c  cmp     [rsp+78h+var_20], 8
0x14002baa2  jb      loc_14002B937
0x14002baa8  mov     rcx, [rsp+78h+lpBuffer]; Block
0x14002baad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002bab2  jmp     loc_14002B937
0x14002bab7  mov     ebx, [rsp+78h+var_44]
0x14002babb  mov     ecx, ebx; dwErrCode
0x14002babd  call    cs:__imp_SetLastError
0x14002bac3  nop
0x14002bac4  cmp     [rsp+78h+var_20], 8
0x14002baca  jb      short loc_14002BAD6
0x14002bacc  mov     rcx, [rsp+78h+lpBuffer]; Block
0x14002bad1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002bad6  xor     eax, eax
0x14002bad8  mov     rcx, [rsp+78h+var_18]
0x14002badd  xor     rcx, rsp; StackCookie
0x14002bae0  call    __security_check_cookie
0x14002bae5  lea     r11, [rsp+78h+var_8]
0x14002baea  mov     rbx, [r11+18h]
0x14002baee  mov     rsi, [r11+20h]
0x14002baf2  mov     rsp, r11
0x14002baf5  pop     r15
0x14002baf7  retn
```

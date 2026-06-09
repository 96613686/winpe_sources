# CreateLogFile

- ea: `0x140027f80`
- end: `0x14002841e`
- name: `CreateLogFile`
- size: `1182`
- prototype: `HANDLE __stdcall(LPCWSTR pszLogFileName, ACCESS_MASK fDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES psaLogFile, ULONG fCreateDisposition, ULONG fFlagsAndAttributes)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140027a58`
- `0x140028424`
- `0x14002bb00`

## callees

- `0x140001b8c`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140027f80`
- `0x14002ae44`
- `0x140065df8`
- `0x14006a3a4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400280b3`
- `KERNEL32!GetLastError` at `0x1400280f9`
- `KERNEL32!GetLastError` at `0x140028166`
- `KERNEL32!GetLastError` at `0x14002820b`
- `KERNEL32!GetLastError` at `0x1400282f2`
- `KERNEL32!GetLastError` at `0x1400283f4`
- `KERNEL32!GetLastError` at `0x1400280b3`
- `KERNEL32!GetLastError` at `0x1400280f9`
- `KERNEL32!GetLastError` at `0x140028166`
- `KERNEL32!GetLastError` at `0x14002820b`
- `KERNEL32!GetLastError` at `0x1400282f2`
- `KERNEL32!GetLastError` at `0x1400283f4`
- `KERNEL32!CloseHandle` at `0x14002833b`
- `KERNEL32!CloseHandle` at `0x1400283c2`
- `KERNEL32!CloseHandle` at `0x14002833b`
- `KERNEL32!CloseHandle` at `0x1400283c2`
- `KERNEL32!WriteFile` at `0x14002815c`
- `KERNEL32!WriteFile` at `0x140028201`
- `KERNEL32!WriteFile` at `0x14002815c`
- `KERNEL32!WriteFile` at `0x140028201`
- `KERNEL32!GetFileSizeEx` at `0x1400280ef`
- `KERNEL32!GetFileSizeEx` at `0x1400280ef`
- `KERNEL32!SetFilePointer` at `0x1400282e7`
- `KERNEL32!SetFilePointer` at `0x1400282e7`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=1
HANDLE __stdcall CreateLogFile(
        LPCWSTR pszLogFileName,
        ACCESS_MASK fDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES psaLogFile,
        ULONG fCreateDisposition,
        ULONG fFlagsAndAttributes)
{
  HANDLE *v6; // r15
  __int64 v7; // rbx
  int v8; // r12d
  const wchar_t *v9; // rax
  int v10; // eax
  __int64 v11; // r9
  DWORD v12; // ebx
  __int64 v13; // rsi
  void *File; // rax
  DWORD LastError; // eax
  CMapDeviceId *v16; // rcx
  __int64 v17; // rdx
  wchar_t *v19; // rcx
  LPCVOID *v20; // rdx
  BOOL v21; // eax
  DWORD v22; // eax
  HANDLE result; // rax
  DWORD v24; // eax
  __int64 v25; // rax
  __int16 Buffer[2]; // [rsp+40h] [rbp-298h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-294h] BYREF
  int v28; // [rsp+48h] [rbp-290h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-288h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-280h]
  HANDLE *v31; // [rsp+60h] [rbp-278h]
  exception *v32; // [rsp+68h] [rbp-270h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+70h] [rbp-268h] BYREF
  __int64 v34; // [rsp+80h] [rbp-258h]
  unsigned __int64 v35; // [rsp+88h] [rbp-250h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-248h] BYREF
  int v37; // [rsp+2E0h] [rbp+8h]

  v37 = (int)pszLogFileName;
  v6 = *(HANDLE **)&dwShareMode;
  v7 = *(_QWORD *)&fDesiredAccess;
  v8 = (int)pszLogFileName;
  v31 = *(HANDLE **)&dwShareMode;
  FileSize.QuadPart = 0;
  NumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  v9 = L"InboxLOG.txt";
  if ( v8 )
    v9 = L"OutboxLOG.txt";
  v10 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v7, v9);
  v12 = v10;
  if ( v10 < 0 )
  {
    v13 = -1;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        (unsigned int)v10);
    }
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v12;
    goto LABEL_55;
  }
  File = (void *)InternalSafeCreateFile(FileName, 0x40000000u, 1u, v11, 4u, 128);
  v13 = (__int64)File;
  hObject = File;
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    v12 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_55;
    }
    v17 = 85;
    goto LABEL_54;
  }
  if ( !GetFileSizeEx(File, &FileSize) )
  {
    LastError = GetLastError();
    v12 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_55;
    }
    v17 = 86;
    goto LABEL_54;
  }
  if ( FileSize.QuadPart )
  {
    if ( SetFilePointer((HANDLE)v13, 0, 0, 2u) == -1 )
    {
      LastError = GetLastError();
      v12 = LastError;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_55;
      }
      v17 = 90;
LABEL_54:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
      goto LABEL_55;
    }
  }
  else
  {
    Buffer[0] = -257;
    if ( !WriteFile((HANDLE)v13, Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_55;
      }
      v17 = 87;
      goto LABEL_54;
    }
    v35 = 7;
    v34 = 0;
    LOWORD(lpBuffer[0]) = 0;
    v19 = (wchar_t *)L"Inbox";
    if ( v8 )
      v19 = (wchar_t *)L"Outbox";
    try
    {
      GetTableColumnsText(v19, lpBuffer);
      v20 = lpBuffer;
      if ( v35 >= 8 )
        v20 = (LPCVOID *)lpBuffer[0];
      v21 = WriteFile((HANDLE)v13, v20, 2 * v34, &NumberOfBytesWritten, 0);
    }
    catch ( exception *v32 )
    {
      v28 = 14;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = (*(__int64 (__fastcall **)(exception *))(*(_QWORD *)v32 + 8LL))(v32);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v25);
      }
      if ( v35 >= 8 )
        operator delete((void *)lpBuffer[0]);
      v8 = v37;
      v13 = (__int64)hObject;
      v12 = v28;
      v6 = v31;
LABEL_56:
      if ( *v6 != (HANDLE)-1LL )
      {
        CloseHandle(*v6);
        *v6 = (HANDLE)-1LL;
      }
      if ( v8 )
        *(&g_ActivityLoggingConfig + 2) = 0;
      else
        *(&g_ActivityLoggingConfig + 1) = 0;
      LODWORD(lpBuffer[0]) = v12;
      WORD2(lpBuffer[0]) = 0;
      StringCchPrintfW((unsigned __int16 *)lpBuffer + 2, 0xCu, L"%ld", v12);
      FaxLog(1, 3 - (unsigned int)(v8 != 0), 2, 3221257532LL, *(_QWORD *)&::fDesiredAccess);
      if ( v13 != -1
        && !CloseHandle((HANDLE)v13)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v24);
      }
LABEL_45:
      result = (HANDLE)v12;
    }
    if ( !v21 )
    {
      v22 = GetLastError();
      v12 = v22;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v22);
      }
      if ( v35 >= 8 )
        operator delete((void *)lpBuffer[0]);
LABEL_55:
      if ( !v12 )
        goto LABEL_45;
      goto LABEL_56;
    }
    if ( v35 >= 8 )
      operator delete((void *)lpBuffer[0]);
  }
  v12 = 0;
  *v6 = (HANDLE)v13;
  goto LABEL_45;
}

```

## disassembly

```asm
0x140027f80  mov     [rsp+arg_18], rbx
0x140027f85  mov     [rsp+arg_0], ecx
0x140027f89  push    rsi
0x140027f8a  push    rdi
0x140027f8b  push    r12
0x140027f8d  push    r14
0x140027f8f  push    r15
0x140027f91  sub     rsp, 2B0h
0x140027f98  mov     rax, cs:__security_cookie
0x140027f9f  xor     rax, rsp
0x140027fa2  mov     [rsp+2D8h+var_38], rax
0x140027faa  mov     r15, r8
0x140027fad  mov     rbx, rdx
0x140027fb0  mov     r12d, ecx
0x140027fb3  mov     [rsp+2D8h+var_278], r8
0x140027fb8  xor     edi, edi
0x140027fba  mov     qword ptr [rsp+2D8h+FileSize], rdi
0x140027fbf  mov     [rsp+2D8h+NumberOfBytesWritten], edi
0x140027fc3  lea     r14, WPP_GLOBAL_Control
0x140027fca  mov     rcx, cs:WPP_GLOBAL_Control
0x140027fd1  cmp     rcx, r14
0x140027fd4  jz      short loc_140027FF5
0x140027fd6  test    byte ptr [rcx+1Ch], 4
0x140027fda  jz      short loc_140027FF5
0x140027fdc  cmp     byte ptr [rcx+19h], 5
0x140027fe0  jb      short loc_140027FF5
0x140027fe2  lea     edx, [rdi+53h]
0x140027fe5  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140027fec  mov     rcx, [rcx+10h]
0x140027ff0  call    WPP_SF_
0x140027ff5  lea     rcx, aOutboxlogTxt; "OutboxLOG.txt"
0x140027ffc  lea     rax, aInboxlogTxt; "InboxLOG.txt"
0x140028003  test    r12d, r12d
0x140028006  cmovnz  rax, rcx
0x14002800a  mov     [rsp+2D8h+lpOverlapped], rax
0x14002800f  mov     r9, rbx
0x140028012  lea     r8, aSS_0; "%s\\%s"
0x140028019  mov     edx, 104h; unsigned __int64
0x14002801e  lea     rcx, [rsp+2D8h+FileName]; unsigned __int16 *
0x140028026  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002802b  mov     ebx, eax
0x14002802d  test    eax, eax
0x14002802f  jns     short loc_14002807D
0x140028031  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140028035  mov     rcx, cs:WPP_GLOBAL_Control
0x14002803c  cmp     rcx, r14
0x14002803f  jz      short loc_140028063
0x140028041  test    byte ptr [rcx+1Ch], 4
0x140028045  jz      short loc_140028063
0x140028047  cmp     byte ptr [rcx+19h], 2
0x14002804b  jb      short loc_140028063
0x14002804d  lea     edx, [rsi+55h]
0x140028050  mov     r9d, eax
0x140028053  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002805a  mov     rcx, [rcx+10h]
0x14002805e  call    WPP_SF_d
0x140028063  mov     eax, ebx
0x140028065  and     eax, 1FFF0000h
0x14002806a  cmp     eax, 70000h
0x14002806f  jnz     loc_14002832A
0x140028075  movzx   ebx, bx
0x140028078  jmp     loc_14002832A
0x14002807d  mov     [rsp+2D8h+var_2B0], 80h; int
0x140028085  mov     dword ptr [rsp+2D8h+lpOverlapped], 4; DWORD
0x14002808d  mov     edx, 40000000h; dwDesiredAccess
0x140028092  mov     r8d, 1; dwShareMode
0x140028098  lea     rcx, [rsp+2D8h+FileName]; lpFileName
0x1400280a0  call    InternalSafeCreateFile
0x1400280a5  mov     rsi, rax
0x1400280a8  mov     [rsp+2D8h+hObject], rax
0x1400280ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400280b1  jnz     short loc_1400280E7
0x1400280b3  call    cs:__imp_GetLastError
0x1400280b9  mov     ebx, eax
0x1400280bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280c2  cmp     rcx, r14
0x1400280c5  jz      loc_14002832A
0x1400280cb  test    byte ptr [rcx+1Ch], 4
0x1400280cf  jz      loc_14002832A
0x1400280d5  cmp     byte ptr [rcx+19h], 2
0x1400280d9  jb      loc_14002832A
0x1400280df  lea     edx, [rsi+56h]
0x1400280e2  jmp     loc_140028317
0x1400280e7  lea     rdx, [rsp+2D8h+FileSize]; lpFileSize
0x1400280ec  mov     rcx, rsi; hFile
0x1400280ef  call    cs:__imp_GetFileSizeEx
0x1400280f5  test    eax, eax
0x1400280f7  jnz     short loc_14002812F
0x1400280f9  call    cs:__imp_GetLastError
0x1400280ff  mov     ebx, eax
0x140028101  mov     rcx, cs:WPP_GLOBAL_Control
0x140028108  cmp     rcx, r14
0x14002810b  jz      loc_14002832A
0x140028111  test    byte ptr [rcx+1Ch], 4
0x140028115  jz      loc_14002832A
0x14002811b  cmp     byte ptr [rcx+19h], 2
0x14002811f  jb      loc_14002832A
0x140028125  mov     edx, 56h ; 'V'
0x14002812a  jmp     loc_140028317
0x14002812f  mov     rcx, rsi; hFile
0x140028132  cmp     qword ptr [rsp+2D8h+FileSize], rdi
0x140028137  jnz     loc_1400282DC
0x14002813d  mov     eax, 0FEFFh
0x140028142  mov     [rsp+2D8h+Buffer], ax
0x140028147  mov     [rsp+2D8h+lpOverlapped], rdi; lpOverlapped
0x14002814c  lea     r9, [rsp+2D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140028151  mov     r8d, 2; nNumberOfBytesToWrite
0x140028157  lea     rdx, [rsp+2D8h+Buffer]; lpBuffer
0x14002815c  call    cs:__imp_WriteFile
0x140028162  test    eax, eax
0x140028164  jnz     short loc_14002819C
0x140028166  call    cs:__imp_GetLastError
0x14002816c  mov     ebx, eax
0x14002816e  mov     rcx, cs:WPP_GLOBAL_Control
0x140028175  cmp     rcx, r14
0x140028178  jz      loc_14002832A
0x14002817e  test    byte ptr [rcx+1Ch], 4
0x140028182  jz      loc_14002832A
0x140028188  cmp     byte ptr [rcx+19h], 2
0x14002818c  jb      loc_14002832A
0x140028192  mov     edx, 57h ; 'W'
0x140028197  jmp     loc_140028317
0x14002819c  mov     [rsp+2D8h+var_250], 7
0x1400281a8  mov     [rsp+2D8h+var_258], rdi
0x1400281b0  mov     word ptr [rsp+2D8h+lpBuffer], di
0x1400281b5  lea     rax, aOutbox; "Outbox"
0x1400281bc  lea     rcx, aInbox; "Inbox"
0x1400281c3  test    r12d, r12d
0x1400281c6  cmovnz  rcx, rax; String1
0x1400281ca  lea     rdx, [rsp+2D8h+lpBuffer]; Src
0x1400281cf  call    GetTableColumnsText
0x1400281d4  nop
0x1400281d5  mov     r8d, dword ptr [rsp+2D8h+var_258]
0x1400281dd  lea     rdx, [rsp+2D8h+lpBuffer]
0x1400281e2  cmp     [rsp+2D8h+var_250], 8
0x1400281eb  cmovnb  rdx, [rsp+2D8h+lpBuffer]; lpBuffer
0x1400281f1  add     r8d, r8d; nNumberOfBytesToWrite
0x1400281f4  mov     [rsp+2D8h+lpOverlapped], rdi; lpOverlapped
0x1400281f9  lea     r9, [rsp+2D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400281fe  mov     rcx, rsi; hFile
0x140028201  call    cs:__imp_WriteFile
0x140028207  test    eax, eax
0x140028209  jnz     short loc_140028262
0x14002820b  call    cs:__imp_GetLastError
0x140028211  mov     ebx, eax
0x140028213  mov     rcx, cs:WPP_GLOBAL_Control
0x14002821a  cmp     rcx, r14
0x14002821d  jz      short loc_140028244
0x14002821f  test    byte ptr [rcx+1Ch], 4
0x140028223  jz      short loc_140028244
0x140028225  cmp     byte ptr [rcx+19h], 2
0x140028229  jb      short loc_140028244
0x14002822b  mov     edx, 59h ; 'Y'
0x140028230  mov     r9d, eax
0x140028233  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002823a  mov     rcx, [rcx+10h]
0x14002823e  call    WPP_SF_d
0x140028243  nop
0x140028244  cmp     [rsp+2D8h+var_250], 8
0x14002824d  jb      loc_14002832A
0x140028253  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x140028258  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002825d  jmp     loc_14002832A
0x140028262  cmp     [rsp+2D8h+var_250], 8
0x14002826b  jb      short loc_140028277
0x14002826d  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x140028272  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140028277  mov     ebx, edi
0x140028279  mov     [r15], rsi
0x14002827c  mov     eax, ebx
0x14002827e  mov     rcx, [rsp+2D8h+var_38]
0x140028286  xor     rcx, rsp; StackCookie
0x140028289  call    __security_check_cookie
0x14002828e  mov     rbx, [rsp+2D8h+arg_18]
0x140028296  add     rsp, 2B0h
0x14002829d  pop     r15
0x14002829f  pop     r14
0x1400282a1  pop     r12
0x1400282a3  pop     rdi
0x1400282a4  pop     rsi
0x1400282a5  retn
0x1400282a6  cmp     [rsp+2D8h+var_250], 8
0x1400282af  jb      short loc_1400282BB
0x1400282b1  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x1400282b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400282bb  xor     edi, edi
0x1400282bd  lea     r14, WPP_GLOBAL_Control
0x1400282c4  mov     r12d, [rsp+2D8h+arg_0]
0x1400282cc  mov     rsi, [rsp+2D8h+hObject]
0x1400282d1  mov     ebx, [rsp+2D8h+var_290]
0x1400282d5  mov     r15, [rsp+2D8h+var_278]
0x1400282da  jmp     short loc_140028332
0x1400282dc  mov     r9d, 2; dwMoveMethod
0x1400282e2  xor     r8d, r8d; lpDistanceToMoveHigh
0x1400282e5  xor     edx, edx; lDistanceToMove
0x1400282e7  call    cs:__imp_SetFilePointer
0x1400282ed  cmp     eax, 0FFFFFFFFh
0x1400282f0  jnz     short loc_140028277
0x1400282f2  call    cs:__imp_GetLastError
0x1400282f8  mov     ebx, eax
0x1400282fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140028301  cmp     rcx, r14
0x140028304  jz      short loc_14002832A
0x140028306  test    byte ptr [rcx+1Ch], 4
0x14002830a  jz      short loc_14002832A
0x14002830c  cmp     byte ptr [rcx+19h], 2
0x140028310  jb      short loc_14002832A
0x140028312  mov     edx, 5Ah ; 'Z'
0x140028317  mov     r9d, eax
0x14002831a  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028321  mov     rcx, [rcx+10h]
0x140028325  call    WPP_SF_d
0x14002832a  test    ebx, ebx
0x14002832c  jz      loc_14002827C
0x140028332  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140028336  jz      short loc_140028348
0x140028338  mov     rcx, [r15]; hObject
0x14002833b  call    cs:__imp_CloseHandle
0x140028341  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x140028348  test    r12d, r12d
0x14002834b  jnz     short loc_140028355
0x14002834d  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, edi; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x140028353  jmp     short loc_14002835B
0x140028355  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, edi; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x14002835b  mov     dword ptr [rsp+2D8h+lpBuffer], ebx
0x14002835f  mov     word ptr [rsp+2D8h+lpBuffer+4], di
0x140028364  mov     r9d, ebx
0x140028367  lea     r8, aLd; "%ld"
0x14002836e  mov     edx, 0Ch; unsigned __int64
0x140028373  lea     rcx, [rsp+2D8h+lpBuffer+4]; unsigned __int16 *
0x140028378  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002837d  lea     r8, [rsp+2D8h+lpBuffer+4]
0x140028382  test    eax, eax
0x140028384  cmovs   r8, rdi
0x140028388  neg     r12d
0x14002838b  sbb     edx, edx
0x14002838d  add     edx, 3
0x140028390  mov     qword ptr [rsp+2D8h+var_2B0], r8
0x140028395  mov     rax, qword ptr cs:fDesiredAccess
0x14002839c  mov     [rsp+2D8h+lpOverlapped], rax
0x1400283a1  mov     ecx, 1
0x1400283a6  mov     r9d, 0C0007D3Ch
0x1400283ac  lea     r8d, [rcx+1]
0x1400283b0  call    FaxLog
0x1400283b5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400283b9  jz      loc_14002827C
0x1400283bf  mov     rcx, rsi; hObject
0x1400283c2  call    cs:__imp_CloseHandle
0x1400283c8  test    eax, eax
0x1400283ca  jnz     loc_14002827C
0x1400283d0  mov     rax, cs:WPP_GLOBAL_Control
0x1400283d7  cmp     rax, r14
0x1400283da  jz      loc_14002827C
0x1400283e0  test    byte ptr [rax+1Ch], 4
0x1400283e4  jz      loc_14002827C
0x1400283ea  cmp     byte ptr [rax+19h], 2
0x1400283ee  jb      loc_14002827C
0x1400283f4  call    cs:__imp_GetLastError
0x1400283fa  mov     edx, 5Bh ; '['
0x1400283ff  mov     r9d, eax
0x140028402  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140028409  mov     rcx, cs:WPP_GLOBAL_Control
0x140028410  mov     rcx, [rcx+10h]
0x140028414  call    WPP_SF_d
0x140028419  jmp     loc_14002827C
```

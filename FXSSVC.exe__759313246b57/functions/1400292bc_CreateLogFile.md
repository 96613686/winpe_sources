# CreateLogFile

- ea: `0x1400292bc`
- end: `0x1400297a7`
- name: `CreateLogFile`
- size: `1259`
- prototype: `HANDLE __stdcall(LPCWSTR pszLogFileName, ACCESS_MASK fDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES psaLogFile, ULONG fCreateDisposition, ULONG fFlagsAndAttributes)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140028d5c`
- `0x1400297b0`
- `0x14002cfa4`

## callees

- `0x140001bac`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x1400292bc`
- `0x14002c25c`
- `0x1400699d0`
- `0x14006e124`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400293ef`
- `KERNEL32!GetLastError` at `0x140029441`
- `KERNEL32!GetLastError` at `0x1400294ba`
- `KERNEL32!GetLastError` at `0x14002956b`
- `KERNEL32!GetLastError` at `0x140029663`
- `KERNEL32!GetLastError` at `0x140029777`
- `KERNEL32!GetLastError` at `0x1400293ef`
- `KERNEL32!GetLastError` at `0x140029441`
- `KERNEL32!GetLastError` at `0x1400294ba`
- `KERNEL32!GetLastError` at `0x14002956b`
- `KERNEL32!GetLastError` at `0x140029663`
- `KERNEL32!GetLastError` at `0x140029777`
- `KERNEL32!CloseHandle` at `0x1400296b2`
- `KERNEL32!CloseHandle` at `0x14002973f`
- `KERNEL32!CloseHandle` at `0x1400296b2`
- `KERNEL32!CloseHandle` at `0x14002973f`
- `KERNEL32!WriteFile` at `0x1400294aa`
- `KERNEL32!WriteFile` at `0x14002955b`
- `KERNEL32!WriteFile` at `0x1400294aa`
- `KERNEL32!WriteFile` at `0x14002955b`
- `KERNEL32!GetFileSizeEx` at `0x140029431`
- `KERNEL32!GetFileSizeEx` at `0x140029431`
- `KERNEL32!SetFilePointer` at `0x14002964e`
- `KERNEL32!SetFilePointer` at `0x14002964e`

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
      FaxLog(1u, 3 - (v8 != 0), 2u, 0xC0007D3C, ::fDesiredAccess);
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
0x1400292bc  mov     [rsp+arg_18], rbx
0x1400292c1  mov     [rsp+arg_0], ecx
0x1400292c5  push    rsi
0x1400292c6  push    rdi
0x1400292c7  push    r12
0x1400292c9  push    r14
0x1400292cb  push    r15
0x1400292cd  sub     rsp, 2B0h
0x1400292d4  mov     rax, cs:__security_cookie
0x1400292db  xor     rax, rsp
0x1400292de  mov     [rsp+2D8h+var_38], rax
0x1400292e6  mov     r15, r8
0x1400292e9  mov     rbx, rdx
0x1400292ec  mov     r12d, ecx
0x1400292ef  mov     [rsp+2D8h+var_278], r8
0x1400292f4  xor     edi, edi
0x1400292f6  mov     qword ptr [rsp+2D8h+FileSize], rdi
0x1400292fb  mov     [rsp+2D8h+NumberOfBytesWritten], edi
0x1400292ff  lea     r14, WPP_GLOBAL_Control
0x140029306  mov     rcx, cs:WPP_GLOBAL_Control
0x14002930d  cmp     rcx, r14
0x140029310  jz      short loc_140029331
0x140029312  test    byte ptr [rcx+1Ch], 4
0x140029316  jz      short loc_140029331
0x140029318  cmp     byte ptr [rcx+19h], 5
0x14002931c  jb      short loc_140029331
0x14002931e  lea     edx, [rdi+53h]
0x140029321  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029328  mov     rcx, [rcx+10h]
0x14002932c  call    WPP_SF_
0x140029331  lea     rcx, aOutboxlogTxt; "OutboxLOG.txt"
0x140029338  lea     rax, aInboxlogTxt; "InboxLOG.txt"
0x14002933f  test    r12d, r12d
0x140029342  cmovnz  rax, rcx
0x140029346  mov     [rsp+2D8h+lpOverlapped], rax
0x14002934b  mov     r9, rbx
0x14002934e  lea     r8, aSS_0; "%s\\%s"
0x140029355  mov     edx, 104h; unsigned __int64
0x14002935a  lea     rcx, [rsp+2D8h+FileName]; unsigned __int16 *
0x140029362  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140029367  mov     ebx, eax
0x140029369  test    eax, eax
0x14002936b  jns     short loc_1400293B9
0x14002936d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140029371  mov     rcx, cs:WPP_GLOBAL_Control
0x140029378  cmp     rcx, r14
0x14002937b  jz      short loc_14002939F
0x14002937d  test    byte ptr [rcx+1Ch], 4
0x140029381  jz      short loc_14002939F
0x140029383  cmp     byte ptr [rcx+19h], 2
0x140029387  jb      short loc_14002939F
0x140029389  lea     edx, [rsi+55h]
0x14002938c  mov     r9d, eax
0x14002938f  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029396  mov     rcx, [rcx+10h]
0x14002939a  call    WPP_SF_d
0x14002939f  mov     eax, ebx
0x1400293a1  and     eax, 1FFF0000h
0x1400293a6  cmp     eax, 70000h
0x1400293ab  jnz     loc_1400296A1
0x1400293b1  movzx   ebx, bx
0x1400293b4  jmp     loc_1400296A1
0x1400293b9  mov     [rsp+2D8h+var_2B0], 80h; int
0x1400293c1  mov     dword ptr [rsp+2D8h+lpOverlapped], 4; DWORD
0x1400293c9  mov     edx, 40000000h; dwDesiredAccess
0x1400293ce  mov     r8d, 1; dwShareMode
0x1400293d4  lea     rcx, [rsp+2D8h+FileName]; lpFileName
0x1400293dc  call    InternalSafeCreateFile
0x1400293e1  mov     rsi, rax
0x1400293e4  mov     [rsp+2D8h+hObject], rax
0x1400293e9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400293ed  jnz     short loc_140029429
0x1400293ef  call    cs:__imp_GetLastError
0x1400293f6  nop     dword ptr [rax+rax+00h]
0x1400293fb  mov     ebx, eax
0x1400293fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140029404  cmp     rcx, r14
0x140029407  jz      loc_1400296A1
0x14002940d  test    byte ptr [rcx+1Ch], 4
0x140029411  jz      loc_1400296A1
0x140029417  cmp     byte ptr [rcx+19h], 2
0x14002941b  jb      loc_1400296A1
0x140029421  lea     edx, [rsi+56h]
0x140029424  jmp     loc_14002968E
0x140029429  lea     rdx, [rsp+2D8h+FileSize]; lpFileSize
0x14002942e  mov     rcx, rsi; hFile
0x140029431  call    cs:__imp_GetFileSizeEx
0x140029438  nop     dword ptr [rax+rax+00h]
0x14002943d  test    eax, eax
0x14002943f  jnz     short loc_14002947D
0x140029441  call    cs:__imp_GetLastError
0x140029448  nop     dword ptr [rax+rax+00h]
0x14002944d  mov     ebx, eax
0x14002944f  mov     rcx, cs:WPP_GLOBAL_Control
0x140029456  cmp     rcx, r14
0x140029459  jz      loc_1400296A1
0x14002945f  test    byte ptr [rcx+1Ch], 4
0x140029463  jz      loc_1400296A1
0x140029469  cmp     byte ptr [rcx+19h], 2
0x14002946d  jb      loc_1400296A1
0x140029473  mov     edx, 56h ; 'V'
0x140029478  jmp     loc_14002968E
0x14002947d  mov     rcx, rsi; hFile
0x140029480  cmp     qword ptr [rsp+2D8h+FileSize], rdi
0x140029485  jnz     loc_140029643
0x14002948b  mov     eax, 0FEFFh
0x140029490  mov     [rsp+2D8h+Buffer], ax
0x140029495  mov     [rsp+2D8h+lpOverlapped], rdi; lpOverlapped
0x14002949a  lea     r9, [rsp+2D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002949f  mov     r8d, 2; nNumberOfBytesToWrite
0x1400294a5  lea     rdx, [rsp+2D8h+Buffer]; lpBuffer
0x1400294aa  call    cs:__imp_WriteFile
0x1400294b1  nop     dword ptr [rax+rax+00h]
0x1400294b6  test    eax, eax
0x1400294b8  jnz     short loc_1400294F6
0x1400294ba  call    cs:__imp_GetLastError
0x1400294c1  nop     dword ptr [rax+rax+00h]
0x1400294c6  mov     ebx, eax
0x1400294c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400294cf  cmp     rcx, r14
0x1400294d2  jz      loc_1400296A1
0x1400294d8  test    byte ptr [rcx+1Ch], 4
0x1400294dc  jz      loc_1400296A1
0x1400294e2  cmp     byte ptr [rcx+19h], 2
0x1400294e6  jb      loc_1400296A1
0x1400294ec  mov     edx, 57h ; 'W'
0x1400294f1  jmp     loc_14002968E
0x1400294f6  mov     [rsp+2D8h+var_250], 7
0x140029502  mov     [rsp+2D8h+var_258], rdi
0x14002950a  mov     word ptr [rsp+2D8h+lpBuffer], di
0x14002950f  lea     rax, aOutbox; "Outbox"
0x140029516  lea     rcx, aInbox; "Inbox"
0x14002951d  test    r12d, r12d
0x140029520  cmovnz  rcx, rax; String1
0x140029524  lea     rdx, [rsp+2D8h+lpBuffer]; Src
0x140029529  call    GetTableColumnsText
0x14002952e  nop
0x14002952f  mov     r8d, dword ptr [rsp+2D8h+var_258]
0x140029537  lea     rdx, [rsp+2D8h+lpBuffer]
0x14002953c  cmp     [rsp+2D8h+var_250], 8
0x140029545  cmovnb  rdx, [rsp+2D8h+lpBuffer]; lpBuffer
0x14002954b  add     r8d, r8d; nNumberOfBytesToWrite
0x14002954e  mov     [rsp+2D8h+lpOverlapped], rdi; lpOverlapped
0x140029553  lea     r9, [rsp+2D8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140029558  mov     rcx, rsi; hFile
0x14002955b  call    cs:__imp_WriteFile
0x140029562  nop     dword ptr [rax+rax+00h]
0x140029567  test    eax, eax
0x140029569  jnz     short loc_1400295C8
0x14002956b  call    cs:__imp_GetLastError
0x140029572  nop     dword ptr [rax+rax+00h]
0x140029577  mov     ebx, eax
0x140029579  mov     rcx, cs:WPP_GLOBAL_Control
0x140029580  cmp     rcx, r14
0x140029583  jz      short loc_1400295AA
0x140029585  test    byte ptr [rcx+1Ch], 4
0x140029589  jz      short loc_1400295AA
0x14002958b  cmp     byte ptr [rcx+19h], 2
0x14002958f  jb      short loc_1400295AA
0x140029591  mov     edx, 59h ; 'Y'
0x140029596  mov     r9d, eax
0x140029599  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x1400295a0  mov     rcx, [rcx+10h]
0x1400295a4  call    WPP_SF_d
0x1400295a9  nop
0x1400295aa  cmp     [rsp+2D8h+var_250], 8
0x1400295b3  jb      loc_1400296A1
0x1400295b9  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x1400295be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400295c3  jmp     loc_1400296A1
0x1400295c8  cmp     [rsp+2D8h+var_250], 8
0x1400295d1  jb      short loc_1400295DD
0x1400295d3  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x1400295d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400295dd  mov     ebx, edi
0x1400295df  mov     [r15], rsi
0x1400295e2  mov     eax, ebx
0x1400295e4  mov     rcx, [rsp+2D8h+var_38]
0x1400295ec  xor     rcx, rsp; StackCookie
0x1400295ef  call    __security_check_cookie
0x1400295f4  mov     rbx, [rsp+2D8h+arg_18]
0x1400295fc  add     rsp, 2B0h
0x140029603  pop     r15
0x140029605  pop     r14
0x140029607  pop     r12
0x140029609  pop     rdi
0x14002960a  pop     rsi
0x14002960b  retn
0x14002960d  cmp     [rsp+2D8h+var_250], 8
0x140029616  jb      short loc_140029622
0x140029618  mov     rcx, [rsp+2D8h+lpBuffer]; Block
0x14002961d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140029622  xor     edi, edi
0x140029624  lea     r14, WPP_GLOBAL_Control
0x14002962b  mov     r12d, [rsp+2D8h+arg_0]
0x140029633  mov     rsi, [rsp+2D8h+hObject]
0x140029638  mov     ebx, [rsp+2D8h+var_290]
0x14002963c  mov     r15, [rsp+2D8h+var_278]
0x140029641  jmp     short loc_1400296A9
0x140029643  mov     r9d, 2; dwMoveMethod
0x140029649  xor     r8d, r8d; lpDistanceToMoveHigh
0x14002964c  xor     edx, edx; lDistanceToMove
0x14002964e  call    cs:__imp_SetFilePointer
0x140029655  nop     dword ptr [rax+rax+00h]
0x14002965a  cmp     eax, 0FFFFFFFFh
0x14002965d  jnz     loc_1400295DD
0x140029663  call    cs:__imp_GetLastError
0x14002966a  nop     dword ptr [rax+rax+00h]
0x14002966f  mov     ebx, eax
0x140029671  mov     rcx, cs:WPP_GLOBAL_Control
0x140029678  cmp     rcx, r14
0x14002967b  jz      short loc_1400296A1
0x14002967d  test    byte ptr [rcx+1Ch], 4
0x140029681  jz      short loc_1400296A1
0x140029683  cmp     byte ptr [rcx+19h], 2
0x140029687  jb      short loc_1400296A1
0x140029689  mov     edx, 5Ah ; 'Z'
0x14002968e  mov     r9d, eax
0x140029691  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029698  mov     rcx, [rcx+10h]
0x14002969c  call    WPP_SF_d
0x1400296a1  test    ebx, ebx
0x1400296a3  jz      loc_1400295E2
0x1400296a9  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400296ad  jz      short loc_1400296C5
0x1400296af  mov     rcx, [r15]; hObject
0x1400296b2  call    cs:__imp_CloseHandle
0x1400296b9  nop     dword ptr [rax+rax+00h]
0x1400296be  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400296c5  test    r12d, r12d
0x1400296c8  jnz     short loc_1400296D2
0x1400296ca  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+4, edi; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x1400296d0  jmp     short loc_1400296D8
0x1400296d2  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A+8, edi; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x1400296d8  mov     dword ptr [rsp+2D8h+lpBuffer], ebx
0x1400296dc  mov     word ptr [rsp+2D8h+lpBuffer+4], di
0x1400296e1  mov     r9d, ebx
0x1400296e4  lea     r8, aLd; "%ld"
0x1400296eb  mov     edx, 0Ch; unsigned __int64
0x1400296f0  lea     rcx, [rsp+2D8h+lpBuffer+4]; unsigned __int16 *
0x1400296f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400296fa  lea     r8, [rsp+2D8h+lpBuffer+4]
0x1400296ff  test    eax, eax
0x140029701  cmovs   r8, rdi
0x140029705  neg     r12d
0x140029708  sbb     edx, edx
0x14002970a  add     edx, 3
0x14002970d  mov     qword ptr [rsp+2D8h+var_2B0], r8
0x140029712  mov     rax, qword ptr cs:fDesiredAccess
0x140029719  mov     [rsp+2D8h+lpOverlapped], rax
0x14002971e  mov     ecx, 1
0x140029723  mov     r9d, 0C0007D3Ch
0x140029729  lea     r8d, [rcx+1]
0x14002972d  call    FaxLog
0x140029732  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140029736  jz      loc_1400295E2
0x14002973c  mov     rcx, rsi; hObject
0x14002973f  call    cs:__imp_CloseHandle
0x140029746  nop     dword ptr [rax+rax+00h]
0x14002974b  test    eax, eax
0x14002974d  jnz     loc_1400295E2
0x140029753  mov     rax, cs:WPP_GLOBAL_Control
0x14002975a  cmp     rax, r14
0x14002975d  jz      loc_1400295E2
0x140029763  test    byte ptr [rax+1Ch], 4
0x140029767  jz      loc_1400295E2
0x14002976d  cmp     byte ptr [rax+19h], 2
0x140029771  jb      loc_1400295E2
0x140029777  call    cs:__imp_GetLastError
0x14002977e  nop     dword ptr [rax+rax+00h]
0x140029783  mov     edx, 5Bh ; '['
0x140029788  mov     r9d, eax
0x14002978b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x140029792  mov     rcx, cs:WPP_GLOBAL_Control
0x140029799  mov     rcx, [rcx+10h]
0x14002979d  call    WPP_SF_d
0x1400297a2  jmp     loc_1400295E2
```

# DpspReadQueuedResolutionFromFile(void *,INSTANCEINFO * *)

- ea: `0x180013214`
- end: `0x1800137a0`
- name: `?DpspReadQueuedResolutionFromFile@@YAJPEAXPEAPEAUINSTANCEINFO@@@Z`
- size: `1420`
- prototype: `__int64 __fastcall(HANDLE hFile, struct INSTANCEINFO **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800137a8`

## callees

- `0x1800013a0`
- `0x180005ec0`
- `0x180006a3c`
- `0x180006ae8`
- `0x180008ea0`
- `0x180008f70`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x18000bbd4`
- `0x180013214`
- `0x180018680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013267`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800133ef`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800133ef`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013508`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001361a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180013508`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001361a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013538`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013565`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001364a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013677`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013538`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013565`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001364a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180013677`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013778`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013778`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013786`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180013786`

## string_xrefs

- `0x1800132a9`: `DpspReadQueuedResolutionFromFile`
- `0x1800132f6`: `DpspReadQueuedResolutionFromFile`

## pseudocode

```c
__int64 __fastcall DpspReadQueuedResolutionFromFile(HANDLE hFile, struct INSTANCEINFO **a2)
{
  _QWORD *v4; // rdi
  signed int LastError; // eax
  signed int Args; // ebx
  _QWORD *v7; // rax
  int v8; // r8d
  int v10; // eax
  __int64 ScenarioFromId; // rax
  int v12; // eax
  void *v13; // rax
  int File; // eax
  PSID v15; // rax
  int v16; // eax
  void *v17; // rax
  int v18; // eax
  PSID v19; // rax
  int ParameterCollectionFromFile; // eax
  __int64 SessionFromId; // rax
  _OWORD *v22; // rax
  int v23; // eax
  size_t Size; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v25; // [rsp+38h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-40h] BYREF
  __int128 v27; // [rsp+50h] [rbp-30h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-20h] BYREF

  Size = 0;
  v25 = 0;
  SystemTimeAsFileTime = 0;
  v4 = 0;
  Buffer = 0;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( Args < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspReadQueuedResolutionFromFile",
        1325,
        (int)L"Error = %d",
        Args);
      goto LABEL_11;
    }
  }
  if ( !a2 )
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1326,
      (int)L"Error = %d",
      87);
    return (unsigned int)Args;
  }
  *a2 = 0;
  v7 = (_QWORD *)WdipAlloc(1264);
  v25 = v7;
  v4 = v7;
  if ( !v7 )
  {
    v8 = 1333;
LABEL_10:
    Args = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      v8,
      (int)L"Error = %d",
      14);
    goto LABEL_11;
  }
  memset_0(v7, 0, 0x4F0u);
  Args = WdipReadFile(hFile, v4, 0x4E0u);
  if ( Args < 0 )
  {
    WdipFree(v4);
    v4 = 0;
    v25 = 0;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1347,
      (int)L"Error = %d",
      Args);
    goto LABEL_11;
  }
  v4[153] = v4 + 156;
  v4[94] = 0;
  v4[95] = 0;
  v4[96] = 0;
  v4[97] = 0;
  v4[98] = 0;
  v4[99] = 0;
  v4[100] = 0;
  v4[152] = 0;
  v4[101] = 0;
  v4[154] = 0;
  v4[155] = 0;
  *((_DWORD *)v4 + 19) = 0;
  v4[1] = v4;
  *v4 = v4;
  InitializeSRWLock((PSRWLOCK)v4 + 2);
  v10 = WdipReadFile(hFile, &Buffer, 0x10u);
  Args = v10;
  if ( v10 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1380,
      (int)L"Error = %d",
      v10);
    goto LABEL_11;
  }
  v27 = Buffer;
  ScenarioFromId = DpspGetScenarioFromId(&v27);
  v4[152] = ScenarioFromId;
  if ( !ScenarioFromId )
  {
    Args = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1383,
      (int)L"Error = %d",
      5);
    goto LABEL_11;
  }
  if ( (*(_BYTE *)(ScenarioFromId + 92) & 1) == 0 )
  {
    Args = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1387,
      (int)L"Error = %d",
      5);
    goto LABEL_11;
  }
  v12 = WdipReadFile(hFile, &Size, 4u);
  Args = v12;
  if ( v12 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1399,
      (int)L"Error = %d",
      v12);
    goto LABEL_11;
  }
  v13 = (void *)WdipAlloc((unsigned int)Size);
  v4[96] = v13;
  if ( !v13 )
  {
    v8 = 1402;
    goto LABEL_10;
  }
  memset_0(v13, 0, (unsigned int)Size);
  File = WdipReadFile(hFile, (LPVOID)v4[96], Size);
  Args = File;
  if ( File < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1411,
      (int)L"Error = %d",
      File);
    goto LABEL_11;
  }
  if ( !IsValidSid((PSID)v4[96]) )
  {
    Args = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1415,
      (int)L"Error = %d",
      5);
    goto LABEL_11;
  }
  if ( EqualSid(g_pAdminSid, (PSID)v4[96]) )
  {
    WdipFree(v4[96]);
    v15 = g_pAdminSid;
  }
  else
  {
    if ( !EqualSid(g_pEveryoneSid, (PSID)v4[96]) )
      goto LABEL_35;
    WdipFree(v4[96]);
    v15 = g_pEveryoneSid;
  }
  v4[96] = v15;
LABEL_35:
  v16 = WdipReadFile(hFile, &Size, 4u);
  Args = v16;
  if ( v16 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1444,
      (int)L"Error = %d",
      v16);
    goto LABEL_11;
  }
  v17 = (void *)WdipAlloc((unsigned int)Size);
  v4[95] = v17;
  if ( !v17 )
  {
    v8 = 1447;
    goto LABEL_10;
  }
  memset_0(v17, 0, (unsigned int)Size);
  v18 = WdipReadFile(hFile, (LPVOID)v4[95], Size);
  Args = v18;
  if ( v18 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1456,
      (int)L"Error = %d",
      v18);
    goto LABEL_11;
  }
  if ( !IsValidSid((PSID)v4[95]) )
  {
    Args = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1460,
      (int)L"Error = %d",
      5);
    goto LABEL_11;
  }
  if ( EqualSid(g_pAdminSid, (PSID)v4[95]) )
  {
    WdipFree(v4[95]);
    v19 = g_pAdminSid;
  }
  else
  {
    if ( !EqualSid(g_pEveryoneSid, (PSID)v4[95]) )
      goto LABEL_48;
    WdipFree(v4[95]);
    v19 = g_pEveryoneSid;
  }
  v4[95] = v19;
LABEL_48:
  ParameterCollectionFromFile = WdipReadParameterCollectionFromFile(v4[153], hFile);
  Args = ParameterCollectionFromFile;
  if ( ParameterCollectionFromFile >= 0 )
  {
    v27 = *(_OWORD *)(v4 + 5);
    SessionFromId = DpspGetSessionFromId(&v27);
    v4[101] = SessionFromId;
    if ( SessionFromId )
    {
      if ( (*(_BYTE *)(SessionFromId + 152) & 1) != 0 )
      {
        v22 = (_OWORD *)WdipAlloc(32);
        v4[98] = v22;
        if ( v22 )
        {
          *v22 = 0;
          v22[1] = 0;
          v23 = StringCbCopyW((unsigned __int16 *)v4[98], 0x20u, L"Winsta0\\Default");
          Args = v23;
          if ( v23 >= 0 )
          {
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            if ( CompareFileTime((const FILETIME *)v4 + 15, &SystemTimeAsFileTime) > 0 )
            {
              *((_DWORD *)v4 + 18) = 0;
              *a2 = (struct INSTANCEINFO *)v4;
              return (unsigned int)Args;
            }
          }
          else
          {
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
              (int)L"DpspReadQueuedResolutionFromFile",
              1511,
              (int)L"Error = %d",
              v23);
          }
          goto LABEL_11;
        }
        v8 = 1504;
        goto LABEL_10;
      }
      Args = -2147467259;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspReadQueuedResolutionFromFile",
        1497,
        (int)L"Error = %d",
        5);
    }
    else
    {
      Args = -2147467259;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspReadQueuedResolutionFromFile",
        1493,
        (int)L"Error = %d",
        5);
    }
  }
  else
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutionFromFile",
      1486,
      (int)L"Error = %d",
      ParameterCollectionFromFile);
  }
LABEL_11:
  if ( v4 )
    DpspFreeSpecificInstanceInfo(&v25);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180013214  mov     [rsp-28h+arg_10], rbx
0x180013219  push    rbp
0x18001321a  push    rsi
0x18001321b  push    rdi
0x18001321c  push    r14
0x18001321e  push    r15
0x180013220  mov     rbp, rsp
0x180013223  sub     rsp, 80h
0x18001322a  mov     rax, cs:__security_cookie
0x180013231  xor     rax, rsp
0x180013234  mov     [rbp+var_10], rax
0x180013238  xor     r15d, r15d
0x18001323b  lea     rax, [rcx+1]
0x18001323f  mov     dword ptr [rbp+Size], r15d
0x180013243  xorps   xmm0, xmm0
0x180013246  mov     dword ptr [rbp+Size+4], r15d
0x18001324a  mov     r14, rdx
0x18001324d  mov     [rbp+var_48], r15
0x180013251  mov     rsi, rcx
0x180013254  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r15
0x180013258  mov     edi, r15d
0x18001325b  movups  [rbp+Buffer], xmm0
0x18001325f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013265  jnz     short loc_18001328F
0x180013267  call    cs:__imp_GetLastError
0x18001326d  mov     ebx, eax
0x18001326f  test    eax, eax
0x180013271  jle     short loc_18001327C
0x180013273  movzx   ebx, ax
0x180013276  or      ebx, 80070000h
0x18001327c  test    ebx, ebx
0x18001327e  jns     short loc_18001328F
0x180013280  movzx   eax, bx
0x180013283  mov     r8d, 52Dh
0x180013289  mov     dword ptr [rsp+80h+Args], eax
0x18001328d  jmp     short loc_1800132EF
0x18001328f  test    r14, r14
0x180013292  jnz     short loc_1800132C3
0x180013294  lea     r9, aErrorD; "Error = %d"
0x18001329b  mov     dword ptr [rsp+80h+Args], 57h ; 'W'; Args
0x1800132a3  mov     r8d, 52Eh; int
0x1800132a9  lea     rdx, aDpspreadqueued; "DpspReadQueuedResolutionFromFile"
0x1800132b0  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800132b7  mov     ebx, 80070057h
0x1800132bc  call    WdipTraceError
0x1800132c1  jmp     short loc_180013317
0x1800132c3  mov     ebx, 4F0h
0x1800132c8  mov     [r14], r15
0x1800132cb  mov     ecx, ebx
0x1800132cd  call    WdipAlloc
0x1800132d2  mov     [rbp+var_48], rax
0x1800132d6  mov     rdi, rax
0x1800132d9  test    rax, rax
0x1800132dc  jnz     short loc_18001333C
0x1800132de  lea     r8d, [rbx+45h]; int
0x1800132e2  mov     dword ptr [rsp+80h+Args], 0Eh; Args
0x1800132ea  mov     ebx, 8007000Eh
0x1800132ef  lea     r9, aErrorD; "Error = %d"
0x1800132f6  lea     rdx, aDpspreadqueued; "DpspReadQueuedResolutionFromFile"
0x1800132fd  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180013304  call    WdipTraceError
0x180013309  test    rdi, rdi
0x18001330c  jz      short loc_180013317
0x18001330e  lea     rcx, [rbp+var_48]
0x180013312  call    DpspFreeSpecificInstanceInfo
0x180013317  mov     eax, ebx
0x180013319  mov     rcx, [rbp+var_10]
0x18001331d  xor     rcx, rsp; StackCookie
0x180013320  call    __security_check_cookie
0x180013325  mov     rbx, [rsp+80h+arg_10]
0x18001332d  add     rsp, 80h
0x180013334  pop     r15
0x180013336  pop     r14
0x180013338  pop     rdi
0x180013339  pop     rsi
0x18001333a  pop     rbp
0x18001333b  retn
0x18001333c  mov     r8, rbx; Size
0x18001333f  xor     edx, edx; Val
0x180013341  mov     rcx, rdi; void *
0x180013344  call    memset_0
0x180013349  lea     r9, [rbp+Size+4]
0x18001334d  mov     r8d, 4E0h; nNumberOfBytesToRead
0x180013353  mov     rdx, rdi; lpBuffer
0x180013356  mov     rcx, rsi; hFile
0x180013359  call    WdipReadFile
0x18001335e  mov     ebx, eax
0x180013360  test    eax, eax
0x180013362  jns     short loc_180013385
0x180013364  mov     rcx, rdi
0x180013367  call    WdipFree
0x18001336c  movzx   ecx, bx
0x18001336f  mov     rdi, r15
0x180013372  mov     dword ptr [rsp+80h+Args], ecx
0x180013376  mov     r8d, 543h
0x18001337c  mov     [rbp+var_48], r15
0x180013380  jmp     loc_1800132EF
0x180013385  lea     rax, [rdi+4E0h]
0x18001338c  mov     [rdi+4C8h], rax
0x180013393  lea     rcx, [rdi+10h]; SRWLock
0x180013397  mov     [rdi+2F0h], r15
0x18001339e  mov     [rdi+2F8h], r15
0x1800133a5  mov     [rdi+300h], r15
0x1800133ac  mov     [rdi+308h], r15
0x1800133b3  mov     [rdi+310h], r15
0x1800133ba  mov     [rdi+318h], r15
0x1800133c1  mov     [rdi+320h], r15
0x1800133c8  mov     [rdi+4C0h], r15
0x1800133cf  mov     [rdi+328h], r15
0x1800133d6  mov     [rdi+4D0h], r15
0x1800133dd  mov     [rdi+4D8h], r15
0x1800133e4  mov     [rdi+4Ch], r15d
0x1800133e8  mov     [rdi+8], rdi
0x1800133ec  mov     [rdi], rdi
0x1800133ef  call    cs:__imp_InitializeSRWLock
0x1800133f5  lea     r9, [rbp+Size+4]
0x1800133f9  mov     r8d, 10h; nNumberOfBytesToRead
0x1800133ff  lea     rdx, [rbp+Buffer]; lpBuffer
0x180013403  mov     rcx, rsi; hFile
0x180013406  call    WdipReadFile
0x18001340b  mov     ebx, eax
0x18001340d  test    eax, eax
0x18001340f  jns     short loc_180013423
0x180013411  movzx   eax, ax
0x180013414  mov     r8d, 564h
0x18001341a  mov     dword ptr [rsp+80h+Args], eax
0x18001341e  jmp     loc_1800132EF
0x180013423  movaps  xmm0, [rbp+Buffer]
0x180013427  lea     rcx, [rbp+var_30]
0x18001342b  movdqa  [rbp+var_30], xmm0
0x180013430  call    DpspGetScenarioFromId
0x180013435  mov     [rdi+4C0h], rax
0x18001343c  test    rax, rax
0x18001343f  jnz     short loc_180013459
0x180013441  mov     ebx, 80004005h
0x180013446  mov     dword ptr [rsp+80h+Args], 4005h
0x18001344e  mov     r8d, 567h
0x180013454  jmp     loc_1800132EF
0x180013459  test    byte ptr [rax+5Ch], 1
0x18001345d  jnz     short loc_180013477
0x18001345f  mov     ebx, 80004005h
0x180013464  mov     dword ptr [rsp+80h+Args], 4005h
0x18001346c  mov     r8d, 56Bh
0x180013472  jmp     loc_1800132EF
0x180013477  lea     r9, [rbp+Size+4]
0x18001347b  mov     r8d, 4; nNumberOfBytesToRead
0x180013481  lea     rdx, [rbp+Size]; lpBuffer
0x180013485  mov     rcx, rsi; hFile
0x180013488  call    WdipReadFile
0x18001348d  mov     ebx, eax
0x18001348f  test    eax, eax
0x180013491  jns     short loc_1800134A5
0x180013493  movzx   eax, ax
0x180013496  mov     r8d, 577h
0x18001349c  mov     dword ptr [rsp+80h+Args], eax
0x1800134a0  jmp     loc_1800132EF
0x1800134a5  mov     ecx, dword ptr [rbp+Size]
0x1800134a8  call    WdipAlloc
0x1800134ad  mov     [rdi+300h], rax
0x1800134b4  test    rax, rax
0x1800134b7  jnz     short loc_1800134C4
0x1800134b9  mov     r8d, 57Ah
0x1800134bf  jmp     loc_1800132E2
0x1800134c4  mov     r8d, dword ptr [rbp+Size]; Size
0x1800134c8  xor     edx, edx; Val
0x1800134ca  mov     rcx, rax; void *
0x1800134cd  call    memset_0
0x1800134d2  mov     r8d, dword ptr [rbp+Size]; nNumberOfBytesToRead
0x1800134d6  lea     r9, [rbp+Size+4]
0x1800134da  mov     rdx, [rdi+300h]; lpBuffer
0x1800134e1  mov     rcx, rsi; hFile
0x1800134e4  call    WdipReadFile
0x1800134e9  mov     ebx, eax
0x1800134eb  test    eax, eax
0x1800134ed  jns     short loc_180013501
0x1800134ef  movzx   eax, ax
0x1800134f2  mov     r8d, 583h
0x1800134f8  mov     dword ptr [rsp+80h+Args], eax
0x1800134fc  jmp     loc_1800132EF
0x180013501  mov     rcx, [rdi+300h]; pSid
0x180013508  call    cs:__imp_IsValidSid
0x18001350e  test    eax, eax
0x180013510  jnz     short loc_18001352A
0x180013512  mov     ebx, 80004005h
0x180013517  mov     dword ptr [rsp+80h+Args], 4005h
0x18001351f  mov     r8d, 587h
0x180013525  jmp     loc_1800132EF
0x18001352a  mov     rdx, [rdi+300h]; pSid2
0x180013531  mov     rcx, cs:g_pAdminSid; pSid1
0x180013538  call    cs:__imp_EqualSid
0x18001353e  test    eax, eax
0x180013540  jz      short loc_180013557
0x180013542  mov     rcx, [rdi+300h]
0x180013549  call    WdipFree
0x18001354e  mov     rax, cs:g_pAdminSid
0x180013555  jmp     short loc_180013582
0x180013557  mov     rdx, [rdi+300h]; pSid2
0x18001355e  mov     rcx, cs:g_pEveryoneSid; pSid1
0x180013565  call    cs:__imp_EqualSid
0x18001356b  test    eax, eax
0x18001356d  jz      short loc_180013589
0x18001356f  mov     rcx, [rdi+300h]
0x180013576  call    WdipFree
0x18001357b  mov     rax, cs:g_pEveryoneSid
0x180013582  mov     [rdi+300h], rax
0x180013589  lea     r9, [rbp+Size+4]
0x18001358d  mov     r8d, 4; nNumberOfBytesToRead
0x180013593  lea     rdx, [rbp+Size]; lpBuffer
0x180013597  mov     rcx, rsi; hFile
0x18001359a  call    WdipReadFile
0x18001359f  mov     ebx, eax
0x1800135a1  test    eax, eax
0x1800135a3  jns     short loc_1800135B7
0x1800135a5  movzx   eax, ax
0x1800135a8  mov     r8d, 5A4h
0x1800135ae  mov     dword ptr [rsp+80h+Args], eax
0x1800135b2  jmp     loc_1800132EF
0x1800135b7  mov     ecx, dword ptr [rbp+Size]
0x1800135ba  call    WdipAlloc
0x1800135bf  mov     [rdi+2F8h], rax
0x1800135c6  test    rax, rax
0x1800135c9  jnz     short loc_1800135D6
0x1800135cb  mov     r8d, 5A7h
0x1800135d1  jmp     loc_1800132E2
0x1800135d6  mov     r8d, dword ptr [rbp+Size]; Size
0x1800135da  xor     edx, edx; Val
0x1800135dc  mov     rcx, rax; void *
0x1800135df  call    memset_0
0x1800135e4  mov     r8d, dword ptr [rbp+Size]; nNumberOfBytesToRead
0x1800135e8  lea     r9, [rbp+Size+4]
0x1800135ec  mov     rdx, [rdi+2F8h]; lpBuffer
0x1800135f3  mov     rcx, rsi; hFile
0x1800135f6  call    WdipReadFile
0x1800135fb  mov     ebx, eax
0x1800135fd  test    eax, eax
0x1800135ff  jns     short loc_180013613
0x180013601  movzx   eax, ax
0x180013604  mov     r8d, 5B0h
0x18001360a  mov     dword ptr [rsp+80h+Args], eax
0x18001360e  jmp     loc_1800132EF
0x180013613  mov     rcx, [rdi+2F8h]; pSid
0x18001361a  call    cs:__imp_IsValidSid
0x180013620  test    eax, eax
0x180013622  jnz     short loc_18001363C
0x180013624  mov     ebx, 80004005h
0x180013629  mov     dword ptr [rsp+80h+Args], 4005h
0x180013631  mov     r8d, 5B4h
0x180013637  jmp     loc_1800132EF
0x18001363c  mov     rdx, [rdi+2F8h]; pSid2
0x180013643  mov     rcx, cs:g_pAdminSid; pSid1
0x18001364a  call    cs:__imp_EqualSid
0x180013650  test    eax, eax
0x180013652  jz      short loc_180013669
0x180013654  mov     rcx, [rdi+2F8h]
0x18001365b  call    WdipFree
0x180013660  mov     rax, cs:g_pAdminSid
0x180013667  jmp     short loc_180013694
0x180013669  mov     rdx, [rdi+2F8h]; pSid2
0x180013670  mov     rcx, cs:g_pEveryoneSid; pSid1
0x180013677  call    cs:__imp_EqualSid
0x18001367d  test    eax, eax
0x18001367f  jz      short loc_18001369B
0x180013681  mov     rcx, [rdi+2F8h]
0x180013688  call    WdipFree
0x18001368d  mov     rax, cs:g_pEveryoneSid
0x180013694  mov     [rdi+2F8h], rax
0x18001369b  mov     rcx, [rdi+4C8h]
0x1800136a2  mov     rdx, rsi
0x1800136a5  call    WdipReadParameterCollectionFromFile
0x1800136aa  mov     ebx, eax
0x1800136ac  test    eax, eax
0x1800136ae  jns     short loc_1800136C2
0x1800136b0  movzx   eax, ax
0x1800136b3  mov     r8d, 5CEh
0x1800136b9  mov     dword ptr [rsp+80h+Args], eax
0x1800136bd  jmp     loc_1800132EF
0x1800136c2  movups  xmm0, xmmword ptr [rdi+28h]
0x1800136c6  lea     rcx, [rbp+var_30]
0x1800136ca  movdqu  [rbp+var_30], xmm0
0x1800136cf  call    DpspGetSessionFromId
0x1800136d4  mov     [rdi+328h], rax
0x1800136db  test    rax, rax
0x1800136de  jnz     short loc_1800136F8
0x1800136e0  mov     ebx, 80004005h
0x1800136e5  mov     dword ptr [rsp+80h+Args], 4005h
0x1800136ed  mov     r8d, 5D5h
0x1800136f3  jmp     loc_1800132EF
0x1800136f8  test    byte ptr [rax+98h], 1
0x1800136ff  jnz     short loc_180013719
0x180013701  mov     ebx, 80004005h
0x180013706  mov     dword ptr [rsp+80h+Args], 4005h
0x18001370e  mov     r8d, 5D9h
0x180013714  jmp     loc_1800132EF
0x180013719  mov     ebx, 20h ; ' '
0x18001371e  mov     ecx, ebx
0x180013720  call    WdipAlloc
0x180013725  mov     [rdi+310h], rax
0x18001372c  test    rax, rax
0x18001372f  jnz     short loc_18001373C
0x180013731  mov     r8d, 5E0h
  ... truncated ...
```

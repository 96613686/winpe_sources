# EfspWriteUserFEQueueToFile(ushort const *,_EFS_USER_FE_QUEUE *)

- ea: `0x1800443ec`
- end: `0x180044882`
- name: `?EfspWriteUserFEQueueToFile@@YAJPEBGPEAU_EFS_USER_FE_QUEUE@@@Z`
- size: `1174`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _EFS_USER_FE_QUEUE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180043bd8`

## callees

- `0x180010bf0`
- `0x180043e4c`
- `0x1800443ec`
- `0x180044888`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004458b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004458b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800446f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800447da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004482d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004479e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044877`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004479e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044877`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180044795`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180044795`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180044662`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004468c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800446b2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800446d3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180044662`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004468c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800446b2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800446d3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044500`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004450d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004451b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180044500`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004450d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004451b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004457c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800447ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004457c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800447ce`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180044823`
- `api-ms-win-core-file-l2-1-0!ReplaceFileW` at `0x180044823`

## pseudocode

```c
__int64 __fastcall EfspWriteUserFEQueueToFile(const unsigned __int16 *a1, struct _EFS_USER_FE_QUEUE *a2)
{
  _DWORD *v2; // rsi
  WCHAR *v4; // r14
  char v6; // r15
  unsigned int StoreFilePath; // ebx
  int v8; // eax
  int v9; // ecx
  WCHAR *v10; // r12
  __int64 v11; // rdx
  int v13; // ecx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  LPCWSTR v16; // rax
  _QWORD *v17; // r15
  int v18; // eax
  DWORD v19; // r8d
  DWORD v20; // r8d
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  HANDLE v25; // rax
  signed int v26; // eax
  signed int v27; // eax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-10h] BYREF
  LPCVOID lpBuffer; // [rsp+A0h] [rbp+50h] BYREF
  LPCWSTR lpReplacementFileName; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 0;
  lpBuffer = 0;
  v4 = 0;
  lpFileName[0] = 0;
  lpReplacementFileName = 0;
  v6 = 1;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 98);
  StoreFilePath = GetStoreFilePath(a1, 0, 0, lpFileName);
  v8 = fnEfsLogTrace1String1Dword(
         g_hPublisher,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
         (unsigned int)&sourceString,
         StoreFilePath,
         34,
         98);
  v10 = (WCHAR *)lpFileName[0];
  if ( v8 >= 0 )
  {
    fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 103);
    LOBYTE(v11) = 1;
    StoreFilePath = GetStoreFilePath(a1, v11, 0, &lpReplacementFileName);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                StoreFilePath,
                34,
                103) < 0 )
    {
LABEL_5:
      v4 = (WCHAR *)lpReplacementFileName;
      goto LABEL_6;
    }
    if ( !a2 )
    {
      DeleteFileW(v10);
      goto LABEL_5;
    }
    v4 = (WCHAR *)lpReplacementFileName;
    FileW = CreateFileW(lpReplacementFileName, 0x40000000u, 0, 0, 2u, 6u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      StoreFilePath = LastError;
      if ( LastError > 0 )
        StoreFilePath = (unsigned __int16)LastError | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 130);
    }
    else
    {
      v16 = (LPCWSTR)((char *)a2 + 8);
      v17 = (_QWORD *)*((_QWORD *)a2 + 1);
      lpReplacementFileName = (LPCWSTR)((char *)a2 + 8);
      while ( v17 != (_QWORD *)v16 )
      {
        fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 34, 144);
        StoreFilePath = CreateFEQStoreFile(v17 - 6, &lpBuffer);
        v18 = fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                StoreFilePath,
                34,
                144);
        v2 = lpBuffer;
        if ( v18 < 0 )
          goto LABEL_50;
        if ( !WriteFile(FileW, lpBuffer, 0x38u, 0, 0) )
        {
          v24 = GetLastError();
          StoreFilePath = v24;
          if ( v24 > 0 )
            StoreFilePath = (unsigned __int16)v24 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 156);
          goto LABEL_50;
        }
        v19 = v2[11];
        if ( v19 && !WriteFile(FileW, (LPCVOID)*(v17 - 3), v19, 0, 0) )
        {
          v21 = GetLastError();
          StoreFilePath = v21;
          if ( v21 > 0 )
            StoreFilePath = (unsigned __int16)v21 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 167);
          goto LABEL_50;
        }
        v20 = v2[12];
        if ( v20 && !WriteFile(FileW, (LPCVOID)*(v17 - 2), v20, 0, 0) )
        {
          v22 = GetLastError();
          StoreFilePath = v22;
          if ( v22 > 0 )
            StoreFilePath = (unsigned __int16)v22 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 179);
          goto LABEL_50;
        }
        if ( !WriteFile(FileW, (LPCVOID)*(v17 - 1), v2[13], 0, 0) )
        {
          v23 = GetLastError();
          StoreFilePath = v23;
          if ( v23 > 0 )
            StoreFilePath = (unsigned __int16)v23 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 189);
          goto LABEL_50;
        }
        EfsFreeHeap(v2);
        v17 = (_QWORD *)*v17;
        v2 = 0;
        v16 = lpReplacementFileName;
        lpBuffer = 0;
      }
      FlushFileBuffers(FileW);
      CloseHandle(FileW);
      v6 = 0;
      v25 = CreateFileW(v10, 0x40000000u, 0, 0, 4u, 6u, 0);
      if ( v25 == (HANDLE)-1LL )
      {
        v26 = GetLastError();
        StoreFilePath = v26;
        if ( v26 > 0 )
          StoreFilePath = (unsigned __int16)v26 | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 219);
      }
      else
      {
        CloseHandle(v25);
        if ( ReplaceFileW(v10, v4, 0, 0, 0, 0) )
        {
          FileW = 0;
LABEL_50:
          if ( v2 )
            EfsFreeHeap(v2);
          v6 = 1;
          if ( FileW )
            CloseHandle(FileW);
          goto LABEL_6;
        }
        v27 = GetLastError();
        StoreFilePath = v27;
        if ( v27 > 0 )
          StoreFilePath = (unsigned __int16)v27 | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, StoreFilePath, 34, 232);
      }
    }
  }
LABEL_6:
  DeleteFileW(v4);
  if ( !v6 )
    DeleteFileW(v10);
  if ( v10 )
    EfsFreeHeap(v10);
  if ( v4 )
    EfsFreeHeap(v4);
  return StoreFilePath;
}

```

## disassembly

```asm
0x1800443ec  mov     [rsp-38h+arg_0], rbx
0x1800443f1  push    rbp
0x1800443f2  push    rsi
0x1800443f3  push    rdi
0x1800443f4  push    r12
0x1800443f6  push    r13
0x1800443f8  push    r14
0x1800443fa  push    r15
0x1800443fc  mov     rbp, rsp
0x1800443ff  sub     rsp, 50h
0x180044403  xor     esi, esi
0x180044405  lea     r8, sourceString
0x18004440c  mov     r13, rdx
0x18004440f  mov     [rbp+lpBuffer], rsi
0x180044413  xor     r14d, r14d
0x180044416  mov     [rbp+lpFileName], rsi
0x18004441a  mov     r12d, 362h
0x180044420  mov     [rbp+lpReplacementFileName], r14
0x180044424  lea     r9d, [rsi+22h]
0x180044428  mov     [rsp+50h+dwCreationDisposition], r12d
0x18004442d  lea     rdx, EFS_TRACE_START_EVENT
0x180044434  mov     rdi, rcx
0x180044437  mov     r15b, 1
0x18004443a  call    fnEfsLogTrace1Strings
0x18004443f  lea     r9, [rbp+lpFileName]
0x180044443  xor     r8d, r8d
0x180044446  xor     edx, edx
0x180044448  mov     rcx, rdi
0x18004444b  call    GetStoreFilePath
0x180044450  mov     rcx, cs:g_hPublisher
0x180044457  lea     r9, sourceString
0x18004445e  mov     dword ptr [rsp+50h+hTemplateFile], r12d
0x180044463  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18004446a  mov     [rsp+50h+dwFlagsAndAttributes], 22h ; '"'
0x180044472  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180044479  mov     [rsp+50h+dwCreationDisposition], eax
0x18004447d  mov     ebx, eax
0x18004447f  call    fnEfsLogTrace1String1Dword
0x180044484  mov     r12, [rbp+lpFileName]
0x180044488  test    eax, eax
0x18004448a  js      short loc_18004450A
0x18004448c  mov     r14d, 367h
0x180044492  lea     r9d, [rsi+22h]
0x180044496  lea     r8, sourceString
0x18004449d  mov     [rsp+50h+dwCreationDisposition], r14d
0x1800444a2  lea     rdx, EFS_TRACE_START_EVENT
0x1800444a9  call    fnEfsLogTrace1Strings
0x1800444ae  lea     r9, [rbp+lpReplacementFileName]
0x1800444b2  xor     r8d, r8d
0x1800444b5  mov     dl, r15b
0x1800444b8  mov     rcx, rdi
0x1800444bb  call    GetStoreFilePath
0x1800444c0  mov     rcx, cs:g_hPublisher
0x1800444c7  lea     r9, sourceString
0x1800444ce  mov     dword ptr [rsp+50h+hTemplateFile], r14d
0x1800444d3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800444da  mov     [rsp+50h+dwFlagsAndAttributes], 22h ; '"'
0x1800444e2  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800444e9  mov     [rsp+50h+dwCreationDisposition], eax
0x1800444ed  mov     ebx, eax
0x1800444ef  call    fnEfsLogTrace1String1Dword
0x1800444f4  test    eax, eax
0x1800444f6  js      short loc_180044506
0x1800444f8  test    r13, r13
0x1800444fb  jnz     short loc_180044555
0x1800444fd  mov     rcx, r12; lpFileName
0x180044500  call    cs:__imp_DeleteFileW
0x180044506  mov     r14, [rbp+lpReplacementFileName]
0x18004450a  mov     rcx, r14; lpFileName
0x18004450d  call    cs:__imp_DeleteFileW
0x180044513  test    r15b, r15b
0x180044516  jnz     short loc_180044521
0x180044518  mov     rcx, r12; lpFileName
0x18004451b  call    cs:__imp_DeleteFileW
0x180044521  test    r12, r12
0x180044524  jz      short loc_18004452E
0x180044526  mov     rcx, r12; lpMem
0x180044529  call    EfsFreeHeap
0x18004452e  test    r14, r14
0x180044531  jz      short loc_18004453B
0x180044533  mov     rcx, r14; lpMem
0x180044536  call    EfsFreeHeap
0x18004453b  mov     eax, ebx
0x18004453d  mov     rbx, [rsp+50h+arg_0]
0x180044545  add     rsp, 50h
0x180044549  pop     r15
0x18004454b  pop     r14
0x18004454d  pop     r13
0x18004454f  pop     r12
0x180044551  pop     rdi
0x180044552  pop     rsi
0x180044553  pop     rbp
0x180044554  retn
0x180044555  mov     r14, [rbp+lpReplacementFileName]
0x180044559  xor     r9d, r9d; lpSecurityAttributes
0x18004455c  mov     [rsp+50h+hTemplateFile], rsi; hTemplateFile
0x180044561  mov     rcx, r14; lpFileName
0x180044564  mov     [rsp+50h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x18004456c  xor     r8d, r8d; dwShareMode
0x18004456f  mov     edx, 40000000h; dwDesiredAccess
0x180044574  mov     [rsp+50h+dwCreationDisposition], 2; dwCreationDisposition
0x18004457c  call    cs:__imp_CreateFileW
0x180044582  mov     rdi, rax
0x180044585  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044589  jnz     short loc_1800445C9
0x18004458b  call    cs:__imp_GetLastError
0x180044591  mov     ebx, eax
0x180044593  test    eax, eax
0x180044595  jle     short loc_1800445A0
0x180044597  movzx   ebx, ax
0x18004459a  or      ebx, 80070000h
0x1800445a0  mov     [rsp+50h+dwCreationDisposition], 382h
0x1800445a8  mov     rcx, cs:g_hPublisher
0x1800445af  lea     rdx, EFS_TRACE_ERROR
0x1800445b6  mov     r9d, 22h ; '"'
0x1800445bc  mov     r8d, ebx
0x1800445bf  call    fnEfsLogTrace1
0x1800445c4  jmp     loc_18004450A
0x1800445c9  lea     rax, [r13+8]
0x1800445cd  mov     r15, [rax]
0x1800445d0  mov     [rbp+lpReplacementFileName], rax
0x1800445d4  cmp     r15, rax
0x1800445d7  jz      loc_180044792
0x1800445dd  mov     esi, 22h ; '"'
0x1800445e2  mov     [rsp+50h+dwCreationDisposition], 390h
0x1800445ea  mov     r9d, esi
0x1800445ed  lea     r8, sourceString
0x1800445f4  lea     rdx, EFS_TRACE_START_EVENT
0x1800445fb  call    fnEfsLogTrace1Strings
0x180044600  lea     rdx, [rbp+lpBuffer]
0x180044604  lea     rcx, [r15-30h]
0x180044608  call    CreateFEQStoreFile
0x18004460d  mov     rcx, cs:g_hPublisher
0x180044614  lea     r9, sourceString
0x18004461b  mov     dword ptr [rsp+50h+hTemplateFile], 390h
0x180044623  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18004462a  mov     [rsp+50h+dwFlagsAndAttributes], esi
0x18004462e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180044635  mov     [rsp+50h+dwCreationDisposition], eax
0x180044639  mov     ebx, eax
0x18004463b  call    fnEfsLogTrace1String1Dword
0x180044640  mov     rsi, [rbp+lpBuffer]
0x180044644  test    eax, eax
0x180044646  js      loc_180044851
0x18004464c  xor     r9d, r9d; lpNumberOfBytesWritten
0x18004464f  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180044658  mov     rdx, rsi; lpBuffer
0x18004465b  mov     rcx, rdi; hFile
0x18004465e  lea     r8d, [r9+38h]; nNumberOfBytesToWrite
0x180044662  call    cs:__imp_WriteFile
0x180044668  test    eax, eax
0x18004466a  jz      loc_180044754
0x180044670  mov     r8d, [rsi+2Ch]; nNumberOfBytesToWrite
0x180044674  test    r8d, r8d
0x180044677  jz      short loc_180044696
0x180044679  mov     rdx, [r15-18h]; lpBuffer
0x18004467d  xor     r9d, r9d; lpNumberOfBytesWritten
0x180044680  mov     rcx, rdi; hFile
0x180044683  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18004468c  call    cs:__imp_WriteFile
0x180044692  test    eax, eax
0x180044694  jz      short loc_1800446F7
0x180044696  mov     r8d, [rsi+30h]; nNumberOfBytesToWrite
0x18004469a  test    r8d, r8d
0x18004469d  jz      short loc_1800446BC
0x18004469f  mov     rdx, [r15-10h]; lpBuffer
0x1800446a3  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800446a6  mov     rcx, rdi; hFile
0x1800446a9  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800446b2  call    cs:__imp_WriteFile
0x1800446b8  test    eax, eax
0x1800446ba  jz      short loc_180044716
0x1800446bc  mov     r8d, [rsi+34h]; nNumberOfBytesToWrite
0x1800446c0  xor     r9d, r9d; lpNumberOfBytesWritten
0x1800446c3  mov     rdx, [r15-8]; lpBuffer
0x1800446c7  mov     rcx, rdi; hFile
0x1800446ca  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x1800446d3  call    cs:__imp_WriteFile
0x1800446d9  test    eax, eax
0x1800446db  jz      short loc_180044735
0x1800446dd  mov     rcx, rsi; lpMem
0x1800446e0  call    EfsFreeHeap
0x1800446e5  mov     r15, [r15]
0x1800446e8  xor     esi, esi
0x1800446ea  mov     rax, [rbp+lpReplacementFileName]
0x1800446ee  mov     [rbp+lpBuffer], rsi
0x1800446f2  jmp     loc_1800445D4
0x1800446f7  call    cs:__imp_GetLastError
0x1800446fd  mov     ebx, eax
0x1800446ff  test    eax, eax
0x180044701  jle     short loc_18004470C
0x180044703  movzx   ebx, ax
0x180044706  or      ebx, 80070000h
0x18004470c  mov     [rsp+50h+dwCreationDisposition], 3A7h
0x180044714  jmp     short loc_180044771
0x180044716  call    cs:__imp_GetLastError
0x18004471c  mov     ebx, eax
0x18004471e  test    eax, eax
0x180044720  jle     short loc_18004472B
0x180044722  movzx   ebx, ax
0x180044725  or      ebx, 80070000h
0x18004472b  mov     [rsp+50h+dwCreationDisposition], 3B3h
0x180044733  jmp     short loc_180044771
0x180044735  call    cs:__imp_GetLastError
0x18004473b  mov     ebx, eax
0x18004473d  test    eax, eax
0x18004473f  jle     short loc_18004474A
0x180044741  movzx   ebx, ax
0x180044744  or      ebx, 80070000h
0x18004474a  mov     [rsp+50h+dwCreationDisposition], 3BDh
0x180044752  jmp     short loc_180044771
0x180044754  call    cs:__imp_GetLastError
0x18004475a  mov     ebx, eax
0x18004475c  test    eax, eax
0x18004475e  jle     short loc_180044769
0x180044760  movzx   ebx, ax
0x180044763  or      ebx, 80070000h
0x180044769  mov     [rsp+50h+dwCreationDisposition], 39Ch
0x180044771  mov     rcx, cs:g_hPublisher
0x180044778  lea     rdx, EFS_TRACE_ERROR
0x18004477f  mov     r9d, 22h ; '"'
0x180044785  mov     r8d, ebx
0x180044788  call    fnEfsLogTrace1
0x18004478d  jmp     loc_180044851
0x180044792  mov     rcx, rdi; hFile
0x180044795  call    cs:__imp_FlushFileBuffers
0x18004479b  mov     rcx, rdi; hObject
0x18004479e  call    cs:__imp_CloseHandle
0x1800447a4  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x1800447ad  xor     r9d, r9d; lpSecurityAttributes
0x1800447b0  mov     [rsp+50h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800447b8  xor     r8d, r8d; dwShareMode
0x1800447bb  mov     edx, 40000000h; dwDesiredAccess
0x1800447c0  mov     [rsp+50h+dwCreationDisposition], 4; dwCreationDisposition
0x1800447c8  mov     rcx, r12; lpFileName
0x1800447cb  xor     r15b, r15b
0x1800447ce  call    cs:__imp_CreateFileW
0x1800447d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800447d8  jnz     short loc_1800447FC
0x1800447da  call    cs:__imp_GetLastError
0x1800447e0  mov     ebx, eax
0x1800447e2  test    eax, eax
0x1800447e4  jle     short loc_1800447EF
0x1800447e6  movzx   ebx, ax
0x1800447e9  or      ebx, 80070000h
0x1800447ef  mov     [rsp+50h+dwCreationDisposition], 3DBh
0x1800447f7  jmp     loc_1800445A8
0x1800447fc  mov     rcx, rax; hObject
0x1800447ff  call    cs:__imp_CloseHandle
0x180044805  xor     r9d, r9d; dwReplaceFlags
0x180044808  mov     qword ptr [rsp+50h+dwFlagsAndAttributes], 0; lpReserved
0x180044811  xor     r8d, r8d; lpBackupFileName
0x180044814  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpExclude
0x18004481d  mov     rdx, r14; lpReplacementFileName
0x180044820  mov     rcx, r12; lpReplacedFileName
0x180044823  call    cs:__imp_ReplaceFileW
0x180044829  test    eax, eax
0x18004482b  jnz     short loc_18004484F
0x18004482d  call    cs:__imp_GetLastError
0x180044833  mov     ebx, eax
0x180044835  test    eax, eax
0x180044837  jle     short loc_180044842
0x180044839  movzx   ebx, ax
0x18004483c  or      ebx, 80070000h
0x180044842  mov     [rsp+50h+dwCreationDisposition], 3E8h
0x18004484a  jmp     loc_1800445A8
0x18004484f  xor     edi, edi
0x180044851  test    rsi, rsi
0x180044854  jz      short loc_18004485E
0x180044856  mov     rcx, rsi; lpMem
0x180044859  call    EfsFreeHeap
0x18004485e  mov     r15b, 1
0x180044861  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180044865  jz      loc_18004450A
0x18004486b  test    rdi, rdi
0x18004486e  jz      loc_18004450A
0x180044874  mov     rcx, rdi; hObject
0x180044877  call    cs:__imp_CloseHandle
0x18004487d  jmp     loc_18004450A
```

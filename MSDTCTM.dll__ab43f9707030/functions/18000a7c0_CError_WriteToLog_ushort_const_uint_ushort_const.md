# CError::WriteToLog(ushort const *,uint,ushort const *,...)

- ea: `0x18000a7c0`
- end: `0x18000ab9c`
- name: `?WriteToLog@CError@@QEAAXPEBGI0ZZ`
- size: `988`
- prototype: `void(CError *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `32`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001160`
- `0x180001360`
- `0x180001420`
- `0x1800014e0`
- `0x1800015a0`
- `0x180001660`
- `0x180001720`
- `0x1800017d0`
- `0x180001880`
- `0x180001930`
- `0x1800019e0`
- `0x180001a90`
- `0x180001b40`
- `0x18000a420`
- `0x18000a580`
- `0x18000a660`
- `0x18000a710`
- `0x1800140d4`
- `0x180014198`
- `0x180014314`
- `0x180015e94`
- `0x180015f98`
- `0x180016490`
- `0x18001654c`
- `0x1800175d8`
- `0x180017d48`
- `0x180018338`
- `0x180018428`
- `0x180018518`
- `0x180018abc`
- `0x180018dbc`
- `0x18001d3c8`

## callees

- `0x180008a50`
- `0x18000a7c0`
- `0x180014898`
- `0x180016f3c`
- `0x180018ee8`
- `0x180019700`
- `0x18001cf3c`
- `0x180084e88`
- `0x180085d18`
- `0x1800889e4`
- `0x180088a30`
- `0x180089378`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aad5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b871a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aad5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b871a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a805`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a91e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a91e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab54`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ab6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aaef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000aaef`
- `ADVAPI32!DeregisterEventSource` at `0x18000aab0`
- `ADVAPI32!DeregisterEventSource` at `0x18000aab0`
- `ADVAPI32!RegisterEventSourceW` at `0x18000aa6c`
- `ADVAPI32!RegisterEventSourceW` at `0x18000aa6c`
- `ADVAPI32!ReportEventW` at `0x18000aaa7`
- `ADVAPI32!ReportEventW` at `0x18000aaa7`

## string_xrefs

- `0x18000ab35`: `This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\n`

## pseudocode

```c
void CError::WriteToLog(CError *this, unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  const unsigned __int16 *v4; // rax
  int v8; // r15d
  unsigned __int16 v9; // cx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rcx
  unsigned int v13; // r8d
  unsigned __int16 *v14; // r9
  DWORD v15; // edi
  unsigned int v16; // edx
  unsigned __int16 *v17; // r8
  DWORD v18; // r12d
  unsigned int v19; // r13d
  WORD v20; // di
  __int64 v21; // rbx
  __int64 v22; // rcx
  int ProcessLogger; // eax
  const unsigned __int16 *v24; // rdx
  int v25; // r8d
  HANDLE v26; // rbx
  __int64 v27; // rcx
  BOOL v28; // r14d
  DWORD CurrentThreadId; // edi
  DWORD CurrentProcessId; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-A8h]
  struct _EXCEPTION_POINTERS *nSize; // [rsp+28h] [rbp-A0h]
  unsigned int v33; // [rsp+60h] [rbp-68h] BYREF
  int v34; // [rsp+64h] [rbp-64h]
  __int64 v35; // [rsp+68h] [rbp-60h]
  __int64 v36; // [rsp+70h] [rbp-58h] BYREF
  LPCWSTR Strings[10]; // [rsp+78h] [rbp-50h] BYREF
  va_list va; // [rsp+F0h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = a4;
  v8 = 0;
  v34 = 0;
  if ( dword_1801536E8 )
  {
    EnterCriticalSection(&stru_1801536C0);
    v8 = 1;
    v34 = 1;
    v4 = a4;
  }
  v9 = 0;
  word_180166580 = 0;
  if ( v4 )
  {
    StringCchVPrintfW(&word_180166580, 0x3FDu, v4, va);
    word_180166D7A = 0;
    Strings[1] = 0;
    v9 = word_180166580;
  }
  if ( v9 )
    StringCchCatW(&word_180166580, 0x400u, L"\r\n");
  v10 = -1;
  do
    ++v10;
  while ( *(&word_180166580 + v10) );
  v33 = 1024 - v10;
  AppendApplicationInfo((unsigned __int16 *)v10, (unsigned int)a2, &v33);
  if ( *((_DWORD *)this + 10) )
    AppendFailfastMessage(v12, v11, &v33);
  v15 = *(_DWORD *)this;
  if ( *(_DWORD *)this )
  {
    StringCchCopyW(&Filename, 0x81u, L"\r\n*** Error Code = 0x%08x : %s");
    GetFormatString(0x3A2u, &Filename);
    word_180166472 = 0;
    FormatMessageW(0x1200u, 0, v15, 0, &word_180166472, 0x80u, 0);
    StringCchPrintfW(&word_180166D90, 0x400u, &Filename, v15, &word_180166472);
    SafeAppend(&word_180166D90, v16, v17, &v33);
  }
  if ( *(_DWORD *)this || *((_DWORD *)this + 10) )
    AppendInternalsInfo(a2, a3, v13, v14, &v33);
  AppendComsvcsFileVersion(v12, v11, &v33);
  v18 = *((_DWORD *)this + 2);
  v19 = *((unsigned __int16 *)this + 2);
  Strings[0] = &word_180166580;
  if ( v18 >> 30 < 2 )
  {
    v20 = 4;
  }
  else if ( v18 >> 30 == 2 )
  {
    v20 = 2;
  }
  else
  {
    v20 = 1;
  }
  v21 = 0;
  v35 = 0;
  v22 = 0;
  if ( g_pfnGetProcessLogger )
  {
    v36 = 0;
    ProcessLogger = g_pfnGetProcessLogger(&v36);
    v22 = 0;
    if ( ProcessLogger >= 0 )
    {
      v21 = v36;
      v35 = v36;
      v22 = v36;
    }
  }
  if ( v22 )
  {
    nSize = 0;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v21 + 24LL))(v21, v20, v19, v18, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v35 = 0;
  }
  else
  {
    v26 = RegisterEventSourceW(0, L"COM+");
    if ( v26 )
    {
      ReportEventW(v26, v20, v19, v18, 0, 1u, 0, Strings, 0);
      DeregisterEventSource(v26);
    }
  }
  v27 = 3221225472LL;
  v28 = (*((_DWORD *)this + 2) & 0xC0000000) == -1073741824;
  if ( v8 )
    LeaveCriticalSection(&stru_1801536C0);
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_DWORD *)this + 11) && (IsDebuggerPresent() || MEMORY[0x7FFE02D4]) )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      nSize = (struct _EXCEPTION_POINTERS *)a2;
      LODWORD(lpBuffer) = CurrentThreadId;
      StringCchPrintfW(
        &word_1801675A0,
        0x3FFu,
        L"This is a COM+ Failfast Break\n  Process.Thread=<%d.%d>\n  File: %s:%d\n  hr=0x%08x\r\n",
        CurrentProcessId,
        lpBuffer);
      OutputDebugStringW(L"\n#####################################################################\n");
      OutputDebugStringW(&word_1801675A0);
      OutputDebugStringW(L"#####################################################################\n");
    }
    if ( *((_DWORD *)this + 10) )
      FailFastStr((const unsigned __int16 *)v27, v24, v25, v28, *((_DWORD *)this + 11), nSize);
  }
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp+arg_18], r9
0x18000a7c5  mov     [rsp+arg_10], r8d
0x18000a7ca  mov     [rsp+arg_8], rdx
0x18000a7cf  push    rbx
0x18000a7d0  push    rsi
0x18000a7d1  push    rdi
0x18000a7d2  push    r12
0x18000a7d4  push    r13
0x18000a7d6  push    r14
0x18000a7d8  push    r15
0x18000a7da  sub     rsp, 90h
0x18000a7e1  mov     rax, r9
0x18000a7e4  mov     r12d, r8d
0x18000a7e7  mov     r13, rdx
0x18000a7ea  mov     rsi, rcx
0x18000a7ed  xor     edi, edi
0x18000a7ef  mov     r15d, edi
0x18000a7f2  mov     [rsp+0C8h+var_64], edi
0x18000a7f6  cmp     cs:dword_1801536E8, edi
0x18000a7fc  jz      short loc_18000A821
0x18000a7fe  lea     rcx, stru_1801536C0; lpCriticalSection
0x18000a805  call    cs:__imp_EnterCriticalSection
0x18000a80b  lea     r14d, [rdi+1]
0x18000a80f  mov     r15d, r14d
0x18000a812  mov     [rsp+0C8h+var_64], r14d
0x18000a817  mov     rax, [rsp+0C8h+arg_18]
0x18000a81f  jmp     short loc_18000A827
0x18000a821  mov     r14d, 1
0x18000a827  mov     ecx, edi
0x18000a829  mov     cs:word_180166580, cx
0x18000a830  lea     rbx, word_180166580
0x18000a837  test    rax, rax
0x18000a83a  jz      short loc_18000A872
0x18000a83c  mov     [rsp+0C8h+var_48], rdi
0x18000a844  lea     r9, [rsp+0C8h+arg_20]; char *
0x18000a84c  mov     r8, rax; unsigned __int16 *
0x18000a84f  mov     edx, 3FDh; unsigned __int64
0x18000a854  mov     rcx, rbx; unsigned __int16 *
0x18000a857  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000a85c  mov     cs:word_180166D7A, di
0x18000a863  mov     [rsp+0C8h+var_48], rdi
0x18000a86b  movzx   ecx, cs:word_180166580
0x18000a872  test    cx, cx
0x18000a875  jz      short loc_18000A88B
0x18000a877  lea     r8, asc_18013717C; "\r\n"
0x18000a87e  mov     edx, 400h; unsigned __int64
0x18000a883  mov     rcx, rbx; unsigned __int16 *
0x18000a886  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a88b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a88f  inc     rcx; unsigned __int16 *
0x18000a892  cmp     [rbx+rcx*2], di
0x18000a896  jnz     short loc_18000A88F
0x18000a898  mov     eax, 400h
0x18000a89d  sub     eax, ecx
0x18000a89f  mov     [rsp+0C8h+var_68], eax
0x18000a8a3  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x18000a8a8  call    ?AppendApplicationInfo@@YAXPEAGKPEAI@Z; AppendApplicationInfo(ushort *,ulong,uint *)
0x18000a8ad  cmp     [rsi+28h], edi
0x18000a8b0  jz      short loc_18000A8BC
0x18000a8b2  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x18000a8b7  call    ?AppendFailfastMessage@@YAXPEAGKPEAI@Z; AppendFailfastMessage(ushort *,ulong,uint *)
0x18000a8bc  mov     edi, [rsi]
0x18000a8be  test    edi, edi
0x18000a8c0  jz      loc_18000A95C
0x18000a8c6  lea     r8, aErrorCode0x08x; "\r\n*** Error Code = 0x%08x : %s"
0x18000a8cd  mov     edx, 81h; unsigned __int64
0x18000a8d2  lea     rcx, Filename; unsigned __int16 *
0x18000a8d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a8de  lea     rdx, Filename; unsigned __int16 *
0x18000a8e5  mov     ecx, 3A2h; unsigned int
0x18000a8ea  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x18000a8ef  xor     eax, eax
0x18000a8f1  mov     cs:word_180166472, ax
0x18000a8f8  mov     [rsp+0C8h+Arguments], rax; Arguments
0x18000a8fd  mov     [rsp+0C8h+nSize], 80h; nSize
0x18000a905  lea     rax, word_180166472
0x18000a90c  mov     [rsp+0C8h+lpBuffer], rax; lpBuffer
0x18000a911  xor     r9d, r9d; dwLanguageId
0x18000a914  mov     r8d, edi; dwMessageId
0x18000a917  xor     edx, edx; lpSource
0x18000a919  mov     ecx, 1200h; dwFlags
0x18000a91e  call    cs:__imp_FormatMessageW
0x18000a924  lea     rax, word_180166472
0x18000a92b  mov     [rsp+0C8h+lpBuffer], rax
0x18000a930  mov     r9d, edi
0x18000a933  lea     r8, Filename; unsigned __int16 *
0x18000a93a  mov     edx, 400h; unsigned __int64
0x18000a93f  lea     rcx, word_180166D90; unsigned __int16 *
0x18000a946  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a94b  lea     r9, [rsp+0C8h+var_68]; unsigned int *
0x18000a950  lea     rcx, word_180166D90; unsigned __int16 *
0x18000a957  call    ?SafeAppend@@YAXPEAGK0PEAI@Z; SafeAppend(ushort *,ulong,ushort *,uint *)
0x18000a95c  cmp     dword ptr [rsi], 0
0x18000a95f  jnz     short loc_18000A967
0x18000a961  cmp     dword ptr [rsi+28h], 0
0x18000a965  jz      short loc_18000A97C
0x18000a967  lea     rax, [rsp+0C8h+var_68]
0x18000a96c  mov     [rsp+0C8h+lpBuffer], rax; unsigned int *
0x18000a971  mov     edx, r12d; unsigned int
0x18000a974  mov     rcx, r13; unsigned __int16 *
0x18000a977  call    ?AppendInternalsInfo@@YAXPEBGIKPEAGPEAI@Z; AppendInternalsInfo(ushort const *,uint,ulong,ushort *,uint *)
0x18000a97c  lea     r8, [rsp+0C8h+var_68]; unsigned int *
0x18000a981  call    ?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z; AppendComsvcsFileVersion(ushort *,ulong,uint *)
0x18000a986  mov     r12d, [rsi+8]
0x18000a98a  movzx   r13d, word ptr [rsi+4]
0x18000a98f  mov     [rsp+0C8h+Strings], rbx
0x18000a994  mov     eax, r12d
0x18000a997  shr     eax, 1Eh
0x18000a99a  xor     r9d, r9d
0x18000a99d  test    eax, eax
0x18000a99f  jz      short loc_18000A9C2
0x18000a9a1  sub     eax, 1
0x18000a9a4  jz      short loc_18000A9C2
0x18000a9a6  sub     eax, 1
0x18000a9a9  jz      short loc_18000A9BB
0x18000a9ab  cmp     eax, 1
0x18000a9ae  jz      short loc_18000A9B6
0x18000a9b0  movzx   edi, r14w
0x18000a9b4  jmp     short loc_18000A9C7
0x18000a9b6  mov     edi, r14d
0x18000a9b9  jmp     short loc_18000A9C7
0x18000a9bb  mov     edi, 2
0x18000a9c0  jmp     short loc_18000A9C7
0x18000a9c2  mov     edi, 4
0x18000a9c7  mov     [rsp+0C8h+var_60], r9
0x18000a9cc  mov     rbx, r9
0x18000a9cf  mov     [rsp+0C8h+var_60], rbx
0x18000a9d4  mov     rcx, r9
0x18000a9d7  mov     rax, cs:?g_pfnGetProcessLogger@@3P6AJPEAX@ZEA; long (*g_pfnGetProcessLogger)(void *)
0x18000a9de  test    rax, rax
0x18000a9e1  jz      short loc_18000AA09
0x18000a9e3  mov     [rsp+0C8h+var_58], r9
0x18000a9e8  lea     rcx, [rsp+0C8h+var_58]
0x18000a9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9f2  xor     r9d, r9d
0x18000a9f5  mov     ecx, r9d
0x18000a9f8  test    eax, eax
0x18000a9fa  js      short loc_18000AA09
0x18000a9fc  mov     rbx, [rsp+0C8h+var_58]
0x18000aa01  mov     [rsp+0C8h+var_60], rbx
0x18000aa06  mov     rcx, rbx
0x18000aa09  test    rcx, rcx
0x18000aa0c  jz      short loc_18000AA63
0x18000aa0e  mov     rax, [rbx]
0x18000aa11  mov     r8d, r13d
0x18000aa14  movzx   edx, di
0x18000aa17  mov     [rsp+0C8h+var_80], r9d
0x18000aa1c  mov     [rsp+0C8h+lpRawData], r9
0x18000aa21  mov     dword ptr [rsp+0C8h+lpStrings], r14d
0x18000aa26  lea     rcx, [rsp+0C8h+Strings]
0x18000aa2b  mov     [rsp+0C8h+Arguments], rcx
0x18000aa30  mov     qword ptr [rsp+0C8h+nSize], r9
0x18000aa35  mov     dword ptr [rsp+0C8h+lpBuffer], r9d
0x18000aa3a  mov     r9d, r12d
0x18000aa3d  mov     rcx, rbx
0x18000aa40  mov     rax, [rax+18h]
0x18000aa44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa49  mov     rax, [rbx]
0x18000aa4c  mov     rcx, rbx
0x18000aa4f  mov     rax, [rax+10h]
0x18000aa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa58  mov     [rsp+0C8h+var_60], 0
0x18000aa61  jmp     short loc_18000AAB6
0x18000aa63  lea     rdx, aCom; "COM+"
0x18000aa6a  xor     ecx, ecx; lpUNCServerName
0x18000aa6c  call    cs:__imp_RegisterEventSourceW
0x18000aa72  mov     rbx, rax
0x18000aa75  xor     ecx, ecx
0x18000aa77  test    rax, rax
0x18000aa7a  jz      short loc_18000AAB6
0x18000aa7c  mov     [rsp+0C8h+lpRawData], rcx; lpRawData
0x18000aa81  lea     rax, [rsp+0C8h+Strings]
0x18000aa86  mov     [rsp+0C8h+lpStrings], rax; lpStrings
0x18000aa8b  mov     dword ptr [rsp+0C8h+Arguments], ecx; dwDataSize
0x18000aa8f  mov     word ptr [rsp+0C8h+nSize], r14w; wNumStrings
0x18000aa95  mov     [rsp+0C8h+lpBuffer], rcx; lpUserSid
0x18000aa9a  mov     r9d, r12d; dwEventID
0x18000aa9d  movzx   r8d, r13w; wCategory
0x18000aaa1  movzx   edx, di; wType
0x18000aaa4  mov     rcx, rbx; hEventLog
0x18000aaa7  call    cs:__imp_ReportEventW
0x18000aaad  mov     rcx, rbx; hEventLog
0x18000aab0  call    cs:__imp_DeregisterEventSource
0x18000aab6  mov     eax, [rsi+8]
0x18000aab9  mov     ecx, 0C0000000h
0x18000aabe  and     eax, ecx
0x18000aac0  xor     r14d, r14d
0x18000aac3  cmp     eax, ecx
0x18000aac5  setz    r14b
0x18000aac9  test    r15d, r15d
0x18000aacc  jz      short loc_18000AADB
0x18000aace  lea     rcx, stru_1801536C0; lpCriticalSection
0x18000aad5  call    cs:__imp_LeaveCriticalSection
0x18000aadb  cmp     dword ptr [rsi+28h], 0
0x18000aadf  jz      loc_18000AB89
0x18000aae5  cmp     dword ptr [rsi+2Ch], 0
0x18000aae9  jz      loc_18000AB74
0x18000aaef  call    cs:__imp_IsDebuggerPresent
0x18000aaf5  test    eax, eax
0x18000aaf7  jnz     short loc_18000AB02
0x18000aaf9  cmp     ds:7FFE02D4h, al
0x18000ab00  jz      short loc_18000AB74
0x18000ab02  mov     ebx, [rsi]
0x18000ab04  call    cs:__imp_GetCurrentThreadId
0x18000ab0a  mov     edi, eax
0x18000ab0c  call    cs:__imp_GetCurrentProcessId
0x18000ab12  mov     dword ptr [rsp+0C8h+lpStrings], ebx
0x18000ab16  mov     ecx, [rsp+0C8h+arg_10]
0x18000ab1d  mov     dword ptr [rsp+0C8h+Arguments], ecx
0x18000ab21  mov     rcx, [rsp+0C8h+arg_8]
0x18000ab29  mov     qword ptr [rsp+0C8h+nSize], rcx; struct _EXCEPTION_POINTERS *
0x18000ab2e  mov     dword ptr [rsp+0C8h+lpBuffer], edi
0x18000ab32  mov     r9d, eax
0x18000ab35  lea     r8, aThisIsAComFail; "This is a COM+ Failfast Break\n  Proces"...
0x18000ab3c  mov     edx, 3FFh; unsigned __int64
0x18000ab41  lea     rcx, word_1801675A0; unsigned __int16 *
0x18000ab48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ab4d  lea     rcx, OutputString; "\n#####################################"...
0x18000ab54  call    cs:__imp_OutputDebugStringW
0x18000ab5a  lea     rcx, word_1801675A0; lpOutputString
0x18000ab61  call    cs:__imp_OutputDebugStringW
0x18000ab67  lea     rcx, asc_18013A480; "#######################################"...
0x18000ab6e  call    cs:__imp_OutputDebugStringW
0x18000ab74  cmp     dword ptr [rsi+28h], 0
0x18000ab78  jz      short loc_18000AB89
0x18000ab7a  mov     eax, [rsi+2Ch]
0x18000ab7d  mov     dword ptr [rsp+0C8h+lpBuffer], eax; int
0x18000ab81  mov     r9d, r14d; int
0x18000ab84  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x18000ab89  add     rsp, 90h
0x18000ab90  pop     r15
0x18000ab92  pop     r14
0x18000ab94  pop     r13
0x18000ab96  pop     r12
0x18000ab98  pop     rdi
0x18000ab99  pop     rsi
0x18000ab9a  pop     rbx
0x18000ab9b  retn
0x1800b8704  push    rbp
0x1800b8706  sub     rsp, 60h
0x1800b870a  mov     rbp, rdx
0x1800b870d  cmp     dword ptr [rbp+64h], 0
0x1800b8711  jz      short loc_1800B8721
0x1800b8713  lea     rcx, stru_1801536C0; lpCriticalSection
0x1800b871a  call    cs:__imp_LeaveCriticalSection
0x1800b8720  nop
0x1800b8721  add     rsp, 60h
0x1800b8725  pop     rbp
0x1800b8726  retn
```

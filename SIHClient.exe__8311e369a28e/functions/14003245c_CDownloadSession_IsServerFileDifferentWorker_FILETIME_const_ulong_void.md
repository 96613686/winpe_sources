# CDownloadSession::IsServerFileDifferentWorker(_FILETIME const &,ulong,void *)

- ea: `0x14003245c`
- end: `0x140032563`
- name: `?IsServerFileDifferentWorker@CDownloadSession@@AEAAHAEBU_FILETIME@@KPEAX@Z`
- size: `263`
- prototype: `int(CDownloadSession *__hidden this, const struct _FILETIME *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400323a0`

## callees

- `0x1400154b4`
- `0x14003245c`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003253b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x14003253b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1400324e4`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1400324e4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14003249c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14003249c`

## pseudocode

```c
__int64 __fastcall CDownloadSession::IsServerFileDifferentWorker(
        CDownloadSession *this,
        const struct _FILETIME *a2,
        int a3,
        void *a4)
{
  unsigned int v7; // esi
  DWORD FileSize; // ebx
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-38h] BYREF

  CreationTime = 0;
  v7 = 1;
  if ( a4 != (void *)-1LL )
  {
    FileSize = GetFileSize(a4, 0);
    WUTrace(0, 0, 32, 5, 0, L"IsServerFileNewer: Local size: %lu.  Remote size: %lu");
    if ( FileSize == a3 )
    {
      if ( GetFileTime(a4, &CreationTime, 0, 0) )
      {
        WUTrace(0, 0, 32, 5, 0, L"IsServerFileNewer: Local time: %x%0x.  Remote time: %x%0x.");
        return CompareFileTime(&CreationTime, a2) != 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14003245c  push    rbx
0x14003245e  push    rbp
0x14003245f  push    rsi
0x140032460  push    rdi
0x140032461  push    r14
0x140032463  sub     rsp, 60h
0x140032467  mov     rax, cs:__security_cookie
0x14003246e  xor     rax, rsp
0x140032471  mov     [rsp+88h+var_30], rax
0x140032476  mov     qword ptr [rsp+88h+CreationTime.dwLowDateTime], 0
0x14003247f  mov     rdi, r9
0x140032482  mov     ebp, r8d
0x140032485  mov     r14, rdx
0x140032488  mov     esi, 1
0x14003248d  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x140032491  jz      loc_140032549
0x140032497  xor     edx, edx; lpFileSizeHigh
0x140032499  mov     rcx, r9; hFile
0x14003249c  call    cs:__imp_GetFileSize
0x1400324a2  mov     [rsp+88h+var_50], ebp
0x1400324a6  lea     r9d, [rsi+4]
0x1400324aa  mov     [rsp+88h+var_58], eax
0x1400324ae  lea     r8d, [rsi+1Fh]
0x1400324b2  mov     ebx, eax
0x1400324b4  xor     edx, edx
0x1400324b6  lea     rax, aIsserverfilene; "IsServerFileNewer: Local size: %lu.  Re"...
0x1400324bd  xor     ecx, ecx
0x1400324bf  mov     [rsp+88h+var_60], rax
0x1400324c4  mov     [rsp+88h+var_68], 0
0x1400324cd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400324d2  cmp     ebx, ebp
0x1400324d4  jnz     short loc_140032549
0x1400324d6  xor     r9d, r9d; lpLastWriteTime
0x1400324d9  lea     rdx, [rsp+88h+CreationTime]; lpCreationTime
0x1400324de  xor     r8d, r8d; lpLastAccessTime
0x1400324e1  mov     rcx, rdi; hFile
0x1400324e4  call    cs:__imp_GetFileTime
0x1400324ea  test    eax, eax
0x1400324ec  jz      short loc_140032549
0x1400324ee  mov     eax, [r14]
0x1400324f1  lea     r9d, [rsi+4]
0x1400324f5  mov     [rsp+88h+var_40], eax
0x1400324f9  lea     r8d, [rsi+1Fh]
0x1400324fd  mov     eax, [r14+4]
0x140032501  xor     edx, edx
0x140032503  mov     [rsp+88h+var_48], eax
0x140032507  xor     ecx, ecx
0x140032509  mov     eax, [rsp+88h+CreationTime.dwLowDateTime]
0x14003250d  mov     [rsp+88h+var_50], eax
0x140032511  mov     eax, [rsp+88h+CreationTime.dwHighDateTime]
0x140032515  mov     [rsp+88h+var_58], eax
0x140032519  lea     rax, aIsserverfilene_0; "IsServerFileNewer: Local time: %x%0x.  "...
0x140032520  mov     [rsp+88h+var_60], rax
0x140032525  mov     [rsp+88h+var_68], 0
0x14003252e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032533  mov     rdx, r14; lpFileTime2
0x140032536  lea     rcx, [rsp+88h+CreationTime]; lpFileTime1
0x14003253b  call    cs:__imp_CompareFileTime
0x140032541  xor     esi, esi
0x140032543  test    eax, eax
0x140032545  setnz   sil
0x140032549  mov     eax, esi
0x14003254b  mov     rcx, [rsp+88h+var_30]
0x140032550  xor     rcx, rsp; StackCookie
0x140032553  call    __security_check_cookie
0x140032558  add     rsp, 60h
0x14003255c  pop     r14
0x14003255e  pop     rdi
0x14003255f  pop     rsi
0x140032560  pop     rbp
0x140032561  pop     rbx
0x140032562  retn
```

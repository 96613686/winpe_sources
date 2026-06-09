# StructuredQueryLog::LogCreateParser(wchar_t const *,ushort,long,_LARGE_INTEGER const &,_LARGE_INTEGER const &)

- ea: `0x180049900`
- end: `0x180049a5d`
- name: `?LogCreateParser@StructuredQueryLog@@QEAAJPEB_WGJAEBT_LARGE_INTEGER@@1@Z`
- size: `349`
- prototype: `__int64 __usercall@<rax>(FILETIME *lpFileTime2@<rcx>, const wchar_t *@<rdx>, unsigned __int16@<r8w>, int@<r9d>, const union _LARGE_INTEGER *, const union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180049608`

## callees

- `0x180049900`
- `0x180049c30`
- `0x180059848`
- `0x180059c0c`
- `0x1800710bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049957`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800499d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049957`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800499d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004999c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049a42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004999c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049a42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a39`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004994a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049970`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004994a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180049970`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049938`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049962`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049938`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180049962`

## string_xrefs

- `0x1800499e3`: `SQCREATEPARSER LANGID=0x%04x, CATALOG=%s\n`

## pseudocode

```c
__int64 __fastcall StructuredQueryLog::LogCreateParser(
        FILETIME *lpFileTime2,
        const wchar_t *a2,
        unsigned __int16 a3,
        int a4,
        const union _LARGE_INTEGER *a5,
        const union _LARGE_INTEGER *a6)
{
  DWORD dwLowDateTime; // edi
  unsigned int v8; // r14d
  RTL_SRWLOCK *v10; // rsi
  DWORD USDWORDW; // eax
  __int64 v12; // rcx
  int LogPrintf; // ebx
  __int64 v14; // rdi
  int v15; // eax
  HANDLE hObject; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp+10h] BYREF

  FileTime1 = (FILETIME)a2;
  dwLowDateTime = lpFileTime2[1].dwLowDateTime;
  v8 = a3;
  hObject = 0;
  FileTime1 = 0;
  GetSystemTimeAsFileTime(&FileTime1);
  v10 = (RTL_SRWLOCK *)&lpFileTime2[2];
  if ( CompareFileTime(&FileTime1, lpFileTime2) > 0 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
    GetSystemTimeAsFileTime(&FileTime1);
    if ( CompareFileTime(&FileTime1, lpFileTime2) > 0 )
    {
      USDWORDW = SHRegGetUSDWORDW();
      LOBYTE(dwLowDateTime) = USDWORDW;
      v12 = *(_QWORD *)&FileTime1 + 300000000LL;
      lpFileTime2[1].dwLowDateTime = USDWORDW;
      *lpFileTime2 = (FILETIME)v12;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)&lpFileTime2[2]);
  }
  if ( (dwLowDateTime & 3) != 0 )
  {
    LogPrintf = StructuredQueryLogHandle(&hObject);
    if ( LogPrintf < 0 )
      return (unsigned int)LogPrintf;
    v14 = (__int64)hObject;
  }
  else
  {
    v14 = -1;
    LogPrintf = 1;
  }
  if ( v14 != -1 )
  {
    AcquireSRWLockExclusive(v10);
    LogPrintf = StructuredQueryLogPrintf(v14, L"SQCREATEPARSER LANGID=0x%04x, CATALOG=%s\n", v8, L"SystemIndex");
    if ( LogPrintf >= 0 )
    {
      if ( a4 < 0 )
        v15 = StructuredQueryLogPrintf(
                v14,
                L"FAILURE=0x%08x - Parser creation failed with this HRESULT.\n",
                (unsigned int)a4);
      else
        v15 = StructuredQueryLogPrintf(v14, L"SUCCESS\n");
      LogPrintf = v15;
      if ( v15 >= 0 )
        LogPrintf = StructuredQueryElapsedTime(v14, a5, a6);
    }
    CloseHandle((HANDLE)v14);
    ReleaseSRWLockExclusive(v10);
  }
  return (unsigned int)LogPrintf;
}

```

## disassembly

```asm
0x180049900  mov     rax, rsp
0x180049903  mov     [rax+18h], rbx
0x180049907  mov     [rax+20h], rbp
0x18004990b  mov     [rax+10h], rdx
0x18004990f  push    rsi
0x180049910  push    rdi
0x180049911  push    r14
0x180049913  sub     rsp, 20h
0x180049917  mov     edi, [rcx+8]
0x18004991a  mov     rbx, rcx
0x18004991d  lea     rcx, [rax+10h]; lpSystemTimeAsFileTime
0x180049921  movzx   r14d, r8w
0x180049925  mov     ebp, r9d
0x180049928  mov     qword ptr [rax+8], 0
0x180049930  mov     qword ptr [rax+10h], 0
0x180049938  call    cs:__imp_GetSystemTimeAsFileTime
0x18004993e  mov     rdx, rbx; lpFileTime2
0x180049941  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180049946  lea     rsi, [rbx+10h]
0x18004994a  call    cs:__imp_CompareFileTime
0x180049950  test    eax, eax
0x180049952  jle     short loc_1800499A2
0x180049954  mov     rcx, rsi; SRWLock
0x180049957  call    cs:__imp_AcquireSRWLockExclusive
0x18004995d  lea     rcx, [rsp+38h+FileTime1]; lpSystemTimeAsFileTime
0x180049962  call    cs:__imp_GetSystemTimeAsFileTime
0x180049968  mov     rdx, rbx; lpFileTime2
0x18004996b  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180049970  call    cs:__imp_CompareFileTime
0x180049976  test    eax, eax
0x180049978  jle     short loc_180049999
0x18004997a  call    SHRegGetUSDWORDW
0x18004997f  mov     rcx, qword ptr [rsp+38h+FileTime1.dwLowDateTime]
0x180049984  mov     edi, eax
0x180049986  add     rcx, 11E1A300h
0x18004998d  mov     [rbx+8], eax
0x180049990  mov     [rbx], ecx
0x180049992  shr     rcx, 20h
0x180049996  mov     [rbx+4], ecx
0x180049999  mov     rcx, rsi; SRWLock
0x18004999c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800499a2  test    dil, 3
0x1800499a6  jz      short loc_1800499C3
0x1800499a8  lea     rcx, [rsp+38h+hObject]
0x1800499ad  call    StructuredQueryLogHandle
0x1800499b2  mov     ebx, eax
0x1800499b4  test    eax, eax
0x1800499b6  js      loc_180049A48
0x1800499bc  mov     rdi, [rsp+38h+hObject]
0x1800499c1  jmp     short loc_1800499CA
0x1800499c3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800499c7  lea     ebx, [rdi+2]
0x1800499ca  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800499ce  jz      short loc_180049A48
0x1800499d0  mov     rcx, rsi; SRWLock
0x1800499d3  call    cs:__imp_AcquireSRWLockExclusive
0x1800499d9  mov     r8d, r14d
0x1800499dc  lea     r9, aSystemindex; "SystemIndex"
0x1800499e3  lea     rdx, aSqcreateparser; "SQCREATEPARSER LANGID=0x%04x, CATALOG=%"...
0x1800499ea  mov     rcx, rdi
0x1800499ed  call    StructuredQueryLogPrintf
0x1800499f2  mov     ebx, eax
0x1800499f4  test    eax, eax
0x1800499f6  js      short loc_180049A36
0x1800499f8  mov     rcx, rdi
0x1800499fb  test    ebp, ebp
0x1800499fd  js      short loc_180049A0D
0x1800499ff  lea     rdx, aSuccess; "SUCCESS\n"
0x180049a06  call    StructuredQueryLogPrintf
0x180049a0b  jmp     short loc_180049A1C
0x180049a0d  mov     r8d, ebp
0x180049a10  lea     rdx, aFailure0x08xPa_3; "FAILURE=0x%08x - Parser creation failed"...
0x180049a17  call    StructuredQueryLogPrintf
0x180049a1c  mov     ebx, eax
0x180049a1e  test    eax, eax
0x180049a20  js      short loc_180049A36
0x180049a22  mov     r8, [rsp+38h+arg_28]
0x180049a27  mov     rcx, rdi
0x180049a2a  mov     rdx, [rsp+38h+arg_20]
0x180049a2f  call    StructuredQueryElapsedTime
0x180049a34  mov     ebx, eax
0x180049a36  mov     rcx, rdi; hObject
0x180049a39  call    cs:__imp_CloseHandle
0x180049a3f  mov     rcx, rsi; SRWLock
0x180049a42  call    cs:__imp_ReleaseSRWLockExclusive
0x180049a48  mov     rbp, [rsp+38h+arg_18]
0x180049a4d  mov     eax, ebx
0x180049a4f  mov     rbx, [rsp+38h+arg_10]
0x180049a54  add     rsp, 20h
0x180049a58  pop     r14
0x180049a5a  pop     rdi
0x180049a5b  pop     rsi
0x180049a5c  retn
```

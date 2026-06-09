# CTrace::MakeLogFileBackUp(ushort *)

- ea: `0x18001f66c`
- end: `0x18001f8f7`
- name: `?MakeLogFileBackUp@CTrace@@AEAAJPEAG@Z`
- size: `651`
- prototype: `__int64 __fastcall(CTrace *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020fcc`

## callees

- `0x1800063b0`
- `0x18001f66c`
- `0x1800240f0`
- `0x1800240fc`
- `0x180084dfc`
- `0x1800b8420`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001f6f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001f6f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f799`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f699`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f699`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001f852`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001f852`
- `KERNEL32!MoveFileW` at `0x18001f78f`
- `KERNEL32!MoveFileW` at `0x18001f78f`

## string_xrefs

- `0x18001f7d3`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001f80f`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001f858`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001f7c7`: `MoveFile Failed, dwAttemptNum = %d`
- `0x18001f803`: `MoveFile %ls to %ls, succeeded`
- `0x18001f89b`: `MoveFile Failed`
- `0x18001f86c`: `MoveFileEx %ls to %ls succeeded`

## pseudocode

```c
__int64 __fastcall CTrace::MakeLogFileBackUp(CTrace *this, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned int i; // r14d
  signed int LastError; // eax
  __int64 v9; // [rsp+20h] [rbp-98h]
  __int64 v10; // [rsp+28h] [rbp-90h]
  __int64 v11; // [rsp+38h] [rbp-80h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-58h] BYREF

  SystemTime = 0;
  if ( GetFileAttributesW(a2) == -1 && GetLastError() == 2 )
  {
    return 0;
  }
  else
  {
    v4 = (unsigned __int16 *)operator new[](0x608u);
    if ( v4 )
    {
      v5 = (unsigned __int16 *)operator new[](0x608u);
      if ( v5 )
      {
        v3 = 0;
        GetLocalTime(&SystemTime);
        StringCbPrintfW(
          v5,
          0x304u,
          L"%1ws.%04d-%02d-%02d-%02d-%02d-%02d-%04d",
          a2,
          SystemTime.wYear,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
        for ( i = 0; i < 0x64; ++i )
        {
          LODWORD(v9) = i;
          StringCbPrintfW(v4, 0x304u, L"%1ws-%02d", v5, v9);
          if ( MoveFileW(a2, v4) )
          {
            TraceStringInline(
              14,
              3,
              L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
              530,
              L"CTrace::MakeLogFileBackUp",
              0,
              L"MoveFile %ls to %ls, succeeded",
              a2,
              v4);
            v3 = 0;
            goto LABEL_21;
          }
          LastError = GetLastError();
          if ( LastError == 5 || LastError == 32 )
            break;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          else
            v3 = LastError;
          LODWORD(v11) = i;
          LODWORD(v10) = v3;
          TraceStringInline(
            14,
            1,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            523,
            L"CTrace::MakeLogFileBackUp",
            v10,
            L"MoveFile Failed, dwAttemptNum = %d",
            v11);
        }
        if ( MoveFileExW(a2, v4, 1u) )
          TraceStringInline(
            14,
            3,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            538,
            L"CTrace::MakeLogFileBackUp",
            0,
            L"MoveFileEx %ls to %ls succeeded",
            a2,
            v4);
        else
          TraceStringInline(
            14,
            1,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            543,
            L"CTrace::MakeLogFileBackUp",
            0,
            L"MoveFile Failed");
      }
      else
      {
        v3 = -2147024882;
      }
LABEL_21:
      operator delete(v4);
      if ( v5 )
        operator delete(v5);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001f66c  push    rbx
0x18001f66e  push    rbp
0x18001f66f  push    rsi
0x18001f670  push    rdi
0x18001f671  push    r13
0x18001f673  push    r14
0x18001f675  sub     rsp, 88h
0x18001f67c  mov     rax, cs:__security_cookie
0x18001f683  xor     rax, rsp
0x18001f686  mov     [rsp+0B8h+var_48], rax
0x18001f68b  xorps   xmm0, xmm0
0x18001f68e  mov     rcx, rdx; lpFileName
0x18001f691  movups  xmmword ptr [rsp+0B8h+SystemTime.wYear], xmm0
0x18001f696  mov     rbp, rdx
0x18001f699  call    cs:__imp_GetFileAttributesW
0x18001f69f  cmp     eax, 0FFFFFFFFh
0x18001f6a2  jnz     short loc_18001F6B6
0x18001f6a4  call    cs:__imp_GetLastError
0x18001f6aa  cmp     eax, 2
0x18001f6ad  jnz     short loc_18001F6B6
0x18001f6af  xor     ebx, ebx
0x18001f6b1  jmp     loc_18001F8D8
0x18001f6b6  mov     ebx, 608h
0x18001f6bb  mov     ecx, ebx; unsigned __int64
0x18001f6bd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f6c2  mov     rdi, rax
0x18001f6c5  test    rax, rax
0x18001f6c8  jnz     short loc_18001F6D4
0x18001f6ca  mov     ebx, 8007000Eh
0x18001f6cf  jmp     loc_18001F8D8
0x18001f6d4  mov     rcx, rbx; unsigned __int64
0x18001f6d7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f6dc  mov     rsi, rax
0x18001f6df  test    rax, rax
0x18001f6e2  jnz     short loc_18001F6EE
0x18001f6e4  mov     ebx, 8007000Eh
0x18001f6e9  jmp     loc_18001F8C3
0x18001f6ee  lea     rcx, [rsp+0B8h+SystemTime]; lpSystemTime
0x18001f6f3  xor     ebx, ebx
0x18001f6f5  call    cs:__imp_GetLocalTime
0x18001f6fb  movzx   ecx, [rsp+0B8h+SystemTime.wSecond]
0x18001f700  movzx   edx, [rsp+0B8h+SystemTime.wMinute]
0x18001f705  movzx   r8d, [rsp+0B8h+SystemTime.wHour]
0x18001f70b  movzx   r9d, [rsp+0B8h+SystemTime.wDay]
0x18001f711  movzx   eax, [rsp+0B8h+SystemTime.wMilliseconds]
0x18001f716  movzx   r10d, [rsp+0B8h+SystemTime.wMonth]
0x18001f71c  movzx   r11d, [rsp+0B8h+SystemTime.wYear]
0x18001f722  mov     [rsp+0B8h+var_68], eax
0x18001f726  mov     [rsp+0B8h+var_70], ecx
0x18001f72a  mov     rcx, rsi; unsigned __int16 *
0x18001f72d  mov     dword ptr [rsp+0B8h+var_78], edx
0x18001f731  mov     edx, 304h; unsigned __int64
0x18001f736  mov     dword ptr [rsp+0B8h+var_80], r8d
0x18001f73b  lea     r8, a1ws04d02d02d02; "%1ws.%04d-%02d-%02d-%02d-%02d-%02d-%04d"
0x18001f742  mov     dword ptr [rsp+0B8h+var_88], r9d
0x18001f747  mov     r9, rbp
0x18001f74a  mov     dword ptr [rsp+0B8h+var_90], r10d
0x18001f74f  mov     dword ptr [rsp+0B8h+var_98], r11d
0x18001f754  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f759  xor     r14d, r14d
0x18001f75c  lea     r13, aCtraceMakelogf; "CTrace::MakeLogFileBackUp"
0x18001f763  cmp     r14d, 64h ; 'd'
0x18001f767  jnb     loc_18001F843
0x18001f76d  mov     r9, rsi
0x18001f770  mov     dword ptr [rsp+0B8h+var_98], r14d
0x18001f775  lea     r8, a1ws02d; "%1ws-%02d"
0x18001f77c  mov     edx, 304h; unsigned __int64
0x18001f781  mov     rcx, rdi; unsigned __int16 *
0x18001f784  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f789  mov     rdx, rdi; lpNewFileName
0x18001f78c  mov     rcx, rbp; lpExistingFileName
0x18001f78f  call    cs:__imp_MoveFileW
0x18001f795  test    eax, eax
0x18001f797  jnz     short loc_18001F7FE
0x18001f799  call    cs:__imp_GetLastError
0x18001f79f  cmp     eax, 5
0x18001f7a2  jz      loc_18001F843
0x18001f7a8  cmp     eax, 20h ; ' '
0x18001f7ab  jz      loc_18001F843
0x18001f7b1  test    eax, eax
0x18001f7b3  jg      short loc_18001F7B9
0x18001f7b5  mov     ebx, eax
0x18001f7b7  jmp     short loc_18001F7C2
0x18001f7b9  movzx   ebx, ax
0x18001f7bc  or      ebx, 80070000h
0x18001f7c2  mov     dword ptr [rsp+0B8h+var_80], r14d
0x18001f7c7  lea     rax, aMovefileFailed_0; "MoveFile Failed, dwAttemptNum = %d"
0x18001f7ce  mov     [rsp+0B8h+var_88], rax
0x18001f7d3  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001f7da  mov     edx, 1
0x18001f7df  mov     dword ptr [rsp+0B8h+var_90], ebx
0x18001f7e3  mov     r9d, 20Bh
0x18001f7e9  mov     [rsp+0B8h+var_98], r13
0x18001f7ee  lea     ecx, [rdx+0Dh]
0x18001f7f1  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f7f6  inc     r14d
0x18001f7f9  jmp     loc_18001F763
0x18001f7fe  mov     [rsp+0B8h+var_78], rdi
0x18001f803  lea     rax, aMovefileLsToLs; "MoveFile %ls to %ls, succeeded"
0x18001f80a  mov     [rsp+0B8h+var_80], rbp
0x18001f80f  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001f816  mov     [rsp+0B8h+var_88], rax
0x18001f81b  mov     edx, 3
0x18001f820  mov     [rsp+0B8h+var_90], 0
0x18001f829  mov     r9d, 212h
0x18001f82f  mov     [rsp+0B8h+var_98], r13
0x18001f834  lea     ecx, [rdx+0Bh]
0x18001f837  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f83c  xor     ebx, ebx
0x18001f83e  jmp     loc_18001F8C3
0x18001f843  mov     r14d, 1
0x18001f849  mov     rdx, rdi; lpNewFileName
0x18001f84c  mov     r8d, r14d; dwFlags
0x18001f84f  mov     rcx, rbp; lpExistingFileName
0x18001f852  call    cs:__imp_MoveFileExW
0x18001f858  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x18001f85f  lea     ecx, [r14+0Dh]
0x18001f863  test    eax, eax
0x18001f865  jz      short loc_18001F89B
0x18001f867  mov     [rsp+0B8h+var_78], rdi
0x18001f86c  lea     rax, aMovefileexLsTo; "MoveFileEx %ls to %ls succeeded"
0x18001f873  mov     [rsp+0B8h+var_80], rbp
0x18001f878  lea     edx, [rcx-0Bh]
0x18001f87b  mov     [rsp+0B8h+var_88], rax
0x18001f880  mov     r9d, 21Ah
0x18001f886  mov     [rsp+0B8h+var_90], 0
0x18001f88f  mov     [rsp+0B8h+var_98], r13
0x18001f894  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f899  jmp     short loc_18001F8C3
0x18001f89b  lea     rax, aMovefileFailed; "MoveFile Failed"
0x18001f8a2  mov     r9d, 21Fh
0x18001f8a8  mov     [rsp+0B8h+var_88], rax
0x18001f8ad  mov     edx, r14d
0x18001f8b0  mov     [rsp+0B8h+var_90], 0
0x18001f8b9  mov     [rsp+0B8h+var_98], r13
0x18001f8be  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001f8c3  mov     rcx, rdi; Block
0x18001f8c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f8cb  test    rsi, rsi
0x18001f8ce  jz      short loc_18001F8D8
0x18001f8d0  mov     rcx, rsi; Block
0x18001f8d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f8d8  mov     eax, ebx
0x18001f8da  mov     rcx, [rsp+0B8h+var_48]
0x18001f8df  xor     rcx, rsp; StackCookie
0x18001f8e2  call    __security_check_cookie
0x18001f8e7  add     rsp, 88h
0x18001f8ee  pop     r14
0x18001f8f0  pop     r13
0x18001f8f2  pop     rdi
0x18001f8f3  pop     rsi
0x18001f8f4  pop     rbp
0x18001f8f5  pop     rbx
0x18001f8f6  retn
```

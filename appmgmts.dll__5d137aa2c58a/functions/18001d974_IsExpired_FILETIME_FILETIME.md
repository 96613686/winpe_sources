# IsExpired(_FILETIME *,_FILETIME *)

- ea: `0x18001d974`
- end: `0x18001daa3`
- name: `?IsExpired@@YAHPEAU_FILETIME@@0@Z`
- size: `303`
- prototype: `_BOOL8 __fastcall(FILETIME *lpFileTime1, FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d240`

## callees

- `0x1800016d0`
- `0x18001b1a0`
- `0x18001d974`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001da75`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001da75`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d9ac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d9bb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d9ac`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001d9bb`

## pseudocode

```c
_BOOL8 __fastcall IsExpired(FILETIME *lpFileTime1, FILETIME *lpFileTime2)
{
  BOOL v4; // ebx
  int wDay; // [rsp+20h] [rbp-60h]
  __int64 v7; // [rsp+20h] [rbp-60h]
  int wYear; // [rsp+28h] [rbp-58h]
  __int64 v9; // [rsp+28h] [rbp-58h]
  int wHour; // [rsp+30h] [rbp-50h]
  __int64 v11; // [rsp+30h] [rbp-50h]
  int wMinute; // [rsp+38h] [rbp-48h]
  __int64 v13; // [rsp+38h] [rbp-48h]
  int wSecond; // [rsp+40h] [rbp-40h]
  __int64 v15; // [rsp+40h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-30h] BYREF
  struct _SYSTEMTIME v17; // [rsp+60h] [rbp-20h] BYREF

  SystemTime = 0;
  v17 = 0;
  v4 = FileTimeToSystemTime(lpFileTime1, &SystemTime);
  if ( FileTimeToSystemTime(lpFileTime2, &v17) && v4 )
  {
    if ( gDebug )
    {
      wSecond = SystemTime.wSecond;
      wMinute = SystemTime.wMinute;
      wHour = SystemTime.wHour;
      wYear = SystemTime.wYear;
      wDay = SystemTime.wDay;
      _DebugMsg(4, 0xCA5u, L"Current Time", SystemTime.wMonth, wDay, wYear, wHour, wMinute, wSecond);
      if ( gDebug )
      {
        LODWORD(v15) = v17.wSecond;
        LODWORD(v13) = v17.wMinute;
        LODWORD(v11) = v17.wHour;
        LODWORD(v9) = v17.wYear;
        LODWORD(v7) = v17.wDay;
        _DebugMsg(4, 0xCA5u, L"Expire Time", v17.wMonth, v7, v9, v11, v13, v15);
      }
    }
  }
  return CompareFileTime(lpFileTime1, lpFileTime2) > 0;
}

```

## disassembly

```asm
0x18001d974  mov     [rsp-18h+arg_10], rbx
0x18001d979  push    rbp
0x18001d97a  push    rsi
0x18001d97b  push    rdi
0x18001d97c  mov     rbp, rsp
0x18001d97f  sub     rsp, 80h
0x18001d986  mov     rax, cs:__security_cookie
0x18001d98d  xor     rax, rsp
0x18001d990  mov     [rbp+var_10], rax
0x18001d994  mov     rsi, rdx
0x18001d997  xorps   xmm0, xmm0
0x18001d99a  xorps   xmm1, xmm1
0x18001d99d  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001d9a1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18001d9a5  mov     rdi, rcx
0x18001d9a8  movups  xmmword ptr [rbp+var_20.wYear], xmm1
0x18001d9ac  call    cs:__imp_FileTimeToSystemTime
0x18001d9b2  lea     rdx, [rbp+var_20]; lpSystemTime
0x18001d9b6  mov     rcx, rsi; lpFileTime
0x18001d9b9  mov     ebx, eax
0x18001d9bb  call    cs:__imp_FileTimeToSystemTime
0x18001d9c1  test    ebx, eax
0x18001d9c3  jz      loc_18001DA6F
0x18001d9c9  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001d9d0  jz      loc_18001DA6F
0x18001d9d6  movzx   ecx, [rbp+SystemTime.wMinute]
0x18001d9da  movzx   edx, [rbp+SystemTime.wHour]
0x18001d9de  movzx   r8d, [rbp+SystemTime.wYear]
0x18001d9e3  movzx   eax, [rbp+SystemTime.wSecond]
0x18001d9e7  movzx   r10d, [rbp+SystemTime.wDay]
0x18001d9ec  movzx   r9d, [rbp+SystemTime.wMonth]
0x18001d9f1  mov     [rsp+80h+var_40], eax
0x18001d9f5  mov     dword ptr [rsp+80h+var_48], ecx
0x18001d9f9  mov     ecx, 4; unsigned int
0x18001d9fe  mov     dword ptr [rsp+80h+var_50], edx
0x18001da02  mov     edx, 0CA5h; unsigned int
0x18001da07  mov     dword ptr [rsp+80h+var_58], r8d
0x18001da0c  lea     r8, aCurrentTime; "Current Time"
0x18001da13  mov     dword ptr [rsp+80h+var_60], r10d
0x18001da18  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001da1d  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001da24  jz      short loc_18001DA6F
0x18001da26  movzx   r8d, [rbp+var_20.wMinute]
0x18001da2b  mov     edx, 0CA5h; unsigned int
0x18001da30  movzx   eax, [rbp+var_20.wSecond]
0x18001da34  mov     ecx, 4; unsigned int
0x18001da39  movzx   r10d, [rbp+var_20.wHour]
0x18001da3e  movzx   r11d, [rbp+var_20.wYear]
0x18001da43  movzx   ebx, [rbp+var_20.wDay]
0x18001da47  movzx   r9d, [rbp+var_20.wMonth]
0x18001da4c  mov     [rsp+80h+var_40], eax
0x18001da50  mov     dword ptr [rsp+80h+var_48], r8d
0x18001da55  lea     r8, aExpireTime; "Expire Time"
0x18001da5c  mov     dword ptr [rsp+80h+var_50], r10d
0x18001da61  mov     dword ptr [rsp+80h+var_58], r11d
0x18001da66  mov     dword ptr [rsp+80h+var_60], ebx
0x18001da6a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001da6f  mov     rdx, rsi; lpFileTime2
0x18001da72  mov     rcx, rdi; lpFileTime1
0x18001da75  call    cs:__imp_CompareFileTime
0x18001da7b  xor     ecx, ecx
0x18001da7d  test    eax, eax
0x18001da7f  setnle  cl
0x18001da82  mov     eax, ecx
0x18001da84  mov     rcx, [rbp+var_10]
0x18001da88  xor     rcx, rsp; StackCookie
0x18001da8b  call    __security_check_cookie
0x18001da90  mov     rbx, [rsp+80h+arg_10]
0x18001da98  add     rsp, 80h
0x18001da9f  pop     rdi
0x18001daa0  pop     rsi
0x18001daa1  pop     rbp
0x18001daa2  retn
```

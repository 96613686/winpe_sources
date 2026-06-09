# CLockScreenHistory::_GPCacheStateFromEntry

- ea: `0x1800b9450`
- end: `0x1800b95df`
- name: `CLockScreenHistory::_GPCacheStateFromEntry`
- size: `399`
- prototype: `__int64 __fastcall(CLockScreenHistory *this, CLockScreenHistory::CLockScreenHistoryEntry *, LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b9970`

## callees

- `0x18000a910`
- `0x180015580`
- `0x18002d43c`
- `0x180049de8`
- `0x180050ba0`
- `0x1800b40e0`
- `0x1800b9450`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b9580`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b9580`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b95a9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800b95a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b94a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b94eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b94a9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800b94eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLockScreenHistory::_GPCacheStateFromEntry(
        CLockScreenHistory *this,
        CLockScreenHistory::CLockScreenHistoryEntry *a2,
        LPCWCH lpString1,
        _DWORD *a4)
{
  __int64 v8; // rdx
  FILETIME FileTime1; // [rsp+30h] [rbp-D0h] BYREF
  LPCWCH lpString2; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h]
  __int64 v13; // [rsp+48h] [rbp-B8h]
  __int128 FileInformation; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+70h] [rbp-90h]
  _OWORD v17[2]; // [rsp+78h] [rbp-88h] BYREF
  int v18; // [rsp+98h] [rbp-68h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  *a4 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  v16 = 0;
  if ( GetFileAttributesExW(lpString1, GetFileExInfoStandard, &FileInformation) )
    *a4 |= 1u;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  if ( (int)StringCchCopyW(FileName, 0x104u, (const unsigned __int16 *)a2 + 289) >= 0
    && GetFileAttributesExW(FileName, GetFileExInfoStandard, v17) )
  {
    *a4 |= 2u;
  }
  lpString2 = 0;
  v12 = 0;
  v13 = 0;
  FileTime1 = 0;
  if ( (*(_BYTE *)a4 & 3) == 3 )
  {
    if ( (int)CLockScreenHistory::_EnsureCurrentUserSid(this) < 0
      || (Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2),
          v12 = -1,
          v13 = -1,
          (int)ReadSystemDataRegistryStringForUser(*(_QWORD *)this, v8, (char *)a2 + 386) < 0)
      || CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) != 2
      || (int)CLockScreenHistory::CLockScreenHistoryEntry::ReadGPImageModifiedTime(a2, *(void **)this, &FileTime1) < 0
      || CompareFileTime(&FileTime1, (const FILETIME *)&FileTime2[0].dwHighDateTime) )
    {
      *a4 |= 4u;
    }
  }
  return Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString2);
}

```

## disassembly

```asm
0x1800b9450  push    rbp
0x1800b9452  push    rbx
0x1800b9453  push    rsi
0x1800b9454  push    rdi
0x1800b9455  push    r12
0x1800b9457  push    r14
0x1800b9459  lea     rbp, [rsp-1C8h]
0x1800b9461  sub     rsp, 2C8h
0x1800b9468  mov     rax, cs:__security_cookie
0x1800b946f  xor     rax, rsp
0x1800b9472  mov     [rbp+1F0h+var_40], rax
0x1800b9479  mov     rbx, r9
0x1800b947c  mov     r14, r8
0x1800b947f  mov     rsi, rdx
0x1800b9482  mov     rdi, rcx
0x1800b9485  mov     dword ptr [r9], 0
0x1800b948c  xorps   xmm0, xmm0
0x1800b948f  xor     eax, eax
0x1800b9491  movups  [rsp+2F0h+FileInformation], xmm0
0x1800b9496  movups  xmmword ptr [rsp+2F0h+FileTime2.dwLowDateTime], xmm0
0x1800b949b  mov     [rsp+2F0h+var_280], eax
0x1800b949f  lea     r8, [rsp+2F0h+FileInformation]; lpFileInformation
0x1800b94a4  xor     edx, edx; fInfoLevelId
0x1800b94a6  mov     rcx, r14; lpFileName
0x1800b94a9  call    cs:__imp_GetFileAttributesExW
0x1800b94af  test    eax, eax
0x1800b94b1  jz      short loc_1800B94B6
0x1800b94b3  or      dword ptr [rbx], 1
0x1800b94b6  xorps   xmm0, xmm0
0x1800b94b9  xor     eax, eax
0x1800b94bb  movups  [rsp+2F0h+var_278], xmm0
0x1800b94c0  movups  [rbp+1F0h+var_268], xmm0
0x1800b94c4  mov     [rbp+1F0h+var_258], eax
0x1800b94c7  lea     r8, [rsi+242h]; unsigned __int16 *
0x1800b94ce  mov     edx, 104h; unsigned __int64
0x1800b94d3  lea     rcx, [rbp+1F0h+FileName]; unsigned __int16 *
0x1800b94d7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b94dc  test    eax, eax
0x1800b94de  js      short loc_1800B94F8
0x1800b94e0  lea     r8, [rsp+2F0h+var_278]; lpFileInformation
0x1800b94e5  xor     edx, edx; fInfoLevelId
0x1800b94e7  lea     rcx, [rbp+1F0h+FileName]; lpFileName
0x1800b94eb  call    cs:__imp_GetFileAttributesExW
0x1800b94f1  test    eax, eax
0x1800b94f3  jz      short loc_1800B94F8
0x1800b94f5  or      dword ptr [rbx], 2
0x1800b94f8  mov     [rsp+2F0h+lpString2], 0
0x1800b9501  mov     [rsp+2F0h+var_2B0], 0
0x1800b950a  mov     [rsp+2F0h+var_2A8], 0
0x1800b9513  mov     qword ptr [rsp+2F0h+FileTime1.dwLowDateTime], 0
0x1800b951c  mov     eax, [rbx]
0x1800b951e  and     eax, 3
0x1800b9521  cmp     al, 3
0x1800b9523  jnz     loc_1800B95B6
0x1800b9529  mov     rcx, rdi; this
0x1800b952c  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x1800b9531  test    eax, eax
0x1800b9533  js      short loc_1800B95B3
0x1800b9535  lea     rcx, [rsp+2F0h+lpString2]
0x1800b953a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b953f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800b9543  mov     [rsp+2F0h+var_2B0], r12
0x1800b9548  mov     [rsp+2F0h+var_2A8], r12
0x1800b954d  lea     r8, [rsi+182h]
0x1800b9554  lea     rax, [rsp+2F0h+lpString2]
0x1800b9559  mov     qword ptr [rsp+2F0h+bIgnoreCase], rax
0x1800b955e  mov     rcx, [rdi]
0x1800b9561  call    ?ReadSystemDataRegistryStringForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@PEAPEAG@Z; ReadSystemDataRegistryStringForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ushort * *)
0x1800b9566  test    eax, eax
0x1800b9568  js      short loc_1800B95B3
0x1800b956a  mov     [rsp+2F0h+bIgnoreCase], 1; bIgnoreCase
0x1800b9572  mov     r9d, r12d; cchCount2
0x1800b9575  mov     r8, [rsp+2F0h+lpString2]; lpString2
0x1800b957a  mov     edx, r12d; cchCount1
0x1800b957d  mov     rcx, r14; lpString1
0x1800b9580  call    cs:__imp_CompareStringOrdinal
0x1800b9586  cmp     eax, 2
0x1800b9589  jnz     short loc_1800B95B3
0x1800b958b  lea     r8, [rsp+2F0h+FileTime1]; struct _FILETIME *
0x1800b9590  mov     rdx, [rdi]; void *
0x1800b9593  mov     rcx, rsi; this
0x1800b9596  call    ?ReadGPImageModifiedTime@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAXPEAU_FILETIME@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::ReadGPImageModifiedTime(void *,_FILETIME *)
0x1800b959b  test    eax, eax
0x1800b959d  js      short loc_1800B95B3
0x1800b959f  lea     rdx, [rsp+2F0h+FileTime2.dwHighDateTime]; lpFileTime2
0x1800b95a4  lea     rcx, [rsp+2F0h+FileTime1]; lpFileTime1
0x1800b95a9  call    cs:__imp_CompareFileTime
0x1800b95af  test    eax, eax
0x1800b95b1  jz      short loc_1800B95B6
0x1800b95b3  or      dword ptr [rbx], 4
0x1800b95b6  lea     rcx, [rsp+2F0h+lpString2]
0x1800b95bb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800b95c0  mov     rcx, [rbp+1F0h+var_40]
0x1800b95c7  xor     rcx, rsp; StackCookie
0x1800b95ca  call    __security_check_cookie
0x1800b95cf  add     rsp, 2C8h
0x1800b95d6  pop     r14
0x1800b95d8  pop     r12
0x1800b95da  pop     rdi
0x1800b95db  pop     rsi
0x1800b95dc  pop     rbx
0x1800b95dd  pop     rbp
0x1800b95de  retn
```

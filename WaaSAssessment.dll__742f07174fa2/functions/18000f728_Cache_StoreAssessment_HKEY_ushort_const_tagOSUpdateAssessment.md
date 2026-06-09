# Cache::StoreAssessment(HKEY__ *,ushort const *,tagOSUpdateAssessment &)

- ea: `0x18000f728`
- end: `0x18000f8e1`
- name: `?StoreAssessment@Cache@@SAJPEAUHKEY__@@PEBGAEAUtagOSUpdateAssessment@@@Z`
- size: `441`
- prototype: `static int(HKEY, const unsigned __int16 *, struct tagOSUpdateAssessment *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800089d0`

## callees

- `0x18000f728`
- `0x18001752c`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f7bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f80c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f838`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f861`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f88a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f7bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f80c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f838`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f861`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000f88a`

## string_xrefs

- `0x18000f79e`: `OSUpdateAssessment`
- `0x18000f8a6`: `Cache::StoreAssessment Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall Cache::StoreAssessment(HKEY a1, const unsigned __int16 *a2, struct tagOSUpdateAssessment *a3)
{
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  int v9; // ebx
  bool v10; // sf
  FILETIME Data; // [rsp+30h] [rbp-88h] BYREF
  _OWORD lpData[3]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v14; // [rsp+70h] [rbp-48h]
  __int64 v15; // [rsp+78h] [rbp-40h]
  __int64 v16; // [rsp+80h] [rbp-38h]
  __int64 v17; // [rsp+88h] [rbp-30h]

  v4 = *(_OWORD *)&a3->assessmentForUpToDate.status;
  lpData[0] = *(_OWORD *)&a3->isEndOfSupport;
  v5 = *(_OWORD *)&a3->assessmentTime.dwLowDateTime;
  lpData[1] = v4;
  v7 = *(_OWORD *)&a3->currentOSBuild;
  lpData[2] = v5;
  v8 = *(_OWORD *)&a3->upToDateOSBuild;
  v15 = *((_QWORD *)&v7 + 1);
  v17 = *((_QWORD *)&v8 + 1);
  v16 = 0;
  v14 = 0;
  v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, a2, L"OSUpdateAssessment", 3u, lpData, 0x50u);
  if ( !v9 )
  {
    Data = a3->releaseInfoTime;
    v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, a2, L"ReleaseInfoTime", 0xBu, &Data, 8u);
    if ( !v9 )
    {
      v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, a2, L"UpToDateStatus", 4u, &a3->assessmentForUpToDate, 4u);
      if ( !v9 )
      {
        v9 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, a2, L"UpToDateImpact", 4u, &a3->assessmentForUpToDate.impact, 4u);
        if ( !v9 )
          v9 = RegSetKeyValueW(
                 HKEY_LOCAL_MACHINE,
                 a2,
                 L"UpToDateDays",
                 4u,
                 &a3->assessmentForUpToDate.daysOutOfDate,
                 4u);
      }
    }
  }
  v10 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v10 = v9 < 0;
  }
  if ( v10 )
    LogLevel(2u, L"Cache::StoreAssessment Failure: 0x%x", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f728  mov     r11, rsp
0x18000f72b  mov     [r11+8], rbx
0x18000f72f  mov     [r11+20h], rbp
0x18000f733  push    rsi
0x18000f734  push    rdi
0x18000f735  push    r14
0x18000f737  sub     rsp, 0A0h
0x18000f73e  mov     rax, cs:__security_cookie
0x18000f745  xor     rax, rsp
0x18000f748  mov     [rsp+0B8h+var_28], rax
0x18000f750  movups  xmm0, xmmword ptr [r8]
0x18000f754  mov     rdi, r8
0x18000f757  lea     rax, [r11-78h]
0x18000f75b  movups  xmm1, xmmword ptr [r8+10h]
0x18000f760  mov     r14, 0FFFFFFFF80000002h
0x18000f767  mov     [rsp+0B8h+cbData], 50h ; 'P'; cbData
0x18000f76f  movaps  [rsp+0B8h+var_78], xmm0
0x18000f774  mov     r9d, 3; dwType
0x18000f77a  movups  xmm0, xmmword ptr [r8+20h]
0x18000f77f  mov     rcx, r14; hKey
0x18000f782  mov     rsi, rdx
0x18000f785  movaps  [rsp+0B8h+var_68], xmm1
0x18000f78a  movups  xmm1, xmmword ptr [r8+30h]
0x18000f78f  mov     [rsp+0B8h+lpData], rax; lpData
0x18000f794  movaps  [rsp+0B8h+var_58], xmm0
0x18000f799  movups  xmm0, xmmword ptr [r8+40h]
0x18000f79e  lea     r8, aOsupdateassess; "OSUpdateAssessment"
0x18000f7a5  movaps  [rsp+0B8h+var_48], xmm1
0x18000f7aa  movaps  xmmword ptr [r11-38h], xmm0
0x18000f7af  mov     qword ptr [r11-38h], 0
0x18000f7b7  mov     qword ptr [r11-48h], 0
0x18000f7bf  call    cs:__imp_RegSetKeyValueW
0x18000f7c5  mov     ebx, eax
0x18000f7c7  test    eax, eax
0x18000f7c9  jnz     loc_18000F892
0x18000f7cf  mov     rax, [rdi+28h]
0x18000f7d3  lea     r9d, [rbx+0Bh]; dwType
0x18000f7d7  mov     dword ptr [rsp+0B8h+Data], eax
0x18000f7db  lea     r8, aReleaseinfotim; "ReleaseInfoTime"
0x18000f7e2  shr     rax, 20h
0x18000f7e6  mov     rdx, rsi; lpSubKey
0x18000f7e9  mov     dword ptr [rsp+0B8h+Data+4], eax
0x18000f7ed  mov     rcx, r14; hKey
0x18000f7f0  mov     rax, [rsp+0B8h+Data]
0x18000f7f5  mov     [rsp+0B8h+Data], rax
0x18000f7fa  lea     rax, [rsp+0B8h+Data]
0x18000f7ff  mov     [rsp+0B8h+cbData], 8; cbData
0x18000f807  mov     [rsp+0B8h+lpData], rax; lpData
0x18000f80c  call    cs:__imp_RegSetKeyValueW
0x18000f812  mov     ebx, eax
0x18000f814  test    eax, eax
0x18000f816  jnz     short loc_18000F892
0x18000f818  lea     ebp, [rbx+4]
0x18000f81b  mov     rdx, rsi; lpSubKey
0x18000f81e  lea     rax, [rdi+10h]
0x18000f822  mov     [rsp+0B8h+cbData], ebp; cbData
0x18000f826  mov     r9d, ebp; dwType
0x18000f829  mov     [rsp+0B8h+lpData], rax; lpData
0x18000f82e  lea     r8, aUptodatestatus; "UpToDateStatus"
0x18000f835  mov     rcx, r14; hKey
0x18000f838  call    cs:__imp_RegSetKeyValueW
0x18000f83e  mov     ebx, eax
0x18000f840  test    eax, eax
0x18000f842  jnz     short loc_18000F892
0x18000f844  lea     rax, [rdi+14h]
0x18000f848  mov     [rsp+0B8h+cbData], ebp; cbData
0x18000f84c  mov     r9d, ebp; dwType
0x18000f84f  mov     [rsp+0B8h+lpData], rax; lpData
0x18000f854  lea     r8, aUptodateimpact; "UpToDateImpact"
0x18000f85b  mov     rdx, rsi; lpSubKey
0x18000f85e  mov     rcx, r14; hKey
0x18000f861  call    cs:__imp_RegSetKeyValueW
0x18000f867  mov     ebx, eax
0x18000f869  test    eax, eax
0x18000f86b  jnz     short loc_18000F892
0x18000f86d  lea     rax, [rdi+18h]
0x18000f871  mov     [rsp+0B8h+cbData], ebp; cbData
0x18000f875  mov     r9d, ebp; dwType
0x18000f878  mov     [rsp+0B8h+lpData], rax; lpData
0x18000f87d  lea     r8, aUptodatedays; "UpToDateDays"
0x18000f884  mov     rdx, rsi; lpSubKey
0x18000f887  mov     rcx, r14; hKey
0x18000f88a  call    cs:__imp_RegSetKeyValueW
0x18000f890  mov     ebx, eax
0x18000f892  test    ebx, ebx
0x18000f894  jle     short loc_18000F8A1
0x18000f896  movzx   ebx, bx
0x18000f899  or      ebx, 80070000h
0x18000f89f  test    ebx, ebx
0x18000f8a1  jns     short loc_18000F8B7
0x18000f8a3  mov     r8d, ebx
0x18000f8a6  lea     rdx, aCacheStoreasse; "Cache::StoreAssessment Failure: 0x%x"
0x18000f8ad  mov     ecx, 2; unsigned __int8
0x18000f8b2  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000f8b7  mov     eax, ebx
0x18000f8b9  mov     rcx, [rsp+0B8h+var_28]
0x18000f8c1  xor     rcx, rsp; StackCookie
0x18000f8c4  call    __security_check_cookie
0x18000f8c9  lea     r11, [rsp+0B8h+var_18]
0x18000f8d1  mov     rbx, [r11+20h]
0x18000f8d5  mov     rbp, [r11+38h]
0x18000f8d9  mov     rsp, r11
0x18000f8dc  pop     r14
0x18000f8de  pop     rdi
0x18000f8df  pop     rsi
0x18000f8e0  retn
```

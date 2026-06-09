# GetUserWorkingDirectories(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18002a1f8`
- end: `0x18002a50b`
- name: `?GetUserWorkingDirectories@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `787`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002bf50`

## callees

- `0x180002590`
- `0x18000aaf4`
- `0x18000ab14`
- `0x18000f29c`
- `0x180013890`
- `0x1800260b8`
- `0x18002a1f8`
- `0x18002dbb4`
- `0x18002e12c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a312`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a30a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a30a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a461`
- `USERENV!GetUserProfileDirectoryW` at `0x18002a345`
- `USERENV!GetUserProfileDirectoryW` at `0x18002a345`
- `WTSAPI32!WTSQueryUserToken` at `0x18002a2d8`
- `WTSAPI32!WTSQueryUserToken` at `0x18002a2d8`
- `WTSAPI32!WTSFreeMemory` at `0x18002a287`
- `WTSAPI32!WTSFreeMemory` at `0x18002a489`
- `WTSAPI32!WTSFreeMemory` at `0x18002a4bf`
- `WTSAPI32!WTSFreeMemory` at `0x18002a287`
- `WTSAPI32!WTSFreeMemory` at `0x18002a489`
- `WTSAPI32!WTSFreeMemory` at `0x18002a4bf`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002a258`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002a258`

## string_xrefs

- `0x18002a26a`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`
- `0x18002a4a3`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall GetUserWorkingDirectories(_QWORD *a1)
{
  int v2; // esi
  const char *v3; // r9
  unsigned int v4; // ebx
  DWORD v6; // r15d
  __m128i si128; // xmm6
  BOOL v8; // r13d
  void *v9; // r12
  _QWORD *v10; // rsi
  void *v11; // r14
  DWORD LastError; // ebx
  __int64 v13; // r8
  int *any_status; // rax
  __int64 v15; // rcx
  int v16; // ebx
  __int64 v17; // rdx
  const char *v18; // r9
  __int64 v19; // r8
  _OWORD *v20; // rdx
  int pCount; // [rsp+20h] [rbp-2C8h]
  DWORD cchSize; // [rsp+30h] [rbp-2B8h] BYREF
  DWORD v23; // [rsp+34h] [rbp-2B4h] BYREF
  int v24; // [rsp+38h] [rbp-2B0h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+40h] [rbp-2A8h] BYREF
  HANDLE hToken; // [rsp+48h] [rbp-2A0h] BYREF
  _BYTE v27[16]; // [rsp+58h] [rbp-290h] BYREF
  void *phToken[2]; // [rsp+68h] [rbp-280h] BYREF
  __m128i v29; // [rsp+78h] [rbp-270h]
  WCHAR ProfileDir[264]; // [rsp+90h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v2 = 0;
  v24 = 0;
  v23 = 0;
  ppSessionInfo = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &v23) )
  {
    v6 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( v6 < v23 )
    {
      hToken = 0;
      phToken[0] = &hToken;
      phToken[1] = 0;
      v29.m128i_i8[0] = 1;
      v8 = WTSQueryUserToken(ppSessionInfo[v6].SessionId, &phToken[1]);
      if ( v29.m128i_i8[0] )
      {
        v9 = phToken[1];
        v10 = phToken[0];
        v11 = *(void **)phToken[0];
        if ( (unsigned __int64)(*(_QWORD *)phToken[0] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          LastError = GetLastError();
          CloseHandle(v11);
          SetLastError(LastError);
        }
        *v10 = v9;
        v2 = v24;
      }
      if ( v8 )
      {
        cchSize = 260;
        if ( GetUserProfileDirectoryW(hToken, ProfileDir, &cchSize) )
        {
          v13 = -1;
          do
            ++v13;
          while ( ProfileDir[v13] );
          try
          {
            *(_OWORD *)phToken = 0;
            v29 = 0u;
            std::wstring::_Construct<1,unsigned short const *>(phToken, ProfileDir, v13);
            any_status = (int *)std::filesystem::_Get_any_status(v27, phToken);
            v16 = *any_status;
            v17 = (unsigned int)any_status[2];
            if ( (_DWORD)v17 && ((v16 - 1) & 0xFFFFFFF7) != 0 )
              std::filesystem::_Throw_fs_error(v15, v17, phToken);
            v2 |= 3u;
            v24 = v2;
            std::wstring::~wstring(phToken);
            if ( v16 == 3 )
            {
              *(_OWORD *)phToken = 0;
              v29 = 0;
              v19 = -1;
              do
                ++v19;
              while ( ProfileDir[v19] );
              std::wstring::_Construct<1,unsigned short const *>(phToken, ProfileDir, v19);
              v20 = (_OWORD *)a1[1];
              if ( v20 == (_OWORD *)a1[2] )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a1, v20, phToken);
              }
              else
              {
                *v20 = *(_OWORD *)phToken;
                v20[1] = v29;
                v29 = si128;
                LOWORD(phToken[0]) = 0;
                a1[1] += 32LL;
              }
              std::wstring::~wstring(phToken);
            }
          }
          catch ( ... )
          {
            return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                   retaddr,
                                   (void *)0x251,
                                   (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
                                   v18);
          }
        }
      }
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hToken);
      ++v6;
    }
    if ( (__int64)(a1[1] - *a1) >> 5 )
    {
      if ( ppSessionInfo )
        WTSFreeMemory(ppSessionInfo);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24E,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
        (const char *)0x80070490LL,
        pCount);
      if ( ppSessionInfo )
        WTSFreeMemory(ppSessionInfo);
      return 2147943568LL;
    }
  }
  else
  {
    v4 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x23B,
           (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
           v3);
    if ( ppSessionInfo )
      WTSFreeMemory(ppSessionInfo);
    return v4;
  }
}

```

## disassembly

```asm
0x18002a1f8  mov     rax, rsp
0x18002a1fb  mov     [rax+10h], rbx
0x18002a1ff  mov     [rax+18h], rsi
0x18002a203  push    rdi
0x18002a204  push    r12
0x18002a206  push    r13
0x18002a208  push    r14
0x18002a20a  push    r15
0x18002a20c  sub     rsp, 2C0h
0x18002a213  movaps  xmmword ptr [rax-38h], xmm6
0x18002a217  mov     rax, cs:__security_cookie
0x18002a21e  xor     rax, rsp
0x18002a221  mov     [rsp+2E8h+var_48], rax
0x18002a229  mov     rdi, rcx
0x18002a22c  xor     r14d, r14d
0x18002a22f  mov     esi, r14d
0x18002a232  mov     [rsp+2E8h+var_2B0], r14d
0x18002a237  mov     [rsp+2E8h+var_2B4], r14d
0x18002a23c  mov     [rsp+2E8h+ppSessionInfo], r14
0x18002a241  lea     rax, [rsp+2E8h+var_2B4]
0x18002a246  mov     qword ptr [rsp+2E8h+pCount], rax; int
0x18002a24b  lea     r9, [rsp+2E8h+ppSessionInfo]; ppSessionInfo
0x18002a250  xor     edx, edx; Reserved
0x18002a252  xor     ecx, ecx; hServer
0x18002a254  lea     r8d, [r14+1]; Version
0x18002a258  call    cs:__imp_WTSEnumerateSessionsW
0x18002a25e  test    eax, eax
0x18002a260  jnz     short loc_18002A294
0x18002a262  mov     rcx, [rsp+2E8h]; this
0x18002a26a  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002a271  mov     edx, 23Bh; void *
0x18002a276  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a27b  mov     ebx, eax
0x18002a27d  mov     rcx, [rsp+2E8h+ppSessionInfo]; pMemory
0x18002a282  test    rcx, rcx
0x18002a285  jz      short loc_18002A28D
0x18002a287  call    cs:__imp_WTSFreeMemory
0x18002a28d  mov     eax, ebx
0x18002a28f  jmp     loc_18002A4CD
0x18002a294  mov     r15d, r14d
0x18002a297  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002a29f  cmp     r15d, [rsp+2E8h+var_2B4]
0x18002a2a4  jnb     loc_18002A46F
0x18002a2aa  mov     [rsp+2E8h+hToken], r14
0x18002a2af  lea     rax, [rsp+2E8h+hToken]
0x18002a2b4  mov     [rsp+2E8h+phToken], rax
0x18002a2b9  mov     [rsp+2E8h+phToken+8], r14
0x18002a2be  mov     byte ptr [rsp+2E8h+var_270], 1
0x18002a2c3  mov     eax, r15d
0x18002a2c6  lea     r8, [rax+rax*2]
0x18002a2ca  lea     rdx, [rsp+2E8h+phToken+8]; phToken
0x18002a2cf  mov     rcx, [rsp+2E8h+ppSessionInfo]
0x18002a2d4  mov     ecx, [rcx+r8*8]; SessionId
0x18002a2d8  call    cs:__imp_WTSQueryUserToken
0x18002a2de  mov     r13d, eax
0x18002a2e1  cmp     byte ptr [rsp+2E8h+var_270], r14b
0x18002a2e6  jz      short loc_18002A322
0x18002a2e8  mov     r12, [rsp+2E8h+phToken+8]
0x18002a2ed  mov     rsi, [rsp+2E8h+phToken]
0x18002a2f2  mov     r14, [rsi]
0x18002a2f5  lea     rdx, [r14-1]
0x18002a2f9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002a2fd  ja      short loc_18002A318
0x18002a2ff  call    cs:__imp_GetLastError
0x18002a305  mov     ebx, eax
0x18002a307  mov     rcx, r14; hObject
0x18002a30a  call    cs:__imp_CloseHandle
0x18002a310  mov     ecx, ebx; dwErrCode
0x18002a312  call    cs:__imp_SetLastError
0x18002a318  mov     [rsi], r12
0x18002a31b  mov     esi, [rsp+2E8h+var_2B0]
0x18002a31f  xor     r14d, r14d
0x18002a322  test    r13d, r13d
0x18002a325  jz      loc_18002A452
0x18002a32b  mov     [rsp+2E8h+cchSize], 104h
0x18002a333  lea     r8, [rsp+2E8h+cchSize]; lpcchSize
0x18002a338  lea     rdx, [rsp+2E8h+ProfileDir]; lpProfileDir
0x18002a340  mov     rcx, [rsp+2E8h+hToken]; hToken
0x18002a345  call    cs:__imp_GetUserProfileDirectoryW
0x18002a34b  test    eax, eax
0x18002a34d  jz      loc_18002A452
0x18002a353  lea     rax, [rsp+2E8h+ProfileDir]
0x18002a35b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a35f  inc     r8
0x18002a362  cmp     [rax+r8*2], r14w
0x18002a367  jnz     short loc_18002A35F
0x18002a369  xorps   xmm0, xmm0
0x18002a36c  movups  xmmword ptr [rsp+2E8h+phToken], xmm0
0x18002a371  mov     qword ptr [rsp+2E8h+var_270], r14
0x18002a376  mov     qword ptr [rsp+2E8h+var_270+8], r14
0x18002a37e  lea     rdx, [rsp+2E8h+ProfileDir]
0x18002a386  lea     rcx, [rsp+2E8h+phToken]
0x18002a38b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a390  nop
0x18002a391  lea     rdx, [rsp+2E8h+phToken]
0x18002a396  lea     rcx, [rsp+2E8h+var_290]
0x18002a39b  call    ?_Get_any_status@filesystem@std@@YA?AU_File_status_and_error@12@AEBVpath@12@W4__std_fs_stats_flags@@@Z; std::filesystem::_Get_any_status(std::filesystem::path const &,__std_fs_stats_flags)
0x18002a3a0  mov     ebx, [rax]
0x18002a3a2  mov     edx, [rax+8]
0x18002a3a5  test    edx, edx
0x18002a3a7  jz      short loc_18002A3B7
0x18002a3a9  lea     eax, [rbx-1]
0x18002a3ac  test    eax, 0FFFFFFF7h
0x18002a3b1  jnz     loc_18002A4FF
0x18002a3b7  or      esi, 3
0x18002a3ba  mov     [rsp+2E8h+var_2B0], esi
0x18002a3be  lea     rcx, [rsp+2E8h+phToken]
0x18002a3c3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a3c8  cmp     ebx, 3
0x18002a3cb  jnz     loc_18002A452
0x18002a3d1  xorps   xmm0, xmm0
0x18002a3d4  movups  xmmword ptr [rsp+2E8h+phToken], xmm0
0x18002a3d9  xorps   xmm1, xmm1
0x18002a3dc  movdqu  [rsp+2E8h+var_270], xmm1
0x18002a3e2  lea     rax, [rsp+2E8h+ProfileDir]
0x18002a3ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a3ee  inc     r8
0x18002a3f1  cmp     [rax+r8*2], r14w
0x18002a3f6  jnz     short loc_18002A3EE
0x18002a3f8  lea     rdx, [rsp+2E8h+ProfileDir]
0x18002a400  lea     rcx, [rsp+2E8h+phToken]
0x18002a405  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a40a  nop
0x18002a40b  mov     rdx, [rdi+8]
0x18002a40f  cmp     rdx, [rdi+10h]
0x18002a413  jz      short loc_18002A439
0x18002a415  movups  xmm0, xmmword ptr [rsp+2E8h+phToken]
0x18002a41a  movups  xmmword ptr [rdx], xmm0
0x18002a41d  movups  xmm1, [rsp+2E8h+var_270]
0x18002a422  movups  xmmword ptr [rdx+10h], xmm1
0x18002a426  movdqu  [rsp+2E8h+var_270], xmm6
0x18002a42c  mov     word ptr [rsp+2E8h+phToken], r14w
0x18002a432  add     qword ptr [rdi+8], 20h ; ' '
0x18002a437  jmp     short loc_18002A447
0x18002a439  lea     r8, [rsp+2E8h+phToken]
0x18002a43e  mov     rcx, rdi
0x18002a441  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18002a446  nop
0x18002a447  lea     rcx, [rsp+2E8h+phToken]
0x18002a44c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a451  nop
0x18002a452  mov     rcx, [rsp+2E8h+hToken]; hObject
0x18002a457  lea     rax, [rcx-1]
0x18002a45b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a45f  ja      short loc_18002A467
0x18002a461  call    cs:__imp_CloseHandle
0x18002a467  inc     r15d
0x18002a46a  jmp     loc_18002A29F
0x18002a46f  mov     rax, [rdi+8]
0x18002a473  sub     rax, [rdi]
0x18002a476  sar     rax, 5
0x18002a47a  test    rax, rax
0x18002a47d  jz      short loc_18002A493
0x18002a47f  mov     rcx, [rsp+2E8h+ppSessionInfo]; pMemory
0x18002a484  test    rcx, rcx
0x18002a487  jz      short loc_18002A48F
0x18002a489  call    cs:__imp_WTSFreeMemory
0x18002a48f  xor     eax, eax
0x18002a491  jmp     short loc_18002A4CD
0x18002a493  mov     rcx, [rsp+2E8h]; this
0x18002a49b  mov     ebx, 80070490h
0x18002a4a0  mov     r9d, ebx; char *
0x18002a4a3  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18002a4aa  mov     edx, 24Eh; void *
0x18002a4af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a4b4  nop
0x18002a4b5  mov     rcx, [rsp+2E8h+ppSessionInfo]; pMemory
0x18002a4ba  test    rcx, rcx
0x18002a4bd  jz      short loc_18002A4C5
0x18002a4bf  call    cs:__imp_WTSFreeMemory
0x18002a4c5  mov     eax, ebx
0x18002a4c7  jmp     short loc_18002A4CD
0x18002a4c9  mov     eax, [rsp+2E8h+cchSize]
0x18002a4cd  mov     rcx, [rsp+2E8h+var_48]
0x18002a4d5  xor     rcx, rsp; StackCookie
0x18002a4d8  call    __security_check_cookie
0x18002a4dd  lea     r11, [rsp+2E8h+var_28]
0x18002a4e5  mov     rbx, [r11+38h]
0x18002a4e9  mov     rsi, [r11+40h]
0x18002a4ed  movaps  xmm6, xmmword ptr [r11-10h]
0x18002a4f2  mov     rsp, r11
0x18002a4f5  pop     r15
0x18002a4f7  pop     r14
0x18002a4f9  pop     r13
0x18002a4fb  pop     r12
0x18002a4fd  pop     rdi
0x18002a4fe  retn
0x18002a4ff  lea     r8, [rsp+2E8h+phToken]
0x18002a504  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
```

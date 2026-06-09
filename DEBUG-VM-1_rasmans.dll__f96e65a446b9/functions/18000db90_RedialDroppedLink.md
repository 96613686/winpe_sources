# RedialDroppedLink

- ea: `0x18000db90`
- end: `0x18000e2d2`
- name: `RedialDroppedLink`
- size: `1858`
- prototype: `void __stdcall(PVOID)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000d918`
- `0x18000da5c`
- `0x18000db90`
- `0x18000e4f0`
- `0x18000e564`
- `0x18000e5f0`
- `0x18000e650`
- `0x18005dd94`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e125`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e125`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000dfe8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000dfe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e1e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e12f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e12f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dce3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000de5a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dce3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000de5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e22c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e27e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e22c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e27e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000dd31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ddc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000dd31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ddc9`
- `USERENV!CreateEnvironmentBlock` at `0x18000e08e`
- `USERENV!CreateEnvironmentBlock` at `0x18000e08e`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e269`
- `USERENV!DestroyEnvironmentBlock` at `0x18000e269`

## pseudocode

```c
void __fastcall RedialDroppedLink(CHAR *a1)
{
  DWORD v2; // r15d
  WCHAR *v3; // r14
  void *v4; // rdi
  _WORD *v5; // r13
  struct _LIST_ENTRY *v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rax
  UINT SystemDirectoryW; // ebx
  WCHAR *v10; // rax
  struct _LIST_ENTRY *Flink; // rbx
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rax
  size_t v18; // rdi
  wchar_t *v19; // rax
  WCHAR *v20; // rsi
  struct _LIST_ENTRY *v21; // rbx
  DWORD v22; // eax
  DWORD v23; // eax
  __int16 v24; // r11
  struct _LIST_ENTRY *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  DWORD v28; // eax
  DWORD v29; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF
  __int64 v32; // [rsp+130h] [rbp+67h]
  void *TokenHandle; // [rsp+138h] [rbp+6Fh] BYREF
  LPVOID Environment; // [rsp+140h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  TokenHandle = 0;
  v2 = 0;
  Environment = 0;
  v3 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  StartupInfo.lpDesktop = L"winsta0\\default";
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v32 = StrdupAtoW(a1 + 8, 0xFDE9u);
  v4 = (void *)v32;
  if ( !v32 )
  {
    v5 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v7 = 19;
LABEL_10:
      WPP_SF_(v6[1].Flink, v7, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  v5 = (_WORD *)StrdupAtoW(a1 + 269, 0xFDE9u);
  if ( v5 )
  {
    v8 = (WCHAR *)LocalAlloc(0x40u, 0x20Au);
    v3 = v8;
    if ( !v8 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v7 = 21;
        goto LABEL_10;
      }
      goto LABEL_92;
    }
    SystemDirectoryW = GetSystemDirectoryW(v8, 0x105u);
    if ( SystemDirectoryW > 0x105 )
    {
      LocalFree(v3);
      v10 = (WCHAR *)LocalAlloc(0x40u, 2LL * SystemDirectoryW);
      v3 = v10;
      if ( !v10 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_92;
        }
        Flink = WPP_GLOBAL_Control[1].Flink;
        LastError = GetLastError();
        v13 = 22;
        goto LABEL_27;
      }
      SystemDirectoryW = GetSystemDirectoryW(v10, SystemDirectoryW);
    }
    if ( !SystemDirectoryW )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_92;
      }
      Flink = WPP_GLOBAL_Control[1].Flink;
      LastError = GetLastError();
      v13 = 23;
LABEL_27:
      WPP_SF_d(Flink, v13, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_92;
    }
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v32 + 2 * v15) );
    v16 = -1;
    do
      ++v16;
    while ( v5[v16] );
    v17 = -1;
    do
      ++v17;
    while ( v3[v17] );
    v18 = (unsigned int)(v15 + 32 + v16 + v17);
    v19 = (wchar_t *)LocalAlloc(0x40u, 2 * v18);
    v20 = v19;
    if ( !v19 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_91;
      }
      v21 = WPP_GLOBAL_Control[1].Flink;
      v22 = GetLastError();
      WPP_SF_d(v21, 24, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v22);
LABEL_90:
      v6 = WPP_GLOBAL_Control;
LABEL_91:
      v4 = (void *)v32;
      goto LABEL_92;
    }
    v23 = StringCchCopyW(v19, v18, v3);
    if ( v23 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_89;
      }
      v26 = 25;
    }
    else
    {
      v27 = -1;
      do
        ++v27;
      while ( v3[v27] != v24 );
      v20[v27] = 92;
      do
        ++v14;
      while ( v3[v14] != v24 );
      v23 = StringCchPrintfW(&v20[v14 + 1], v18 - v14 - 1, L"rasautou -r -c -f \"%s\" -e \"%s\"", v32, v5);
      if ( v23 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_89;
        }
        v26 = 26;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 27, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v20);
        }
        if ( OpenProcessToken(*(HANDLE *)a1, 0xF01FFu, &TokenHandle) )
        {
          v23 = RasImpersonateUser(TokenHandle);
          v2 = v23;
          if ( !v23 )
          {
            if ( CreateEnvironmentBlock(&Environment, TokenHandle, 0) )
            {
              if ( CreateProcessAsUserW(
                     TokenHandle,
                     0,
                     v20,
                     0,
                     0,
                     0,
                     0x428u,
                     Environment,
                     0,
                     &StartupInfo,
                     &ProcessInformation) )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    32,
                    WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids,
                    ProcessInformation.dwProcessId);
                }
              }
              else
              {
                v29 = GetLastError();
                v2 = v29;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                {
                  WPP_SF_Sd(
                    WPP_GLOBAL_Control[1].Flink,
                    31,
                    (unsigned int)WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids,
                    (_DWORD)v20,
                    v29);
                }
              }
            }
            else
            {
              v28 = GetLastError();
              v2 = v28;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 30, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v28);
              }
            }
            RasRevertToSelf();
            goto LABEL_89;
          }
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_89:
            LocalFree(v20);
            goto LABEL_90;
          }
          v26 = 29;
        }
        else
        {
          v23 = GetLastError();
          v2 = v23;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_89;
          }
          v26 = 28;
        }
      }
    }
    WPP_SF_d(v25[1].Flink, v26, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v23);
    goto LABEL_89;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v7 = 20;
    goto LABEL_10;
  }
LABEL_92:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v6 = WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    v6 = WPP_GLOBAL_Control;
  }
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    LocalFree(v4);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    LocalFree(v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( *(_QWORD *)a1 )
      CloseHandle(*(HANDLE *)a1);
    LocalFree(a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( Environment )
  {
    DestroyEnvironmentBlock(Environment);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    LocalFree(v3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 6u )
  {
    WPP_SF_d(v6[1].Flink, 33, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v2);
  }
}

```

## disassembly

```asm
0x18000db90  mov     [rsp-8+arg_18], rbx
0x18000db95  push    rbp
0x18000db96  push    rsi
0x18000db97  push    rdi
0x18000db98  push    r12
0x18000db9a  push    r13
0x18000db9c  push    r14
0x18000db9e  push    r15
0x18000dba0  lea     rbp, [rsp-27h]
0x18000dba5  sub     rsp, 0F0h
0x18000dbac  mov     r12, rcx
0x18000dbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbb6  lea     rax, WPP_GLOBAL_Control
0x18000dbbd  cmp     rcx, rax
0x18000dbc0  jz      short loc_18000DBE6
0x18000dbc2  test    dword ptr [rcx+1Ch], 2000h
0x18000dbc9  jz      short loc_18000DBE6
0x18000dbcb  cmp     byte ptr [rcx+19h], 6
0x18000dbcf  jb      short loc_18000DBE6
0x18000dbd1  mov     rcx, [rcx+10h]
0x18000dbd5  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dbdc  mov     edx, 12h
0x18000dbe1  call    WPP_SF_
0x18000dbe6  xor     esi, esi
0x18000dbe8  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18000dbec  xor     edx, edx; Val
0x18000dbee  mov     [rbp+57h+TokenHandle], rsi
0x18000dbf2  mov     r15d, esi
0x18000dbf5  mov     [rbp+57h+Environment], rsi
0x18000dbf9  mov     r14d, esi
0x18000dbfc  lea     ebx, [rsi+68h]
0x18000dbff  mov     r8d, ebx; Size
0x18000dc02  call    memset_0
0x18000dc07  xor     eax, eax
0x18000dc09  mov     [rbp+57h+StartupInfo.cb], ebx
0x18000dc0c  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18000dc10  lea     rcx, [r12+8]; lpMultiByteStr
0x18000dc15  lea     rax, aWinsta0Default; "winsta0\\default"
0x18000dc1c  xorps   xmm0, xmm0
0x18000dc1f  mov     ebx, 0FDE9h
0x18000dc24  mov     [rbp+57h+StartupInfo.lpDesktop], rax
0x18000dc28  mov     edx, ebx; CodePage
0x18000dc2a  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18000dc2e  call    StrdupAtoW
0x18000dc33  mov     [rbp+57h+arg_0], rax
0x18000dc37  mov     rdi, rax
0x18000dc3a  test    rax, rax
0x18000dc3d  jnz     short loc_18000DC8F
0x18000dc3f  mov     r13d, esi
0x18000dc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc49  lea     rbx, WPP_GLOBAL_Control
0x18000dc50  cmp     rcx, rbx
0x18000dc53  jz      loc_18000E1C4
0x18000dc59  test    dword ptr [rcx+1Ch], 2000h
0x18000dc60  jz      loc_18000E1C4
0x18000dc66  cmp     byte ptr [rcx+19h], 2
0x18000dc6a  jb      loc_18000E1C4
0x18000dc70  lea     edx, [rsi+13h]
0x18000dc73  mov     rcx, [rcx+10h]
0x18000dc77  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dc7e  call    WPP_SF_
0x18000dc83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc8a  jmp     loc_18000E1C4
0x18000dc8f  lea     rcx, [r12+10Dh]; lpMultiByteStr
0x18000dc97  mov     edx, ebx; CodePage
0x18000dc99  call    StrdupAtoW
0x18000dc9e  mov     r13, rax
0x18000dca1  test    rax, rax
0x18000dca4  jnz     short loc_18000DCD9
0x18000dca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcad  lea     rbx, WPP_GLOBAL_Control
0x18000dcb4  cmp     rcx, rbx
0x18000dcb7  jz      loc_18000E1C4
0x18000dcbd  test    dword ptr [rcx+1Ch], 2000h
0x18000dcc4  jz      loc_18000E1C4
0x18000dcca  cmp     byte ptr [rcx+19h], 2
0x18000dcce  jb      loc_18000E1C4
0x18000dcd4  lea     edx, [rax+14h]
0x18000dcd7  jmp     short loc_18000DC73
0x18000dcd9  mov     edx, 20Ah; uBytes
0x18000dcde  mov     ecx, 40h ; '@'; uFlags
0x18000dce3  call    cs:__imp_LocalAlloc
0x18000dce9  mov     r14, rax
0x18000dcec  test    rax, rax
0x18000dcef  jnz     short loc_18000DD27
0x18000dcf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf8  lea     rbx, WPP_GLOBAL_Control
0x18000dcff  cmp     rcx, rbx
0x18000dd02  jz      loc_18000E1C4
0x18000dd08  test    dword ptr [rcx+1Ch], 2000h
0x18000dd0f  jz      loc_18000E1C4
0x18000dd15  cmp     byte ptr [rcx+19h], 2
0x18000dd19  jb      loc_18000E1C4
0x18000dd1f  lea     edx, [rax+15h]
0x18000dd22  jmp     loc_18000DC73
0x18000dd27  mov     esi, 105h
0x18000dd2c  mov     rcx, r14; lpBuffer
0x18000dd2f  mov     edx, esi; uSize
0x18000dd31  call    cs:__imp_GetSystemDirectoryW
0x18000dd37  mov     ebx, eax
0x18000dd39  cmp     eax, esi
0x18000dd3b  jbe     loc_18000DDD3
0x18000dd41  mov     rcx, r14; hMem
0x18000dd44  call    cs:__imp_LocalFree
0x18000dd4a  mov     edx, ebx
0x18000dd4c  mov     ecx, 40h ; '@'; uFlags
0x18000dd51  add     rdx, rdx; uBytes
0x18000dd54  call    cs:__imp_LocalAlloc
0x18000dd5a  xor     esi, esi
0x18000dd5c  mov     r14, rax
0x18000dd5f  test    rax, rax
0x18000dd62  jnz     short loc_18000DDC4
0x18000dd64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd6b  lea     rbx, WPP_GLOBAL_Control
0x18000dd72  cmp     rcx, rbx
0x18000dd75  jz      loc_18000E1C4
0x18000dd7b  test    dword ptr [rcx+1Ch], 2000h
0x18000dd82  jz      loc_18000E1C4
0x18000dd88  cmp     byte ptr [rcx+19h], 2
0x18000dd8c  jb      loc_18000E1C4
0x18000dd92  mov     rbx, [rcx+10h]
0x18000dd96  call    cs:__imp_GetLastError
0x18000dd9c  lea     edx, [rsi+16h]
0x18000dd9f  mov     r9d, eax
0x18000dda2  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dda9  mov     rcx, rbx
0x18000ddac  call    WPP_SF_d
0x18000ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddb8  lea     rbx, WPP_GLOBAL_Control
0x18000ddbf  jmp     loc_18000E1C4
0x18000ddc4  mov     edx, ebx; uSize
0x18000ddc6  mov     rcx, rax; lpBuffer
0x18000ddc9  call    cs:__imp_GetSystemDirectoryW
0x18000ddcf  mov     ebx, eax
0x18000ddd1  jmp     short loc_18000DDD5
0x18000ddd3  xor     esi, esi
0x18000ddd5  test    ebx, ebx
0x18000ddd7  jnz     short loc_18000DE18
0x18000ddd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dde0  lea     rbx, WPP_GLOBAL_Control
0x18000dde7  cmp     rcx, rbx
0x18000ddea  jz      loc_18000E1C4
0x18000ddf0  test    dword ptr [rcx+1Ch], 2000h
0x18000ddf7  jz      loc_18000E1C4
0x18000ddfd  cmp     byte ptr [rcx+19h], 2
0x18000de01  jb      loc_18000E1C4
0x18000de07  mov     rbx, [rcx+10h]
0x18000de0b  call    cs:__imp_GetLastError
0x18000de11  mov     edx, 17h
0x18000de16  jmp     short loc_18000DD9F
0x18000de18  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000de1c  mov     r8, rbx
0x18000de1f  inc     r8
0x18000de22  cmp     [rdi+r8*2], si
0x18000de27  jnz     short loc_18000DE1F
0x18000de29  mov     rdx, rbx
0x18000de2c  inc     rdx
0x18000de2f  cmp     [r13+rdx*2+0], si
0x18000de35  jnz     short loc_18000DE2C
0x18000de37  mov     rax, rbx
0x18000de3a  inc     rax
0x18000de3d  cmp     [r14+rax*2], si
0x18000de42  jnz     short loc_18000DE3A
0x18000de44  lea     rdi, [rdx+rax]
0x18000de48  add     r8, 20h ; ' '
0x18000de4c  add     rdi, r8
0x18000de4f  mov     ecx, 40h ; '@'; uFlags
0x18000de54  mov     edi, edi
0x18000de56  lea     rdx, [rdi+rdi]; uBytes
0x18000de5a  call    cs:__imp_LocalAlloc
0x18000de60  xor     r11d, r11d
0x18000de63  mov     rsi, rax
0x18000de66  test    rax, rax
0x18000de69  jnz     short loc_18000DEC4
0x18000de6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de72  lea     rbx, WPP_GLOBAL_Control
0x18000de79  cmp     rcx, rbx
0x18000de7c  jz      loc_18000E1C0
0x18000de82  test    dword ptr [rcx+1Ch], 2000h
0x18000de89  jz      loc_18000E1C0
0x18000de8f  cmp     byte ptr [rcx+19h], 2
0x18000de93  jb      loc_18000E1C0
0x18000de99  mov     rbx, [rcx+10h]
0x18000de9d  call    cs:__imp_GetLastError
0x18000dea3  lea     edx, [rsi+18h]
0x18000dea6  mov     rcx, rbx
0x18000dea9  mov     r9d, eax
0x18000deac  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000deb3  call    WPP_SF_d
0x18000deb8  lea     rbx, WPP_GLOBAL_Control
0x18000debf  jmp     loc_18000E1B9
0x18000dec4  mov     r8, r14; pszSrc
0x18000dec7  mov     rdx, rdi; cchDest
0x18000deca  mov     rcx, rsi; pszDest
0x18000decd  call    StringCchCopyW
0x18000ded2  test    eax, eax
0x18000ded4  jz      short loc_18000DF22
0x18000ded6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dedd  lea     rbx, WPP_GLOBAL_Control
0x18000dee4  cmp     rcx, rbx
0x18000dee7  jz      loc_18000E1B0
0x18000deed  mov     edi, 2000h
0x18000def2  test    [rcx+1Ch], edi
0x18000def5  jz      loc_18000E1B0
0x18000defb  cmp     byte ptr [rcx+19h], 2
0x18000deff  jb      loc_18000E1B0
0x18000df05  mov     edx, 19h
0x18000df0a  mov     rcx, [rcx+10h]
0x18000df0e  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000df15  mov     r9d, eax
0x18000df18  call    WPP_SF_d
0x18000df1d  jmp     loc_18000E1B0
0x18000df22  mov     rax, rbx
0x18000df25  inc     rax
0x18000df28  cmp     [r14+rax*2], r11w
0x18000df2d  jnz     short loc_18000DF25
0x18000df2f  mov     word ptr [rsi+rax*2], 5Ch ; '\'
0x18000df35  inc     rbx
0x18000df38  cmp     [r14+rbx*2], r11w
0x18000df3d  jnz     short loc_18000DF35
0x18000df3f  mov     r9, [rbp+57h+arg_0]
0x18000df43  lea     r8, aRasautouRCFSES; "rasautou -r -c -f \"%s\" -e \"%s\""
0x18000df4a  sub     rdi, rbx
0x18000df4d  mov     [rsp+120h+lpThreadAttributes], r13
0x18000df52  inc     rbx
0x18000df55  lea     rdx, [rdi-1]; unsigned __int64
0x18000df59  lea     rcx, [rsi+rbx*2]; unsigned __int16 *
0x18000df5d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000df62  xor     ebx, ebx
0x18000df64  test    eax, eax
0x18000df66  jz      short loc_18000DFA0
0x18000df68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df6f  lea     rbx, WPP_GLOBAL_Control
0x18000df76  cmp     rcx, rbx
0x18000df79  jz      loc_18000E1B0
0x18000df7f  test    dword ptr [rcx+1Ch], 2000h
0x18000df86  jz      loc_18000E1B0
0x18000df8c  cmp     byte ptr [rcx+19h], 2
0x18000df90  jb      loc_18000E1B0
0x18000df96  mov     edx, 1Ah
0x18000df9b  jmp     loc_18000DF0A
0x18000dfa0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfa7  lea     rax, WPP_GLOBAL_Control
0x18000dfae  mov     edi, 2000h
0x18000dfb3  cmp     rcx, rax
0x18000dfb6  jz      short loc_18000DFDB
0x18000dfb8  test    [rcx+1Ch], edi
0x18000dfbb  jz      short loc_18000DFDB
0x18000dfbd  cmp     byte ptr [rcx+19h], 4
0x18000dfc1  jb      short loc_18000DFDB
0x18000dfc3  mov     rcx, [rcx+10h]
0x18000dfc7  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dfce  mov     edx, 1Bh
0x18000dfd3  mov     r9, rsi
0x18000dfd6  call    WPP_SF_S
0x18000dfdb  mov     rcx, [r12]; ProcessHandle
0x18000dfdf  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18000dfe3  mov     edx, 0F01FFh; DesiredAccess
0x18000dfe8  call    cs:__imp_OpenProcessToken
0x18000dfee  test    eax, eax
0x18000dff0  jnz     short loc_18000E042
0x18000dff2  call    cs:__imp_GetLastError
0x18000dff8  mov     r15d, eax
0x18000dffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e002  lea     rbx, WPP_GLOBAL_Control
0x18000e009  cmp     rcx, rbx
0x18000e00c  jz      loc_18000E1B0
0x18000e012  test    [rcx+1Ch], edi
0x18000e015  jz      loc_18000E1B0
0x18000e01b  cmp     byte ptr [rcx+19h], 2
0x18000e01f  jb      loc_18000E1B0
0x18000e025  mov     edx, 1Ch
0x18000e02a  mov     rcx, [rcx+10h]
0x18000e02e  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000e035  mov     r9d, eax
0x18000e038  call    WPP_SF_d
0x18000e03d  jmp     loc_18000E1B0
0x18000e042  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18000e046  call    RasImpersonateUser
0x18000e04b  mov     r15d, eax
0x18000e04e  test    eax, eax
0x18000e050  jz      short loc_18000E083
0x18000e052  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e059  lea     rbx, WPP_GLOBAL_Control
0x18000e060  cmp     rcx, rbx
0x18000e063  jz      loc_18000E1B0
0x18000e069  test    [rcx+1Ch], edi
0x18000e06c  jz      loc_18000E1B0
0x18000e072  cmp     byte ptr [rcx+19h], 2
0x18000e076  jb      loc_18000E1B0
0x18000e07c  mov     edx, 1Dh
0x18000e081  jmp     short loc_18000E02A
0x18000e083  mov     rdx, [rbp+57h+TokenHandle]; hToken
0x18000e087  lea     rcx, [rbp+57h+Environment]; lpEnvironment
0x18000e08b  xor     r8d, r8d; bInherit
0x18000e08e  call    cs:__imp_CreateEnvironmentBlock
0x18000e094  test    eax, eax
0x18000e096  jnz     short loc_18000E0E8
0x18000e098  call    cs:__imp_GetLastError
0x18000e09e  mov     r15d, eax
  ... truncated ...
```

# DavFsQueryDirectory

- ea: `0x180023360`
- end: `0x180023956`
- name: `DavFsQueryDirectory`
- size: `1526`
- prototype: `__int64 __fastcall(unsigned int *pvCallbackContext)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000bc5c`
- `0x18000bfe0`
- `0x18000d9e4`
- `0x180010478`
- `0x180010770`
- `0x180011360`
- `0x180023360`
- `0x180023c50`
- `0x1800297e4`
- `0x180029bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800233f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023436`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023479`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800237e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023746`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023936`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800236a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800236a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002393c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002393c`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x1800235d0`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x1800235d0`
- `KERNEL32!LocalFree` at `0x18002342b`
- `KERNEL32!LocalFree` at `0x18002346e`
- `KERNEL32!LocalFree` at `0x18002342b`
- `KERNEL32!LocalFree` at `0x18002346e`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18002389a`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18002389a`
- `WINHTTP!WinHttpSetOption` at `0x18002384c`
- `WINHTTP!WinHttpSetOption` at `0x18002384c`
- `WINHTTP!WinHttpCloseHandle` at `0x1800233e9`
- `WINHTTP!WinHttpCloseHandle` at `0x1800233e9`

## string_xrefs

- `0x1800237b1`: `DavFsQueryDirectory`

## pseudocode

```c
__int64 __fastcall DavFsQueryDirectory(unsigned int *pvCallbackContext)
{
  bool v1; // zf
  DWORD LastError; // ebx
  unsigned int v4; // eax
  void *v5; // rcx
  DWORD v6; // eax
  void *v7; // rcx
  DWORD v8; // eax
  void *v9; // rcx
  DWORD v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  WCHAR *v14; // r15
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r13d
  __int64 v18; // r12
  unsigned int v19; // eax
  _QWORD *v20; // rcx
  DWORD v21; // eax
  __int64 *v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rdi
  void *v25; // rbx
  DWORD v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  int v30; // edx
  int v31; // r8d
  int v32; // [rsp+20h] [rbp-98h]
  int v33; // [rsp+28h] [rbp-90h]
  int v34; // [rsp+30h] [rbp-88h]
  int Buffer; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+10h] BYREF
  __int64 *v37; // [rsp+D0h] [rbp+18h] BYREF
  HINTERNET hInternet; // [rsp+D8h] [rbp+20h]

  v1 = pvCallbackContext[158] == 0;
  v37 = 0;
  v36 = 0;
  hInternet = 0;
  Buffer = 1;
  if ( !v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
    LastError = 0;
    goto LABEL_6;
  }
  v14 = (WCHAR *)(*((_QWORD *)pvCallbackContext + 81) + 2LL);
  if ( *((_QWORD *)pvCallbackContext + 81) == -2 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_30;
    v16 = 11;
LABEL_29:
    WPP_SF_(v15[2], v16, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
LABEL_30:
    LastError = 87;
LABEL_91:
    v4 = DavMapErrorToNtStatus(LastError);
    goto LABEL_7;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v14);
    v15 = WPP_GLOBAL_Control;
  }
  v17 = pvCallbackContext[164];
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
  {
    WPP_SF_d(v15[2], 13, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v17);
    v15 = WPP_GLOBAL_Control;
  }
  v18 = *((_QWORD *)pvCallbackContext + 83) + 2LL;
  if ( *((_QWORD *)pvCallbackContext + 83) == -2 )
  {
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 1) == 0 )
      goto LABEL_30;
    v16 = 14;
    goto LABEL_29;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 )
    WPP_SF_S(v15[2], 15, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v18);
  DavRemoveDummyShareFromFileName(v18);
  v19 = pvCallbackContext[159];
  pvCallbackContext[128] = v19;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v19);
      v20 = WPP_GLOBAL_Control;
    }
    if ( v20 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v20 + 28) & 2) != 0 )
      {
        WPP_SF_d(v20[2], 17, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, pvCallbackContext[160]);
        v20 = WPP_GLOBAL_Control;
      }
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 2) != 0 )
        WPP_SF_d(v20[2], 18, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, pvCallbackContext[161]);
    }
  }
  v21 = UMReflectorImpersonate(pvCallbackContext, *((_QWORD *)pvCallbackContext + 9));
  LastError = v21;
  if ( !v21 )
  {
    EnterCriticalSection(&HashServerEntryTableLock);
    if ( !(unsigned int)DavDoesUserEntryExist(v14, v17, pvCallbackContext + 160, &v37, (__int64 **)&v36)
      || !v36
      || (v22 = v37) == 0 )
    {
      LastError = 1223;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids);
      LeaveCriticalSection(&HashServerEntryTableLock);
      goto LABEL_89;
    }
    *((_QWORD *)pvCallbackContext + 63) = v36;
    *((_QWORD *)pvCallbackContext + 62) = v22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v22);
    ++*((_DWORD *)v22 + 16);
    v23 = v22[5];
    v24 = v22[4];
    LeaveCriticalSection(&HashServerEntryTableLock);
    pvCallbackContext[13] = 1;
    pvCallbackContext[14] = 1;
    *((_QWORD *)pvCallbackContext + 65) = 0;
    *((_QWORD *)pvCallbackContext + 66) = 0;
    *((_QWORD *)pvCallbackContext + 67) = 0;
    *((_QWORD *)pvCallbackContext + 68) = 0;
    if ( !(unsigned int)DavHttpOpenRequestW(v24, v23, (unsigned int)L"PROPFIND", v18, v32, v33, v34, 0) )
    {
      LastError = GetLastError();
      goto LABEL_89;
    }
    v25 = hInternet;
    if ( hInternet )
    {
      if ( !g_DisableCookies || WinHttpSetOption(hInternet, 0x3Fu, &Buffer, 4u) )
      {
        *((_QWORD *)pvCallbackContext + 69) = v25;
        if ( WinHttpAddRequestHeaders(v25, L"Content-Length: 0", 0xFFFFFFFF, 0xA0000000) )
        {
          v29 = DavAsyncCommonStates(pvCallbackContext);
          LastError = v29;
          if ( v29
            && v29 != 997
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v31, v18, v29);
          }
          goto LABEL_89;
        }
        v26 = GetLastError();
        LastError = v26;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_89:
          RevertToSelf();
          goto LABEL_90;
        }
        v28 = 24;
      }
      else
      {
        v26 = GetLastError();
        LastError = v26;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_89;
        v28 = 23;
      }
    }
    else
    {
      v26 = GetLastError();
      LastError = v26;
      if ( v26 == 997 )
        goto LABEL_89;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_89;
      v28 = 22;
    }
    WPP_SF_d(v27[2], v28, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v26);
    goto LABEL_89;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v21);
    goto LABEL_91;
  }
LABEL_90:
  if ( LastError )
    goto LABEL_91;
LABEL_6:
  v4 = 0;
LABEL_7:
  pvCallbackContext[8] = v4;
  v5 = (void *)*((_QWORD *)pvCallbackContext + 69);
  if ( v5 )
  {
    if ( !WinHttpCloseHandle(v5) )
    {
      v6 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v6);
    }
  }
  v7 = (void *)*((_QWORD *)pvCallbackContext + 65);
  if ( v7 )
  {
    if ( LocalFree(v7) )
    {
      v8 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v8);
    }
  }
  v9 = (void *)*((_QWORD *)pvCallbackContext + 66);
  if ( v9 )
  {
    if ( LocalFree(v9) )
    {
      v10 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids, v10);
    }
  }
  DavFsFinalizeTheDavCallBackContext((__int64)pvCallbackContext);
  if ( *((_QWORD *)pvCallbackContext + 62) )
    DavFinalizePerUserEntry((unsigned int **)pvCallbackContext + 62, v11, v12);
  return LastError;
}

```

## disassembly

```asm
0x180023360  mov     rax, rsp
0x180023363  push    rbx
0x180023364  push    rbp
0x180023365  push    rsi
0x180023366  push    rdi
0x180023367  push    r12
0x180023369  push    r13
0x18002336b  push    r14
0x18002336d  push    r15
0x18002336f  sub     rsp, 78h
0x180023373  cmp     dword ptr [rcx+278h], 0
0x18002337a  mov     rsi, rcx
0x18002337d  mov     qword ptr [rax+18h], 0
0x180023385  mov     qword ptr [rax+10h], 0
0x18002338d  mov     qword ptr [rax+20h], 0
0x180023395  mov     dword ptr [rax+8], 1
0x18002339c  jz      loc_1800234D2
0x1800233a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800233a9  lea     rbp, WPP_GLOBAL_Control
0x1800233b0  lea     r14, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x1800233b7  cmp     rcx, rbp
0x1800233ba  jz      short loc_1800233D6
0x1800233bc  mov     dil, 2
0x1800233bf  test    [rcx+1Ch], dil
0x1800233c3  jz      short loc_1800233D6
0x1800233c5  mov     rcx, [rcx+10h]
0x1800233c9  mov     edx, 0Ah
0x1800233ce  mov     r8, r14
0x1800233d1  call    WPP_SF_
0x1800233d6  xor     ebx, ebx
0x1800233d8  xor     eax, eax
0x1800233da  mov     [rsi+20h], eax
0x1800233dd  mov     rcx, [rsi+228h]; hInternet
0x1800233e4  test    rcx, rcx
0x1800233e7  jz      short loc_18002341F
0x1800233e9  call    cs:__imp_WinHttpCloseHandle
0x1800233ef  test    eax, eax
0x1800233f1  jnz     short loc_18002341F
0x1800233f3  call    cs:__imp_GetLastError
0x1800233f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023400  cmp     rcx, rbp
0x180023403  jz      short loc_18002341F
0x180023405  test    byte ptr [rcx+1Ch], 1
0x180023409  jz      short loc_18002341F
0x18002340b  mov     rcx, [rcx+10h]
0x18002340f  mov     edx, 30h ; '0'
0x180023414  mov     r9d, eax
0x180023417  mov     r8, r14
0x18002341a  call    WPP_SF_d
0x18002341f  mov     rcx, [rsi+208h]; hMem
0x180023426  test    rcx, rcx
0x180023429  jz      short loc_180023462
0x18002342b  call    cs:__imp_LocalFree
0x180023431  test    rax, rax
0x180023434  jz      short loc_180023462
0x180023436  call    cs:__imp_GetLastError
0x18002343c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023443  cmp     rcx, rbp
0x180023446  jz      short loc_180023462
0x180023448  test    byte ptr [rcx+1Ch], 1
0x18002344c  jz      short loc_180023462
0x18002344e  mov     rcx, [rcx+10h]
0x180023452  mov     edx, 31h ; '1'
0x180023457  mov     r9d, eax
0x18002345a  mov     r8, r14
0x18002345d  call    WPP_SF_d
0x180023462  mov     rcx, [rsi+210h]; hMem
0x180023469  test    rcx, rcx
0x18002346c  jz      short loc_1800234A5
0x18002346e  call    cs:__imp_LocalFree
0x180023474  test    rax, rax
0x180023477  jz      short loc_1800234A5
0x180023479  call    cs:__imp_GetLastError
0x18002347f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023486  cmp     rcx, rbp
0x180023489  jz      short loc_1800234A5
0x18002348b  test    byte ptr [rcx+1Ch], 1
0x18002348f  jz      short loc_1800234A5
0x180023491  mov     rcx, [rcx+10h]
0x180023495  mov     edx, 32h ; '2'
0x18002349a  mov     r9d, eax
0x18002349d  mov     r8, r14
0x1800234a0  call    WPP_SF_d
0x1800234a5  mov     rcx, rsi
0x1800234a8  call    DavFsFinalizeTheDavCallBackContext
0x1800234ad  lea     rcx, [rsi+1F0h]
0x1800234b4  cmp     qword ptr [rcx], 0
0x1800234b8  jz      short loc_1800234BF
0x1800234ba  call    DavFinalizePerUserEntry
0x1800234bf  mov     eax, ebx
0x1800234c1  add     rsp, 78h
0x1800234c5  pop     r15
0x1800234c7  pop     r14
0x1800234c9  pop     r13
0x1800234cb  pop     r12
0x1800234cd  pop     rdi
0x1800234ce  pop     rsi
0x1800234cf  pop     rbp
0x1800234d0  pop     rbx
0x1800234d1  retn
0x1800234d2  mov     r15, [rcx+288h]
0x1800234d9  add     r15, 2
0x1800234dd  jnz     short loc_180023519
0x1800234df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234e6  lea     rbp, WPP_GLOBAL_Control
0x1800234ed  lea     r14, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x1800234f4  cmp     rcx, rbp
0x1800234f7  jz      short loc_18002350F
0x1800234f9  test    byte ptr [rcx+1Ch], 1
0x1800234fd  jz      short loc_18002350F
0x1800234ff  lea     edx, [r15+0Bh]
0x180023503  mov     rcx, [rcx+10h]
0x180023507  mov     r8, r14
0x18002350a  call    WPP_SF_
0x18002350f  mov     ebx, 57h ; 'W'
0x180023514  jmp     loc_18002394A
0x180023519  mov     rcx, cs:WPP_GLOBAL_Control
0x180023520  lea     rbp, WPP_GLOBAL_Control
0x180023527  lea     r14, WPP_b36fc55277b33bf64a16477ae3d2a75a_Traceguids
0x18002352e  mov     dil, 2
0x180023531  cmp     rcx, rbp
0x180023534  jz      short loc_180023557
0x180023536  test    [rcx+1Ch], dil
0x18002353a  jz      short loc_180023557
0x18002353c  mov     rcx, [rcx+10h]
0x180023540  mov     edx, 0Ch
0x180023545  mov     r9, r15
0x180023548  mov     r8, r14
0x18002354b  call    WPP_SF_S
0x180023550  mov     rcx, cs:WPP_GLOBAL_Control
0x180023557  mov     r13d, [rsi+290h]
0x18002355e  cmp     rcx, rbp
0x180023561  jz      short loc_180023584
0x180023563  test    [rcx+1Ch], dil
0x180023567  jz      short loc_180023584
0x180023569  mov     rcx, [rcx+10h]
0x18002356d  mov     edx, 0Dh
0x180023572  mov     r9d, r13d
0x180023575  mov     r8, r14
0x180023578  call    WPP_SF_d
0x18002357d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023584  mov     r12, [rsi+298h]
0x18002358b  add     r12, 2
0x18002358f  jnz     short loc_1800235AE
0x180023591  cmp     rcx, rbp
0x180023594  jz      loc_18002350F
0x18002359a  test    byte ptr [rcx+1Ch], 1
0x18002359e  jz      loc_18002350F
0x1800235a4  lea     edx, [r12+0Eh]
0x1800235a9  jmp     loc_180023503
0x1800235ae  cmp     rcx, rbp
0x1800235b1  jz      short loc_1800235CD
0x1800235b3  test    [rcx+1Ch], dil
0x1800235b7  jz      short loc_1800235CD
0x1800235b9  mov     rcx, [rcx+10h]
0x1800235bd  mov     edx, 0Fh
0x1800235c2  mov     r9, r12
0x1800235c5  mov     r8, r14
0x1800235c8  call    WPP_SF_S
0x1800235cd  mov     rcx, r12
0x1800235d0  call    cs:__imp_DavRemoveDummyShareFromFileName
0x1800235d6  mov     eax, [rsi+27Ch]
0x1800235dc  mov     [rsi+200h], eax
0x1800235e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235e9  cmp     rcx, rbp
0x1800235ec  jz      short loc_18002365C
0x1800235ee  test    [rcx+1Ch], dil
0x1800235f2  jz      short loc_18002360F
0x1800235f4  mov     rcx, [rcx+10h]
0x1800235f8  mov     edx, 10h
0x1800235fd  mov     r9d, eax
0x180023600  mov     r8, r14
0x180023603  call    WPP_SF_d
0x180023608  mov     rcx, cs:WPP_GLOBAL_Control
0x18002360f  cmp     rcx, rbp
0x180023612  jz      short loc_18002365C
0x180023614  test    [rcx+1Ch], dil
0x180023618  jz      short loc_180023639
0x18002361a  mov     r9d, [rsi+280h]
0x180023621  mov     edx, 11h
0x180023626  mov     rcx, [rcx+10h]
0x18002362a  mov     r8, r14
0x18002362d  call    WPP_SF_d
0x180023632  mov     rcx, cs:WPP_GLOBAL_Control
0x180023639  cmp     rcx, rbp
0x18002363c  jz      short loc_18002365C
0x18002363e  test    [rcx+1Ch], dil
0x180023642  jz      short loc_18002365C
0x180023644  mov     r9d, [rsi+284h]
0x18002364b  mov     edx, 12h
0x180023650  mov     rcx, [rcx+10h]
0x180023654  mov     r8, r14
0x180023657  call    WPP_SF_d
0x18002365c  mov     rdx, [rsi+48h]
0x180023660  mov     rcx, rsi
0x180023663  call    UMReflectorImpersonate
0x180023668  mov     ebx, eax
0x18002366a  test    eax, eax
0x18002366c  jz      short loc_1800236A1
0x18002366e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023675  cmp     rcx, rbp
0x180023678  jz      loc_180023942
0x18002367e  test    byte ptr [rcx+1Ch], 1
0x180023682  jz      loc_180023942
0x180023688  mov     rcx, [rcx+10h]
0x18002368c  mov     edx, 13h
0x180023691  mov     r9d, eax
0x180023694  mov     r8, r14
0x180023697  call    WPP_SF_d
0x18002369c  jmp     loc_18002394A
0x1800236a1  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x1800236a8  call    cs:__imp_EnterCriticalSection
0x1800236ae  lea     rax, [rsp+0B8h+arg_8]
0x1800236b6  mov     edx, r13d
0x1800236b9  lea     r8, [rsi+280h]
0x1800236c0  mov     [rsp+0B8h+var_98], rax; __int64
0x1800236c5  lea     r9, [rsp+0B8h+arg_10]
0x1800236cd  mov     rcx, r15; hMem
0x1800236d0  call    DavDoesUserEntryExist
0x1800236d5  test    eax, eax
0x1800236d7  jz      loc_180023907
0x1800236dd  mov     rax, [rsp+0B8h+arg_8]
0x1800236e5  test    rax, rax
0x1800236e8  jz      loc_180023907
0x1800236ee  mov     r15, [rsp+0B8h+arg_10]
0x1800236f6  test    r15, r15
0x1800236f9  jz      loc_180023907
0x1800236ff  mov     [rsi+1F8h], rax
0x180023706  mov     [rsi+1F0h], r15
0x18002370d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023714  cmp     rcx, rbp
0x180023717  jz      short loc_180023733
0x180023719  test    [rcx+1Ch], dil
0x18002371d  jz      short loc_180023733
0x18002371f  mov     rcx, [rcx+10h]
0x180023723  mov     edx, 15h
0x180023728  mov     r9, r15
0x18002372b  mov     r8, r14
0x18002372e  call    WPP_SF_q
0x180023733  inc     dword ptr [r15+40h]
0x180023737  lea     rcx, HashServerEntryTableLock; lpCriticalSection
0x18002373e  mov     rbx, [r15+28h]
0x180023742  mov     rdi, [r15+20h]
0x180023746  call    cs:__imp_LeaveCriticalSection
0x18002374c  mov     rax, [rsi+1F8h]
0x180023753  lea     rcx, [rsp+0B8h+hInternet]
0x18002375b  mov     [rsp+0B8h+var_58], rcx
0x180023760  lea     r8, aPropfind; "PROPFIND"
0x180023767  mov     dword ptr [rsi+34h], 1
0x18002376e  mov     r9, r12
0x180023771  mov     dword ptr [rsi+38h], 1
0x180023778  mov     rdx, rbx
0x18002377b  mov     qword ptr [rsi+208h], 0
0x180023786  mov     rcx, rdi
0x180023789  mov     qword ptr [rsi+210h], 0
0x180023794  mov     qword ptr [rsi+218h], 0
0x18002379f  mov     qword ptr [rsi+220h], 0
0x1800237aa  mov     eax, [rax+20h]
0x1800237ad  mov     [rsp+0B8h+var_68], eax
0x1800237b1  lea     rax, aDavfsquerydire; "DavFsQueryDirectory"
0x1800237b8  mov     [rsp+0B8h+var_70], rax
0x1800237bd  mov     [rsp+0B8h+var_80], 0
0x1800237c5  call    DavHttpOpenRequestW
0x1800237ca  test    eax, eax
0x1800237cc  jnz     short loc_1800237DB
0x1800237ce  call    cs:__imp_GetLastError
0x1800237d4  mov     ebx, eax
0x1800237d6  jmp     loc_18002393C
0x1800237db  mov     rbx, [rsp+0B8h+hInternet]
0x1800237e3  test    rbx, rbx
0x1800237e6  jnz     short loc_18002382E
0x1800237e8  call    cs:__imp_GetLastError
0x1800237ee  mov     ebx, eax
0x1800237f0  cmp     eax, 3E5h
0x1800237f5  jz      loc_18002393C
0x1800237fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180023802  cmp     rcx, rbp
0x180023805  jz      loc_18002393C
0x18002380b  test    byte ptr [rcx+1Ch], 1
0x18002380f  jz      loc_18002393C
0x180023815  mov     edx, 16h
0x18002381a  mov     rcx, [rcx+10h]
0x18002381e  mov     r9d, eax
0x180023821  mov     r8, r14
0x180023824  call    WPP_SF_d
0x180023829  jmp     loc_18002393C
0x18002382e  cmp     cs:g_DisableCookies, 0
0x180023835  jz      short loc_18002387F
0x180023837  mov     r9d, 4; dwBufferLength
0x18002383d  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x180023845  mov     rcx, rbx; hInternet
0x180023848  lea     edx, [r9+3Bh]; dwOption
0x18002384c  call    cs:__imp_WinHttpSetOption
0x180023852  test    eax, eax
0x180023854  jnz     short loc_18002387F
0x180023856  call    cs:__imp_GetLastError
0x18002385c  mov     ebx, eax
0x18002385e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023865  cmp     rcx, rbp
0x180023868  jz      loc_18002393C
  ... truncated ...
```

# ProtocolRetry

- ea: `0x180025300`
- end: `0x180025a53`
- name: `ProtocolRetry`
- size: `1875`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036280`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18001709c`
- `0x180018d9c`
- `0x180025300`
- `0x18003af58`
- `0x18004033c`
- `0x1800abc80`
- `0x1800e7206`
- `0x1800e7212`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002570c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002570c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025606`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025894`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800259b3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025489`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025517`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800255fc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002588a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025489`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025517`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800255fc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18002588a`

## pseudocode

```c
double __fastcall ProtocolRetry(__int64 a1, __int64 a2, __int64 a3)
{
  struct _LIST_ENTRY *v5; // rcx
  __int128 v6; // xmm0
  int v7; // r15d
  __int64 v8; // r13
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD LastError; // eax
  _OWORD *v13; // rbx
  __int64 v14; // rcx
  CHAR *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  DWORD v22; // eax
  __int64 v23; // rdx
  CHAR *v24; // rax
  _OWORD *v25; // rcx
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm1
  __int64 v32; // rcx
  CHAR *v33; // rax
  DWORD CurrentProcessId; // eax
  unsigned int EntryDialParams; // eax
  struct _LIST_ENTRY *v36; // rcx
  __int64 v37; // rdx
  __int64 UserData; // rax
  DWORD v39; // eax
  __int64 v40; // rcx
  WCHAR *v41; // rax
  __int64 v42; // rax
  __int64 (__fastcall *v43)(__int64); // rax
  unsigned int *v44; // rax
  __int64 v45; // rcx
  _BYTE *i; // rax
  _BYTE *v47; // rax
  int v49[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v50[1034]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR WideCharStr[275]; // [rsp+45Ah] [rbp+35Ah] BYREF
  CHAR MultiByteStr[16]; // [rsp+680h] [rbp+580h] BYREF
  CHAR v53[272]; // [rsp+690h] [rbp+590h] BYREF
  CHAR lpMultiByteStr[272]; // [rsp+7A0h] [rbp+6A0h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    *(double *)&v6 = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 900, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v7 = 1;
  v8 = 514;
  if ( !a1 )
  {
    v9 = 615;
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      v10 = 901;
LABEL_10:
      v11 = v9;
LABEL_11:
      *(double *)&v6 = WPP_SF_d(v5[1].Flink, v10, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v11);
      goto LABEL_90;
    }
    goto LABEL_90;
  }
  if ( *(_DWORD *)(a1 + 28) == 2 )
  {
    if ( *(_DWORD *)(a1 + 1360) == 3 )
    {
      *(_QWORD *)(a3 + 1088) = *(_QWORD *)(a1 + 1272);
      goto LABEL_81;
    }
    *(_QWORD *)&v6 = 0;
    *(_OWORD *)MultiByteStr = 0;
    memset_0(lpMultiByteStr, 0, 0x101u);
    memset_0(v53, 0, 0x101u);
    if ( !WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 1052), -1, MultiByteStr, 16, 0, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_90;
      }
      v10 = 903;
      goto LABEL_24;
    }
    *(_QWORD *)&v6 = *(_QWORD *)MultiByteStr;
    *(_OWORD *)(a3 + 1052) = *(_OWORD *)MultiByteStr;
    v13 = (_OWORD *)(a3 + 24);
    if ( !WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 24), -1, lpMultiByteStr, 257, 0, 0) )
    {
      LastError = GetLastError();
      v9 = LastError;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_90;
      }
      v10 = 904;
      goto LABEL_24;
    }
    v14 = 2;
    v15 = lpMultiByteStr;
    do
    {
      v16 = *((_OWORD *)v15 + 1);
      *v13 = *(_OWORD *)v15;
      v17 = *((_OWORD *)v15 + 2);
      v13[1] = v16;
      v18 = *((_OWORD *)v15 + 3);
      v13[2] = v17;
      v19 = *((_OWORD *)v15 + 4);
      v13[3] = v18;
      v20 = *((_OWORD *)v15 + 5);
      v13[4] = v19;
      v6 = *((_OWORD *)v15 + 6);
      v13[5] = v20;
      v21 = *((_OWORD *)v15 + 7);
      v15 += 128;
      v13[6] = v6;
      v13[7] = v21;
      v13 += 8;
      --v14;
    }
    while ( v14 );
    v7 = 0;
    *(_BYTE *)v13 = *v15;
    if ( *(_QWORD *)(a1 + 1248) )
    {
      LastError = DecryptPassword(a1, a3 + 538);
      v9 = LastError;
      if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_90;
        }
        v10 = 906;
LABEL_24:
        v11 = LastError;
        goto LABEL_11;
      }
    }
    else
    {
      if ( WideCharToMultiByte(0, 0x400u, (LPCWCH)(a3 + 538), -1, v53, 257, 0, 0) )
      {
        v23 = 2;
        v24 = v53;
        v9 = 0;
        v25 = (_OWORD *)(a3 + 538);
        do
        {
          v26 = *((_OWORD *)v24 + 1);
          *v25 = *(_OWORD *)v24;
          v27 = *((_OWORD *)v24 + 2);
          v25[1] = v26;
          v28 = *((_OWORD *)v24 + 3);
          v25[2] = v27;
          v29 = *((_OWORD *)v24 + 4);
          v25[3] = v28;
          v30 = *((_OWORD *)v24 + 5);
          v25[4] = v29;
          v6 = *((_OWORD *)v24 + 6);
          v25[5] = v30;
          v31 = *((_OWORD *)v24 + 7);
          v24 += 128;
          v25[6] = v6;
          v25[7] = v31;
          v25 += 8;
          --v23;
        }
        while ( v23 );
        *(_BYTE *)v25 = *v24;
      }
      else
      {
        v22 = GetLastError();
        v9 = v22;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          *(double *)&v6 = WPP_SF_d(
                             WPP_GLOBAL_Control[1].Flink,
                             905,
                             WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                             v22);
        }
      }
      v32 = 257;
      v33 = v53;
      do
      {
        *v33++ = 0;
        --v32;
      }
      while ( v32 );
      v7 = 1;
      if ( v9 )
        goto LABEL_90;
    }
    if ( !strcmp_0((const char *)(a3 + 538), "****************") )
    {
      v7 = 0;
      if ( g_fInProc )
      {
        memset_0(v50, 0, 0x630u);
        v49[0] = -2147483646;
        UserData = GetUserData(a1 + 1080, 9);
        if ( !UserData )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            *(double *)&v6 = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 908, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
          }
          goto LABEL_80;
        }
        EntryDialParams = GetEntryDialParams(0, *(unsigned int *)(UserData + 24), v49, v50, 1);
        if ( !EntryDialParams && (v49[0] & 2) != 0 )
        {
          if ( WideCharToMultiByte(0, 0x400u, WideCharStr, -1, (LPSTR)(a3 + 538), 257, 0, 0) )
          {
            v7 = 1;
          }
          else
          {
            v39 = GetLastError();
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              *(double *)&v6 = WPP_SF_d(
                                 WPP_GLOBAL_Control[1].Flink,
                                 910,
                                 WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
                                 v39);
            }
          }
          v40 = 514;
          v41 = WideCharStr;
          do
          {
            *(_BYTE *)v41 = 0;
            v41 = (WCHAR *)((char *)v41 + 1);
            --v40;
          }
          while ( v40 );
          if ( (v49[0] & 0x40) != 0 )
          {
            v42 = *(_QWORD *)(a1 + 1064);
            if ( v42 )
              *(_DWORD *)(v42 + 112) |= 2u;
          }
          goto LABEL_80;
        }
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v37 = 909;
LABEL_79:
          *(double *)&v6 = WPP_SF_d(v36[1].Flink, v37, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, EntryDialParams);
        }
      }
      else
      {
        CurrentProcessId = GetCurrentProcessId();
        EntryDialParams = DwGetPasswordA(a1, a3 + 538, CurrentProcessId);
        if ( EntryDialParams )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_80;
          }
          v37 = 907;
          goto LABEL_79;
        }
        v7 = 1;
      }
    }
LABEL_80:
    DwCacheCredMgrCredentials(a3, a1);
LABEL_81:
    v43 = (__int64 (__fastcall *)(__int64))qword_18010A098[8 * (__int64)*(int *)(a1 + 1360)];
    if ( v43 )
    {
      v9 = v43(a3);
      if ( v9 )
      {
        if ( *(_DWORD *)(a1 + 1360) == 3 )
        {
          v44 = *(unsigned int **)(a1 + 1272);
          if ( v44 )
          {
            v45 = *v44;
            for ( i = v44 + 1; v45; --v45 )
              *i++ = 0;
            LocalFree(*(HLOCAL *)(a1 + 1272));
          }
        }
      }
      *(_QWORD *)(a1 + 1272) = 0;
    }
    else
    {
      v9 = 839;
    }
    goto LABEL_90;
  }
  v9 = 619;
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 2u )
  {
    v10 = 902;
    goto LABEL_10;
  }
LABEL_90:
  *(_QWORD *)(a3 + 1088) = 0;
  if ( v7 )
  {
    v47 = (_BYTE *)(a3 + 538);
    do
    {
      *v47++ = 0;
      --v8;
    }
    while ( v8 );
  }
  *(_DWORD *)a3 = v9;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    *(double *)&v6 = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 911, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v9);
  }
  return *(double *)&v6;
}

```

## disassembly

```asm
0x180025300  mov     [rsp-8+arg_8], rbx
0x180025305  mov     [rsp-8+arg_18], rsi
0x18002530a  push    rbp
0x18002530b  push    r12
0x18002530d  push    r13
0x18002530f  push    r14
0x180025311  push    r15
0x180025313  lea     rbp, [rsp-7C0h]
0x18002531b  sub     rsp, 8C0h
0x180025322  mov     rax, cs:__security_cookie
0x180025329  xor     rax, rsp
0x18002532c  mov     [rbp+7E0h+var_30], rax
0x180025333  mov     r12, r8
0x180025336  mov     rsi, rcx
0x180025339  mov     rcx, cs:WPP_GLOBAL_Control
0x180025340  lea     rdx, WPP_GLOBAL_Control
0x180025347  mov     r14d, 2000h
0x18002534d  cmp     rcx, rdx
0x180025350  jz      short loc_180025381
0x180025352  test    [rcx+1Ch], r14d
0x180025356  jz      short loc_180025381
0x180025358  cmp     byte ptr [rcx+19h], 6
0x18002535c  jb      short loc_180025381
0x18002535e  mov     rcx, [rcx+10h]
0x180025362  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180025369  mov     edx, 384h
0x18002536e  call    WPP_SF_
0x180025373  mov     rcx, cs:WPP_GLOBAL_Control
0x18002537a  lea     rdx, WPP_GLOBAL_Control
0x180025381  mov     r15d, 1
0x180025387  mov     r13d, 202h
0x18002538d  test    rsi, rsi
0x180025390  jnz     short loc_1800253D0
0x180025392  lea     ebx, [r13+65h]
0x180025396  cmp     rcx, rdx
0x180025399  jz      loc_1800259CB
0x18002539f  test    [rcx+1Ch], r14d
0x1800253a3  jz      loc_1800259CB
0x1800253a9  cmp     byte ptr [rcx+19h], 2
0x1800253ad  jb      loc_1800259CB
0x1800253b3  mov     edx, 385h
0x1800253b8  mov     r9d, ebx
0x1800253bb  mov     rcx, [rcx+10h]
0x1800253bf  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x1800253c6  call    WPP_SF_d
0x1800253cb  jmp     loc_1800259C4
0x1800253d0  cmp     dword ptr [rsi+1Ch], 2
0x1800253d4  jz      short loc_1800253FF
0x1800253d6  mov     ebx, 26Bh
0x1800253db  cmp     rcx, rdx
0x1800253de  jz      loc_1800259CB
0x1800253e4  test    [rcx+1Ch], r14d
0x1800253e8  jz      loc_1800259CB
0x1800253ee  cmp     byte ptr [rcx+19h], 2
0x1800253f2  jb      loc_1800259CB
0x1800253f8  mov     edx, 386h
0x1800253fd  jmp     short loc_1800253B8
0x1800253ff  cmp     dword ptr [rsi+550h], 3
0x180025406  jnz     short loc_18002541C
0x180025408  mov     rax, [rsi+4F8h]
0x18002540f  mov     [r12+440h], rax
0x180025417  jmp     loc_180025950
0x18002541c  xorps   xmm0, xmm0
0x18002541f  lea     rcx, [rbp+7E0h+var_140]; void *
0x180025426  mov     ebx, 101h
0x18002542b  xor     edx, edx; Val
0x18002542d  mov     r8d, ebx; Size
0x180025430  movups  xmmword ptr [rbp+7E0h+MultiByteStr], xmm0
0x180025437  call    memset_0
0x18002543c  mov     r8d, ebx; Size
0x18002543f  lea     rcx, [rbp+7E0h+var_250]; void *
0x180025446  xor     edx, edx; Val
0x180025448  call    memset_0
0x18002544d  mov     [rsp+8E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180025456  lea     rax, [rbp+7E0h+MultiByteStr]
0x18002545d  mov     [rsp+8E0h+lpDefaultChar], 0; lpDefaultChar
0x180025466  lea     rbx, [r12+41Ch]
0x18002546e  mov     [rsp+8E0h+cbMultiByte], 10h; cbMultiByte
0x180025476  mov     r8, rbx; lpWideCharStr
0x180025479  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002547d  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x180025482  mov     edx, 400h; dwFlags
0x180025487  xor     ecx, ecx; CodePage
0x180025489  call    cs:__imp_WideCharToMultiByte
0x18002548f  test    eax, eax
0x180025491  jnz     short loc_1800254D3
0x180025493  call    cs:__imp_GetLastError
0x180025499  mov     ebx, eax
0x18002549b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254a2  lea     rdx, WPP_GLOBAL_Control
0x1800254a9  cmp     rcx, rdx
0x1800254ac  jz      loc_1800259CB
0x1800254b2  test    [rcx+1Ch], r14d
0x1800254b6  jz      loc_1800259CB
0x1800254bc  cmp     byte ptr [rcx+19h], 2
0x1800254c0  jb      loc_1800259CB
0x1800254c6  mov     edx, 387h
0x1800254cb  mov     r9d, eax
0x1800254ce  jmp     loc_1800253BB
0x1800254d3  movups  xmm0, xmmword ptr [rbp+7E0h+MultiByteStr]
0x1800254da  mov     [rsp+8E0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1800254e3  lea     rax, [rbp+7E0h+var_140]
0x1800254ea  mov     [rsp+8E0h+lpDefaultChar], 0; lpDefaultChar
0x1800254f3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800254f7  movdqu  xmmword ptr [rbx], xmm0
0x1800254fb  lea     rbx, [r12+18h]
0x180025500  mov     [rsp+8E0h+cbMultiByte], 101h; cbMultiByte
0x180025508  mov     r8, rbx; lpWideCharStr
0x18002550b  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x180025510  mov     edx, 400h; dwFlags
0x180025515  xor     ecx, ecx; CodePage
0x180025517  call    cs:__imp_WideCharToMultiByte
0x18002551d  test    eax, eax
0x18002551f  jnz     short loc_18002555E
0x180025521  call    cs:__imp_GetLastError
0x180025527  mov     ebx, eax
0x180025529  mov     rcx, cs:WPP_GLOBAL_Control
0x180025530  lea     rdx, WPP_GLOBAL_Control
0x180025537  cmp     rcx, rdx
0x18002553a  jz      loc_1800259CB
0x180025540  test    [rcx+1Ch], r14d
0x180025544  jz      loc_1800259CB
0x18002554a  cmp     byte ptr [rcx+19h], 2
0x18002554e  jb      loc_1800259CB
0x180025554  mov     edx, 388h
0x180025559  jmp     loc_1800254CB
0x18002555e  mov     ecx, 2
0x180025563  lea     rax, [rbp+7E0h+var_140]
0x18002556a  lea     edx, [rcx+7Eh]
0x18002556d  movups  xmm0, xmmword ptr [rax]
0x180025570  movups  xmm1, xmmword ptr [rax+10h]
0x180025574  movups  xmmword ptr [rbx], xmm0
0x180025577  movups  xmm0, xmmword ptr [rax+20h]
0x18002557b  movups  xmmword ptr [rbx+10h], xmm1
0x18002557f  movups  xmm1, xmmword ptr [rax+30h]
0x180025583  movups  xmmword ptr [rbx+20h], xmm0
0x180025587  movups  xmm0, xmmword ptr [rax+40h]
0x18002558b  movups  xmmword ptr [rbx+30h], xmm1
0x18002558f  movups  xmm1, xmmword ptr [rax+50h]
0x180025593  movups  xmmword ptr [rbx+40h], xmm0
0x180025597  movups  xmm0, xmmword ptr [rax+60h]
0x18002559b  movups  xmmword ptr [rbx+50h], xmm1
0x18002559f  movups  xmm1, xmmword ptr [rax+70h]
0x1800255a3  add     rax, rdx
0x1800255a6  movups  xmmword ptr [rbx+60h], xmm0
0x1800255aa  movups  xmmword ptr [rbx+70h], xmm1
0x1800255ae  add     rbx, rdx
0x1800255b1  sub     rcx, r15; CodePage
0x1800255b4  jnz     short loc_18002556D
0x1800255b6  mov     al, [rax]
0x1800255b8  lea     r14, [r12+21Ah]
0x1800255c0  xor     r15d, r15d
0x1800255c3  mov     [rbx], al
0x1800255c5  cmp     [rsi+4E0h], r15
0x1800255cc  jnz     loc_180025760
0x1800255d2  mov     [rsp+8E0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800255d7  lea     rax, [rbp+7E0h+var_250]
0x1800255de  mov     [rsp+8E0h+lpDefaultChar], r15; lpDefaultChar
0x1800255e3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800255e7  mov     [rsp+8E0h+cbMultiByte], 101h; cbMultiByte
0x1800255ef  mov     r8, r14; lpWideCharStr
0x1800255f2  mov     edx, 400h; dwFlags
0x1800255f7  mov     [rsp+8E0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800255fc  call    cs:__imp_WideCharToMultiByte
0x180025602  test    eax, eax
0x180025604  jnz     short loc_180025656
0x180025606  call    cs:__imp_GetLastError
0x18002560c  mov     ebx, eax
0x18002560e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025615  lea     rdx, WPP_GLOBAL_Control
0x18002561c  cmp     rcx, rdx
0x18002561f  jz      loc_1800256C1
0x180025625  test    dword ptr [rcx+1Ch], 2000h
0x18002562c  jz      loc_1800256C1
0x180025632  cmp     byte ptr [rcx+19h], 2
0x180025636  jb      loc_1800256C1
0x18002563c  mov     rcx, [rcx+10h]
0x180025640  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180025647  mov     edx, 389h
0x18002564c  mov     r9d, eax
0x18002564f  call    WPP_SF_d
0x180025654  jmp     short loc_1800256BA
0x180025656  mov     edx, 2
0x18002565b  lea     rax, [rbp+7E0h+var_250]
0x180025662  mov     ebx, r15d
0x180025665  mov     rcx, r14
0x180025668  lea     r8d, [rdx+7Eh]
0x18002566c  movups  xmm0, xmmword ptr [rax]
0x18002566f  movups  xmm1, xmmword ptr [rax+10h]
0x180025673  movups  xmmword ptr [rcx], xmm0
0x180025676  movups  xmm0, xmmword ptr [rax+20h]
0x18002567a  movups  xmmword ptr [rcx+10h], xmm1
0x18002567e  movups  xmm1, xmmword ptr [rax+30h]
0x180025682  movups  xmmword ptr [rcx+20h], xmm0
0x180025686  movups  xmm0, xmmword ptr [rax+40h]
0x18002568a  movups  xmmword ptr [rcx+30h], xmm1
0x18002568e  movups  xmm1, xmmword ptr [rax+50h]
0x180025692  movups  xmmword ptr [rcx+40h], xmm0
0x180025696  movups  xmm0, xmmword ptr [rax+60h]
0x18002569a  movups  xmmword ptr [rcx+50h], xmm1
0x18002569e  movups  xmm1, xmmword ptr [rax+70h]
0x1800256a2  add     rax, r8
0x1800256a5  movups  xmmword ptr [rcx+60h], xmm0
0x1800256a9  movups  xmmword ptr [rcx+70h], xmm1
0x1800256ad  add     rcx, r8
0x1800256b0  sub     rdx, 1
0x1800256b4  jnz     short loc_18002566C
0x1800256b6  mov     al, [rax]
0x1800256b8  mov     [rcx], al
0x1800256ba  lea     rdx, WPP_GLOBAL_Control
0x1800256c1  mov     ecx, 101h
0x1800256c6  lea     rax, [rbp+7E0h+var_250]
0x1800256cd  mov     [rax], r15b
0x1800256d0  inc     rax
0x1800256d3  sub     rcx, 1
0x1800256d7  jnz     short loc_1800256CD
0x1800256d9  lea     r15d, [rcx+1]
0x1800256dd  test    ebx, ebx
0x1800256df  jnz     loc_1800259CB
0x1800256e5  lea     rdx, Str2; "****************"
0x1800256ec  mov     rcx, r14; Str1
0x1800256ef  call    strcmp_0
0x1800256f4  test    eax, eax
0x1800256f6  jnz     loc_180025945
0x1800256fc  xor     r15d, r15d
0x1800256ff  cmp     cs:g_fInProc, r15d
0x180025706  jnz     loc_1800257B8
0x18002570c  call    cs:__imp_GetCurrentProcessId
0x180025712  mov     rdx, r14
0x180025715  mov     rcx, rsi
0x180025718  mov     r8d, eax
0x18002571b  call    DwGetPasswordA
0x180025720  test    eax, eax
0x180025722  jz      loc_1800257AD
0x180025728  mov     rcx, cs:WPP_GLOBAL_Control
0x18002572f  lea     rdx, WPP_GLOBAL_Control
0x180025736  cmp     rcx, rdx
0x180025739  jz      loc_180025945
0x18002573f  test    dword ptr [rcx+1Ch], 2000h
0x180025746  jz      loc_180025945
0x18002574c  cmp     byte ptr [rcx+19h], 2
0x180025750  jb      loc_180025945
0x180025756  mov     edx, 38Bh
0x18002575b  jmp     loc_180025932
0x180025760  mov     rdx, r14
0x180025763  mov     rcx, rsi
0x180025766  call    DecryptPassword
0x18002576b  mov     ebx, eax
0x18002576d  test    eax, eax
0x18002576f  jz      loc_1800256E5
0x180025775  mov     rcx, cs:WPP_GLOBAL_Control
0x18002577c  lea     rdx, WPP_GLOBAL_Control
0x180025783  cmp     rcx, rdx
0x180025786  jz      loc_1800259CB
0x18002578c  test    dword ptr [rcx+1Ch], 2000h
0x180025793  jz      loc_1800259CB
0x180025799  cmp     byte ptr [rcx+19h], 2
0x18002579d  jb      loc_1800259CB
0x1800257a3  mov     edx, 38Ah
0x1800257a8  jmp     loc_1800254CB
0x1800257ad  mov     r15d, 1
0x1800257b3  jmp     loc_180025945
0x1800257b8  xor     edx, edx; Val
0x1800257ba  lea     rcx, [rsp+8E0h+var_890]; void *
0x1800257bf  mov     r8d, 630h; Size
0x1800257c5  call    memset_0
0x1800257ca  lea     rcx, [rsi+438h]
0x1800257d1  mov     [rsp+8E0h+var_8A0], 80000002h
0x1800257d9  mov     edx, 9
0x1800257de  call    GetUserData
0x1800257e3  test    rax, rax
0x1800257e6  jnz     short loc_180025830
0x1800257e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257ef  lea     rdx, WPP_GLOBAL_Control
0x1800257f6  cmp     rcx, rdx
0x1800257f9  jz      loc_180025945
0x1800257ff  test    dword ptr [rcx+1Ch], 2000h
0x180025806  jz      loc_180025945
0x18002580c  cmp     byte ptr [rcx+19h], 2
0x180025810  jb      loc_180025945
0x180025816  mov     rcx, [rcx+10h]
0x18002581a  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180025821  mov     edx, 38Ch
0x180025826  call    WPP_SF_
0x18002582b  jmp     loc_180025945
0x180025830  mov     edx, [rax+18h]
0x180025833  lea     r9, [rsp+8E0h+var_890]
0x180025838  lea     r8, [rsp+8E0h+var_8A0]
0x18002583d  mov     dword ptr [rsp+8E0h+lpMultiByteStr], 1
0x180025845  xor     ecx, ecx
0x180025847  call    GetEntryDialParams
0x18002584c  test    eax, eax
0x18002584e  jnz     loc_18002590B
0x180025854  mov     ecx, [rsp+8E0h+var_8A0]
0x180025858  test    cl, 2
0x18002585b  jz      loc_18002590B
0x180025861  mov     [rsp+8E0h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180025866  lea     r8, [rbp+7E0h+WideCharStr]; lpWideCharStr
0x18002586d  mov     [rsp+8E0h+lpDefaultChar], r15; lpDefaultChar
0x180025872  or      r9d, 0FFFFFFFFh; cchWideChar
  ... truncated ...
```

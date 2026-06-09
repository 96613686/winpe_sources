# GetPhonebookDirectory

- ea: `0x180069ab4`
- end: `0x180069f1e`
- name: `GetPhonebookDirectory`
- size: `1130`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068774`
- `0x180069914`
- `0x18006a4fc`
- `0x180072928`
- `0x18007c5d8`
- `0x1800803dc`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005e74`
- `0x18000bf70`
- `0x18005c398`
- `0x18005cd78`
- `0x18005d454`
- `0x180069ab4`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069c4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180069c4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069c20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180069c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180069c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069c3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180069c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069c5b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180069e6e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180069e6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180069b71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180069b71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180069dae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180069dbe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180069dae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180069dbe`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180069d4f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180069d4f`

## pseudocode

```c
__int64 __fastcall GetPhonebookDirectory(unsigned int a1, wchar_t *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  unsigned int v5; // esi
  DWORD v6; // edi
  STRSAFE_LPWSTR *v7; // r9
  HRESULT v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v13; // rdx
  int v14; // ebx
  unsigned __int16 BasicProfileFolderPath; // ax
  __int64 v16; // r9
  int v17; // ebx
  HRESULT v18; // eax
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  HGLOBAL hMem; // [rsp+38h] [rbp-C8h]
  _BYTE v23[528]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 31, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a1, 261);
    v4 = WPP_GLOBAL_Control;
  }
  hMem = 0;
  TokenHandle = 0;
  memset_0(v23, 0, 0x20Au);
  if ( a1 >= 2 )
  {
    v5 = 0;
    v6 = 0;
    if ( GetSystemDirectoryW(a2, 0x105u) - 1 <= 0xF2 )
    {
      v8 = StringCchCatExW(a2, 0x105u, L"\\Ras\\", v7, pcchRemaining, 0x100u);
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_13;
        }
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 42, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (unsigned int)v8);
      }
      v9 = WPP_GLOBAL_Control;
LABEL_13:
      v5 = 1;
      goto LABEL_59;
    }
    goto LABEL_58;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 0x80) != 0 && BYTE1(v4[1].Blink) >= 5u )
    WPP_SF_(v4[1].Flink, 34, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  CurrentThread = GetCurrentThread();
  v5 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( !v5 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 1008 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 36;
        goto LABEL_56;
      }
      goto LABEL_59;
    }
    CurrentProcess = GetCurrentProcess();
    v5 = OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle);
    if ( !v5 )
    {
      LastError = GetLastError();
      v6 = LastError;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 35;
LABEL_56:
        v16 = LastError;
        goto LABEL_57;
      }
      goto LABEL_59;
    }
  }
  LastError = GetSidFromToken(TokenHandle);
  v6 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v13 = 37;
      goto LABEL_56;
    }
  }
  else
  {
    v14 = a1 != 0 ? 3 : 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        38,
        &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        (unsigned int)(v14 + 4));
    }
    BasicProfileFolderPath = GetBasicProfileFolderPath((unsigned int)(v14 + 4), hMem, v23, 261);
    v6 = BasicProfileFolderPath;
    if ( BasicProfileFolderPath )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 39;
        v16 = BasicProfileFolderPath;
LABEL_57:
        WPP_SF_d(v9[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v16);
        goto LABEL_58;
      }
    }
    else
    {
      LastError = StringCchCopyWrapW(a2, 261, v23);
      v6 = LastError;
      if ( !LastError )
      {
        v17 = 260 - lstrlenW(L"\\Microsoft\\Network\\Connections\\Pbk\\");
        if ( lstrlenW(a2) <= v17 )
        {
          v18 = StringCchCatExW(a2, 0x105u, L"\\Microsoft\\Network\\Connections\\Pbk\\", v7, pcchRemaining, 0x100u);
          if ( v18 < 0 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                40,
                &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                (unsigned int)v18);
              v9 = WPP_GLOBAL_Control;
            }
            v5 = 0;
            goto LABEL_59;
          }
          v5 = 1;
        }
LABEL_58:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_59;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 0x80) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v13 = 41;
        goto LABEL_56;
      }
    }
  }
LABEL_59:
  if ( hMem )
  {
    GlobalFree(hMem);
    v9 = WPP_GLOBAL_Control;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 0x80) != 0 && BYTE1(v9[1].Blink) >= 6u )
      WPP_SF_c(v9[1].Flink, 43, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 0);
    return 0;
  }
  else
  {
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 0x80) != 0 && BYTE1(v9[1].Blink) >= 6u )
    {
      LOBYTE(v7) = v5 != 0;
      WPP_SF_c(v9[1].Flink, 44, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180069ab4  mov     [rsp-8+arg_10], rbx
0x180069ab9  push    rbp
0x180069aba  push    rsi
0x180069abb  push    rdi
0x180069abc  push    r12
0x180069abe  push    r13
0x180069ac0  push    r14
0x180069ac2  push    r15
0x180069ac4  lea     rbp, [rsp-160h]
0x180069acc  sub     rsp, 260h
0x180069ad3  mov     rax, cs:__security_cookie
0x180069ada  xor     rax, rsp
0x180069add  mov     [rbp+190h+var_40], rax
0x180069ae4  mov     r15, rdx
0x180069ae7  mov     r14d, ecx
0x180069aea  mov     rbx, cs:WPP_GLOBAL_Control
0x180069af1  lea     r13, WPP_GLOBAL_Control
0x180069af8  mov     r12b, 80h
0x180069afb  cmp     rbx, r13
0x180069afe  jz      short loc_180069B33
0x180069b00  test    [rbx+1Ch], r12b
0x180069b04  jz      short loc_180069B33
0x180069b06  cmp     byte ptr [rbx+19h], 6
0x180069b0a  jb      short loc_180069B33
0x180069b0c  mov     r9d, ecx
0x180069b0f  mov     dword ptr [rsp+290h+pcchRemaining], 105h; pcchRemaining
0x180069b17  mov     rcx, [rbx+10h]
0x180069b1b  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069b22  mov     edx, 1Fh
0x180069b27  call    WPP_SF_Dd
0x180069b2c  mov     rbx, cs:WPP_GLOBAL_Control
0x180069b33  xor     edx, edx; Val
0x180069b35  mov     [rsp+290h+hMem], 0
0x180069b3e  mov     r8d, 20Ah; Size
0x180069b44  mov     [rsp+290h+TokenHandle], 0
0x180069b4d  lea     rcx, [rsp+290h+var_250]; void *
0x180069b52  call    memset_0
0x180069b57  cmp     r14d, 2
0x180069b5b  jb      loc_180069BE1
0x180069b61  mov     r14d, 105h
0x180069b67  mov     rcx, r15; lpBuffer
0x180069b6a  mov     edx, r14d; uSize
0x180069b6d  xor     esi, esi
0x180069b6f  xor     edi, edi
0x180069b71  call    cs:__imp_GetSystemDirectoryW
0x180069b77  dec     eax
0x180069b79  cmp     eax, 0F2h
0x180069b7e  ja      loc_180069E5A
0x180069b84  lea     r8, aRas; "\\Ras\\"
0x180069b8b  mov     [rsp+290h+dwFlags], 100h; dwFlags
0x180069b93  mov     edx, r14d; cchDest
0x180069b96  mov     rcx, r15; pszDest
0x180069b99  call    StringCchCatExW
0x180069b9e  test    eax, eax
0x180069ba0  jns     short loc_180069BD0
0x180069ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ba9  cmp     rcx, r13
0x180069bac  jz      short loc_180069BD7
0x180069bae  test    [rcx+1Ch], r12b
0x180069bb2  jz      short loc_180069BD7
0x180069bb4  cmp     byte ptr [rcx+19h], 2
0x180069bb8  jb      short loc_180069BD7
0x180069bba  mov     rcx, [rcx+10h]
0x180069bbe  lea     edx, [rsi+2Ah]
0x180069bc1  mov     r9d, eax
0x180069bc4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069bcb  call    WPP_SF_d
0x180069bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180069bd7  mov     esi, 1
0x180069bdc  jmp     loc_180069E61
0x180069be1  cmp     rbx, r13
0x180069be4  jz      short loc_180069C07
0x180069be6  test    [rbx+1Ch], r12b
0x180069bea  jz      short loc_180069C07
0x180069bec  cmp     byte ptr [rbx+19h], 5
0x180069bf0  jb      short loc_180069C07
0x180069bf2  mov     rcx, [rbx+10h]
0x180069bf6  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069bfd  mov     edx, 22h ; '"'
0x180069c02  call    WPP_SF_
0x180069c07  call    cs:__imp_GetCurrentThread
0x180069c0d  mov     ebx, 0Ch
0x180069c12  lea     r9, [rsp+290h+TokenHandle]; TokenHandle
0x180069c17  mov     rcx, rax; ThreadHandle
0x180069c1a  mov     edx, ebx; DesiredAccess
0x180069c1c  lea     r8d, [rbx-0Bh]; OpenAsSelf
0x180069c20  call    cs:__imp_OpenThreadToken
0x180069c26  mov     esi, eax
0x180069c28  test    eax, eax
0x180069c2a  jnz     loc_180069CBD
0x180069c30  call    cs:__imp_GetLastError
0x180069c36  mov     edi, eax
0x180069c38  cmp     eax, 3F0h
0x180069c3d  jnz     short loc_180069C8F
0x180069c3f  call    cs:__imp_GetCurrentProcess
0x180069c45  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180069c4a  mov     edx, ebx; DesiredAccess
0x180069c4c  mov     rcx, rax; ProcessHandle
0x180069c4f  call    cs:__imp_OpenProcessToken
0x180069c55  mov     esi, eax
0x180069c57  test    eax, eax
0x180069c59  jnz     short loc_180069CBD
0x180069c5b  call    cs:__imp_GetLastError
0x180069c61  mov     edi, eax
0x180069c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180069c6a  cmp     rcx, r13
0x180069c6d  jz      loc_180069E61
0x180069c73  test    [rcx+1Ch], r12b
0x180069c77  jz      loc_180069E61
0x180069c7d  cmp     byte ptr [rcx+19h], 2
0x180069c81  jb      loc_180069E61
0x180069c87  lea     edx, [rbx+17h]
0x180069c8a  jmp     loc_180069E47
0x180069c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180069c96  cmp     rcx, r13
0x180069c99  jz      loc_180069E61
0x180069c9f  test    [rcx+1Ch], r12b
0x180069ca3  jz      loc_180069E61
0x180069ca9  cmp     byte ptr [rcx+19h], 2
0x180069cad  jb      loc_180069E61
0x180069cb3  mov     edx, 24h ; '$'
0x180069cb8  jmp     loc_180069E47
0x180069cbd  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180069cc2  lea     rdx, [rsp+290h+hMem]
0x180069cc7  call    GetSidFromToken
0x180069ccc  mov     edi, eax
0x180069cce  test    eax, eax
0x180069cd0  jz      short loc_180069D00
0x180069cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180069cd9  cmp     rcx, r13
0x180069cdc  jz      loc_180069E61
0x180069ce2  test    [rcx+1Ch], r12b
0x180069ce6  jz      loc_180069E61
0x180069cec  cmp     byte ptr [rcx+19h], 2
0x180069cf0  jb      loc_180069E61
0x180069cf6  mov     edx, 25h ; '%'
0x180069cfb  jmp     loc_180069E47
0x180069d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d07  neg     r14d
0x180069d0a  sbb     ebx, ebx
0x180069d0c  and     ebx, 3
0x180069d0f  cmp     rcx, r13
0x180069d12  jz      short loc_180069D39
0x180069d14  test    [rcx+1Ch], r12b
0x180069d18  jz      short loc_180069D39
0x180069d1a  cmp     byte ptr [rcx+19h], 5
0x180069d1e  jb      short loc_180069D39
0x180069d20  mov     rcx, [rcx+10h]
0x180069d24  lea     r9d, [rbx+4]
0x180069d28  mov     edx, 26h ; '&'
0x180069d2d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069d34  call    WPP_SF_d
0x180069d39  mov     rdx, [rsp+290h+hMem]
0x180069d3e  lea     r8, [rsp+290h+var_250]
0x180069d43  mov     r14d, 105h
0x180069d49  lea     ecx, [rbx+4]
0x180069d4c  mov     r9d, r14d
0x180069d4f  call    cs:__imp_GetBasicProfileFolderPath
0x180069d55  movzx   edi, ax
0x180069d58  test    edi, edi
0x180069d5a  jz      short loc_180069D8D
0x180069d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180069d63  cmp     rcx, r13
0x180069d66  jz      loc_180069E61
0x180069d6c  test    [rcx+1Ch], r12b
0x180069d70  jz      loc_180069E61
0x180069d76  cmp     byte ptr [rcx+19h], 2
0x180069d7a  jb      loc_180069E61
0x180069d80  mov     edx, 27h ; '''
0x180069d85  mov     r9d, edi
0x180069d88  jmp     loc_180069E4A
0x180069d8d  lea     r8, [rsp+290h+var_250]
0x180069d92  mov     rdx, r14
0x180069d95  mov     rcx, r15
0x180069d98  call    StringCchCopyWrapW
0x180069d9d  mov     edi, eax
0x180069d9f  test    eax, eax
0x180069da1  jnz     loc_180069E2A
0x180069da7  lea     rcx, aMicrosoftNetwo; "\\Microsoft\\Network\\Connections\\Pbk"...
0x180069dae  call    cs:__imp_lstrlenW
0x180069db4  mov     ebx, 104h
0x180069db9  mov     rcx, r15; lpString
0x180069dbc  sub     ebx, eax
0x180069dbe  call    cs:__imp_lstrlenW
0x180069dc4  cmp     eax, ebx
0x180069dc6  jg      loc_180069E5A
0x180069dcc  lea     r8, aMicrosoftNetwo; "\\Microsoft\\Network\\Connections\\Pbk"...
0x180069dd3  mov     [rsp+290h+dwFlags], 100h; dwFlags
0x180069ddb  mov     rdx, r14; cchDest
0x180069dde  mov     rcx, r15; pszDest
0x180069de1  call    StringCchCatExW
0x180069de6  test    eax, eax
0x180069de8  jns     short loc_180069E23
0x180069dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180069df1  cmp     rcx, r13
0x180069df4  jz      short loc_180069E1F
0x180069df6  test    [rcx+1Ch], r12b
0x180069dfa  jz      short loc_180069E1F
0x180069dfc  cmp     byte ptr [rcx+19h], 2
0x180069e00  jb      short loc_180069E1F
0x180069e02  mov     rcx, [rcx+10h]
0x180069e06  lea     edx, [rdi+28h]
0x180069e09  mov     r9d, eax
0x180069e0c  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069e13  call    WPP_SF_d
0x180069e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e1f  xor     esi, esi
0x180069e21  jmp     short loc_180069E61
0x180069e23  mov     esi, 1
0x180069e28  jmp     short loc_180069E5A
0x180069e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e31  cmp     rcx, r13
0x180069e34  jz      short loc_180069E61
0x180069e36  test    [rcx+1Ch], r12b
0x180069e3a  jz      short loc_180069E61
0x180069e3c  cmp     byte ptr [rcx+19h], 2
0x180069e40  jb      short loc_180069E61
0x180069e42  mov     edx, 29h ; ')'
0x180069e47  mov     r9d, eax
0x180069e4a  mov     rcx, [rcx+10h]
0x180069e4e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069e55  call    WPP_SF_d
0x180069e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e61  mov     rax, [rsp+290h+hMem]
0x180069e66  test    rax, rax
0x180069e69  jz      short loc_180069E7B
0x180069e6b  mov     rcx, rax; hMem
0x180069e6e  call    cs:__imp_GlobalFree
0x180069e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e7b  mov     rax, [rsp+290h+TokenHandle]
0x180069e80  test    rax, rax
0x180069e83  jz      short loc_180069E95
0x180069e85  mov     rcx, rax; hObject
0x180069e88  call    cs:__imp_CloseHandle
0x180069e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180069e95  test    edi, edi
0x180069e97  jz      short loc_180069EC6
0x180069e99  cmp     rcx, r13
0x180069e9c  jz      short loc_180069EC2
0x180069e9e  test    [rcx+1Ch], r12b
0x180069ea2  jz      short loc_180069EC2
0x180069ea4  cmp     byte ptr [rcx+19h], 6
0x180069ea8  jb      short loc_180069EC2
0x180069eaa  mov     rcx, [rcx+10h]
0x180069eae  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069eb5  mov     edx, 2Bh ; '+'
0x180069eba  xor     r9d, r9d
0x180069ebd  call    WPP_SF_c
0x180069ec2  xor     eax, eax
0x180069ec4  jmp     short loc_180069EF4
0x180069ec6  cmp     rcx, r13
0x180069ec9  jz      short loc_180069EF2
0x180069ecb  test    [rcx+1Ch], r12b
0x180069ecf  jz      short loc_180069EF2
0x180069ed1  cmp     byte ptr [rcx+19h], 6
0x180069ed5  jb      short loc_180069EF2
0x180069ed7  mov     rcx, [rcx+10h]
0x180069edb  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180069ee2  test    esi, esi
0x180069ee4  mov     edx, 2Ch ; ','
0x180069ee9  setnz   r9b
0x180069eed  call    WPP_SF_c
0x180069ef2  mov     eax, esi
0x180069ef4  mov     rcx, [rbp+190h+var_40]
0x180069efb  xor     rcx, rsp; StackCookie
0x180069efe  call    __security_check_cookie
0x180069f03  mov     rbx, [rsp+290h+arg_10]
0x180069f0b  add     rsp, 260h
0x180069f12  pop     r15
0x180069f14  pop     r14
0x180069f16  pop     r13
0x180069f18  pop     r12
0x180069f1a  pop     rdi
0x180069f1b  pop     rsi
0x180069f1c  pop     rbp
0x180069f1d  retn
```

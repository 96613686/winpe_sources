# TfsCreateEntry

- ea: `0x18002a964`
- end: `0x18002adf7`
- name: `TfsCreateEntry`
- size: `1171`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *, wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019454`

## callees

- `0x18000b6b4`
- `0x18000b7dc`
- `0x18000ba14`
- `0x18000bc5c`
- `0x18002a964`
- `0x18002afb0`
- `0x18002b5f4`
- `0x18002cb44`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002abfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002abfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ac33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002adcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002acba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002adcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a9d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a9d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ad21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002ad21`
- `RPCRT4!UuidCreate` at `0x18002ab2b`
- `RPCRT4!UuidCreate` at `0x18002ab2b`
- `KERNEL32!LocalAlloc` at `0x18002ac73`
- `KERNEL32!LocalAlloc` at `0x18002ac73`
- `KERNEL32!SystemTimeToFileTime` at `0x18002ad30`
- `KERNEL32!SystemTimeToFileTime` at `0x18002ad30`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aba9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aba9`

## pseudocode

```c
__int64 __fastcall TfsCreateEntry(__int64 a1, const wchar_t *a2, const wchar_t *a3, wchar_t *a4, unsigned int *a5)
{
  STRSAFE_LPCWSTR *v5; // r13
  DWORD Entry; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 v15; // rdi
  unsigned int v16; // r8d
  __int64 v17; // rcx
  unsigned int *v18; // rbx
  size_t v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // eax
  OLECHAR *v22; // rbx
  unsigned int *v23; // rdx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v26; // esi
  __int64 v27; // rcx
  __int64 v28; // rax
  _DWORD *v29; // rax
  _DWORD *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  int v33; // r8d
  char *v34; // rax
  char **v35; // rcx
  __int64 v36; // [rsp+40h] [rbp-88h] BYREF
  unsigned int *v37; // [rsp+48h] [rbp-80h]
  unsigned int v38; // [rsp+50h] [rbp-78h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+58h] [rbp-70h]
  UUID Uuid; // [rsp+60h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-58h] BYREF

  v5 = (STRSAFE_LPCWSTR *)DavTfsStore;
  v37 = a5;
  v36 = 0;
  SystemTime = 0;
  Uuid = 0;
  if ( !DavTfsStore )
    return 6;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)DavTfsStore + 56);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DavTfsStore + 56));
  Entry = TfsFindEntry(v5, a2, &v36);
  v11 = Entry;
  if ( Entry )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v13 = 34;
    goto LABEL_50;
  }
  v14 = v36;
  if ( v36 && *(_DWORD *)(v36 + 24) != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v36);
    *(_DWORD *)(v14 + 24) = 2;
  }
  v15 = -1;
  v16 = *((_DWORD *)v5 + 10) + 40;
  if ( a3 )
  {
    v17 = -1;
    do
      ++v17;
    while ( a3[v17] );
    v16 = *((_DWORD *)v5 + 10) + 41 + v17;
    if ( v16 < *((_DWORD *)v5 + 10) + 41 )
    {
      v11 = 534;
LABEL_51:
      LeaveCriticalSection(lpCriticalSection);
      return v11;
    }
  }
  v18 = v37;
  v19 = *v37;
  if ( (unsigned int)v19 < v16 )
  {
    if ( !a3 )
      goto LABEL_32;
    v20 = -1;
    do
      ++v20;
    while ( a3[v20] );
    if ( v19 < (unsigned __int64)v16 - v20 - 1 )
    {
LABEL_32:
      *v37 = v16;
      v11 = 122;
      goto LABEL_51;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids,
        (_DWORD)a3,
        (__int64)a2);
      v19 = *v18;
    }
    a3 = 0;
  }
  StringCchCopyW(a4, v19, v5[6]);
  v36 = *((unsigned int *)v5 + 10);
  a4[v36] = 92;
  v21 = UuidCreate(&Uuid);
  v11 = v21;
  if ( v21 && v21 != 1824 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, v21);
    goto LABEL_51;
  }
  v22 = &a4[v36];
  StringFromGUID2(&Uuid, v22 + 1, *v37 - ((2 * v36 + 2) >> 1));
  if ( a3 )
  {
    v23 = v37;
    v22[39] = 46;
    StringCchCopyW(v22 + 40, *v23 - (v22 + 40 - a4), a3);
  }
  FileW = CreateFileW(a4, 0x80u, 1u, 0, 1u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v26 = 0;
    CloseHandle(FileW);
LABEL_42:
    LODWORD(v36) = TfsGetHashId(a2);
    v27 = -1;
    do
      ++v27;
    while ( a2[v27] );
    v28 = -1;
    do
      ++v28;
    while ( a4[v28] );
    v38 = 2 * (v27 + v28) + 100;
    v29 = LocalAlloc(0x40u, v38);
    v30 = v29;
    if ( !v29 )
    {
      Entry = GetLastError();
      v11 = Entry;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v13 = 38;
LABEL_50:
      WPP_SF_d(v12[2], v13, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids, Entry);
      goto LABEL_51;
    }
    v29[4] = v38;
    v31 = -1;
    *(_QWORD *)(v30 + 5) = 0;
    do
      ++v31;
    while ( a2[v31] );
    v30[7] = v31;
    *((_QWORD *)v30 + 4) = v30 + 24;
    v32 = -1;
    do
      ++v32;
    while ( a4[v32] );
    v30[10] = v32;
    *((_QWORD *)v30 + 6) = *((_QWORD *)v30 + 4) + 2LL + 2LL * (unsigned int)v30[7];
    v30[14] = 0;
    *((_QWORD *)v30 + 8) = 0;
    *((_QWORD *)v30 + 9) = 0;
    *((_QWORD *)v30 + 10) = 0;
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, (LPFILETIME)v30 + 11);
    StringCchCopyW(*((STRSAFE_LPWSTR *)v30 + 4), (unsigned int)(v30[7] + 1), a2);
    StringCchCopyW(*((STRSAFE_LPWSTR *)v30 + 6), (unsigned int)(v30[10] + 1), a4);
    v34 = (char *)&v5[2 * (unsigned int)v36 + 12];
    v35 = (char **)*((_QWORD *)v34 + 1);
    if ( *v35 != v34 )
      __fastfail(3u);
    *(_QWORD *)v30 = v34;
    *((_QWORD *)v30 + 1) = v35;
    *v35 = (char *)v30;
    *((_QWORD *)v34 + 1) = v30;
    do
      ++v15;
    while ( a4[v15] );
    *v37 = v15 + 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v33, (_DWORD)v30, (__int64)a4, (__int64)a2);
    goto LABEL_63;
  }
  LastError = GetLastError();
  v26 = LastError;
  if ( LastError == 183 || LastError == 80 )
  {
    v26 = 87;
    goto LABEL_63;
  }
  if ( !LastError )
    goto LABEL_42;
LABEL_63:
  LeaveCriticalSection(lpCriticalSection);
  return v26;
}

```

## disassembly

```asm
0x18002a964  push    rbx
0x18002a966  push    rbp
0x18002a967  push    rsi
0x18002a968  push    rdi
0x18002a969  push    r12
0x18002a96b  push    r13
0x18002a96d  push    r14
0x18002a96f  sub     rsp, 90h
0x18002a976  mov     rax, cs:__security_cookie
0x18002a97d  xor     rax, rsp
0x18002a980  mov     [rsp+0C8h+var_48], rax
0x18002a988  mov     rax, [rsp+0C8h+arg_20]
0x18002a990  xorps   xmm0, xmm0
0x18002a993  mov     r13, cs:DavTfsStore
0x18002a99a  xorps   xmm1, xmm1
0x18002a99d  mov     [rsp+0C8h+var_80], rax
0x18002a9a2  mov     r14, r9
0x18002a9a5  xor     eax, eax
0x18002a9a7  mov     rsi, r8
0x18002a9aa  mov     [rsp+0C8h+var_88], rax
0x18002a9af  mov     r12, rdx
0x18002a9b2  movups  xmmword ptr [rsp+0C8h+SystemTime.wYear], xmm0
0x18002a9b7  movups  xmmword ptr [rsp+0C8h+Uuid.Data1], xmm1
0x18002a9bc  test    r13, r13
0x18002a9bf  jnz     short loc_18002A9CA
0x18002a9c1  lea     eax, [r13+6]
0x18002a9c5  jmp     loc_18002ADD5
0x18002a9ca  lea     rax, [r13+38h]
0x18002a9ce  mov     rcx, rax; lpCriticalSection
0x18002a9d1  mov     [rsp+0C8h+lpCriticalSection], rax
0x18002a9d6  call    cs:__imp_EnterCriticalSection
0x18002a9dc  lea     r8, [rsp+0C8h+var_88]
0x18002a9e1  mov     rdx, r12
0x18002a9e4  mov     rcx, r13
0x18002a9e7  call    TfsFindEntry
0x18002a9ec  xor     r9d, r9d
0x18002a9ef  mov     ebx, eax
0x18002a9f1  test    eax, eax
0x18002a9f3  jz      short loc_18002AA1F
0x18002a9f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9fc  lea     rbp, WPP_GLOBAL_Control
0x18002aa03  cmp     rcx, rbp
0x18002aa06  jz      loc_18002ACB5
0x18002aa0c  test    byte ptr [rcx+1Ch], 1
0x18002aa10  jz      loc_18002ACB5
0x18002aa16  lea     edx, [r9+22h]
0x18002aa1a  jmp     loc_18002ACA2
0x18002aa1f  mov     rbx, [rsp+0C8h+var_88]
0x18002aa24  lea     rbp, WPP_GLOBAL_Control
0x18002aa2b  test    rbx, rbx
0x18002aa2e  jz      short loc_18002AA6A
0x18002aa30  cmp     dword ptr [rbx+18h], 2
0x18002aa34  jz      short loc_18002AA6A
0x18002aa36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa3d  cmp     rcx, rbp
0x18002aa40  jz      short loc_18002AA63
0x18002aa42  test    byte ptr [rcx+1Ch], 1
0x18002aa46  jz      short loc_18002AA63
0x18002aa48  mov     rcx, [rcx+10h]
0x18002aa4c  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002aa53  mov     edx, 23h ; '#'
0x18002aa58  mov     r9, rbx
0x18002aa5b  call    WPP_SF_q
0x18002aa60  xor     r9d, r9d
0x18002aa63  mov     dword ptr [rbx+18h], 2
0x18002aa6a  mov     r8d, [r13+28h]
0x18002aa6e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002aa72  add     r8d, 28h ; '('
0x18002aa76  test    rsi, rsi
0x18002aa79  jz      short loc_18002AA9F
0x18002aa7b  mov     rcx, rdi
0x18002aa7e  inc     rcx
0x18002aa81  cmp     [rsi+rcx*2], r9w
0x18002aa86  jnz     short loc_18002AA7E
0x18002aa88  lea     eax, [r8+1]
0x18002aa8c  lea     r8d, [rax+rcx]
0x18002aa90  cmp     r8d, eax
0x18002aa93  jnb     short loc_18002AA9F
0x18002aa95  mov     ebx, 216h
0x18002aa9a  jmp     loc_18002ACB5
0x18002aa9f  mov     rbx, [rsp+0C8h+var_80]
0x18002aaa4  mov     edx, [rbx]
0x18002aaa6  cmp     edx, r8d
0x18002aaa9  jnb     short loc_18002AB0A
0x18002aaab  test    rsi, rsi
0x18002aaae  jz      loc_18002AB75
0x18002aab4  mov     rax, rdi
0x18002aab7  inc     rax
0x18002aaba  cmp     [rsi+rax*2], r9w
0x18002aabf  jnz     short loc_18002AAB7
0x18002aac1  mov     ecx, r8d
0x18002aac4  sub     rcx, rax
0x18002aac7  dec     rcx
0x18002aaca  cmp     rdx, rcx
0x18002aacd  jb      loc_18002AB75
0x18002aad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aada  cmp     rcx, rbp
0x18002aadd  jz      short loc_18002AB07
0x18002aadf  test    byte ptr [rcx+1Ch], 2
0x18002aae3  jz      short loc_18002AB07
0x18002aae5  mov     rcx, [rcx+10h]
0x18002aae9  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002aaf0  mov     edx, 24h ; '$'
0x18002aaf5  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r12
0x18002aafa  mov     r9, rsi
0x18002aafd  call    WPP_SF_SS
0x18002ab02  mov     edx, [rbx]; cchDest
0x18002ab04  xor     r9d, r9d
0x18002ab07  mov     rsi, r9
0x18002ab0a  mov     r8, [r13+30h]; pszSrc
0x18002ab0e  mov     rcx, r14; pszDest
0x18002ab11  call    StringCchCopyW
0x18002ab16  mov     eax, [r13+28h]
0x18002ab1a  lea     rcx, [rsp+0C8h+Uuid]; Uuid
0x18002ab1f  mov     [rsp+0C8h+var_88], rax
0x18002ab24  mov     word ptr [r14+rax*2], 5Ch ; '\'
0x18002ab2b  call    cs:__imp_UuidCreate
0x18002ab31  mov     ebx, eax
0x18002ab33  test    eax, eax
0x18002ab35  jz      short loc_18002AB82
0x18002ab37  cmp     eax, 720h
0x18002ab3c  jz      short loc_18002AB82
0x18002ab3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab45  cmp     rcx, rbp
0x18002ab48  jz      loc_18002ACB5
0x18002ab4e  test    byte ptr [rcx+1Ch], 1
0x18002ab52  jz      loc_18002ACB5
0x18002ab58  mov     rcx, [rcx+10h]
0x18002ab5c  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002ab63  mov     edx, 25h ; '%'
0x18002ab68  mov     r9d, eax
0x18002ab6b  call    WPP_SF_d
0x18002ab70  jmp     loc_18002ACB5
0x18002ab75  mov     [rbx], r8d
0x18002ab78  mov     ebx, 7Ah ; 'z'
0x18002ab7d  jmp     loc_18002ACB5
0x18002ab82  mov     rax, [rsp+0C8h+var_88]
0x18002ab87  mov     rcx, [rsp+0C8h+var_80]
0x18002ab8c  lea     rbx, [r14+rax*2]
0x18002ab90  mov     r8d, [rcx]
0x18002ab93  lea     rax, [rbx+2]
0x18002ab97  sub     rax, r14
0x18002ab9a  lea     rdx, [rbx+2]; lpsz
0x18002ab9e  sar     rax, 1
0x18002aba1  lea     rcx, [rsp+0C8h+Uuid]; rguid
0x18002aba6  sub     r8d, eax; cchMax
0x18002aba9  call    cs:__imp_StringFromGUID2
0x18002abaf  test    rsi, rsi
0x18002abb2  jz      short loc_18002ABD9
0x18002abb4  mov     rdx, [rsp+0C8h+var_80]
0x18002abb9  lea     rcx, [rbx+50h]; pszDest
0x18002abbd  mov     rax, rcx
0x18002abc0  mov     word ptr [rbx+4Eh], 2Eh ; '.'
0x18002abc6  sub     rax, r14
0x18002abc9  mov     r8, rsi; pszSrc
0x18002abcc  sar     rax, 1
0x18002abcf  mov     edx, [rdx]
0x18002abd1  sub     rdx, rax; cchDest
0x18002abd4  call    StringCchCopyW
0x18002abd9  xor     ebx, ebx
0x18002abdb  mov     edx, 80h; dwDesiredAccess
0x18002abe0  mov     [rsp+0C8h+hTemplateFile], rbx; hTemplateFile
0x18002abe5  xor     r9d, r9d; lpSecurityAttributes
0x18002abe8  mov     [rsp+0C8h+dwFlagsAndAttributes], edx; dwFlagsAndAttributes
0x18002abec  mov     rcx, r14; lpFileName
0x18002abef  mov     [rsp+0C8h+dwCreationDisposition], 1; dwCreationDisposition
0x18002abf7  lea     r8d, [rbx+1]; dwShareMode
0x18002abfb  call    cs:__imp_CreateFileW
0x18002ac01  cmp     rax, rdi
0x18002ac04  jnz     short loc_18002AC2E
0x18002ac06  call    cs:__imp_GetLastError
0x18002ac0c  mov     esi, eax
0x18002ac0e  cmp     eax, 0B7h
0x18002ac13  jz      short loc_18002AC24
0x18002ac15  cmp     eax, 50h ; 'P'
0x18002ac18  jz      short loc_18002AC24
0x18002ac1a  test    eax, eax
0x18002ac1c  jnz     loc_18002ADC8
0x18002ac22  jmp     short loc_18002AC39
0x18002ac24  mov     esi, 57h ; 'W'
0x18002ac29  jmp     loc_18002ADC8
0x18002ac2e  mov     rcx, rax; hObject
0x18002ac31  mov     esi, ebx
0x18002ac33  call    cs:__imp_CloseHandle
0x18002ac39  mov     rcx, r12
0x18002ac3c  call    TfsGetHashId
0x18002ac41  mov     dword ptr [rsp+0C8h+var_88], eax
0x18002ac45  mov     rcx, rdi
0x18002ac48  inc     rcx
0x18002ac4b  cmp     [r12+rcx*2], bx
0x18002ac50  jnz     short loc_18002AC48
0x18002ac52  mov     rax, rdi
0x18002ac55  inc     rax
0x18002ac58  cmp     [r14+rax*2], bx
0x18002ac5d  jnz     short loc_18002AC55
0x18002ac5f  add     eax, ecx
0x18002ac61  mov     ecx, 40h ; '@'; uFlags
0x18002ac66  lea     eax, ds:64h[rax*2]
0x18002ac6d  mov     edx, eax; uBytes
0x18002ac6f  mov     [rsp+0C8h+var_78], eax
0x18002ac73  call    cs:__imp_LocalAlloc
0x18002ac79  xor     edx, edx
0x18002ac7b  mov     rbx, rax
0x18002ac7e  test    rax, rax
0x18002ac81  jnz     short loc_18002ACC7
0x18002ac83  call    cs:__imp_GetLastError
0x18002ac89  mov     ebx, eax
0x18002ac8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac92  cmp     rcx, rbp
0x18002ac95  jz      short loc_18002ACB5
0x18002ac97  test    byte ptr [rcx+1Ch], 1
0x18002ac9b  jz      short loc_18002ACB5
0x18002ac9d  mov     edx, 26h ; '&'
0x18002aca2  mov     rcx, [rcx+10h]
0x18002aca6  lea     r8, WPP_5f1a3cf1cc213e2c9d1db611a3b6a3c0_Traceguids
0x18002acad  mov     r9d, eax
0x18002acb0  call    WPP_SF_d
0x18002acb5  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x18002acba  call    cs:__imp_LeaveCriticalSection
0x18002acc0  mov     eax, ebx
0x18002acc2  jmp     loc_18002ADD5
0x18002acc7  mov     eax, [rsp+0C8h+var_78]
0x18002accb  mov     [rbx+10h], eax
0x18002acce  mov     rax, rdi
0x18002acd1  mov     [rbx+14h], rdx
0x18002acd5  inc     rax
0x18002acd8  cmp     [r12+rax*2], dx
0x18002acdd  jnz     short loc_18002ACD5
0x18002acdf  mov     [rbx+1Ch], eax
0x18002ace2  lea     rax, [rbx+60h]
0x18002ace6  mov     [rbx+20h], rax
0x18002acea  mov     rax, rdi
0x18002aced  inc     rax
0x18002acf0  cmp     [r14+rax*2], dx
0x18002acf5  jnz     short loc_18002ACED
0x18002acf7  mov     [rbx+28h], eax
0x18002acfa  mov     rax, [rbx+20h]
0x18002acfe  mov     ecx, [rbx+1Ch]
0x18002ad01  add     rax, 2
0x18002ad05  lea     rcx, [rax+rcx*2]
0x18002ad09  mov     [rbx+30h], rcx
0x18002ad0d  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x18002ad12  mov     [rbx+38h], edx
0x18002ad15  mov     [rbx+40h], rdx
0x18002ad19  mov     [rbx+48h], rdx
0x18002ad1d  mov     [rbx+50h], rdx
0x18002ad21  call    cs:__imp_GetSystemTime
0x18002ad27  lea     rdx, [rbx+58h]; lpFileTime
0x18002ad2b  lea     rcx, [rsp+0C8h+SystemTime]; lpSystemTime
0x18002ad30  call    cs:__imp_SystemTimeToFileTime
0x18002ad36  mov     edx, [rbx+1Ch]
0x18002ad39  mov     r8, r12; pszSrc
0x18002ad3c  mov     rcx, [rbx+20h]; pszDest
0x18002ad40  inc     edx; cchDest
0x18002ad42  call    StringCchCopyW
0x18002ad47  mov     edx, [rbx+28h]
0x18002ad4a  mov     r8, r14; pszSrc
0x18002ad4d  mov     rcx, [rbx+30h]; pszDest
0x18002ad51  inc     edx; cchDest
0x18002ad53  call    StringCchCopyW
0x18002ad58  mov     eax, dword ptr [rsp+0C8h+var_88]
0x18002ad5c  add     rax, 6
0x18002ad60  shl     rax, 4
0x18002ad64  add     rax, r13
0x18002ad67  mov     rcx, [rax+8]
0x18002ad6b  cmp     [rcx], rax
0x18002ad6e  jz      short loc_18002AD77
0x18002ad70  mov     ecx, 3
0x18002ad75  int     29h; Win8: RtlFailFast(ecx)
0x18002ad77  mov     [rbx], rax
0x18002ad7a  mov     [rbx+8], rcx
0x18002ad7e  mov     [rcx], rbx
0x18002ad81  mov     [rax+8], rbx
0x18002ad85  xor     eax, eax
0x18002ad87  inc     rdi
0x18002ad8a  cmp     [r14+rdi*2], ax
0x18002ad8f  jnz     short loc_18002AD87
0x18002ad91  mov     rcx, [rsp+0C8h+var_80]
0x18002ad96  lea     eax, [rdi+1]
0x18002ad99  mov     [rcx], eax
0x18002ad9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ada2  cmp     rcx, rbp
0x18002ada5  jz      short loc_18002ADC8
0x18002ada7  test    byte ptr [rcx+1Ch], 2
0x18002adab  jz      short loc_18002ADC8
0x18002adad  mov     rcx, [rcx+10h]
0x18002adb1  mov     edx, 27h ; '''
0x18002adb6  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], r12
0x18002adbb  mov     r9, rbx
0x18002adbe  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r14
0x18002adc3  call    WPP_SF_qSS
0x18002adc8  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x18002adcd  call    cs:__imp_LeaveCriticalSection
0x18002add3  mov     eax, esi
0x18002add5  mov     rcx, [rsp+0C8h+var_48]
0x18002addd  xor     rcx, rsp; StackCookie
0x18002ade0  call    __security_check_cookie
0x18002ade5  add     rsp, 90h
0x18002adec  pop     r14
0x18002adee  pop     r13
  ... truncated ...
```

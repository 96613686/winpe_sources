# BitsHelper::GetActiveUserToken(void * *)

- ea: `0x14000ff7c`
- end: `0x1400100da`
- name: `?GetActiveUserToken@BitsHelper@@AEAAJPEAPEAX@Z`
- size: `350`
- prototype: `int __fastcall(BitsHelper *this, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400100e0`
- `0x140010ce8`

## callees

- `0x140003cb0`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000a4e0`
- `0x14000ff7c`
- `0x140011418`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x14001004a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400100ad`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x14001004a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1400100ad`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140010080`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x140010080`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x140010017`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x140010017`

## string_xrefs

- `0x14000ffc6`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001002a`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400100bb`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
int __fastcall BitsHelper::GetActiveUserToken(BitsHelper *this, void **a2)
{
  BitsHelper *v3; // rcx
  int IsLocalSystem; // eax
  int LastError; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  DWORD v9; // ecx
  DWORD v10; // r8d
  __int64 v11; // r10
  PWTS_SESSION_INFO_1W v12; // rdx
  unsigned int pCount; // [rsp+20h] [rbp-20h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  BitsHelper *v16; // [rsp+60h] [rbp+20h] BYREF
  DWORD NumberOfEntries; // [rsp+70h] [rbp+30h] BYREF
  DWORD pLevel; // [rsp+78h] [rbp+38h] BYREF

  v16 = this;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1E2,
             (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
             (const char *)0x32,
             pCount);
  *a2 = 0;
  LOBYTE(v16) = 0;
  IsLocalSystem = BitsHelper::IsLocalSystem(v3, (bool *)&v16);
  LastError = IsLocalSystem;
  if ( IsLocalSystem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
      (const char *)(unsigned int)IsLocalSystem,
      pCount);
    return LastError;
  }
  if ( (_BYTE)v16 )
  {
    pLevel = 1;
    ppSessionInfo = 0;
    NumberOfEntries = 0;
    if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
    {
      v8 = 509;
LABEL_9:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v8,
                    (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                    v7);
      if ( ppSessionInfo )
        WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, ppSessionInfo, NumberOfEntries);
      return LastError;
    }
    v9 = 0;
    v10 = NumberOfEntries;
    while ( 1 )
    {
      if ( v9 >= NumberOfEntries )
        goto LABEL_20;
      v11 = v9;
      if ( ppSessionInfo[v11].State == WTSActive )
        break;
      ++v9;
    }
    if ( v9 == -1 )
    {
LABEL_20:
      if ( !ppSessionInfo )
        return 0;
      v12 = ppSessionInfo;
      goto LABEL_22;
    }
    if ( !WTSQueryUserToken(ppSessionInfo[v11].SessionId, a2) )
    {
      v8 = 529;
      goto LABEL_9;
    }
    v12 = ppSessionInfo;
    if ( ppSessionInfo )
    {
      v10 = NumberOfEntries;
LABEL_22:
      WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v12, v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000ff7c  mov     [rsp-18h+arg_0], rcx
0x14000ff81  push    rbp
0x14000ff82  push    rbx
0x14000ff83  push    rdi
0x14000ff84  mov     rbp, rsp
0x14000ff87  sub     rsp, 40h
0x14000ff8b  mov     rdi, rdx
0x14000ff8e  call    IsWTSEnumerateSessionsExWPresent
0x14000ff93  test    al, al
0x14000ff95  jz      loc_1400100B7
0x14000ff9b  call    IsWTSEnumerateSessionsExWPresent
0x14000ffa0  test    al, al
0x14000ffa2  jz      loc_1400100B7
0x14000ffa8  lea     rdx, [rbp+arg_0]; bool *
0x14000ffac  mov     qword ptr [rdi], 0
0x14000ffb3  mov     byte ptr [rbp+arg_0], 0
0x14000ffb7  call    ?IsLocalSystem@BitsHelper@@AEAAJPEA_N@Z; BitsHelper::IsLocalSystem(bool *)
0x14000ffbc  mov     ebx, eax
0x14000ffbe  test    eax, eax
0x14000ffc0  jns     short loc_14000FFE1
0x14000ffc2  mov     rcx, [rbp+18h]; this
0x14000ffc6  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14000ffcd  mov     r9d, eax; char *
0x14000ffd0  mov     edx, 1E8h; void *
0x14000ffd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ffda  mov     eax, ebx
0x14000ffdc  jmp     loc_1400100D2
0x14000ffe1  cmp     byte ptr [rbp+arg_0], 0
0x14000ffe5  jz      loc_1400100B3
0x14000ffeb  lea     rax, [rbp+NumberOfEntries]
0x14000ffef  mov     [rbp+pLevel], 1
0x14000fff6  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x14000fffa  mov     qword ptr [rsp+40h+pCount], rax; pCount
0x14000ffff  xor     r8d, r8d; Filter
0x140010002  mov     [rbp+ppSessionInfo], 0
0x14001000a  lea     rdx, [rbp+pLevel]; pLevel
0x14001000e  mov     [rbp+NumberOfEntries], 0
0x140010015  xor     ecx, ecx; hServer
0x140010017  call    cs:__imp_WTSEnumerateSessionsExW
0x14001001d  test    eax, eax
0x14001001f  jnz     short loc_140010052
0x140010021  mov     edx, 1FDh; void *
0x140010026  mov     rcx, [rbp+18h]; this
0x14001002a  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140010031  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010036  mov     rdx, [rbp+ppSessionInfo]; pMemory
0x14001003a  mov     ebx, eax
0x14001003c  test    rdx, rdx
0x14001003f  jz      short loc_14000FFDA
0x140010041  mov     r8d, [rbp+NumberOfEntries]; NumberOfEntries
0x140010045  mov     ecx, 2; WTSTypeClass
0x14001004a  call    cs:__imp_WTSFreeMemoryExW
0x140010050  jmp     short loc_14000FFDA
0x140010052  mov     r9, [rbp+ppSessionInfo]
0x140010056  xor     ecx, ecx
0x140010058  mov     r8d, [rbp+NumberOfEntries]; NumberOfEntries
0x14001005c  cmp     ecx, r8d
0x14001005f  jnb     short loc_1400100A0
0x140010061  mov     eax, ecx
0x140010063  imul    r10, rax, 38h ; '8'
0x140010067  cmp     dword ptr [r10+r9+4], 0
0x14001006d  jz      short loc_140010073
0x14001006f  inc     ecx
0x140010071  jmp     short loc_14001005C
0x140010073  cmp     ecx, 0FFFFFFFFh
0x140010076  jz      short loc_1400100A0
0x140010078  mov     ecx, [r10+r9+8]; SessionId
0x14001007d  mov     rdx, rdi; phToken
0x140010080  call    cs:__imp_WTSQueryUserToken
0x140010086  test    eax, eax
0x140010088  jnz     short loc_140010091
0x14001008a  mov     edx, 211h
0x14001008f  jmp     short loc_140010026
0x140010091  mov     rdx, [rbp+ppSessionInfo]
0x140010095  test    rdx, rdx
0x140010098  jz      short loc_1400100B3
0x14001009a  mov     r8d, [rbp+NumberOfEntries]
0x14001009e  jmp     short loc_1400100A8
0x1400100a0  test    r9, r9
0x1400100a3  jz      short loc_1400100B3
0x1400100a5  mov     rdx, r9; pMemory
0x1400100a8  mov     ecx, 2; WTSTypeClass
0x1400100ad  call    cs:__imp_WTSFreeMemoryExW
0x1400100b3  xor     eax, eax
0x1400100b5  jmp     short loc_1400100D2
0x1400100b7  mov     rcx, [rbp+18h]; this
0x1400100bb  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x1400100c2  mov     r9d, 32h ; '2'; char *
0x1400100c8  mov     edx, 1E2h; void *
0x1400100cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400100d2  add     rsp, 40h
0x1400100d6  pop     rdi
0x1400100d7  pop     rbx
0x1400100d8  pop     rbp
0x1400100d9  retn
```

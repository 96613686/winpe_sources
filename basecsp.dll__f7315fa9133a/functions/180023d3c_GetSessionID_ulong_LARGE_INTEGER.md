# GetSessionID(ulong *,_LARGE_INTEGER *)

- ea: `0x180023d3c`
- end: `0x180023ed2`
- name: `?GetSessionID@@YAKPEAKPEAT_LARGE_INTEGER@@@Z`
- size: `406`
- prototype: `unsigned int __fastcall(unsigned int *TokenInformation, union _LARGE_INTEGER *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023ed8`
- `0x180026fdc`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x180023d3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023dc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023db0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023db0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e08`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023e08`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180023e33`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x180023e33`
- `WTSAPI32!WTSFreeMemory` at `0x180023e66`
- `WTSAPI32!WTSFreeMemory` at `0x180023e66`

## pseudocode

```c
__int64 __fastcall GetSessionID(unsigned int *TokenInformation, union _LARGE_INTEGER *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  void *v6; // rcx
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR ppBuffer; // [rsp+78h] [rbp+38h] BYREF

  TokenHandle = 0;
  pBytesReturned = 0;
  ppBuffer = 0;
  WppTraceIndent(TokenInformation, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( !GetTokenInformation(TokenHandle, TokenSessionId, TokenInformation, 4u, &pBytesReturned)
      || !WTSQuerySessionInformationW(0, *TokenInformation, WTSSessionInfo, &ppBuffer, &pBytesReturned) )
    {
      LastError = GetLastError();
      goto LABEL_15;
    }
    if ( pBytesReturned != 216 )
    {
      LastError = -2146893820;
      goto LABEL_15;
    }
    *a2 = *(union _LARGE_INTEGER *)(ppBuffer + 88);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_15;
    *TokenInformation = -1;
    a2->QuadPart = 0;
  }
  LastError = 0;
LABEL_15:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  v6 = TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180023d3c  mov     [rsp-18h+arg_0], rbx
0x180023d41  mov     [rsp-18h+arg_8], rsi
0x180023d46  push    rbp
0x180023d47  push    rdi
0x180023d48  push    r15
0x180023d4a  mov     rbp, rsp
0x180023d4d  sub     rsp, 40h
0x180023d51  mov     rsi, rdx
0x180023d54  mov     [rbp+TokenHandle], 0
0x180023d5c  xor     edx, edx
0x180023d5e  mov     [rbp+pBytesReturned], 0
0x180023d65  mov     rdi, rcx
0x180023d68  mov     [rbp+ppBuffer], 0
0x180023d70  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023d75  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d7c  lea     r15, WPP_GLOBAL_Control
0x180023d83  cmp     rcx, r15
0x180023d86  jz      short loc_180023DB0
0x180023d88  test    byte ptr [rcx+1Ch], 2
0x180023d8c  jz      short loc_180023DB0
0x180023d8e  cmp     byte ptr [rcx+19h], 5
0x180023d92  jb      short loc_180023DB0
0x180023d94  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023d9b  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023da2  mov     rcx, [rcx+10h]
0x180023da6  mov     edx, 17h
0x180023dab  call    WPP_SF_s
0x180023db0  call    cs:__imp_GetCurrentThread
0x180023db6  mov     edx, 8; DesiredAccess
0x180023dbb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023dbf  mov     rcx, rax; ThreadHandle
0x180023dc2  lea     r8d, [rdx-7]; OpenAsSelf
0x180023dc6  call    cs:__imp_OpenThreadToken
0x180023dcc  test    eax, eax
0x180023dce  jnz     short loc_180023DEE
0x180023dd0  call    cs:__imp_GetLastError
0x180023dd6  mov     ebx, eax
0x180023dd8  cmp     eax, 3F0h
0x180023ddd  jnz     short loc_180023E5D
0x180023ddf  mov     dword ptr [rdi], 0FFFFFFFFh
0x180023de5  mov     qword ptr [rsi], 0
0x180023dec  jmp     short loc_180023E5B
0x180023dee  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180023df2  lea     rax, [rbp+pBytesReturned]
0x180023df6  mov     r9d, 4; TokenInformationLength
0x180023dfc  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180023e01  mov     r8, rdi; TokenInformation
0x180023e04  lea     edx, [r9+8]; TokenInformationClass
0x180023e08  call    cs:__imp_GetTokenInformation
0x180023e0e  test    eax, eax
0x180023e10  jnz     short loc_180023E1C
0x180023e12  call    cs:__imp_GetLastError
0x180023e18  mov     ebx, eax
0x180023e1a  jmp     short loc_180023E5D
0x180023e1c  mov     edx, [rdi]; SessionId
0x180023e1e  lea     rax, [rbp+pBytesReturned]
0x180023e22  lea     r9, [rbp+ppBuffer]; ppBuffer
0x180023e26  mov     [rsp+40h+ReturnLength], rax; pBytesReturned
0x180023e2b  mov     r8d, 18h; WTSInfoClass
0x180023e31  xor     ecx, ecx; hServer
0x180023e33  call    cs:__imp_WTSQuerySessionInformationW
0x180023e39  test    eax, eax
0x180023e3b  jz      short loc_180023E12
0x180023e3d  cmp     [rbp+pBytesReturned], 0D8h
0x180023e44  jz      short loc_180023E4D
0x180023e46  mov     ebx, 80090004h
0x180023e4b  jmp     short loc_180023E5D
0x180023e4d  mov     rax, [rbp+ppBuffer]
0x180023e51  mov     rcx, [rax+0B0h]
0x180023e58  mov     [rsi], rcx
0x180023e5b  xor     ebx, ebx
0x180023e5d  mov     rcx, [rbp+ppBuffer]; pMemory
0x180023e61  test    rcx, rcx
0x180023e64  jz      short loc_180023E6C
0x180023e66  call    cs:__imp_WTSFreeMemory
0x180023e6c  mov     rcx, [rbp+TokenHandle]; hObject
0x180023e70  test    rcx, rcx
0x180023e73  jz      short loc_180023E7B
0x180023e75  call    cs:__imp_CloseHandle
0x180023e7b  mov     edx, 1
0x180023e80  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e8c  cmp     rcx, r15
0x180023e8f  jz      short loc_180023EBD
0x180023e91  test    byte ptr [rcx+1Ch], 2
0x180023e95  jz      short loc_180023EBD
0x180023e97  cmp     byte ptr [rcx+19h], 5
0x180023e9b  jb      short loc_180023EBD
0x180023e9d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023ea4  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180023eab  mov     rcx, [rcx+10h]
0x180023eaf  mov     edx, 18h
0x180023eb4  mov     dword ptr [rsp+40h+ReturnLength], ebx
0x180023eb8  call    WPP_SF_sD
0x180023ebd  mov     rsi, [rsp+40h+arg_8]
0x180023ec2  mov     eax, ebx
0x180023ec4  mov     rbx, [rsp+40h+arg_0]
0x180023ec9  add     rsp, 40h
0x180023ecd  pop     r15
0x180023ecf  pop     rdi
0x180023ed0  pop     rbp
0x180023ed1  retn
```

# GetCurrentSid(_SE_SID &)

- ea: `0x140006064`
- end: `0x140006234`
- name: `?GetCurrentSid@@YAKAEAT_SE_SID@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a4a0`

## callees

- `0x1400016a0`
- `0x140006064`
- `0x14000bf20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400061bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1400061bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140006178`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140006178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400061c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400061c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400060cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400060cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400060de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400060de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140006097`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400060ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400060ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000620b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000620b`

## pseudocode

```c
__int64 __fastcall GetCurrentSid(PSID pDestinationSid)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 88;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_12;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 19;
LABEL_22:
        WPP_SF_d(v5[2], v6, &WPP_b0092361ee8d34528df1964c4db39788_Traceguids, LastError);
        goto LABEL_23;
      }
      goto LABEL_23;
    }
LABEL_12:
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = 0;
      if ( !CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
      {
        LastError = GetLastError();
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 22;
          goto LABEL_22;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 21;
        goto LABEL_22;
      }
    }
    goto LABEL_23;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 20;
    goto LABEL_22;
  }
LABEL_23:
  CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x140006064  mov     [rsp+arg_8], rbx
0x140006069  push    rdi
0x14000606a  sub     rsp, 0B0h
0x140006071  mov     rax, cs:__security_cookie
0x140006078  xor     rax, rsp
0x14000607b  mov     [rsp+0B8h+var_18], rax
0x140006083  mov     rdi, rcx
0x140006086  mov     [rsp+0B8h+TokenHandle], 0
0x14000608f  mov     [rsp+0B8h+TokenInformationLength], 58h ; 'X'
0x140006097  call    cs:__imp_GetCurrentThread
0x14000609d  mov     edx, 8; DesiredAccess
0x1400060a2  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1400060a7  mov     rcx, rax; ThreadHandle
0x1400060aa  lea     r8d, [rdx-7]; OpenAsSelf
0x1400060ae  call    cs:__imp_OpenThreadToken
0x1400060b4  test    eax, eax
0x1400060b6  jnz     loc_14000615A
0x1400060bc  call    cs:__imp_GetLastError
0x1400060c2  mov     ebx, eax
0x1400060c4  cmp     eax, 3F0h
0x1400060c9  jnz     short loc_140006125
0x1400060cb  call    cs:__imp_GetCurrentProcess
0x1400060d1  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1400060d6  mov     edx, 8; DesiredAccess
0x1400060db  mov     rcx, rax; ProcessHandle
0x1400060de  call    cs:__imp_OpenProcessToken
0x1400060e4  test    eax, eax
0x1400060e6  jnz     short loc_14000615A
0x1400060e8  call    cs:__imp_GetLastError
0x1400060ee  mov     ebx, eax
0x1400060f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060f7  lea     rax, WPP_GLOBAL_Control
0x1400060fe  cmp     rcx, rax
0x140006101  jz      loc_140006206
0x140006107  cmp     byte ptr [rcx+19h], 2
0x14000610b  jb      loc_140006206
0x140006111  test    byte ptr [rcx+1Ch], 1
0x140006115  jz      loc_140006206
0x14000611b  mov     edx, 13h
0x140006120  jmp     loc_1400061F3
0x140006125  mov     rcx, cs:WPP_GLOBAL_Control
0x14000612c  lea     rax, WPP_GLOBAL_Control
0x140006133  cmp     rcx, rax
0x140006136  jz      loc_140006206
0x14000613c  cmp     byte ptr [rcx+19h], 2
0x140006140  jb      loc_140006206
0x140006146  test    byte ptr [rcx+1Ch], 1
0x14000614a  jz      loc_140006206
0x140006150  mov     edx, 14h
0x140006155  jmp     loc_1400061F3
0x14000615a  mov     r9d, [rsp+0B8h+TokenInformationLength]; TokenInformationLength
0x14000615f  lea     rax, [rsp+0B8h+TokenInformationLength]
0x140006164  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x140006169  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14000616e  mov     edx, 1; TokenInformationClass
0x140006173  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x140006178  call    cs:__imp_GetTokenInformation
0x14000617e  test    eax, eax
0x140006180  jnz     short loc_1400061B0
0x140006182  call    cs:__imp_GetLastError
0x140006188  mov     ebx, eax
0x14000618a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006191  lea     rax, WPP_GLOBAL_Control
0x140006198  cmp     rcx, rax
0x14000619b  jz      short loc_140006206
0x14000619d  cmp     byte ptr [rcx+19h], 2
0x1400061a1  jb      short loc_140006206
0x1400061a3  test    byte ptr [rcx+1Ch], 1
0x1400061a7  jz      short loc_140006206
0x1400061a9  mov     edx, 15h
0x1400061ae  jmp     short loc_1400061F3
0x1400061b0  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x1400061b5  xor     ebx, ebx
0x1400061b7  mov     rdx, rdi; pDestinationSid
0x1400061ba  lea     ecx, [rbx+44h]; nDestinationSidLength
0x1400061bd  call    cs:__imp_CopySid
0x1400061c3  test    eax, eax
0x1400061c5  jnz     short loc_140006206
0x1400061c7  call    cs:__imp_GetLastError
0x1400061cd  mov     ebx, eax
0x1400061cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061d6  lea     rax, WPP_GLOBAL_Control
0x1400061dd  cmp     rcx, rax
0x1400061e0  jz      short loc_140006206
0x1400061e2  cmp     byte ptr [rcx+19h], 2
0x1400061e6  jb      short loc_140006206
0x1400061e8  test    byte ptr [rcx+1Ch], 1
0x1400061ec  jz      short loc_140006206
0x1400061ee  mov     edx, 16h
0x1400061f3  mov     rcx, [rcx+10h]
0x1400061f7  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x1400061fe  mov     r9d, ebx
0x140006201  call    WPP_SF_d
0x140006206  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x14000620b  call    cs:__imp_CloseHandle
0x140006211  mov     eax, ebx
0x140006213  mov     rcx, [rsp+0B8h+var_18]
0x14000621b  xor     rcx, rsp; StackCookie
0x14000621e  call    __security_check_cookie
0x140006223  mov     rbx, [rsp+0B8h+arg_8]
0x14000622b  add     rsp, 0B0h
0x140006232  pop     rdi
0x140006233  retn
```

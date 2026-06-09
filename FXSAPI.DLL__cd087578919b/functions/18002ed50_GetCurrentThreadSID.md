# GetCurrentThreadSID

- ea: `0x18002ed50`
- end: `0x18002f0e9`
- name: `GetCurrentThreadSID`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002dff4`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002ed50`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18002edfa`
- `KERNEL32!GetCurrentProcess` at `0x18002edfa`
- `KERNEL32!GetCurrentThread` at `0x18002edb3`
- `KERNEL32!GetCurrentThread` at `0x18002edb3`
- `KERNEL32!CloseHandle` at `0x18002f0a4`
- `KERNEL32!CloseHandle` at `0x18002f0a4`
- `KERNEL32!SetLastError` at `0x18002f0c1`
- `KERNEL32!SetLastError` at `0x18002f0c1`
- `KERNEL32!GetLastError` at `0x18002ede5`
- `KERNEL32!GetLastError` at `0x18002ee1f`
- `KERNEL32!GetLastError` at `0x18002eeb0`
- `KERNEL32!GetLastError` at `0x18002ef2c`
- `KERNEL32!GetLastError` at `0x18002ef65`
- `KERNEL32!GetLastError` at `0x18002f055`
- `KERNEL32!GetLastError` at `0x18002ede5`
- `KERNEL32!GetLastError` at `0x18002ee1f`
- `KERNEL32!GetLastError` at `0x18002eeb0`
- `KERNEL32!GetLastError` at `0x18002ef2c`
- `KERNEL32!GetLastError` at `0x18002ef65`
- `KERNEL32!GetLastError` at `0x18002f055`
- `ADVAPI32!CopySid` at `0x18002f045`
- `ADVAPI32!CopySid` at `0x18002f045`
- `ADVAPI32!IsValidSid` at `0x18002efa7`
- `ADVAPI32!IsValidSid` at `0x18002efa7`
- `ADVAPI32!OpenProcessToken` at `0x18002ee0f`
- `ADVAPI32!OpenProcessToken` at `0x18002ee0f`
- `ADVAPI32!GetLengthSid` at `0x18002efeb`
- `ADVAPI32!GetLengthSid` at `0x18002efeb`
- `ADVAPI32!OpenThreadToken` at `0x18002edd1`
- `ADVAPI32!OpenThreadToken` at `0x18002edd1`
- `ADVAPI32!GetTokenInformation` at `0x18002eea0`
- `ADVAPI32!GetTokenInformation` at `0x18002ef55`
- `ADVAPI32!GetTokenInformation` at `0x18002eea0`
- `ADVAPI32!GetTokenInformation` at `0x18002ef55`

## pseudocode

```c
void *GetCurrentThreadSID()
{
  void *v0; // r14
  PSID *v1; // r15
  DWORD v2; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  PSID *v8; // rax
  PSID v9; // rdi
  DWORD LengthSid; // esi
  void *v11; // rax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v1 = 0;
  TokenInformationLength = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_16;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v2 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 48;
LABEL_51:
        WPP_SF_d(v6[2], v7, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
        goto LABEL_52;
      }
      goto LABEL_52;
    }
LABEL_16:
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError != 122 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 50;
          goto LABEL_51;
        }
        goto LABEL_52;
      }
      v2 = 0;
    }
    v8 = (PSID *)pMemAlloc(TokenInformationLength);
    v1 = v8;
    if ( v8 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
      {
        v9 = *v1;
        if ( IsValidSid(*v1) )
        {
          LengthSid = GetLengthSid(v9);
          v11 = (void *)pMemAlloc(LengthSid);
          v0 = v11;
          if ( v11 )
          {
            if ( !CopySid(LengthSid, v11, v9) )
            {
              LastError = GetLastError();
              v2 = LastError;
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 55;
                goto LABEL_51;
              }
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                54,
                WPP_db036311db36307996a98c23702218b2_Traceguids,
                LengthSid);
            }
            v2 = 14;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_db036311db36307996a98c23702218b2_Traceguids);
          }
          v2 = 1337;
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 52;
          goto LABEL_51;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_db036311db36307996a98c23702218b2_Traceguids,
          TokenInformationLength);
      }
      v2 = GetLastError();
    }
    goto LABEL_52;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 49;
    goto LABEL_51;
  }
LABEL_52:
  pMemFree(v1);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
  {
    pMemFree(v0);
    v0 = 0;
    SetLastError(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18002ed50  mov     [rsp-38h+arg_10], rbx
0x18002ed55  push    rbp
0x18002ed56  push    rsi
0x18002ed57  push    rdi
0x18002ed58  push    r12
0x18002ed5a  push    r13
0x18002ed5c  push    r14
0x18002ed5e  push    r15
0x18002ed60  mov     rbp, rsp
0x18002ed63  sub     rsp, 30h
0x18002ed67  xor     r14d, r14d
0x18002ed6a  mov     [rbp+TokenHandle], 0
0x18002ed72  xor     r15d, r15d
0x18002ed75  mov     [rbp+TokenInformationLength], r14d
0x18002ed79  xor     ebx, ebx
0x18002ed7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed82  lea     r13, WPP_GLOBAL_Control
0x18002ed89  lea     rsi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002ed90  mov     r12b, 2
0x18002ed93  cmp     rcx, r13
0x18002ed96  jz      short loc_18002EDB3
0x18002ed98  test    [rcx+1Ch], r12b
0x18002ed9c  jz      short loc_18002EDB3
0x18002ed9e  cmp     byte ptr [rcx+19h], 5
0x18002eda2  jb      short loc_18002EDB3
0x18002eda4  mov     rcx, [rcx+10h]
0x18002eda8  lea     edx, [rbx+2Fh]
0x18002edab  mov     r8, rsi
0x18002edae  call    WPP_SF_
0x18002edb3  call    cs:__imp_GetCurrentThread
0x18002edba  nop     dword ptr [rax+rax+00h]
0x18002edbf  mov     edi, 8
0x18002edc4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002edc8  mov     rcx, rax; ThreadHandle
0x18002edcb  mov     edx, edi; DesiredAccess
0x18002edcd  lea     r8d, [rdi-7]; OpenAsSelf
0x18002edd1  call    cs:__imp_OpenThreadToken
0x18002edd8  nop     dword ptr [rax+rax+00h]
0x18002eddd  test    eax, eax
0x18002eddf  jnz     loc_18002EE87
0x18002ede5  call    cs:__imp_GetLastError
0x18002edec  nop     dword ptr [rax+rax+00h]
0x18002edf1  mov     ebx, eax
0x18002edf3  cmp     eax, 3F0h
0x18002edf8  jnz     short loc_18002EE5C
0x18002edfa  call    cs:__imp_GetCurrentProcess
0x18002ee01  nop     dword ptr [rax+rax+00h]
0x18002ee06  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002ee0a  mov     edx, edi; DesiredAccess
0x18002ee0c  mov     rcx, rax; ProcessHandle
0x18002ee0f  call    cs:__imp_OpenProcessToken
0x18002ee16  nop     dword ptr [rax+rax+00h]
0x18002ee1b  test    eax, eax
0x18002ee1d  jnz     short loc_18002EE87
0x18002ee1f  call    cs:__imp_GetLastError
0x18002ee26  nop     dword ptr [rax+rax+00h]
0x18002ee2b  mov     ebx, eax
0x18002ee2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee34  cmp     rcx, r13
0x18002ee37  jz      loc_18002F093
0x18002ee3d  test    [rcx+1Ch], r12b
0x18002ee41  jz      loc_18002F093
0x18002ee47  cmp     [rcx+19h], r12b
0x18002ee4b  jb      loc_18002F093
0x18002ee51  lea     edx, [rdi+28h]
0x18002ee54  mov     r8, rsi
0x18002ee57  jmp     loc_18002F087
0x18002ee5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee63  cmp     rcx, r13
0x18002ee66  jz      loc_18002F093
0x18002ee6c  test    [rcx+1Ch], r12b
0x18002ee70  jz      loc_18002F093
0x18002ee76  cmp     [rcx+19h], r12b
0x18002ee7a  jb      loc_18002F093
0x18002ee80  mov     edx, 31h ; '1'
0x18002ee85  jmp     short loc_18002EE54
0x18002ee87  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002ee8b  lea     rax, [rbp+TokenInformationLength]
0x18002ee8f  xor     r9d, r9d; TokenInformationLength
0x18002ee92  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002ee97  xor     r8d, r8d; TokenInformation
0x18002ee9a  lea     edi, [r9+1]
0x18002ee9e  mov     edx, edi; TokenInformationClass
0x18002eea0  call    cs:__imp_GetTokenInformation
0x18002eea7  nop     dword ptr [rax+rax+00h]
0x18002eeac  test    eax, eax
0x18002eeae  jnz     short loc_18002EEF1
0x18002eeb0  call    cs:__imp_GetLastError
0x18002eeb7  nop     dword ptr [rax+rax+00h]
0x18002eebc  mov     ebx, eax
0x18002eebe  cmp     eax, 7Ah ; 'z'
0x18002eec1  jz      short loc_18002EEEF
0x18002eec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eeca  cmp     rcx, r13
0x18002eecd  jz      loc_18002F093
0x18002eed3  test    [rcx+1Ch], r12b
0x18002eed7  jz      loc_18002F093
0x18002eedd  cmp     [rcx+19h], r12b
0x18002eee1  jb      loc_18002F093
0x18002eee7  lea     edx, [rdi+31h]
0x18002eeea  jmp     loc_18002EE54
0x18002eeef  xor     ebx, ebx
0x18002eef1  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x18002eef4  call    pMemAlloc
0x18002eef9  mov     r15, rax
0x18002eefc  test    rax, rax
0x18002eeff  jnz     short loc_18002EF3F
0x18002ef01  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef08  cmp     rcx, r13
0x18002ef0b  jz      short loc_18002EF2C
0x18002ef0d  test    [rcx+1Ch], r12b
0x18002ef11  jz      short loc_18002EF2C
0x18002ef13  cmp     [rcx+19h], r12b
0x18002ef17  jb      short loc_18002EF2C
0x18002ef19  mov     r9d, [rbp+TokenInformationLength]
0x18002ef1d  lea     edx, [rax+33h]
0x18002ef20  mov     rcx, [rcx+10h]
0x18002ef24  mov     r8, rsi
0x18002ef27  call    WPP_SF_d
0x18002ef2c  call    cs:__imp_GetLastError
0x18002ef33  nop     dword ptr [rax+rax+00h]
0x18002ef38  mov     ebx, eax
0x18002ef3a  jmp     loc_18002F093
0x18002ef3f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002ef43  lea     rax, [rbp+TokenInformationLength]
0x18002ef47  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002ef4b  mov     r8, r15; TokenInformation
0x18002ef4e  mov     edx, edi; TokenInformationClass
0x18002ef50  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002ef55  call    cs:__imp_GetTokenInformation
0x18002ef5c  nop     dword ptr [rax+rax+00h]
0x18002ef61  test    eax, eax
0x18002ef63  jnz     short loc_18002EFA1
0x18002ef65  call    cs:__imp_GetLastError
0x18002ef6c  nop     dword ptr [rax+rax+00h]
0x18002ef71  mov     ebx, eax
0x18002ef73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef7a  cmp     rcx, r13
0x18002ef7d  jz      loc_18002F093
0x18002ef83  test    [rcx+1Ch], r12b
0x18002ef87  jz      loc_18002F093
0x18002ef8d  cmp     [rcx+19h], r12b
0x18002ef91  jb      loc_18002F093
0x18002ef97  mov     edx, 34h ; '4'
0x18002ef9c  jmp     loc_18002EE54
0x18002efa1  mov     rdi, [r15]
0x18002efa4  mov     rcx, rdi; pSid
0x18002efa7  call    cs:__imp_IsValidSid
0x18002efae  nop     dword ptr [rax+rax+00h]
0x18002efb3  test    eax, eax
0x18002efb5  jnz     short loc_18002EFE8
0x18002efb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efbe  cmp     rcx, r13
0x18002efc1  jz      short loc_18002EFDE
0x18002efc3  test    [rcx+1Ch], r12b
0x18002efc7  jz      short loc_18002EFDE
0x18002efc9  cmp     [rcx+19h], r12b
0x18002efcd  jb      short loc_18002EFDE
0x18002efcf  mov     rcx, [rcx+10h]
0x18002efd3  lea     edx, [rax+35h]
0x18002efd6  mov     r8, rsi
0x18002efd9  call    WPP_SF_
0x18002efde  mov     ebx, 539h
0x18002efe3  jmp     loc_18002F093
0x18002efe8  mov     rcx, rdi; pSid
0x18002efeb  call    cs:__imp_GetLengthSid
0x18002eff2  nop     dword ptr [rax+rax+00h]
0x18002eff7  mov     ecx, eax; dwBytes
0x18002eff9  mov     esi, eax
0x18002effb  call    pMemAlloc
0x18002f000  mov     r14, rax
0x18002f003  test    rax, rax
0x18002f006  jnz     short loc_18002F03D
0x18002f008  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f00f  cmp     rcx, r13
0x18002f012  jz      short loc_18002F036
0x18002f014  test    [rcx+1Ch], r12b
0x18002f018  jz      short loc_18002F036
0x18002f01a  cmp     [rcx+19h], r12b
0x18002f01e  jb      short loc_18002F036
0x18002f020  mov     rcx, [rcx+10h]
0x18002f024  lea     edx, [rax+36h]
0x18002f027  mov     r9d, esi
0x18002f02a  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002f031  call    WPP_SF_d
0x18002f036  mov     ebx, 0Eh
0x18002f03b  jmp     short loc_18002F093
0x18002f03d  mov     r8, rdi; pSourceSid
0x18002f040  mov     rdx, rax; pDestinationSid
0x18002f043  mov     ecx, esi; nDestinationSidLength
0x18002f045  call    cs:__imp_CopySid
0x18002f04c  nop     dword ptr [rax+rax+00h]
0x18002f051  test    eax, eax
0x18002f053  jnz     short loc_18002F093
0x18002f055  call    cs:__imp_GetLastError
0x18002f05c  nop     dword ptr [rax+rax+00h]
0x18002f061  mov     ebx, eax
0x18002f063  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f06a  cmp     rcx, r13
0x18002f06d  jz      short loc_18002F093
0x18002f06f  test    [rcx+1Ch], r12b
0x18002f073  jz      short loc_18002F093
0x18002f075  cmp     [rcx+19h], r12b
0x18002f079  jb      short loc_18002F093
0x18002f07b  mov     edx, 37h ; '7'
0x18002f080  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002f087  mov     rcx, [rcx+10h]
0x18002f08b  mov     r9d, eax
0x18002f08e  call    WPP_SF_d
0x18002f093  mov     rcx, r15; lpMem
0x18002f096  call    pMemFree
0x18002f09b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002f09f  test    rcx, rcx
0x18002f0a2  jz      short loc_18002F0B0
0x18002f0a4  call    cs:__imp_CloseHandle
0x18002f0ab  nop     dword ptr [rax+rax+00h]
0x18002f0b0  test    ebx, ebx
0x18002f0b2  jz      short loc_18002F0CD
0x18002f0b4  mov     rcx, r14; lpMem
0x18002f0b7  call    pMemFree
0x18002f0bc  mov     ecx, ebx; dwErrCode
0x18002f0be  xor     r14d, r14d
0x18002f0c1  call    cs:__imp_SetLastError
0x18002f0c8  nop     dword ptr [rax+rax+00h]
0x18002f0cd  mov     rbx, [rsp+30h+arg_10]
0x18002f0d5  mov     rax, r14
0x18002f0d8  add     rsp, 30h
0x18002f0dc  pop     r15
0x18002f0de  pop     r14
0x18002f0e0  pop     r13
0x18002f0e2  pop     r12
0x18002f0e4  pop     rdi
0x18002f0e5  pop     rsi
0x18002f0e6  pop     rbp
0x18002f0e7  retn
```

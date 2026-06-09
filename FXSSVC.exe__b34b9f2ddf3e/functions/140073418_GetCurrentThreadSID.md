# GetCurrentThreadSID

- ea: `0x140073418`
- end: `0x14007374a`
- name: `GetCurrentThreadSID`
- size: `818`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400452ac`
- `0x140045798`
- `0x140072970`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x140073418`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14007366b`
- `ADVAPI32!GetLengthSid` at `0x14007366b`
- `ADVAPI32!IsValidSid` at `0x14007362d`
- `ADVAPI32!IsValidSid` at `0x14007362d`
- `ADVAPI32!OpenProcessToken` at `0x1400734bf`
- `ADVAPI32!OpenProcessToken` at `0x1400734bf`
- `ADVAPI32!OpenThreadToken` at `0x140073493`
- `ADVAPI32!OpenThreadToken` at `0x140073493`
- `ADVAPI32!GetTokenInformation` at `0x140073544`
- `ADVAPI32!GetTokenInformation` at `0x1400735e7`
- `ADVAPI32!GetTokenInformation` at `0x140073544`
- `ADVAPI32!GetTokenInformation` at `0x1400735e7`
- `ADVAPI32!CopySid` at `0x1400736bf`
- `ADVAPI32!CopySid` at `0x1400736bf`
- `KERNEL32!GetLastError` at `0x1400734a1`
- `KERNEL32!GetLastError` at `0x1400734c9`
- `KERNEL32!GetLastError` at `0x14007354e`
- `KERNEL32!GetLastError` at `0x1400735c4`
- `KERNEL32!GetLastError` at `0x1400735f1`
- `KERNEL32!GetLastError` at `0x1400736c9`
- `KERNEL32!GetLastError` at `0x1400734a1`
- `KERNEL32!GetLastError` at `0x1400734c9`
- `KERNEL32!GetLastError` at `0x14007354e`
- `KERNEL32!GetLastError` at `0x1400735c4`
- `KERNEL32!GetLastError` at `0x1400735f1`
- `KERNEL32!GetLastError` at `0x1400736c9`
- `KERNEL32!SetLastError` at `0x140073729`
- `KERNEL32!SetLastError` at `0x140073729`
- `KERNEL32!CloseHandle` at `0x140073712`
- `KERNEL32!CloseHandle` at `0x140073712`
- `KERNEL32!GetCurrentThread` at `0x14007347b`
- `KERNEL32!GetCurrentThread` at `0x14007347b`
- `KERNEL32!GetCurrentProcess` at `0x1400734b0`
- `KERNEL32!GetCurrentProcess` at `0x1400734b0`

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
  CMapDeviceId *v6; // rcx
  __int64 v7; // rdx
  PSID *v8; // rax
  PSID v9; // rdi
  DWORD LengthSid; // esi
  void *v11; // rax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  v0 = 0;
  TokenHandle = 0;
  v1 = 0;
  TokenInformationLength = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 48;
LABEL_51:
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
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
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
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
0x140073418  mov     [rsp-38h+arg_10], rbx
0x14007341d  push    rbp
0x14007341e  push    rsi
0x14007341f  push    rdi
0x140073420  push    r12
0x140073422  push    r13
0x140073424  push    r14
0x140073426  push    r15
0x140073428  mov     rbp, rsp
0x14007342b  sub     rsp, 30h
0x14007342f  xor     r14d, r14d
0x140073432  mov     [rbp+TokenHandle], 0
0x14007343a  xor     r15d, r15d
0x14007343d  mov     [rbp+TokenInformationLength], r14d
0x140073441  xor     ebx, ebx
0x140073443  mov     rcx, cs:WPP_GLOBAL_Control
0x14007344a  lea     r13, WPP_GLOBAL_Control
0x140073451  lea     rsi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073458  mov     r12b, 2
0x14007345b  cmp     rcx, r13
0x14007345e  jz      short loc_14007347B
0x140073460  test    [rcx+1Ch], r12b
0x140073464  jz      short loc_14007347B
0x140073466  cmp     byte ptr [rcx+19h], 5
0x14007346a  jb      short loc_14007347B
0x14007346c  mov     rcx, [rcx+10h]
0x140073470  lea     edx, [rbx+2Fh]
0x140073473  mov     r8, rsi
0x140073476  call    WPP_SF_
0x14007347b  call    cs:__imp_GetCurrentThread
0x140073481  mov     edi, 8
0x140073486  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14007348a  mov     rcx, rax; ThreadHandle
0x14007348d  mov     edx, edi; DesiredAccess
0x14007348f  lea     r8d, [rdi-7]; OpenAsSelf
0x140073493  call    cs:__imp_OpenThreadToken
0x140073499  test    eax, eax
0x14007349b  jnz     loc_14007352B
0x1400734a1  call    cs:__imp_GetLastError
0x1400734a7  mov     ebx, eax
0x1400734a9  cmp     eax, 3F0h
0x1400734ae  jnz     short loc_140073500
0x1400734b0  call    cs:__imp_GetCurrentProcess
0x1400734b6  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400734ba  mov     edx, edi; DesiredAccess
0x1400734bc  mov     rcx, rax; ProcessHandle
0x1400734bf  call    cs:__imp_OpenProcessToken
0x1400734c5  test    eax, eax
0x1400734c7  jnz     short loc_14007352B
0x1400734c9  call    cs:__imp_GetLastError
0x1400734cf  mov     ebx, eax
0x1400734d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400734d8  cmp     rcx, r13
0x1400734db  jz      loc_140073701
0x1400734e1  test    [rcx+1Ch], r12b
0x1400734e5  jz      loc_140073701
0x1400734eb  cmp     [rcx+19h], r12b
0x1400734ef  jb      loc_140073701
0x1400734f5  lea     edx, [rdi+28h]
0x1400734f8  mov     r8, rsi
0x1400734fb  jmp     loc_1400736F5
0x140073500  mov     rcx, cs:WPP_GLOBAL_Control
0x140073507  cmp     rcx, r13
0x14007350a  jz      loc_140073701
0x140073510  test    [rcx+1Ch], r12b
0x140073514  jz      loc_140073701
0x14007351a  cmp     [rcx+19h], r12b
0x14007351e  jb      loc_140073701
0x140073524  mov     edx, 31h ; '1'
0x140073529  jmp     short loc_1400734F8
0x14007352b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14007352f  lea     rax, [rbp+TokenInformationLength]
0x140073533  xor     r9d, r9d; TokenInformationLength
0x140073536  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14007353b  xor     r8d, r8d; TokenInformation
0x14007353e  lea     edi, [r9+1]
0x140073542  mov     edx, edi; TokenInformationClass
0x140073544  call    cs:__imp_GetTokenInformation
0x14007354a  test    eax, eax
0x14007354c  jnz     short loc_140073589
0x14007354e  call    cs:__imp_GetLastError
0x140073554  mov     ebx, eax
0x140073556  cmp     eax, 7Ah ; 'z'
0x140073559  jz      short loc_140073587
0x14007355b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073562  cmp     rcx, r13
0x140073565  jz      loc_140073701
0x14007356b  test    [rcx+1Ch], r12b
0x14007356f  jz      loc_140073701
0x140073575  cmp     [rcx+19h], r12b
0x140073579  jb      loc_140073701
0x14007357f  lea     edx, [rdi+31h]
0x140073582  jmp     loc_1400734F8
0x140073587  xor     ebx, ebx
0x140073589  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x14007358c  call    pMemAlloc
0x140073591  mov     r15, rax
0x140073594  test    rax, rax
0x140073597  jnz     short loc_1400735D1
0x140073599  mov     rcx, cs:WPP_GLOBAL_Control
0x1400735a0  cmp     rcx, r13
0x1400735a3  jz      short loc_1400735C4
0x1400735a5  test    [rcx+1Ch], r12b
0x1400735a9  jz      short loc_1400735C4
0x1400735ab  cmp     [rcx+19h], r12b
0x1400735af  jb      short loc_1400735C4
0x1400735b1  mov     r9d, [rbp+TokenInformationLength]
0x1400735b5  lea     edx, [rax+33h]
0x1400735b8  mov     rcx, [rcx+10h]
0x1400735bc  mov     r8, rsi
0x1400735bf  call    WPP_SF_d
0x1400735c4  call    cs:__imp_GetLastError
0x1400735ca  mov     ebx, eax
0x1400735cc  jmp     loc_140073701
0x1400735d1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400735d5  lea     rax, [rbp+TokenInformationLength]
0x1400735d9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400735dd  mov     r8, r15; TokenInformation
0x1400735e0  mov     edx, edi; TokenInformationClass
0x1400735e2  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400735e7  call    cs:__imp_GetTokenInformation
0x1400735ed  test    eax, eax
0x1400735ef  jnz     short loc_140073627
0x1400735f1  call    cs:__imp_GetLastError
0x1400735f7  mov     ebx, eax
0x1400735f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140073600  cmp     rcx, r13
0x140073603  jz      loc_140073701
0x140073609  test    [rcx+1Ch], r12b
0x14007360d  jz      loc_140073701
0x140073613  cmp     [rcx+19h], r12b
0x140073617  jb      loc_140073701
0x14007361d  mov     edx, 34h ; '4'
0x140073622  jmp     loc_1400734F8
0x140073627  mov     rdi, [r15]
0x14007362a  mov     rcx, rdi; pSid
0x14007362d  call    cs:__imp_IsValidSid
0x140073633  test    eax, eax
0x140073635  jnz     short loc_140073668
0x140073637  mov     rcx, cs:WPP_GLOBAL_Control
0x14007363e  cmp     rcx, r13
0x140073641  jz      short loc_14007365E
0x140073643  test    [rcx+1Ch], r12b
0x140073647  jz      short loc_14007365E
0x140073649  cmp     [rcx+19h], r12b
0x14007364d  jb      short loc_14007365E
0x14007364f  mov     rcx, [rcx+10h]
0x140073653  lea     edx, [rax+35h]
0x140073656  mov     r8, rsi
0x140073659  call    WPP_SF_
0x14007365e  mov     ebx, 539h
0x140073663  jmp     loc_140073701
0x140073668  mov     rcx, rdi; pSid
0x14007366b  call    cs:__imp_GetLengthSid
0x140073671  mov     ecx, eax; dwBytes
0x140073673  mov     esi, eax
0x140073675  call    pMemAlloc
0x14007367a  mov     r14, rax
0x14007367d  test    rax, rax
0x140073680  jnz     short loc_1400736B7
0x140073682  mov     rcx, cs:WPP_GLOBAL_Control
0x140073689  cmp     rcx, r13
0x14007368c  jz      short loc_1400736B0
0x14007368e  test    [rcx+1Ch], r12b
0x140073692  jz      short loc_1400736B0
0x140073694  cmp     [rcx+19h], r12b
0x140073698  jb      short loc_1400736B0
0x14007369a  mov     rcx, [rcx+10h]
0x14007369e  lea     edx, [rax+36h]
0x1400736a1  mov     r9d, esi
0x1400736a4  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400736ab  call    WPP_SF_d
0x1400736b0  mov     ebx, 0Eh
0x1400736b5  jmp     short loc_140073701
0x1400736b7  mov     r8, rdi; pSourceSid
0x1400736ba  mov     rdx, rax; pDestinationSid
0x1400736bd  mov     ecx, esi; nDestinationSidLength
0x1400736bf  call    cs:__imp_CopySid
0x1400736c5  test    eax, eax
0x1400736c7  jnz     short loc_140073701
0x1400736c9  call    cs:__imp_GetLastError
0x1400736cf  mov     ebx, eax
0x1400736d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400736d8  cmp     rcx, r13
0x1400736db  jz      short loc_140073701
0x1400736dd  test    [rcx+1Ch], r12b
0x1400736e1  jz      short loc_140073701
0x1400736e3  cmp     [rcx+19h], r12b
0x1400736e7  jb      short loc_140073701
0x1400736e9  mov     edx, 37h ; '7'
0x1400736ee  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400736f5  mov     rcx, [rcx+10h]
0x1400736f9  mov     r9d, eax
0x1400736fc  call    WPP_SF_d
0x140073701  mov     rcx, r15; lpMem
0x140073704  call    pMemFree
0x140073709  mov     rcx, [rbp+TokenHandle]; hObject
0x14007370d  test    rcx, rcx
0x140073710  jz      short loc_140073718
0x140073712  call    cs:__imp_CloseHandle
0x140073718  test    ebx, ebx
0x14007371a  jz      short loc_14007372F
0x14007371c  mov     rcx, r14; lpMem
0x14007371f  call    pMemFree
0x140073724  mov     ecx, ebx; dwErrCode
0x140073726  xor     r14d, r14d
0x140073729  call    cs:__imp_SetLastError
0x14007372f  mov     rbx, [rsp+30h+arg_10]
0x140073737  mov     rax, r14
0x14007373a  add     rsp, 30h
0x14007373e  pop     r15
0x140073740  pop     r14
0x140073742  pop     r13
0x140073744  pop     r12
0x140073746  pop     rdi
0x140073747  pop     rsi
0x140073748  pop     rbp
0x140073749  retn
```

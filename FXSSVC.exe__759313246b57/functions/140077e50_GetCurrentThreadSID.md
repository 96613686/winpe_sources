# GetCurrentThreadSID

- ea: `0x140077e50`
- end: `0x1400781e9`
- name: `GetCurrentThreadSID`
- size: `921`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140047d20`
- `0x140048284`
- `0x1400772c8`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x140077e50`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x1400780eb`
- `ADVAPI32!GetLengthSid` at `0x1400780eb`
- `ADVAPI32!IsValidSid` at `0x1400780a7`
- `ADVAPI32!IsValidSid` at `0x1400780a7`
- `ADVAPI32!OpenProcessToken` at `0x140077f0f`
- `ADVAPI32!OpenProcessToken` at `0x140077f0f`
- `ADVAPI32!OpenThreadToken` at `0x140077ed1`
- `ADVAPI32!OpenThreadToken` at `0x140077ed1`
- `ADVAPI32!GetTokenInformation` at `0x140077fa0`
- `ADVAPI32!GetTokenInformation` at `0x140078055`
- `ADVAPI32!GetTokenInformation` at `0x140077fa0`
- `ADVAPI32!GetTokenInformation` at `0x140078055`
- `ADVAPI32!CopySid` at `0x140078145`
- `ADVAPI32!CopySid` at `0x140078145`
- `KERNEL32!GetLastError` at `0x140077ee5`
- `KERNEL32!GetLastError` at `0x140077f1f`
- `KERNEL32!GetLastError` at `0x140077fb0`
- `KERNEL32!GetLastError` at `0x14007802c`
- `KERNEL32!GetLastError` at `0x140078065`
- `KERNEL32!GetLastError` at `0x140078155`
- `KERNEL32!GetLastError` at `0x140077ee5`
- `KERNEL32!GetLastError` at `0x140077f1f`
- `KERNEL32!GetLastError` at `0x140077fb0`
- `KERNEL32!GetLastError` at `0x14007802c`
- `KERNEL32!GetLastError` at `0x140078065`
- `KERNEL32!GetLastError` at `0x140078155`
- `KERNEL32!SetLastError` at `0x1400781c1`
- `KERNEL32!SetLastError` at `0x1400781c1`
- `KERNEL32!CloseHandle` at `0x1400781a4`
- `KERNEL32!CloseHandle` at `0x1400781a4`
- `KERNEL32!GetCurrentThread` at `0x140077eb3`
- `KERNEL32!GetCurrentThread` at `0x140077eb3`
- `KERNEL32!GetCurrentProcess` at `0x140077efa`
- `KERNEL32!GetCurrentProcess` at `0x140077efa`

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
0x140077e50  mov     [rsp-38h+arg_10], rbx
0x140077e55  push    rbp
0x140077e56  push    rsi
0x140077e57  push    rdi
0x140077e58  push    r12
0x140077e5a  push    r13
0x140077e5c  push    r14
0x140077e5e  push    r15
0x140077e60  mov     rbp, rsp
0x140077e63  sub     rsp, 30h
0x140077e67  xor     r14d, r14d
0x140077e6a  mov     [rbp+TokenHandle], 0
0x140077e72  xor     r15d, r15d
0x140077e75  mov     [rbp+TokenInformationLength], r14d
0x140077e79  xor     ebx, ebx
0x140077e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077e82  lea     r13, WPP_GLOBAL_Control
0x140077e89  lea     rsi, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077e90  mov     r12b, 2
0x140077e93  cmp     rcx, r13
0x140077e96  jz      short loc_140077EB3
0x140077e98  test    [rcx+1Ch], r12b
0x140077e9c  jz      short loc_140077EB3
0x140077e9e  cmp     byte ptr [rcx+19h], 5
0x140077ea2  jb      short loc_140077EB3
0x140077ea4  mov     rcx, [rcx+10h]
0x140077ea8  lea     edx, [rbx+2Fh]
0x140077eab  mov     r8, rsi
0x140077eae  call    WPP_SF_
0x140077eb3  call    cs:__imp_GetCurrentThread
0x140077eba  nop     dword ptr [rax+rax+00h]
0x140077ebf  mov     edi, 8
0x140077ec4  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140077ec8  mov     rcx, rax; ThreadHandle
0x140077ecb  mov     edx, edi; DesiredAccess
0x140077ecd  lea     r8d, [rdi-7]; OpenAsSelf
0x140077ed1  call    cs:__imp_OpenThreadToken
0x140077ed8  nop     dword ptr [rax+rax+00h]
0x140077edd  test    eax, eax
0x140077edf  jnz     loc_140077F87
0x140077ee5  call    cs:__imp_GetLastError
0x140077eec  nop     dword ptr [rax+rax+00h]
0x140077ef1  mov     ebx, eax
0x140077ef3  cmp     eax, 3F0h
0x140077ef8  jnz     short loc_140077F5C
0x140077efa  call    cs:__imp_GetCurrentProcess
0x140077f01  nop     dword ptr [rax+rax+00h]
0x140077f06  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140077f0a  mov     edx, edi; DesiredAccess
0x140077f0c  mov     rcx, rax; ProcessHandle
0x140077f0f  call    cs:__imp_OpenProcessToken
0x140077f16  nop     dword ptr [rax+rax+00h]
0x140077f1b  test    eax, eax
0x140077f1d  jnz     short loc_140077F87
0x140077f1f  call    cs:__imp_GetLastError
0x140077f26  nop     dword ptr [rax+rax+00h]
0x140077f2b  mov     ebx, eax
0x140077f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f34  cmp     rcx, r13
0x140077f37  jz      loc_140078193
0x140077f3d  test    [rcx+1Ch], r12b
0x140077f41  jz      loc_140078193
0x140077f47  cmp     [rcx+19h], r12b
0x140077f4b  jb      loc_140078193
0x140077f51  lea     edx, [rdi+28h]
0x140077f54  mov     r8, rsi
0x140077f57  jmp     loc_140078187
0x140077f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f63  cmp     rcx, r13
0x140077f66  jz      loc_140078193
0x140077f6c  test    [rcx+1Ch], r12b
0x140077f70  jz      loc_140078193
0x140077f76  cmp     [rcx+19h], r12b
0x140077f7a  jb      loc_140078193
0x140077f80  mov     edx, 31h ; '1'
0x140077f85  jmp     short loc_140077F54
0x140077f87  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140077f8b  lea     rax, [rbp+TokenInformationLength]
0x140077f8f  xor     r9d, r9d; TokenInformationLength
0x140077f92  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140077f97  xor     r8d, r8d; TokenInformation
0x140077f9a  lea     edi, [r9+1]
0x140077f9e  mov     edx, edi; TokenInformationClass
0x140077fa0  call    cs:__imp_GetTokenInformation
0x140077fa7  nop     dword ptr [rax+rax+00h]
0x140077fac  test    eax, eax
0x140077fae  jnz     short loc_140077FF1
0x140077fb0  call    cs:__imp_GetLastError
0x140077fb7  nop     dword ptr [rax+rax+00h]
0x140077fbc  mov     ebx, eax
0x140077fbe  cmp     eax, 7Ah ; 'z'
0x140077fc1  jz      short loc_140077FEF
0x140077fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140077fca  cmp     rcx, r13
0x140077fcd  jz      loc_140078193
0x140077fd3  test    [rcx+1Ch], r12b
0x140077fd7  jz      loc_140078193
0x140077fdd  cmp     [rcx+19h], r12b
0x140077fe1  jb      loc_140078193
0x140077fe7  lea     edx, [rdi+31h]
0x140077fea  jmp     loc_140077F54
0x140077fef  xor     ebx, ebx
0x140077ff1  mov     ecx, [rbp+TokenInformationLength]; dwBytes
0x140077ff4  call    pMemAlloc
0x140077ff9  mov     r15, rax
0x140077ffc  test    rax, rax
0x140077fff  jnz     short loc_14007803F
0x140078001  mov     rcx, cs:WPP_GLOBAL_Control
0x140078008  cmp     rcx, r13
0x14007800b  jz      short loc_14007802C
0x14007800d  test    [rcx+1Ch], r12b
0x140078011  jz      short loc_14007802C
0x140078013  cmp     [rcx+19h], r12b
0x140078017  jb      short loc_14007802C
0x140078019  mov     r9d, [rbp+TokenInformationLength]
0x14007801d  lea     edx, [rax+33h]
0x140078020  mov     rcx, [rcx+10h]
0x140078024  mov     r8, rsi
0x140078027  call    WPP_SF_d
0x14007802c  call    cs:__imp_GetLastError
0x140078033  nop     dword ptr [rax+rax+00h]
0x140078038  mov     ebx, eax
0x14007803a  jmp     loc_140078193
0x14007803f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140078043  lea     rax, [rbp+TokenInformationLength]
0x140078047  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14007804b  mov     r8, r15; TokenInformation
0x14007804e  mov     edx, edi; TokenInformationClass
0x140078050  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140078055  call    cs:__imp_GetTokenInformation
0x14007805c  nop     dword ptr [rax+rax+00h]
0x140078061  test    eax, eax
0x140078063  jnz     short loc_1400780A1
0x140078065  call    cs:__imp_GetLastError
0x14007806c  nop     dword ptr [rax+rax+00h]
0x140078071  mov     ebx, eax
0x140078073  mov     rcx, cs:WPP_GLOBAL_Control
0x14007807a  cmp     rcx, r13
0x14007807d  jz      loc_140078193
0x140078083  test    [rcx+1Ch], r12b
0x140078087  jz      loc_140078193
0x14007808d  cmp     [rcx+19h], r12b
0x140078091  jb      loc_140078193
0x140078097  mov     edx, 34h ; '4'
0x14007809c  jmp     loc_140077F54
0x1400780a1  mov     rdi, [r15]
0x1400780a4  mov     rcx, rdi; pSid
0x1400780a7  call    cs:__imp_IsValidSid
0x1400780ae  nop     dword ptr [rax+rax+00h]
0x1400780b3  test    eax, eax
0x1400780b5  jnz     short loc_1400780E8
0x1400780b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400780be  cmp     rcx, r13
0x1400780c1  jz      short loc_1400780DE
0x1400780c3  test    [rcx+1Ch], r12b
0x1400780c7  jz      short loc_1400780DE
0x1400780c9  cmp     [rcx+19h], r12b
0x1400780cd  jb      short loc_1400780DE
0x1400780cf  mov     rcx, [rcx+10h]
0x1400780d3  lea     edx, [rax+35h]
0x1400780d6  mov     r8, rsi
0x1400780d9  call    WPP_SF_
0x1400780de  mov     ebx, 539h
0x1400780e3  jmp     loc_140078193
0x1400780e8  mov     rcx, rdi; pSid
0x1400780eb  call    cs:__imp_GetLengthSid
0x1400780f2  nop     dword ptr [rax+rax+00h]
0x1400780f7  mov     ecx, eax; dwBytes
0x1400780f9  mov     esi, eax
0x1400780fb  call    pMemAlloc
0x140078100  mov     r14, rax
0x140078103  test    rax, rax
0x140078106  jnz     short loc_14007813D
0x140078108  mov     rcx, cs:WPP_GLOBAL_Control
0x14007810f  cmp     rcx, r13
0x140078112  jz      short loc_140078136
0x140078114  test    [rcx+1Ch], r12b
0x140078118  jz      short loc_140078136
0x14007811a  cmp     [rcx+19h], r12b
0x14007811e  jb      short loc_140078136
0x140078120  mov     rcx, [rcx+10h]
0x140078124  lea     edx, [rax+36h]
0x140078127  mov     r9d, esi
0x14007812a  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140078131  call    WPP_SF_d
0x140078136  mov     ebx, 0Eh
0x14007813b  jmp     short loc_140078193
0x14007813d  mov     r8, rdi; pSourceSid
0x140078140  mov     rdx, rax; pDestinationSid
0x140078143  mov     ecx, esi; nDestinationSidLength
0x140078145  call    cs:__imp_CopySid
0x14007814c  nop     dword ptr [rax+rax+00h]
0x140078151  test    eax, eax
0x140078153  jnz     short loc_140078193
0x140078155  call    cs:__imp_GetLastError
0x14007815c  nop     dword ptr [rax+rax+00h]
0x140078161  mov     ebx, eax
0x140078163  mov     rcx, cs:WPP_GLOBAL_Control
0x14007816a  cmp     rcx, r13
0x14007816d  jz      short loc_140078193
0x14007816f  test    [rcx+1Ch], r12b
0x140078173  jz      short loc_140078193
0x140078175  cmp     [rcx+19h], r12b
0x140078179  jb      short loc_140078193
0x14007817b  mov     edx, 37h ; '7'
0x140078180  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140078187  mov     rcx, [rcx+10h]
0x14007818b  mov     r9d, eax
0x14007818e  call    WPP_SF_d
0x140078193  mov     rcx, r15; lpMem
0x140078196  call    pMemFree
0x14007819b  mov     rcx, [rbp+TokenHandle]; hObject
0x14007819f  test    rcx, rcx
0x1400781a2  jz      short loc_1400781B0
0x1400781a4  call    cs:__imp_CloseHandle
0x1400781ab  nop     dword ptr [rax+rax+00h]
0x1400781b0  test    ebx, ebx
0x1400781b2  jz      short loc_1400781CD
0x1400781b4  mov     rcx, r14; lpMem
0x1400781b7  call    pMemFree
0x1400781bc  mov     ecx, ebx; dwErrCode
0x1400781be  xor     r14d, r14d
0x1400781c1  call    cs:__imp_SetLastError
0x1400781c8  nop     dword ptr [rax+rax+00h]
0x1400781cd  mov     rbx, [rsp+30h+arg_10]
0x1400781d5  mov     rax, r14
0x1400781d8  add     rsp, 30h
0x1400781dc  pop     r15
0x1400781de  pop     r14
0x1400781e0  pop     r13
0x1400781e2  pop     r12
0x1400781e4  pop     rdi
0x1400781e5  pop     rsi
0x1400781e6  pop     rbp
0x1400781e7  retn
```

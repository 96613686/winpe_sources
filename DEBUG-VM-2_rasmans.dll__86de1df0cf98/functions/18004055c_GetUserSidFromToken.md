# GetUserSidFromToken

- ea: `0x18004055c`
- end: `0x1800408e6`
- name: `GetUserSidFromToken`
- size: `906`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013f44`
- `0x180015c90`
- `0x180040428`

## callees

- `0x180005e34`
- `0x180005f1c`
- `0x18004055c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004061f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004061f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800405f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800405f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800405dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800405dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040610`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040897`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040897`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004062d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004062d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040819`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004080f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004080f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800406c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004077f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800406c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004077f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004071a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800407cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004071a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800407cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040872`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(void *a1, HLOCAL *a2)
{
  int v3; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  PSID *v10; // rdi
  DWORD v11; // eax
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  HLOCAL v14; // rax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 659, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1);
    a1 = TokenHandle;
  }
  TokenInformationLength = 0;
  if ( a1 != (void *)-1LL )
  {
    v3 = 0;
    if ( a1 )
    {
LABEL_22:
      if ( !GetTokenInformation(a1, TokenUser, 0, 0, &TokenInformationLength) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError != 122 )
        {
          if ( !LastError )
            goto LABEL_55;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v9 = 662;
            goto LABEL_15;
          }
          goto LABEL_56;
        }
      }
      v10 = (PSID *)LocalAlloc(0, TokenInformationLength);
      if ( !v10 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( !LastError )
          goto LABEL_55;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v9 = 663;
          goto LABEL_15;
        }
        goto LABEL_56;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
      {
        v14 = LocalAlloc(0, 0x44u);
        *a2 = v14;
        if ( v14 )
        {
          v6 = 0;
          if ( CopySid(0x44u, v14, *v10) )
            goto LABEL_54;
          v11 = GetLastError();
          v6 = v11;
          if ( !v11 )
            goto LABEL_54;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_54;
          }
          v13 = 666;
        }
        else
        {
          v11 = GetLastError();
          v6 = v11;
          if ( !v11 )
            goto LABEL_54;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_54;
          }
          v13 = 665;
        }
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( !v11 )
          goto LABEL_54;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_54;
        }
        v13 = 664;
      }
      WPP_SF_d(v12[1].Flink, v13, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v11);
LABEL_54:
      LocalFree(v10);
      goto LABEL_55;
    }
  }
  v3 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_21:
    a1 = TokenHandle;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( !LastError )
      {
LABEL_55:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_56;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v9 = 660;
LABEL_15:
        WPP_SF_d(v8[1].Flink, v9, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
        goto LABEL_55;
      }
      goto LABEL_56;
    }
    goto LABEL_21;
  }
  if ( !LastError )
    goto LABEL_55;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v9 = 661;
    goto LABEL_15;
  }
LABEL_56:
  if ( *a2 && v6 )
  {
    LocalFree(*a2);
    *a2 = 0;
    v8 = WPP_GLOBAL_Control;
  }
  if ( v3 && TokenHandle )
  {
    CloseHandle(TokenHandle);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x2000) != 0
    && BYTE1(v8[1].Blink) >= 6u )
  {
    WPP_SF_d(v8[1].Flink, 667, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18004055c  mov     [rsp-28h+arg_10], rbx
0x180040561  mov     [rsp-28h+arg_18], rsi
0x180040566  mov     [rsp-28h+TokenHandle], rcx
0x18004056b  push    rbp
0x18004056c  push    rdi
0x18004056d  push    r12
0x18004056f  push    r13
0x180040571  push    r14
0x180040573  mov     rbp, rsp
0x180040576  sub     rsp, 30h
0x18004057a  mov     rsi, rdx
0x18004057d  mov     rax, cs:WPP_GLOBAL_Control
0x180040584  lea     r13, WPP_GLOBAL_Control
0x18004058b  mov     r12d, 2000h
0x180040591  cmp     rax, r13
0x180040594  jz      short loc_1800405BE
0x180040596  test    [rax+1Ch], r12d
0x18004059a  jz      short loc_1800405BE
0x18004059c  cmp     byte ptr [rax+19h], 6
0x1800405a0  jb      short loc_1800405BE
0x1800405a2  mov     r9, rcx
0x1800405a5  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800405ac  mov     rcx, [rax+10h]
0x1800405b0  mov     edx, 293h
0x1800405b5  call    WPP_SF_q
0x1800405ba  mov     rcx, [rbp+TokenHandle]
0x1800405be  mov     [rbp+TokenInformationLength], 0
0x1800405c5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800405c9  jz      short loc_1800405D7
0x1800405cb  xor     r14d, r14d
0x1800405ce  test    rcx, rcx
0x1800405d1  jnz     loc_1800406B5
0x1800405d7  mov     r14d, 1
0x1800405dd  call    cs:__imp_GetCurrentThread
0x1800405e3  lea     edi, [r14+7]
0x1800405e7  mov     r8d, r14d; OpenAsSelf
0x1800405ea  mov     rcx, rax; ThreadHandle
0x1800405ed  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800405f1  mov     edx, edi; DesiredAccess
0x1800405f3  call    cs:__imp_OpenThreadToken
0x1800405f9  test    eax, eax
0x1800405fb  jnz     loc_1800406B1
0x180040601  call    cs:__imp_GetLastError
0x180040607  mov     ebx, eax
0x180040609  cmp     eax, 3F0h
0x18004060e  jnz     short loc_18004067E
0x180040610  call    cs:__imp_GetCurrentProcess
0x180040616  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004061a  mov     edx, edi; DesiredAccess
0x18004061c  mov     rcx, rax; ProcessHandle
0x18004061f  call    cs:__imp_OpenProcessToken
0x180040625  test    eax, eax
0x180040627  jnz     loc_1800406B1
0x18004062d  call    cs:__imp_GetLastError
0x180040633  mov     ebx, eax
0x180040635  test    eax, eax
0x180040637  jz      loc_18004085E
0x18004063d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040644  cmp     rcx, r13
0x180040647  jz      loc_180040865
0x18004064d  test    [rcx+1Ch], r12d
0x180040651  jz      loc_180040865
0x180040657  cmp     byte ptr [rcx+19h], 2
0x18004065b  jb      loc_180040865
0x180040661  mov     edx, 294h
0x180040666  mov     rcx, [rcx+10h]
0x18004066a  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x180040671  mov     r9d, eax
0x180040674  call    WPP_SF_d
0x180040679  jmp     loc_18004085E
0x18004067e  test    eax, eax
0x180040680  jz      loc_18004085E
0x180040686  mov     rcx, cs:WPP_GLOBAL_Control
0x18004068d  cmp     rcx, r13
0x180040690  jz      loc_180040865
0x180040696  test    [rcx+1Ch], r12d
0x18004069a  jz      loc_180040865
0x1800406a0  cmp     byte ptr [rcx+19h], 2
0x1800406a4  jb      loc_180040865
0x1800406aa  mov     edx, 295h
0x1800406af  jmp     short loc_180040666
0x1800406b1  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800406b5  xor     r9d, r9d; TokenInformationLength
0x1800406b8  lea     rax, [rbp+TokenInformationLength]
0x1800406bc  xor     r8d, r8d; TokenInformation
0x1800406bf  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800406c4  lea     edx, [r9+1]; TokenInformationClass
0x1800406c8  call    cs:__imp_GetTokenInformation
0x1800406ce  test    eax, eax
0x1800406d0  jnz     short loc_180040715
0x1800406d2  call    cs:__imp_GetLastError
0x1800406d8  mov     ebx, eax
0x1800406da  cmp     eax, 7Ah ; 'z'
0x1800406dd  jz      short loc_180040715
0x1800406df  test    eax, eax
0x1800406e1  jz      loc_18004085E
0x1800406e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406ee  cmp     rcx, r13
0x1800406f1  jz      loc_180040865
0x1800406f7  test    [rcx+1Ch], r12d
0x1800406fb  jz      loc_180040865
0x180040701  cmp     byte ptr [rcx+19h], 2
0x180040705  jb      loc_180040865
0x18004070b  mov     edx, 296h
0x180040710  jmp     loc_180040666
0x180040715  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180040718  xor     ecx, ecx; uFlags
0x18004071a  call    cs:__imp_LocalAlloc
0x180040720  mov     rdi, rax
0x180040723  test    rax, rax
0x180040726  jnz     short loc_180040766
0x180040728  call    cs:__imp_GetLastError
0x18004072e  mov     ebx, eax
0x180040730  test    eax, eax
0x180040732  jz      loc_18004085E
0x180040738  mov     rcx, cs:WPP_GLOBAL_Control
0x18004073f  cmp     rcx, r13
0x180040742  jz      loc_180040865
0x180040748  test    [rcx+1Ch], r12d
0x18004074c  jz      loc_180040865
0x180040752  cmp     byte ptr [rcx+19h], 2
0x180040756  jb      loc_180040865
0x18004075c  mov     edx, 297h
0x180040761  jmp     loc_180040666
0x180040766  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004076a  lea     rax, [rbp+TokenInformationLength]
0x18004076e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180040772  mov     r8, rdi; TokenInformation
0x180040775  mov     edx, 1; TokenInformationClass
0x18004077a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004077f  call    cs:__imp_GetTokenInformation
0x180040785  test    eax, eax
0x180040787  jnz     short loc_1800407C4
0x180040789  call    cs:__imp_GetLastError
0x18004078f  mov     ebx, eax
0x180040791  test    eax, eax
0x180040793  jz      loc_180040855
0x180040799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407a0  cmp     rcx, r13
0x1800407a3  jz      loc_180040855
0x1800407a9  test    [rcx+1Ch], r12d
0x1800407ad  jz      loc_180040855
0x1800407b3  cmp     byte ptr [rcx+19h], 2
0x1800407b7  jb      loc_180040855
0x1800407bd  mov     edx, 298h
0x1800407c2  jmp     short loc_180040842
0x1800407c4  mov     edx, 44h ; 'D'; uBytes
0x1800407c9  xor     ecx, ecx; uFlags
0x1800407cb  call    cs:__imp_LocalAlloc
0x1800407d1  mov     [rsi], rax
0x1800407d4  test    rax, rax
0x1800407d7  jnz     short loc_180040804
0x1800407d9  call    cs:__imp_GetLastError
0x1800407df  mov     ebx, eax
0x1800407e1  test    eax, eax
0x1800407e3  jz      short loc_180040855
0x1800407e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407ec  cmp     rcx, r13
0x1800407ef  jz      short loc_180040855
0x1800407f1  test    [rcx+1Ch], r12d
0x1800407f5  jz      short loc_180040855
0x1800407f7  cmp     byte ptr [rcx+19h], 2
0x1800407fb  jb      short loc_180040855
0x1800407fd  mov     edx, 299h
0x180040802  jmp     short loc_180040842
0x180040804  mov     r8, [rdi]; pSourceSid
0x180040807  xor     ebx, ebx
0x180040809  mov     rdx, rax; pDestinationSid
0x18004080c  lea     ecx, [rbx+44h]; nDestinationSidLength
0x18004080f  call    cs:__imp_CopySid
0x180040815  test    eax, eax
0x180040817  jnz     short loc_180040855
0x180040819  call    cs:__imp_GetLastError
0x18004081f  mov     ebx, eax
0x180040821  test    eax, eax
0x180040823  jz      short loc_180040855
0x180040825  mov     rcx, cs:WPP_GLOBAL_Control
0x18004082c  cmp     rcx, r13
0x18004082f  jz      short loc_180040855
0x180040831  test    [rcx+1Ch], r12d
0x180040835  jz      short loc_180040855
0x180040837  cmp     byte ptr [rcx+19h], 2
0x18004083b  jb      short loc_180040855
0x18004083d  mov     edx, 29Ah
0x180040842  mov     rcx, [rcx+10h]
0x180040846  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18004084d  mov     r9d, eax
0x180040850  call    WPP_SF_d
0x180040855  mov     rcx, rdi; hMem
0x180040858  call    cs:__imp_LocalFree
0x18004085e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040865  cmp     qword ptr [rsi], 0
0x180040869  jz      short loc_180040886
0x18004086b  test    ebx, ebx
0x18004086d  jz      short loc_180040886
0x18004086f  mov     rcx, [rsi]; hMem
0x180040872  call    cs:__imp_LocalFree
0x180040878  mov     qword ptr [rsi], 0
0x18004087f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040886  test    r14d, r14d
0x180040889  jz      short loc_1800408A4
0x18004088b  mov     rax, [rbp+TokenHandle]
0x18004088f  test    rax, rax
0x180040892  jz      short loc_1800408A4
0x180040894  mov     rcx, rax; hObject
0x180040897  call    cs:__imp_CloseHandle
0x18004089d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408a4  cmp     rcx, r13
0x1800408a7  jz      short loc_1800408CD
0x1800408a9  test    [rcx+1Ch], r12d
0x1800408ad  jz      short loc_1800408CD
0x1800408af  cmp     byte ptr [rcx+19h], 6
0x1800408b3  jb      short loc_1800408CD
0x1800408b5  mov     rcx, [rcx+10h]
0x1800408b9  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x1800408c0  mov     edx, 29Bh
0x1800408c5  mov     r9d, ebx
0x1800408c8  call    WPP_SF_d
0x1800408cd  mov     rsi, [rsp+30h+arg_18]
0x1800408d2  mov     eax, ebx
0x1800408d4  mov     rbx, [rsp+30h+arg_10]
0x1800408d9  add     rsp, 30h
0x1800408dd  pop     r14
0x1800408df  pop     r13
0x1800408e1  pop     r12
0x1800408e3  pop     rdi
0x1800408e4  pop     rbp
0x1800408e5  retn
```

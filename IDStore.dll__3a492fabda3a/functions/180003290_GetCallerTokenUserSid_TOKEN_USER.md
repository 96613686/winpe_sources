# GetCallerTokenUserSid(_TOKEN_USER * *)

- ea: `0x180003290`
- end: `0x18000354e`
- name: `?GetCallerTokenUserSid@@YAJPEAPEAU_TOKEN_USER@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(struct _TOKEN_USER **, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c80`
- `0x1800074dc`
- `0x180013b40`

## callees

- `0x180003290`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800033aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800033aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800032ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800032ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800032d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800032d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800033bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800033bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000345d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000345d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003363`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003363`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003339`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180003339`

## string_xrefs

- `0x180003422`: `GetCallerTokenUserSid`
- `0x1800034e0`: `GetCallerTokenUserSid`
- `0x180003538`: `GetCallerTokenUserSid`

## pseudocode

```c
__int64 __fastcall GetCallerTokenUserSid(struct _TOKEN_USER **a1, __int64 a2, __int64 a3)
{
  HANDLE CurrentThread; // rax
  struct _TOKEN_USER *v5; // rbx
  unsigned int v6; // edi
  int v7; // edx
  __int64 v8; // r8
  CIdentityProfileHandler *v9; // rcx
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v13; // eax
  CIdentityProfileHandler *v14; // rcx
  __int64 v15; // rdx
  signed int v16; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "GetCallerTokenUserSid");
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v5 = 0;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_5;
      v13 = GetLastError();
      v6 = v13;
      if ( v13 > 0 )
        v6 = (unsigned __int16)v13 | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v15 = 133;
LABEL_36:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v6);
        v14 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v15 = 134;
        goto LABEL_36;
      }
    }
LABEL_37:
    if ( (v6 & 0x80000000) == 0 )
      goto LABEL_7;
    goto LABEL_38;
  }
LABEL_5:
  TokenInformationLength = 84;
  v5 = (struct _TOKEN_USER *)CoTaskMemAlloc(0x54u);
  if ( v5 )
  {
    v6 = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
    {
LABEL_7:
      *a1 = v5;
      goto LABEL_8;
    }
    v16 = GetLastError();
    v6 = v16;
    if ( v16 > 0 )
      v6 = (unsigned __int16)v16 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_37;
    }
    v15 = 136;
    goto LABEL_36;
  }
  v6 = -2147024882;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, 2147942414LL);
      v14 = WPP_GLOBAL_Control;
    }
LABEL_38:
    if ( v14 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v14 + 2), 137, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v6);
  }
  CoTaskMemFree(v5);
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_11;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (unsigned int)"GetCallerTokenUserSid", v6);
LABEL_11:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v9 + 2), 12, v8, "GetCallerTokenUserSid");
  return v6;
}

```

## disassembly

```asm
0x180003290  push    rdi
0x180003292  push    r14
0x180003294  sub     rsp, 38h
0x180003298  mov     [rsp+48h+arg_18], rbp
0x18000329d  xor     ebp, ebp
0x18000329f  mov     [rsp+48h+var_18], rsi
0x1800032a4  mov     rsi, rcx
0x1800032a7  mov     [rsp+48h+TokenInformationLength], ebp
0x1800032ab  mov     [rsp+48h+TokenHandle], rbp
0x1800032b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032b7  lea     r14, WPP_GLOBAL_Control
0x1800032be  cmp     rcx, r14
0x1800032c1  jz      short loc_1800032D0
0x1800032c3  test    dword ptr [rcx+1Ch], 400h
0x1800032ca  jnz     loc_1800034DC
0x1800032d0  mov     [rsp+48h+arg_0], rbx
0x1800032d5  call    cs:__imp_GetCurrentThread
0x1800032db  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800032e0  mov     edx, 8; DesiredAccess
0x1800032e5  mov     rcx, rax; ThreadHandle
0x1800032e8  mov     r8d, 1; OpenAsSelf
0x1800032ee  call    cs:__imp_OpenThreadToken
0x1800032f4  test    eax, eax
0x1800032f6  jz      loc_180003394
0x1800032fc  mov     ecx, 54h ; 'T'; cb
0x180003301  mov     [rsp+48h+TokenInformationLength], 54h ; 'T'
0x180003309  call    cs:__imp_CoTaskMemAlloc
0x18000330f  mov     rbx, rax
0x180003312  test    rax, rax
0x180003315  jz      loc_1800034F6
0x18000331b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180003320  lea     rax, [rsp+48h+TokenInformationLength]
0x180003325  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000332a  mov     r8, rbx; TokenInformation
0x18000332d  mov     edx, 1; TokenInformationClass
0x180003332  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180003337  mov     edi, ebp
0x180003339  call    cs:__imp_GetTokenInformation
0x18000333f  test    eax, eax
0x180003341  jz      loc_18000345D
0x180003347  mov     [rsi], rbx
0x18000334a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000334f  mov     rsi, [rsp+48h+var_18]
0x180003354  mov     rbp, [rsp+48h+arg_18]
0x180003359  mov     rbx, [rsp+48h+arg_0]
0x18000335e  test    rcx, rcx
0x180003361  jz      short loc_180003369
0x180003363  call    cs:__imp_CloseHandle
0x180003369  test    edi, edi
0x18000336b  js      loc_180003404
0x180003371  mov     rcx, cs:WPP_GLOBAL_Control
0x180003378  cmp     rcx, r14
0x18000337b  jz      short loc_18000338A
0x18000337d  test    dword ptr [rcx+1Ch], 400h
0x180003384  jnz     loc_180003534
0x18000338a  mov     eax, edi
0x18000338c  add     rsp, 38h
0x180003390  pop     r14
0x180003392  pop     rdi
0x180003393  retn
0x180003394  mov     rbx, rbp
0x180003397  call    cs:__imp_GetLastError
0x18000339d  mov     edi, eax
0x18000339f  cmp     eax, 3F0h
0x1800033a4  jnz     loc_180003437
0x1800033aa  call    cs:__imp_GetCurrentProcess
0x1800033b0  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800033b5  mov     edx, 8; DesiredAccess
0x1800033ba  mov     rcx, rax; ProcessHandle
0x1800033bd  call    cs:__imp_OpenProcessToken
0x1800033c3  test    eax, eax
0x1800033c5  jnz     loc_1800032FC
0x1800033cb  call    cs:__imp_GetLastError
0x1800033d1  mov     edi, eax
0x1800033d3  test    eax, eax
0x1800033d5  jle     short loc_1800033E0
0x1800033d7  movzx   edi, ax
0x1800033da  or      edi, 80070000h
0x1800033e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e7  cmp     rcx, r14
0x1800033ea  jz      loc_1800034A3
0x1800033f0  test    byte ptr [rcx+1Ch], 4
0x1800033f4  jz      loc_1800034A3
0x1800033fa  mov     edx, 85h
0x1800033ff  jmp     loc_180003489
0x180003404  mov     rcx, cs:WPP_GLOBAL_Control
0x18000340b  cmp     rcx, r14
0x18000340e  jz      loc_18000338A
0x180003414  test    byte ptr [rcx+1Ch], 4
0x180003418  jz      loc_180003378
0x18000341e  mov     rcx, [rcx+10h]
0x180003422  lea     r9, aGetcallertoken; "GetCallerTokenUserSid"
0x180003429  mov     dword ptr [rsp+48h+ReturnLength], edi
0x18000342d  call    WPP_SF_sL
0x180003432  jmp     loc_180003371
0x180003437  test    eax, eax
0x180003439  jle     short loc_180003444
0x18000343b  movzx   edi, ax
0x18000343e  or      edi, 80070000h
0x180003444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344b  cmp     rcx, r14
0x18000344e  jz      short loc_1800034A3
0x180003450  test    byte ptr [rcx+1Ch], 4
0x180003454  jz      short loc_1800034A3
0x180003456  mov     edx, 86h
0x18000345b  jmp     short loc_180003489
0x18000345d  call    cs:__imp_GetLastError
0x180003463  mov     edi, eax
0x180003465  test    eax, eax
0x180003467  jle     short loc_180003472
0x180003469  movzx   edi, ax
0x18000346c  or      edi, 80070000h
0x180003472  mov     rcx, cs:WPP_GLOBAL_Control
0x180003479  cmp     rcx, r14
0x18000347c  jz      short loc_1800034A3
0x18000347e  test    byte ptr [rcx+1Ch], 4
0x180003482  jz      short loc_1800034A3
0x180003484  mov     edx, 88h
0x180003489  mov     rcx, [rcx+10h]
0x18000348d  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180003494  mov     r9d, edi
0x180003497  call    WPP_SF_d
0x18000349c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034a3  test    edi, edi
0x1800034a5  jns     loc_180003347
0x1800034ab  cmp     rcx, r14
0x1800034ae  jz      short loc_1800034CE
0x1800034b0  test    byte ptr [rcx+1Ch], 4
0x1800034b4  jz      short loc_1800034CE
0x1800034b6  mov     rcx, [rcx+10h]
0x1800034ba  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800034c1  mov     edx, 89h
0x1800034c6  mov     r9d, edi
0x1800034c9  call    WPP_SF_d
0x1800034ce  mov     rcx, rbx; pv
0x1800034d1  call    cs:__imp_CoTaskMemFree
0x1800034d7  jmp     loc_18000334A
0x1800034dc  mov     rcx, [rcx+10h]
0x1800034e0  lea     r9, aGetcallertoken; "GetCallerTokenUserSid"
0x1800034e7  mov     edx, 0Ah
0x1800034ec  call    WPP_SF_s
0x1800034f1  jmp     loc_1800032D0
0x1800034f6  mov     edi, 8007000Eh
0x1800034fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003502  cmp     rcx, r14
0x180003505  jz      short loc_1800034CE
0x180003507  test    byte ptr [rcx+1Ch], 4
0x18000350b  jz      short loc_1800034AB
0x18000350d  mov     rcx, [rcx+10h]
0x180003511  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180003518  mov     edx, 87h
0x18000351d  mov     r9d, 8007000Eh
0x180003523  call    WPP_SF_d
0x180003528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000352f  jmp     loc_1800034AB
0x180003534  mov     rcx, [rcx+10h]
0x180003538  lea     r9, aGetcallertoken; "GetCallerTokenUserSid"
0x18000353f  mov     edx, 0Ch
0x180003544  call    WPP_SF_s
0x180003549  jmp     loc_18000338A
```

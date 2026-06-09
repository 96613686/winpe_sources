# CThreadChasing::GetWaitingOnApplicationVersion(void *,ushort *)

- ea: `0x14001c528`
- end: `0x14001cb56`
- name: `?GetWaitingOnApplicationVersion@CThreadChasing@@QEAAXPEAXPEAG@Z`
- size: `1582`
- prototype: `void(CThreadChasing *__hidden this, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14002b5d8`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400041e8`
- `0x140005550`
- `0x1400101a8`
- `0x140014ee4`
- `0x140014f14`
- `0x140015138`
- `0x14001c528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c8aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ca1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ca58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c7a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c8aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001c94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ca1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ca58`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c618`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c795`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c618`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001c795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001caeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cb13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cb28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001caeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cb13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001cb28`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14001c8f6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14001c8f6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c687`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c72a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c804`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c89a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c687`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c72a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c804`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001c89a`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14001c93e`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14001c93e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001c5a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001c5a4`

## pseudocode

```c
void __fastcall CThreadChasing::GetWaitingOnApplicationVersion(CThreadChasing *this, void *a2, unsigned __int16 *a3)
{
  DWORD v4; // r8d
  PSID *v6; // rdi
  PSID *v7; // rbx
  HANDLE v8; // r15
  signed int LastError; // eax
  const struct std::nothrow_t *v10; // rdx
  signed int v11; // esi
  CUserModeHangReport *v12; // rcx
  __int64 v13; // rdx
  void **v14; // rax
  signed int v15; // eax
  PSID *v16; // rax
  signed int v17; // eax
  void **v18; // rax
  signed int v19; // eax
  PSID *v20; // rax
  __int64 v21; // rdx
  signed int v22; // eax
  signed int v23; // eax
  int FileInfo; // eax
  unsigned __int16 v25; // cx
  unsigned __int16 v26; // cx
  signed int v27; // eax
  signed int v28; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v32; // [rsp+48h] [rbp-B8h]
  __int128 v33; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  TokenHandle = 0;
  *(_QWORD *)a3 = 0;
  hObject = 0;
  v4 = *((_DWORD *)this + 1127);
  TokenInformationLength = 0;
  v35 = 0;
  v32 = 0;
  v6 = 0;
  v7 = 0;
  v33 = 0;
  Filename[0] = 0;
  v34 = 0;
  v8 = OpenProcess(0x410u, 0, v4);
  if ( (unsigned __int64)v8 + 1 <= 1 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 48;
LABEL_70:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, (unsigned int)v11);
      v12 = WPP_GLOBAL_Control;
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  v14 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(v8, 0x20008u, v14) )
  {
    v15 = GetLastError();
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 49;
      goto LABEL_70;
    }
LABEL_71:
    if ( v11 >= 0 )
      goto LABEL_75;
    goto LABEL_72;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    v28 = GetLastError();
    v11 = v28;
    if ( v28 > 0 )
      v11 = (unsigned __int16)v28 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 50;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  v16 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v16;
  if ( !v16 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      goto LABEL_77;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids, 2147942414LL);
    goto LABEL_19;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v16, TokenInformationLength, &TokenInformationLength) )
  {
    v17 = GetLastError();
    v11 = v17;
    if ( v17 > 0 )
      v11 = (unsigned __int16)v17 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 52;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  v18 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
  if ( !OpenProcessToken(a2, 0x20008u, v18) )
  {
    v19 = GetLastError();
    v11 = v19;
    if ( v19 > 0 )
      v11 = (unsigned __int16)v19 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 53;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  if ( GetTokenInformation(hObject, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    v27 = GetLastError();
    v11 = v27;
    if ( v27 > 0 )
      v11 = (unsigned __int16)v27 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 54;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  v20 = (PSID *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v20;
  if ( !v20 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      goto LABEL_77;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_72;
    v21 = 55;
LABEL_38:
    WPP_SF_(*((_QWORD *)v12 + 2), v21, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
LABEL_19:
    v12 = WPP_GLOBAL_Control;
LABEL_72:
    if ( v12 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v12 + 2), 60, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids);
LABEL_75:
    if ( !v7 )
      goto LABEL_77;
    goto LABEL_76;
  }
  if ( !GetTokenInformation(hObject, TokenUser, v20, TokenInformationLength, &TokenInformationLength) )
  {
    v22 = GetLastError();
    v11 = v22;
    if ( v22 > 0 )
      v11 = (unsigned __int16)v22 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 56;
      goto LABEL_70;
    }
    goto LABEL_71;
  }
  if ( EqualSid(*v7, *v6) )
  {
    if ( !K32GetModuleFileNameExW(v8, 0, Filename, 0x104u) )
    {
      v23 = GetLastError();
      v11 = v23;
      if ( v23 > 0 )
        v11 = (unsigned __int16)v23 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 58;
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    FileInfo = UtilGetFileInfo(Filename, 0);
    if ( FileInfo < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
        goto LABEL_75;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_72;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids,
        (unsigned int)Filename,
        FileInfo);
      goto LABEL_19;
    }
    v25 = WORD4(v32);
    *a3 = WORD5(v32);
    a3[1] = v25;
    v26 = WORD6(v32);
    a3[2] = HIWORD(v32);
    a3[3] = v26;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_72;
      v21 = 57;
      goto LABEL_38;
    }
  }
LABEL_76:
  operator delete(v7, v10);
LABEL_77:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v6 )
    operator delete(v6, v10);
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  if ( (unsigned __int64)v8 + 1 > 1 )
    CloseHandle(v8);
}

```

## disassembly

```asm
0x14001c528  push    rbp
0x14001c52a  push    rbx
0x14001c52b  push    rsi
0x14001c52c  push    rdi
0x14001c52d  push    r12
0x14001c52f  push    r14
0x14001c531  push    r15
0x14001c533  lea     rbp, [rsp-1A0h]
0x14001c53b  sub     rsp, 2A0h
0x14001c542  mov     rax, cs:__security_cookie
0x14001c549  xor     rax, rsp
0x14001c54c  mov     [rbp+1D0h+var_40], rax
0x14001c553  xor     eax, eax
0x14001c555  mov     [rsp+2D0h+TokenHandle], 0
0x14001c55e  xorps   xmm0, xmm0
0x14001c561  mov     [r8], rax
0x14001c564  mov     rsi, r8
0x14001c567  mov     [rsp+2D0h+hObject], 0
0x14001c570  mov     r8d, [rcx+119Ch]; dwProcessId
0x14001c577  mov     r14, rdx
0x14001c57a  mov     ecx, 410h; dwDesiredAccess
0x14001c57f  mov     [rsp+2D0h+TokenInformationLength], 0
0x14001c587  xor     edx, edx; bInheritHandle
0x14001c589  mov     [rsp+2D0h+var_258], eax
0x14001c58d  movups  [rsp+2D0h+var_288], xmm0
0x14001c592  xor     edi, edi
0x14001c594  xor     ebx, ebx
0x14001c596  movups  [rsp+2D0h+var_278], xmm0
0x14001c59b  mov     [rbp+1D0h+Filename], ax
0x14001c59f  movups  [rsp+2D0h+var_268], xmm0
0x14001c5a4  call    cs:__imp_OpenProcess
0x14001c5ab  nop     dword ptr [rax+rax+00h]
0x14001c5b0  mov     r15, rax
0x14001c5b3  lea     r12, [rax+1]
0x14001c5b7  cmp     r12, 1
0x14001c5bb  ja      short loc_14001C603
0x14001c5bd  call    cs:__imp_GetLastError
0x14001c5c4  nop     dword ptr [rax+rax+00h]
0x14001c5c9  mov     esi, eax
0x14001c5cb  test    eax, eax
0x14001c5cd  jle     short loc_14001C5D8
0x14001c5cf  movzx   esi, ax
0x14001c5d2  or      esi, 80070000h
0x14001c5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c5df  lea     r14, WPP_GLOBAL_Control
0x14001c5e6  cmp     rcx, r14
0x14001c5e9  jz      loc_14001CAAB
0x14001c5ef  test    byte ptr [rcx+1Ch], 1
0x14001c5f3  jz      loc_14001CAAB
0x14001c5f9  mov     edx, 30h ; '0'
0x14001c5fe  jmp     loc_14001CA91
0x14001c603  lea     rcx, [rsp+2D0h+TokenHandle]
0x14001c608  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14001c60d  mov     r8, rax; TokenHandle
0x14001c610  mov     edx, 20008h; DesiredAccess
0x14001c615  mov     rcx, r15; ProcessHandle
0x14001c618  call    cs:__imp_OpenProcessToken
0x14001c61f  nop     dword ptr [rax+rax+00h]
0x14001c624  test    eax, eax
0x14001c626  jnz     short loc_14001C66E
0x14001c628  call    cs:__imp_GetLastError
0x14001c62f  nop     dword ptr [rax+rax+00h]
0x14001c634  mov     esi, eax
0x14001c636  test    eax, eax
0x14001c638  jle     short loc_14001C643
0x14001c63a  movzx   esi, ax
0x14001c63d  or      esi, 80070000h
0x14001c643  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c64a  lea     r14, WPP_GLOBAL_Control
0x14001c651  cmp     rcx, r14
0x14001c654  jz      loc_14001CAAB
0x14001c65a  test    byte ptr [rcx+1Ch], 1
0x14001c65e  jz      loc_14001CAAB
0x14001c664  mov     edx, 31h ; '1'
0x14001c669  jmp     loc_14001CA91
0x14001c66e  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x14001c673  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001c678  xor     r9d, r9d; TokenInformationLength
0x14001c67b  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001c680  xor     r8d, r8d; TokenInformation
0x14001c683  lea     edx, [r9+1]; TokenInformationClass
0x14001c687  call    cs:__imp_GetTokenInformation
0x14001c68e  nop     dword ptr [rax+rax+00h]
0x14001c693  test    eax, eax
0x14001c695  jnz     loc_14001CA58
0x14001c69b  call    cs:__imp_GetLastError
0x14001c6a2  nop     dword ptr [rax+rax+00h]
0x14001c6a7  cmp     eax, 7Ah ; 'z'
0x14001c6aa  jnz     loc_14001CA58
0x14001c6b0  mov     ecx, [rsp+2D0h+TokenInformationLength]; unsigned __int64
0x14001c6b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c6bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001c6c0  mov     rdi, rax
0x14001c6c3  test    rax, rax
0x14001c6c6  jnz     short loc_14001C70E
0x14001c6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6cf  lea     r14, WPP_GLOBAL_Control
0x14001c6d6  cmp     rcx, r14
0x14001c6d9  jz      loc_14001CADC
0x14001c6df  test    byte ptr [rcx+1Ch], 1
0x14001c6e3  jz      loc_14001CAAF
0x14001c6e9  mov     rcx, [rcx+10h]
0x14001c6ed  lea     edx, [rax+33h]
0x14001c6f0  mov     r9d, 8007000Eh
0x14001c6f6  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c6fd  call    WPP_SF_d
0x14001c702  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c709  jmp     loc_14001CAAF
0x14001c70e  mov     r9d, [rsp+2D0h+TokenInformationLength]; TokenInformationLength
0x14001c713  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001c718  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x14001c71d  mov     r8, rdi; TokenInformation
0x14001c720  mov     edx, 1; TokenInformationClass
0x14001c725  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001c72a  call    cs:__imp_GetTokenInformation
0x14001c731  nop     dword ptr [rax+rax+00h]
0x14001c736  test    eax, eax
0x14001c738  jnz     short loc_14001C780
0x14001c73a  call    cs:__imp_GetLastError
0x14001c741  nop     dword ptr [rax+rax+00h]
0x14001c746  mov     esi, eax
0x14001c748  test    eax, eax
0x14001c74a  jle     short loc_14001C755
0x14001c74c  movzx   esi, ax
0x14001c74f  or      esi, 80070000h
0x14001c755  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c75c  lea     r14, WPP_GLOBAL_Control
0x14001c763  cmp     rcx, r14
0x14001c766  jz      loc_14001CAAB
0x14001c76c  test    byte ptr [rcx+1Ch], 1
0x14001c770  jz      loc_14001CAAB
0x14001c776  mov     edx, 34h ; '4'
0x14001c77b  jmp     loc_14001CA91
0x14001c780  lea     rcx, [rsp+2D0h+hObject]
0x14001c785  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14001c78a  mov     r8, rax; TokenHandle
0x14001c78d  mov     edx, 20008h; DesiredAccess
0x14001c792  mov     rcx, r14; ProcessHandle
0x14001c795  call    cs:__imp_OpenProcessToken
0x14001c79c  nop     dword ptr [rax+rax+00h]
0x14001c7a1  test    eax, eax
0x14001c7a3  jnz     short loc_14001C7EB
0x14001c7a5  call    cs:__imp_GetLastError
0x14001c7ac  nop     dword ptr [rax+rax+00h]
0x14001c7b1  mov     esi, eax
0x14001c7b3  test    eax, eax
0x14001c7b5  jle     short loc_14001C7C0
0x14001c7b7  movzx   esi, ax
0x14001c7ba  or      esi, 80070000h
0x14001c7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7c7  lea     r14, WPP_GLOBAL_Control
0x14001c7ce  cmp     rcx, r14
0x14001c7d1  jz      loc_14001CAAB
0x14001c7d7  test    byte ptr [rcx+1Ch], 1
0x14001c7db  jz      loc_14001CAAB
0x14001c7e1  mov     edx, 35h ; '5'
0x14001c7e6  jmp     loc_14001CA91
0x14001c7eb  mov     rcx, [rsp+2D0h+hObject]; TokenHandle
0x14001c7f0  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001c7f5  xor     r9d, r9d; TokenInformationLength
0x14001c7f8  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001c7fd  xor     r8d, r8d; TokenInformation
0x14001c800  lea     edx, [r9+1]; TokenInformationClass
0x14001c804  call    cs:__imp_GetTokenInformation
0x14001c80b  nop     dword ptr [rax+rax+00h]
0x14001c810  test    eax, eax
0x14001c812  jnz     loc_14001CA1D
0x14001c818  call    cs:__imp_GetLastError
0x14001c81f  nop     dword ptr [rax+rax+00h]
0x14001c824  cmp     eax, 7Ah ; 'z'
0x14001c827  jnz     loc_14001CA1D
0x14001c82d  mov     ecx, [rsp+2D0h+TokenInformationLength]; unsigned __int64
0x14001c831  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001c838  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001c83d  mov     rbx, rax
0x14001c840  test    rax, rax
0x14001c843  jnz     short loc_14001C87E
0x14001c845  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c84c  lea     r14, WPP_GLOBAL_Control
0x14001c853  cmp     rcx, r14
0x14001c856  jz      loc_14001CADC
0x14001c85c  test    byte ptr [rcx+1Ch], 1
0x14001c860  jz      loc_14001CAAF
0x14001c866  lea     edx, [rax+37h]
0x14001c869  mov     rcx, [rcx+10h]
0x14001c86d  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c874  call    WPP_SF_
0x14001c879  jmp     loc_14001C702
0x14001c87e  mov     r9d, [rsp+2D0h+TokenInformationLength]; TokenInformationLength
0x14001c883  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001c888  mov     rcx, [rsp+2D0h+hObject]; TokenHandle
0x14001c88d  mov     r8, rbx; TokenInformation
0x14001c890  mov     edx, 1; TokenInformationClass
0x14001c895  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001c89a  call    cs:__imp_GetTokenInformation
0x14001c8a1  nop     dword ptr [rax+rax+00h]
0x14001c8a6  test    eax, eax
0x14001c8a8  jnz     short loc_14001C8F0
0x14001c8aa  call    cs:__imp_GetLastError
0x14001c8b1  nop     dword ptr [rax+rax+00h]
0x14001c8b6  mov     esi, eax
0x14001c8b8  test    eax, eax
0x14001c8ba  jle     short loc_14001C8C5
0x14001c8bc  movzx   esi, ax
0x14001c8bf  or      esi, 80070000h
0x14001c8c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c8cc  lea     r14, WPP_GLOBAL_Control
0x14001c8d3  cmp     rcx, r14
0x14001c8d6  jz      loc_14001CAAB
0x14001c8dc  test    byte ptr [rcx+1Ch], 1
0x14001c8e0  jz      loc_14001CAAB
0x14001c8e6  mov     edx, 38h ; '8'
0x14001c8eb  jmp     loc_14001CA91
0x14001c8f0  mov     rdx, [rdi]; pSid2
0x14001c8f3  mov     rcx, [rbx]; pSid1
0x14001c8f6  call    cs:__imp_EqualSid
0x14001c8fd  nop     dword ptr [rax+rax+00h]
0x14001c902  test    eax, eax
0x14001c904  jnz     short loc_14001C92F
0x14001c906  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c90d  lea     r14, WPP_GLOBAL_Control
0x14001c914  cmp     rcx, r14
0x14001c917  jz      loc_14001CAD4
0x14001c91d  test    byte ptr [rcx+1Ch], 1
0x14001c921  jz      loc_14001CAAF
0x14001c927  lea     edx, [rax+39h]
0x14001c92a  jmp     loc_14001C869
0x14001c92f  mov     r9d, 104h; nSize
0x14001c935  lea     r8, [rbp+1D0h+Filename]; lpFilename
0x14001c939  xor     edx, edx; hModule
0x14001c93b  mov     rcx, r15; hProcess
0x14001c93e  call    cs:__imp_K32GetModuleFileNameExW
0x14001c945  nop     dword ptr [rax+rax+00h]
0x14001c94a  test    eax, eax
0x14001c94c  jnz     short loc_14001C994
0x14001c94e  call    cs:__imp_GetLastError
0x14001c955  nop     dword ptr [rax+rax+00h]
0x14001c95a  mov     esi, eax
0x14001c95c  test    eax, eax
0x14001c95e  jle     short loc_14001C969
0x14001c960  movzx   esi, ax
0x14001c963  or      esi, 80070000h
0x14001c969  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c970  lea     r14, WPP_GLOBAL_Control
0x14001c977  cmp     rcx, r14
0x14001c97a  jz      loc_14001CAAB
0x14001c980  test    byte ptr [rcx+1Ch], 1
0x14001c984  jz      loc_14001CAAB
0x14001c98a  mov     edx, 3Ah ; ':'
0x14001c98f  jmp     loc_14001CA91
0x14001c994  xor     r9d, r9d
0x14001c997  mov     dword ptr [rsp+2D0h+ReturnLength], 0; int
0x14001c99f  xor     r8d, r8d
0x14001c9a2  lea     rdx, [rsp+2D0h+var_288]
0x14001c9a7  lea     rcx, [rbp+1D0h+Filename]; lpwstrFilename
0x14001c9ab  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x14001c9b0  test    eax, eax
0x14001c9b2  jns     short loc_14001C9F7
0x14001c9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c9bb  lea     r14, WPP_GLOBAL_Control
0x14001c9c2  cmp     rcx, r14
0x14001c9c5  jz      loc_14001CACF
0x14001c9cb  test    byte ptr [rcx+1Ch], 1
0x14001c9cf  jz      loc_14001CAAF
0x14001c9d5  mov     rcx, [rcx+10h]
0x14001c9d9  lea     r9, [rbp+1D0h+Filename]
0x14001c9dd  mov     edx, 3Bh ; ';'
0x14001c9e2  mov     dword ptr [rsp+2D0h+ReturnLength], eax
0x14001c9e6  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001c9ed  call    WPP_SF_Sd
0x14001c9f2  jmp     loc_14001C702
0x14001c9f7  mov     ecx, dword ptr [rsp+2D0h+var_288+8]
0x14001c9fb  mov     eax, ecx
0x14001c9fd  shr     eax, 10h
0x14001ca00  mov     [rsi], ax
0x14001ca03  mov     [rsi+2], cx
0x14001ca07  mov     ecx, dword ptr [rsp+2D0h+var_288+0Ch]
0x14001ca0b  mov     eax, ecx
0x14001ca0d  shr     eax, 10h
0x14001ca10  mov     [rsi+4], ax
0x14001ca14  mov     [rsi+6], cx
0x14001ca18  jmp     loc_14001CAD4
0x14001ca1d  call    cs:__imp_GetLastError
0x14001ca24  nop     dword ptr [rax+rax+00h]
0x14001ca29  mov     esi, eax
0x14001ca2b  test    eax, eax
0x14001ca2d  jle     short loc_14001CA38
0x14001ca2f  movzx   esi, ax
0x14001ca32  or      esi, 80070000h
0x14001ca38  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca3f  lea     r14, WPP_GLOBAL_Control
0x14001ca46  cmp     rcx, r14
0x14001ca49  jz      short loc_14001CAAB
0x14001ca4b  test    byte ptr [rcx+1Ch], 1
0x14001ca4f  jz      short loc_14001CAAB
0x14001ca51  mov     edx, 36h ; '6'
0x14001ca56  jmp     short loc_14001CA91
0x14001ca58  call    cs:__imp_GetLastError
0x14001ca5f  nop     dword ptr [rax+rax+00h]
0x14001ca64  mov     esi, eax
  ... truncated ...
```

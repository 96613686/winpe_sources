# CThreadChasing::GetWaitingOnApplicationVersion(void *,ushort *)

- ea: `0x14001b48c`
- end: `0x14001ba35`
- name: `?GetWaitingOnApplicationVersion@CThreadChasing@@QEAAXPEAXPEAG@Z`
- size: `1449`
- prototype: `void(CThreadChasing *__hidden this, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140029a14`

## callees

- `0x140002470`
- `0x140002728`
- `0x140004198`
- `0x140005498`
- `0x14000fb60`
- `0x14001444c`
- `0x140014474`
- `0x140014678`
- `0x14001b48c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b5e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b6d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b91b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b950`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001b570`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001b6c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001b570`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001b6c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ba0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ba0e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14001b806`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14001b806`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b5d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b66a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b72c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b7b6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b5d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b66a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b72c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001b7b6`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14001b848`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14001b848`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001b508`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001b508`

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
0x14001b48c  push    rbp
0x14001b48e  push    rbx
0x14001b48f  push    rsi
0x14001b490  push    rdi
0x14001b491  push    r12
0x14001b493  push    r14
0x14001b495  push    r15
0x14001b497  lea     rbp, [rsp-1A0h]
0x14001b49f  sub     rsp, 2A0h
0x14001b4a6  mov     rax, cs:__security_cookie
0x14001b4ad  xor     rax, rsp
0x14001b4b0  mov     [rbp+1D0h+var_40], rax
0x14001b4b7  xor     eax, eax
0x14001b4b9  mov     [rsp+2D0h+TokenHandle], 0
0x14001b4c2  xorps   xmm0, xmm0
0x14001b4c5  mov     [r8], rax
0x14001b4c8  mov     rsi, r8
0x14001b4cb  mov     [rsp+2D0h+hObject], 0
0x14001b4d4  mov     r8d, [rcx+119Ch]; dwProcessId
0x14001b4db  mov     r14, rdx
0x14001b4de  mov     ecx, 410h; dwDesiredAccess
0x14001b4e3  mov     [rsp+2D0h+TokenInformationLength], 0
0x14001b4eb  xor     edx, edx; bInheritHandle
0x14001b4ed  mov     [rsp+2D0h+var_258], eax
0x14001b4f1  movups  [rsp+2D0h+var_288], xmm0
0x14001b4f6  xor     edi, edi
0x14001b4f8  xor     ebx, ebx
0x14001b4fa  movups  [rsp+2D0h+var_278], xmm0
0x14001b4ff  mov     [rbp+1D0h+Filename], ax
0x14001b503  movups  [rsp+2D0h+var_268], xmm0
0x14001b508  call    cs:__imp_OpenProcess
0x14001b50e  mov     r15, rax
0x14001b511  lea     r12, [rax+1]
0x14001b515  cmp     r12, 1
0x14001b519  ja      short loc_14001B55B
0x14001b51b  call    cs:__imp_GetLastError
0x14001b521  mov     esi, eax
0x14001b523  test    eax, eax
0x14001b525  jle     short loc_14001B530
0x14001b527  movzx   esi, ax
0x14001b52a  or      esi, 80070000h
0x14001b530  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b537  lea     r14, WPP_GLOBAL_Control
0x14001b53e  cmp     rcx, r14
0x14001b541  jz      loc_14001B99D
0x14001b547  test    byte ptr [rcx+1Ch], 1
0x14001b54b  jz      loc_14001B99D
0x14001b551  mov     edx, 30h ; '0'
0x14001b556  jmp     loc_14001B983
0x14001b55b  lea     rcx, [rsp+2D0h+TokenHandle]
0x14001b560  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14001b565  mov     r8, rax; TokenHandle
0x14001b568  mov     edx, 20008h; DesiredAccess
0x14001b56d  mov     rcx, r15; ProcessHandle
0x14001b570  call    cs:__imp_OpenProcessToken
0x14001b576  test    eax, eax
0x14001b578  jnz     short loc_14001B5BA
0x14001b57a  call    cs:__imp_GetLastError
0x14001b580  mov     esi, eax
0x14001b582  test    eax, eax
0x14001b584  jle     short loc_14001B58F
0x14001b586  movzx   esi, ax
0x14001b589  or      esi, 80070000h
0x14001b58f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b596  lea     r14, WPP_GLOBAL_Control
0x14001b59d  cmp     rcx, r14
0x14001b5a0  jz      loc_14001B99D
0x14001b5a6  test    byte ptr [rcx+1Ch], 1
0x14001b5aa  jz      loc_14001B99D
0x14001b5b0  mov     edx, 31h ; '1'
0x14001b5b5  jmp     loc_14001B983
0x14001b5ba  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x14001b5bf  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001b5c4  xor     r9d, r9d; TokenInformationLength
0x14001b5c7  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001b5cc  xor     r8d, r8d; TokenInformation
0x14001b5cf  lea     edx, [r9+1]; TokenInformationClass
0x14001b5d3  call    cs:__imp_GetTokenInformation
0x14001b5d9  test    eax, eax
0x14001b5db  jnz     loc_14001B950
0x14001b5e1  call    cs:__imp_GetLastError
0x14001b5e7  cmp     eax, 7Ah ; 'z'
0x14001b5ea  jnz     loc_14001B950
0x14001b5f0  mov     ecx, [rsp+2D0h+TokenInformationLength]; unsigned __int64
0x14001b5f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b5fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001b600  mov     rdi, rax
0x14001b603  test    rax, rax
0x14001b606  jnz     short loc_14001B64E
0x14001b608  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b60f  lea     r14, WPP_GLOBAL_Control
0x14001b616  cmp     rcx, r14
0x14001b619  jz      loc_14001B9CE
0x14001b61f  test    byte ptr [rcx+1Ch], 1
0x14001b623  jz      loc_14001B9A1
0x14001b629  mov     rcx, [rcx+10h]
0x14001b62d  lea     edx, [rax+33h]
0x14001b630  mov     r9d, 8007000Eh
0x14001b636  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b63d  call    WPP_SF_d
0x14001b642  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b649  jmp     loc_14001B9A1
0x14001b64e  mov     r9d, [rsp+2D0h+TokenInformationLength]; TokenInformationLength
0x14001b653  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001b658  mov     rcx, [rsp+2D0h+TokenHandle]; TokenHandle
0x14001b65d  mov     r8, rdi; TokenInformation
0x14001b660  mov     edx, 1; TokenInformationClass
0x14001b665  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001b66a  call    cs:__imp_GetTokenInformation
0x14001b670  test    eax, eax
0x14001b672  jnz     short loc_14001B6B4
0x14001b674  call    cs:__imp_GetLastError
0x14001b67a  mov     esi, eax
0x14001b67c  test    eax, eax
0x14001b67e  jle     short loc_14001B689
0x14001b680  movzx   esi, ax
0x14001b683  or      esi, 80070000h
0x14001b689  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b690  lea     r14, WPP_GLOBAL_Control
0x14001b697  cmp     rcx, r14
0x14001b69a  jz      loc_14001B99D
0x14001b6a0  test    byte ptr [rcx+1Ch], 1
0x14001b6a4  jz      loc_14001B99D
0x14001b6aa  mov     edx, 34h ; '4'
0x14001b6af  jmp     loc_14001B983
0x14001b6b4  lea     rcx, [rsp+2D0h+hObject]
0x14001b6b9  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x14001b6be  mov     r8, rax; TokenHandle
0x14001b6c1  mov     edx, 20008h; DesiredAccess
0x14001b6c6  mov     rcx, r14; ProcessHandle
0x14001b6c9  call    cs:__imp_OpenProcessToken
0x14001b6cf  test    eax, eax
0x14001b6d1  jnz     short loc_14001B713
0x14001b6d3  call    cs:__imp_GetLastError
0x14001b6d9  mov     esi, eax
0x14001b6db  test    eax, eax
0x14001b6dd  jle     short loc_14001B6E8
0x14001b6df  movzx   esi, ax
0x14001b6e2  or      esi, 80070000h
0x14001b6e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b6ef  lea     r14, WPP_GLOBAL_Control
0x14001b6f6  cmp     rcx, r14
0x14001b6f9  jz      loc_14001B99D
0x14001b6ff  test    byte ptr [rcx+1Ch], 1
0x14001b703  jz      loc_14001B99D
0x14001b709  mov     edx, 35h ; '5'
0x14001b70e  jmp     loc_14001B983
0x14001b713  mov     rcx, [rsp+2D0h+hObject]; TokenHandle
0x14001b718  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001b71d  xor     r9d, r9d; TokenInformationLength
0x14001b720  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001b725  xor     r8d, r8d; TokenInformation
0x14001b728  lea     edx, [r9+1]; TokenInformationClass
0x14001b72c  call    cs:__imp_GetTokenInformation
0x14001b732  test    eax, eax
0x14001b734  jnz     loc_14001B91B
0x14001b73a  call    cs:__imp_GetLastError
0x14001b740  cmp     eax, 7Ah ; 'z'
0x14001b743  jnz     loc_14001B91B
0x14001b749  mov     ecx, [rsp+2D0h+TokenInformationLength]; unsigned __int64
0x14001b74d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b754  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001b759  mov     rbx, rax
0x14001b75c  test    rax, rax
0x14001b75f  jnz     short loc_14001B79A
0x14001b761  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b768  lea     r14, WPP_GLOBAL_Control
0x14001b76f  cmp     rcx, r14
0x14001b772  jz      loc_14001B9CE
0x14001b778  test    byte ptr [rcx+1Ch], 1
0x14001b77c  jz      loc_14001B9A1
0x14001b782  lea     edx, [rax+37h]
0x14001b785  mov     rcx, [rcx+10h]
0x14001b789  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b790  call    WPP_SF_
0x14001b795  jmp     loc_14001B642
0x14001b79a  mov     r9d, [rsp+2D0h+TokenInformationLength]; TokenInformationLength
0x14001b79f  lea     rax, [rsp+2D0h+TokenInformationLength]
0x14001b7a4  mov     rcx, [rsp+2D0h+hObject]; TokenHandle
0x14001b7a9  mov     r8, rbx; TokenInformation
0x14001b7ac  mov     edx, 1; TokenInformationClass
0x14001b7b1  mov     [rsp+2D0h+ReturnLength], rax; ReturnLength
0x14001b7b6  call    cs:__imp_GetTokenInformation
0x14001b7bc  test    eax, eax
0x14001b7be  jnz     short loc_14001B800
0x14001b7c0  call    cs:__imp_GetLastError
0x14001b7c6  mov     esi, eax
0x14001b7c8  test    eax, eax
0x14001b7ca  jle     short loc_14001B7D5
0x14001b7cc  movzx   esi, ax
0x14001b7cf  or      esi, 80070000h
0x14001b7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b7dc  lea     r14, WPP_GLOBAL_Control
0x14001b7e3  cmp     rcx, r14
0x14001b7e6  jz      loc_14001B99D
0x14001b7ec  test    byte ptr [rcx+1Ch], 1
0x14001b7f0  jz      loc_14001B99D
0x14001b7f6  mov     edx, 38h ; '8'
0x14001b7fb  jmp     loc_14001B983
0x14001b800  mov     rdx, [rdi]; pSid2
0x14001b803  mov     rcx, [rbx]; pSid1
0x14001b806  call    cs:__imp_EqualSid
0x14001b80c  test    eax, eax
0x14001b80e  jnz     short loc_14001B839
0x14001b810  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b817  lea     r14, WPP_GLOBAL_Control
0x14001b81e  cmp     rcx, r14
0x14001b821  jz      loc_14001B9C6
0x14001b827  test    byte ptr [rcx+1Ch], 1
0x14001b82b  jz      loc_14001B9A1
0x14001b831  lea     edx, [rax+39h]
0x14001b834  jmp     loc_14001B785
0x14001b839  mov     r9d, 104h; nSize
0x14001b83f  lea     r8, [rbp+1D0h+Filename]; lpFilename
0x14001b843  xor     edx, edx; hModule
0x14001b845  mov     rcx, r15; hProcess
0x14001b848  call    cs:__imp_K32GetModuleFileNameExW
0x14001b84e  test    eax, eax
0x14001b850  jnz     short loc_14001B892
0x14001b852  call    cs:__imp_GetLastError
0x14001b858  mov     esi, eax
0x14001b85a  test    eax, eax
0x14001b85c  jle     short loc_14001B867
0x14001b85e  movzx   esi, ax
0x14001b861  or      esi, 80070000h
0x14001b867  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b86e  lea     r14, WPP_GLOBAL_Control
0x14001b875  cmp     rcx, r14
0x14001b878  jz      loc_14001B99D
0x14001b87e  test    byte ptr [rcx+1Ch], 1
0x14001b882  jz      loc_14001B99D
0x14001b888  mov     edx, 3Ah ; ':'
0x14001b88d  jmp     loc_14001B983
0x14001b892  xor     r9d, r9d
0x14001b895  mov     dword ptr [rsp+2D0h+ReturnLength], 0; int
0x14001b89d  xor     r8d, r8d
0x14001b8a0  lea     rdx, [rsp+2D0h+var_288]
0x14001b8a5  lea     rcx, [rbp+1D0h+Filename]; lpwstrFilename
0x14001b8a9  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x14001b8ae  test    eax, eax
0x14001b8b0  jns     short loc_14001B8F5
0x14001b8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8b9  lea     r14, WPP_GLOBAL_Control
0x14001b8c0  cmp     rcx, r14
0x14001b8c3  jz      loc_14001B9C1
0x14001b8c9  test    byte ptr [rcx+1Ch], 1
0x14001b8cd  jz      loc_14001B9A1
0x14001b8d3  mov     rcx, [rcx+10h]
0x14001b8d7  lea     r9, [rbp+1D0h+Filename]
0x14001b8db  mov     edx, 3Bh ; ';'
0x14001b8e0  mov     dword ptr [rsp+2D0h+ReturnLength], eax
0x14001b8e4  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b8eb  call    WPP_SF_Sd
0x14001b8f0  jmp     loc_14001B642
0x14001b8f5  mov     ecx, dword ptr [rsp+2D0h+var_288+8]
0x14001b8f9  mov     eax, ecx
0x14001b8fb  shr     eax, 10h
0x14001b8fe  mov     [rsi], ax
0x14001b901  mov     [rsi+2], cx
0x14001b905  mov     ecx, dword ptr [rsp+2D0h+var_288+0Ch]
0x14001b909  mov     eax, ecx
0x14001b90b  shr     eax, 10h
0x14001b90e  mov     [rsi+4], ax
0x14001b912  mov     [rsi+6], cx
0x14001b916  jmp     loc_14001B9C6
0x14001b91b  call    cs:__imp_GetLastError
0x14001b921  mov     esi, eax
0x14001b923  test    eax, eax
0x14001b925  jle     short loc_14001B930
0x14001b927  movzx   esi, ax
0x14001b92a  or      esi, 80070000h
0x14001b930  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b937  lea     r14, WPP_GLOBAL_Control
0x14001b93e  cmp     rcx, r14
0x14001b941  jz      short loc_14001B99D
0x14001b943  test    byte ptr [rcx+1Ch], 1
0x14001b947  jz      short loc_14001B99D
0x14001b949  mov     edx, 36h ; '6'
0x14001b94e  jmp     short loc_14001B983
0x14001b950  call    cs:__imp_GetLastError
0x14001b956  mov     esi, eax
0x14001b958  test    eax, eax
0x14001b95a  jle     short loc_14001B965
0x14001b95c  movzx   esi, ax
0x14001b95f  or      esi, 80070000h
0x14001b965  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b96c  lea     r14, WPP_GLOBAL_Control
0x14001b973  cmp     rcx, r14
0x14001b976  jz      short loc_14001B99D
0x14001b978  test    byte ptr [rcx+1Ch], 1
0x14001b97c  jz      short loc_14001B99D
0x14001b97e  mov     edx, 32h ; '2'
0x14001b983  mov     rcx, [rcx+10h]
0x14001b987  lea     r8, WPP_7464a2c5d2ed3c7e486d29065e766280_Traceguids
0x14001b98e  mov     r9d, esi
0x14001b991  call    WPP_SF_d
0x14001b996  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b99d  test    esi, esi
0x14001b99f  jns     short loc_14001B9C1
0x14001b9a1  cmp     rcx, r14
  ... truncated ...
```

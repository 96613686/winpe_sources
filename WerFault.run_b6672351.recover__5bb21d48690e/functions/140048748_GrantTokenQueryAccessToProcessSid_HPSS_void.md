# GrantTokenQueryAccessToProcessSid(HPSS__ *,void *)

- ea: `0x140048748`
- end: `0x140048c87`
- name: `?GrantTokenQueryAccessToProcessSid@@YAJPEAUHPSS__@@PEAX@Z`
- size: `1343`
- prototype: `int(struct HPSS__ *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140047b58`

## callees

- `0x140002748`
- `0x1400041e8`
- `0x140005550`
- `0x14001186c`
- `0x140014f14`
- `0x140048748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004889c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004890e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400489dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004889c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004890e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400489dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048b29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140048be0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004888c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004888c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048c5c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1400488f9`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1400489cd`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1400488f9`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1400489cd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140048a2e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140048a2e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140048b19`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140048b19`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140048b79`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140048b79`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x140048bd0`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x140048bd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140048ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140048c26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140048ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140048c26`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x14004881e`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x14004881e`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140048ace`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x140048ace`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GrantTokenQueryAccessToProcessSid(struct HPSS__ *a1, void *a2)
{
  void *v3; // rsi
  const struct std::nothrow_t *v4; // rdx
  signed int ProcessUserSid; // ebx
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  void **v8; // rax
  signed int v9; // eax
  signed int LastError; // eax
  DWORD v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-59h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-51h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+40h] [rbp-49h] BYREF
  PACL pDacl[2]; // [rsp+48h] [rbp-41h] BYREF
  HANDLE ProcessHandle; // [rsp+58h] [rbp-31h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-29h] BYREF
  void *v25; // [rsp+90h] [rbp+7h]
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+B8h] [rbp+2Fh]
  DWORD nLengthNeeded; // [rsp+100h] [rbp+77h] BYREF
  WINBOOL bDaclPresent; // [rsp+108h] [rbp+7Fh] BYREF

  ProcessHandle = 0;
  Handle = 0;
  pDacl[1] = 0;
  nLengthNeeded = 0;
  v3 = 0;
  v25 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v27 = 0;
  pDacl[0] = 0;
  hMem = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  ProcessUserSid = UtilGetProcessUserSid(a2);
  if ( ProcessUserSid >= 0 )
  {
    ProcessUserSid = PssQuerySnapshot(a1, 1, &ProcessHandle, 8);
    if ( ProcessUserSid )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids,
          (unsigned int)ProcessUserSid);
      }
      if ( ProcessUserSid > 0 )
        ProcessUserSid = (unsigned __int16)ProcessUserSid | 0x80070000;
      goto LABEL_72;
    }
    v8 = (void **)tlx::replace<tlx::file_handle_traits>(&Handle);
    if ( OpenProcessToken(ProcessHandle, 0xF01FFu, v8) )
    {
      if ( GetKernelObjectSecurity(Handle, 4u, 0, 0, &nLengthNeeded) )
      {
        v11 = nLengthNeeded;
      }
      else
      {
        LastError = GetLastError();
        ProcessUserSid = LastError;
        if ( LastError > 0 )
          ProcessUserSid = (unsigned __int16)LastError | 0x80070000;
        if ( ProcessUserSid >= 0 )
          ProcessUserSid = -2147467259;
        v11 = nLengthNeeded;
        if ( !nLengthNeeded || ProcessUserSid != -2147024774 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 13;
            goto LABEL_5;
          }
          goto LABEL_72;
        }
      }
      v3 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
      v25 = v3;
      if ( v3 )
      {
        if ( GetKernelObjectSecurity(Handle, 4u, v3, nLengthNeeded, &nLengthNeeded) )
        {
          if ( GetSecurityDescriptorDacl(v3, &bDaclPresent, pDacl, &bDaclDefaulted) )
          {
            if ( !bDaclPresent )
              pDacl[0] = 0;
            pListOfExplicitEntries.grfAccessPermissions = 8;
            *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 1;
            pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
            *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
            pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
            pListOfExplicitEntries.Trustee.ptstrName = 0;
            hMem = 0;
            v14 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl[0], (PACL *)&hMem);
            ProcessUserSid = v14;
            if ( v14 )
            {
              if ( v14 > 0 )
                ProcessUserSid = (unsigned __int16)v14 | 0x80070000;
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v7 = 17;
                goto LABEL_5;
              }
            }
            else if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
            {
              if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, (PACL)hMem, 0) )
              {
                if ( SetKernelObjectSecurity(Handle, 4u, pSecurityDescriptor) )
                {
                  ProcessUserSid = 0;
                }
                else
                {
                  v17 = GetLastError();
                  ProcessUserSid = v17;
                  if ( v17 > 0 )
                    ProcessUserSid = (unsigned __int16)v17 | 0x80070000;
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v7 = 20;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                v16 = GetLastError();
                ProcessUserSid = v16;
                if ( v16 > 0 )
                  ProcessUserSid = (unsigned __int16)v16 | 0x80070000;
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v7 = 19;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              v15 = GetLastError();
              ProcessUserSid = v15;
              if ( v15 > 0 )
                ProcessUserSid = (unsigned __int16)v15 | 0x80070000;
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v7 = 18;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v13 = GetLastError();
            ProcessUserSid = v13;
            if ( v13 > 0 )
              ProcessUserSid = (unsigned __int16)v13 | 0x80070000;
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 16;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v12 = GetLastError();
          ProcessUserSid = v12;
          if ( v12 > 0 )
            ProcessUserSid = (unsigned __int16)v12 | 0x80070000;
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v7 = 15;
            goto LABEL_5;
          }
        }
      }
      else
      {
        ProcessUserSid = -2147024882;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 14;
          goto LABEL_5;
        }
      }
      goto LABEL_72;
    }
    v9 = GetLastError();
    ProcessUserSid = v9;
    if ( v9 > 0 )
      ProcessUserSid = (unsigned __int16)v9 | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 12;
      goto LABEL_5;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 10;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids, (unsigned int)ProcessUserSid);
    }
  }
LABEL_72:
  if ( hMem )
    LocalFree(hMem);
  if ( v3 )
    operator delete(v3, v4);
  if ( (unsigned __int64)Handle + 1 > 1 )
    CloseHandle(Handle);
  return (unsigned int)ProcessUserSid;
}

```

## disassembly

```asm
0x140048748  mov     [rsp-8+arg_0], rbx
0x14004874d  mov     [rsp-8+arg_8], rsi
0x140048752  push    rbp
0x140048753  push    rdi
0x140048754  push    r12
0x140048756  push    r14
0x140048758  push    r15
0x14004875a  lea     rbp, [rsp-37h]
0x14004875f  sub     rsp, 0C0h
0x140048766  mov     rax, rdx
0x140048769  mov     rdi, rcx
0x14004876c  xor     r15d, r15d
0x14004876f  mov     [rbp+57h+ProcessHandle], r15
0x140048773  mov     [rbp+57h+Handle], r15
0x140048777  mov     [rbp+57h+var_90], r15
0x14004877b  mov     [rbp+57h+nLengthNeeded], r15d
0x14004877f  mov     esi, r15d
0x140048782  mov     [rbp+57h+var_50], r15
0x140048786  xorps   xmm0, xmm0
0x140048789  xor     ecx, ecx
0x14004878b  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x14004878f  movups  [rbp+57h+var_38], xmm0
0x140048793  mov     [rbp+57h+var_28], rcx
0x140048797  mov     [rbp+57h+pDacl], r15
0x14004879b  mov     [rbp+57h+hMem], r15
0x14004879f  mov     [rbp+57h+bDaclPresent], r15d
0x1400487a3  mov     [rbp+57h+bDaclDefaulted], r15d
0x1400487a7  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], r15d
0x1400487ab  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], xmm0
0x1400487af  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee+4], xmm0
0x1400487b3  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1400487b7  lea     rdx, [rbp+57h+var_90]
0x1400487bb  mov     rcx, rax; ProcessHandle
0x1400487be  call    ?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x1400487c3  mov     ebx, eax
0x1400487c5  mov     r14, [rbp+57h+var_90]
0x1400487c9  lea     r12d, [r15+1]
0x1400487cd  test    eax, eax
0x1400487cf  jns     short loc_14004880E
0x1400487d1  lea     rax, WPP_GLOBAL_Control
0x1400487d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487df  cmp     rcx, rax
0x1400487e2  jz      loc_140048C1D
0x1400487e8  test    [rcx+1Ch], r12b
0x1400487ec  jz      loc_140048C1D
0x1400487f2  lea     edx, [r15+0Ah]
0x1400487f6  mov     r9d, ebx
0x1400487f9  lea     r8, WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids
0x140048800  mov     rcx, [rcx+10h]
0x140048804  call    WPP_SF_d
0x140048809  jmp     loc_140048C1D
0x14004880e  mov     r9d, 8
0x140048814  lea     r8, [rbp+57h+ProcessHandle]
0x140048818  mov     edx, r12d
0x14004881b  mov     rcx, rdi
0x14004881e  call    cs:__imp_PssQuerySnapshot
0x140048825  nop     dword ptr [rax+rax+00h]
0x14004882a  mov     ebx, eax
0x14004882c  test    eax, eax
0x14004882e  jz      short loc_140048877
0x140048830  lea     rax, WPP_GLOBAL_Control
0x140048837  mov     rcx, cs:WPP_GLOBAL_Control
0x14004883e  cmp     rcx, rax
0x140048841  jz      short loc_140048861
0x140048843  test    byte ptr [rcx+1Ch], 2
0x140048847  jz      short loc_140048861
0x140048849  mov     edx, 0Bh
0x14004884e  mov     r9d, ebx
0x140048851  lea     r8, WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids
0x140048858  mov     rcx, [rcx+10h]
0x14004885c  call    WPP_SF_d
0x140048861  test    ebx, ebx
0x140048863  jle     loc_140048C1D
0x140048869  movzx   ebx, bx
0x14004886c  or      ebx, 80070000h
0x140048872  jmp     loc_140048C1D
0x140048877  lea     rcx, [rbp+57h+Handle]
0x14004887b  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140048880  mov     r8, rax; TokenHandle
0x140048883  mov     edx, 0F01FFh; DesiredAccess
0x140048888  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14004888c  call    cs:__imp_OpenProcessToken
0x140048893  nop     dword ptr [rax+rax+00h]
0x140048898  test    eax, eax
0x14004889a  jnz     short loc_1400488E2
0x14004889c  call    cs:__imp_GetLastError
0x1400488a3  nop     dword ptr [rax+rax+00h]
0x1400488a8  mov     ebx, eax
0x1400488aa  test    eax, eax
0x1400488ac  jle     short loc_1400488B7
0x1400488ae  movzx   ebx, ax
0x1400488b1  or      ebx, 80070000h
0x1400488b7  lea     rax, WPP_GLOBAL_Control
0x1400488be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488c5  cmp     rcx, rax
0x1400488c8  jz      loc_140048C1D
0x1400488ce  test    [rcx+1Ch], r12b
0x1400488d2  jz      loc_140048C1D
0x1400488d8  mov     edx, 0Ch
0x1400488dd  jmp     loc_1400487F6
0x1400488e2  lea     rax, [rbp+57h+nLengthNeeded]
0x1400488e6  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400488eb  xor     r9d, r9d; nLength
0x1400488ee  xor     r8d, r8d; pSecurityDescriptor
0x1400488f1  lea     edx, [r9+4]; RequestedInformation
0x1400488f5  mov     rcx, [rbp+57h+Handle]; Handle
0x1400488f9  call    cs:__imp_GetKernelObjectSecurity
0x140048900  nop     dword ptr [rax+rax+00h]
0x140048905  mov     edi, 80070000h
0x14004890a  test    eax, eax
0x14004890c  jnz     short loc_140048969
0x14004890e  call    cs:__imp_GetLastError
0x140048915  nop     dword ptr [rax+rax+00h]
0x14004891a  mov     ebx, eax
0x14004891c  test    eax, eax
0x14004891e  jle     short loc_140048925
0x140048920  movzx   ebx, ax
0x140048923  or      ebx, edi
0x140048925  mov     eax, 80004005h
0x14004892a  test    ebx, ebx
0x14004892c  cmovns  ebx, eax
0x14004892f  mov     eax, [rbp+57h+nLengthNeeded]
0x140048932  test    eax, eax
0x140048934  jz      short loc_14004893E
0x140048936  cmp     ebx, 8007007Ah
0x14004893c  jz      short loc_14004896C
0x14004893e  lea     rax, WPP_GLOBAL_Control
0x140048945  mov     rcx, cs:WPP_GLOBAL_Control
0x14004894c  cmp     rcx, rax
0x14004894f  jz      loc_140048C1D
0x140048955  test    [rcx+1Ch], r12b
0x140048959  jz      loc_140048C1D
0x14004895f  mov     edx, 0Dh
0x140048964  jmp     loc_1400487F6
0x140048969  mov     eax, [rbp+57h+nLengthNeeded]
0x14004896c  mov     ecx, eax; unsigned __int64
0x14004896e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140048975  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14004897a  mov     rsi, rax
0x14004897d  mov     [rbp+57h+var_50], rax
0x140048981  test    rax, rax
0x140048984  jnz     short loc_1400489B4
0x140048986  mov     ebx, 8007000Eh
0x14004898b  lea     rax, WPP_GLOBAL_Control
0x140048992  mov     rcx, cs:WPP_GLOBAL_Control
0x140048999  cmp     rcx, rax
0x14004899c  jz      loc_140048C1D
0x1400489a2  test    [rcx+1Ch], r12b
0x1400489a6  jz      loc_140048C1D
0x1400489ac  lea     edx, [rsi+0Eh]
0x1400489af  jmp     loc_1400487F6
0x1400489b4  lea     rax, [rbp+57h+nLengthNeeded]
0x1400489b8  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1400489bd  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1400489c1  mov     r8, rsi; pSecurityDescriptor
0x1400489c4  mov     edx, 4; RequestedInformation
0x1400489c9  mov     rcx, [rbp+57h+Handle]; Handle
0x1400489cd  call    cs:__imp_GetKernelObjectSecurity
0x1400489d4  nop     dword ptr [rax+rax+00h]
0x1400489d9  test    eax, eax
0x1400489db  jnz     short loc_140048A1F
0x1400489dd  call    cs:__imp_GetLastError
0x1400489e4  nop     dword ptr [rax+rax+00h]
0x1400489e9  mov     ebx, eax
0x1400489eb  test    eax, eax
0x1400489ed  jle     short loc_1400489F4
0x1400489ef  movzx   ebx, ax
0x1400489f2  or      ebx, edi
0x1400489f4  lea     rax, WPP_GLOBAL_Control
0x1400489fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a02  cmp     rcx, rax
0x140048a05  jz      loc_140048C1D
0x140048a0b  test    [rcx+1Ch], r12b
0x140048a0f  jz      loc_140048C1D
0x140048a15  mov     edx, 0Fh
0x140048a1a  jmp     loc_1400487F6
0x140048a1f  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x140048a23  lea     r8, [rbp+57h+pDacl]; pDacl
0x140048a27  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x140048a2b  mov     rcx, rsi; pSecurityDescriptor
0x140048a2e  call    cs:__imp_GetSecurityDescriptorDacl
0x140048a35  nop     dword ptr [rax+rax+00h]
0x140048a3a  test    eax, eax
0x140048a3c  jnz     short loc_140048A80
0x140048a3e  call    cs:__imp_GetLastError
0x140048a45  nop     dword ptr [rax+rax+00h]
0x140048a4a  mov     ebx, eax
0x140048a4c  test    eax, eax
0x140048a4e  jle     short loc_140048A55
0x140048a50  movzx   ebx, ax
0x140048a53  or      ebx, edi
0x140048a55  lea     rax, WPP_GLOBAL_Control
0x140048a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a63  cmp     rcx, rax
0x140048a66  jz      loc_140048C1D
0x140048a6c  test    [rcx+1Ch], r12b
0x140048a70  jz      loc_140048C1D
0x140048a76  mov     edx, 10h
0x140048a7b  jmp     loc_1400487F6
0x140048a80  cmp     [rbp+57h+bDaclPresent], r15d
0x140048a84  jnz     short loc_140048A8A
0x140048a86  mov     [rbp+57h+pDacl], r15
0x140048a8a  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 8
0x140048a91  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], r12
0x140048a95  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r15
0x140048a99  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r15
0x140048a9d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r12d
0x140048aa1  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x140048aa5  mov     rcx, [rbp+57h+hMem]; hMem
0x140048aa9  mov     [rbp+57h+hMem], r15
0x140048aad  test    rcx, rcx
0x140048ab0  jz      short loc_140048ABF
0x140048ab2  call    cs:__imp_LocalFree
0x140048ab9  nop     dword ptr [rax+rax+00h]
0x140048abe  nop
0x140048abf  lea     r9, [rbp+57h+hMem]; NewAcl
0x140048ac3  mov     r8, [rbp+57h+pDacl]; OldAcl
0x140048ac7  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x140048acb  mov     ecx, r12d; cCountOfExplicitEntries
0x140048ace  call    cs:__imp_SetEntriesInAclW
0x140048ad5  nop     dword ptr [rax+rax+00h]
0x140048ada  mov     ebx, eax
0x140048adc  test    eax, eax
0x140048ade  jz      short loc_140048B12
0x140048ae0  jle     short loc_140048AE7
0x140048ae2  movzx   ebx, ax
0x140048ae5  or      ebx, edi
0x140048ae7  lea     rax, WPP_GLOBAL_Control
0x140048aee  mov     rcx, cs:WPP_GLOBAL_Control
0x140048af5  cmp     rcx, rax
0x140048af8  jz      loc_140048C1D
0x140048afe  test    [rcx+1Ch], r12b
0x140048b02  jz      loc_140048C1D
0x140048b08  mov     edx, 11h
0x140048b0d  jmp     loc_1400487F6
0x140048b12  mov     edx, r12d; dwRevision
0x140048b15  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140048b19  call    cs:__imp_InitializeSecurityDescriptor
0x140048b20  nop     dword ptr [rax+rax+00h]
0x140048b25  test    eax, eax
0x140048b27  jnz     short loc_140048B6B
0x140048b29  call    cs:__imp_GetLastError
0x140048b30  nop     dword ptr [rax+rax+00h]
0x140048b35  mov     ebx, eax
0x140048b37  test    eax, eax
0x140048b39  jle     short loc_140048B40
0x140048b3b  movzx   ebx, ax
0x140048b3e  or      ebx, edi
0x140048b40  lea     rax, WPP_GLOBAL_Control
0x140048b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140048b4e  cmp     rcx, rax
0x140048b51  jz      loc_140048C1D
0x140048b57  test    [rcx+1Ch], r12b
0x140048b5b  jz      loc_140048C1D
0x140048b61  mov     edx, 12h
0x140048b66  jmp     loc_1400487F6
0x140048b6b  xor     r9d, r9d; bDaclDefaulted
0x140048b6e  mov     r8, [rbp+57h+hMem]; pDacl
0x140048b72  mov     edx, r12d; bDaclPresent
0x140048b75  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140048b79  call    cs:__imp_SetSecurityDescriptorDacl
0x140048b80  nop     dword ptr [rax+rax+00h]
0x140048b85  test    eax, eax
0x140048b87  jnz     short loc_140048BC3
0x140048b89  call    cs:__imp_GetLastError
0x140048b90  nop     dword ptr [rax+rax+00h]
0x140048b95  mov     ebx, eax
0x140048b97  test    eax, eax
0x140048b99  jle     short loc_140048BA0
0x140048b9b  movzx   ebx, ax
0x140048b9e  or      ebx, edi
0x140048ba0  lea     rax, WPP_GLOBAL_Control
0x140048ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x140048bae  cmp     rcx, rax
0x140048bb1  jz      short loc_140048C1D
0x140048bb3  test    [rcx+1Ch], r12b
0x140048bb7  jz      short loc_140048C1D
0x140048bb9  mov     edx, 13h
0x140048bbe  jmp     loc_1400487F6
0x140048bc3  lea     r8, [rbp+57h+pSecurityDescriptor]; SecurityDescriptor
0x140048bc7  mov     edx, 4; SecurityInformation
0x140048bcc  mov     rcx, [rbp+57h+Handle]; Handle
0x140048bd0  call    cs:__imp_SetKernelObjectSecurity
0x140048bd7  nop     dword ptr [rax+rax+00h]
0x140048bdc  test    eax, eax
0x140048bde  jnz     short loc_140048C1A
0x140048be0  call    cs:__imp_GetLastError
0x140048be7  nop     dword ptr [rax+rax+00h]
0x140048bec  mov     ebx, eax
0x140048bee  test    eax, eax
0x140048bf0  jle     short loc_140048BF7
0x140048bf2  movzx   ebx, ax
0x140048bf5  or      ebx, edi
0x140048bf7  lea     rax, WPP_GLOBAL_Control
0x140048bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140048c05  cmp     rcx, rax
0x140048c08  jz      short loc_140048C1D
0x140048c0a  test    [rcx+1Ch], r12b
0x140048c0e  jz      short loc_140048C1D
0x140048c10  mov     edx, 14h
  ... truncated ...
```

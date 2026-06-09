# GrantTokenQueryAccessToProcessSid(HPSS__ *,void *)

- ea: `0x1400455ac`
- end: `0x140045a78`
- name: `?GrantTokenQueryAccessToProcessSid@@YAJPEAUHPSS__@@PEAX@Z`
- size: `1228`
- prototype: `__int64 __fastcall(struct HPSS__ *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140044abc`

## callees

- `0x140002728`
- `0x140004198`
- `0x140005498`
- `0x14001114c`
- `0x140014474`
- `0x1400455ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400456f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004575a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004581d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400459e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400456f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004575a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004581d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140045999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400459e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400456ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400456ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140045a54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140045a54`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14004574b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x140045813`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14004574b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x140045813`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140045868`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x140045868`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14004593b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14004593b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14004598f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x14004598f`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1400459da`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x1400459da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400458e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045a24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400458e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140045a24`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140045682`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x140045682`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1400458f6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1400458f6`

## pseudocode

```c
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
0x1400455ac  mov     [rsp-8+arg_0], rbx
0x1400455b1  mov     [rsp-8+arg_8], rsi
0x1400455b6  push    rbp
0x1400455b7  push    rdi
0x1400455b8  push    r12
0x1400455ba  push    r14
0x1400455bc  push    r15
0x1400455be  lea     rbp, [rsp-37h]
0x1400455c3  sub     rsp, 0C0h
0x1400455ca  mov     rax, rdx
0x1400455cd  mov     rdi, rcx
0x1400455d0  xor     r15d, r15d
0x1400455d3  mov     [rbp+57h+ProcessHandle], r15
0x1400455d7  mov     [rbp+57h+Handle], r15
0x1400455db  mov     [rbp+57h+var_90], r15
0x1400455df  mov     [rbp+57h+nLengthNeeded], r15d
0x1400455e3  mov     esi, r15d
0x1400455e6  mov     [rbp+57h+var_50], r15
0x1400455ea  xorps   xmm0, xmm0
0x1400455ed  xor     ecx, ecx
0x1400455ef  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x1400455f3  movups  [rbp+57h+var_38], xmm0
0x1400455f7  mov     [rbp+57h+var_28], rcx
0x1400455fb  mov     [rbp+57h+pDacl], r15
0x1400455ff  mov     [rbp+57h+hMem], r15
0x140045603  mov     [rbp+57h+bDaclPresent], r15d
0x140045607  mov     [rbp+57h+bDaclDefaulted], r15d
0x14004560b  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], r15d
0x14004560f  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], xmm0
0x140045613  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee+4], xmm0
0x140045617  movups  xmmword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x14004561b  lea     rdx, [rbp+57h+var_90]
0x14004561f  mov     rcx, rax; ProcessHandle
0x140045622  call    ?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x140045627  mov     ebx, eax
0x140045629  mov     r14, [rbp+57h+var_90]
0x14004562d  lea     r12d, [r15+1]
0x140045631  test    eax, eax
0x140045633  jns     short loc_140045672
0x140045635  lea     rax, WPP_GLOBAL_Control
0x14004563c  mov     rcx, cs:WPP_GLOBAL_Control
0x140045643  cmp     rcx, rax
0x140045646  jz      loc_140045A1B
0x14004564c  test    [rcx+1Ch], r12b
0x140045650  jz      loc_140045A1B
0x140045656  lea     edx, [r15+0Ah]
0x14004565a  mov     r9d, ebx
0x14004565d  lea     r8, WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids
0x140045664  mov     rcx, [rcx+10h]
0x140045668  call    WPP_SF_d
0x14004566d  jmp     loc_140045A1B
0x140045672  mov     r9d, 8
0x140045678  lea     r8, [rbp+57h+ProcessHandle]
0x14004567c  mov     edx, r12d
0x14004567f  mov     rcx, rdi
0x140045682  call    cs:__imp_PssQuerySnapshot
0x140045688  mov     ebx, eax
0x14004568a  test    eax, eax
0x14004568c  jz      short loc_1400456D5
0x14004568e  lea     rax, WPP_GLOBAL_Control
0x140045695  mov     rcx, cs:WPP_GLOBAL_Control
0x14004569c  cmp     rcx, rax
0x14004569f  jz      short loc_1400456BF
0x1400456a1  test    byte ptr [rcx+1Ch], 2
0x1400456a5  jz      short loc_1400456BF
0x1400456a7  mov     edx, 0Bh
0x1400456ac  mov     r9d, ebx
0x1400456af  lea     r8, WPP_6f75cda72bc433f65b146bf8166aa339_Traceguids
0x1400456b6  mov     rcx, [rcx+10h]
0x1400456ba  call    WPP_SF_d
0x1400456bf  test    ebx, ebx
0x1400456c1  jle     loc_140045A1B
0x1400456c7  movzx   ebx, bx
0x1400456ca  or      ebx, 80070000h
0x1400456d0  jmp     loc_140045A1B
0x1400456d5  lea     rcx, [rbp+57h+Handle]
0x1400456d9  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400456de  mov     r8, rax; TokenHandle
0x1400456e1  mov     edx, 0F01FFh; DesiredAccess
0x1400456e6  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400456ea  call    cs:__imp_OpenProcessToken
0x1400456f0  test    eax, eax
0x1400456f2  jnz     short loc_140045734
0x1400456f4  call    cs:__imp_GetLastError
0x1400456fa  mov     ebx, eax
0x1400456fc  test    eax, eax
0x1400456fe  jle     short loc_140045709
0x140045700  movzx   ebx, ax
0x140045703  or      ebx, 80070000h
0x140045709  lea     rax, WPP_GLOBAL_Control
0x140045710  mov     rcx, cs:WPP_GLOBAL_Control
0x140045717  cmp     rcx, rax
0x14004571a  jz      loc_140045A1B
0x140045720  test    [rcx+1Ch], r12b
0x140045724  jz      loc_140045A1B
0x14004572a  mov     edx, 0Ch
0x14004572f  jmp     loc_14004565A
0x140045734  lea     rax, [rbp+57h+nLengthNeeded]
0x140045738  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14004573d  xor     r9d, r9d; nLength
0x140045740  xor     r8d, r8d; pSecurityDescriptor
0x140045743  lea     edx, [r9+4]; RequestedInformation
0x140045747  mov     rcx, [rbp+57h+Handle]; Handle
0x14004574b  call    cs:__imp_GetKernelObjectSecurity
0x140045751  mov     edi, 80070000h
0x140045756  test    eax, eax
0x140045758  jnz     short loc_1400457AF
0x14004575a  call    cs:__imp_GetLastError
0x140045760  mov     ebx, eax
0x140045762  test    eax, eax
0x140045764  jle     short loc_14004576B
0x140045766  movzx   ebx, ax
0x140045769  or      ebx, edi
0x14004576b  mov     eax, 80004005h
0x140045770  test    ebx, ebx
0x140045772  cmovns  ebx, eax
0x140045775  mov     eax, [rbp+57h+nLengthNeeded]
0x140045778  test    eax, eax
0x14004577a  jz      short loc_140045784
0x14004577c  cmp     ebx, 8007007Ah
0x140045782  jz      short loc_1400457B2
0x140045784  lea     rax, WPP_GLOBAL_Control
0x14004578b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045792  cmp     rcx, rax
0x140045795  jz      loc_140045A1B
0x14004579b  test    [rcx+1Ch], r12b
0x14004579f  jz      loc_140045A1B
0x1400457a5  mov     edx, 0Dh
0x1400457aa  jmp     loc_14004565A
0x1400457af  mov     eax, [rbp+57h+nLengthNeeded]
0x1400457b2  mov     ecx, eax; unsigned __int64
0x1400457b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400457bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400457c0  mov     rsi, rax
0x1400457c3  mov     [rbp+57h+var_50], rax
0x1400457c7  test    rax, rax
0x1400457ca  jnz     short loc_1400457FA
0x1400457cc  mov     ebx, 8007000Eh
0x1400457d1  lea     rax, WPP_GLOBAL_Control
0x1400457d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457df  cmp     rcx, rax
0x1400457e2  jz      loc_140045A1B
0x1400457e8  test    [rcx+1Ch], r12b
0x1400457ec  jz      loc_140045A1B
0x1400457f2  lea     edx, [rsi+0Eh]
0x1400457f5  jmp     loc_14004565A
0x1400457fa  lea     rax, [rbp+57h+nLengthNeeded]
0x1400457fe  mov     [rsp+0E0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x140045803  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x140045807  mov     r8, rsi; pSecurityDescriptor
0x14004580a  mov     edx, 4; RequestedInformation
0x14004580f  mov     rcx, [rbp+57h+Handle]; Handle
0x140045813  call    cs:__imp_GetKernelObjectSecurity
0x140045819  test    eax, eax
0x14004581b  jnz     short loc_140045859
0x14004581d  call    cs:__imp_GetLastError
0x140045823  mov     ebx, eax
0x140045825  test    eax, eax
0x140045827  jle     short loc_14004582E
0x140045829  movzx   ebx, ax
0x14004582c  or      ebx, edi
0x14004582e  lea     rax, WPP_GLOBAL_Control
0x140045835  mov     rcx, cs:WPP_GLOBAL_Control
0x14004583c  cmp     rcx, rax
0x14004583f  jz      loc_140045A1B
0x140045845  test    [rcx+1Ch], r12b
0x140045849  jz      loc_140045A1B
0x14004584f  mov     edx, 0Fh
0x140045854  jmp     loc_14004565A
0x140045859  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x14004585d  lea     r8, [rbp+57h+pDacl]; pDacl
0x140045861  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x140045865  mov     rcx, rsi; pSecurityDescriptor
0x140045868  call    cs:__imp_GetSecurityDescriptorDacl
0x14004586e  test    eax, eax
0x140045870  jnz     short loc_1400458AE
0x140045872  call    cs:__imp_GetLastError
0x140045878  mov     ebx, eax
0x14004587a  test    eax, eax
0x14004587c  jle     short loc_140045883
0x14004587e  movzx   ebx, ax
0x140045881  or      ebx, edi
0x140045883  lea     rax, WPP_GLOBAL_Control
0x14004588a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045891  cmp     rcx, rax
0x140045894  jz      loc_140045A1B
0x14004589a  test    [rcx+1Ch], r12b
0x14004589e  jz      loc_140045A1B
0x1400458a4  mov     edx, 10h
0x1400458a9  jmp     loc_14004565A
0x1400458ae  cmp     [rbp+57h+bDaclPresent], r15d
0x1400458b2  jnz     short loc_1400458B8
0x1400458b4  mov     [rbp+57h+pDacl], r15
0x1400458b8  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 8
0x1400458bf  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], r12
0x1400458c3  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r15
0x1400458c7  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r15
0x1400458cb  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r12d
0x1400458cf  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], r14
0x1400458d3  mov     rcx, [rbp+57h+hMem]; hMem
0x1400458d7  mov     [rbp+57h+hMem], r15
0x1400458db  test    rcx, rcx
0x1400458de  jz      short loc_1400458E7
0x1400458e0  call    cs:__imp_LocalFree
0x1400458e6  nop
0x1400458e7  lea     r9, [rbp+57h+hMem]; NewAcl
0x1400458eb  mov     r8, [rbp+57h+pDacl]; OldAcl
0x1400458ef  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1400458f3  mov     ecx, r12d; cCountOfExplicitEntries
0x1400458f6  call    cs:__imp_SetEntriesInAclW
0x1400458fc  mov     ebx, eax
0x1400458fe  test    eax, eax
0x140045900  jz      short loc_140045934
0x140045902  jle     short loc_140045909
0x140045904  movzx   ebx, ax
0x140045907  or      ebx, edi
0x140045909  lea     rax, WPP_GLOBAL_Control
0x140045910  mov     rcx, cs:WPP_GLOBAL_Control
0x140045917  cmp     rcx, rax
0x14004591a  jz      loc_140045A1B
0x140045920  test    [rcx+1Ch], r12b
0x140045924  jz      loc_140045A1B
0x14004592a  mov     edx, 11h
0x14004592f  jmp     loc_14004565A
0x140045934  mov     edx, r12d; dwRevision
0x140045937  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14004593b  call    cs:__imp_InitializeSecurityDescriptor
0x140045941  test    eax, eax
0x140045943  jnz     short loc_140045981
0x140045945  call    cs:__imp_GetLastError
0x14004594b  mov     ebx, eax
0x14004594d  test    eax, eax
0x14004594f  jle     short loc_140045956
0x140045951  movzx   ebx, ax
0x140045954  or      ebx, edi
0x140045956  lea     rax, WPP_GLOBAL_Control
0x14004595d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045964  cmp     rcx, rax
0x140045967  jz      loc_140045A1B
0x14004596d  test    [rcx+1Ch], r12b
0x140045971  jz      loc_140045A1B
0x140045977  mov     edx, 12h
0x14004597c  jmp     loc_14004565A
0x140045981  xor     r9d, r9d; bDaclDefaulted
0x140045984  mov     r8, [rbp+57h+hMem]; pDacl
0x140045988  mov     edx, r12d; bDaclPresent
0x14004598b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14004598f  call    cs:__imp_SetSecurityDescriptorDacl
0x140045995  test    eax, eax
0x140045997  jnz     short loc_1400459CD
0x140045999  call    cs:__imp_GetLastError
0x14004599f  mov     ebx, eax
0x1400459a1  test    eax, eax
0x1400459a3  jle     short loc_1400459AA
0x1400459a5  movzx   ebx, ax
0x1400459a8  or      ebx, edi
0x1400459aa  lea     rax, WPP_GLOBAL_Control
0x1400459b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400459b8  cmp     rcx, rax
0x1400459bb  jz      short loc_140045A1B
0x1400459bd  test    [rcx+1Ch], r12b
0x1400459c1  jz      short loc_140045A1B
0x1400459c3  mov     edx, 13h
0x1400459c8  jmp     loc_14004565A
0x1400459cd  lea     r8, [rbp+57h+pSecurityDescriptor]; SecurityDescriptor
0x1400459d1  mov     edx, 4; SecurityInformation
0x1400459d6  mov     rcx, [rbp+57h+Handle]; Handle
0x1400459da  call    cs:__imp_SetKernelObjectSecurity
0x1400459e0  test    eax, eax
0x1400459e2  jnz     short loc_140045A18
0x1400459e4  call    cs:__imp_GetLastError
0x1400459ea  mov     ebx, eax
0x1400459ec  test    eax, eax
0x1400459ee  jle     short loc_1400459F5
0x1400459f0  movzx   ebx, ax
0x1400459f3  or      ebx, edi
0x1400459f5  lea     rax, WPP_GLOBAL_Control
0x1400459fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140045a03  cmp     rcx, rax
0x140045a06  jz      short loc_140045A1B
0x140045a08  test    [rcx+1Ch], r12b
0x140045a0c  jz      short loc_140045A1B
0x140045a0e  mov     edx, 14h
0x140045a13  jmp     loc_14004565A
0x140045a18  mov     ebx, r15d
0x140045a1b  mov     rcx, [rbp+57h+hMem]; hMem
0x140045a1f  test    rcx, rcx
0x140045a22  jz      short loc_140045A2B
0x140045a24  call    cs:__imp_LocalFree
0x140045a2a  nop
0x140045a2b  test    rsi, rsi
0x140045a2e  jz      short loc_140045A39
0x140045a30  mov     rcx, rsi; void *
0x140045a33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140045a38  nop
0x140045a39  test    r14, r14
0x140045a3c  jz      short loc_140045A47
0x140045a3e  mov     rcx, r14; void *
0x140045a41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140045a46  nop
  ... truncated ...
```

# CWSManSecurityUI::SetSecurity(ulong,void *)

- ea: `0x18012a480`
- end: `0x18012a935`
- name: `?SetSecurity@CWSManSecurityUI@@UEAAJKPEAX@Z`
- size: `1205`
- prototype: `__int64 __fastcall(CWSManSecurityUI *this, char, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800b5490`
- `0x1801123a8`
- `0x180112460`
- `0x18011a6d4`
- `0x18012636c`
- `0x18012a480`
- `0x18012a93c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a68a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a6e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a8e0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a5fa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a680`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a5fa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18012a680`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18012a6d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18012a75a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18012a6d9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18012a75a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a8f9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a902`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a91e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a8f9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a902`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18012a91e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18012a57e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18012a57e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18012a897`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18012a897`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWSManSecurityUI::SetSecurity(CWSManSecurityUI *this, char a2, void *a3)
{
  PVOID *v6; // rcx
  PSECURITY_DESCRIPTOR v7; // r15
  __int64 *v8; // r12
  __int64 v9; // rdx
  signed int v10; // ebx
  __int64 v11; // r14
  const WCHAR *v12; // rcx
  DWORD LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  struct _ACL *v16; // r8
  DWORD v17; // eax
  signed int v18; // eax
  DWORD v19; // eax
  signed int v20; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-30h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v25; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-10h] BYREF
  BOOL bDaclPresent; // [rsp+A0h] [rbp+40h] BYREF
  BOOL bDaclDefaulted; // [rsp+B0h] [rbp+50h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+B8h] [rbp+58h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, this, a2);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = 0;
  SecurityDescriptor = 0;
  v25 = 0;
  v8 = (__int64 *)((char *)this + 32);
  StringSecurityDescriptor = 0;
  pDacl = 0;
  pSacl = 0;
  if ( !a3 )
  {
    if ( v6 == &WPP_GLOBAL_Control || (*((_DWORD *)v6 + 7) & 0x1000000) == 0 )
      goto LABEL_9;
    v9 = 23;
LABEL_8:
    WPP_SF_q(v6[2], v9, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, this);
LABEL_9:
    v10 = -2147024809;
    goto LABEL_73;
  }
  if ( !*((_DWORD *)this + 13) )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000000) != 0 )
      WPP_SF_q(v6[2], 24, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, this);
    v10 = -2147467259;
    goto LABEL_73;
  }
  v11 = *v8;
  v12 = (const WCHAR *)*v8;
  *((_DWORD *)this + 14) = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v12, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids,
        LastError,
        v11);
    goto LABEL_19;
  }
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( (a2 & 4) != 0 )
  {
    if ( !GetSecurityDescriptorDacl(a3, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      v10 = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_19;
      v15 = 26;
LABEL_26:
      WPP_SF_d(v14[2], v15, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, (unsigned int)v10);
LABEL_19:
      if ( v10 <= 0 )
        goto LABEL_73;
      v10 = (unsigned __int16)v10;
      goto LABEL_72;
    }
    if ( !bDaclPresent || !pDacl )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) == 0 )
        goto LABEL_9;
      v9 = 27;
      goto LABEL_8;
    }
  }
  else if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v10 = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_19;
    v15 = 28;
    goto LABEL_26;
  }
  if ( (a2 & 8) != 0 )
  {
    if ( !GetSecurityDescriptorSacl(a3, &bDaclPresent, &pSacl, &bDaclDefaulted) )
    {
      v10 = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_19;
      v15 = 29;
      goto LABEL_26;
    }
    if ( !bDaclPresent || (v16 = pSacl) == 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) == 0 )
        goto LABEL_9;
      v9 = 30;
      goto LABEL_8;
    }
  }
  else
  {
    if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bDaclPresent, &pSacl, &bDaclDefaulted) )
    {
      v10 = GetLastError();
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
        goto LABEL_19;
      v15 = 31;
      goto LABEL_26;
    }
    v16 = pSacl;
  }
  if ( (a2 & 2) != 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) == 0 )
      goto LABEL_9;
    v9 = 32;
    goto LABEL_8;
  }
  if ( (a2 & 1) != 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) == 0 )
      goto LABEL_9;
    v9 = 33;
    goto LABEL_8;
  }
  if ( (unsigned int)CSecurity::AdjustSecurityDescriptorWithNewAcls(SecurityDescriptor, pDacl, v16, &v25) )
  {
    v7 = v25;
    v10 = 0;
    StringSecurityDescriptorLen = 0;
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
            v25,
            1u,
            0xFu,
            &StringSecurityDescriptor,
            &StringSecurityDescriptorLen) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, v19);
      }
      v20 = GetLastError();
      v10 = v20;
      if ( v20 > 0 )
      {
        v10 = (unsigned __int16)v20;
LABEL_72:
        v10 |= 0x80070000;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    {
      v17 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids, v17);
    }
    v18 = GetLastError();
    v10 = v18;
    if ( v18 > 0 )
      v10 = (unsigned __int16)v18 | 0x80070000;
    v7 = v25;
  }
LABEL_73:
  LocalFree(SecurityDescriptor);
  LocalFree(v7);
  if ( v10 < 0 )
    LocalFree(StringSecurityDescriptor);
  else
    AutoCleanup<AutoLocalFree,void *>::operator=(v8, StringSecurityDescriptor);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18012a480  push    rbp
0x18012a482  push    rbx
0x18012a483  push    rsi
0x18012a484  push    rdi
0x18012a485  push    r12
0x18012a487  push    r14
0x18012a489  push    r15
0x18012a48b  mov     rbp, rsp
0x18012a48e  sub     rsp, 60h
0x18012a492  mov     rsi, r8
0x18012a495  mov     edi, edx
0x18012a497  mov     rbx, rcx
0x18012a49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a4a1  lea     rax, WPP_GLOBAL_Control
0x18012a4a8  mov     edx, 1000000h
0x18012a4ad  cmp     rcx, rax
0x18012a4b0  jz      short loc_18012A4E6
0x18012a4b2  test    [rcx+1Ch], edx
0x18012a4b5  jz      short loc_18012A4E6
0x18012a4b7  mov     rcx, [rcx+10h]
0x18012a4bb  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a4c2  mov     edx, 16h
0x18012a4c7  mov     dword ptr [rsp+60h+StringSecurityDescriptorLen], edi
0x18012a4cb  mov     r9, rbx
0x18012a4ce  call    WPP_SF_qD
0x18012a4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a4da  lea     rax, WPP_GLOBAL_Control
0x18012a4e1  mov     edx, 1000000h
0x18012a4e6  xor     r15d, r15d
0x18012a4e9  mov     [rbp+SecurityDescriptor], 0
0x18012a4f1  mov     [rbp+var_18], r15
0x18012a4f5  lea     r12, [rbx+20h]
0x18012a4f9  mov     [rbp+StringSecurityDescriptor], r15
0x18012a4fd  mov     [rbp+pDacl], r15
0x18012a501  mov     [rbp+pSacl], r15
0x18012a505  test    rsi, rsi
0x18012a508  jnz     short loc_18012A534
0x18012a50a  cmp     rcx, rax
0x18012a50d  jz      short loc_18012A52A
0x18012a50f  test    [rcx+1Ch], edx
0x18012a512  jz      short loc_18012A52A
0x18012a514  lea     edx, [rsi+17h]
0x18012a517  mov     rcx, [rcx+10h]
0x18012a51b  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a522  mov     r9, rbx
0x18012a525  call    WPP_SF_q
0x18012a52a  mov     ebx, 80070057h
0x18012a52f  jmp     loc_18012A8F5
0x18012a534  cmp     [rbx+34h], r15d
0x18012a538  jnz     short loc_18012A566
0x18012a53a  cmp     rcx, rax
0x18012a53d  jz      short loc_18012A55C
0x18012a53f  test    [rcx+1Ch], edx
0x18012a542  jz      short loc_18012A55C
0x18012a544  mov     rcx, [rcx+10h]
0x18012a548  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a54f  mov     edx, 18h
0x18012a554  mov     r9, rbx
0x18012a557  call    WPP_SF_q
0x18012a55c  mov     ebx, 80004005h
0x18012a561  jmp     loc_18012A8F5
0x18012a566  mov     r14, [r12]
0x18012a56a  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18012a56e  mov     eax, 1
0x18012a573  mov     rcx, r14; StringSecurityDescriptor
0x18012a576  mov     edx, eax; StringSDRevision
0x18012a578  mov     [rbx+38h], eax
0x18012a57b  xor     r9d, r9d; SecurityDescriptorSize
0x18012a57e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18012a584  test    eax, eax
0x18012a586  jnz     short loc_18012A5D9
0x18012a588  call    cs:__imp_GetLastError
0x18012a58e  mov     ebx, eax
0x18012a590  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a597  lea     rdx, WPP_GLOBAL_Control
0x18012a59e  cmp     rcx, rdx
0x18012a5a1  jz      short loc_18012A5C9
0x18012a5a3  test    dword ptr [rcx+1Ch], 400000h
0x18012a5aa  jz      short loc_18012A5C9
0x18012a5ac  mov     rcx, [rcx+10h]
0x18012a5b0  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a5b7  mov     edx, 19h
0x18012a5bc  mov     [rsp+60h+StringSecurityDescriptorLen], r14
0x18012a5c1  mov     r9d, eax
0x18012a5c4  call    WPP_SF_dS
0x18012a5c9  test    ebx, ebx
0x18012a5cb  jle     loc_18012A8F5
0x18012a5d1  movzx   ebx, bx
0x18012a5d4  jmp     loc_18012A8EF
0x18012a5d9  mov     [rbp+bDaclPresent], r15d
0x18012a5dd  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18012a5e1  mov     [rbp+bDaclDefaulted], r15d
0x18012a5e5  lea     r8, [rbp+pDacl]; pDacl
0x18012a5e9  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18012a5ed  test    dil, 4
0x18012a5f1  jz      loc_18012A67C
0x18012a5f7  mov     rcx, rsi; pSecurityDescriptor
0x18012a5fa  call    cs:__imp_GetSecurityDescriptorDacl
0x18012a600  test    eax, eax
0x18012a602  jnz     short loc_18012A642
0x18012a604  call    cs:__imp_GetLastError
0x18012a60a  mov     ebx, eax
0x18012a60c  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a613  lea     rdx, WPP_GLOBAL_Control
0x18012a61a  cmp     rcx, rdx
0x18012a61d  jz      short loc_18012A5C9
0x18012a61f  test    dword ptr [rcx+1Ch], 400000h
0x18012a626  jz      short loc_18012A5C9
0x18012a628  mov     edx, 1Ah
0x18012a62d  mov     rcx, [rcx+10h]
0x18012a631  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a638  mov     r9d, ebx
0x18012a63b  call    WPP_SF_d
0x18012a640  jmp     short loc_18012A5C9
0x18012a642  cmp     [rbp+bDaclPresent], r15d
0x18012a646  jz      short loc_18012A64E
0x18012a648  cmp     [rbp+pDacl], r15
0x18012a64c  jnz     short loc_18012A6C0
0x18012a64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a655  lea     rdx, WPP_GLOBAL_Control
0x18012a65c  cmp     rcx, rdx
0x18012a65f  jz      loc_18012A52A
0x18012a665  test    dword ptr [rcx+1Ch], 1000000h
0x18012a66c  jz      loc_18012A52A
0x18012a672  mov     edx, 1Bh
0x18012a677  jmp     loc_18012A517
0x18012a67c  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18012a680  call    cs:__imp_GetSecurityDescriptorDacl
0x18012a686  test    eax, eax
0x18012a688  jnz     short loc_18012A6C0
0x18012a68a  call    cs:__imp_GetLastError
0x18012a690  mov     ebx, eax
0x18012a692  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a699  lea     rdx, WPP_GLOBAL_Control
0x18012a6a0  cmp     rcx, rdx
0x18012a6a3  jz      loc_18012A5C9
0x18012a6a9  test    dword ptr [rcx+1Ch], 400000h
0x18012a6b0  jz      loc_18012A5C9
0x18012a6b6  mov     edx, 1Ch
0x18012a6bb  jmp     loc_18012A62D
0x18012a6c0  lea     r9, [rbp+bDaclDefaulted]; lpbSaclDefaulted
0x18012a6c4  lea     r8, [rbp+pSacl]; pSacl
0x18012a6c8  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x18012a6cc  test    dil, 8
0x18012a6d0  jz      loc_18012A756
0x18012a6d6  mov     rcx, rsi; pSecurityDescriptor
0x18012a6d9  call    cs:__imp_GetSecurityDescriptorSacl
0x18012a6df  test    eax, eax
0x18012a6e1  jnz     short loc_18012A719
0x18012a6e3  call    cs:__imp_GetLastError
0x18012a6e9  mov     ebx, eax
0x18012a6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a6f2  lea     rdx, WPP_GLOBAL_Control
0x18012a6f9  cmp     rcx, rdx
0x18012a6fc  jz      loc_18012A5C9
0x18012a702  test    dword ptr [rcx+1Ch], 400000h
0x18012a709  jz      loc_18012A5C9
0x18012a70f  mov     edx, 1Dh
0x18012a714  jmp     loc_18012A62D
0x18012a719  cmp     [rbp+bDaclPresent], r15d
0x18012a71d  jz      short loc_18012A728
0x18012a71f  mov     r8, [rbp+pSacl]
0x18012a723  test    r8, r8
0x18012a726  jnz     short loc_18012A79E
0x18012a728  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a72f  lea     rdx, WPP_GLOBAL_Control
0x18012a736  cmp     rcx, rdx
0x18012a739  jz      loc_18012A52A
0x18012a73f  test    dword ptr [rcx+1Ch], 1000000h
0x18012a746  jz      loc_18012A52A
0x18012a74c  mov     edx, 1Eh
0x18012a751  jmp     loc_18012A517
0x18012a756  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18012a75a  call    cs:__imp_GetSecurityDescriptorSacl
0x18012a760  test    eax, eax
0x18012a762  jnz     short loc_18012A79A
0x18012a764  call    cs:__imp_GetLastError
0x18012a76a  mov     ebx, eax
0x18012a76c  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a773  lea     rdx, WPP_GLOBAL_Control
0x18012a77a  cmp     rcx, rdx
0x18012a77d  jz      loc_18012A5C9
0x18012a783  test    dword ptr [rcx+1Ch], 400000h
0x18012a78a  jz      loc_18012A5C9
0x18012a790  mov     edx, 1Fh
0x18012a795  jmp     loc_18012A62D
0x18012a79a  mov     r8, [rbp+pSacl]; struct _ACL *
0x18012a79e  test    dil, 2
0x18012a7a2  jz      short loc_18012A7D2
0x18012a7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a7ab  lea     rdx, WPP_GLOBAL_Control
0x18012a7b2  cmp     rcx, rdx
0x18012a7b5  jz      loc_18012A52A
0x18012a7bb  test    dword ptr [rcx+1Ch], 1000000h
0x18012a7c2  jz      loc_18012A52A
0x18012a7c8  mov     edx, 20h ; ' '
0x18012a7cd  jmp     loc_18012A517
0x18012a7d2  test    dil, 1
0x18012a7d6  jz      short loc_18012A806
0x18012a7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a7df  lea     rdx, WPP_GLOBAL_Control
0x18012a7e6  cmp     rcx, rdx
0x18012a7e9  jz      loc_18012A52A
0x18012a7ef  test    dword ptr [rcx+1Ch], 1000000h
0x18012a7f6  jz      loc_18012A52A
0x18012a7fc  mov     edx, 21h ; '!'
0x18012a801  jmp     loc_18012A517
0x18012a806  mov     rdx, [rbp+pDacl]; struct _ACL *
0x18012a80a  lea     r9, [rbp+var_18]; void **
0x18012a80e  mov     rcx, [rbp+SecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18012a812  call    ?AdjustSecurityDescriptorWithNewAcls@CSecurity@@SAHPEAU_SECURITY_DESCRIPTOR@@PEAU_ACL@@1PEAPEAX@Z; CSecurity::AdjustSecurityDescriptorWithNewAcls(_SECURITY_DESCRIPTOR *,_ACL *,_ACL *,void * *)
0x18012a817  test    eax, eax
0x18012a819  jnz     short loc_18012A877
0x18012a81b  mov     rax, cs:WPP_GLOBAL_Control
0x18012a822  lea     rdx, WPP_GLOBAL_Control
0x18012a829  cmp     rax, rdx
0x18012a82c  jz      short loc_18012A85C
0x18012a82e  test    dword ptr [rax+1Ch], 1000000h
0x18012a835  jz      short loc_18012A85C
0x18012a837  call    cs:__imp_GetLastError
0x18012a83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a844  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a84b  mov     edx, 22h ; '"'
0x18012a850  mov     r9d, eax
0x18012a853  mov     rcx, [rcx+10h]
0x18012a857  call    WPP_SF_d
0x18012a85c  call    cs:__imp_GetLastError
0x18012a862  mov     ebx, eax
0x18012a864  test    eax, eax
0x18012a866  jle     short loc_18012A871
0x18012a868  movzx   ebx, ax
0x18012a86b  or      ebx, 80070000h
0x18012a871  mov     r15, [rbp+var_18]
0x18012a875  jmp     short loc_18012A8F5
0x18012a877  mov     r15, [rbp+var_18]
0x18012a87b  lea     rax, [rbp+arg_18]
0x18012a87f  xor     ebx, ebx
0x18012a881  mov     [rsp+60h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18012a886  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18012a88a  mov     [rbp+arg_18], ebx
0x18012a88d  mov     rcx, r15; SecurityDescriptor
0x18012a890  lea     edx, [rbx+1]; RequestedStringSDRevision
0x18012a893  lea     r8d, [rbx+0Fh]; SecurityInformation
0x18012a897  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18012a89d  test    eax, eax
0x18012a89f  jnz     short loc_18012A8F5
0x18012a8a1  mov     rax, cs:WPP_GLOBAL_Control
0x18012a8a8  lea     rdx, WPP_GLOBAL_Control
0x18012a8af  cmp     rax, rdx
0x18012a8b2  jz      short loc_18012A8E0
0x18012a8b4  test    dword ptr [rax+1Ch], 1000000h
0x18012a8bb  jz      short loc_18012A8E0
0x18012a8bd  call    cs:__imp_GetLastError
0x18012a8c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18012a8ca  lea     edx, [rbx+23h]
0x18012a8cd  mov     r9d, eax
0x18012a8d0  lea     r8, WPP_bab436ce77c83f5ec2fa421bcc00cd3b_Traceguids
0x18012a8d7  mov     rcx, [rcx+10h]
0x18012a8db  call    WPP_SF_d
0x18012a8e0  call    cs:__imp_GetLastError
0x18012a8e6  mov     ebx, eax
0x18012a8e8  test    eax, eax
0x18012a8ea  jle     short loc_18012A8F5
0x18012a8ec  movzx   ebx, ax
0x18012a8ef  or      ebx, 80070000h
0x18012a8f5  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18012a8f9  call    cs:__imp_LocalFree
0x18012a8ff  mov     rcx, r15; hMem
0x18012a902  call    cs:__imp_LocalFree
0x18012a908  test    ebx, ebx
0x18012a90a  js      short loc_18012A91A
0x18012a90c  mov     rdx, [rbp+StringSecurityDescriptor]
0x18012a910  mov     rcx, r12
0x18012a913  call    ??4?$AutoCleanup@VAutoLocalFree@@PEAX@@QEAAAEAVAutoLocalFree@@PEAX@Z; AutoCleanup<AutoLocalFree,void *>::operator=(void *)
0x18012a918  jmp     short loc_18012A924
0x18012a91a  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18012a91e  call    cs:__imp_LocalFree
0x18012a924  mov     eax, ebx
0x18012a926  add     rsp, 60h
0x18012a92a  pop     r15
0x18012a92c  pop     r14
0x18012a92e  pop     r12
0x18012a930  pop     rdi
0x18012a931  pop     rsi
0x18012a932  pop     rbx
0x18012a933  pop     rbp
0x18012a934  retn
```

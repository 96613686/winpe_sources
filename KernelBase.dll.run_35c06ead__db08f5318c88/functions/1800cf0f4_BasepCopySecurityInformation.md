# BasepCopySecurityInformation

- ea: `0x1800cf0f4`
- end: `0x1800cf75e`
- name: `BasepCopySecurityInformation`
- size: `1642`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE, int, SECURITY_INFORMATION SecurityInfo, __int64, char, __int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cd450`
- `0x1800d061c`

## callees

- `0x1800134a0`
- `0x1800220f0`
- `0x1800cf0f4`
- `0x1800cf764`
- `0x1800cf810`
- `0x18012e7a0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800cf567`
- `ntdll!RtlSetLastWin32Error` at `0x1800cf567`
- `ntdll!RtlGetLastNtStatus` at `0x1800cf553`
- `ntdll!RtlGetLastNtStatus` at `0x1800cf553`
- `ntdll!RtlpMergeSecurityAttributeInformation` at `0x1800cf59b`
- `ntdll!RtlpMergeSecurityAttributeInformation` at `0x1800cf59b`
- `ntdll!RtlFindAceByType` at `0x1800cf2aa`
- `ntdll!RtlFindAceByType` at `0x1800cf2aa`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800cf53c`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1800cf53c`
- `ntdll!RtlFreeHeap` at `0x1800cf430`
- `ntdll!RtlFreeHeap` at `0x1800cf430`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf27f`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf2f0`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf37a`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf27f`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf2f0`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800cf37a`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1800cf3db`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!SetSecurityInfo` at `0x1800cf3db`

## pseudocode

```c
__int64 __fastcall BasepCopySecurityInformation(
        __int64 a1,
        void *a2,
        int a3,
        __int64 a4,
        HANDLE a5,
        int a6,
        SECURITY_INFORMATION SecurityInfo,
        __int64 a8,
        char a9,
        _DWORD *a10,
        int a11)
{
  HANDLE v12; // r14
  BOOL v13; // esi
  SECURITY_INFORMATION v14; // edi
  SECURITY_INFORMATION v15; // r15d
  __int64 v16; // rbx
  int v17; // r13d
  unsigned int v18; // r14d
  HANDLE v19; // r13
  __int64 v20; // r9
  ULONG v21; // r14d
  bool v22; // r14
  __int64 AceByType; // rax
  HANDLE v24; // r15
  PSID v25; // r8
  DWORD v26; // eax
  NTSTATUS ControlSecurityDescriptor; // eax
  PACL v29; // rdx
  PACL v30; // rcx
  __int64 v31; // rdx
  PACL pSacl; // [rsp+48h] [rbp-59h] BYREF
  PVOID P; // [rsp+50h] [rbp-51h] BYREF
  PACL pDacl; // [rsp+58h] [rbp-49h] BYREF
  ULONG Revision; // [rsp+60h] [rbp-41h] BYREF
  PSID v36; // [rsp+68h] [rbp-39h] BYREF
  PACL ppSacl; // [rsp+70h] [rbp-31h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+80h] [rbp-21h] BYREF
  PSID psidGroup; // [rsp+88h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+90h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR v42; // [rsp+98h] [rbp-9h] BYREF
  WORD Control; // [rsp+E8h] [rbp+47h] BYREF
  HANDLE handle; // [rsp+F0h] [rbp+4Fh]
  int v45; // [rsp+F8h] [rbp+57h]

  v45 = a3;
  handle = a2;
  v12 = a2;
  pDacl = 0;
  pSacl = 0;
  *a10 = 0;
  ppSacl = 0;
  P = 0;
  ppsidOwner = 0;
  psidGroup = 0;
  v36 = 0;
  ppSecurityDescriptor = 0;
  v42 = 0;
  hMem = 0;
  Control = 0;
  Revision = 0;
  if ( !a1 || !a4 || !(unsigned __int8)IsSetSecurityInfoPresent() )
  {
    v18 = 1;
    goto LABEL_40;
  }
  v13 = 1;
  if ( (a9 & 8) == 0 )
  {
    if ( (SecurityInfo & 0xFFFFFFDF) != 0 )
    {
      v31 = a8;
      if ( a8 )
      {
        *(_QWORD *)(a8 + 40) = a5;
        *(_DWORD *)(v31 + 20) = 1;
        *(_DWORD *)(v31 + 24) = 50;
        *(_QWORD *)(v31 + 64) = 0;
        *(_QWORD *)(v31 + 32) = v12;
      }
      v13 = BasepCopyFileCallback(20) != 0;
    }
    goto LABEL_39;
  }
  v14 = SecurityInfo;
  v15 = SecurityInfo;
  v16 = a8;
  v17 = a6;
  if ( (SecurityInfo & 4) != 0 && ((a3 & 0x80020000) == 0 || (a6 & 0x40000) == 0) )
  {
    v14 = SecurityInfo & 0xFFFFFFFB;
    if ( a8 )
    {
      *(_QWORD *)(a8 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v12;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(16) )
      goto LABEL_40;
    v12 = handle;
  }
  if ( (v15 & 3) != 0 && ((a3 & 0x80020000) == 0 || (v17 & 0x80000) == 0) )
  {
    v14 &= 0xFFFFFFFC;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v12;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(17) )
      goto LABEL_40;
  }
  if ( (v15 & 8) != 0 && (v17 & a3 & 0x1000000) == 0 )
  {
    v14 &= ~8u;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 32) = handle;
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 1314;
      *(_QWORD *)(v16 + 64) = 0;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(19) )
      goto LABEL_40;
  }
  if ( (v15 & 0x20) != 0 && ((v45 & 0x80020000) == 0 || v17 >= 0 || (v17 & 0x40000) == 0) )
    v14 &= ~0x20u;
  if ( (v15 & 0x10) != 0 && ((v45 & 0x80020000) == 0 || (v17 & 0x80000) == 0) )
  {
    v14 &= ~0x10u;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 32) = handle;
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 5;
      *(_QWORD *)(v16 + 64) = 0;
    }
    v18 = 0;
    if ( !(unsigned int)BasepCopyFileCallback(19) )
      goto LABEL_40;
  }
  if ( !v14 )
    goto LABEL_39;
  if ( a11 )
    v15 = v14 | 1;
  v19 = handle;
  v21 = GetSecurityInfo(handle, SE_FILE_OBJECT, v15, &ppsidOwner, &psidGroup, &pDacl, &pSacl, &ppSecurityDescriptor);
  if ( !v21 )
  {
    v22 = 0;
    if ( (v14 & 0x20) != 0 && ((AceByType = RtlFindAceByType(pSacl, 18, 0), v22 = AceByType != 0, a11) || AceByType) )
    {
      v24 = a5;
      if ( GetSecurityInfo(a5, SE_FILE_OBJECT, 0x20u, 0, 0, 0, &ppSacl, &v42) )
        v14 &= ~0x20u;
    }
    else
    {
      v24 = a5;
    }
    if ( !pDacl )
      v14 &= ~4u;
    if ( !pSacl )
      v14 &= 0xFFFFFFC7;
    if ( (v14 & 0xC) != 0 )
    {
      ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(ppSecurityDescriptor, &Control, &Revision);
      if ( ControlSecurityDescriptor < 0 )
      {
        BaseSetLastNTError((unsigned int)ControlSecurityDescriptor);
        goto LABEL_70;
      }
    }
    if ( (v14 & 4) != 0 )
    {
      v14 |= (Control & 0x1000) != 0 ? 0x80000000 : 0x20000000;
      if ( a11 )
      {
        if ( GetSecurityInfo(v24, SE_FILE_OBJECT, 1u, &v36, 0, 0, 0, &hMem) )
        {
          v25 = 0;
          v36 = 0;
        }
        else
        {
          v25 = v36;
        }
        BasepCopyCreatorOwnerACE(pDacl, ppsidOwner, v25);
      }
    }
    if ( (v14 & 8) != 0 )
    {
      if ( (Control & 0x2000) != 0 )
        v14 |= 0x40000000u;
      else
        v14 |= 0x10000000u;
    }
    if ( (v14 & 0x20) == 0 )
    {
LABEL_37:
      while ( v14 )
      {
        v26 = SetSecurityInfo(v24, SE_FILE_OBJECT, v14, ppsidOwner, psidGroup, pDacl, pSacl);
        if ( !v26 )
          break;
        if ( (v14 & 3) != 0 )
        {
          if ( v16 )
          {
            *(_DWORD *)(v16 + 20) = 1;
            *(_DWORD *)(v16 + 24) = v26;
            *(_QWORD *)(v16 + 64) = 0;
            *(_QWORD *)(v16 + 32) = v19;
            *(_QWORD *)(v16 + 40) = v24;
          }
          if ( !(unsigned int)BasepCopyFileCallback(18) )
            goto LABEL_71;
          v14 &= 0xFFFFFFFC;
        }
        else
        {
          if ( v16 )
          {
            *(_DWORD *)(v16 + 20) = 1;
            *(_DWORD *)(v16 + 24) = v26;
            *(_QWORD *)(v16 + 64) = 0;
            *(_QWORD *)(v16 + 32) = v19;
            *(_QWORD *)(v16 + 40) = v24;
          }
          if ( !(unsigned int)BasepCopyFileCallback(16) )
            goto LABEL_71;
          v14 = 0;
        }
      }
      goto LABEL_39;
    }
    if ( a11 )
    {
      v29 = pSacl;
      LOBYTE(v20) = 1;
      v30 = ppSacl;
    }
    else
    {
      if ( !v22 )
      {
LABEL_76:
        if ( P )
          pSacl = (PACL)P;
        goto LABEL_37;
      }
      v29 = ppSacl;
      v20 = 0;
      v30 = pSacl;
    }
    if ( (int)RtlpMergeSecurityAttributeInformation(v30, v29, &P, v20) < 0 )
      goto LABEL_37;
    goto LABEL_76;
  }
  if ( RtlGetLastNtStatus() == -1073741637 )
  {
    if ( v16 )
    {
      *(_QWORD *)(v16 + 40) = a5;
      *(_DWORD *)(v16 + 20) = 1;
      *(_DWORD *)(v16 + 24) = 50;
      *(_QWORD *)(v16 + 64) = 0;
      *(_QWORD *)(v16 + 32) = v19;
    }
    if ( (unsigned int)BasepCopyFileCallback(20) )
    {
LABEL_39:
      v18 = v13;
      goto LABEL_40;
    }
  }
  RtlSetLastWin32Error(v21);
LABEL_70:
  *a10 = 1;
LABEL_71:
  v18 = 0;
LABEL_40:
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  if ( v42 )
    LocalFree(v42);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return v18;
}

```

## disassembly

```asm
0x1800cf0f4  mov     rax, rsp
0x1800cf0f7  mov     [rax+20h], rbx
0x1800cf0fb  mov     [rax+18h], r8d
0x1800cf0ff  mov     [rax+10h], rdx
0x1800cf103  push    rbp
0x1800cf104  push    rsi
0x1800cf105  push    rdi
0x1800cf106  push    r12
0x1800cf108  push    r13
0x1800cf10a  push    r14
0x1800cf10c  push    r15
0x1800cf10e  lea     rbp, [rax-3Fh]
0x1800cf112  sub     rsp, 0A0h
0x1800cf119  mov     rax, [rbp+37h+arg_48]
0x1800cf120  mov     r12d, r8d
0x1800cf123  xor     r8d, r8d
0x1800cf126  mov     r14, rdx
0x1800cf129  mov     [rbp+37h+pDacl], r8
0x1800cf12d  mov     [rbp+37h+pSacl], r8
0x1800cf131  mov     [rax], r8d
0x1800cf134  mov     [rbp+37h+var_68], r8
0x1800cf138  mov     [rbp+37h+P], r8
0x1800cf13c  mov     [rbp+37h+ppsidOwner], r8
0x1800cf140  mov     [rbp+37h+psidGroup], r8
0x1800cf144  mov     [rbp+37h+var_70], r8
0x1800cf148  mov     [rbp+37h+ppSecurityDescriptor], r8
0x1800cf14c  mov     [rbp+37h+var_40], r8
0x1800cf150  mov     [rbp+37h+hMem], r8
0x1800cf154  mov     [rbp+37h+Control], r8w
0x1800cf159  mov     [rbp+37h+Revision], r8d
0x1800cf15d  test    rcx, rcx
0x1800cf160  jz      loc_1800CF1E7
0x1800cf166  test    r9, r9
0x1800cf169  jz      short loc_1800CF1E7
0x1800cf16b  call    IsSetSecurityInfoPresent
0x1800cf170  xor     r8d, r8d
0x1800cf173  test    al, al
0x1800cf175  jz      short loc_1800CF1E7
0x1800cf177  test    [rbp+37h+arg_40], 8
0x1800cf17e  lea     esi, [r8+1]
0x1800cf182  jz      loc_1800CF608
0x1800cf188  mov     edi, [rbp+37h+SecurityInfo]
0x1800cf18b  mov     r15d, edi
0x1800cf18e  mov     rbx, [rbp+37h+arg_38]
0x1800cf192  mov     r13d, [rbp+37h+arg_28]
0x1800cf196  test    dil, 4
0x1800cf19a  jnz     loc_1800CF4E6
0x1800cf1a0  test    r15b, 3
0x1800cf1a4  jz      short loc_1800CF1F2
0x1800cf1a6  test    r12d, 80020000h
0x1800cf1ad  setnz   cl
0x1800cf1b0  bt      r13d, 13h
0x1800cf1b5  setb    al
0x1800cf1b8  test    al, cl
0x1800cf1ba  jnz     short loc_1800CF1F2
0x1800cf1bc  and     edi, 0FFFFFFFCh
0x1800cf1bf  test    rbx, rbx
0x1800cf1c2  jz      loc_180193CE7
0x1800cf1c8  mov     rax, [rbp+37h+arg_20]
0x1800cf1cc  mov     [rbx+28h], rax
0x1800cf1d0  mov     [rbx+14h], esi
0x1800cf1d3  mov     dword ptr [rbx+18h], 5
0x1800cf1da  mov     [rbx+40h], r8
0x1800cf1de  mov     [rbx+20h], r14
0x1800cf1e2  jmp     loc_180193CE7
0x1800cf1e7  mov     r14d, 1
0x1800cf1ed  jmp     loc_1800CF3EC
0x1800cf1f2  test    r15b, 8
0x1800cf1f6  jnz     loc_1800CF498
0x1800cf1fc  mov     eax, [rbp+37h+arg_10]
0x1800cf1ff  mov     r12d, 0FFFFFFDFh
0x1800cf205  test    r15b, 20h
0x1800cf209  jz      short loc_1800CF22A
0x1800cf20b  test    eax, 80020000h
0x1800cf210  jz      loc_1800CF5F7
0x1800cf216  test    r13d, r13d
0x1800cf219  jns     loc_1800CF5F7
0x1800cf21f  bt      r13d, 12h
0x1800cf224  jnb     loc_1800CF5F7
0x1800cf22a  test    r15b, 10h
0x1800cf22e  jnz     loc_1800CF454
0x1800cf234  test    edi, edi
0x1800cf236  jz      loc_1800CF3E9
0x1800cf23c  cmp     [rbp+37h+arg_50], r8d
0x1800cf243  jz      short loc_1800CF24B
0x1800cf245  mov     r15d, edi
0x1800cf248  or      r15d, esi
0x1800cf24b  mov     r13, [rbp+37h+handle]
0x1800cf24f  lea     rax, [rbp+37h+ppSecurityDescriptor]
0x1800cf253  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800cf258  lea     r9, [rbp+37h+ppsidOwner]; ppsidOwner
0x1800cf25c  lea     rax, [rbp+37h+pSacl]
0x1800cf260  mov     r8d, r15d; SecurityInfo
0x1800cf263  mov     [rsp+0D0h+ppSacl], rax; ppSacl
0x1800cf268  mov     edx, esi; ObjectType
0x1800cf26a  lea     rax, [rbp+37h+pDacl]
0x1800cf26e  mov     rcx, r13; handle
0x1800cf271  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x1800cf276  lea     rax, [rbp+37h+psidGroup]
0x1800cf27a  mov     [rsp+0D0h+ppsidGroup], rax; ppsidGroup
0x1800cf27f  call    cs:__imp_GetSecurityInfo
0x1800cf285  xor     r15d, r15d
0x1800cf288  mov     r14d, eax
0x1800cf28b  test    eax, eax
0x1800cf28d  jnz     loc_1800CF553
0x1800cf293  mov     r14b, r15b
0x1800cf296  test    dil, 20h
0x1800cf29a  jz      loc_1800CF4DD
0x1800cf2a0  mov     rcx, [rbp+37h+pSacl]
0x1800cf2a4  lea     edx, [rax+12h]
0x1800cf2a7  xor     r8d, r8d
0x1800cf2aa  call    cs:__imp_RtlFindAceByType
0x1800cf2b0  test    rax, rax
0x1800cf2b3  setnz   r14b
0x1800cf2b7  cmp     [rbp+37h+arg_50], r15d
0x1800cf2be  jz      loc_1800CF4D4
0x1800cf2c4  lea     rax, [rbp+37h+var_40]
0x1800cf2c8  xor     r9d, r9d; ppsidOwner
0x1800cf2cb  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800cf2d0  mov     edx, esi; ObjectType
0x1800cf2d2  lea     rax, [rbp+37h+var_68]
0x1800cf2d6  mov     [rsp+0D0h+ppSacl], rax; ppSacl
0x1800cf2db  mov     [rsp+0D0h+ppDacl], r15; ppDacl
0x1800cf2e0  lea     r8d, [r9+20h]; SecurityInfo
0x1800cf2e4  mov     [rsp+0D0h+ppsidGroup], r15; ppsidGroup
0x1800cf2e9  mov     r15, [rbp+37h+arg_20]
0x1800cf2ed  mov     rcx, r15; handle
0x1800cf2f0  call    cs:__imp_GetSecurityInfo
0x1800cf2f6  test    eax, eax
0x1800cf2f8  jnz     loc_1800CF708
0x1800cf2fe  cmp     [rbp+37h+pDacl], 0
0x1800cf303  jnz     short loc_1800CF308
0x1800cf305  and     edi, 0FFFFFFFBh
0x1800cf308  cmp     [rbp+37h+pSacl], 0
0x1800cf30d  jnz     short loc_1800CF312
0x1800cf30f  and     edi, 0FFFFFFC7h
0x1800cf312  test    dil, 0Ch
0x1800cf316  jnz     loc_1800CF530
0x1800cf31c  test    dil, 4
0x1800cf320  jz      short loc_1800CF39C
0x1800cf322  movzx   eax, [rbp+37h+Control]
0x1800cf326  mov     ecx, 1000h
0x1800cf32b  and     ax, cx
0x1800cf32e  neg     ax
0x1800cf331  sbb     ecx, ecx
0x1800cf333  and     ecx, 60000000h
0x1800cf339  add     ecx, 20000000h
0x1800cf33f  or      edi, ecx
0x1800cf341  cmp     [rbp+37h+arg_50], 0
0x1800cf348  jz      short loc_1800CF39C
0x1800cf34a  lea     rax, [rbp+37h+hMem]
0x1800cf34e  mov     r8d, esi; SecurityInfo
0x1800cf351  mov     [rsp+38h], rax; ppSecurityDescriptor
0x1800cf356  lea     r9, [rbp+37h+var_70]; ppsidOwner
0x1800cf35a  mov     [rsp+0D0h+ppSacl], 0; ppSacl
0x1800cf363  mov     edx, esi; ObjectType
0x1800cf365  mov     [rsp+0D0h+ppDacl], 0; ppDacl
0x1800cf36e  mov     rcx, r15; handle
0x1800cf371  mov     [rsp+0D0h+ppsidGroup], 0; ppsidGroup
0x1800cf37a  call    cs:__imp_GetSecurityInfo
0x1800cf380  test    eax, eax
0x1800cf382  jz      loc_1800CF5FF
0x1800cf388  xor     r8d, r8d; PSID
0x1800cf38b  mov     [rbp+37h+var_70], r8
0x1800cf38f  mov     rdx, [rbp+37h+ppsidOwner]; Sid1
0x1800cf393  mov     rcx, [rbp+37h+pDacl]; Acl
0x1800cf397  call    BasepCopyCreatorOwnerACE
0x1800cf39c  test    dil, 8
0x1800cf3a0  jnz     loc_1800CF710
0x1800cf3a6  test    dil, 20h
0x1800cf3aa  jnz     loc_1800CF57E
0x1800cf3b0  test    edi, edi
0x1800cf3b2  jz      short loc_1800CF3E9
0x1800cf3b4  mov     rax, [rbp+37h+pSacl]
0x1800cf3b8  mov     r8d, edi; SecurityInfo
0x1800cf3bb  mov     r9, [rbp+37h+ppsidOwner]; psidOwner
0x1800cf3bf  mov     edx, esi; ObjectType
0x1800cf3c1  mov     [rsp+0D0h+ppSacl], rax; pSacl
0x1800cf3c6  mov     rcx, r15; handle
0x1800cf3c9  mov     rax, [rbp+37h+pDacl]
0x1800cf3cd  mov     [rsp+0D0h+ppDacl], rax; pDacl
0x1800cf3d2  mov     rax, [rbp+37h+psidGroup]
0x1800cf3d6  mov     [rsp+0D0h+ppsidGroup], rax; psidGroup
0x1800cf3db  call    cs:__imp_SetSecurityInfo
0x1800cf3e1  test    eax, eax
0x1800cf3e3  jnz     loc_1800CF5CC
0x1800cf3e9  mov     r14d, esi
0x1800cf3ec  mov     rcx, [rbp+37h+ppSecurityDescriptor]; hMem
0x1800cf3f0  test    rcx, rcx
0x1800cf3f3  jz      short loc_1800CF3FA
0x1800cf3f5  call    LocalFree
0x1800cf3fa  mov     rcx, [rbp+37h+hMem]; hMem
0x1800cf3fe  test    rcx, rcx
0x1800cf401  jz      short loc_1800CF408
0x1800cf403  call    LocalFree
0x1800cf408  mov     rcx, [rbp+37h+var_40]; hMem
0x1800cf40c  test    rcx, rcx
0x1800cf40f  jz      short loc_1800CF416
0x1800cf411  call    LocalFree
0x1800cf416  cmp     [rbp+37h+P], 0
0x1800cf41b  jz      short loc_1800CF436
0x1800cf41d  mov     rcx, gs:60h
0x1800cf426  xor     edx, edx; Flags
0x1800cf428  mov     r8, [rbp+37h+P]; P
0x1800cf42c  mov     rcx, [rcx+30h]; HeapHandle
0x1800cf430  call    cs:__imp_RtlFreeHeap
0x1800cf436  mov     rbx, [rsp+0D0h+arg_18]
0x1800cf43e  mov     eax, r14d
0x1800cf441  add     rsp, 0A0h
0x1800cf448  pop     r15
0x1800cf44a  pop     r14
0x1800cf44c  pop     r13
0x1800cf44e  pop     r12
0x1800cf450  pop     rdi
0x1800cf451  pop     rsi
0x1800cf452  pop     rbp
0x1800cf453  retn
0x1800cf454  test    eax, 80020000h
0x1800cf459  setnz   cl
0x1800cf45c  bt      r13d, 13h
0x1800cf461  setb    al
0x1800cf464  test    al, cl
0x1800cf466  jnz     loc_1800CF234
0x1800cf46c  and     edi, 0FFFFFFEFh
0x1800cf46f  test    rbx, rbx
0x1800cf472  jnz     loc_1800CF6E5
0x1800cf478  mov     rdx, rbx
0x1800cf47b  mov     ecx, 13h
0x1800cf480  mov     r14d, r8d
0x1800cf483  call    BasepCopyFileCallback
0x1800cf488  xor     r8d, r8d
0x1800cf48b  test    eax, eax
0x1800cf48d  jz      loc_1800CF3EC
0x1800cf493  jmp     loc_1800CF234
0x1800cf498  mov     eax, r12d
0x1800cf49b  and     eax, r13d
0x1800cf49e  bt      eax, 18h
0x1800cf4a2  jb      loc_1800CF1FC
0x1800cf4a8  and     edi, 0FFFFFFF7h
0x1800cf4ab  test    rbx, rbx
0x1800cf4ae  jnz     loc_1800CF6C2
0x1800cf4b4  mov     rdx, rbx
0x1800cf4b7  mov     ecx, 13h
0x1800cf4bc  mov     r14d, r8d
0x1800cf4bf  call    BasepCopyFileCallback
0x1800cf4c4  xor     r8d, r8d
0x1800cf4c7  test    eax, eax
0x1800cf4c9  jnz     loc_1800CF1FC
0x1800cf4cf  jmp     loc_1800CF3EC
0x1800cf4d4  test    rax, rax
0x1800cf4d7  jnz     loc_1800CF2C4
0x1800cf4dd  mov     r15, [rbp+37h+arg_20]
0x1800cf4e1  jmp     loc_1800CF2FE
0x1800cf4e6  test    r12d, 80020000h
0x1800cf4ed  setnz   cl
0x1800cf4f0  bt      r13d, 12h
0x1800cf4f5  setb    al
0x1800cf4f8  test    al, cl
0x1800cf4fa  jnz     loc_1800CF1A0
0x1800cf500  and     edi, 0FFFFFFFBh
0x1800cf503  test    rbx, rbx
0x1800cf506  jnz     loc_1800CF6A3
0x1800cf50c  mov     rdx, rbx
0x1800cf50f  mov     ecx, 10h
0x1800cf514  mov     r14d, r8d
0x1800cf517  call    BasepCopyFileCallback
0x1800cf51c  xor     r8d, r8d
0x1800cf51f  test    eax, eax
0x1800cf521  jz      loc_1800CF3EC
0x1800cf527  mov     r14, [rbp+37h+handle]
0x1800cf52b  jmp     loc_1800CF1A0
0x1800cf530  mov     rcx, [rbp+37h+ppSecurityDescriptor]; SecurityDescriptor
0x1800cf534  lea     r8, [rbp+37h+Revision]; Revision
0x1800cf538  lea     rdx, [rbp+37h+Control]; Control
0x1800cf53c  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1800cf542  test    eax, eax
0x1800cf544  jns     loc_1800CF31C
0x1800cf54a  mov     ecx, eax
0x1800cf54c  call    BaseSetLastNTError
0x1800cf551  jmp     short loc_1800CF56D
0x1800cf553  call    cs:__imp_RtlGetLastNtStatus
0x1800cf559  cmp     eax, 0C00000BBh
0x1800cf55e  jz      loc_1800CF644
0x1800cf564  mov     ecx, r14d; LastError
0x1800cf567  call    cs:__imp_RtlSetLastWin32Error
0x1800cf56d  mov     rax, [rbp+37h+arg_48]
0x1800cf574  mov     [rax], esi
0x1800cf576  xor     r14d, r14d
0x1800cf579  jmp     loc_1800CF3EC
0x1800cf57e  cmp     [rbp+37h+arg_50], 0
0x1800cf585  jnz     short loc_1800CF5BF
0x1800cf587  test    r14b, r14b
0x1800cf58a  jz      short loc_1800CF5A9
0x1800cf58c  mov     rdx, [rbp+37h+var_68]
0x1800cf590  xor     r9d, r9d
0x1800cf593  mov     rcx, [rbp+37h+pSacl]
0x1800cf597  lea     r8, [rbp+37h+P]
0x1800cf59b  call    cs:__imp_RtlpMergeSecurityAttributeInformation
0x1800cf5a1  test    eax, eax
0x1800cf5a3  js      loc_1800CF3B0
  ... truncated ...
```

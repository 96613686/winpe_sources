# FwPolicy2::get_LocalPolicyModifyState(NET_FW_MODIFY_STATE_ *)

- ea: `0x18000b390`
- end: `0x18000b8b2`
- name: `?get_LocalPolicyModifyState@FwPolicy2@@UEAAJPEAW4NET_FW_MODIFY_STATE_@@@Z`
- size: `1314`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_MODIFY_STATE_ *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x180008a10`
- `0x180008b30`
- `0x18000b390`
- `0x18000c130`
- `0x18000c560`
- `0x18000d850`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000b67e`
- `ntdll!EtwEventWrite` at `0x18000b701`
- `ntdll!EtwEventWrite` at `0x18000b67e`
- `ntdll!EtwEventWrite` at `0x18000b701`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b6a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b6a1`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000b46b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000b61a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000b46b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18000b61a`
- `fwbase!FwReportErrorAsWinError` at `0x18000b541`
- `fwbase!FwReportErrorAsWinError` at `0x18000b7ba`
- `fwbase!FwReportErrorAsWinError` at `0x18000b834`
- `fwbase!FwReportErrorAsWinError` at `0x18000b8a5`
- `fwbase!FwReportErrorAsWinError` at `0x18000b541`
- `fwbase!FwReportErrorAsWinError` at `0x18000b7ba`
- `fwbase!FwReportErrorAsWinError` at `0x18000b834`
- `fwbase!FwReportErrorAsWinError` at `0x18000b8a5`
- `fwbase!FwReportReturnError` at `0x18000b7d0`
- `fwbase!FwReportReturnError` at `0x18000b7d0`

## string_xrefs

- `0x18000b7ac`: `FWOpenPolicyStore`
- `0x18000b533`: `FWGetGlobalConfig`
- `0x18000b826`: `FWGetConfig`
- `0x18000b897`: `FWGetConfig`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_LocalPolicyModifyState(FwPolicy2 *this, enum NET_FW_MODIFY_STATE_ *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int i; // ebx
  int ProfileTypeFromProfileIndex; // eax
  int v10; // edi
  unsigned int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r13d
  enum NET_FW_MODIFY_STATE_ v17; // r14d
  unsigned int j; // edi
  int v20; // r15d
  int v21; // r12d
  unsigned int v22; // r15d
  int v23; // [rsp+48h] [rbp-9h]
  __int64 v24; // [rsp+58h] [rbp+7h] BYREF
  int v25; // [rsp+60h] [rbp+Fh] BYREF
  int v26; // [rsp+64h] [rbp+13h] BYREF
  int v27; // [rsp+68h] [rbp+17h] BYREF
  int v28; // [rsp+6Ch] [rbp+1Bh] BYREF
  __int64 v29; // [rsp+70h] [rbp+1Fh]
  int v30; // [rsp+78h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v26 = 4;
  v24 = 0;
  v29 = 0;
  v30 = 0;
  v28 = 0;
  v3 = FWGetGlobalConfig(545, 0, 5, 2, 0, (__int64)&v28, (__int64)&v26);
  if ( v3 )
  {
    v13 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWGetGlobalConfig", v3);
    goto LABEL_23;
  }
  v4 = FWOpenPolicyStore(0x221u, 0, 1u, 1u, 0, &v24);
  if ( v4 == 2 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  }
  else
  {
    if ( v4 )
    {
LABEL_49:
      v13 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWOpenPolicyStore", v4);
      goto LABEL_23;
    }
    for ( i = 0; i < 3; ++i )
    {
      ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(i);
      v10 = ProfileTypeFromProfileIndex;
      if ( (ProfileTypeFromProfileIndex & v28) != 0 )
      {
        v25 = 0;
        v26 = 4;
        v27 = 0;
        v11 = FWGetConfig2(v24, 3, ProfileTypeFromProfileIndex, 0, (__int64)&v25, (__int64)&v26, (__int64)&v27);
        if ( v11 == 2 )
        {
          v25 = 0;
        }
        else
        {
          if ( v11 )
            goto LABEL_55;
          if ( v25 )
            *((_DWORD *)&v29 + i) = 1;
        }
        v27 = 0;
        v11 = FWGetConfig2(v24, 13, v10, 0, (__int64)&v25, (__int64)&v26, (__int64)&v27);
        if ( v11 == 2 )
        {
          v25 = 1;
        }
        else
        {
          if ( v11 )
          {
LABEL_55:
            v13 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWGetConfig", v11);
            goto LABEL_23;
          }
          if ( !v25 )
            *((_DWORD *)&v29 + i) = 1;
        }
      }
    }
    FWClosePolicyStore(v24, v5, v6, v7);
    v24 = 0;
  }
  v4 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v24);
  if ( v4 )
    goto LABEL_49;
  v13 = 0;
  v16 = 0;
  v17 = NET_FW_MODIFY_STATE_OK;
  for ( j = 0; ; ++j )
  {
    if ( j >= 3 )
    {
      *a2 = v17;
      goto LABEL_23;
    }
    v20 = FwGetProfileTypeFromProfileIndex(j);
    if ( (v20 & v28) != 0 )
      break;
LABEL_42:
    ;
  }
  v21 = *((_DWORD *)&v29 + j);
  if ( v21 == 1 )
  {
LABEL_40:
    if ( v16 )
    {
      if ( v21 != v17 )
      {
        if ( v17 == NET_FW_MODIFY_STATE_INBOUND_BLOCKED )
        {
          v17 = v21;
        }
        else if ( !v21 )
        {
          v17 = NET_FW_MODIFY_STATE_OK;
        }
        v13 = 1;
      }
    }
    else
    {
      v16 = 1;
      v17 = v21;
      v13 = 0;
    }
    goto LABEL_42;
  }
  v25 = 0;
  v26 = 4;
  v23 = v24;
  v27 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v22 = Int_FWGetOrSetConfig(1, v23, 3, v20, 1, (__int64)&v25, (__int64)&v26, (__int64)&v27);
  if ( v22 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v22);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  if ( !v22 )
  {
    if ( v25 )
    {
      v21 = 2;
      *((_DWORD *)&v29 + j) = 2;
    }
    goto LABEL_40;
  }
  v13 = FwReportErrorAsWinError("FwPolicy2::get_LocalPolicyModifyState", "FWGetConfig", v22);
LABEL_23:
  if ( v24 )
    FWClosePolicyStore(v24, v12, v14, v15);
  if ( v13 < 0 )
    return FwReportReturnError("FwPolicy2::get_LocalPolicyModifyState", (unsigned int)v13);
  else
    return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b390  mov     r11, rsp
0x18000b393  push    rbp
0x18000b394  push    rbx
0x18000b395  lea     rbp, [r11-5Fh]
0x18000b399  sub     rsp, 98h
0x18000b3a0  mov     rax, cs:__security_cookie
0x18000b3a7  xor     rax, rsp
0x18000b3aa  mov     [rbp+57h+var_28], rax
0x18000b3ae  mov     [r11+8], rsi
0x18000b3b2  mov     rsi, rdx
0x18000b3b5  mov     [r11-28h], r15
0x18000b3b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b3c0  lea     rbx, WPP_GLOBAL_Control
0x18000b3c7  cmp     rcx, rbx
0x18000b3ca  jnz     loc_18000B735
0x18000b3d0  xor     r15d, r15d
0x18000b3d3  mov     [rbp+57h+var_44], 4
0x18000b3da  lea     rax, [rbp+57h+var_44]
0x18000b3de  mov     [rbp+57h+var_50], r15
0x18000b3e2  mov     [rsp+0A0h+var_70], rax
0x18000b3e7  mov     ecx, 221h
0x18000b3ec  lea     rax, [rbp+57h+var_3C]
0x18000b3f0  mov     [rbp+57h+var_38], r15
0x18000b3f4  mov     [rsp+0A0h+var_78], rax
0x18000b3f9  xor     edx, edx
0x18000b3fb  mov     r9d, 2
0x18000b401  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000b406  mov     r8d, 5
0x18000b40c  mov     [rbp+57h+var_30], r15d
0x18000b410  mov     [rbp+57h+var_3C], r15d
0x18000b414  call    FWGetGlobalConfig
0x18000b419  test    eax, eax
0x18000b41b  jnz     loc_18000B530
0x18000b421  lea     rax, [rbp+57h+var_50]
0x18000b425  mov     [rsp+0A0h+arg_10], rdi
0x18000b42d  mov     r9d, 1
0x18000b433  mov     [rsp+0A0h+var_78], rax
0x18000b438  mov     r8d, r9d
0x18000b43b  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000b440  mov     ecx, 221h
0x18000b445  xor     edx, edx
0x18000b447  call    FWOpenPolicyStore
0x18000b44c  cmp     eax, 2
0x18000b44f  jz      loc_18000B54E
0x18000b455  test    eax, eax
0x18000b457  jnz     loc_18000B7A9
0x18000b45d  mov     ebx, r15d
0x18000b460  cmp     ebx, 3
0x18000b463  jnb     loc_18000B797
0x18000b469  mov     ecx, ebx
0x18000b46b  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000b471  mov     edi, eax
0x18000b473  test    [rbp+57h+var_3C], eax
0x18000b476  jz      loc_18000B529
0x18000b47c  mov     rcx, [rbp+57h+var_50]
0x18000b480  lea     rax, [rbp+57h+var_40]
0x18000b484  mov     [rsp+0A0h+var_70], rax
0x18000b489  xor     r9d, r9d
0x18000b48c  lea     rax, [rbp+57h+var_44]
0x18000b490  mov     [rbp+57h+var_48], r15d
0x18000b494  mov     [rsp+0A0h+var_78], rax
0x18000b499  mov     r8d, edi
0x18000b49c  lea     rax, [rbp+57h+var_48]
0x18000b4a0  mov     [rbp+57h+var_44], 4
0x18000b4a7  mov     edx, 3
0x18000b4ac  mov     [rsp+0A0h+var_80], rax
0x18000b4b1  mov     [rbp+57h+var_40], r15d
0x18000b4b5  call    FWGetConfig2
0x18000b4ba  cmp     eax, 2
0x18000b4bd  jz      loc_18000B7FF
0x18000b4c3  test    eax, eax
0x18000b4c5  jnz     loc_18000B823
0x18000b4cb  cmp     [rbp+57h+var_48], r15d
0x18000b4cf  jnz     loc_18000B808
0x18000b4d5  mov     rcx, [rbp+57h+var_50]
0x18000b4d9  lea     rax, [rbp+57h+var_40]
0x18000b4dd  mov     [rsp+0A0h+var_70], rax
0x18000b4e2  xor     r9d, r9d
0x18000b4e5  lea     rax, [rbp+57h+var_44]
0x18000b4e9  mov     [rbp+57h+var_40], r15d
0x18000b4ed  mov     [rsp+0A0h+var_78], rax
0x18000b4f2  mov     r8d, edi
0x18000b4f5  lea     rax, [rbp+57h+var_48]
0x18000b4f9  mov     edx, 0Dh
0x18000b4fe  mov     [rsp+0A0h+var_80], rax
0x18000b503  call    FWGetConfig2
0x18000b508  cmp     eax, 2
0x18000b50b  jz      loc_18000B817
0x18000b511  test    eax, eax
0x18000b513  jnz     loc_18000B823
0x18000b519  cmp     [rbp+57h+var_48], r15d
0x18000b51d  jnz     short loc_18000B529
0x18000b51f  mov     eax, ebx
0x18000b521  mov     dword ptr [rbp+rax*4+57h+var_38], 1
0x18000b529  inc     ebx
0x18000b52b  jmp     loc_18000B460
0x18000b530  mov     r8d, eax
0x18000b533  lea     rdx, aFwgetglobalcon_4; "FWGetGlobalConfig"
0x18000b53a  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000b541  call    cs:__imp_FwReportErrorAsWinError
0x18000b547  mov     ebx, eax
0x18000b549  jmp     loc_18000B5D8
0x18000b54e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b555  cmp     rcx, rbx
0x18000b558  jnz     loc_18000B7DB
0x18000b55e  lea     rax, [rbp+57h+var_50]
0x18000b562  mov     ecx, 221h
0x18000b567  mov     [rsp+0A0h+var_78], rax
0x18000b56c  xor     edx, edx
0x18000b56e  mov     r9d, 1
0x18000b574  mov     dword ptr [rsp+0A0h+var_80], r15d
0x18000b579  mov     r8d, 5
0x18000b57f  call    FWOpenPolicyStore
0x18000b584  test    eax, eax
0x18000b586  jnz     loc_18000B7A9
0x18000b58c  mov     [rsp+90h], r13
0x18000b594  mov     ebx, r15d
0x18000b597  mov     [rsp+0A0h+var_18], r14
0x18000b59f  mov     r13d, r15d
0x18000b5a2  mov     r14d, r15d
0x18000b5a5  mov     [rsp+0A0h+arg_18], r12
0x18000b5ad  mov     edi, r15d
0x18000b5b0  cmp     edi, 3
0x18000b5b3  jb      short loc_18000B618
0x18000b5b5  mov     [rsi], r14d
0x18000b5b8  mov     r12, [rsp+0A0h+arg_18]
0x18000b5c0  mov     r13, [rsp+90h]
0x18000b5c8  mov     r14, [rsp+0A0h+var_18]
0x18000b5d0  mov     rdi, [rsp+0A0h+arg_10]
0x18000b5d8  mov     rcx, [rbp+57h+var_50]
0x18000b5dc  mov     r15, [rsp+0A0h+var_20]
0x18000b5e4  mov     rsi, [rsp+0A0h+arg_0]
0x18000b5ec  test    rcx, rcx
0x18000b5ef  jnz     short loc_18000B611
0x18000b5f1  test    ebx, ebx
0x18000b5f3  js      loc_18000B7C7
0x18000b5f9  mov     eax, ebx
0x18000b5fb  mov     rcx, [rbp+57h+var_28]
0x18000b5ff  xor     rcx, rsp; StackCookie
0x18000b602  call    __security_check_cookie
0x18000b607  add     rsp, 98h
0x18000b60e  pop     rbx
0x18000b60f  pop     rbp
0x18000b610  retn
0x18000b611  call    FWClosePolicyStore
0x18000b616  jmp     short loc_18000B5F1
0x18000b618  mov     ecx, edi
0x18000b61a  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18000b620  mov     r15d, eax
0x18000b623  test    [rbp+57h+var_3C], eax
0x18000b626  jz      loc_18000B72E
0x18000b62c  mov     ecx, edi
0x18000b62e  lea     rax, [rbp+57h+var_38]
0x18000b632  mov     r12d, [rax+rcx*4]
0x18000b636  lea     rax, [rax+rcx*4]
0x18000b63a  mov     [rbp+57h+var_58], rax
0x18000b63e  cmp     r12d, 1
0x18000b642  jz      loc_18000B71A
0x18000b648  mov     rcx, cs:g_Provider
0x18000b64f  mov     rax, [rbp+57h+var_50]
0x18000b653  mov     [rbp+57h+var_48], 0
0x18000b65a  mov     [rbp+57h+var_44], 4
0x18000b661  mov     [rbp+57h+var_60], rax
0x18000b665  mov     [rbp+57h+var_40], 0
0x18000b66c  test    rcx, rcx
0x18000b66f  jz      short loc_18000B684
0x18000b671  xor     r9d, r9d
0x18000b674  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000b67b  xor     r8d, r8d
0x18000b67e  call    cs:__imp_EtwEventWrite
0x18000b684  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68b  lea     rax, WPP_GLOBAL_Control
0x18000b692  cmp     rcx, rax
0x18000b695  jz      short loc_18000B6A1
0x18000b697  test    byte ptr [rcx+1Ch], 8
0x18000b69b  jnz     loc_18000B841
0x18000b6a1  call    cs:__imp_GetTickCount64
0x18000b6a7  mov     rdx, [rbp+57h+var_60]
0x18000b6ab  lea     rax, [rbp+57h+var_40]
0x18000b6af  mov     [rsp+38h], rax
0x18000b6b4  mov     r9d, r15d
0x18000b6b7  lea     rax, [rbp+57h+var_44]
0x18000b6bb  mov     r8d, 3
0x18000b6c1  mov     [rsp+0A0h+var_70], rax
0x18000b6c6  mov     ecx, 1
0x18000b6cb  lea     rax, [rbp+57h+var_48]
0x18000b6cf  mov     [rsp+0A0h+var_78], rax
0x18000b6d4  mov     dword ptr [rsp+0A0h+var_80], 1
0x18000b6dc  call    Int_FWGetOrSetConfig
0x18000b6e1  mov     r15d, eax
0x18000b6e4  test    eax, eax
0x18000b6e6  jnz     short loc_18000B759
0x18000b6e8  mov     rcx, cs:g_Provider
0x18000b6ef  test    rcx, rcx
0x18000b6f2  jz      short loc_18000B707
0x18000b6f4  xor     r9d, r9d
0x18000b6f7  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000b6fe  xor     r8d, r8d
0x18000b701  call    cs:__imp_EtwEventWrite
0x18000b707  test    r15d, r15d
0x18000b70a  jnz     loc_18000B894
0x18000b710  cmp     [rbp+57h+var_48], r15d
0x18000b714  jnz     loc_18000B85B
0x18000b71a  test    r13d, r13d
0x18000b71d  jnz     loc_18000B86D
0x18000b723  mov     r13d, 1
0x18000b729  mov     r14d, r12d
0x18000b72c  xor     ebx, ebx
0x18000b72e  inc     edi
0x18000b730  jmp     loc_18000B5B0
0x18000b735  test    byte ptr [rcx+1Ch], 8
0x18000b739  jz      loc_18000B3D0
0x18000b73f  mov     rcx, [rcx+10h]
0x18000b743  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000b74a  mov     edx, 31h ; '1'
0x18000b74f  call    WPP_SF_
0x18000b754  jmp     loc_18000B3D0
0x18000b759  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b760  lea     rax, WPP_GLOBAL_Control
0x18000b767  cmp     rcx, rax
0x18000b76a  jz      loc_18000B6E8
0x18000b770  test    byte ptr [rcx+1Ch], 1
0x18000b774  jz      loc_18000B6E8
0x18000b77a  mov     rcx, [rcx+10h]
0x18000b77e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000b785  mov     edx, 6Bh ; 'k'
0x18000b78a  mov     r9d, r15d
0x18000b78d  call    WPP_SF_d
0x18000b792  jmp     loc_18000B6E8
0x18000b797  mov     rcx, [rbp+57h+var_50]
0x18000b79b  call    FWClosePolicyStore
0x18000b7a0  mov     [rbp+57h+var_50], r15
0x18000b7a4  jmp     loc_18000B55E
0x18000b7a9  mov     r8d, eax
0x18000b7ac  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x18000b7b3  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000b7ba  call    cs:__imp_FwReportErrorAsWinError
0x18000b7c0  mov     ebx, eax
0x18000b7c2  jmp     loc_18000B5D0
0x18000b7c7  mov     edx, ebx
0x18000b7c9  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000b7d0  call    cs:__imp_FwReportReturnError
0x18000b7d6  jmp     loc_18000B5FB
0x18000b7db  test    byte ptr [rcx+1Ch], 4
0x18000b7df  jz      loc_18000B55E
0x18000b7e5  mov     rcx, [rcx+10h]
0x18000b7e9  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18000b7f0  mov     edx, 32h ; '2'
0x18000b7f5  call    WPP_SF_
0x18000b7fa  jmp     loc_18000B55E
0x18000b7ff  mov     [rbp+57h+var_48], r15d
0x18000b803  jmp     loc_18000B4D5
0x18000b808  mov     eax, ebx
0x18000b80a  mov     dword ptr [rbp+rax*4+57h+var_38], 1
0x18000b812  jmp     loc_18000B4D5
0x18000b817  mov     [rbp+57h+var_48], 1
0x18000b81e  jmp     loc_18000B529
0x18000b823  mov     r8d, eax
0x18000b826  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x18000b82d  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000b834  call    cs:__imp_FwReportErrorAsWinError
0x18000b83a  mov     ebx, eax
0x18000b83c  jmp     loc_18000B5D0
0x18000b841  mov     rcx, [rcx+10h]
0x18000b845  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000b84c  mov     edx, 6Ah ; 'j'
0x18000b851  call    WPP_SF_
0x18000b856  jmp     loc_18000B6A1
0x18000b85b  mov     rax, [rbp+57h+var_58]
0x18000b85f  mov     r12d, 2
0x18000b865  mov     [rax], r12d
0x18000b868  jmp     loc_18000B71A
0x18000b86d  cmp     r12d, r14d
0x18000b870  jz      loc_18000B72E
0x18000b876  cmp     r14d, 2
0x18000b87a  jnz     short loc_18000B881
0x18000b87c  mov     r14d, r12d
0x18000b87f  jmp     short loc_18000B88A
0x18000b881  xor     eax, eax
0x18000b883  test    r12d, r12d
0x18000b886  cmovz   r14d, eax
0x18000b88a  mov     ebx, 1
0x18000b88f  jmp     loc_18000B72E
0x18000b894  mov     r8d, r15d
0x18000b897  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x18000b89e  lea     rcx, aFwpolicy2GetLo; "FwPolicy2::get_LocalPolicyModifyState"
0x18000b8a5  call    cs:__imp_FwReportErrorAsWinError
0x18000b8ab  mov     ebx, eax
0x18000b8ad  jmp     loc_18000B5B8
```

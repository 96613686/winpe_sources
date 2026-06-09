# VaultLogonSessionNotification(_LSAP_LOGON_SESSION_NOTIFICATION *)

- ea: `0x180027980`
- end: `0x180027d40`
- name: `?VaultLogonSessionNotification@@YAKPEAU_LSAP_LOGON_SESSION_NOTIFICATION@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(struct _LSAP_LOGON_SESSION_NOTIFICATION *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012210`
- `0x180027980`
- `0x1800311e0`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003ba98`
- `0x18003baf8`
- `0x18003c9f8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180027b97`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180027b97`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180027b80`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180027b80`
- `ntdll!RtlEqualSid` at `0x180027bc6`
- `ntdll!RtlEqualSid` at `0x180027bc6`
- `ntdll!RtlValidSid` at `0x180027b6f`
- `ntdll!RtlValidSid` at `0x180027b6f`
- `ntdll!RtlConvertSharedToExclusive` at `0x180027c55`
- `ntdll!RtlConvertSharedToExclusive` at `0x180027c55`
- `ntdll!RtlReleaseResource` at `0x180027be0`
- `ntdll!RtlReleaseResource` at `0x180027c0f`
- `ntdll!RtlReleaseResource` at `0x180027c46`
- `ntdll!RtlReleaseResource` at `0x180027c8c`
- `ntdll!RtlReleaseResource` at `0x180027cb3`
- `ntdll!RtlReleaseResource` at `0x180027be0`
- `ntdll!RtlReleaseResource` at `0x180027c0f`
- `ntdll!RtlReleaseResource` at `0x180027c46`
- `ntdll!RtlReleaseResource` at `0x180027c8c`
- `ntdll!RtlReleaseResource` at `0x180027cb3`
- `ntdll!RtlAcquireResourceShared` at `0x180027b66`
- `ntdll!RtlAcquireResourceShared` at `0x180027c1d`
- `ntdll!RtlAcquireResourceShared` at `0x180027b66`
- `ntdll!RtlAcquireResourceShared` at `0x180027c1d`

## string_xrefs

- `0x180027a5d`: `Created`
- `0x180027a56`: `Deleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall VaultLogonSessionNotification(struct _LSAP_LOGON_SESSION_NOTIFICATION *a1, int a2, int a3)
{
  __int64 v4; // r14
  PVOID *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  const char *v8; // r9
  void *v9; // rsi
  int v10; // r9d
  int v11; // ecx
  __int64 v12; // rbx
  bool v13; // si
  _QWORD *v14; // rcx
  _QWORD *v15; // r9
  _QWORD *v16; // rcx
  _QWORD *v17; // r8
  __int64 v18; // rdx
  CVaultMgr *v19; // rcx

  v4 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 2) == 0 )
      goto LABEL_9;
    v6 = 24;
LABEL_8:
    WPP_SF_(v5[2], v6, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_9:
    v7 = 87;
    goto LABEL_61;
  }
  if ( VaultGlobals::g_eEngineState != 2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
    {
      WPP_SF_(v5[2], 25, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_14;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
  {
    v8 = "Created";
    if ( *((_DWORD *)a1 + 1) != 1 )
      v8 = "Deleted";
    WPP_SF_sLLL((unsigned int)v5[2], a2, a3, (_DWORD)v8, *((_DWORD *)a1 + 2), *((_DWORD *)a1 + 4), *((_DWORD *)a1 + 3));
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = (void *)*((_QWORD *)a1 + 3);
  if ( !v9 )
  {
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 2) == 0 )
      goto LABEL_9;
    v6 = 27;
    goto LABEL_8;
  }
  v10 = *((_DWORD *)a1 + 2);
  if ( v10 && v10 != 2 && v10 != 4 && v10 != 5 && (unsigned int)(v10 - 10) >= 2 )
  {
    if ( v5 == &WPP_GLOBAL_Control || (*((_BYTE *)v5 + 28) & 8) == 0 )
    {
LABEL_14:
      v7 = 0;
      goto LABEL_61;
    }
    WPP_SF_LLL(v5[2]);
    v7 = 0;
LABEL_60:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_61;
  }
  v7 = 0;
  if ( *((_DWORD *)a1 + 1) == 1 )
    goto LABEL_61;
  if ( *((_DWORD *)a1 + 1) != 2 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
    {
      WPP_SF_d(v5[2], 30, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, *((unsigned int *)a1 + 1));
      v5 = (PVOID *)WPP_GLOBAL_Control;
      v7 = 87;
      goto LABEL_61;
    }
    goto LABEL_9;
  }
  RtlAcquireResourceShared(&Resource, 1u);
  if ( RtlValidSid(v9) && (v11 = *GetSidSubAuthorityCount(v9), (_BYTE)v11) )
  {
    v12 = VaultGlobals::g_VaultMgr[*GetSidSubAuthority(v9, v11 - 1) % 0xB];
    if ( v12 )
    {
      while ( !RtlEqualSid(v9, *(PSID *)v12) )
      {
        v12 = *(_QWORD *)(v12 + 16);
        if ( !v12 )
          goto LABEL_42;
      }
      (***(void (__fastcall ****)(_QWORD))(v12 + 8))(*(_QWORD *)(v12 + 8));
      v4 = *(_QWORD *)(v12 + 8);
      RtlReleaseResource(&Resource);
      v13 = 0;
      RtlAcquireResourceShared((PRTL_RESOURCE)(v4 + 72), 1u);
      v14 = *(_QWORD **)(v4 + 8);
      v7 = 0;
      if ( !v14 )
        goto LABEL_50;
      while ( *v14 != *(_QWORD *)((char *)a1 + 12) )
      {
        v14 = (_QWORD *)v14[1];
        if ( !v14 )
          goto LABEL_50;
      }
      RtlConvertSharedToExclusive((PRTL_RESOURCE)(v4 + 72));
      v15 = *(_QWORD **)(v4 + 8);
      v16 = v15;
      v17 = v15;
      if ( v15 )
      {
        while ( 1 )
        {
          v18 = v16[1];
          if ( *v16 == *(_QWORD *)((char *)a1 + 12) )
            break;
          v17 = v16;
          v16 = (_QWORD *)v16[1];
          if ( !v18 )
            goto LABEL_50;
        }
        if ( v15 == v16 )
        {
          *(_QWORD *)(v4 + 8) = v18;
          v13 = v18 == 0;
        }
        else
        {
          v17[1] = v18;
        }
        VaultFreeInternal(v16);
        RtlReleaseResource((PRTL_RESOURCE)(v4 + 72));
        if ( v13 )
          CVaultMgr::DeleteUserVaultManager(v19, *((void **)a1 + 3));
      }
      else
      {
LABEL_50:
        RtlReleaseResource((PRTL_RESOURCE)(v4 + 72));
      }
      goto LABEL_60;
    }
LABEL_42:
    RtlReleaseResource(&Resource);
    v7 = 1168;
  }
  else
  {
    v7 = 87;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_64;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, v7);
    goto LABEL_60;
  }
LABEL_61:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(v5[2], 31, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, v7);
LABEL_64:
  if ( v4 )
    AutoDereference<IVaultKeyManager>(v4);
  return v7;
}

```

## disassembly

```asm
0x180027980  push    rbx
0x180027982  push    rbp
0x180027983  push    rsi
0x180027984  push    rdi
0x180027985  push    r14
0x180027987  push    r15
0x180027989  sub     rsp, 68h
0x18002798d  mov     rdi, rcx
0x180027990  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180027997  mov     [rsp+98h+var_58], rax
0x18002799c  xor     r14d, r14d
0x18002799f  mov     [rsp+98h+var_50], r14
0x1800279a4  mov     [rsp+98h+var_48], r14d
0x1800279a9  lea     r15, WPP_GLOBAL_Control
0x1800279b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279b7  cmp     rcx, r15
0x1800279ba  jz      short loc_1800279DE
0x1800279bc  test    byte ptr [rcx+1Ch], 8
0x1800279c0  jz      short loc_1800279DE
0x1800279c2  mov     edx, 17h
0x1800279c7  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x1800279ce  mov     rcx, [rcx+10h]
0x1800279d2  call    WPP_SF_
0x1800279d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279de  test    rdi, rdi
0x1800279e1  jnz     short loc_180027A14
0x1800279e3  cmp     rcx, r15
0x1800279e6  jz      short loc_180027A0A
0x1800279e8  test    byte ptr [rcx+1Ch], 2
0x1800279ec  jz      short loc_180027A0A
0x1800279ee  mov     edx, 18h
0x1800279f3  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x1800279fa  mov     rcx, [rcx+10h]
0x1800279fe  call    WPP_SF_
0x180027a03  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a0a  mov     ebx, 57h ; 'W'
0x180027a0f  jmp     loc_180027CFF
0x180027a14  cmp     cs:?g_eEngineState@VaultGlobals@@3W4eVaultEngineState@@A, 2; eVaultEngineState VaultGlobals::g_eEngineState
0x180027a1b  jz      short loc_180027A4B
0x180027a1d  cmp     rcx, r15
0x180027a20  jz      short loc_180027A44
0x180027a22  test    byte ptr [rcx+1Ch], 4
0x180027a26  jz      short loc_180027A44
0x180027a28  mov     edx, 19h
0x180027a2d  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180027a34  mov     rcx, [rcx+10h]
0x180027a38  call    WPP_SF_
0x180027a3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a44  xor     ebx, ebx
0x180027a46  jmp     loc_180027CFF
0x180027a4b  cmp     rcx, r15
0x180027a4e  jz      short loc_180027A91
0x180027a50  test    byte ptr [rcx+1Ch], 8
0x180027a54  jz      short loc_180027A91
0x180027a56  lea     rax, aDeleted; "Deleted"
0x180027a5d  lea     r9, aCreated; "Created"
0x180027a64  cmp     dword ptr [rdi+4], 1
0x180027a68  cmovnz  r9, rax
0x180027a6c  mov     eax, [rdi+0Ch]
0x180027a6f  mov     [rsp+98h+var_68], eax
0x180027a73  mov     eax, [rdi+10h]
0x180027a76  mov     [rsp+98h+var_70], eax
0x180027a7a  mov     eax, [rdi+8]
0x180027a7d  mov     [rsp+98h+var_78], eax
0x180027a81  mov     rcx, [rcx+10h]
0x180027a85  call    WPP_SF_sLLL
0x180027a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a91  mov     rsi, [rdi+18h]
0x180027a95  test    rsi, rsi
0x180027a98  jnz     short loc_180027AB7
0x180027a9a  cmp     rcx, r15
0x180027a9d  jz      loc_180027A0A
0x180027aa3  test    byte ptr [rcx+1Ch], 2
0x180027aa7  jz      loc_180027A0A
0x180027aad  mov     edx, 1Bh
0x180027ab2  jmp     loc_1800279F3
0x180027ab7  mov     r9d, [rdi+8]
0x180027abb  test    r9d, r9d
0x180027abe  jz      short loc_180027B0D
0x180027ac0  mov     edx, r9d
0x180027ac3  sub     edx, 2
0x180027ac6  jz      short loc_180027B0D
0x180027ac8  sub     edx, 2
0x180027acb  jz      short loc_180027B0D
0x180027acd  sub     edx, 1
0x180027ad0  jz      short loc_180027B0D
0x180027ad2  sub     edx, 5
0x180027ad5  jz      short loc_180027B0D
0x180027ad7  cmp     edx, 1
0x180027ada  jz      short loc_180027B0D
0x180027adc  cmp     rcx, r15
0x180027adf  jz      loc_180027A44
0x180027ae5  test    byte ptr [rcx+1Ch], 8
0x180027ae9  jz      loc_180027A44
0x180027aef  mov     eax, [rdi+0Ch]
0x180027af2  mov     [rsp+98h+var_70], eax
0x180027af6  mov     eax, [rdi+10h]
0x180027af9  mov     [rsp+98h+var_78], eax
0x180027afd  mov     rcx, [rcx+10h]
0x180027b01  call    WPP_SF_LLL
0x180027b06  xor     ebx, ebx
0x180027b08  jmp     loc_180027CF8
0x180027b0d  xor     ebx, ebx
0x180027b0f  mov     r9d, [rdi+4]
0x180027b13  mov     eax, r9d
0x180027b16  sub     eax, 1
0x180027b19  jz      loc_180027CFF
0x180027b1f  cmp     eax, 1
0x180027b22  jz      short loc_180027B5D
0x180027b24  cmp     rcx, r15
0x180027b27  jz      loc_180027A0A
0x180027b2d  test    byte ptr [rcx+1Ch], 2
0x180027b31  jz      loc_180027A0A
0x180027b37  mov     edx, 1Eh
0x180027b3c  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180027b43  mov     rcx, [rcx+10h]
0x180027b47  call    WPP_SF_d
0x180027b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b53  mov     ebx, 57h ; 'W'
0x180027b58  jmp     loc_180027CFF
0x180027b5d  mov     dl, 1; Wait
0x180027b5f  lea     rcx, Resource; Resource
0x180027b66  call    cs:__imp_RtlAcquireResourceShared
0x180027b6c  mov     rcx, rsi; Sid
0x180027b6f  call    cs:__imp_RtlValidSid
0x180027b75  test    al, al
0x180027b77  jz      loc_180027CC9
0x180027b7d  mov     rcx, rsi; pSid
0x180027b80  call    cs:__imp_GetSidSubAuthorityCount
0x180027b86  movzx   ecx, byte ptr [rax]
0x180027b89  test    cl, cl
0x180027b8b  jz      loc_180027CC9
0x180027b91  lea     edx, [rcx-1]; nSubAuthority
0x180027b94  mov     rcx, rsi; pSid
0x180027b97  call    cs:__imp_GetSidSubAuthority
0x180027b9d  mov     ecx, [rax]
0x180027b9f  mov     eax, 0BA2E8BA3h
0x180027ba4  mul     ecx
0x180027ba6  shr     edx, 3
0x180027ba9  imul    eax, edx, 0Bh
0x180027bac  sub     ecx, eax
0x180027bae  lea     rbx, ?g_VaultMgr@VaultGlobals@@3VCVaultMgr@@A; CVaultMgr VaultGlobals::g_VaultMgr
0x180027bb5  mov     rbx, [rbx+rcx*8]
0x180027bb9  test    rbx, rbx
0x180027bbc  jz      short loc_180027BD9
0x180027bbe  xchg    ax, ax
0x180027bc0  mov     rdx, [rbx]; Sid2
0x180027bc3  mov     rcx, rsi; Sid1
0x180027bc6  call    cs:__imp_RtlEqualSid
0x180027bcc  test    al, al
0x180027bce  jnz     short loc_180027BF0
0x180027bd0  mov     rbx, [rbx+10h]
0x180027bd4  test    rbx, rbx
0x180027bd7  jnz     short loc_180027BC0
0x180027bd9  lea     rcx, Resource; Resource
0x180027be0  call    cs:__imp_RtlReleaseResource
0x180027be6  mov     ebx, 490h
0x180027beb  jmp     loc_180027CCE
0x180027bf0  mov     rcx, [rbx+8]
0x180027bf4  mov     rax, [rcx]
0x180027bf7  mov     rax, [rax]
0x180027bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bff  mov     r14, [rbx+8]
0x180027c03  mov     [rsp+98h+var_50], r14
0x180027c08  lea     rcx, Resource; Resource
0x180027c0f  call    cs:__imp_RtlReleaseResource
0x180027c15  xor     esi, esi
0x180027c17  mov     dl, 1; Wait
0x180027c19  lea     rcx, [r14+48h]; Resource
0x180027c1d  call    cs:__imp_RtlAcquireResourceShared
0x180027c23  mov     rcx, [r14+8]
0x180027c27  xor     ebx, ebx
0x180027c29  test    rcx, rcx
0x180027c2c  jz      short loc_180027C42
0x180027c2e  xchg    ax, ax
0x180027c30  mov     rax, [rcx]
0x180027c33  cmp     rax, [rdi+0Ch]
0x180027c37  jz      short loc_180027C51
0x180027c39  mov     rcx, [rcx+8]
0x180027c3d  test    rcx, rcx
0x180027c40  jnz     short loc_180027C30
0x180027c42  lea     rcx, [r14+48h]; Resource
0x180027c46  call    cs:__imp_RtlReleaseResource
0x180027c4c  jmp     loc_180027CF8
0x180027c51  lea     rcx, [r14+48h]; Resource
0x180027c55  call    cs:__imp_RtlConvertSharedToExclusive
0x180027c5b  mov     r9, [r14+8]
0x180027c5f  mov     rcx, r9; hMem
0x180027c62  mov     r8, r9
0x180027c65  test    r9, r9
0x180027c68  jz      short loc_180027C42
0x180027c6a  nop     word ptr [rax+rax+00h]
0x180027c70  mov     rax, [rcx]
0x180027c73  mov     rdx, [rcx+8]
0x180027c77  cmp     rax, [rdi+0Ch]
0x180027c7b  jz      short loc_180027C94
0x180027c7d  mov     r8, rcx
0x180027c80  mov     rcx, rdx
0x180027c83  test    rdx, rdx
0x180027c86  jnz     short loc_180027C70
0x180027c88  lea     rcx, [r14+48h]; Resource
0x180027c8c  call    cs:__imp_RtlReleaseResource
0x180027c92  jmp     short loc_180027CF8
0x180027c94  cmp     r9, rcx
0x180027c97  jnz     short loc_180027CA6
0x180027c99  mov     [r14+8], rdx
0x180027c9d  test    rdx, rdx
0x180027ca0  setz    sil
0x180027ca4  jmp     short loc_180027CAA
0x180027ca6  mov     [r8+8], rdx
0x180027caa  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180027caf  lea     rcx, [r14+48h]; Resource
0x180027cb3  call    cs:__imp_RtlReleaseResource
0x180027cb9  test    sil, sil
0x180027cbc  jz      short loc_180027CF8
0x180027cbe  mov     rdx, [rdi+18h]; void *
0x180027cc2  call    ?DeleteUserVaultManager@CVaultMgr@@QEAAKPEAX@Z; CVaultMgr::DeleteUserVaultManager(void *)
0x180027cc7  jmp     short loc_180027CF8
0x180027cc9  mov     ebx, 57h ; 'W'
0x180027cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cd5  cmp     rcx, r15
0x180027cd8  jz      short loc_180027D23
0x180027cda  test    byte ptr [rcx+1Ch], 2
0x180027cde  jz      short loc_180027CFF
0x180027ce0  mov     edx, 1Dh
0x180027ce5  mov     r9d, ebx
0x180027ce8  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180027cef  mov     rcx, [rcx+10h]
0x180027cf3  call    WPP_SF_d
0x180027cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cff  cmp     rcx, r15
0x180027d02  jz      short loc_180027D23
0x180027d04  test    byte ptr [rcx+1Ch], 8
0x180027d08  jz      short loc_180027D23
0x180027d0a  mov     edx, 1Fh
0x180027d0f  mov     r9d, ebx
0x180027d12  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180027d19  mov     rcx, [rcx+10h]
0x180027d1d  call    WPP_SF_d
0x180027d22  nop
0x180027d23  test    r14, r14
0x180027d26  jz      short loc_180027D31
0x180027d28  mov     rcx, r14
0x180027d2b  call    ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180027d30  nop
0x180027d31  mov     eax, ebx
0x180027d33  add     rsp, 68h
0x180027d37  pop     r15
0x180027d39  pop     r14
0x180027d3b  pop     rdi
0x180027d3c  pop     rsi
0x180027d3d  pop     rbp
0x180027d3e  pop     rbx
0x180027d3f  retn
```

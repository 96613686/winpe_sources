# CConfigManager::DeleteCredentialsFromCredmanStore(IRequestContext *,ushort *)

- ea: `0x18019bf20`
- end: `0x18019c329`
- name: `?DeleteCredentialsFromCredmanStore@CConfigManager@@SAHPEAVIRequestContext@@PEAG@Z`
- size: `1033`
- prototype: `__int64 __fastcall(struct IRequestContext *, LPCWSTR TargetName)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180196b88`
- `0x180198e6c`
- `0x18019ae98`

## callees

- `0x180005d10`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x1801133b0`
- `0x18019bf20`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c258`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019bfec`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019bfec`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019bff9`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019bff9`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019c041`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019c309`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019c041`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019c309`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18019c1aa`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18019c1aa`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019c2b0`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019c2b0`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18019c217`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x18019c217`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019c091`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019c091`

## string_xrefs

- `0x18019bf5b`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019c031`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019c0c0`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019c2de`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConfigManager::DeleteCredentialsFromCredmanStore(struct IRequestContext *a1, WCHAR *TargetName)
{
  __int64 v5; // r14
  PCREDENTIALW v6; // rcx
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  PCREDENTIAL_ATTRIBUTEW Attributes; // rax
  int v10; // r8d
  DWORD v11; // eax
  void (__fastcall *v12)(struct IRequestContext *, _QWORD); // rbx
  DWORD v13; // eax
  DWORD LastError; // eax
  __int64 v15; // rdx
  PCREDENTIALW v16; // rax
  __int64 CredentialBlobSize; // rdx
  LPBYTE CredentialBlob; // rcx
  unsigned int v19; // ebx
  HANDLE hObject; // [rsp+30h] [rbp-49h] BYREF
  __int128 v21; // [rsp+38h] [rbp-41h] BYREF
  int *v22; // [rsp+48h] [rbp-31h]
  struct _CREDENTIALW v23; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v24; // [rsp+A0h] [rbp+27h]
  int v25; // [rsp+E0h] [rbp+67h] BYREF
  PCREDENTIALW Credential; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2632, L"2632", 0x54Fu, 0);
    return 0;
  }
  if ( !TargetName )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2633, L"2633", 0x54Fu, a1);
    return 0;
  }
  Credential = 0;
  v5 = 80;
  memset_0(&v23, 0, sizeof(v23));
  v21 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
  v24 = &CConfigManager::s_lock;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive(&CConfigManager::s_lock) )
    RtlQueueAcquireFastLockExclusive(&CConfigManager::s_lock);
  hObject = (HANDLE)-1LL;
  if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 4u) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2657, L"2657", 0x54Fu, a1);
    RtlReleaseFastLockExclusive(&CConfigManager::s_lock);
    return 0;
  }
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, TargetName);
  if ( !CredReadW(TargetName, 1u, 0, &Credential) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_41;
    LastError = GetLastError();
    v15 = 112;
    goto LABEL_40;
  }
  v6 = Credential;
  if ( !Credential->AttributeCount )
  {
    v7 = L"2673";
    v8 = 2673;
LABEL_19:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", v8, v7, 0x54Fu, a1);
    goto LABEL_41;
  }
  Attributes = Credential->Attributes;
  if ( !Attributes )
  {
    v7 = L"2675";
    v8 = 2675;
    goto LABEL_19;
  }
  v10 = *(_DWORD *)Attributes->Value;
  v25 = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      109,
      (unsigned int)WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
      (_DWORD)TargetName,
      v10);
    v6 = Credential;
    v10 = v25;
  }
  if ( !v10 )
  {
    v7 = L"2681";
    v8 = 2681;
    goto LABEL_19;
  }
  v25 = v10 - 1;
  if ( v10 != 1 )
  {
    v23.Flags = 0;
    v23.Type = 1;
    v23.TargetName = TargetName;
    v23.Comment = 0;
    v23.CredentialBlobSize = v6->CredentialBlobSize;
    v23.CredentialBlob = v6->CredentialBlob;
    v23.Persist = 2;
    HIDWORD(v21) = 4;
    v22 = &v25;
    *(_QWORD *)&v21 = TargetName;
    v23.AttributeCount = 1;
    v23.Attributes = (PCREDENTIAL_ATTRIBUTEW)&v21;
    *(_OWORD *)&v23.TargetAlias = 0;
    if ( !CredWriteW(&v23, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        v11 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v11);
      }
      v12 = *(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL);
      v13 = GetLastError();
      v12(a1, v13);
    }
    goto LABEL_41;
  }
  if ( !CredDeleteW(TargetName, 1u, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
  {
    LastError = GetLastError();
    v15 = 111;
LABEL_40:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, LastError);
  }
LABEL_41:
  v16 = Credential;
  if ( Credential )
  {
    CredentialBlobSize = Credential->CredentialBlobSize;
    CredentialBlob = Credential->CredentialBlob;
    if ( Credential->CredentialBlobSize )
    {
      do
      {
        *CredentialBlob++ = 0;
        --CredentialBlobSize;
      }
      while ( CredentialBlobSize );
      v16 = Credential;
    }
    do
    {
      LOBYTE(v16->Flags) = 0;
      v16 = (PCREDENTIALW)((char *)v16 + 1);
      --v5;
    }
    while ( v5 );
    CredFree(Credential);
    Credential = 0;
  }
  if ( (unsigned int)CSecurity::EndRevertToSelf(hObject) )
  {
    v19 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 144LL))(a1);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2751, L"2751", 0x54Fu, a1);
    v19 = 0;
  }
  RtlReleaseFastLockExclusive(&CConfigManager::s_lock);
  return v19;
}

```

## disassembly

```asm
0x18019bf20  mov     [rsp-8+arg_8], rbx
0x18019bf25  push    rbp
0x18019bf26  push    rsi
0x18019bf27  push    r12
0x18019bf29  push    r13
0x18019bf2b  push    r14
0x18019bf2d  lea     rbp, [rsp-37h]
0x18019bf32  sub     rsp, 0B0h
0x18019bf39  mov     rbx, rdx
0x18019bf3c  mov     rsi, rcx
0x18019bf3f  test    rcx, rcx
0x18019bf42  jnz     short loc_18019BF6E
0x18019bf44  mov     [rsp+0D0h+var_B0], rcx; struct IRequestContext *
0x18019bf49  lea     r8, a2632; "2632"
0x18019bf50  mov     edx, 0A48h; unsigned int
0x18019bf55  mov     r9d, 54Fh; unsigned int
0x18019bf5b  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019bf62  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019bf67  xor     eax, eax
0x18019bf69  jmp     loc_18019C311
0x18019bf6e  test    rbx, rbx
0x18019bf71  jnz     short loc_18019BF86
0x18019bf73  mov     [rsp+0D0h+var_B0], rsi
0x18019bf78  lea     r8, a2633; "2633"
0x18019bf7f  mov     edx, 0A49h
0x18019bf84  jmp     short loc_18019BF55
0x18019bf86  mov     [rbp+57h+Credential], 0
0x18019bf8e  mov     r14d, 50h ; 'P'
0x18019bf94  mov     r8d, r14d; Size
0x18019bf97  xor     edx, edx; Val
0x18019bf99  lea     rcx, [rbp+57h+var_80]; void *
0x18019bf9d  call    memset_0
0x18019bfa2  xorps   xmm0, xmm0
0x18019bfa5  xor     eax, eax
0x18019bfa7  movups  [rbp+57h+var_98], xmm0
0x18019bfab  mov     [rbp+57h+var_88], rax
0x18019bfaf  lea     r13, WPP_GLOBAL_Control
0x18019bfb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18019bfbd  cmp     rcx, r13
0x18019bfc0  jz      short loc_18019BFDE
0x18019bfc2  test    dword ptr [rcx+1Ch], 200000h
0x18019bfc9  jz      short loc_18019BFDE
0x18019bfcb  lea     edx, [rax+6Bh]
0x18019bfce  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019bfd5  mov     rcx, [rcx+10h]
0x18019bfd9  call    WPP_SF_
0x18019bfde  lea     r12, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019bfe5  mov     [rbp+57h+var_30], r12
0x18019bfe9  mov     rcx, r12
0x18019bfec  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x18019bff2  test    eax, eax
0x18019bff4  jnz     short loc_18019C000
0x18019bff6  mov     rcx, r12
0x18019bff9  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x18019bfff  nop
0x18019c000  mov     [rbp+57h+hObject], 0FFFFFFFFFFFFFFFFh
0x18019c008  mov     edx, 4; DesiredAccess
0x18019c00d  lea     rcx, [rbp+57h+hObject]; void **
0x18019c011  call    ?BeginRevertToSelf@CSecurity@@SAHPEAPEAXK@Z; CSecurity::BeginRevertToSelf(void * *,ulong)
0x18019c016  test    eax, eax
0x18019c018  jnz     short loc_18019C04C
0x18019c01a  mov     [rsp+0D0h+var_B0], rsi; struct IRequestContext *
0x18019c01f  mov     r9d, 54Fh; unsigned int
0x18019c025  lea     r8, a2657; "2657"
0x18019c02c  mov     edx, 0A61h; unsigned int
0x18019c031  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019c038  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019c03d  nop
0x18019c03e  mov     rcx, r12
0x18019c041  call    cs:__imp_RtlReleaseFastLockExclusive
0x18019c047  jmp     loc_18019BF67
0x18019c04c  mov     [rbp+57h+arg_0], 0
0x18019c053  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c05a  cmp     rcx, r13
0x18019c05d  jz      short loc_18019C080
0x18019c05f  test    dword ptr [rcx+1Ch], 200000h
0x18019c066  jz      short loc_18019C080
0x18019c068  mov     edx, 6Ch ; 'l'
0x18019c06d  mov     r9, rbx
0x18019c070  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c077  mov     rcx, [rcx+10h]
0x18019c07b  call    WPP_SF_S
0x18019c080  lea     r9, [rbp+57h+Credential]; Credential
0x18019c084  xor     r8d, r8d; Flags
0x18019c087  lea     r12d, [r8+1]
0x18019c08b  mov     edx, r12d; Type
0x18019c08e  mov     rcx, rbx; TargetName
0x18019c091  call    cs:__imp_CredReadW
0x18019c097  test    eax, eax
0x18019c099  jz      loc_18019C243
0x18019c09f  mov     rcx, [rbp+57h+Credential]
0x18019c0a3  cmp     dword ptr [rcx+34h], 0
0x18019c0a7  jnz     short loc_18019C0D1
0x18019c0a9  lea     r8, a2673; "2673"
0x18019c0b0  mov     edx, 0A71h; unsigned int
0x18019c0b5  mov     [rsp+0D0h+var_B0], rsi; struct IRequestContext *
0x18019c0ba  mov     r9d, 54Fh; unsigned int
0x18019c0c0  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019c0c7  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019c0cc  jmp     loc_18019C27D
0x18019c0d1  mov     rax, [rcx+38h]
0x18019c0d5  test    rax, rax
0x18019c0d8  jnz     short loc_18019C0E8
0x18019c0da  lea     r8, a2675; "2675"
0x18019c0e1  mov     edx, 0A73h
0x18019c0e6  jmp     short loc_18019C0B5
0x18019c0e8  mov     rax, [rax+10h]
0x18019c0ec  mov     r8d, [rax]
0x18019c0ef  mov     [rbp+57h+arg_0], r8d
0x18019c0f3  mov     rax, cs:WPP_GLOBAL_Control
0x18019c0fa  cmp     rax, r13
0x18019c0fd  jz      short loc_18019C12D
0x18019c0ff  test    dword ptr [rax+1Ch], 200000h
0x18019c106  jz      short loc_18019C12D
0x18019c108  mov     edx, 6Dh ; 'm'
0x18019c10d  mov     dword ptr [rsp+0D0h+var_B0], r8d
0x18019c112  mov     r9, rbx
0x18019c115  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c11c  mov     rcx, [rax+10h]
0x18019c120  call    WPP_SF_Sd
0x18019c125  mov     rcx, [rbp+57h+Credential]
0x18019c129  mov     r8d, [rbp+57h+arg_0]
0x18019c12d  test    r8d, r8d
0x18019c130  jnz     short loc_18019C143
0x18019c132  lea     r8, a2681; "2681"
0x18019c139  mov     edx, 0A79h
0x18019c13e  jmp     loc_18019C0B5
0x18019c143  add     r8d, 0FFFFFFFFh
0x18019c147  mov     [rbp+57h+arg_0], r8d
0x18019c14b  jz      loc_18019C20E
0x18019c151  mov     [rbp+57h+var_80.Flags], 0
0x18019c158  mov     [rbp+57h+var_80.Type], r12d
0x18019c15c  mov     [rbp+57h+var_80.TargetName], rbx
0x18019c160  mov     [rbp+57h+var_80.Comment], 0
0x18019c168  mov     eax, [rcx+20h]
0x18019c16b  mov     [rbp+57h+var_80.CredentialBlobSize], eax
0x18019c16e  mov     rax, [rcx+28h]
0x18019c172  mov     [rbp+57h+var_80.CredentialBlob], rax
0x18019c176  mov     [rbp+57h+var_80.Persist], 2
0x18019c17d  mov     dword ptr [rbp+57h+var_98+0Ch], 4
0x18019c184  lea     rax, [rbp+57h+arg_0]
0x18019c188  mov     [rbp+57h+var_88], rax
0x18019c18c  mov     qword ptr [rbp+57h+var_98], rbx
0x18019c190  mov     [rbp+57h+var_80.AttributeCount], r12d
0x18019c194  lea     rax, [rbp+57h+var_98]
0x18019c198  mov     [rbp+57h+var_80.Attributes], rax
0x18019c19c  xorps   xmm0, xmm0
0x18019c19f  movdqa  xmmword ptr [rbp+57h+var_80.TargetAlias], xmm0
0x18019c1a4  xor     edx, edx; Flags
0x18019c1a6  lea     rcx, [rbp+57h+var_80]; Credential
0x18019c1aa  call    cs:__imp_CredWriteW
0x18019c1b0  test    eax, eax
0x18019c1b2  jnz     loc_18019C27D
0x18019c1b8  mov     rax, cs:WPP_GLOBAL_Control
0x18019c1bf  cmp     rax, r13
0x18019c1c2  jz      short loc_18019C1F2
0x18019c1c4  test    dword ptr [rax+1Ch], 400000h
0x18019c1cb  jz      short loc_18019C1F2
0x18019c1cd  call    cs:__imp_GetLastError
0x18019c1d3  mov     edx, 6Eh ; 'n'
0x18019c1d8  mov     r9d, eax
0x18019c1db  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c1e9  mov     rcx, [rcx+10h]
0x18019c1ed  call    WPP_SF_d
0x18019c1f2  mov     rax, [rsi]
0x18019c1f5  mov     rbx, [rax+48h]
0x18019c1f9  call    cs:__imp_GetLastError
0x18019c1ff  mov     edx, eax
0x18019c201  mov     rcx, rsi
0x18019c204  mov     rax, rbx
0x18019c207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c20c  jmp     short loc_18019C27D
0x18019c20e  xor     r8d, r8d; Flags
0x18019c211  mov     edx, r12d; Type
0x18019c214  mov     rcx, rbx; TargetName
0x18019c217  call    cs:__imp_CredDeleteW
0x18019c21d  test    eax, eax
0x18019c21f  jnz     short loc_18019C27D
0x18019c221  mov     rax, cs:WPP_GLOBAL_Control
0x18019c228  cmp     rax, r13
0x18019c22b  jz      short loc_18019C27D
0x18019c22d  test    dword ptr [rax+1Ch], 800h
0x18019c234  jz      short loc_18019C27D
0x18019c236  call    cs:__imp_GetLastError
0x18019c23c  mov     edx, 6Fh ; 'o'
0x18019c241  jmp     short loc_18019C263
0x18019c243  mov     rax, cs:WPP_GLOBAL_Control
0x18019c24a  cmp     rax, r13
0x18019c24d  jz      short loc_18019C27D
0x18019c24f  test    dword ptr [rax+1Ch], 800h
0x18019c256  jz      short loc_18019C27D
0x18019c258  call    cs:__imp_GetLastError
0x18019c25e  mov     edx, 70h ; 'p'
0x18019c263  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c26a  mov     r9d, eax
0x18019c26d  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c274  mov     rcx, [rcx+10h]
0x18019c278  call    WPP_SF_d
0x18019c27d  mov     rax, [rbp+57h+Credential]
0x18019c281  test    rax, rax
0x18019c284  jz      short loc_18019C2BA
0x18019c286  mov     edx, [rax+20h]
0x18019c289  mov     rcx, [rax+28h]
0x18019c28d  test    rdx, rdx
0x18019c290  jz      short loc_18019C2A1
0x18019c292  mov     byte ptr [rcx], 0
0x18019c295  add     rcx, r12
0x18019c298  sub     rdx, r12
0x18019c29b  jnz     short loc_18019C292
0x18019c29d  mov     rax, [rbp+57h+Credential]
0x18019c2a1  mov     byte ptr [rax], 0
0x18019c2a4  add     rax, r12
0x18019c2a7  sub     r14, r12
0x18019c2aa  jnz     short loc_18019C2A1
0x18019c2ac  mov     rcx, [rbp+57h+Credential]; Buffer
0x18019c2b0  call    cs:__imp_CredFree
0x18019c2b6  mov     [rbp+57h+Credential], r14
0x18019c2ba  mov     rcx, [rbp+57h+hObject]; hObject
0x18019c2be  call    ?EndRevertToSelf@CSecurity@@SAHPEAX@Z; CSecurity::EndRevertToSelf(void *)
0x18019c2c3  test    eax, eax
0x18019c2c5  jnz     short loc_18019C2EE
0x18019c2c7  mov     [rsp+0D0h+var_B0], rsi; struct IRequestContext *
0x18019c2cc  mov     r9d, 54Fh; unsigned int
0x18019c2d2  lea     r8, a2751; "2751"
0x18019c2d9  mov     edx, 0ABFh; unsigned int
0x18019c2de  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019c2e5  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019c2ea  xor     ebx, ebx
0x18019c2ec  jmp     short loc_18019C302
0x18019c2ee  mov     rax, [rsi]
0x18019c2f1  mov     rcx, rsi
0x18019c2f4  mov     rax, [rax+90h]
0x18019c2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c300  mov     ebx, eax
0x18019c302  lea     rcx, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019c309  call    cs:__imp_RtlReleaseFastLockExclusive
0x18019c30f  mov     eax, ebx
0x18019c311  mov     rbx, [rsp+0D0h+arg_8]
0x18019c319  add     rsp, 0B0h
0x18019c320  pop     r14
0x18019c322  pop     r13
0x18019c324  pop     r12
0x18019c326  pop     rsi
0x18019c327  pop     rbp
0x18019c328  retn
```

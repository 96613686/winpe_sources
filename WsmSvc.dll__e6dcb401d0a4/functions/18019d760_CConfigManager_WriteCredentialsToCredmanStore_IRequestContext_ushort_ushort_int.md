# CConfigManager::WriteCredentialsToCredmanStore(IRequestContext *,ushort *,ushort *,int)

- ea: `0x18019d760`
- end: `0x18019db42`
- name: `?WriteCredentialsToCredmanStore@CConfigManager@@SAHPEAVIRequestContext@@PEAG1H@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct IRequestContext *, LPCWSTR TargetName, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180198e6c`
- `0x18019d740`

## callees

- `0x180005d10`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x180112380`
- `0x1801123a8`
- `0x1801123e8`
- `0x18011d8c0`
- `0x18019d760`
- `0x1801ba152`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019da59`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019d84a`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019d84a`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019d857`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019d857`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019d8a1`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019db26`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019d8a1`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019db26`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18019d9dc`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18019d9dc`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019daa4`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019daa4`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019d90b`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019d90b`

## string_xrefs

- `0x18019d7a4`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019d88d`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019dafa`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConfigManager::WriteCredentialsToCredmanStore(
        struct IRequestContext *a1,
        WCHAR *TargetName,
        BYTE *a3,
        int a4)
{
  __int64 v9; // r15
  __int64 v10; // rsi
  unsigned int v11; // r8d
  DWORD LastError; // eax
  DWORD v13; // eax
  void (__fastcall *v14)(struct IRequestContext *, __int64); // rdi
  __int64 v15; // rdx
  PCREDENTIALW v16; // rax
  __int64 CredentialBlobSize; // rdx
  LPBYTE CredentialBlob; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  LPBYTE v21; // rcx
  struct _CREDENTIALW *v22; // rax
  unsigned int v23; // ebx
  PCREDENTIALW Credential; // [rsp+30h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-71h] BYREF
  __int128 v26; // [rsp+40h] [rbp-69h] BYREF
  int *v27; // [rsp+50h] [rbp-59h]
  struct _CREDENTIALW v28; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v29; // [rsp+B0h] [rbp+7h]
  int v30; // [rsp+110h] [rbp+67h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2446, L"2446", 0x54Fu, 0);
    return 0;
  }
  if ( !TargetName )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2447, L"2447", 0x54Fu, a1);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2448, L"2448", 0x54Fu, a1);
    return 0;
  }
  Credential = 0;
  v9 = 80;
  memset_0(&v28, 0, sizeof(v28));
  v26 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
  v29 = &CConfigManager::s_lock;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive(&CConfigManager::s_lock) )
    RtlQueueAcquireFastLockExclusive(&CConfigManager::s_lock);
  v10 = -1;
  hObject = (HANDLE)-1LL;
  if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 4u) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2474, L"2474", 0x54Fu, a1);
    RtlReleaseFastLockExclusive(&CConfigManager::s_lock);
    return 0;
  }
  v30 = 0;
  v26 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      99,
      (unsigned int)WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
      (_DWORD)TargetName,
      (__int64)&Class);
  if ( !CredReadW(TargetName, 1u, 0, &Credential) )
    goto LABEL_22;
  v11 = *(_DWORD *)Credential->Attributes->Value;
  v30 = v11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      (unsigned int)WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids,
      (_DWORD)TargetName,
      v11);
LABEL_22:
    v11 = v30;
  }
  if ( a4 )
  {
LABEL_26:
    v28.Flags = 0;
    v28.Type = 1;
    v28.TargetName = TargetName;
    v28.Comment = 0;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    v28.CredentialBlobSize = 2 * v10 + 2;
    v28.CredentialBlob = a3;
    v28.Persist = 2;
    HIDWORD(v26) = 4;
    v27 = &v30;
    *(_QWORD *)&v26 = TargetName;
    v28.AttributeCount = 1;
    v28.Attributes = (PCREDENTIAL_ATTRIBUTEW)&v26;
    *(_OWORD *)&v28.TargetAlias = 0;
    if ( !CredWriteW(&v28, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, LastError);
      }
      v13 = GetLastError();
      v14 = *(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL);
      if ( v13 == 8 )
        v15 = 2150859091LL;
      else
        v15 = GetLastError();
      v14(a1, v15);
    }
    goto LABEL_37;
  }
  if ( v11 + 1 >= v11 )
  {
    v30 = v11 + 1;
    goto LABEL_26;
  }
  v30 = -1;
  (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 2150859091LL);
LABEL_37:
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
    v19 = 80;
    do
    {
      LOBYTE(v16->Flags) = 0;
      v16 = (PCREDENTIALW)((char *)v16 + 1);
      --v19;
    }
    while ( v19 );
    CredFree(Credential);
    Credential = 0;
  }
  v20 = v28.CredentialBlobSize;
  v21 = v28.CredentialBlob;
  if ( v28.CredentialBlobSize )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  v22 = &v28;
  do
  {
    LOBYTE(v22->Flags) = 0;
    v22 = (struct _CREDENTIALW *)((char *)v22 + 1);
    --v9;
  }
  while ( v9 );
  if ( (unsigned int)CSecurity::EndRevertToSelf(hObject) )
  {
    v23 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 144LL))(a1);
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2554, L"2554", 0x54Fu, a1);
    v23 = 0;
  }
  RtlReleaseFastLockExclusive(&CConfigManager::s_lock);
  return v23;
}

```

## disassembly

```asm
0x18019d760  push    rbp
0x18019d762  push    rbx
0x18019d763  push    rsi
0x18019d764  push    rdi
0x18019d765  push    r12
0x18019d767  push    r13
0x18019d769  push    r14
0x18019d76b  push    r15
0x18019d76d  lea     rbp, [rsp-1Fh]
0x18019d772  sub     rsp, 0C8h
0x18019d779  mov     r12d, r9d
0x18019d77c  mov     r14, r8
0x18019d77f  mov     rdi, rdx
0x18019d782  mov     rbx, rcx
0x18019d785  xor     r13d, r13d
0x18019d788  test    rcx, rcx
0x18019d78b  jnz     short loc_18019D7B7
0x18019d78d  mov     [rsp+100h+var_E0], r13; struct IRequestContext *
0x18019d792  lea     r8, a2446; "2446"
0x18019d799  mov     edx, 98Eh; unsigned int
0x18019d79e  mov     r9d, 54Fh; unsigned int
0x18019d7a4  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019d7ab  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019d7b0  xor     eax, eax
0x18019d7b2  jmp     loc_18019DB2E
0x18019d7b7  test    rdi, rdi
0x18019d7ba  jnz     short loc_18019D7CF
0x18019d7bc  mov     [rsp+100h+var_E0], rbx
0x18019d7c1  lea     r8, a2447; "2447"
0x18019d7c8  mov     edx, 98Fh
0x18019d7cd  jmp     short loc_18019D79E
0x18019d7cf  test    r14, r14
0x18019d7d2  jnz     short loc_18019D7E7
0x18019d7d4  mov     [rsp+100h+var_E0], rbx
0x18019d7d9  lea     r8, a2448; "2448"
0x18019d7e0  mov     edx, 990h
0x18019d7e5  jmp     short loc_18019D79E
0x18019d7e7  mov     [rbp+57h+Credential], r13
0x18019d7eb  mov     r15d, 50h ; 'P'
0x18019d7f1  mov     r8d, r15d; Size
0x18019d7f4  xor     edx, edx; Val
0x18019d7f6  lea     rcx, [rbp+57h+var_A0]; void *
0x18019d7fa  call    memset_0
0x18019d7ff  xorps   xmm0, xmm0
0x18019d802  xor     eax, eax
0x18019d804  movups  [rbp+57h+var_C0], xmm0
0x18019d808  mov     [rbp+57h+var_B0], rax
0x18019d80c  lea     rax, WPP_GLOBAL_Control
0x18019d813  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d81a  cmp     rcx, rax
0x18019d81d  jz      short loc_18019D83C
0x18019d81f  test    dword ptr [rcx+1Ch], 200000h
0x18019d826  jz      short loc_18019D83C
0x18019d828  lea     edx, [r15+12h]
0x18019d82c  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d833  mov     rcx, [rcx+10h]
0x18019d837  call    WPP_SF_
0x18019d83c  lea     rsi, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019d843  mov     [rbp+57h+var_50], rsi
0x18019d847  mov     rcx, rsi
0x18019d84a  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x18019d850  test    eax, eax
0x18019d852  jnz     short loc_18019D85E
0x18019d854  mov     rcx, rsi
0x18019d857  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x18019d85d  nop
0x18019d85e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18019d862  mov     [rbp+57h+hObject], rsi
0x18019d866  lea     edx, [rsi+5]; DesiredAccess
0x18019d869  lea     rcx, [rbp+57h+hObject]; void **
0x18019d86d  call    ?BeginRevertToSelf@CSecurity@@SAHPEAPEAXK@Z; CSecurity::BeginRevertToSelf(void * *,ulong)
0x18019d872  test    eax, eax
0x18019d874  jnz     short loc_18019D8AC
0x18019d876  mov     [rsp+100h+var_E0], rbx; struct IRequestContext *
0x18019d87b  mov     r9d, 54Fh; unsigned int
0x18019d881  lea     r8, a2474; "2474"
0x18019d888  mov     edx, 9AAh; unsigned int
0x18019d88d  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019d894  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019d899  nop
0x18019d89a  lea     rcx, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019d8a1  call    cs:__imp_RtlReleaseFastLockExclusive
0x18019d8a7  jmp     loc_18019D7B0
0x18019d8ac  mov     [rbp+57h+arg_0], r13d
0x18019d8b0  xorps   xmm0, xmm0
0x18019d8b3  xor     eax, eax
0x18019d8b5  movups  [rbp+57h+var_C0], xmm0
0x18019d8b9  mov     [rbp+57h+var_B0], rax
0x18019d8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d8c4  lea     rax, WPP_GLOBAL_Control
0x18019d8cb  cmp     rcx, rax
0x18019d8ce  jz      short loc_18019D8FD
0x18019d8d0  test    dword ptr [rcx+1Ch], 200000h
0x18019d8d7  jz      short loc_18019D8FD
0x18019d8d9  mov     edx, 63h ; 'c'
0x18019d8de  lea     rax, Class
0x18019d8e5  mov     [rsp+100h+var_E0], rax
0x18019d8ea  mov     r9, rdi
0x18019d8ed  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d8f4  mov     rcx, [rcx+10h]
0x18019d8f8  call    WPP_SF_SS
0x18019d8fd  lea     r9, [rbp+57h+Credential]; Credential
0x18019d901  xor     r8d, r8d; Flags
0x18019d904  lea     edx, [r8+1]; Type
0x18019d908  mov     rcx, rdi; TargetName
0x18019d90b  call    cs:__imp_CredReadW
0x18019d911  test    eax, eax
0x18019d913  jz      short loc_18019D961
0x18019d915  mov     rax, [rbp+57h+Credential]
0x18019d919  mov     rcx, [rax+38h]
0x18019d91d  mov     rax, [rcx+10h]
0x18019d921  mov     r8d, [rax]
0x18019d924  mov     [rbp+57h+arg_0], r8d
0x18019d928  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d92f  lea     rax, WPP_GLOBAL_Control
0x18019d936  cmp     rcx, rax
0x18019d939  jz      short loc_18019D965
0x18019d93b  test    dword ptr [rcx+1Ch], 200000h
0x18019d942  jz      short loc_18019D965
0x18019d944  mov     edx, 64h ; 'd'
0x18019d949  mov     dword ptr [rsp+100h+var_E0], r8d
0x18019d94e  mov     r9, rdi
0x18019d951  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d958  mov     rcx, [rcx+10h]
0x18019d95c  call    WPP_SF_Sd
0x18019d961  mov     r8d, [rbp+57h+arg_0]
0x18019d965  test    r12d, r12d
0x18019d968  jnz     short loc_18019D97A
0x18019d96a  lea     eax, [r8+1]
0x18019d96e  cmp     eax, r8d
0x18019d971  jb      loc_18019DA44
0x18019d977  mov     [rbp+57h+arg_0], eax
0x18019d97a  mov     [rbp+57h+var_A0.Flags], r13d
0x18019d97e  mov     [rbp+57h+var_A0.Type], 1
0x18019d985  mov     [rbp+57h+var_A0.TargetName], rdi
0x18019d989  mov     [rbp+57h+var_A0.Comment], r13
0x18019d98d  inc     rsi
0x18019d990  cmp     [r14+rsi*2], r13w
0x18019d995  jnz     short loc_18019D98D
0x18019d997  lea     eax, ds:2[rsi*2]
0x18019d99e  mov     [rbp+57h+var_A0.CredentialBlobSize], eax
0x18019d9a1  mov     [rbp+57h+var_A0.CredentialBlob], r14
0x18019d9a5  mov     [rbp+57h+var_A0.Persist], 2
0x18019d9ac  mov     dword ptr [rbp+57h+var_C0+0Ch], 4
0x18019d9b3  lea     rax, [rbp+57h+arg_0]
0x18019d9b7  mov     [rbp+57h+var_B0], rax
0x18019d9bb  mov     qword ptr [rbp+57h+var_C0], rdi
0x18019d9bf  mov     [rbp+57h+var_A0.AttributeCount], 1
0x18019d9c6  lea     rax, [rbp+57h+var_C0]
0x18019d9ca  mov     [rbp+57h+var_A0.Attributes], rax
0x18019d9ce  xorps   xmm0, xmm0
0x18019d9d1  movdqa  xmmword ptr [rbp+57h+var_A0.TargetAlias], xmm0
0x18019d9d6  xor     edx, edx; Flags
0x18019d9d8  lea     rcx, [rbp+57h+var_A0]; Credential
0x18019d9dc  call    cs:__imp_CredWriteW
0x18019d9e2  test    eax, eax
0x18019d9e4  jnz     loc_18019DA6C
0x18019d9ea  mov     rax, cs:WPP_GLOBAL_Control
0x18019d9f1  lea     rcx, WPP_GLOBAL_Control
0x18019d9f8  cmp     rax, rcx
0x18019d9fb  jz      short loc_18019DA2B
0x18019d9fd  test    dword ptr [rax+1Ch], 400000h
0x18019da04  jz      short loc_18019DA2B
0x18019da06  call    cs:__imp_GetLastError
0x18019da0c  mov     edx, 65h ; 'e'
0x18019da11  mov     r9d, eax
0x18019da14  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019da1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18019da22  mov     rcx, [rcx+10h]
0x18019da26  call    WPP_SF_d
0x18019da2b  call    cs:__imp_GetLastError
0x18019da31  mov     rcx, [rbx]
0x18019da34  mov     rdi, [rcx+48h]
0x18019da38  cmp     eax, 8
0x18019da3b  jnz     short loc_18019DA59
0x18019da3d  mov     edx, 80338153h
0x18019da42  jmp     short loc_18019DA61
0x18019da44  mov     [rbp+57h+arg_0], 0FFFFFFFFh
0x18019da4b  mov     rax, [rbx]
0x18019da4e  mov     edx, 80338153h
0x18019da53  mov     rax, [rax+48h]
0x18019da57  jmp     short loc_18019DA64
0x18019da59  call    cs:__imp_GetLastError
0x18019da5f  mov     edx, eax
0x18019da61  mov     rax, rdi
0x18019da64  mov     rcx, rbx
0x18019da67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019da6c  mov     rax, [rbp+57h+Credential]
0x18019da70  test    rax, rax
0x18019da73  jz      short loc_18019DAAE
0x18019da75  mov     edx, [rax+20h]
0x18019da78  mov     rcx, [rax+28h]
0x18019da7c  test    rdx, rdx
0x18019da7f  jz      short loc_18019DA91
0x18019da81  mov     [rcx], r13b
0x18019da84  inc     rcx
0x18019da87  sub     rdx, 1
0x18019da8b  jnz     short loc_18019DA81
0x18019da8d  mov     rax, [rbp+57h+Credential]
0x18019da91  mov     rcx, r15
0x18019da94  mov     [rax], r13b
0x18019da97  inc     rax
0x18019da9a  sub     rcx, 1
0x18019da9e  jnz     short loc_18019DA94
0x18019daa0  mov     rcx, [rbp+57h+Credential]; Buffer
0x18019daa4  call    cs:__imp_CredFree
0x18019daaa  mov     [rbp+57h+Credential], r13
0x18019daae  mov     eax, [rbp+57h+var_A0.CredentialBlobSize]
0x18019dab1  mov     rcx, [rbp+57h+var_A0.CredentialBlob]
0x18019dab5  test    rax, rax
0x18019dab8  jz      short loc_18019DAC6
0x18019daba  mov     [rcx], r13b
0x18019dabd  inc     rcx
0x18019dac0  sub     rax, 1
0x18019dac4  jnz     short loc_18019DABA
0x18019dac6  lea     rax, [rbp+57h+var_A0]
0x18019daca  mov     [rax], r13b
0x18019dacd  inc     rax
0x18019dad0  sub     r15, 1
0x18019dad4  jnz     short loc_18019DACA
0x18019dad6  mov     rcx, [rbp+57h+hObject]; hObject
0x18019dada  call    ?EndRevertToSelf@CSecurity@@SAHPEAX@Z; CSecurity::EndRevertToSelf(void *)
0x18019dadf  test    eax, eax
0x18019dae1  jnz     short loc_18019DB0B
0x18019dae3  mov     [rsp+100h+var_E0], rbx; struct IRequestContext *
0x18019dae8  mov     r9d, 54Fh; unsigned int
0x18019daee  lea     r8, a2554; "2554"
0x18019daf5  mov     edx, 9FAh; unsigned int
0x18019dafa  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019db01  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019db06  mov     ebx, r13d
0x18019db09  jmp     short loc_18019DB1F
0x18019db0b  mov     rax, [rbx]
0x18019db0e  mov     rcx, rbx
0x18019db11  mov     rax, [rax+90h]
0x18019db18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019db1d  mov     ebx, eax
0x18019db1f  lea     rcx, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019db26  call    cs:__imp_RtlReleaseFastLockExclusive
0x18019db2c  mov     eax, ebx
0x18019db2e  add     rsp, 0C8h
0x18019db35  pop     r15
0x18019db37  pop     r14
0x18019db39  pop     r13
0x18019db3b  pop     r12
0x18019db3d  pop     rdi
0x18019db3e  pop     rsi
0x18019db3f  pop     rbx
0x18019db40  pop     rbp
0x18019db41  retn
```

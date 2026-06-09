# CConfigManager::ReadCredentialsFromCredmanStore(IRequestContext *,ushort *,ushort *)

- ea: `0x18019d1e0`
- end: `0x18019d45e`
- name: `?ReadCredentialsFromCredmanStore@CConfigManager@@SAHPEAVIRequestContext@@PEAG1@Z`
- size: `638`
- prototype: `__int64 __fastcall(struct IRequestContext *, LPCWSTR TargetName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801a4894`

## callees

- `0x180005d10`
- `0x18005d800`
- `0x1800fe3b0`
- `0x1800fe7a0`
- `0x18010d8c6`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18019d1e0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019d375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019d375`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019d298`
- `miutils!RtlTryAcquireFastLockExclusive` at `0x18019d298`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019d2a9`
- `miutils!RtlQueueAcquireFastLockExclusive` at `0x18019d2a9`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019d44b`
- `miutils!RtlReleaseFastLockExclusive` at `0x18019d44b`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019d3e8`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18019d3e8`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019d325`
- `api-ms-win-security-credentials-l1-1-0!CredReadW` at `0x18019d325`

## string_xrefs

- `0x18019d21e`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019d2d9`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019d424`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConfigManager::ReadCredentialsFromCredmanStore(
        struct IRequestContext *a1,
        LPCWSTR TargetName,
        unsigned __int16 *a3)
{
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  PCREDENTIALW v9; // rbx
  DWORD LastError; // eax
  __int64 CredentialBlobSize; // rcx
  LPBYTE CredentialBlob; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  PCREDENTIALW Credential; // [rsp+60h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+40h] BYREF
  __int64 *v17; // [rsp+78h] [rbp+48h]

  if ( a3 )
    *a3 = 0;
  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2564, L"2564", 0x54Fu, 0);
    return 0;
  }
  if ( !TargetName )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2565, L"2565", 0x54Fu, a1);
    return 0;
  }
  Credential = 0;
  hObject = (HANDLE)-1LL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
  v17 = &CConfigManager::s_lock;
  if ( !(unsigned int)RtlTryAcquireFastLockExclusive(&CConfigManager::s_lock) )
    RtlQueueAcquireFastLockExclusive(&CConfigManager::s_lock);
  if ( !(unsigned int)CSecurity::BeginRevertToSelf(&hObject, 4u) )
  {
    v7 = L"2587";
    v8 = 2587;
LABEL_15:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", v8, v7, 0x54Fu, a1);
LABEL_27:
    v9 = Credential;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, TargetName);
  if ( !CredReadW(TargetName, 1u, 0, &Credential) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, LastError);
    }
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 2150859262LL);
    goto LABEL_27;
  }
  v9 = Credential;
  if ( (Credential->CredentialBlobSize & 0xFFFFFFFE) >= 0x5000 )
  {
    v7 = L"2595";
    v8 = 2595;
    goto LABEL_15;
  }
  memcpy_0(a3, Credential->CredentialBlob, Credential->CredentialBlobSize);
LABEL_28:
  if ( v9 )
  {
    CredentialBlobSize = v9->CredentialBlobSize;
    CredentialBlob = v9->CredentialBlob;
    if ( v9->CredentialBlobSize )
    {
      do
      {
        *CredentialBlob++ = 0;
        --CredentialBlobSize;
      }
      while ( CredentialBlobSize );
      v9 = Credential;
    }
    v13 = 80;
    do
    {
      LOBYTE(v9->Flags) = 0;
      v9 = (PCREDENTIALW)((char *)v9 + 1);
      --v13;
    }
    while ( v13 );
    CredFree(Credential);
    Credential = 0;
  }
  WSManMemory::Free(0, 0);
  if ( !(unsigned int)CSecurity::EndRevertToSelf(hObject) )
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 2620, L"2620", 0x54Fu, a1);
  v14 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 144LL))(a1);
  RtlReleaseFastLockExclusive(&CConfigManager::s_lock);
  return v14;
}

```

## disassembly

```asm
0x18019d1e0  push    rbp
0x18019d1e2  push    rbx
0x18019d1e3  push    rsi
0x18019d1e4  push    rdi
0x18019d1e5  push    r15
0x18019d1e7  mov     rbp, rsp
0x18019d1ea  sub     rsp, 30h
0x18019d1ee  mov     rsi, r8
0x18019d1f1  mov     rbx, rdx
0x18019d1f4  mov     rdi, rcx
0x18019d1f7  test    r8, r8
0x18019d1fa  jz      short loc_18019D202
0x18019d1fc  xor     eax, eax
0x18019d1fe  mov     [r8], ax
0x18019d202  test    rdi, rdi
0x18019d205  jnz     short loc_18019D231
0x18019d207  mov     [rsp+30h+var_10], rdi; struct IRequestContext *
0x18019d20c  lea     r8, a2564; "2564"
0x18019d213  mov     edx, 0A04h; unsigned int
0x18019d218  mov     r9d, 54Fh; unsigned int
0x18019d21e  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019d225  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019d22a  xor     eax, eax
0x18019d22c  jmp     loc_18019D453
0x18019d231  test    rbx, rbx
0x18019d234  jnz     short loc_18019D249
0x18019d236  mov     [rsp+30h+var_10], rdi
0x18019d23b  lea     r8, a2565; "2565"
0x18019d242  mov     edx, 0A05h
0x18019d247  jmp     short loc_18019D218
0x18019d249  mov     [rbp+Credential], 0
0x18019d251  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18019d259  lea     r15, WPP_GLOBAL_Control
0x18019d260  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d267  cmp     rcx, r15
0x18019d26a  jz      short loc_18019D28A
0x18019d26c  test    dword ptr [rcx+1Ch], 200000h
0x18019d273  jz      short loc_18019D28A
0x18019d275  mov     edx, 67h ; 'g'
0x18019d27a  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d281  mov     rcx, [rcx+10h]
0x18019d285  call    WPP_SF_
0x18019d28a  lea     rax, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019d291  mov     [rbp+arg_18], rax
0x18019d295  mov     rcx, rax
0x18019d298  call    cs:__imp_RtlTryAcquireFastLockExclusive
0x18019d29e  test    eax, eax
0x18019d2a0  jnz     short loc_18019D2B0
0x18019d2a2  lea     rcx, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019d2a9  call    cs:__imp_RtlQueueAcquireFastLockExclusive
0x18019d2af  nop
0x18019d2b0  mov     edx, 4; DesiredAccess
0x18019d2b5  lea     rcx, [rbp+hObject]; void **
0x18019d2b9  call    ?BeginRevertToSelf@CSecurity@@SAHPEAPEAXK@Z; CSecurity::BeginRevertToSelf(void * *,ulong)
0x18019d2be  test    eax, eax
0x18019d2c0  jnz     short loc_18019D2EA
0x18019d2c2  lea     r8, a2587; "2587"
0x18019d2c9  mov     edx, 0A1Bh; unsigned int
0x18019d2ce  mov     r9d, 54Fh; unsigned int
0x18019d2d4  mov     [rsp+30h+var_10], rdi; struct IRequestContext *
0x18019d2d9  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019d2e0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019d2e5  jmp     loc_18019D3AE
0x18019d2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d2f1  cmp     rcx, r15
0x18019d2f4  jz      short loc_18019D317
0x18019d2f6  test    dword ptr [rcx+1Ch], 200000h
0x18019d2fd  jz      short loc_18019D317
0x18019d2ff  mov     edx, 68h ; 'h'
0x18019d304  mov     r9, rbx
0x18019d307  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d30e  mov     rcx, [rcx+10h]
0x18019d312  call    WPP_SF_S
0x18019d317  lea     r9, [rbp+Credential]; Credential
0x18019d31b  xor     r8d, r8d; Flags
0x18019d31e  lea     edx, [r8+1]; Type
0x18019d322  mov     rcx, rbx; TargetName
0x18019d325  call    cs:__imp_CredReadW
0x18019d32b  test    eax, eax
0x18019d32d  jz      short loc_18019D360
0x18019d32f  mov     rbx, [rbp+Credential]
0x18019d333  mov     eax, [rbx+20h]
0x18019d336  and     eax, 0FFFFFFFEh
0x18019d339  cmp     eax, 5000h
0x18019d33e  jb      short loc_18019D34E
0x18019d340  lea     r8, a2595; "2595"
0x18019d347  mov     edx, 0A23h
0x18019d34c  jmp     short loc_18019D2CE
0x18019d34e  mov     r8d, [rbx+20h]; Size
0x18019d352  mov     rdx, [rbx+28h]; Src
0x18019d356  mov     rcx, rsi; void *
0x18019d359  call    memcpy_0
0x18019d35e  jmp     short loc_18019D3B2
0x18019d360  mov     rax, cs:WPP_GLOBAL_Control
0x18019d367  cmp     rax, r15
0x18019d36a  jz      short loc_18019D39A
0x18019d36c  test    dword ptr [rax+1Ch], 800h
0x18019d373  jz      short loc_18019D39A
0x18019d375  call    cs:__imp_GetLastError
0x18019d37b  mov     edx, 69h ; 'i'
0x18019d380  mov     r9d, eax
0x18019d383  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019d38a  mov     rcx, cs:WPP_GLOBAL_Control
0x18019d391  mov     rcx, [rcx+10h]
0x18019d395  call    WPP_SF_d
0x18019d39a  mov     rax, [rdi]
0x18019d39d  mov     edx, 803381FEh
0x18019d3a2  mov     rcx, rdi
0x18019d3a5  mov     rax, [rax+48h]
0x18019d3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d3ae  mov     rbx, [rbp+Credential]
0x18019d3b2  test    rbx, rbx
0x18019d3b5  jz      short loc_18019D3F6
0x18019d3b7  mov     ecx, [rbx+20h]
0x18019d3ba  mov     rax, [rbx+28h]
0x18019d3be  test    rcx, rcx
0x18019d3c1  jz      short loc_18019D3D3
0x18019d3c3  mov     byte ptr [rax], 0
0x18019d3c6  inc     rax
0x18019d3c9  sub     rcx, 1
0x18019d3cd  jnz     short loc_18019D3C3
0x18019d3cf  mov     rbx, [rbp+Credential]
0x18019d3d3  mov     eax, 50h ; 'P'
0x18019d3d8  mov     byte ptr [rbx], 0
0x18019d3db  inc     rbx
0x18019d3de  sub     rax, 1
0x18019d3e2  jnz     short loc_18019D3D8
0x18019d3e4  mov     rcx, [rbp+Credential]; Buffer
0x18019d3e8  call    cs:__imp_CredFree
0x18019d3ee  mov     [rbp+Credential], 0
0x18019d3f6  xor     edx, edx; int
0x18019d3f8  xor     ecx, ecx; void *
0x18019d3fa  call    ?Free@WSManMemory@@SAXPEAXH@Z; WSManMemory::Free(void *,int)
0x18019d3ff  nop
0x18019d400  mov     rcx, [rbp+hObject]; hObject
0x18019d404  call    ?EndRevertToSelf@CSecurity@@SAHPEAX@Z; CSecurity::EndRevertToSelf(void *)
0x18019d409  test    eax, eax
0x18019d40b  jnz     short loc_18019D430
0x18019d40d  mov     [rsp+30h+var_10], rdi; struct IRequestContext *
0x18019d412  mov     r9d, 54Fh; unsigned int
0x18019d418  lea     r8, a2620; "2620"
0x18019d41f  mov     edx, 0A3Ch; unsigned int
0x18019d424  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019d42b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019d430  mov     rax, [rdi]
0x18019d433  mov     rcx, rdi
0x18019d436  mov     rax, [rax+90h]
0x18019d43d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019d442  mov     ebx, eax
0x18019d444  lea     rcx, ?s_lock@CConfigManager@@0VFastLock@@A; FastLock CConfigManager::s_lock
0x18019d44b  call    cs:__imp_RtlReleaseFastLockExclusive
0x18019d451  mov     eax, ebx
0x18019d453  add     rsp, 30h
0x18019d457  pop     r15
0x18019d459  pop     rdi
0x18019d45a  pop     rsi
0x18019d45b  pop     rbx
0x18019d45c  pop     rbp
0x18019d45d  retn
```

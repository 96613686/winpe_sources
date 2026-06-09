# VaultInitialize(HINSTANCE__ *,ushort const *)

- ea: `0x1800021e8`
- end: `0x180002404`
- name: `?VaultInitialize@@YAKPEAUHINSTANCE__@@PEBG@Z`
- size: `540`
- prototype: `unsigned int(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001aa0`

## callees

- `0x180001710`
- `0x180001970`
- `0x180001a50`
- `0x1800021e8`
- `0x180002b4c`
- `0x180003fb0`
- `0x18000c664`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800023ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800023ba`
- `LSASRV!LsaIRegisterLogonSessionCallback` at `0x18000231e`
- `LSASRV!LsaIRegisterLogonSessionCallback` at `0x18000231e`
- `ntdll!RtlNtStatusToDosError` at `0x18000232a`
- `ntdll!RtlNtStatusToDosError` at `0x180002379`
- `ntdll!RtlNtStatusToDosError` at `0x18000232a`
- `ntdll!RtlNtStatusToDosError` at `0x180002379`

## pseudocode

```c
__int64 __fastcall VaultInitialize(HINSTANCE a1, const unsigned __int16 *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // edi
  VaultCryptoGlobals *v6; // rcx
  unsigned int GlobalSchemaVault; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  CVaultMgr *v10; // rcx
  CVaultGlobalSchemaMgr *v11; // rcx
  NTSTATUS v12; // eax
  NTSTATUS v13; // eax

  v3 = DuplicateString(a2, &VaultGlobals::g_pszDefaultVaultName);
  VaultGlobals::g_hModuleHandle = a1;
  v4 = v3;
  if ( !v3 )
  {
    GlobalSchemaVault = VaultEnableSinglePrivilege();
    if ( GlobalSchemaVault )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return GlobalSchemaVault;
      v9 = 16;
    }
    else
    {
      GlobalSchemaVault = VaultCryptoGlobals::InitializeCrypto(v6);
      if ( GlobalSchemaVault )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return GlobalSchemaVault;
        v9 = 17;
      }
      else
      {
        GlobalSchemaVault = CVaultMgr::Initialize(v10);
        if ( GlobalSchemaVault )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            return GlobalSchemaVault;
          v9 = 18;
        }
        else
        {
          GlobalSchemaVault = CVaultGlobalSchemaMgr::LoadGlobalSchemaVault(v11);
          if ( GlobalSchemaVault )
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              return GlobalSchemaVault;
            v9 = 19;
          }
          else
          {
            v12 = LsaIRegisterLogonSessionCallback(VaultLogonSessionNotification);
            if ( v12 >= 0 )
            {
              VaultGlobals::g_fRegisteredLogonSessCallback = 1;
              VaultGlobals::g_eEngineState = 2;
              v13 = InitializeDomainStatus();
              if ( v13 >= 0 )
              {
                if ( ConvertStringSidToSidW(
                       L"S-1-15-3-1024-3826530540-457977918-831996869-4121746106-3747742610-578447321-1227403828-2925310924",
                       &VaultGlobals::g_PrivAppSID) )
                {
                  return 0;
                }
                GlobalSchemaVault = GetLastError();
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  return GlobalSchemaVault;
                v9 = 22;
              }
              else
              {
                GlobalSchemaVault = RtlNtStatusToDosError(v13);
                v8 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                  return GlobalSchemaVault;
                v9 = 21;
              }
            }
            else
            {
              GlobalSchemaVault = RtlNtStatusToDosError(v12);
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                return GlobalSchemaVault;
              v9 = 20;
            }
          }
        }
      }
    }
    WPP_SF_d(v8[2], v9, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, GlobalSchemaVault);
    return GlobalSchemaVault;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids, v3);
  return v4;
}

```

## disassembly

```asm
0x1800021e8  mov     [rsp+arg_0], rbx
0x1800021ed  push    rdi
0x1800021ee  sub     rsp, 20h
0x1800021f2  mov     rax, rdx
0x1800021f5  mov     rbx, rcx
0x1800021f8  mov     rcx, rax; unsigned __int16 *
0x1800021fb  lea     rdx, ?g_pszDefaultVaultName@VaultGlobals@@3PEBGEB; unsigned __int16 **
0x180002202  call    ?DuplicateString@@YAKPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180002207  mov     cs:?g_hModuleHandle@VaultGlobals@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * VaultGlobals::g_hModuleHandle
0x18000220e  mov     edi, eax
0x180002210  test    eax, eax
0x180002212  jz      short loc_18000224C
0x180002214  mov     rcx, cs:WPP_GLOBAL_Control
0x18000221b  lea     rdx, WPP_GLOBAL_Control
0x180002222  cmp     rcx, rdx
0x180002225  jz      short loc_180002245
0x180002227  test    byte ptr [rcx+1Ch], 2
0x18000222b  jz      short loc_180002245
0x18000222d  mov     rcx, [rcx+10h]
0x180002231  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180002238  mov     edx, 0Fh
0x18000223d  mov     r9d, eax
0x180002240  call    WPP_SF_d
0x180002245  mov     eax, edi
0x180002247  jmp     loc_1800023F9
0x18000224c  call    ?VaultEnableSinglePrivilege@@YAKJ@Z; VaultEnableSinglePrivilege(long)
0x180002251  mov     ebx, eax
0x180002253  test    eax, eax
0x180002255  jz      short loc_18000228F
0x180002257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000225e  lea     rdx, WPP_GLOBAL_Control
0x180002265  cmp     rcx, rdx
0x180002268  jz      short loc_180002288
0x18000226a  test    byte ptr [rcx+1Ch], 2
0x18000226e  jz      short loc_180002288
0x180002270  mov     edx, 10h
0x180002275  mov     rcx, [rcx+10h]
0x180002279  lea     r8, WPP_df576fef64e13af7ed0e333d0abd1cdb_Traceguids
0x180002280  mov     r9d, ebx
0x180002283  call    WPP_SF_d
0x180002288  mov     eax, ebx
0x18000228a  jmp     loc_1800023F9
0x18000228f  call    ?InitializeCrypto@VaultCryptoGlobals@@YAKXZ; VaultCryptoGlobals::InitializeCrypto(void)
0x180002294  mov     ebx, eax
0x180002296  test    eax, eax
0x180002298  jz      short loc_1800022BA
0x18000229a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022a1  lea     rdx, WPP_GLOBAL_Control
0x1800022a8  cmp     rcx, rdx
0x1800022ab  jz      short loc_180002288
0x1800022ad  test    byte ptr [rcx+1Ch], 2
0x1800022b1  jz      short loc_180002288
0x1800022b3  mov     edx, 11h
0x1800022b8  jmp     short loc_180002275
0x1800022ba  call    ?Initialize@CVaultMgr@@QEAAKXZ; CVaultMgr::Initialize(void)
0x1800022bf  mov     ebx, eax
0x1800022c1  test    eax, eax
0x1800022c3  jz      short loc_1800022E5
0x1800022c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022cc  lea     rdx, WPP_GLOBAL_Control
0x1800022d3  cmp     rcx, rdx
0x1800022d6  jz      short loc_180002288
0x1800022d8  test    byte ptr [rcx+1Ch], 2
0x1800022dc  jz      short loc_180002288
0x1800022de  mov     edx, 12h
0x1800022e3  jmp     short loc_180002275
0x1800022e5  call    ?LoadGlobalSchemaVault@CVaultGlobalSchemaMgr@@QEAAKXZ; CVaultGlobalSchemaMgr::LoadGlobalSchemaVault(void)
0x1800022ea  mov     ebx, eax
0x1800022ec  test    eax, eax
0x1800022ee  jz      short loc_180002317
0x1800022f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022f7  lea     rdx, WPP_GLOBAL_Control
0x1800022fe  cmp     rcx, rdx
0x180002301  jz      short loc_180002288
0x180002303  test    byte ptr [rcx+1Ch], 2
0x180002307  jz      loc_180002288
0x18000230d  mov     edx, 13h
0x180002312  jmp     loc_180002275
0x180002317  lea     rcx, ?VaultLogonSessionNotification@@YAKPEAU_LSAP_LOGON_SESSION_NOTIFICATION@@@Z; VaultLogonSessionNotification(_LSAP_LOGON_SESSION_NOTIFICATION *)
0x18000231e  call    cs:__imp_LsaIRegisterLogonSessionCallback
0x180002324  test    eax, eax
0x180002326  jns     short loc_18000235D
0x180002328  mov     ecx, eax; Status
0x18000232a  call    cs:__imp_RtlNtStatusToDosError
0x180002330  mov     ebx, eax
0x180002332  mov     rcx, cs:WPP_GLOBAL_Control
0x180002339  lea     rdx, WPP_GLOBAL_Control
0x180002340  cmp     rcx, rdx
0x180002343  jz      loc_180002288
0x180002349  test    byte ptr [rcx+1Ch], 2
0x18000234d  jz      loc_180002288
0x180002353  mov     edx, 14h
0x180002358  jmp     loc_180002275
0x18000235d  mov     cs:?g_fRegisteredLogonSessCallback@VaultGlobals@@3EA, 1; uchar VaultGlobals::g_fRegisteredLogonSessCallback
0x180002364  mov     cs:?g_eEngineState@VaultGlobals@@3W4eVaultEngineState@@A, 2; eVaultEngineState VaultGlobals::g_eEngineState
0x18000236e  call    ?InitializeDomainStatus@@YAJXZ; InitializeDomainStatus(void)
0x180002373  test    eax, eax
0x180002375  jns     short loc_1800023AC
0x180002377  mov     ecx, eax; Status
0x180002379  call    cs:__imp_RtlNtStatusToDosError
0x18000237f  mov     ebx, eax
0x180002381  mov     rcx, cs:WPP_GLOBAL_Control
0x180002388  lea     rdx, WPP_GLOBAL_Control
0x18000238f  cmp     rcx, rdx
0x180002392  jz      loc_180002288
0x180002398  test    byte ptr [rcx+1Ch], 2
0x18000239c  jz      loc_180002288
0x1800023a2  mov     edx, 15h
0x1800023a7  jmp     loc_180002275
0x1800023ac  lea     rdx, ?g_PrivAppSID@VaultGlobals@@3PEAXEA; Sid
0x1800023b3  lea     rcx, StringSid; "S-1-15-3-1024-3826530540-457977918-8319"...
0x1800023ba  call    cs:__imp_ConvertStringSidToSidW
0x1800023c0  test    eax, eax
0x1800023c2  jnz     short loc_1800023F7
0x1800023c4  call    cs:__imp_GetLastError
0x1800023ca  mov     ebx, eax
0x1800023cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023d3  lea     rdx, WPP_GLOBAL_Control
0x1800023da  cmp     rcx, rdx
0x1800023dd  jz      loc_180002288
0x1800023e3  test    byte ptr [rcx+1Ch], 2
0x1800023e7  jz      loc_180002288
0x1800023ed  mov     edx, 16h
0x1800023f2  jmp     loc_180002275
0x1800023f7  xor     eax, eax
0x1800023f9  mov     rbx, [rsp+28h+arg_0]
0x1800023fe  add     rsp, 20h
0x180002402  pop     rdi
0x180002403  retn
```

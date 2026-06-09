# CMigrationPlugin::raw_PostApply(IMigrationContext *)

- ea: `0x1800149a0`
- end: `0x180014be9`
- name: `?raw_PostApply@CMigrationPlugin@@UEAAJPEAUIMigrationContext@@@Z`
- size: `585`
- prototype: `__int64 __fastcall(CMigrationPlugin *this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800026f0`
- `0x18000c490`
- `0x18000c590`
- `0x18000dec0`
- `0x1800105b4`
- `0x180010774`
- `0x1800109a8`
- `0x180010a58`
- `0x180011220`
- `0x180011678`
- `0x1800124d8`
- `0x1800127e0`
- `0x180013c50`
- `0x1800149a0`
- `0x180015358`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014b6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014b6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014b3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014b3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014b76`

## string_xrefs

- `0x180014a48`: `WSMIG - IcsFilterReplaced: TRUE`
- `0x180014a3f`: `WSMIG - IsIcsFilterReplaced: FALSE`
- `0x180014a65`: `WSMIG - DiacriticsUpdated: TRUE`
- `0x180014a5b`: `WSMIG - DiacriticsUpdated: FALSE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMigrationPlugin::raw_PostApply(CMigrationPlugin *this, struct IUnknown *a2)
{
  struct IUnknown v2; // rax
  int v4; // eax
  const struct _GUID *v5; // r8
  char v6; // bl
  struct IMigrationContext *v7; // rdx
  char v8; // r14
  char v9; // si
  const wchar_t *v10; // rdx
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rdx
  struct IUnknown v13; // rax
  int v14; // eax
  const struct _GUID *v15; // r8
  _WORD v17[2]; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v19[3]; // [rsp+35h] [rbp-CBh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2.lpVtbl = a2->lpVtbl;
  v17[0] = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, _WORD *))v2.lpVtbl[6].AddRef)(a2, v17);
  if ( v4 < 0 )
    _com_issue_errorex(v4, a2, v5);
  if ( !v17[0] )
    StopWSearch();
  *(_DWORD *)Data = 0;
  if ( (unsigned __int8)IsInUpgrade(a2) )
  {
    LOBYTE(v17[0]) = IsIcsFilterReplaced();
    v6 = v17[0];
    v19[0] = DiacriticsInspection::IsUpdated(a2, v7);
    v8 = v19[0];
    v9 = IsDataMigrationEligible(a2);
    v18 = v9;
    v10 = L"WSMIG - IcsFilterReplaced: TRUE";
    if ( !v6 )
      v10 = L"WSMIG - IsIcsFilterReplaced: FALSE";
    WSMigLog(a2, v10);
    v11 = L"WSMIG - DiacriticsUpdated: TRUE";
    if ( !v8 )
      v11 = L"WSMIG - DiacriticsUpdated: FALSE";
    WSMigLog(a2, v11);
    v12 = L"WSMIG - DataMigrationEligible: TRUE";
    if ( !v9 )
      v12 = L"WSMIG - DataMigrationEligible: FALSE";
    WSMigLog(a2, v12);
    SearchIndexerDiagnosticTelemetry::Migration_PostApplyUpgrade<bool &,bool &,bool &>(v17, v19, &v18);
    if ( v6 || v8 || !v9 )
    {
      WSMigLog(a2, L"WSMIG - Index Reset For Upgrade");
      *(_DWORD *)Data = 6;
      SearchIndexerDiagnosticTelemetry::Rebuild<bool &,bool &,bool &>(v17, v19, &v18);
    }
  }
  else
  {
    WSMigLog(a2, L"WSMIG - Index Reset For Migration");
    *(_DWORD *)Data = 7;
    SearchIndexerDiagnosticTelemetry::Migration_PostApplyMigrate();
  }
  if ( *(_DWORD *)Data )
  {
    hKey = 0;
    MapRegKeyPathIfNeeded(a2, (OLECHAR *)L"SOFTWARE\\Microsoft\\Windows Search");
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x40000000u, &hKey) )
    {
      RegSetValueExW(hKey, L"RebuildIndex", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
  }
  v13.lpVtbl = a2->lpVtbl;
  v17[0] = 0;
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, _WORD *))v13.lpVtbl[6].AddRef)(a2, v17);
  if ( v14 < 0 )
    _com_issue_errorex(v14, a2, v15);
  if ( !v17[0] )
  {
    StartWSearch();
    DestroyWSearchIdleObject(a2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800149a0  push    rbp
0x1800149a2  push    rbx
0x1800149a3  push    rsi
0x1800149a4  push    rdi
0x1800149a5  push    r14
0x1800149a7  push    r15
0x1800149a9  lea     rbp, [rsp-178h]
0x1800149b1  sub     rsp, 278h
0x1800149b8  mov     rax, cs:__security_cookie
0x1800149bf  xor     rax, rsp
0x1800149c2  mov     [rbp+1A0h+var_40], rax
0x1800149c9  mov     rax, [rdx]
0x1800149cc  mov     rdi, rdx
0x1800149cf  xor     r15d, r15d
0x1800149d2  lea     rdx, [rsp+2A0h+var_270]
0x1800149d7  mov     rcx, rdi
0x1800149da  mov     [rsp+2A0h+var_270], r15w
0x1800149e0  mov     rax, [rax+98h]
0x1800149e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ec  test    eax, eax
0x1800149ee  js      loc_180014BD3
0x1800149f4  cmp     [rsp+2A0h+var_270], r15w
0x1800149fa  jnz     short loc_180014A01
0x1800149fc  call    StopWSearch
0x180014a01  mov     rcx, rdi
0x180014a04  mov     dword ptr [rsp+2A0h+Data], r15d
0x180014a09  call    IsInUpgrade
0x180014a0e  test    al, al
0x180014a10  jz      loc_180014AE4
0x180014a16  call    IsIcsFilterReplaced
0x180014a1b  mov     rcx, rdi; this
0x180014a1e  mov     byte ptr [rsp+2A0h+var_270], al
0x180014a22  mov     bl, al
0x180014a24  call    ?IsUpdated@DiacriticsInspection@@YA_NPEAUIMigrationContext@@@Z; DiacriticsInspection::IsUpdated(IMigrationContext *)
0x180014a29  mov     rcx, rdi
0x180014a2c  mov     [rsp+2A0h+var_26B], al
0x180014a30  mov     r14b, al
0x180014a33  call    IsDataMigrationEligible
0x180014a38  mov     sil, al
0x180014a3b  mov     [rsp+2A0h+var_26C], al
0x180014a3f  lea     rax, aWsmigIsicsfilt; "WSMIG - IsIcsFilterReplaced: FALSE"
0x180014a46  test    bl, bl
0x180014a48  lea     rdx, aWsmigIcsfilter; "WSMIG - IcsFilterReplaced: TRUE"
0x180014a4f  mov     rcx, rdi
0x180014a52  cmovz   rdx, rax
0x180014a56  call    WSMigLog
0x180014a5b  lea     rax, aWsmigDiacritic_0; "WSMIG - DiacriticsUpdated: FALSE"
0x180014a62  test    r14b, r14b
0x180014a65  lea     rdx, aWsmigDiacritic; "WSMIG - DiacriticsUpdated: TRUE"
0x180014a6c  mov     rcx, rdi
0x180014a6f  cmovz   rdx, rax
0x180014a73  call    WSMigLog
0x180014a78  lea     rax, aWsmigDatamigra_0; "WSMIG - DataMigrationEligible: FALSE"
0x180014a7f  test    sil, sil
0x180014a82  lea     rdx, aWsmigDatamigra; "WSMIG - DataMigrationEligible: TRUE"
0x180014a89  mov     rcx, rdi
0x180014a8c  cmovz   rdx, rax
0x180014a90  call    WSMigLog
0x180014a95  lea     r8, [rsp+2A0h+var_26C]
0x180014a9a  lea     rdx, [rsp+2A0h+var_26B]
0x180014a9f  lea     rcx, [rsp+2A0h+var_270]
0x180014aa4  call    ??$Migration_PostApplyUpgrade@AEA_NAEA_NAEA_N@SearchIndexerDiagnosticTelemetry@@SAXAEA_N00@Z; SearchIndexerDiagnosticTelemetry::Migration_PostApplyUpgrade<bool &,bool &,bool &>(bool &,bool &,bool &)
0x180014aa9  test    bl, bl
0x180014aab  jnz     short loc_180014AB7
0x180014aad  test    r14b, r14b
0x180014ab0  jnz     short loc_180014AB7
0x180014ab2  test    sil, sil
0x180014ab5  jnz     short loc_180014B00
0x180014ab7  lea     rdx, aWsmigIndexRese; "WSMIG - Index Reset For Upgrade"
0x180014abe  mov     rcx, rdi
0x180014ac1  call    WSMigLog
0x180014ac6  lea     r8, [rsp+2A0h+var_26C]
0x180014acb  mov     dword ptr [rsp+2A0h+Data], 6
0x180014ad3  lea     rdx, [rsp+2A0h+var_26B]
0x180014ad8  lea     rcx, [rsp+2A0h+var_270]
0x180014add  call    ??$Rebuild@AEA_NAEA_NAEA_N@SearchIndexerDiagnosticTelemetry@@SAXAEA_N00@Z; SearchIndexerDiagnosticTelemetry::Rebuild<bool &,bool &,bool &>(bool &,bool &,bool &)
0x180014ae2  jmp     short loc_180014B00
0x180014ae4  lea     rdx, aWsmigIndexRese_0; "WSMIG - Index Reset For Migration"
0x180014aeb  mov     rcx, rdi
0x180014aee  call    WSMigLog
0x180014af3  mov     dword ptr [rsp+2A0h+Data], 7
0x180014afb  call    ?Migration_PostApplyMigrate@SearchIndexerDiagnosticTelemetry@@SAXXZ; SearchIndexerDiagnosticTelemetry::Migration_PostApplyMigrate(void)
0x180014b00  cmp     dword ptr [rsp+2A0h+Data], r15d
0x180014b05  jz      short loc_180014B7C
0x180014b07  lea     r8, [rsp+2A0h+SubKey]
0x180014b0c  mov     [rsp+2A0h+hKey], r15
0x180014b11  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Search"
0x180014b18  mov     rcx, rdi; struct IUnknown *
0x180014b1b  call    MapRegKeyPathIfNeeded
0x180014b20  lea     rax, [rsp+2A0h+hKey]
0x180014b25  mov     r9d, 40000000h; samDesired
0x180014b2b  xor     r8d, r8d; ulOptions
0x180014b2e  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180014b33  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180014b38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014b3f  call    cs:__imp_RegOpenKeyExW
0x180014b45  test    eax, eax
0x180014b47  jnz     short loc_180014B7C
0x180014b49  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180014b4e  lea     r9d, [rax+4]; dwType
0x180014b52  lea     rax, [rsp+2A0h+Data]
0x180014b57  mov     [rsp+2A0h+cbData], r9d; cbData
0x180014b5c  xor     r8d, r8d; Reserved
0x180014b5f  mov     [rsp+2A0h+phkResult], rax; lpData
0x180014b64  lea     rdx, aRebuildindex; "RebuildIndex"
0x180014b6b  call    cs:__imp_RegSetValueExW
0x180014b71  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180014b76  call    cs:__imp_RegCloseKey
0x180014b7c  mov     rax, [rdi]
0x180014b7f  lea     rdx, [rsp+2A0h+var_270]
0x180014b84  mov     rcx, rdi
0x180014b87  mov     [rsp+2A0h+var_270], r15w
0x180014b8d  mov     rax, [rax+98h]
0x180014b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b99  test    eax, eax
0x180014b9b  js      short loc_180014BDE
0x180014b9d  cmp     [rsp+2A0h+var_270], r15w
0x180014ba3  jnz     short loc_180014BB2
0x180014ba5  call    StartWSearch
0x180014baa  mov     rcx, rdi
0x180014bad  call    DestroyWSearchIdleObject
0x180014bb2  xor     eax, eax
0x180014bb4  mov     rcx, [rbp+1A0h+var_40]
0x180014bbb  xor     rcx, rsp; StackCookie
0x180014bbe  call    __security_check_cookie
0x180014bc3  add     rsp, 278h
0x180014bca  pop     r15
0x180014bcc  pop     r14
0x180014bce  pop     rdi
0x180014bcf  pop     rsi
0x180014bd0  pop     rbx
0x180014bd1  pop     rbp
0x180014bd2  retn
0x180014bd3  mov     rdx, rdi; struct IUnknown *
0x180014bd6  mov     ecx, eax; int
0x180014bd8  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180014bde  mov     rdx, rdi; struct IUnknown *
0x180014be1  mov     ecx, eax; int
0x180014be3  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
```

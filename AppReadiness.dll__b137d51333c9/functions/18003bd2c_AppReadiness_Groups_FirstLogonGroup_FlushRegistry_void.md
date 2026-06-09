# AppReadiness::Groups::FirstLogonGroup::FlushRegistry(void)

- ea: `0x18003bd2c`
- end: `0x18003bf4a`
- name: `?FlushRegistry@FirstLogonGroup@Groups@AppReadiness@@AEAAXXZ`
- size: `542`
- prototype: `void __fastcall(AppReadiness::Groups::FirstLogonGroup *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026ab0`

## callees

- `0x1800041e0`
- `0x180008cd0`
- `0x1800091a0`
- `0x180009290`
- `0x18003bd2c`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003bdd8`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003be82`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003bdd8`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18003be82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bdc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bdc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x18003be71`
- `api-ms-win-core-registry-l1-1-0!RegOpenUserClassesRoot` at `0x18003be71`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Groups::FirstLogonGroup::FlushRegistry(AppReadiness::Groups::FirstLogonGroup *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rax
  const WCHAR *v5; // rdx
  char *v6; // rbx
  __int64 v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // rax
  int v10; // ecx
  _QWORD *v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // rax
  int v16; // ecx
  _QWORD *v17; // r8
  __int64 v18; // rcx
  void **v19; // [rsp+30h] [rbp-28h] BYREF
  HKEY v20; // [rsp+38h] [rbp-20h] BYREF
  void **v21; // [rsp+40h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-10h] BYREF

  v2 = (char *)this + 8;
  if ( (Microsoft_Windows_AppReadinessEnableBits & 0x10000) != 0 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))((char *)this + 8);
    McTemplateU0z_EventWriteTransfer(v3, FirstLogon_RegistryFlush_Start);
  }
  v21 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  hKey = 0;
  v4 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
  v5 = (const WCHAR *)(v4 + 64);
  if ( *(_QWORD *)(v4 + 88) > 7u )
  {
    v5 = *(const WCHAR **)v5;
    v6 = (char *)this + 8;
  }
  else
  {
    v6 = v2;
  }
  v8 = RegOpenKeyExW(HKEY_USERS, v5, 0, 0x20019u, &hKey);
  if ( v8 || (v8 = RegFlushKey(hKey)) != 0 )
  {
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 112LL))(v2);
      v11 = (_QWORD *)(v9 + 64);
      if ( *(_QWORD *)(v9 + 88) > 7u )
        v11 = (_QWORD *)*v11;
      McTemplateU0zzq_EventWriteTransfer(
        v10,
        (unsigned int)FirstLogon_RegistryFlush_Failed,
        (_DWORD)v11,
        (unsigned int)L"HKEY_CURRENT_USER",
        v8);
      v6 = (char *)this + 8;
    }
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x4000) != 0 )
      McTemplateU0zq_EventWriteTransfer(v7, FirstLogon_RegistryFlush_FailedWithoutUserInfo, L"HKEY_CURRENT_USER", v8);
  }
  v19 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  v20 = 0;
  v12 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 112LL))(v6);
  v14 = RegOpenUserClassesRoot(*(HANDLE *)(v12 + 112), 0, 0x20019u, &v20);
  if ( v14 || (v14 = RegFlushKey(v20)) != 0 )
  {
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x40000) != 0 )
    {
      v15 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v6 + 112LL))(v6);
      v17 = (_QWORD *)(v15 + 64);
      if ( *(_QWORD *)(v15 + 88) > 7u )
        v17 = (_QWORD *)*v17;
      McTemplateU0zzq_EventWriteTransfer(
        v16,
        (unsigned int)FirstLogon_RegistryFlush_Failed,
        (_DWORD)v17,
        (unsigned int)L"HKEY_CLASSESS_ROOT",
        v14);
      v6 = (char *)this + 8;
    }
    if ( (Microsoft_Windows_AppReadinessEnableBits & 0x4000) != 0 )
      McTemplateU0zq_EventWriteTransfer(v13, FirstLogon_RegistryFlush_FailedWithoutUserInfo, L"HKEY_CLASSESS_ROOT", v14);
  }
  if ( (Microsoft_Windows_AppReadinessEnableBits & 0x10000) != 0 )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 112LL))(v6);
    McTemplateU0z_EventWriteTransfer(v18, FirstLogon_RegistryFlush_Stop);
  }
  v19 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v19);
  v21 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v21);
}

```

## disassembly

```asm
0x18003bd2c  push    rbp
0x18003bd2e  push    rbx
0x18003bd2f  push    rsi
0x18003bd30  push    rdi
0x18003bd31  push    r14
0x18003bd33  push    r15
0x18003bd35  mov     rbp, rsp
0x18003bd38  sub     rsp, 58h
0x18003bd3c  mov     r14, rcx
0x18003bd3f  lea     rdi, [rcx+8]
0x18003bd43  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 1
0x18003bd4a  jz      short loc_18003BD75
0x18003bd4c  mov     rax, [rdi]
0x18003bd4f  mov     rcx, rdi
0x18003bd52  mov     rax, [rax+70h]
0x18003bd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd5b  lea     r8, [rax+40h]
0x18003bd5f  cmp     qword ptr [r8+18h], 7
0x18003bd64  jbe     short loc_18003BD69
0x18003bd66  mov     r8, [r8]
0x18003bd69  lea     rdx, FirstLogon_RegistryFlush_Start
0x18003bd70  call    McTemplateU0z_EventWriteTransfer
0x18003bd75  lea     r15, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18003bd7c  mov     [rbp+var_18], r15
0x18003bd80  mov     [rbp+hKey], 0
0x18003bd88  mov     rax, [rdi]
0x18003bd8b  mov     rcx, rdi
0x18003bd8e  mov     rax, [rax+70h]
0x18003bd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd97  lea     rdx, [rax+40h]
0x18003bd9b  cmp     qword ptr [rdx+18h], 7
0x18003bda0  ja      short loc_18003BDA7
0x18003bda2  mov     rbx, rdi
0x18003bda5  jmp     short loc_18003BDAE
0x18003bda7  mov     rdx, [rdx]; lpSubKey
0x18003bdaa  lea     rbx, [r14+8]
0x18003bdae  lea     rax, [rbp+hKey]
0x18003bdb2  mov     [rsp+58h+phkResult], rax; phkResult
0x18003bdb7  mov     r9d, 20019h; samDesired
0x18003bdbd  xor     r8d, r8d; ulOptions
0x18003bdc0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003bdc7  call    cs:__imp_RegOpenKeyExW
0x18003bdcd  movsxd  rsi, eax
0x18003bdd0  test    eax, eax
0x18003bdd2  jnz     short loc_18003BDE5
0x18003bdd4  mov     rcx, [rbp+hKey]; hKey
0x18003bdd8  call    cs:__imp_RegFlushKey
0x18003bdde  movsxd  rsi, eax
0x18003bde1  test    eax, eax
0x18003bde3  jz      short loc_18003BE45
0x18003bde5  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 4
0x18003bdec  jz      short loc_18003BE26
0x18003bdee  mov     rax, [rdi]
0x18003bdf1  mov     rcx, rdi
0x18003bdf4  mov     rax, [rax+70h]
0x18003bdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdfd  lea     r8, [rax+40h]
0x18003be01  cmp     qword ptr [r8+18h], 7
0x18003be06  jbe     short loc_18003BE0B
0x18003be08  mov     r8, [r8]
0x18003be0b  mov     dword ptr [rsp+58h+phkResult], esi
0x18003be0f  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18003be16  lea     rdx, FirstLogon_RegistryFlush_Failed
0x18003be1d  call    McTemplateU0zzq_EventWriteTransfer
0x18003be22  lea     rbx, [r14+8]
0x18003be26  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 40h
0x18003be2d  jz      short loc_18003BE45
0x18003be2f  mov     r9d, esi
0x18003be32  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18003be39  lea     rdx, FirstLogon_RegistryFlush_FailedWithoutUserInfo
0x18003be40  call    McTemplateU0zq_EventWriteTransfer
0x18003be45  mov     [rbp+var_28], r15
0x18003be49  mov     [rbp+var_20], 0
0x18003be51  mov     rax, [r14+8]
0x18003be55  mov     rcx, rbx
0x18003be58  mov     rax, [rax+70h]
0x18003be5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be61  lea     r9, [rbp+var_20]; phkResult
0x18003be65  xor     edx, edx; dwOptions
0x18003be67  mov     r8d, 20019h; samDesired
0x18003be6d  mov     rcx, [rax+70h]; hToken
0x18003be71  call    cs:__imp_RegOpenUserClassesRoot
0x18003be77  movsxd  rdi, eax
0x18003be7a  test    eax, eax
0x18003be7c  jnz     short loc_18003BE8F
0x18003be7e  mov     rcx, [rbp+var_20]; hKey
0x18003be82  call    cs:__imp_RegFlushKey
0x18003be88  movsxd  rdi, eax
0x18003be8b  test    eax, eax
0x18003be8d  jz      short loc_18003BEEF
0x18003be8f  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 4
0x18003be96  jz      short loc_18003BED0
0x18003be98  mov     rax, [rbx]
0x18003be9b  mov     rcx, rbx
0x18003be9e  mov     rax, [rax+70h]
0x18003bea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bea7  lea     r8, [rax+40h]
0x18003beab  cmp     qword ptr [r8+18h], 7
0x18003beb0  jbe     short loc_18003BEB5
0x18003beb2  mov     r8, [r8]
0x18003beb5  mov     dword ptr [rsp+58h+phkResult], edi
0x18003beb9  lea     r9, aHkeyClassessRo; "HKEY_CLASSESS_ROOT"
0x18003bec0  lea     rdx, FirstLogon_RegistryFlush_Failed
0x18003bec7  call    McTemplateU0zzq_EventWriteTransfer
0x18003becc  lea     rbx, [r14+8]
0x18003bed0  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+1, 40h
0x18003bed7  jz      short loc_18003BEEF
0x18003bed9  mov     r9d, edi
0x18003bedc  lea     r8, aHkeyClassessRo; "HKEY_CLASSESS_ROOT"
0x18003bee3  lea     rdx, FirstLogon_RegistryFlush_FailedWithoutUserInfo
0x18003beea  call    McTemplateU0zq_EventWriteTransfer
0x18003beef  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 1
0x18003bef6  jz      short loc_18003BF22
0x18003bef8  mov     rax, [rbx]
0x18003befb  mov     rcx, rbx
0x18003befe  mov     rax, [rax+70h]
0x18003bf02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf07  lea     r8, [rax+40h]
0x18003bf0b  cmp     qword ptr [r8+18h], 7
0x18003bf10  jbe     short loc_18003BF15
0x18003bf12  mov     r8, [r8]
0x18003bf15  lea     rdx, FirstLogon_RegistryFlush_Stop
0x18003bf1c  call    McTemplateU0z_EventWriteTransfer
0x18003bf21  nop
0x18003bf22  mov     [rbp+var_28], r15
0x18003bf26  lea     rcx, [rbp+var_28]
0x18003bf2a  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003bf2f  nop
0x18003bf30  mov     [rbp+var_18], r15
0x18003bf34  lea     rcx, [rbp+var_18]
0x18003bf38  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003bf3d  add     rsp, 58h
0x18003bf41  pop     r15
0x18003bf43  pop     r14
0x18003bf45  pop     rdi
0x18003bf46  pop     rsi
0x18003bf47  pop     rbx
0x18003bf48  pop     rbp
0x18003bf49  retn
```

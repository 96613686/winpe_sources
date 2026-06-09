# CProcessStateManager::_WriteColorKeysIfNecessary(ushort const *)

- ea: `0x18001a780`
- end: `0x18001a836`
- name: `?_WriteColorKeysIfNecessary@CProcessStateManager@@AEAAXPEBG@Z`
- size: `182`
- prototype: `void(CProcessStateManager *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001aad0`
- `0x18001ac90`

## callees

- `0x18001363c`
- `0x180014d24`
- `0x18001a780`

## import_xrefs

- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18001a7a2`
- `CredProvCommonCore!__imp_?IsFirstBoot@@YA_NXZ` at `0x18001a7a2`
- `KERNEL32!LocalFree` at `0x18001a825`
- `KERNEL32!LocalFree` at `0x18001a825`
- `UxTheme!__imp_SetImmersiveColorSetSharedMemoryACLforUser` at `0x18001a79c`
- `UxTheme!__imp_SetImmersiveColorSetSharedMemoryACLforUser` at `0x18001a79c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a7c3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a7c3`

## pseudocode

```c
void __fastcall CProcessStateManager::_WriteColorKeysIfNecessary(
        CProcessStateManager *this,
        const unsigned __int16 *a2)
{
  CProcessStateManager *v4; // rcx
  bool IsHighContrastOn; // al
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // r9
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    SetImmersiveColorSetSharedMemoryACLforUser(a2);
    if ( IsFirstBoot() )
    {
      if ( *((_BYTE *)this + 105) )
      {
        Sid = 0;
        if ( ConvertStringSidToSidW(a2, &Sid) )
        {
          IsHighContrastOn = CProcessStateManager::IsHighContrastOn(v4);
          _WriteSystemDataRegistryDWORDForUser(Sid, v6, L"HighContrastEnabled", v7, IsHighContrastOn);
          _WriteSystemDataRegistryDWORDForUser(Sid, v8, L"StartColor", v9, *((_DWORD *)this + 58));
          _WriteSystemDataRegistryDWORDForUser(Sid, v10, L"AccentColor", v11, *((_DWORD *)this + 59));
          LocalFree(Sid);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001a780  test    rdx, rdx
0x18001a783  jz      locret_18001A835
0x18001a789  mov     [rsp+arg_0], rbx
0x18001a78e  push    rdi
0x18001a78f  sub     rsp, 30h
0x18001a793  mov     rdi, rcx
0x18001a796  mov     rbx, rdx
0x18001a799  mov     rcx, rdx
0x18001a79c  call    cs:__imp_SetImmersiveColorSetSharedMemoryACLforUser
0x18001a7a2  call    cs:__imp_?IsFirstBoot@@YA_NXZ; IsFirstBoot(void)
0x18001a7a8  test    al, al
0x18001a7aa  jz      short loc_18001A82B
0x18001a7ac  cmp     byte ptr [rdi+69h], 0
0x18001a7b0  jz      short loc_18001A82B
0x18001a7b2  lea     rdx, [rsp+38h+Sid]; Sid
0x18001a7b7  mov     [rsp+38h+Sid], 0
0x18001a7c0  mov     rcx, rbx; StringSid
0x18001a7c3  call    cs:__imp_ConvertStringSidToSidW
0x18001a7c9  test    eax, eax
0x18001a7cb  jz      short loc_18001A82B
0x18001a7cd  call    ?IsHighContrastOn@CProcessStateManager@@QEAA_NXZ; CProcessStateManager::IsHighContrastOn(void)
0x18001a7d2  mov     rcx, [rsp+38h+Sid]
0x18001a7d7  lea     r8, aHighcontrasten; "HighContrastEnabled"
0x18001a7de  movzx   eax, al
0x18001a7e1  mov     [rsp+38h+var_18], eax
0x18001a7e5  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x18001a7ea  mov     eax, [rdi+0E8h]
0x18001a7f0  lea     r8, aStartcolor; "StartColor"
0x18001a7f7  mov     rcx, [rsp+38h+Sid]
0x18001a7fc  mov     [rsp+38h+var_18], eax
0x18001a800  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x18001a805  mov     eax, [rdi+0ECh]
0x18001a80b  lea     r8, aAccentcolor; "AccentColor"
0x18001a812  mov     rcx, [rsp+38h+Sid]
0x18001a817  mov     [rsp+38h+var_18], eax
0x18001a81b  call    ?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z; _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)
0x18001a820  mov     rcx, [rsp+38h+Sid]; hMem
0x18001a825  call    cs:__imp_LocalFree
0x18001a82b  mov     rbx, [rsp+38h+arg_0]
0x18001a830  add     rsp, 30h
0x18001a834  pop     rdi
0x18001a835  retn
```

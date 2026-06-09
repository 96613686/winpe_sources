# ZtUpdateSettingsAndCommit

- ea: `0x1800049b0`
- end: `0x180004e0f`
- name: `ZtUpdateSettingsAndCommit`
- size: `1119`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, struct _DNS_ZT_SETTINGS **)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800044e4`
- `0x1800052c4`

## callees

- `0x1800014b0`
- `0x180004310`
- `0x1800046ec`
- `0x1800048f0`
- `0x1800049b0`
- `0x180005134`
- `0x18000dbcc`
- `0x18000dc74`
- `0x18000dcb0`
- `0x18000dd04`
- `0x18000ddec`
- `0x18000e080`
- `0x18000ff50`
- `0x180015008`
- `0x180015094`

## import_xrefs

- `ntdll!NtCommitRegistryTransaction` at `0x180004c01`
- `ntdll!NtCommitRegistryTransaction` at `0x180004c01`
- `ntdll!RtlNtStatusToDosError` at `0x180004c09`
- `ntdll!RtlNtStatusToDosError` at `0x180004c09`
- `ntdll!NtClose` at `0x180004dc9`
- `ntdll!NtClose` at `0x180004dc9`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180004d87`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180004d87`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180004d9b`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180004d9b`
- `DNSAPI!DnsFreeZtSettings` at `0x180004d01`
- `DNSAPI!DnsFreeZtSettings` at `0x180004d01`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180004dae`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180004dae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004de4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004de4`

## pseudocode

```c
__int64 __fastcall ZtUpdateSettingsAndCommit(__int64 a1, __int64 a2, __int64 a3, int a4, struct _DNS_ZT_SETTINGS **a5)
{
  int v5; // r13d
  __int64 v6; // rsi
  struct _DNS_ZT_SETTINGS *v8; // rdi
  ULONG v10; // ebx
  ULONG v11; // eax
  unsigned int updated; // eax
  __int64 v13; // rdx
  ULONG SettingsLocked; // eax
  volatile signed __int32 *v15; // rdx
  signed __int32 v16; // eax
  HANDLE v17; // rbx
  NTSTATUS v18; // eax
  char v19; // al
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v24; // [rsp+50h] [rbp-C8h] BYREF
  struct _DNS_ZT_SETTINGS *v25; // [rsp+58h] [rbp-C0h] BYREF
  signed __int32 v26; // [rsp+60h] [rbp-B8h]
  __int64 v27; // [rsp+68h] [rbp-B0h] BYREF
  LPVOID v28; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+78h] [rbp-A0h]
  LPVOID lpMem; // [rsp+80h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-88h] BYREF
  __int64 v33; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v34[48]; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v35; // [rsp+D0h] [rbp-48h]

  v5 = 0;
  v6 = (int)a2;
  hKey = 0;
  Handle = 0;
  v24 = 0;
  v8 = (struct _DNS_ZT_SETTINGS *)a3;
  v26 = 0;
  v27 = 0;
  v33 = 0;
  v25 = 0;
  v28 = 0;
  lpMem = 0;
  v35 = 0;
  v29 = 0;
  memset(v34, 0, sizeof(v34));
  if ( !a3 )
  {
    v10 = 87;
    goto LABEL_49;
  }
  if ( (unsigned int)a2 > 1 )
  {
    v22 = 87;
    v10 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_49;
    v21 = 44;
    goto LABEL_48;
  }
  v11 = ZtRegOpen(a2, a2, a3, &hKey, &Handle);
  v10 = v11;
  if ( v11 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_49;
    v21 = 45;
    v22 = v11;
LABEL_48:
    WPP_SF_d(1026, v21, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v22);
    goto LABEL_49;
  }
  updated = ZtUpdateSettingsSaveBackup(a1, (unsigned int)v6, v8, &v24, &v27, &v33, &v28, &lpMem);
  v10 = updated;
  if ( updated )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
    {
      v13 = 46;
      goto LABEL_39;
    }
    goto LABEL_41;
  }
  if ( (*((_BYTE *)v8 + 8) & 1) != 0 )
  {
    updated = ZtHelperUpdateConfig((unsigned int)v6, *((_QWORD *)v8 + 2), v34);
    v10 = updated;
    if ( updated )
    {
      if ( (xmmword_18001F260 & 4) != 0 )
      {
        v13 = 47;
LABEL_39:
        v20 = updated;
        goto LABEL_40;
      }
      goto LABEL_41;
    }
  }
  if ( (a1 & 0x20) != 0 )
  {
    if ( g_fVelocityZtdnsApiRefactor )
      SettingsLocked = ZtGetSettingsLocked(31, 1, &v25);
    else
      SettingsLocked = ZtHelperGetSettingsLocked(31, 1, &v25);
    v10 = SettingsLocked;
    if ( SettingsLocked )
      goto LABEL_41;
    v8 = v25;
    v5 = 1;
  }
  else
  {
    v25 = v8;
  }
  updated = ZtWriteSettings(v8, Handle, hKey);
  v10 = updated;
  if ( updated )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
    {
      v13 = 48;
      goto LABEL_39;
    }
    goto LABEL_41;
  }
  if ( !a4 )
  {
    v15 = (volatile signed __int32 *)&g_rgZtHelperSettingsState + 5 * v6;
    if ( !v15 )
    {
      v20 = 87;
      v10 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_41;
      v13 = 50;
      goto LABEL_40;
    }
    v16 = _InterlockedCompareExchange(v15, 0, 0);
    _InterlockedIncrement(v15);
    v29 |= 0x80uLL;
    v26 = v16;
LABEL_24:
    v17 = Handle;
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_q(1026, 10, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, Handle);
    v18 = NtCommitRegistryTransaction(v17, 0);
    v10 = RtlNtStatusToDosError(v18);
    v19 = xmmword_18001F260;
    if ( (xmmword_18001F260 & 4) != 0 )
    {
      WPP_SF_d(1026, 11, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, v10);
      v19 = xmmword_18001F260;
    }
    if ( !v10 )
    {
      if ( a5 )
      {
        *a5 = v25;
        v25 = 0;
      }
      goto LABEL_42;
    }
    if ( (v19 & 4) == 0 )
      goto LABEL_41;
    v13 = 51;
    v20 = v10;
LABEL_40:
    WPP_SF_d(1026, v13, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v20);
    goto LABEL_41;
  }
  updated = ZtPromoteStagingToActive(hKey);
  v10 = updated;
  if ( !updated )
    goto LABEL_24;
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v13 = 49;
    goto LABEL_39;
  }
LABEL_41:
  ZtRestoreBackupSettings((unsigned int)v6, &v24, &v27, &v33, &v28, &lpMem);
LABEL_42:
  if ( v5 )
    DnsFreeZtSettings(v25);
LABEL_49:
  v25 = 0;
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeTrustedServers(v24, v27);
    v27 = 0;
    v24 = 0;
    ZtFreeTrustedCa(v28);
    v28 = 0;
    ZtFreeClientCertConfig(lpMem);
  }
  else
  {
    DnsFreeZtTrustedServers(v24, v27);
    v27 = 0;
    v24 = 0;
    DnsFreeZtTrustedCa(v28);
    v28 = 0;
    DnsFreeZtClientCertConfig(lpMem);
  }
  lpMem = 0;
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x1800049b0  mov     r11, rsp
0x1800049b3  push    rbx
0x1800049b4  push    rsi
0x1800049b5  push    rdi
0x1800049b6  push    r12
0x1800049b8  push    r13
0x1800049ba  push    r14
0x1800049bc  push    r15
0x1800049be  sub     rsp, 0E0h
0x1800049c5  mov     rax, cs:__security_cookie
0x1800049cc  xor     rax, rsp
0x1800049cf  mov     [rsp+118h+var_40], rax
0x1800049d7  mov     r15, [rsp+118h+arg_20]
0x1800049df  xor     r13d, r13d
0x1800049e2  xorps   xmm0, xmm0
0x1800049e5  movsxd  rsi, edx
0x1800049e8  xor     eax, eax
0x1800049ea  mov     [r11-88h], r13
0x1800049f1  mov     [r11-90h], r13
0x1800049f8  mov     r12d, r9d
0x1800049fb  mov     [rsp+118h+var_C8], r13d
0x180004a00  mov     rdi, r8
0x180004a03  mov     [rsp+118h+var_B8], r13d
0x180004a08  mov     r14, rcx
0x180004a0b  mov     [rsp+118h+var_B0], r13
0x180004a10  mov     [r11-80h], r13
0x180004a14  mov     [rsp+118h+var_C0], r13
0x180004a19  mov     [rsp+118h+var_A8], r13
0x180004a1e  mov     [r11-98h], r13
0x180004a25  mov     [r11-48h], rax
0x180004a29  mov     [rsp+118h+var_A0], r13
0x180004a2e  movups  xmmword ptr [r11-78h], xmm0
0x180004a33  movups  xmmword ptr [r11-68h], xmm0
0x180004a38  movups  xmmword ptr [r11-58h], xmm0
0x180004a3d  test    r8, r8
0x180004a40  jnz     short loc_180004A4A
0x180004a42  lea     ebx, [rax+57h]
0x180004a45  jmp     loc_180004D43
0x180004a4a  cmp     esi, 1
0x180004a4d  ja      loc_180004D1C
0x180004a53  lea     rax, [rsp+118h+Handle]
0x180004a5b  mov     ecx, esi
0x180004a5d  lea     r9, [rsp+118h+hKey]
0x180004a65  mov     [rsp+118h+var_F8], rax
0x180004a6a  call    ZtRegOpen
0x180004a6f  mov     ebx, eax
0x180004a71  test    eax, eax
0x180004a73  jnz     loc_180004D09
0x180004a79  lea     rax, [rsp+118h+var_A0]
0x180004a7e  mov     r8, rdi
0x180004a81  mov     [rsp+118h+var_D0], rax
0x180004a86  lea     r9, [rsp+118h+var_C8]
0x180004a8b  lea     rax, [rsp+118h+lpMem]
0x180004a93  mov     edx, esi
0x180004a95  mov     [rsp+118h+var_E0], rax
0x180004a9a  mov     rcx, r14
0x180004a9d  lea     rax, [rsp+118h+var_A8]
0x180004aa2  mov     [rsp+118h+var_E8], rax
0x180004aa7  lea     rax, [rsp+118h+var_80]
0x180004aaf  mov     [rsp+118h+var_F0], rax
0x180004ab4  lea     rax, [rsp+118h+var_B0]
0x180004ab9  mov     [rsp+118h+var_F8], rax
0x180004abe  call    ?ZtUpdateSettingsSaveBackup@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@PEA_K@Z; ZtUpdateSettingsSaveBackup(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x180004ac3  mov     ebx, eax
0x180004ac5  test    eax, eax
0x180004ac7  jnz     loc_180004C93
0x180004acd  test    byte ptr [rdi+8], 1
0x180004ad1  jz      short loc_180004B03
0x180004ad3  mov     rdx, [rdi+10h]
0x180004ad7  lea     r8, [rsp+118h+var_78]
0x180004adf  mov     ecx, esi
0x180004ae1  call    ?ZtHelperUpdateConfig@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@1@Z; ZtHelperUpdateConfig(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,_DNS_ZT_CONFIG *)
0x180004ae6  mov     ebx, eax
0x180004ae8  test    eax, eax
0x180004aea  jz      short loc_180004B03
0x180004aec  test    byte ptr cs:xmmword_18001F260, 4
0x180004af3  jz      loc_180004CB5
0x180004af9  mov     edx, 2Fh ; '/'
0x180004afe  jmp     loc_180004CA1
0x180004b03  test    r14b, 20h
0x180004b07  jz      short loc_180004B44
0x180004b09  xor     r9d, r9d
0x180004b0c  lea     r8, [rsp+118h+var_C0]
0x180004b11  cmp     cs:g_fVelocityZtdnsApiRefactor, r13d
0x180004b18  lea     edx, [r9+1]
0x180004b1c  lea     ecx, [rdx+1Eh]
0x180004b1f  jz      short loc_180004B28
0x180004b21  call    ZtGetSettingsLocked
0x180004b26  jmp     short loc_180004B2D
0x180004b28  call    ?ZtHelperGetSettingsLocked@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAPEAU_DNS_ZT_SETTINGS@@PEAU_DNS_ZT_SETTINGS_STATE@@@Z; ZtHelperGetSettingsLocked(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS * *,_DNS_ZT_SETTINGS_STATE *)
0x180004b2d  mov     ebx, eax
0x180004b2f  test    eax, eax
0x180004b31  jnz     loc_180004CB5
0x180004b37  mov     rdi, [rsp+118h+var_C0]
0x180004b3c  mov     r13d, 1
0x180004b42  jmp     short loc_180004B49
0x180004b44  mov     [rsp+118h+var_C0], rdi
0x180004b49  mov     r8, [rsp+118h+hKey]; HKEY
0x180004b51  mov     rcx, rdi; struct _DNS_ZT_SETTINGS *
0x180004b54  mov     rdx, [rsp+118h+Handle]; void *
0x180004b5c  call    ?ZtWriteSettings@@YAJPEAU_DNS_ZT_SETTINGS@@PEAXPEAUHKEY__@@@Z; ZtWriteSettings(_DNS_ZT_SETTINGS *,void *,HKEY__ *)
0x180004b61  mov     ebx, eax
0x180004b63  test    eax, eax
0x180004b65  jnz     loc_180004C83
0x180004b6b  test    r12d, r12d
0x180004b6e  jz      short loc_180004BA4
0x180004b70  mov     rcx, [rsp+118h+hKey]; hKey
0x180004b78  lea     r8, [rsp+118h+var_A0]
0x180004b7d  lea     rdx, [rsp+118h+var_B8]
0x180004b82  call    ZtPromoteStagingToActive
0x180004b87  mov     ebx, eax
0x180004b89  test    eax, eax
0x180004b8b  jz      short loc_180004BD2
0x180004b8d  test    byte ptr cs:xmmword_18001F260, 4
0x180004b94  jz      loc_180004CB5
0x180004b9a  mov     edx, 31h ; '1'
0x180004b9f  jmp     loc_180004CA1
0x180004ba4  lea     rcx, [rsi+rsi*4]
0x180004ba8  lea     rax, g_rgZtHelperSettingsState
0x180004baf  lea     rdx, [rax+rcx*4]
0x180004bb3  test    rdx, rdx
0x180004bb6  jz      loc_180004C6B
0x180004bbc  xor     ecx, ecx
0x180004bbe  xor     eax, eax
0x180004bc0  lock cmpxchg [rdx], ecx
0x180004bc4  lock inc dword ptr [rdx]
0x180004bc7  bts     [rsp+118h+var_A0], 7
0x180004bce  mov     [rsp+118h+var_B8], eax
0x180004bd2  mov     rbx, [rsp+118h+Handle]
0x180004bda  test    byte ptr cs:xmmword_18001F260, 4
0x180004be1  jz      short loc_180004BFC
0x180004be3  mov     edx, 0Ah
0x180004be8  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180004bef  mov     ecx, 402h
0x180004bf4  mov     r9, rbx
0x180004bf7  call    WPP_SF_q
0x180004bfc  xor     edx, edx
0x180004bfe  mov     rcx, rbx
0x180004c01  call    cs:__imp_NtCommitRegistryTransaction
0x180004c07  mov     ecx, eax; Status
0x180004c09  call    cs:__imp_RtlNtStatusToDosError
0x180004c0f  mov     ebx, eax
0x180004c11  mov     al, byte ptr cs:xmmword_18001F260
0x180004c17  test    al, 4
0x180004c19  jz      short loc_180004C3A
0x180004c1b  mov     edx, 0Bh
0x180004c20  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180004c27  mov     ecx, 402h
0x180004c2c  mov     r9d, ebx
0x180004c2f  call    WPP_SF_d
0x180004c34  mov     al, byte ptr cs:xmmword_18001F260
0x180004c3a  test    ebx, ebx
0x180004c3c  jnz     short loc_180004C5D
0x180004c3e  test    r15, r15
0x180004c41  jz      loc_180004CF7
0x180004c47  mov     rax, [rsp+118h+var_C0]
0x180004c4c  mov     [r15], rax
0x180004c4f  mov     [rsp+118h+var_C0], 0
0x180004c58  jmp     loc_180004CF7
0x180004c5d  test    al, 4
0x180004c5f  jz      short loc_180004CB5
0x180004c61  mov     edx, 33h ; '3'
0x180004c66  mov     r9d, ebx
0x180004c69  jmp     short loc_180004CA4
0x180004c6b  test    byte ptr cs:xmmword_18001F260, 4
0x180004c72  mov     r9d, 57h ; 'W'
0x180004c78  mov     ebx, r9d
0x180004c7b  jz      short loc_180004CB5
0x180004c7d  lea     edx, [r9-25h]
0x180004c81  jmp     short loc_180004CA4
0x180004c83  test    byte ptr cs:xmmword_18001F260, 4
0x180004c8a  jz      short loc_180004CB5
0x180004c8c  mov     edx, 30h ; '0'
0x180004c91  jmp     short loc_180004CA1
0x180004c93  test    byte ptr cs:xmmword_18001F260, 4
0x180004c9a  jz      short loc_180004CB5
0x180004c9c  mov     edx, 2Eh ; '.'
0x180004ca1  mov     r9d, eax
0x180004ca4  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004cab  mov     ecx, 402h
0x180004cb0  call    WPP_SF_d
0x180004cb5  mov     rax, [rsp+118h+var_A0]
0x180004cba  lea     r9, [rsp+118h+var_80]
0x180004cc2  mov     [rsp+118h+var_D8], rax
0x180004cc7  lea     r8, [rsp+118h+var_B0]
0x180004ccc  mov     eax, [rsp+118h+var_B8]
0x180004cd0  lea     rdx, [rsp+118h+var_C8]
0x180004cd5  mov     dword ptr [rsp+118h+var_E0], eax
0x180004cd9  mov     ecx, esi
0x180004cdb  lea     rax, [rsp+118h+lpMem]
0x180004ce3  mov     [rsp+118h+var_F0], rax
0x180004ce8  lea     rax, [rsp+118h+var_A8]
0x180004ced  mov     [rsp+118h+var_F8], rax
0x180004cf2  call    ?ZtRestoreBackupSettings@@YAXW4_ZTDNS_SETTINGS_TYPE@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@K_K@Z; ZtRestoreBackupSettings(_ZTDNS_SETTINGS_TYPE,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,ulong,unsigned __int64)
0x180004cf7  test    r13d, r13d
0x180004cfa  jz      short loc_180004D43
0x180004cfc  mov     rcx, [rsp+118h+var_C0]
0x180004d01  call    cs:__imp_DnsFreeZtSettings
0x180004d07  jmp     short loc_180004D43
0x180004d09  test    byte ptr cs:xmmword_18001F260, 4
0x180004d10  jz      short loc_180004D43
0x180004d12  mov     edx, 2Dh ; '-'
0x180004d17  mov     r9d, eax
0x180004d1a  jmp     short loc_180004D32
0x180004d1c  mov     r9d, 57h ; 'W'
0x180004d22  mov     ebx, r9d
0x180004d25  test    byte ptr cs:xmmword_18001F260, 4
0x180004d2c  jz      short loc_180004D43
0x180004d2e  lea     edx, [r9-2Bh]
0x180004d32  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004d39  mov     ecx, 402h
0x180004d3e  call    WPP_SF_d
0x180004d43  mov     rdx, [rsp+118h+var_B0]
0x180004d48  xor     edi, edi
0x180004d4a  cmp     cs:g_fVelocityZtdnsApiRefactor, edi
0x180004d50  mov     ecx, [rsp+118h+var_C8]
0x180004d54  mov     [rsp+118h+var_C0], rdi
0x180004d59  jz      short loc_180004D87
0x180004d5b  call    ZtFreeTrustedServers
0x180004d60  mov     rcx, [rsp+118h+var_A8]; lpMem
0x180004d65  mov     [rsp+118h+var_B0], rdi
0x180004d6a  mov     [rsp+118h+var_C8], edi
0x180004d6e  call    ZtFreeTrustedCa
0x180004d73  mov     rcx, [rsp+118h+lpMem]; lpMem
0x180004d7b  mov     [rsp+118h+var_A8], rdi
0x180004d80  call    ZtFreeClientCertConfig
0x180004d85  jmp     short loc_180004DB4
0x180004d87  call    cs:__imp_DnsFreeZtTrustedServers
0x180004d8d  mov     rcx, [rsp+118h+var_A8]
0x180004d92  mov     [rsp+118h+var_B0], rdi
0x180004d97  mov     [rsp+118h+var_C8], edi
0x180004d9b  call    cs:__imp_DnsFreeZtTrustedCa
0x180004da1  mov     rcx, [rsp+118h+lpMem]
0x180004da9  mov     [rsp+118h+var_A8], rdi
0x180004dae  call    cs:__imp_DnsFreeZtClientCertConfig
0x180004db4  mov     rcx, [rsp+118h+Handle]; Handle
0x180004dbc  mov     [rsp+118h+lpMem], rdi
0x180004dc4  test    rcx, rcx
0x180004dc7  jz      short loc_180004DD7
0x180004dc9  call    cs:__imp_NtClose
0x180004dcf  mov     [rsp+118h+Handle], rdi
0x180004dd7  mov     rcx, [rsp+118h+hKey]; hKey
0x180004ddf  test    rcx, rcx
0x180004de2  jz      short loc_180004DEA
0x180004de4  call    cs:__imp_RegCloseKey
0x180004dea  mov     eax, ebx
0x180004dec  mov     rcx, [rsp+118h+var_40]
0x180004df4  xor     rcx, rsp; StackCookie
0x180004df7  call    __security_check_cookie
0x180004dfc  add     rsp, 0E0h
0x180004e03  pop     r15
0x180004e05  pop     r14
0x180004e07  pop     r13
0x180004e09  pop     r12
0x180004e0b  pop     rdi
0x180004e0c  pop     rsi
0x180004e0d  pop     rbx
0x180004e0e  retn
```

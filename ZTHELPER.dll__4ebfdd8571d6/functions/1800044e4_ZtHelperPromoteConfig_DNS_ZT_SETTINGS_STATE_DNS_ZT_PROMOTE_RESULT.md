# ZtHelperPromoteConfig(_DNS_ZT_SETTINGS_STATE *,_DNS_ZT_PROMOTE_RESULT *)

- ea: `0x1800044e4`
- end: `0x1800046e4`
- name: `?ZtHelperPromoteConfig@@YAJPEAU_DNS_ZT_SETTINGS_STATE@@PEAW4_DNS_ZT_PROMOTE_RESULT@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(struct _DNS_ZT_SETTINGS_STATE *, enum _DNS_ZT_PROMOTE_RESULT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002650`

## callees

- `0x1800014b0`
- `0x180004310`
- `0x1800044e4`
- `0x18000482c`
- `0x1800049b0`
- `0x18000e080`
- `0x18000e270`
- `0x180015008`
- `0x180015094`
- `0x1800153dc`

## import_xrefs

- `DNSAPI!DnsFreeZtSettings` at `0x180004694`
- `DNSAPI!DnsFreeZtSettings` at `0x180004694`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004613`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004685`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004613`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004685`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004575`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004575`

## pseudocode

```c
__int64 __fastcall ZtHelperPromoteConfig(struct _DNS_ZT_SETTINGS_STATE *a1, enum _DNS_ZT_PROMOTE_RESULT *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // esi
  unsigned int v9; // edi
  unsigned int SettingsLocked; // eax
  __int64 v11; // rdx
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  int v14; // [rsp+38h] [rbp-28h] BYREF
  __int128 v15; // [rsp+3Ch] [rbp-24h]

  v14 = 0;
  v15 = 0;
  v13 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 58, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, a1);
  if ( !a1 )
    goto LABEL_4;
  if ( g_fVelocityZtdnsProbing )
  {
    if ( !a2 )
    {
LABEL_4:
      v4 = 87;
      goto LABEL_30;
    }
    *(_DWORD *)a2 = 0;
  }
  AcquireSRWLockExclusive(&g_rwZtSettingsLock);
  if ( !(unsigned int)ZtSynchronizeSettingsState(a1, &dword_18001F364) )
  {
    v4 = 0;
    if ( g_fVelocityZtdnsProbing )
    {
      v8 = 1;
      v9 = 2;
      goto LABEL_20;
    }
LABEL_29:
    ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
    goto LABEL_30;
  }
  v9 = 1;
  if ( g_fVelocityZtdnsApiRefactor )
  {
    SettingsLocked = ZtGetSettingsLocked(31, 1, &v13);
    v4 = SettingsLocked;
    if ( SettingsLocked )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_29;
      v11 = 59;
LABEL_28:
      WPP_SF_d(1026, v11, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, SettingsLocked);
      goto LABEL_29;
    }
  }
  else
  {
    SettingsLocked = ZtHelperGetSettingsLocked(31, 1, &v13);
    v4 = SettingsLocked;
    if ( SettingsLocked )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_29;
      v11 = 60;
      goto LABEL_28;
    }
  }
  SettingsLocked = ZtUpdateSettingsAndCommit(0, 0, v13, 1, 0);
  v4 = SettingsLocked;
  if ( SettingsLocked )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_29;
    v11 = 61;
    goto LABEL_28;
  }
  ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
  v4 = ZtNotifyDnscache(0, v13, &v14);
  if ( v4 || !g_fVelocityZtdnsProbing )
    goto LABEL_30;
  v8 = 0;
LABEL_20:
  *(_DWORD *)a2 = v9;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_L(v6, v5, v7, v9);
  if ( v8 )
    goto LABEL_29;
LABEL_30:
  if ( v13 )
  {
    DnsFreeZtSettings(v13);
    v13 = 0;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 63, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800044e4  mov     [rsp-28h+arg_10], rbx
0x1800044e9  push    rbp
0x1800044ea  push    rsi
0x1800044eb  push    rdi
0x1800044ec  push    r13
0x1800044ee  push    r14
0x1800044f0  mov     rbp, rsp
0x1800044f3  sub     rsp, 60h
0x1800044f7  mov     rax, cs:__security_cookie
0x1800044fe  xor     rax, rsp
0x180004501  mov     [rbp+var_10], rax
0x180004505  xorps   xmm0, xmm0
0x180004508  mov     [rbp+var_28], 0
0x18000450f  movups  [rbp+var_24], xmm0
0x180004513  mov     r14, rdx
0x180004516  mov     [rbp+var_30], 0
0x18000451e  mov     rbx, rcx
0x180004521  test    byte ptr cs:xmmword_18001F260, 4
0x180004528  lea     rsi, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x18000452f  mov     r13d, 402h
0x180004535  jz      short loc_18000454A
0x180004537  mov     edx, 3Ah ; ':'
0x18000453c  mov     ecx, r13d
0x18000453f  mov     r9, rbx
0x180004542  mov     r8, rsi
0x180004545  call    WPP_SF_q
0x18000454a  test    rbx, rbx
0x18000454d  jnz     short loc_180004559
0x18000454f  mov     ebx, 57h ; 'W'
0x180004554  jmp     loc_18000468B
0x180004559  cmp     cs:g_fVelocityZtdnsProbing, 0
0x180004560  jz      short loc_18000456E
0x180004562  test    r14, r14
0x180004565  jz      short loc_18000454F
0x180004567  mov     dword ptr [r14], 0
0x18000456e  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180004575  call    cs:__imp_AcquireSRWLockExclusive
0x18000457b  lea     rdx, dword_18001F364
0x180004582  mov     rcx, rbx
0x180004585  call    ZtSynchronizeSettingsState
0x18000458a  test    eax, eax
0x18000458c  jnz     short loc_1800045A7
0x18000458e  xor     ebx, ebx
0x180004590  cmp     cs:g_fVelocityZtdnsProbing, ebx
0x180004596  jz      loc_18000467E
0x18000459c  lea     esi, [rax+1]
0x18000459f  lea     edi, [rax+2]
0x1800045a2  jmp     loc_180004638
0x1800045a7  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x1800045ae  lea     r9, [rbp+var_28]
0x1800045b2  mov     edi, 1
0x1800045b7  lea     r8, [rbp+var_30]
0x1800045bb  mov     edx, edi
0x1800045bd  lea     ecx, [rdi+1Eh]
0x1800045c0  jz      short loc_1800045E2
0x1800045c2  call    ZtGetSettingsLocked
0x1800045c7  mov     ebx, eax
0x1800045c9  test    eax, eax
0x1800045cb  jz      short loc_1800045ED
0x1800045cd  test    byte ptr cs:xmmword_18001F260, 4
0x1800045d4  jz      loc_18000467E
0x1800045da  lea     edx, [rdi+3Ah]
0x1800045dd  jmp     loc_180004670
0x1800045e2  call    ?ZtHelperGetSettingsLocked@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAPEAU_DNS_ZT_SETTINGS@@PEAU_DNS_ZT_SETTINGS_STATE@@@Z; ZtHelperGetSettingsLocked(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS * *,_DNS_ZT_SETTINGS_STATE *)
0x1800045e7  mov     ebx, eax
0x1800045e9  test    eax, eax
0x1800045eb  jnz     short loc_180004662
0x1800045ed  mov     r8, [rbp+var_30]
0x1800045f1  mov     r9d, edi
0x1800045f4  xor     edx, edx
0x1800045f6  mov     [rsp+60h+var_40], 0
0x1800045ff  xor     ecx, ecx
0x180004601  call    ZtUpdateSettingsAndCommit
0x180004606  mov     ebx, eax
0x180004608  test    eax, eax
0x18000460a  jnz     short loc_180004652
0x18000460c  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180004613  call    cs:__imp_ReleaseSRWLockExclusive
0x180004619  mov     rdx, [rbp+var_30]
0x18000461d  lea     r8, [rbp+var_28]
0x180004621  xor     ecx, ecx
0x180004623  call    ?ZtNotifyDnscache@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAU_DNS_ZT_SETTINGS_STATE@@@Z; ZtNotifyDnscache(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,_DNS_ZT_SETTINGS_STATE *)
0x180004628  mov     ebx, eax
0x18000462a  test    eax, eax
0x18000462c  jnz     short loc_18000468B
0x18000462e  cmp     cs:g_fVelocityZtdnsProbing, eax
0x180004634  jz      short loc_18000468B
0x180004636  xor     esi, esi
0x180004638  mov     [r14], edi
0x18000463b  test    byte ptr cs:xmmword_18001F260, 4
0x180004642  jz      short loc_18000464C
0x180004644  mov     r9d, edi
0x180004647  call    WPP_SF_L
0x18000464c  test    esi, esi
0x18000464e  jnz     short loc_18000467E
0x180004650  jmp     short loc_18000468B
0x180004652  test    byte ptr cs:xmmword_18001F260, 4
0x180004659  jz      short loc_18000467E
0x18000465b  mov     edx, 3Dh ; '='
0x180004660  jmp     short loc_180004670
0x180004662  test    byte ptr cs:xmmword_18001F260, 4
0x180004669  jz      short loc_18000467E
0x18000466b  mov     edx, 3Ch ; '<'
0x180004670  mov     r9d, eax
0x180004673  mov     r8, rsi
0x180004676  mov     ecx, r13d
0x180004679  call    WPP_SF_d
0x18000467e  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180004685  call    cs:__imp_ReleaseSRWLockExclusive
0x18000468b  mov     rcx, [rbp+var_30]
0x18000468f  test    rcx, rcx
0x180004692  jz      short loc_1800046A2
0x180004694  call    cs:__imp_DnsFreeZtSettings
0x18000469a  mov     [rbp+var_30], 0
0x1800046a2  test    byte ptr cs:xmmword_18001F260, 4
0x1800046a9  jz      short loc_1800046C2
0x1800046ab  mov     edx, 3Fh ; '?'
0x1800046b0  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x1800046b7  mov     ecx, r13d
0x1800046ba  mov     r9d, ebx
0x1800046bd  call    WPP_SF_d
0x1800046c2  mov     eax, ebx
0x1800046c4  mov     rcx, [rbp+var_10]
0x1800046c8  xor     rcx, rsp; StackCookie
0x1800046cb  call    __security_check_cookie
0x1800046d0  mov     rbx, [rsp+60h+arg_10]
0x1800046d8  add     rsp, 60h
0x1800046dc  pop     r14
0x1800046de  pop     r13
0x1800046e0  pop     rdi
0x1800046e1  pop     rsi
0x1800046e2  pop     rbp
0x1800046e3  retn
```

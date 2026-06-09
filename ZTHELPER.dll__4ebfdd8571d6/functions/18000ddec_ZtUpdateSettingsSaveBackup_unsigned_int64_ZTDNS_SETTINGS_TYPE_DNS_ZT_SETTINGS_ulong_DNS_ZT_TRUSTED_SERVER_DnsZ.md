# ZtUpdateSettingsSaveBackup(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,unsigned __int64 *)

- ea: `0x18000ddec`
- end: `0x18000df66`
- name: `?ZtUpdateSettingsSaveBackup@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@PEA_K@Z`
- size: `378`
- prototype: `__int64 __fastcall(char, unsigned int, __int64, __int64, __int64, DnsZtRuleMap **, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800049b0`

## callees

- `0x18000ddec`
- `0x180010c18`
- `0x1800111cc`
- `0x180011548`
- `0x180011e34`
- `0x180012410`
- `0x180015008`
- `0x180015094`

## pseudocode

```c
__int64 __fastcall ZtUpdateSettingsSaveBackup(
        char a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        DnsZtRuleMap **a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10)
{
  unsigned int updated; // edi
  int v15; // r15d
  _DWORD *v16; // rdx
  _BOOL8 v17; // r9
  unsigned int v18; // eax
  unsigned int *v19; // rdx

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_q(1035, 10, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids, a3);
  if ( !a3 )
  {
    updated = 87;
    goto LABEL_27;
  }
  updated = 0;
  v15 = 1;
  if ( (*(_BYTE *)(a3 + 8) & 2) != 0 )
  {
    v16 = (_DWORD *)(a3 + 32);
    v17 = (a1 & 0x20) != 0 && *v16;
    updated = ZtUpdateServersGlobal(a2, (unsigned int)*v16, *(_QWORD *)(a3 + 24), v17, a4, a5);
    if ( updated )
      goto LABEL_27;
    *a10 |= 2uLL;
  }
  if ( (*(_BYTE *)(a3 + 8) & 0x10) != 0 )
  {
    updated = ZtUpdateTrustedCaGlobal(a2, *(_QWORD *)(a3 + 64), a7);
    if ( updated )
      goto LABEL_27;
    *a10 |= 0x10uLL;
  }
  if ( (*(_BYTE *)(a3 + 8) & 8) != 0 )
  {
    updated = ZtUpdateClientCertsGlobal(a2, *(_QWORD *)(a3 + 56), a8);
    if ( updated )
      goto LABEL_27;
    *a10 |= 8uLL;
  }
  if ( (*(_BYTE *)(a3 + 8) & 4) != 0 )
  {
    if ( (a1 & 0x40) != 0 )
    {
      v18 = ZtDeleteRulesGlobal(a2, *(_DWORD *)(a3 + 48), *(_QWORD *)(a3 + 40), a6);
    }
    else
    {
      v19 = (unsigned int *)(a3 + 48);
      if ( (a1 & 0x20) == 0 || !*v19 )
        v15 = 0;
      v18 = ZtUpdateRulesGlobal(a2, *v19, *(_QWORD *)(a3 + 40), v15, a6);
    }
    updated = v18;
    if ( !v18 )
      *a10 |= 4uLL;
  }
LABEL_27:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 11, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids, updated);
  return updated;
}

```

## disassembly

```asm
0x18000ddec  push    rbx
0x18000ddee  push    rbp
0x18000ddef  push    rsi
0x18000ddf0  push    rdi
0x18000ddf1  push    r12
0x18000ddf3  push    r14
0x18000ddf5  push    r15
0x18000ddf7  sub     rsp, 30h
0x18000ddfb  mov     r12, r9
0x18000ddfe  mov     rbx, r8
0x18000de01  mov     ebp, edx
0x18000de03  mov     r14, rcx
0x18000de06  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000de0d  jz      short loc_18000DE28
0x18000de0f  mov     edx, 0Ah
0x18000de14  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000de1b  mov     ecx, 40Bh
0x18000de20  mov     r9, rbx
0x18000de23  call    WPP_SF_q
0x18000de28  test    rbx, rbx
0x18000de2b  jnz     short loc_18000DE35
0x18000de2d  lea     edi, [rbx+57h]
0x18000de30  jmp     loc_18000DF33
0x18000de35  mov     rsi, [rsp+68h+arg_48]
0x18000de3d  xor     edi, edi
0x18000de3f  test    byte ptr [rbx+8], 2
0x18000de43  lea     r15d, [rdi+1]
0x18000de47  jz      short loc_18000DE8C
0x18000de49  lea     rdx, [rbx+20h]
0x18000de4d  test    r14b, 20h
0x18000de51  jz      short loc_18000DE5C
0x18000de53  cmp     [rdx], edi
0x18000de55  jbe     short loc_18000DE5C
0x18000de57  mov     r9d, r15d
0x18000de5a  jmp     short loc_18000DE5F
0x18000de5c  xor     r9d, r9d
0x18000de5f  mov     rax, [rsp+68h+arg_20]
0x18000de67  mov     ecx, ebp
0x18000de69  mov     r8, [rbx+18h]
0x18000de6d  mov     edx, [rdx]
0x18000de6f  mov     [rsp+68h+var_40], rax
0x18000de74  mov     [rsp+68h+var_48], r12
0x18000de79  call    ZtUpdateServersGlobal
0x18000de7e  mov     edi, eax
0x18000de80  test    eax, eax
0x18000de82  jnz     loc_18000DF33
0x18000de88  or      qword ptr [rsi], 2
0x18000de8c  test    byte ptr [rbx+8], 10h
0x18000de90  jz      short loc_18000DEB3
0x18000de92  mov     r8, [rsp+68h+arg_30]
0x18000de9a  mov     ecx, ebp
0x18000de9c  mov     rdx, [rbx+40h]
0x18000dea0  call    ZtUpdateTrustedCaGlobal
0x18000dea5  mov     edi, eax
0x18000dea7  test    eax, eax
0x18000dea9  jnz     loc_18000DF33
0x18000deaf  or      qword ptr [rsi], 10h
0x18000deb3  test    byte ptr [rbx+8], 8
0x18000deb7  jz      short loc_18000DED6
0x18000deb9  mov     r8, [rsp+68h+arg_38]
0x18000dec1  mov     ecx, ebp
0x18000dec3  mov     rdx, [rbx+38h]
0x18000dec7  call    ZtUpdateClientCertsGlobal
0x18000decc  mov     edi, eax
0x18000dece  test    eax, eax
0x18000ded0  jnz     short loc_18000DF33
0x18000ded2  or      qword ptr [rsi], 8
0x18000ded6  test    byte ptr [rbx+8], 4
0x18000deda  jz      short loc_18000DF33
0x18000dedc  test    r14b, 40h
0x18000dee0  jz      short loc_18000DEFA
0x18000dee2  mov     r9, [rsp+68h+arg_28]
0x18000deea  mov     ecx, ebp
0x18000deec  mov     r8, [rbx+28h]
0x18000def0  mov     edx, [rbx+30h]
0x18000def3  call    ?ZtDeleteRulesGlobal@@YAJW4_ZTDNS_SETTINGS_TYPE@@KPEAU_DNS_ZT_RULE@@PEAPEAVDnsZtRuleMap@@@Z; ZtDeleteRulesGlobal(_ZTDNS_SETTINGS_TYPE,ulong,_DNS_ZT_RULE *,DnsZtRuleMap * *)
0x18000def8  jmp     short loc_18000DF29
0x18000defa  lea     rdx, [rbx+30h]
0x18000defe  test    r14b, 20h
0x18000df02  jz      short loc_18000DF09
0x18000df04  cmp     dword ptr [rdx], 0
0x18000df07  ja      short loc_18000DF0C
0x18000df09  xor     r15d, r15d
0x18000df0c  mov     rax, [rsp+68h+arg_28]
0x18000df14  mov     r9d, r15d
0x18000df17  mov     r8, [rbx+28h]
0x18000df1b  mov     ecx, ebp
0x18000df1d  mov     edx, [rdx]
0x18000df1f  mov     [rsp+68h+var_48], rax
0x18000df24  call    ?ZtUpdateRulesGlobal@@YAJW4_ZTDNS_SETTINGS_TYPE@@KPEAU_DNS_ZT_RULE@@HPEAPEAVDnsZtRuleMap@@@Z; ZtUpdateRulesGlobal(_ZTDNS_SETTINGS_TYPE,ulong,_DNS_ZT_RULE *,int,DnsZtRuleMap * *)
0x18000df29  mov     edi, eax
0x18000df2b  test    eax, eax
0x18000df2d  jnz     short loc_18000DF33
0x18000df2f  or      qword ptr [rsi], 4
0x18000df33  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000df3a  jz      short loc_18000DF55
0x18000df3c  mov     edx, 0Bh
0x18000df41  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000df48  mov     ecx, 40Bh
0x18000df4d  mov     r9d, edi
0x18000df50  call    WPP_SF_d
0x18000df55  mov     eax, edi
0x18000df57  add     rsp, 30h
0x18000df5b  pop     r15
0x18000df5d  pop     r14
0x18000df5f  pop     r12
0x18000df61  pop     rdi
0x18000df62  pop     rsi
0x18000df63  pop     rbp
0x18000df64  pop     rbx
0x18000df65  retn
```

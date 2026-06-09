# ZtRestoreBackupSettings(_ZTDNS_SETTINGS_TYPE,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,ulong,unsigned __int64)

- ea: `0x18000dd04`
- end: `0x18000dde4`
- name: `?ZtRestoreBackupSettings@@YAXW4_ZTDNS_SETTINGS_TYPE@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@K_K@Z`
- size: `224`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64, __int64, __int64, __int32, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800049b0`

## callees

- `0x18000dd04`
- `0x180010a50`
- `0x180011490`
- `0x180011d64`
- `0x1800121b0`
- `0x180015114`
- `0x180015c1c`

## pseudocode

```c
__int64 __fastcall ZtRestoreBackupSettings(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int32 a8,
        char a9)
{
  __int64 result; // rax
  __int64 v11; // rdi
  _UNKNOWN *retaddr; // [rsp+88h] [rbp+0h] BYREF

  result = (__int64)&retaddr;
  v11 = a1;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    result = WPP_SF_dqqqqqi(a1, a2, a3, a1, a3, a4, a5, a6);
  if ( (a9 & 2) != 0 )
    result = ZtRestoreServersGlobal((unsigned int)v11, a2, a3);
  if ( (a9 & 0x10) != 0 )
    result = ZtRestoreTrustedCaGlobal((unsigned int)v11, a5);
  if ( (a9 & 8) != 0 )
    result = ZtRestoreClientCertConfigGlobal((unsigned int)v11, a6);
  if ( (a9 & 4) != 0 )
    result = ZtRestoreRulesGlobal((unsigned int)v11, a4);
  if ( a9 < 0 )
    result = (unsigned int)_InterlockedExchange((volatile __int32 *)&g_rgZtHelperSettingsState + 5 * v11, a8);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    return WPP_SF_(1035, 13, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18000dd04  mov     rax, rsp
0x18000dd07  push    rbx
0x18000dd08  push    rbp
0x18000dd09  push    rsi
0x18000dd0a  push    rdi
0x18000dd0b  push    r12
0x18000dd0d  push    r14
0x18000dd0f  push    r15
0x18000dd11  sub     rsp, 50h
0x18000dd15  mov     r15, r9
0x18000dd18  movsxd  rdi, ecx
0x18000dd1b  mov     rbp, r8
0x18000dd1e  mov     r12, rdx
0x18000dd21  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000dd28  mov     rbx, [rsp+88h+arg_40]
0x18000dd30  mov     r14, [rsp+88h+arg_28]
0x18000dd38  mov     rsi, [rsp+88h+arg_20]
0x18000dd40  jz      short loc_18000DD5E
0x18000dd42  mov     [rax-40h], rbx
0x18000dd46  mov     [rax-50h], r14
0x18000dd4a  mov     [rax-58h], rsi
0x18000dd4e  mov     [rax-60h], r9
0x18000dd52  mov     r9d, edi
0x18000dd55  mov     [rax-68h], r8
0x18000dd59  call    WPP_SF_dqqqqqi
0x18000dd5e  test    bl, 2
0x18000dd61  jz      short loc_18000DD70
0x18000dd63  mov     r8, rbp
0x18000dd66  mov     rdx, r12
0x18000dd69  mov     ecx, edi
0x18000dd6b  call    ZtRestoreServersGlobal
0x18000dd70  test    bl, 10h
0x18000dd73  jz      short loc_18000DD7F
0x18000dd75  mov     rdx, rsi
0x18000dd78  mov     ecx, edi
0x18000dd7a  call    ZtRestoreTrustedCaGlobal
0x18000dd7f  test    bl, 8
0x18000dd82  jz      short loc_18000DD8E
0x18000dd84  mov     rdx, r14
0x18000dd87  mov     ecx, edi
0x18000dd89  call    ZtRestoreClientCertConfigGlobal
0x18000dd8e  test    bl, 4
0x18000dd91  jz      short loc_18000DD9D
0x18000dd93  mov     rdx, r15
0x18000dd96  mov     ecx, edi
0x18000dd98  call    ?ZtRestoreRulesGlobal@@YAXW4_ZTDNS_SETTINGS_TYPE@@PEAPEAVDnsZtRuleMap@@@Z; ZtRestoreRulesGlobal(_ZTDNS_SETTINGS_TYPE,DnsZtRuleMap * *)
0x18000dd9d  test    bl, bl
0x18000dd9f  jns     short loc_18000DDB6
0x18000dda1  mov     eax, [rsp+88h+arg_38]
0x18000dda8  lea     rcx, [rdi+rdi*4]
0x18000ddac  lea     rdx, g_rgZtHelperSettingsState
0x18000ddb3  xchg    eax, [rdx+rcx*4]
0x18000ddb6  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ddbd  jz      short loc_18000DDD5
0x18000ddbf  mov     edx, 0Dh
0x18000ddc4  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000ddcb  mov     ecx, 40Bh
0x18000ddd0  call    WPP_SF_
0x18000ddd5  add     rsp, 50h
0x18000ddd9  pop     r15
0x18000dddb  pop     r14
0x18000dddd  pop     r12
0x18000dddf  pop     rdi
0x18000dde0  pop     rsi
0x18000dde1  pop     rbp
0x18000dde2  pop     rbx
0x18000dde3  retn
```

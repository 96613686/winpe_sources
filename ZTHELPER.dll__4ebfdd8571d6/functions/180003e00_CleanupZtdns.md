# CleanupZtdns

- ea: `0x180003e00`
- end: `0x180003f51`
- name: `CleanupZtdns`
- size: `337`
- prototype: `int()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003450`

## callees

- `0x180003e00`
- `0x180007630`
- `0x18000dbcc`
- `0x18000dc74`
- `0x18000dcb0`
- `0x180015114`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedServers` at `0x180003e51`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180003e51`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180003eba`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180003eba`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180003eef`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x180003eef`
- `CRYPT32!CertFreeCertificateContext` at `0x180003f0e`
- `CRYPT32!CertFreeCertificateContext` at `0x180003f0e`

## pseudocode

```c
int CleanupZtdns()
{
  __int64 i; // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 j; // rbx
  DnsZtRuleMap *v4; // rcx
  __int64 k; // rbx
  void *v6; // rcx
  __int64 m; // rbx
  void *v8; // rcx
  int result; // eax
  const CERT_CONTEXT *v10; // rcx

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_(1026, 36, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids);
  for ( i = 0; i != 2; ++i )
  {
    v1 = g_pDnsZtServers[i];
    v2 = (unsigned int)g_cDnsZtServers[i];
    if ( g_fVelocityZtdnsApiRefactor )
      ZtFreeTrustedServers(v2, v1);
    else
      DnsFreeZtTrustedServers(v2, v1);
    g_pDnsZtServers[i] = 0;
    g_cDnsZtServers[i] = 0;
  }
  for ( j = 0; j != 2; ++j )
  {
    v4 = (DnsZtRuleMap *)g_rgspDnsZtRuleMap[j];
    if ( v4 )
    {
      DnsZtRuleMap::Release(v4);
      g_rgspDnsZtRuleMap[j] = 0;
    }
  }
  for ( k = 0; k != 2; ++k )
  {
    v6 = (void *)g_rgpZtTrustedCa[k];
    if ( g_fVelocityZtdnsApiRefactor )
      ZtFreeTrustedCa(v6);
    else
      DnsFreeZtTrustedCa(v6);
    g_rgpZtTrustedCa[k] = 0;
  }
  for ( m = 0; m != 2; ++m )
  {
    v8 = (void *)g_rgpZtClientCerts[m];
    if ( g_fVelocityZtdnsApiRefactor )
      result = ZtFreeClientCertConfig(v8);
    else
      result = DnsFreeZtClientCertConfig(v8);
    v10 = (const CERT_CONTEXT *)g_rgpZtClientCertContext[m];
    g_rgpZtClientCerts[m] = 0;
    if ( v10 )
    {
      result = CertFreeCertificateContext(v10);
      g_rgpZtClientCertContext[m] = 0;
    }
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    return WPP_SF_(1026, 37, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180003e00  mov     [rsp+arg_0], rbx
0x180003e05  push    rsi
0x180003e06  sub     rsp, 20h
0x180003e0a  test    byte ptr cs:xmmword_18001F260, 4
0x180003e11  jz      short loc_180003E29
0x180003e13  mov     edx, 24h ; '$'
0x180003e18  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003e1f  mov     ecx, 402h
0x180003e24  call    WPP_SF_
0x180003e29  xor     ebx, ebx
0x180003e2b  lea     rsi, cs:180000000h
0x180003e32  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180003e39  mov     rdx, rva g_pDnsZtServers[rsi+rbx*8]
0x180003e41  mov     ecx, rva g_cDnsZtServers[rsi+rbx*4]
0x180003e48  jz      short loc_180003E51
0x180003e4a  call    ZtFreeTrustedServers
0x180003e4f  jmp     short loc_180003E57
0x180003e51  call    cs:__imp_DnsFreeZtTrustedServers
0x180003e57  mov     rva g_pDnsZtServers[rsi+rbx*8], 0
0x180003e63  mov     rva g_cDnsZtServers[rsi+rbx*4], 0
0x180003e6e  inc     rbx
0x180003e71  cmp     rbx, 2
0x180003e75  jnz     short loc_180003E32
0x180003e77  xor     ebx, ebx
0x180003e79  mov     rcx, rva ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A[rsi+rbx*8]; this
0x180003e81  test    rcx, rcx
0x180003e84  jz      short loc_180003E97
0x180003e86  call    ?Release@DnsZtRuleMap@@QEAAKXZ; DnsZtRuleMap::Release(void)
0x180003e8b  mov     rva ?g_rgspDnsZtRuleMap@@3PAV?$AutoInterface@VDnsZtRuleMap@@@@A[rsi+rbx*8], 0; AutoInterface<DnsZtRuleMap> near * g_rgspDnsZtRuleMap ...
0x180003e97  inc     rbx
0x180003e9a  cmp     rbx, 2
0x180003e9e  jnz     short loc_180003E79
0x180003ea0  xor     ebx, ebx
0x180003ea2  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180003ea9  mov     rcx, rva g_rgpZtTrustedCa[rsi+rbx*8]; lpMem
0x180003eb1  jz      short loc_180003EBA
0x180003eb3  call    ZtFreeTrustedCa
0x180003eb8  jmp     short loc_180003EC0
0x180003eba  call    cs:__imp_DnsFreeZtTrustedCa
0x180003ec0  mov     rva g_rgpZtTrustedCa[rsi+rbx*8], 0
0x180003ecc  inc     rbx
0x180003ecf  cmp     rbx, 2
0x180003ed3  jnz     short loc_180003EA2
0x180003ed5  xor     ebx, ebx
0x180003ed7  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180003ede  mov     rcx, rva g_rgpZtClientCerts[rsi+rbx*8]; lpMem
0x180003ee6  jz      short loc_180003EEF
0x180003ee8  call    ZtFreeClientCertConfig
0x180003eed  jmp     short loc_180003EF5
0x180003eef  call    cs:__imp_DnsFreeZtClientCertConfig
0x180003ef5  mov     rcx, rva g_rgpZtClientCertContext[rsi+rbx*8]; pCertContext
0x180003efd  mov     rva g_rgpZtClientCerts[rsi+rbx*8], 0
0x180003f09  test    rcx, rcx
0x180003f0c  jz      short loc_180003F20
0x180003f0e  call    cs:__imp_CertFreeCertificateContext
0x180003f14  mov     rva g_rgpZtClientCertContext[rsi+rbx*8], 0
0x180003f20  inc     rbx
0x180003f23  cmp     rbx, 2
0x180003f27  jnz     short loc_180003ED7
0x180003f29  test    byte ptr cs:xmmword_18001F260, 4
0x180003f30  jz      short loc_180003F46
0x180003f32  lea     edx, [rbx+23h]
0x180003f35  mov     ecx, 402h
0x180003f3a  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003f41  call    WPP_SF_
0x180003f46  mov     rbx, [rsp+28h+arg_0]
0x180003f4b  add     rsp, 20h
0x180003f4f  pop     rsi
0x180003f50  retn
```

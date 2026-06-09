# ZtRestoreClientCertConfigGlobal

- ea: `0x1800121b0`
- end: `0x18001227d`
- name: `ZtRestoreClientCertConfigGlobal`
- size: `205`
- prototype: `void __fastcall(int, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000dd04`

## callees

- `0x18000dbcc`
- `0x1800121b0`
- `0x180015040`
- `0x180015114`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18001223a`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18001223a`
- `CRYPT32!CertFreeCertificateContext` at `0x180012248`
- `CRYPT32!CertFreeCertificateContext` at `0x180012248`

## pseudocode

```c
void __fastcall ZtRestoreClientCertConfigGlobal(int a1, __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  bool v5; // zf
  LPVOID *v6; // rcx
  const CERT_CONTEXT *v7; // rbx

  v3 = a1;
  v4 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dqq(1035, 0x14u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, a1, a2, 0);
  if ( a2 )
  {
    v4 = *a2;
    *a2 = 0;
  }
  v5 = g_fVelocityZtdnsApiRefactor == 0;
  v6 = (LPVOID *)g_rgpZtClientCerts[v3];
  v7 = (const CERT_CONTEXT *)g_rgpZtClientCertContext[v3];
  g_rgpZtClientCerts[v3] = v4;
  g_rgpZtClientCertContext[v3] = 0;
  if ( v5 )
    DnsFreeZtClientCertConfig(v6);
  else
    ZtFreeClientCertConfig(v6);
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_(1035, 0x15u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids);
}

```

## disassembly

```asm
0x1800121b0  mov     rax, rsp
0x1800121b3  mov     [rax+8], rbx
0x1800121b7  mov     [rax+10h], rsi
0x1800121bb  push    rdi
0x1800121bc  sub     rsp, 30h
0x1800121c0  mov     rbx, rdx
0x1800121c3  movsxd  rsi, ecx
0x1800121c6  xor     edi, edi
0x1800121c8  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800121cf  jz      short loc_1800121F0
0x1800121d1  mov     [rax-10h], rdi
0x1800121d5  lea     edx, [rdi+14h]
0x1800121d8  mov     ecx, 40Bh
0x1800121dd  mov     [rax-18h], rbx
0x1800121e1  mov     r9d, esi
0x1800121e4  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x1800121eb  call    WPP_SF_dqq
0x1800121f0  test    rbx, rbx
0x1800121f3  jz      short loc_1800121FF
0x1800121f5  mov     rdi, [rbx]
0x1800121f8  mov     qword ptr [rbx], 0
0x1800121ff  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180012206  lea     rdx, cs:180000000h
0x18001220d  mov     rcx, rva g_rgpZtClientCerts[rdx+rsi*8]; lpMem
0x180012215  mov     rbx, rva g_rgpZtClientCertContext[rdx+rsi*8]
0x18001221d  mov     rva g_rgpZtClientCerts[rdx+rsi*8], rdi
0x180012225  mov     rva g_rgpZtClientCertContext[rdx+rsi*8], 0
0x180012231  jz      short loc_18001223A
0x180012233  call    ZtFreeClientCertConfig
0x180012238  jmp     short loc_180012240
0x18001223a  call    cs:__imp_DnsFreeZtClientCertConfig
0x180012240  test    rbx, rbx
0x180012243  jz      short loc_18001224E
0x180012245  mov     rcx, rbx; pCertContext
0x180012248  call    cs:__imp_CertFreeCertificateContext
0x18001224e  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012255  jz      short loc_18001226D
0x180012257  mov     edx, 15h
0x18001225c  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x180012263  mov     ecx, 40Bh
0x180012268  call    WPP_SF_
0x18001226d  mov     rbx, [rsp+38h+arg_0]
0x180012272  mov     rsi, [rsp+38h+arg_8]
0x180012277  add     rsp, 30h
0x18001227b  pop     rdi
0x18001227c  retn
```

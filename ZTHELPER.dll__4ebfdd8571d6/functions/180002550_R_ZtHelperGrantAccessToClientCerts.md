# R_ZtHelperGrantAccessToClientCerts

- ea: `0x180002550`
- end: `0x180002644`
- name: `R_ZtHelperGrantAccessToClientCerts`
- size: `244`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002550`
- `0x1800092d0`
- `0x18000f1cc`
- `0x180015008`

## pseudocode

```c
__int64 __fastcall R_ZtHelperGrantAccessToClientCerts(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 21, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, a2);
  if ( !a3 )
  {
    v5 = 87;
    goto LABEL_20;
  }
  if ( !g_fVelocityZtdns )
  {
    v5 = 50;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v7 = 22;
LABEL_18:
    v8 = v5;
    goto LABEL_19;
  }
  if ( a2 > 1 )
  {
    v5 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v7 = 23;
    goto LABEL_18;
  }
  v6 = Rpc_DnsRegistryAccessCheck(0x20019u);
  v5 = v6;
  if ( v6 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v7 = 24;
  }
  else
  {
    v6 = ZtHelperGrantAccessToClientCerts(a2, a3);
    v5 = v6;
    if ( !v6 )
      goto LABEL_20;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v5;
    v7 = 25;
  }
  v8 = v6;
LABEL_19:
  WPP_SF_d(1026, v7, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, v8);
LABEL_20:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 26, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180002550  push    rbx
0x180002552  push    rsi
0x180002553  push    rdi
0x180002554  push    r14
0x180002556  push    r15
0x180002558  sub     rsp, 20h
0x18000255c  mov     rsi, r8
0x18000255f  mov     edi, edx
0x180002561  test    byte ptr cs:xmmword_18001F260, 4
0x180002568  lea     r15, WPP_22a03a71573c3b2e75584fcdd9415dca_Traceguids
0x18000256f  mov     r14d, 402h
0x180002575  jz      short loc_18000258A
0x180002577  mov     edx, 15h
0x18000257c  mov     ecx, r14d
0x18000257f  mov     r9d, edi
0x180002582  mov     r8, r15
0x180002585  call    WPP_SF_d
0x18000258a  test    rsi, rsi
0x18000258d  jnz     short loc_180002597
0x18000258f  lea     ebx, [rsi+57h]
0x180002592  jmp     loc_18000261A
0x180002597  cmp     cs:g_fVelocityZtdns, 0
0x18000259e  jz      short loc_1800025FB
0x1800025a0  cmp     edi, 1
0x1800025a3  ja      short loc_1800025E8
0x1800025a5  mov     ecx, 20019h; DesiredAccess
0x1800025aa  call    Rpc_DnsRegistryAccessCheck
0x1800025af  mov     ebx, eax
0x1800025b1  test    eax, eax
0x1800025b3  jnz     short loc_1800025D8
0x1800025b5  mov     rdx, rsi
0x1800025b8  mov     ecx, edi
0x1800025ba  call    ZtHelperGrantAccessToClientCerts
0x1800025bf  mov     ebx, eax
0x1800025c1  test    eax, eax
0x1800025c3  jz      short loc_18000261A
0x1800025c5  test    byte ptr cs:xmmword_18001F260, 4
0x1800025cc  jz      short loc_180002636
0x1800025ce  mov     edx, 19h
0x1800025d3  mov     r9d, eax
0x1800025d6  jmp     short loc_18000260F
0x1800025d8  test    byte ptr cs:xmmword_18001F260, 4
0x1800025df  jz      short loc_180002636
0x1800025e1  mov     edx, 18h
0x1800025e6  jmp     short loc_1800025D3
0x1800025e8  mov     ebx, 57h ; 'W'
0x1800025ed  test    byte ptr cs:xmmword_18001F260, 4
0x1800025f4  jz      short loc_180002636
0x1800025f6  lea     edx, [rbx-40h]
0x1800025f9  jmp     short loc_18000260C
0x1800025fb  mov     ebx, 32h ; '2'
0x180002600  test    byte ptr cs:xmmword_18001F260, 4
0x180002607  jz      short loc_180002636
0x180002609  lea     edx, [rbx-1Ch]
0x18000260c  mov     r9d, ebx
0x18000260f  mov     r8, r15
0x180002612  mov     ecx, r14d
0x180002615  call    WPP_SF_d
0x18000261a  test    byte ptr cs:xmmword_18001F260, 4
0x180002621  jz      short loc_180002636
0x180002623  mov     edx, 1Ah
0x180002628  mov     ecx, r14d
0x18000262b  mov     r9d, ebx
0x18000262e  mov     r8, r15
0x180002631  call    WPP_SF_d
0x180002636  mov     eax, ebx
0x180002638  add     rsp, 20h
0x18000263c  pop     r15
0x18000263e  pop     r14
0x180002640  pop     rdi
0x180002641  pop     rsi
0x180002642  pop     rbx
0x180002643  retn
```

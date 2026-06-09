# RasRemoveNrptRules

- ea: `0x18005a9f4`
- end: `0x18005abce`
- name: `RasRemoveNrptRules`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800483a0`

## callees

- `0x180005954`
- `0x180028464`
- `0x18005a9f4`
- `0x18005abd4`

## import_xrefs

- `DNSAPI!DnsRemoveNrptRule` at `0x18005aaff`
- `DNSAPI!DnsRemoveNrptRule` at `0x18005aaff`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x18005ab78`
- `DNSAPI!DnsFreeNrptRuleNamesList` at `0x18005ab78`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x18005aa6e`
- `DNSAPI!DnsGetNrptRuleNamesList` at `0x18005aa6e`

## pseudocode

```c
__int64 __fastcall RasRemoveNrptRules(_QWORD *a1, __int64 a2, __int64 a3)
{
  FwPolicy2 *v4; // rcx
  unsigned int NrptRuleNamesList; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int v9; // edi
  _QWORD *v10; // rsi
  int i; // ebp
  const wchar_t *v12; // rcx
  size_t v13; // r8
  __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+18h] BYREF

  v16 = a3;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, a3, 1, 1);
    v4 = WPP_GLOBAL_Control;
  }
  v15 = 0;
  v16 = 0;
  if ( a1 )
  {
    NrptRuleNamesList = DnsGetNrptRuleNamesList(&v15, &v16);
    v6 = NrptRuleNamesList;
    if ( NrptRuleNamesList )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_33:
        if ( v15 )
        {
          DnsFreeNrptRuleNamesList(&v15, v16);
          v4 = WPP_GLOBAL_Control;
        }
        goto LABEL_35;
      }
      v7 = 39;
      v8 = NrptRuleNamesList;
      goto LABEL_31;
    }
    v9 = 0;
    while ( 2 )
    {
      if ( v9 >= v16 )
        goto LABEL_32;
      v10 = a1;
      for ( i = 0; ; i = 1 )
      {
        if ( !v10 || i )
          goto LABEL_21;
        v12 = (const wchar_t *)v10[6];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( !wcsnicmp(v12, *(const wchar_t **)(v15 + 8LL * v9), v13) )
          break;
        v10 = (_QWORD *)*v10;
      }
      v6 = DnsRemoveNrptRule(*(_QWORD *)(v15 + 8LL * v9));
      if ( !v6 )
      {
LABEL_21:
        ++v9;
        continue;
      }
      break;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v7 = 40;
LABEL_30:
    v8 = v6;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v4 + 2), v7, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v8);
LABEL_32:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v6 = 87;
  if ( v4 == (FwPolicy2 *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v7 = 38;
    goto LABEL_30;
  }
LABEL_35:
  if ( v4 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(*((_QWORD *)v4 + 2), 41, &WPP_247047d951ef37ad2b5171979a346086_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18005a9f4  mov     rax, rsp
0x18005a9f7  mov     [rax+10h], rbx
0x18005a9fb  mov     [rax+20h], rbp
0x18005a9ff  mov     [rax+18h], r8d
0x18005aa03  push    rsi
0x18005aa04  push    rdi
0x18005aa05  push    r12
0x18005aa07  push    r14
0x18005aa09  push    r15
0x18005aa0b  sub     rsp, 30h
0x18005aa0f  mov     r14, rcx
0x18005aa12  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa19  lea     rdi, WPP_GLOBAL_Control
0x18005aa20  cmp     rcx, rdi
0x18005aa23  jz      short loc_18005AA4E
0x18005aa25  test    byte ptr [rcx+1Ch], 1
0x18005aa29  jz      short loc_18005AA4E
0x18005aa2b  cmp     byte ptr [rcx+19h], 6
0x18005aa2f  jb      short loc_18005AA4E
0x18005aa31  mov     rcx, [rcx+10h]
0x18005aa35  mov     edx, 25h ; '%'
0x18005aa3a  mov     byte ptr [rax-38h], 1
0x18005aa3e  lea     r9d, [rdx-24h]
0x18005aa42  call    WPP_SF_dc
0x18005aa47  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa4e  xor     r12d, r12d
0x18005aa51  mov     [rsp+58h+arg_0], r12
0x18005aa56  mov     [rsp+58h+arg_10], r12d
0x18005aa5b  test    r14, r14
0x18005aa5e  jz      loc_18005AB35
0x18005aa64  lea     rdx, [rsp+58h+arg_10]
0x18005aa69  lea     rcx, [rsp+58h+arg_0]
0x18005aa6e  call    cs:__imp_DnsGetNrptRuleNamesList
0x18005aa74  mov     ebx, eax
0x18005aa76  test    eax, eax
0x18005aa78  jz      short loc_18005AAAB
0x18005aa7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa81  cmp     rcx, rdi
0x18005aa84  jz      loc_18005AB68
0x18005aa8a  test    byte ptr [rcx+1Ch], 1
0x18005aa8e  jz      loc_18005AB68
0x18005aa94  cmp     byte ptr [rcx+19h], 2
0x18005aa98  jb      loc_18005AB68
0x18005aa9e  lea     edx, [r12+27h]
0x18005aaa3  mov     r9d, eax
0x18005aaa6  jmp     loc_18005AB51
0x18005aaab  mov     edi, r12d
0x18005aaae  cmp     edi, [rsp+58h+arg_10]
0x18005aab2  jnb     loc_18005AB61
0x18005aab8  mov     rsi, r14
0x18005aabb  mov     ebp, r12d
0x18005aabe  test    rsi, rsi
0x18005aac1  jz      short loc_18005AB0B
0x18005aac3  cmp     ebp, 1
0x18005aac6  jnb     short loc_18005AB0B
0x18005aac8  mov     rcx, [rsi+30h]; String1
0x18005aacc  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005aad0  mov     r15d, edi
0x18005aad3  inc     r8; MaxCount
0x18005aad6  cmp     [rcx+r8*2], r12w
0x18005aadb  jnz     short loc_18005AAD3
0x18005aadd  mov     rdx, [rsp+58h+arg_0]
0x18005aae2  mov     rdx, [rdx+r15*8]; String2
0x18005aae6  call    _wcsnicmp
0x18005aaeb  test    eax, eax
0x18005aaed  jz      short loc_18005AAF6
0x18005aaef  mov     rsi, [rsi]
0x18005aaf2  inc     ebp
0x18005aaf4  jmp     short loc_18005AABE
0x18005aaf6  mov     rcx, [rsp+58h+arg_0]
0x18005aafb  mov     rcx, [rcx+r15*8]
0x18005aaff  call    cs:__imp_DnsRemoveNrptRule
0x18005ab05  mov     ebx, eax
0x18005ab07  test    eax, eax
0x18005ab09  jnz     short loc_18005AB0F
0x18005ab0b  inc     edi
0x18005ab0d  jmp     short loc_18005AAAE
0x18005ab0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab16  lea     rax, WPP_GLOBAL_Control
0x18005ab1d  cmp     rcx, rax
0x18005ab20  jz      short loc_18005AB68
0x18005ab22  test    byte ptr [rcx+1Ch], 1
0x18005ab26  jz      short loc_18005AB68
0x18005ab28  cmp     byte ptr [rcx+19h], 2
0x18005ab2c  jb      short loc_18005AB68
0x18005ab2e  mov     edx, 28h ; '('
0x18005ab33  jmp     short loc_18005AB4E
0x18005ab35  mov     ebx, 57h ; 'W'
0x18005ab3a  cmp     rcx, rdi
0x18005ab3d  jz      short loc_18005ABB5
0x18005ab3f  test    byte ptr [rcx+1Ch], 1
0x18005ab43  jz      short loc_18005AB8C
0x18005ab45  cmp     byte ptr [rcx+19h], 2
0x18005ab49  jb      short loc_18005AB8C
0x18005ab4b  lea     edx, [rbx-31h]
0x18005ab4e  mov     r9d, ebx
0x18005ab51  mov     rcx, [rcx+10h]
0x18005ab55  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x18005ab5c  call    WPP_SF_d
0x18005ab61  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab68  cmp     [rsp+58h+arg_0], r12
0x18005ab6d  jz      short loc_18005AB85
0x18005ab6f  mov     edx, [rsp+58h+arg_10]
0x18005ab73  lea     rcx, [rsp+58h+arg_0]
0x18005ab78  call    cs:__imp_DnsFreeNrptRuleNamesList
0x18005ab7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab85  lea     rdi, WPP_GLOBAL_Control
0x18005ab8c  cmp     rcx, rdi
0x18005ab8f  jz      short loc_18005ABB5
0x18005ab91  test    byte ptr [rcx+1Ch], 1
0x18005ab95  jz      short loc_18005ABB5
0x18005ab97  cmp     byte ptr [rcx+19h], 6
0x18005ab9b  jb      short loc_18005ABB5
0x18005ab9d  mov     rcx, [rcx+10h]
0x18005aba1  lea     r8, WPP_247047d951ef37ad2b5171979a346086_Traceguids
0x18005aba8  mov     edx, 29h ; ')'
0x18005abad  mov     r9d, ebx
0x18005abb0  call    WPP_SF_d
0x18005abb5  mov     rbp, [rsp+58h+arg_18]
0x18005abba  mov     eax, ebx
0x18005abbc  mov     rbx, [rsp+58h+arg_8]
0x18005abc1  add     rsp, 30h
0x18005abc5  pop     r15
0x18005abc7  pop     r14
0x18005abc9  pop     r12
0x18005abcb  pop     rdi
0x18005abcc  pop     rsi
0x18005abcd  retn
```

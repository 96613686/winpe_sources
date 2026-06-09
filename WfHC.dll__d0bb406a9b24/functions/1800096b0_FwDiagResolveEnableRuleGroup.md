# FwDiagResolveEnableRuleGroup

- ea: `0x1800096b0`
- end: `0x18000989b`
- name: `FwDiagResolveEnableRuleGroup`
- size: `491`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800096b0`
- `0x180009a50`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180009717`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009717`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000976b`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000976b`
- `FirewallAPI!FWSetFirewallRule` at `0x180009832`
- `FirewallAPI!FWSetFirewallRule` at `0x180009832`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800097d0`
- `FirewallAPI!FWQueryFirewallRules` at `0x1800097d0`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009852`
- `FirewallAPI!FWFreeFirewallRules` at `0x180009852`
- `FirewallAPI!FWClosePolicyStore` at `0x180009861`
- `FirewallAPI!FWClosePolicyStore` at `0x180009861`

## pseudocode

```c
__int64 __fastcall FwDiagResolveEnableRuleGroup(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rbx
  unsigned int v4; // edi
  __int64 *v5; // rbx
  int v6; // esi
  int v7; // eax
  __int128 v8; // [rsp+48h] [rbp-9h] BYREF
  __int128 v9; // [rsp+58h] [rbp+7h] BYREF
  __int64 v10; // [rsp+68h] [rbp+17h]
  __int128 v11; // [rsp+70h] [rbp+1Fh] BYREF
  __int64 v12; // [rsp+80h] [rbp+2Fh]
  int v13; // [rsp+B8h] [rbp+67h] BYREF
  int v14; // [rsp+C0h] [rbp+6Fh] BYREF
  __int64 v15; // [rsp+C8h] [rbp+77h] BYREF
  __int64 *v16; // [rsp+D0h] [rbp+7Fh] BYREF

  if ( !a1 || !*(_QWORD *)(a1 + 16) )
    return 87;
  v13 = 4;
  v14 = 0;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, &v14, &v13);
  if ( !(_DWORD)result )
  {
    v3 = *(_QWORD *)(a1 + 16);
    v10 = 0;
    v12 = 0;
    v15 = 0;
    v16 = 0;
    v13 = 0;
    v9 = 0;
    v8 = 0;
    v11 = 0;
    v4 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v15);
    if ( !v4 )
    {
      *((_QWORD *)&v8 + 1) = &v9;
      *(_QWORD *)&v9 = 8;
      *((_QWORD *)&v11 + 1) = &v8;
      v10 = v3;
      DWORD2(v9) = 5;
      LODWORD(v8) = 1;
      DWORD1(v11) = 1;
      LODWORD(v12) = 0x10000;
      LOWORD(v11) = 545;
      v4 = FWQueryFirewallRules(v15, &v11, 0, &v13, &v16);
      if ( !v4 )
      {
        v5 = v16;
        if ( !v13 || !v16 )
        {
          v4 = 87;
          goto LABEL_16;
        }
        v6 = v14;
        do
        {
          if ( v5[39] )
          {
            v7 = *((_DWORD *)v5 + 10);
            if ( (v7 & v6) != 0 )
            {
              if ( (v7 & ~v6) != 0 )
              {
                v4 = FwDiagSplitRule(v15, v5);
                if ( v4 )
                  break;
              }
              *((_WORD *)v5 + 146) |= 1u;
              v4 = FWSetFirewallRule(v15, v5);
              if ( v4 )
                break;
            }
          }
          v5 = (__int64 *)*v5;
        }
        while ( v5 );
      }
    }
    v5 = v16;
LABEL_16:
    if ( v5 )
      FWFreeFirewallRules(v5);
    if ( v15 )
      FWClosePolicyStore();
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800096b0  mov     r11, rsp
0x1800096b3  push    rbp
0x1800096b4  push    rbx
0x1800096b5  push    rdi
0x1800096b6  lea     rbp, [r11-5Fh]
0x1800096ba  sub     rsp, 90h
0x1800096c1  mov     rbx, rcx
0x1800096c4  test    rcx, rcx
0x1800096c7  jz      loc_18000988B
0x1800096cd  cmp     qword ptr [rcx+10h], 0
0x1800096d2  jz      loc_18000988B
0x1800096d8  mov     [r11-20h], rsi
0x1800096dc  lea     rax, [rbp+57h+arg_0]
0x1800096e0  mov     [r11-78h], rax
0x1800096e4  xor     esi, esi
0x1800096e6  mov     [r11-28h], r14
0x1800096ea  lea     rax, [rbp+57h+arg_8]
0x1800096ee  mov     [r11-80h], rax
0x1800096f2  mov     r14d, 221h
0x1800096f8  mov     ecx, r14d
0x1800096fb  mov     dword ptr [rsp+0A0h+var_80], esi
0x1800096ff  xor     edx, edx
0x180009701  mov     [rbp+57h+arg_0], 4
0x180009708  mov     r9d, 2
0x18000970e  mov     [rbp+57h+arg_8], esi
0x180009711  mov     r8d, 5
0x180009717  call    cs:__imp_FWGetGlobalConfig
0x18000971d  test    eax, eax
0x18000971f  jnz     loc_180009869
0x180009725  mov     rbx, [rbx+10h]
0x180009729  xor     eax, eax
0x18000972b  xorps   xmm0, xmm0
0x18000972e  mov     [rbp+57h+var_40], rax
0x180009732  mov     [rbp+57h+var_28], rax
0x180009736  mov     r9d, 2
0x18000973c  lea     rax, [rbp+57h+arg_10]
0x180009740  mov     [rbp+57h+arg_10], rsi
0x180009744  xorps   xmm1, xmm1
0x180009747  mov     [rsp+28h], rax
0x18000974c  mov     ecx, r14d
0x18000974f  mov     dword ptr [rsp+0A0h+var_80], esi
0x180009753  xor     edx, edx
0x180009755  mov     [rbp+57h+arg_18], rsi
0x180009759  mov     r8d, r9d
0x18000975c  mov     [rbp+57h+arg_0], esi
0x18000975f  movups  [rbp+57h+var_50], xmm0
0x180009763  movups  [rbp+57h+var_60], xmm0
0x180009767  movups  [rbp+57h+var_38], xmm1
0x18000976b  call    cs:__imp_FWOpenPolicyStore
0x180009771  mov     edi, eax
0x180009773  test    eax, eax
0x180009775  jnz     loc_180009846
0x18000977b  mov     rcx, [rbp+57h+arg_10]
0x18000977f  lea     rax, [rbp+57h+var_50]
0x180009783  mov     qword ptr [rbp+57h+var_60+8], rax
0x180009787  lea     r9, [rbp+57h+arg_0]
0x18000978b  lea     rax, [rbp+57h+var_60]
0x18000978f  mov     qword ptr [rbp+57h+var_50], 8
0x180009797  mov     qword ptr [rbp+57h+var_38+8], rax
0x18000979b  lea     rdx, [rbp+57h+var_38]
0x18000979f  lea     rax, [rbp+57h+arg_18]
0x1800097a3  mov     [rbp+57h+var_40], rbx
0x1800097a7  xor     r8d, r8d
0x1800097aa  mov     [rsp+0A0h+var_80], rax
0x1800097af  mov     dword ptr [rbp+57h+var_50+8], 5
0x1800097b6  mov     dword ptr [rbp+57h+var_60], 1
0x1800097bd  mov     dword ptr [rbp+57h+var_38+4], 1
0x1800097c4  mov     dword ptr [rbp+57h+var_28], 10000h
0x1800097cb  mov     word ptr [rbp+57h+var_38], r14w
0x1800097d0  call    cs:__imp_FWQueryFirewallRules
0x1800097d6  mov     edi, eax
0x1800097d8  test    eax, eax
0x1800097da  jnz     short loc_180009846
0x1800097dc  mov     rbx, [rbp+57h+arg_18]
0x1800097e0  cmp     [rbp+57h+arg_0], esi
0x1800097e3  jz      loc_180009884
0x1800097e9  test    rbx, rbx
0x1800097ec  jz      loc_180009884
0x1800097f2  mov     esi, [rbp+57h+arg_8]
0x1800097f5  cmp     qword ptr [rbx+138h], 0
0x1800097fd  jz      short loc_18000983E
0x1800097ff  mov     eax, [rbx+28h]
0x180009802  test    esi, eax
0x180009804  jz      short loc_18000983E
0x180009806  mov     r8d, esi
0x180009809  not     r8d
0x18000980c  and     r8d, eax
0x18000980f  jz      short loc_180009823
0x180009811  mov     rcx, [rbp+57h+arg_10]
0x180009815  mov     rdx, rbx
0x180009818  call    FwDiagSplitRule
0x18000981d  mov     edi, eax
0x18000981f  test    eax, eax
0x180009821  jnz     short loc_180009846
0x180009823  or      word ptr [rbx+124h], 1
0x18000982b  mov     rdx, rbx
0x18000982e  mov     rcx, [rbp+57h+arg_10]
0x180009832  call    cs:__imp_FWSetFirewallRule
0x180009838  mov     edi, eax
0x18000983a  test    eax, eax
0x18000983c  jnz     short loc_180009846
0x18000983e  mov     rbx, [rbx]
0x180009841  test    rbx, rbx
0x180009844  jnz     short loc_1800097F5
0x180009846  mov     rbx, [rbp+57h+arg_18]
0x18000984a  test    rbx, rbx
0x18000984d  jz      short loc_180009858
0x18000984f  mov     rcx, rbx
0x180009852  call    cs:__imp_FWFreeFirewallRules
0x180009858  mov     rcx, [rbp+57h+arg_10]
0x18000985c  test    rcx, rcx
0x18000985f  jz      short loc_180009867
0x180009861  call    cs:__imp_FWClosePolicyStore
0x180009867  mov     eax, edi
0x180009869  mov     rsi, [rsp+88h]
0x180009871  mov     r14, [rsp+0A0h+var_20]
0x180009879  add     rsp, 90h
0x180009880  pop     rdi
0x180009881  pop     rbx
0x180009882  pop     rbp
0x180009883  retn
0x180009884  mov     edi, 57h ; 'W'
0x180009889  jmp     short loc_18000984A
0x18000988b  mov     eax, 57h ; 'W'
0x180009890  add     rsp, 90h
0x180009897  pop     rdi
0x180009898  pop     rbx
0x180009899  pop     rbp
0x18000989a  retn
```

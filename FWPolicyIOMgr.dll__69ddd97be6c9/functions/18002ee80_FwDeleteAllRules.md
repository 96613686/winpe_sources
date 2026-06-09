# FwDeleteAllRules

- ea: `0x18002ee80`
- end: `0x18002ef3d`
- name: `FwDeleteAllRules`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18000463c`
- `0x18001e9ac`
- `0x18002ee80`

## import_xrefs

- `fwbase!FwRegDeleteKey` at `0x18002eeee`
- `fwbase!FwRegDeleteKey` at `0x18002eeee`

## pseudocode

```c
__int64 __fastcall FwDeleteAllRules(__int64 a1, signed int a2)
{
  unsigned int v4; // ebx
  __int64 AppropiateRuleHive; // rsi
  unsigned int i; // edi
  unsigned int v7; // eax

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v4 = 0;
  if ( a2 >= 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  AppropiateRuleHive = FwGetAppropiateRuleHive(a1, a2);
  for ( i = 0; i < *(_DWORD *)AppropiateRuleHive; ++i )
  {
    v7 = FwRegDeleteKey(*(_QWORD *)(a1 + 40), *(_QWORD *)(*(_QWORD *)(AppropiateRuleHive + 8) + 16LL * i));
    v4 = 0;
    if ( v7 != -2147024894 )
      v4 = v7;
    if ( (v4 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v4);
      return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002ee80  push    rbx
0x18002ee82  push    rbp
0x18002ee83  push    rsi
0x18002ee84  push    rdi
0x18002ee85  push    r14
0x18002ee87  sub     rsp, 20h
0x18002ee8b  mov     edi, edx
0x18002ee8d  mov     rbp, rcx
0x18002ee90  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee97  lea     r14, WPP_GLOBAL_Control
0x18002ee9e  cmp     rcx, r14
0x18002eea1  jz      short loc_18002EEBE
0x18002eea3  test    byte ptr [rcx+1Ch], 8
0x18002eea7  jz      short loc_18002EEBE
0x18002eea9  mov     rcx, [rcx+10h]
0x18002eead  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002eeb4  mov     edx, 6Ah ; 'j'
0x18002eeb9  call    WPP_SF_
0x18002eebe  xor     ebx, ebx
0x18002eec0  cmp     edi, 5
0x18002eec3  jl      short loc_18002EECA
0x18002eec5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002eeca  mov     edx, edi
0x18002eecc  mov     rcx, rbp
0x18002eecf  call    ?FwGetAppropiateRuleHive@@YAPEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAU_tag_WF_POLICY_STORE@@W4FW_RULE_TYPE@@@Z; FwGetAppropiateRuleHive(_tag_WF_POLICY_STORE *,FW_RULE_TYPE)
0x18002eed4  mov     rsi, rax
0x18002eed7  xor     edi, edi
0x18002eed9  cmp     edi, [rsi]
0x18002eedb  jnb     short loc_18002EF30
0x18002eedd  mov     rdx, [rsi+8]
0x18002eee1  mov     rcx, [rbp+28h]
0x18002eee5  mov     eax, edi
0x18002eee7  add     rax, rax
0x18002eeea  mov     rdx, [rdx+rax*8]
0x18002eeee  call    cs:__imp_FwRegDeleteKey
0x18002eef4  xor     ebx, ebx
0x18002eef6  cmp     eax, 80070002h
0x18002eefb  cmovnz  ebx, eax
0x18002eefe  test    ebx, ebx
0x18002ef00  js      short loc_18002EF06
0x18002ef02  inc     edi
0x18002ef04  jmp     short loc_18002EED9
0x18002ef06  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef0d  cmp     rcx, r14
0x18002ef10  jz      short loc_18002EF30
0x18002ef12  test    byte ptr [rcx+1Ch], 1
0x18002ef16  jz      short loc_18002EF30
0x18002ef18  mov     rcx, [rcx+10h]
0x18002ef1c  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18002ef23  mov     edx, 6Bh ; 'k'
0x18002ef28  mov     r9d, ebx
0x18002ef2b  call    WPP_SF_d
0x18002ef30  mov     eax, ebx
0x18002ef32  add     rsp, 20h
0x18002ef36  pop     r14
0x18002ef38  pop     rdi
0x18002ef39  pop     rsi
0x18002ef3a  pop     rbp
0x18002ef3b  pop     rbx
0x18002ef3c  retn
```

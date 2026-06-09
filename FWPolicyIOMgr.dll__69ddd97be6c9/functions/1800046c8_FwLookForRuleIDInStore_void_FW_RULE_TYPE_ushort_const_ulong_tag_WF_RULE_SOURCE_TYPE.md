# FwLookForRuleIDInStore(void *,FW_RULE_TYPE,ushort const *,ulong *,_tag_WF_RULE_SOURCE_TYPE *)

- ea: `0x1800046c8`
- end: `0x18000486b`
- name: `?FwLookForRuleIDInStore@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAKPEAW4_tag_WF_RULE_SOURCE_TYPE@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(__int64, signed int, __int64, _DWORD *, _DWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004320`
- `0x1800044f0`
- `0x1800049e0`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x18000463c`
- `0x1800046c8`
- `0x180004874`
- `0x18001e9ac`
- `0x18001f650`

## import_xrefs

- `fwbase!FwRegOpenKey` at `0x18000477f`
- `fwbase!FwRegOpenKey` at `0x18000477f`
- `fwbase!FwRegCloseKey` at `0x1800047bb`
- `fwbase!FwRegCloseKey` at `0x1800047e4`
- `fwbase!FwRegCloseKey` at `0x1800047bb`
- `fwbase!FwRegCloseKey` at `0x1800047e4`

## pseudocode

```c
__int64 __fastcall FwLookForRuleIDInStore(__int64 a1, signed int a2, __int64 a3, _DWORD *a4, _DWORD *a5)
{
  int v8; // ebx
  __int64 AppropiateRuleHive; // rsi
  unsigned int i; // edi
  LPCOLESTR v11; // rcx
  __int64 v13; // rdx
  int v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h]
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  int v17; // [rsp+48h] [rbp-20h] BYREF

  v15 = a3;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v16 = 0;
  v8 = 0;
  v17 = 0;
  if ( a2 >= 5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a4 = 0;
  AppropiateRuleHive = FwGetAppropiateRuleHive(a1, a2);
  for ( i = 0; i < *(_DWORD *)AppropiateRuleHive; ++i )
  {
    v8 = FwRegOpenKey(*(_QWORD *)(a1 + 40), *(_QWORD *)(*(_QWORD *)(AppropiateRuleHive + 8) + 16LL * i), 9, &v16, &v17);
    if ( v8 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 231;
LABEL_23:
        WPP_SF_d(*((_QWORD *)v11 + 2), v13, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v8);
      }
LABEL_16:
      FwRegCloseKey(v16);
      return (unsigned int)v8;
    }
    if ( v17 )
    {
      v14 = 0;
      v8 = FwAdvPolicyLookForRuleID(v16, v15, &v14);
      if ( v8 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v13 = 232;
          goto LABEL_23;
        }
        goto LABEL_16;
      }
      if ( v14 )
      {
        *a4 += v14;
        *a5 = *(_DWORD *)(*(_QWORD *)(AppropiateRuleHive + 8) + 16LL * i + 8);
      }
      FwRegCloseKey(v16);
      v16 = 0;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800046c8  push    rbp
0x1800046ca  push    rbx
0x1800046cb  push    rsi
0x1800046cc  push    rdi
0x1800046cd  push    r12
0x1800046cf  push    r13
0x1800046d1  push    r14
0x1800046d3  push    r15
0x1800046d5  mov     rbp, rsp
0x1800046d8  sub     rsp, 68h
0x1800046dc  mov     rax, cs:__security_cookie
0x1800046e3  xor     rax, rsp
0x1800046e6  mov     [rbp+var_18], rax
0x1800046ea  mov     r12, [rbp+arg_20]
0x1800046ee  mov     r15, r9
0x1800046f1  mov     [rbp+var_30], r8
0x1800046f5  mov     edi, edx
0x1800046f7  mov     r13, rcx
0x1800046fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180004701  lea     rax, WPP_GLOBAL_Control
0x180004708  cmp     rcx, rax
0x18000470b  jz      short loc_180004728
0x18000470d  test    byte ptr [rcx+1Ch], 8
0x180004711  jz      short loc_180004728
0x180004713  mov     rcx, [rcx+10h]
0x180004717  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18000471e  mov     edx, 0E6h
0x180004723  call    WPP_SF_
0x180004728  xor     r14d, r14d
0x18000472b  mov     [rbp+var_28], r14
0x18000472f  mov     ebx, r14d
0x180004732  mov     [rbp+var_20], r14d
0x180004736  cmp     edi, 5
0x180004739  jge     loc_180004829
0x18000473f  mov     edx, edi
0x180004741  mov     [r15], r14d
0x180004744  mov     rcx, r13
0x180004747  call    ?FwGetAppropiateRuleHive@@YAPEAU_tag_WF_POLICY_STORE_HIVE_LIST@@PEAU_tag_WF_POLICY_STORE@@W4FW_RULE_TYPE@@@Z; FwGetAppropiateRuleHive(_tag_WF_POLICY_STORE *,FW_RULE_TYPE)
0x18000474c  mov     rsi, rax
0x18000474f  mov     edi, r14d
0x180004752  cmp     edi, [rsi]
0x180004754  jnb     loc_1800047EA
0x18000475a  mov     rdx, [rsi+8]
0x18000475e  lea     rax, [rbp+var_20]
0x180004762  mov     rcx, [r13+28h]
0x180004766  lea     r9, [rbp+var_28]
0x18000476a  mov     r14d, edi
0x18000476d  mov     r8d, 9
0x180004773  add     r14, r14
0x180004776  mov     [rsp+68h+var_48], rax
0x18000477b  mov     rdx, [rdx+r14*8]
0x18000477f  call    cs:__imp_FwRegOpenKey
0x180004785  mov     ebx, eax
0x180004787  test    eax, eax
0x180004789  js      short loc_1800047CD
0x18000478b  cmp     [rbp+var_20], 0
0x18000478f  jz      short loc_1800047C9
0x180004791  mov     rdx, [rbp+var_30]
0x180004795  lea     r8, [rbp+var_38]
0x180004799  mov     rcx, [rbp+var_28]
0x18000479d  mov     [rbp+var_38], 0
0x1800047a4  call    FwAdvPolicyLookForRuleID
0x1800047a9  mov     ebx, eax
0x1800047ab  test    eax, eax
0x1800047ad  js      short loc_180004809
0x1800047af  mov     eax, [rbp+var_38]
0x1800047b2  cmp     eax, 1
0x1800047b5  jnb     short loc_180004833
0x1800047b7  mov     rcx, [rbp+var_28]
0x1800047bb  call    cs:__imp_FwRegCloseKey
0x1800047c1  mov     [rbp+var_28], 0
0x1800047c9  inc     edi
0x1800047cb  jmp     short loc_180004752
0x1800047cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047d4  lea     rax, WPP_GLOBAL_Control
0x1800047db  cmp     rcx, rax
0x1800047de  jnz     short loc_180004848
0x1800047e0  mov     rcx, [rbp+var_28]
0x1800047e4  call    cs:__imp_FwRegCloseKey
0x1800047ea  mov     eax, ebx
0x1800047ec  mov     rcx, [rbp+var_18]
0x1800047f0  xor     rcx, rsp; StackCookie
0x1800047f3  call    __security_check_cookie
0x1800047f8  add     rsp, 68h
0x1800047fc  pop     r15
0x1800047fe  pop     r14
0x180004800  pop     r13
0x180004802  pop     r12
0x180004804  pop     rdi
0x180004805  pop     rsi
0x180004806  pop     rbx
0x180004807  pop     rbp
0x180004808  retn
0x180004809  mov     rcx, cs:WPP_GLOBAL_Control
0x180004810  lea     rax, WPP_GLOBAL_Control
0x180004817  cmp     rcx, rax
0x18000481a  jz      short loc_1800047E0
0x18000481c  test    byte ptr [rcx+1Ch], 1
0x180004820  jz      short loc_1800047E0
0x180004822  mov     edx, 0E8h
0x180004827  jmp     short loc_180004853
0x180004829  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000482e  jmp     loc_18000473F
0x180004833  add     [r15], eax
0x180004836  mov     rax, [rsi+8]
0x18000483a  mov     ecx, [rax+r14*8+8]
0x18000483f  mov     [r12], ecx
0x180004843  jmp     loc_1800047B7
0x180004848  test    byte ptr [rcx+1Ch], 1
0x18000484c  jz      short loc_1800047E0
0x18000484e  mov     edx, 0E7h
0x180004853  mov     rcx, [rcx+10h]
0x180004857  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18000485e  mov     r9d, ebx
0x180004861  call    WPP_SF_d
0x180004866  jmp     loc_1800047E0
```

# GetPredefinedSvcRulesFromStore(void *,_tag_FW_PROFILE_TYPE,ushort const *,_tag_FW_RULE * *)

- ea: `0x18001e068`
- end: `0x18001e159`
- name: `?GetPredefinedSvcRulesFromStore@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAU_tag_FW_RULE@@@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800308f8`
- `0x180030ab8`

## callees

- `0x180009080`
- `0x18000b8c0`
- `0x18001e068`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e0ec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e0ec`
- `fwbase!FwReportReturnError` at `0x18001e124`
- `fwbase!FwReportReturnError` at `0x18001e151`
- `fwbase!FwReportReturnError` at `0x18001e124`
- `fwbase!FwReportReturnError` at `0x18001e151`
- `FWPolicyIOMgr!FwCopyRule` at `0x18001e0fc`
- `FWPolicyIOMgr!FwCopyRule` at `0x18001e0fc`

## pseudocode

```c
__int64 __fastcall GetPredefinedSvcRulesFromStore(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  signed int v9; // ebx
  _QWORD *i; // rdi
  __int64 v11; // rcx
  int v12; // eax
  __int64 v14; // rdx
  _QWORD *v15; // [rsp+30h] [rbp-48h] BYREF
  int v16; // [rsp+38h] [rbp-40h] BYREF

  v15 = 0;
  v16 = 0;
  v6 = FWEnumFirewallRules(a1, 196608, a2, 7, (__int64)&v16, (__int64)&v15);
  v9 = v6;
  if ( v6 > 0 )
    v9 = (unsigned __int16)v6 | 0x80070000;
  if ( v9 < 0 )
  {
    v14 = (unsigned int)v9;
LABEL_16:
    FwReportReturnError("GetPredefinedSvcRulesFromStore", v14);
  }
  else
  {
    for ( i = v15; i; i = (_QWORD *)*i )
    {
      v11 = i[39];
      if ( v11 && !(unsigned int)_o__wcsicmp(v11, a3) )
      {
        v12 = FwCopyRule(i, a4);
        v9 = v12;
        if ( v12 < 0 )
        {
          v14 = (unsigned int)v12;
          goto LABEL_16;
        }
        a4 = (_QWORD *)*a4;
      }
    }
  }
  FWFreeFirewallRules((__int64)v15, v7, v8);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("GetPredefinedSvcRulesFromStore", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e068  mov     r11, rsp
0x18001e06b  push    rbx
0x18001e06c  push    rbp
0x18001e06d  push    rsi
0x18001e06e  push    rdi
0x18001e06f  sub     rsp, 58h
0x18001e073  mov     rax, cs:__security_cookie
0x18001e07a  xor     rax, rsp
0x18001e07d  mov     [rsp+78h+var_38], rax
0x18001e082  lea     rax, [r11-48h]
0x18001e086  mov     qword ptr [r11-48h], 0
0x18001e08e  mov     [r11-50h], rax
0x18001e092  mov     rbp, r8
0x18001e095  lea     rax, [r11-40h]
0x18001e099  mov     [rsp+78h+var_40], 0
0x18001e0a1  mov     rsi, r9
0x18001e0a4  mov     [r11-58h], rax
0x18001e0a8  mov     r8d, edx
0x18001e0ab  mov     r9d, 7
0x18001e0b1  mov     edx, 30000h
0x18001e0b6  call    FWEnumFirewallRules
0x18001e0bb  mov     ebx, eax
0x18001e0bd  test    eax, eax
0x18001e0bf  jle     short loc_18001E0CA
0x18001e0c1  movzx   ebx, ax
0x18001e0c4  or      ebx, 80070000h
0x18001e0ca  test    ebx, ebx
0x18001e0cc  js      short loc_18001E144
0x18001e0ce  mov     rdi, [rsp+78h+var_48]
0x18001e0d3  test    rdi, rdi
0x18001e0d6  jz      short loc_18001E10D
0x18001e0d8  mov     rcx, [rdi+138h]
0x18001e0df  test    rcx, rcx
0x18001e0e2  jnz     short loc_18001E0E9
0x18001e0e4  mov     rdi, [rdi]
0x18001e0e7  jmp     short loc_18001E0D3
0x18001e0e9  mov     rdx, rbp
0x18001e0ec  call    cs:__imp__o__wcsicmp
0x18001e0f2  test    eax, eax
0x18001e0f4  jnz     short loc_18001E0E4
0x18001e0f6  mov     rdx, rsi
0x18001e0f9  mov     rcx, rdi
0x18001e0fc  call    cs:__imp_FwCopyRule
0x18001e102  mov     ebx, eax
0x18001e104  test    eax, eax
0x18001e106  js      short loc_18001E148
0x18001e108  mov     rsi, [rsi]
0x18001e10b  jmp     short loc_18001E0E4
0x18001e10d  mov     rcx, [rsp+78h+var_48]
0x18001e112  call    FWFreeFirewallRules
0x18001e117  test    ebx, ebx
0x18001e119  jns     short loc_18001E12C
0x18001e11b  mov     edx, ebx
0x18001e11d  lea     rcx, aGetpredefineds; "GetPredefinedSvcRulesFromStore"
0x18001e124  call    cs:__imp_FwReportReturnError
0x18001e12a  mov     ebx, eax
0x18001e12c  mov     eax, ebx
0x18001e12e  mov     rcx, [rsp+78h+var_38]
0x18001e133  xor     rcx, rsp; StackCookie
0x18001e136  call    __security_check_cookie
0x18001e13b  add     rsp, 58h
0x18001e13f  pop     rdi
0x18001e140  pop     rsi
0x18001e141  pop     rbp
0x18001e142  pop     rbx
0x18001e143  retn
0x18001e144  mov     edx, ebx
0x18001e146  jmp     short loc_18001E14A
0x18001e148  mov     edx, eax
0x18001e14a  lea     rcx, aGetpredefineds; "GetPredefinedSvcRulesFromStore"
0x18001e151  call    cs:__imp_FwReportReturnError
0x18001e157  jmp     short loc_18001E10D
```

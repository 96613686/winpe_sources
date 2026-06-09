# GetPredefinedSvcRulesFromStore(void *,_tag_FW_PROFILE_TYPE,ushort const *,_tag_FW_RULE * *)

- ea: `0x18001f8c4`
- end: `0x18001f9d2`
- name: `?GetPredefinedSvcRulesFromStore@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAU_tag_FW_RULE@@@Z`
- size: `270`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032ba8`
- `0x180032d78`

## callees

- `0x180009780`
- `0x18000c3f0`
- `0x18001f8c4`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f94c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001f94c`
- `fwbase!FwReportReturnError` at `0x18001f990`
- `fwbase!FwReportReturnError` at `0x18001f9c4`
- `fwbase!FwReportReturnError` at `0x18001f990`
- `fwbase!FwReportReturnError` at `0x18001f9c4`
- `FWPolicyIOMgr!FwCopyRule` at `0x18001f962`
- `FWPolicyIOMgr!FwCopyRule` at `0x18001f962`

## pseudocode

```c
__int64 __fastcall GetPredefinedSvcRulesFromStore(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  int v6; // eax
  signed int v7; // ebx
  _QWORD *i; // rdi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v12; // rdx
  _QWORD *v13; // [rsp+30h] [rbp-48h] BYREF
  int v14; // [rsp+38h] [rbp-40h] BYREF

  v13 = 0;
  v14 = 0;
  v6 = FWEnumFirewallRules(a1, 196608, a2, 7, (__int64)&v14, (__int64)&v13);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v12 = (unsigned int)v7;
LABEL_16:
    FwReportReturnError("GetPredefinedSvcRulesFromStore", v12);
  }
  else
  {
    for ( i = v13; i; i = (_QWORD *)*i )
    {
      v9 = i[39];
      if ( v9 && !(unsigned int)_o__wcsicmp(v9, a3) )
      {
        v10 = FwCopyRule(i, a4);
        v7 = v10;
        if ( v10 < 0 )
        {
          v12 = (unsigned int)v10;
          goto LABEL_16;
        }
        a4 = (_QWORD *)*a4;
      }
    }
  }
  FWFreeFirewallRules((__int64)v13);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("GetPredefinedSvcRulesFromStore", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001f8c4  mov     r11, rsp
0x18001f8c7  push    rbx
0x18001f8c8  push    rbp
0x18001f8c9  push    rsi
0x18001f8ca  push    rdi
0x18001f8cb  sub     rsp, 58h
0x18001f8cf  mov     rax, cs:__security_cookie
0x18001f8d6  xor     rax, rsp
0x18001f8d9  mov     [rsp+78h+var_38], rax
0x18001f8de  lea     rax, [r11-48h]
0x18001f8e2  mov     qword ptr [r11-48h], 0
0x18001f8ea  mov     [r11-50h], rax
0x18001f8ee  mov     rbp, r8
0x18001f8f1  lea     rax, [r11-40h]
0x18001f8f5  mov     [rsp+78h+var_40], 0
0x18001f8fd  mov     rsi, r9
0x18001f900  mov     [r11-58h], rax
0x18001f904  mov     r8d, edx
0x18001f907  mov     r9d, 7
0x18001f90d  mov     edx, 30000h
0x18001f912  call    FWEnumFirewallRules
0x18001f917  mov     ebx, eax
0x18001f919  test    eax, eax
0x18001f91b  jle     short loc_18001F926
0x18001f91d  movzx   ebx, ax
0x18001f920  or      ebx, 80070000h
0x18001f926  test    ebx, ebx
0x18001f928  js      loc_18001F9B7
0x18001f92e  mov     rdi, [rsp+78h+var_48]
0x18001f933  test    rdi, rdi
0x18001f936  jz      short loc_18001F979
0x18001f938  mov     rcx, [rdi+138h]
0x18001f93f  test    rcx, rcx
0x18001f942  jnz     short loc_18001F949
0x18001f944  mov     rdi, [rdi]
0x18001f947  jmp     short loc_18001F933
0x18001f949  mov     rdx, rbp
0x18001f94c  call    cs:__imp__o__wcsicmp
0x18001f953  nop     dword ptr [rax+rax+00h]
0x18001f958  test    eax, eax
0x18001f95a  jnz     short loc_18001F944
0x18001f95c  mov     rdx, rsi
0x18001f95f  mov     rcx, rdi
0x18001f962  call    cs:__imp_FwCopyRule
0x18001f969  nop     dword ptr [rax+rax+00h]
0x18001f96e  mov     ebx, eax
0x18001f970  test    eax, eax
0x18001f972  js      short loc_18001F9BB
0x18001f974  mov     rsi, [rsi]
0x18001f977  jmp     short loc_18001F944
0x18001f979  mov     rcx, [rsp+78h+var_48]
0x18001f97e  call    FWFreeFirewallRules
0x18001f983  test    ebx, ebx
0x18001f985  jns     short loc_18001F99E
0x18001f987  mov     edx, ebx
0x18001f989  lea     rcx, aGetpredefineds; "GetPredefinedSvcRulesFromStore"
0x18001f990  call    cs:__imp_FwReportReturnError
0x18001f997  nop     dword ptr [rax+rax+00h]
0x18001f99c  mov     ebx, eax
0x18001f99e  mov     eax, ebx
0x18001f9a0  mov     rcx, [rsp+78h+var_38]
0x18001f9a5  xor     rcx, rsp; StackCookie
0x18001f9a8  call    __security_check_cookie
0x18001f9ad  add     rsp, 58h
0x18001f9b1  pop     rdi
0x18001f9b2  pop     rsi
0x18001f9b3  pop     rbp
0x18001f9b4  pop     rbx
0x18001f9b5  retn
0x18001f9b7  mov     edx, ebx
0x18001f9b9  jmp     short loc_18001F9BD
0x18001f9bb  mov     edx, eax
0x18001f9bd  lea     rcx, aGetpredefineds; "GetPredefinedSvcRulesFromStore"
0x18001f9c4  call    cs:__imp_FwReportReturnError
0x18001f9cb  nop     dword ptr [rax+rax+00h]
0x18001f9d0  jmp     short loc_18001F979
```
